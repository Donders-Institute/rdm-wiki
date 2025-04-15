Moving Stimulus Scripts to Lab Computers
**************

Once your stimulus script works on your local computer, you will want to set it up in the laboratory where you will be running your experiment. 
:bdg-primary:`High Performance Storage` drives (such as the :bdg-primary:`Home Drive`, :bdg-primary:`Project Storage`, :bdg-primary:`Groupshare`) are mounted on lab computers, which means that you can actually run scripts that are stored in these locations. 
However, it is recommended that you set up your stimulus scripts and the files that they use on :bdg-primary:`local storage`, so that if these connections are interrupted your experiment can still be run. 

Location on Local Storage
==========

First, you need to know where you are allowed to store your stimulus materials on the :bdg-primary:`local storage` of the lab PCs.
Your on all lab PCs, you should create a folder within the users folder in the :bdg-primary:`Data` drive (``D:\Users\``) that corresponds to your DCCN username (i.e. firlas). 
Then you can create a folder for your project within your user folder(``D:\Users\firlas\project\``). 
The stimulus script and materials can now be transferred into this folder. 

Transferring to the Project Folder with Cyberduck
==========

Using thumb drives to transfer files onto lap PCs is strongly, strongly discouraged due to potential security risks. 
Therefore, you will have to use data transfer :bdg-dark:`Tools` to achieve this: let's go through an example using Cyberduck.

.. _this link: https://github.com/Donders-Institute/rdm-wiki/blob/main/RDM_Workshop_Materials.zip

Let's start with an example - on your laptop, open `this link`_ and push ``Control + Shift + S`` to download a zip file. 
In this zip file, you find a file which will make up some data for you to practice with. 
Open your Downloads folder and unzip the file you've just downloaded.

1. Establish a Network Connection to Trigon (either eduVPN or hardwired)
2. Log into Cyberduck

* Open Cyberduck and click ``Open Connection``
* In the protocol field, select ``SSH File Transfer Protocol``
* In the ``Server`` field, write ``mentat001.dccn.nl``
* In the ``Username`` field, write ``firlas@dccn.nl``
* In the ``Password`` field, insert your DCCN password
* When prompted with the unknown fingerprint warning, click ``Allow``

3. Navigate to the project folder (if you are not following the workshop, you can request access to this or do the same in your home directory: instead of ``/project/3010000.05/XXXXXXX.XX/materials/`` you use ``/project/XXXXXXX.XX/materials/``)

* At the top, click the dropdown menu to change the current directory to ``/``
* Click on ``project``
* Click on ``3010000.05``
* Right click below the last entry and choose ``New Folder``
* Type ``XXXXXXX.XX`` (this will be your project folder)
* Right click below the last entry and choose ``New Folder``
* Type ``materials``

4. Upload the files

* Click the ``Upload`` button
* Upload the three files from the folder you just downloaded and unzipped

Moving the Stimulus Script to the Lab PC
========

Fortunately, the Desktops in the Instruction Room and Trainee Room function the same as those in the various labs, so we can practice that now. 
Now, for those who are participating in the workshop let's put the script on our *Lab PC*.

1. Log into the Lab PC
2. Open File Explorer and navigate to where you just uploaded the files to 
3. Copy the files
4. Navigate to ``D:\Users\firlas\RDM_WorkshopPractice\materials`` and paste the files

Ensure Necessary Software
==========

On the lab PCs, only certain softwares are installed. 
If you are using other softwares to run your experiment, you will need to ask the TG to install these on the lab PC for you. 