Restoring Lost Data
**********

To give an example on how you might analyze data on the :bdg-primary:`HPC Cluster`, we're going to analyze the data we 'collected' earlier using the ``MakeDataUp.m`` program. 
However, before doing so we want to make sure that our data set is complete! 
Let's walk through an example of how you can restore data that was lost in the :bdg-primary:`Project Folder` but is in the :bdg-primary:`DAC`.

Practice Restoring Data with Stager
=======

Since everyone needs to be able to analyze the data, however, let's first duplicate the files in the ``/project/3010000.05/raw/`` into a new folder that you can make changes to without affecting others' work. 
Copy all of the directories in the ``/project/3010000.05/raw/`` folder (the keyboard shortcut is Ctrl + A). 
Now, navigate to the ``/project/3010000.05/1234567.89/raw/`` folder and create a new folder with your DCCN username. 
Open the ``/project/3010000.05/1234567.89/raw/firlas/`` folder and paste the contents of the ``/project/3010000.05/raw/`` folder.


1. Check for data loss between subjects number 1 to 10

* Open ``Applications`` and go to ``File Explorer`` in the dropdown menu
* At the file directory where it says ``/home/groupname/firlas/``, replace it with ``/project/3010000.05/1234567.89/raw/firlas/``
* Notice that there are no folders for ``sub-002``, ``sub-005``, and ``sub-006`` - this data has been accidentally deleted

2. Establish a Network Connection to Trigon (either eduVPN or hardwired)

3. Go to https://stager.dccn.nl

4. Log in to the Stager service

.. _this page: https://rdm.dccn.nl/docs/3_Planning/3_Analyzing.html#private-collection-with-repocli
.. _read how to do that here: https://intranet.donders.ru.nl/index.php?id=vnc00&no_cache=1&sword_list%5B%5D=tigerVNC

* Input your DCCN username in the following format ``firlas@dccn.nl`` and your DCCN password in the fields under the ``Project Storage`` section
* Input your RU username in the following format ``u1234567@ru.nl`` and your Radboud Data Repository password in the fields under the ``Radboud Data Repository`` section (revist `this page`_ if you don't remember how to do this)

5. Select the Radboud Data Repository directories to download

* Double-click on ``dccn`` on the Radboud Data Repository Side
* Double-click on ``DAC_3010000.05_873`` on the Radboud Data Repository Side
* Double-click on ``raw`` on the Radboud Data Repository Side
* Check the boxes next to the ``sub-002``, ``sub-005``, and ``sub-006`` directories

6. Select the Project Storage directory to download the data into

* Double-click on the ``3010000.05/`` directory on the Project Storage side 
* Double-click on the ``1234567.89`` directory on the Project Storage side
* Double-click on the ``raw`` directory on the Project Storage side
* Check the box next to your ``firlas`` directory on the Project Storage side

7. Press the ``Download`` button

Practice Restoring Data with Repocli
======

1. Check for data loss between subjects number 1 to 10

* Open ``Applications`` and go to ``File Explorer`` in the dropdown menu
* At the file directory where it says ``/home/groupname/firlas/``, replace it with ``/project/3010000.05/1234567.89/raw/firlas/``
* Notice that there are no folders for ``sub-002``, ``sub-005``, and ``sub-006`` - this data has been accidentally deleted

2. Establish a Network Connection to Trigon (either eduVPN or hardwired)

3. Open a TigerVNC session (`read how to do that here`_)

4. Login to the :bdg-primary:`Radboud Data Repository`

* Open TigerVNC
* Open the terminal application
* Type ``repocli shell`` and then push ``enter``
* Type ``config`` and then push ``enter``
* Enter your RU username (u1234567@ru.nl) and then push ``enter``
* Enter the RDR password you retreived in step 2, then push ``enter``

5. Download the Data Sharing Collection to Your Home Directory

* Type ``get dccn/DAC_3010000.05_873/raw/sub-002 /project/3010000.05/1234567.89/raw/firlas/`` and then push ``enter``
* Type ``get dccn/DAC_3010000.05_873/raw/sub-005 /project/3010000.05/1234567.89/raw/firlas/`` and then push ``enter``
* Type ``get dccn/DAC_3010000.05_873/raw/sub-006 /project/3010000.05/1234567.89/raw/firlas/`` and then push ``enter``

Snapshot
======

.. _this link: https://intranet.donders.ru.nl/index.php?id=6645

If you accidentally delete 1 or more files, you may be able to retreive them with a :bdg-dark:`snapshot` by simply copying and pasting. 
:bdg-dark:`Snapshots` are sporadic captures of the state of a computer system at a point in time. 
To read more about :bdg-dark:`snapshots` and how you can restore deleted data, visit `this link`_ on the intranet.

Advanced Example
=======

In the above excercise, we saw how we can restore data from a :bdg-primary:`DAC` to your :bdg-primary:`Project Folder`. 
However, with many folders and subfolders to check, this can be tedious, inefficient, and prone to user error. 
So in this advanced example we will automate this process by creating a Bash script which runs on the :bdg-primary:`HPC cluster`.

Restoring All Missing Subject Directores
----------

1. Start a TigerVNC session
2. Run ``/project/3010000.05/1234567.89/scripts/makeMissing.sh`` 

Open the terminal emulator and run the following code

::

    cd /project/3010000.05/1234567.89/scripts/
    chmod +x makeMissing.sh
    ./makeMissing.sh

3. Create ``/project/3010000.05/1234567.89/scripts/firlas/restoreMissng.sh``

Open the text editor and write code that compares all :bdg-primary:`DAC` files to :bdg-primary:`Project Folder` files, 
restoring files that are in the :bdg-primary:`DAC` but not the :bdg-primary:`Project Folder`. 
Save the file as ``/project/3010000.05/1234567.89/scripts/firlas/restoreMissng.sh``

.. dropdown:: Hint 1

    You will need to enumerate all of the files in each folder in the :bdg-primary:`DAC`, which can be done in bash in the following way

    :: 
        
        #!/bin/bash
        repocli ls dccn/DAC_3010000.05_873/raw/

.. dropdown:: Hint 2
    
    You will need to go through all of the folders, which can be done in the following way:

    ::

        #!/bin/bash
        for sub_dir in $(repocli ls dccn/DAC_3010000.05_873/raw/); do 
            echo "dccn/DAC_3010000.05_873/raw/"$sub_dir; 
        done
    
    Inside the for loop, we're just printing the subject's directory

.. dropdown:: Answer

    ::

        #!/bin/bash
        for sub_dir in $(repocli ls dccn/DAC_3010000.05_873/raw/); do 
            if [ ! -d "/project/3010000.05/1234567.89/raw/firlas/"$sub_dir ]; then
                repocli get "dccn/DAC_3010000.05_873/raw/"$sub_dir "/project/3010000.05/1234567.89/raw/firlas/"$sub_dir
            fi
        done

4. Run ``/project/3010000.05/1234567.89/scripts/firlas/restoreMissng.sh``

::

    cd /project/3010000.05/1234567.89/scripts/firlas
    chmod +x restoreMissng.sh
    ./restoreMissng.sh