Checking Data Integrity
*********

Along with ensuring that we have all data files - and restoring the ones which we do not have - it is also useful to check the integrity of our data. 
In the :bdg-warning:`file transfer process` it is possible that files become corrupted: that they do not contain the complete and accurate data. 

At the :bdg-danger:`DCCN`, we it is typically recommended to use :bdg-dark:`Uploader` and the automatic upload protocol for the MEG and MRI. 
These processes transfer directly to the :bdg-primary:`RDR` and :bdg-primary:`Project Folder` - however, after this process you may unintentionally change some files. 
If you use another tool, such as :bdg-dark:`Cyberduck`, :bdg-dark:`FileZilla`, or something else you may even unintentionally upload the wrong file. 
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
To illustrate how the :bdg-warning:`hash algorithm` works, let's use ``/project/3010000.05/raw/longData.csv``.
If you open this file, you will see that it has many rows of data - one for each trial, per subject in our "experiment". 

1. Compute the hash/digest for ``/project/3010000.05/raw/longData.csv``

* Open the terminal emulator in TigerVNC
* Type ``sha256sum /project/3010000.05/raw/longData.csv``

2. Check if the hash/digest changes depending on the file name and location

* Duplicate ``/project/3010000.05/raw/longData.csv`` as ``/project/3010000.05/XXXXXXX.XX/raw/copyLongData.csv``
* Type ``sha256sum /project/3010000.05/XXXXXXX.XX/raw/copyLongData.csv``
* Compare the hash/digest from ``/project/3010000.05/raw/longData.csv`` to ``/project/3010000.05/XXXXXXX.XX/raw/longData.csv``: these should be identical

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
            echo "A file is corrupted"
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

3. Edit ``/project/3010000.05/XXXXXXX.XX/scripts/restoreMissing.sh``

Open ``/project/3010000.05/XXXXXXX.XX/scripts/restoreMissing.sh`` in your text editor. 
Add a statement which goes through each file in each folder of the :bdg-primary:`Project Folder`, comparing its hash/digest to that of the corresponding :bdg-primary:`DAC` folder.
Make sure to save the file upon completion. 

.. dropdown:: Hint 1: Recursively Enumerate Files in a Subject's Folder

    ::

        find "/project/3010000.05/XXXXXXX.XX/raw/$sub_dir" -type f

.. dropdown:: Hint 2: Check the SHA-256 sum of a file in the :bdg-primary:`DAC`

    We cannot compute the SHA-256 (or any other hash/digest) for a file in the :bdg-primary:`RDR`. 
    Thus, we will need to get all of the files in each :bdg-primary:`RDR` subject folder, so that we can do this comparison. 

    ::

        repocli get "dccn/DAC_3010000.05_873/raw/"$sub_dir "/project/3010000.05/XXXXXXX.XX/temp/

.. dropdown:: Answer

    ::

        #!/bin/bash
        for sub_dir in $(repocli ls dccn/DAC_3010000.05_873/raw/); do 
            if [ ! -d "/project/3010000.05/XXXXXXX.XX/raw/"$sub_dir ]; then
                repocli get "dccn/DAC_3010000.05_873/raw/"$sub_dir "/project/3010000.05/XXXXXXX.XX/raw/"$sub_dir
            fi
            repocli get "dccn/DAC_3010000.05_873/raw/"$sub_dir "/project/3010000.05/XXXXXXX.XX/temp/"
            for file in $(find "/project/3010000.05/XXXXXXX.XX/raw/$sub_dir" -type f); do 
                tempfile="${file/raw/temp}"
                if [ "$(sha256sum file | awk '{print $1}')" != "$(sha256sum tempfile | awk '{print $1}')" ]; then
                    rm -f "$file"
                    cp "$temp_file" "$file"
                fi
            done
        done

        rm -rf /project/3010000.05/XXXXXXX.XX/temp/