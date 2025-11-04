Checking Data Integrity
*********

Along with ensuring that we have all data files - and restoring the ones which we do not have - it is also useful to check the integrity of our data. 
In the :bdg-warning:`file transfer process` it is possible that files become corrupted: that they do not contain the complete and accurate data. 

At the :bdg-danger:`DCCN`, it is typically recommended to use :bdg-dark:`Uploader` and the automatic upload protocol for the MEG and MRI. 
These processes transfer directly to the :bdg-primary:`RDR` and :bdg-primary:`Project Folder` - however, after this process you may unintentionally change some files. 
If you use another tool, such as :bdg-dark:`Cyberduck` or something else, you may even unintentionally upload the wrong file. 
Thus, we will want to ensure that we use the correct, uncorrupted files in our analyses: we check the integrity of our data. 
To do this, we will use a :bdg-warning:`hash algorithm`.

Hash Algorithm
=======

A :bdg-warning:`hash algorithm` takes data as an input - for instance, a file - and produces a string of characters. 
This string of characters - called a hash or digest - can be used to compare the contents of one file to another. 
There are multiple types of :bdg-warning:`hash algorithms`, but each is designed to:

* Uniquely identify a file's contents
* Be irreversible
* Be fast (and computationally inexpensive)

The most commonly used :bdg-warning:`hash algorithm` is the SHA-256 algorithm, which produces a 64-character hexidecimal string (each hexidecimal character has 4 digits, hence the 256).

Practice Checking Data Integrity
=======

Let's first see a demonstration of how the SHA-256 algorithm works. 
To do this, we will need a file to check. 
To illustrate how the :bdg-warning:`hash algorithm` works, let's create a new file which contains all of our raw behavioral data: ``/project/3010000.05/XXXXXXX.XX/raw/longData.csv``.

::

    cd /project/3010000.05/XXXXXXX.XX/scripts
    Rscript combineData.R /project/3010000.05/XXXXXXX.XX/raw/

If you open this file, you will see that it has many rows of data - one for each trial, per subject in our "experiment". 

1. Compute the hash/digest for ``/project/3010000.05/XXXXXXX.XX/raw/longData.csv``

* Open the terminal emulator in TigerVNC
* Type ``sha256sum /project/3010000.05/XXXXXXX.XX/raw/longData.csv``

2. Check if the hash/digest changes depending on the file name and location

* Duplicate ``/project/3010000.05/XXXXXXX.XX/raw/longData.csv`` as ``/project/3010000.05/XXXXXXX.XX/raw/copyLongData.csv``
* Type ``sha256sum /project/3010000.05/XXXXXXX.XX/raw/copyLongData.csv``
* Compare the hash/digest from ``/project/3010000.05/XXXXXXX.XX/raw/longData.csv`` to ``/project/3010000.05/XXXXXXX.XX/raw/longData.csv``: these should be identical

3. Check if the hash/digest catches data falsification

* Open ``/project/3010000.05/XXXXXXX.XX/raw/longData.csv`` in text editor, and change **only one** digit
* Save this file and close it
* Type ``sha256sum /project/3010000.05/XXXXXXX.XX/raw/copyLongData.csv``
* Compare the hash/digest from this to the hash/digest from before you falsified data: these should be very different

4. Directly compare the hash/digest from one file to another

.. dropdown:: Answer

    ::

        if [ "$(sha256sum /project/3010000.05/XXXXXXX.XX/raw/copyLongData.csv | awk '{print $1}')" = "$(sha256sum /project/3010000.05/XXXXXXX.XX/raw/longData.csv | awk '{print $1}')" ]; then
            echo "Files are identical."
        else
            echo "One of the Files is corrupted"
        fi

Advanced Example: Replacing Corrupted Files
=======

Now, you know how to compare the SHA-256 sum of one file to another, in order to see if they have the same data. 
From the last lesson, you also know how to restore files in a missing folder. 
What would be nice to do now is to combine these two processes: let's edit ``/project/3010000.05/XXXXXXX.XX/scripts/restoreMissing.sh`` to do two new things.
The first thing we want to do is to check data integrity, and - if we find that the data in our :bdg-primary:`Project Folder` has been changed, we want to then restore the changes files. 

We need to first delete and corrupt some files so that we can go back and restore them. 

1. Start a TigerVNC session

2. Run ``/project/3010000.05/scripts/deleteAndCorrupt.sh`` 

Open the terminal emulator and run the following code

::

    cd /project/3010000.05/scripts/
    chmod +x deleteAndCorrupt.sh
    ./deleteAndCorrupt.sh /project/3010000.05/XXXXXXX.XX/raw/

3. Create ``/project/3010000.05/XXXXXXX.XX/scripts/checkIntegrity.sh`` 

4. Write a script which restores the corrupted files recursively

.. dropdown:: Hint 1: Find the Folder Each File Should Be In

    ::

        #!/bin/bash
        BASE_PATH="/project/3010000.05/XXXXXXX.XX"
        MANIFEST="$BASE_PATH/docs/MANIFEST.txt"

        while read -r sha path; do

            local_path="$BASE_PATH/$path"
            dir_path=$(dirname "$local_path")

        done < "$MANIFEST"

.. dropdown:: Hint 2: Check the SHA-256 sum of a file in the :bdg-primary:`DAC` 

    We cannot compute the SHA-256 (or any other hash/digest) for a file in the :bdg-primary:`RDR`. 
    Luckily, you can download a manifest file from the :bdg-primary:`RDR` which contains the SHA-256 for **each** file within a collection. 
    
    1. Log in to https://data.ru.nl
    2. Go to ``My Collections``
    3. Open ``di.dccn.DAC_3010000.05_873``
    4. Navigate to the ``Manifest`` tab
    5. Click ``Generate manifest file``
    6. Move the ``MANIFEST.txt`` file to ``/project/3010000.05/XXXXXXX.XX/docs``

.. dropdown:: Answer 

    ::

        #!/bin/bash
        if [ -z "$1" ]; then
            echo "Usage: $0 /project/3010000.05/XXXXXXX.XX"
            exit 1
        fi
        BASE_PATH="$1"
        REPO_PATH="$2"
        MANIFEST="$BASE_PATH/docs/MANIFEST.txt"

        while read -r sha path; do

            local_path="$BASE_PATH/$path"
            dir_path=$(dirname "$local_path")

            if [[ "$path" == *old* ]]; then
                continue
            else
                echo "$dir_path/"
            fi

            if [ ! -d "$dir_path" ]; then
                mkdir -p "$dir_path/"
                echo "Made folder $dir_path"
                continue
                
            fi

            if [ -d "$local_path" ]; then
                local_sha=$(sha256sum "$local_path" | awk '{print $1}')
                if [ "$sha" != "$local_sha" ]; then
                    repocli get "$REPO_PATH/$path" "$dir_path"
                    echo "Replaced corrupted file $dir_path"
                fi
            else
                repocli get "$REPO_PATH/$path" "$dir_path"
                echo "Restored repository file $REPO_PATH/$path to $dir_path"		
            fi

        done < "$MANIFEST"

Now save this file and run it in the terminal by typing the following:

::

    cd /project/3010000.05/XXXXXXX.XX/scripts
    chmod +x checkIntegrity.sh
    ./checkIntegrity.sh "/project/3010000.05/XXXXXXX.XX" "dccn/DAC_3010000.05_873"