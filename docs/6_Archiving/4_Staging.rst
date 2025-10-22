Moving Data to Your DSC
*******

Once you have finalized your results and you want to publish them in your project's :bdg-primary:`DSC`, you will need to :bdg-warning:`transfer` these files. 
The most straightforward way to :bdg-warning:`transfer` files is via :bdg-dark:`Stager`.

Using Stager to Transfer files
=========

1. Establish a connection to the Trigon Network using either eduVPN or a hardwired connection

.. _this page: https://rdm.dccn.nl/docs/3_Planning/3_Analyzing.html#private-collection-with-repocli

2. Login to Stager

* Go to https://stager.dccn.nl
* After login, the folders in the DCCN Project Storage are displayed on the left side of the screen.
* Input your RDR data access credentials in the fields under the ``Radboud Data Repository`` section (revist `this page`_ if you don't remember where to find these)

3. Select the Directories to Upload 

* On the Project Storage side, double click ``/3010000.05/`` 
* On the Project Storage side, double click ``/XXXXXXX.XX/`` 
* On the Project Storage side, check the boxes next to the ``data``, ``results``, ``scripts`` and ``materials`` directories: these are all of the folders we want to share to our :bdg-primary:`DSC`

.. Warning::

    At this stage, you must be **certain** that none of the data in these folders contains sensitive or potentially identifying information if you are sharing your data openly.  

4. Select the Directory to Upload to in the Radboud Data Repository

* On the Radboud Data Repository side, double click ``dccn``
* On the Radboud Data Repository side, double click ``DSC_3010000.05_519``
* On the Radboud Data Repository side, select the ``+`` icon at the bottom of the screen
* In the Dialog box, type ``XXXXXXX.XX`` and push ``Create``
* On the Radboud Data Repository side, check the box next to the directory you have just created

5. Upload the data to your Data Sharing Collection

* Push the ``Upload`` button

Using Repocli to Transfer files
=========

1. Establish a connection to the Trigon Network using either eduVPN or a hardwired connection

.. _this page: https://rdm.dccn.nl/docs/3_Planning/3_Analyzing.html#private-collection-with-repocli

2. Open a TigerVNC session (`read how to do that here`_)

3. Login to the :bdg-primary:`Radboud Data Repository`

* Open TigerVNC
* Open the terminal application
* Type ``repocli shell`` and then push ``enter``
* Type ``config`` and then push ``enter``
* Enter your RU username (u1234567@ru.nl) and then push ``enter``
* Enter the RDR password you retreived in step 2, then push ``enter``

4. Make a subdirectory for your files

* Type ``mkdir /dccn/DSC_3010000.05_519/XXXXXXX.XX`` and push ``enter``

5. Upload to the Data Sharing Collection 

* Type ``put /project/3010000.05/XXXXXXX.XX/results/ dccn/DAC_3010000.05_873/XXXXXXX.XX/results/`` 
* Type ``put /project/3010000.05/XXXXXXX.XX/data/ dccn/DAC_3010000.05_873/XXXXXXX.XX/data/`` 
* Type ``put /project/3010000.05/XXXXXXX.XX/materials/ dccn/DAC_3010000.05_873/XXXXXXX.XX/materials/`` 
* Type ``put /project/3010000.05/XXXXXXX.XX/scripts/ dccn/DAC_3010000.05_873/XXXXXXX.XX/scripts/`` 

Advanced Example: Scripting Uploads of Select files
=============

If your analyses involve T1 images, journals may request that you share this data in raw form. 
However, this data is identifiable which is why we defaced the images. 
Thus, we need to be sure that we **only** upload the defaced images. 
The most efficient way to do this is with repocli, by scripting the uploads.
Create a file in ``/project/3010000.05/XXXXXXX.XX/scripts/`` called ``stageT1.sh``. 
Open this file and write a script which stages all T1 images with repocli.

.. dropdown:: Answer

    :: 

        #!/bin/bash

        RAW_PATH="$1"
        REPO_PATH="$2"

        for subject in "$RAW_PATH"/sub-*; do
            find "$subject/ses-mri01" -type f -path "*/mprage*/*.nii" -name "defaced*.nii" | while read -r nii_file; do
                rel_path="${nii_file#$RAW_PATH/}"
                remote_path="$REPO_PATH/$rel_path"

                repocli put "$nii_file" "$remote_path"
            done
        done

Now save this file and run it in the terminal by typing the following:

::

    cd /project/3010000.05/XXXXXXX.XX/scripts
    chmod +x stageT1.sh
    ./stageT1.sh "/project/3010000.05/XXXXXXX.XX" "dccn/DAC_3010000.05_873"