Restoring Lost Data
**********

To give an example on how you might analyze data on the :bdg-primary:`HPC Cluster`, we're going to analyze the data we 'collected' earlier using the ``MakeDataUp.m`` program. 
However, before doing so we want to make sure that our data set is complete! 
Let's walk through an example of how you can restore data that was lost in the :bdg-primary:`Project Folder` but is in the :bdg-primary:`DAC`.

Practice Restoring Data
=======

Since everyone needs to be able to analyze the data, however, let's first duplicate the files in the ``/project/3010000.05/raw/`` into a new folder that you can make changes to without affecting others' work. 
Copy all of the directories in the ``/project/3010000.05/raw/`` folder. 
Now, navigate to the ``/project/3010000.05/data/`` folder and create a new folder with your DCCN username. 
Open the ``/project/3010000.05/data/firlas/`` folder and paste the contents of the ``/project/3010000.05/raw/`` folder.


1. Check for data loss between subjects number 1 to 10

* Open ``Applications`` and go to ``File Explorer`` in the dropdown menu
* At the file directory where it says ``/home/groupname/firlas/``, replace it with ``/project/3010000.05/data/firlas/``
* Notice that there are no folders for ``sub-002``, ``sub-005``, and ``sub-006`` - this data has been accidentally deleted

2. Establish a Network Connection to Trigon (either eduVPN or hardwired)

3. Go to https://stager.dccn.nl

4. Log in to the Stager service

* Input your DCCN username in the following format ``firlas@dccn.nl`` and your DCCN password in the fields under the ``Project Storage`` section
* Input your RU username in the following format ``u1234567@ru.nl`` and your RU password in the fields under the ``Donders Repository`` section

5. Select the Donders Repository directories to download

* Double-click on ``dccn`` on the Donders Repository Side
* Double-click on ``DAC_3010000.05_873`` on the Donders Repository Side
* Double-click on ``data`` on the Donders Repository Side
* Check the boxes next to the ``sub-002``, ``sub-005``, and ``sub-006`` directories

6. Select the Project Storage directory to download the data into

* Double-click on the ``3010000.05/`` directory on the Project Storage side 
* Double-click on the ``data`` directory on the Project Storage side
* Check the box next to your ``firlas`` directory on the Project Storage side

7. Press the ``Download`` button

Snapshot
======

.. _this link: https://intranet.donders.ru.nl/index.php?id=6645

If you accidentally delete 1 or more files, you may be able to retreive them wit a :bdg-dark:`snapshot` by simply copying and pasting. 
:bdg-dark:`Snapshots` are sporadic captures of the state of a computer system at a point in time. 
To read more about :bdg-dark:`snapshots` and how you can restore deleted data, you can open `this link`_.