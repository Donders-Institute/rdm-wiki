Using Uploader
********

For your MRI and MEG data, files will be automatically transferred to both your :bdg-primary:`Project Folder` and its :bdg-primary:`Data Acquisition Collection`. 
However, for all other modalities, you will have to upload your data to these locations manually: the best way to do this is with :bdg-dark:`Uploader`. 
Just like the automatic data transfer protocol, :bdg-dark:`Uploader` saves data in :bdg-info:`BIDS format`. 

In order to demonstrate how to use :bdg-dark:`Uploader`, let's do an example that mimics what you will have to do in the laboratory after your participant has completed the experiment.

Practice Using Uploader
==========

1. Create a Lab Account

.. Note::

    Lab Accounts ensure that participants cannot access project storage while left alone. 
    This is very useful as it ensures data integrity. 
    Lab Accounts last for 7 days but can be refreshed at any time.

* On your laptop, log into https://portal.dccn.nl
* Click on your user profile in the top right corner and select ``My Profile``
* Click on ``Lab Account`` on the left side
* Choose ``Create Lab Account``

2. Get Experimental Data

* On the Desktop, log in using your lab account credentials
* Open MatLab
* Go to where you put the ``MakeDataUp.m`` file on the local PC (if you are following the workshop, it will be here: ``D:\Users\firlas\RDM_WorkshopPractice\materials``)
* Open the file ``MakeDataUp.m`` (this would be a stimulus presentation program that records behavioral responses)
* Run the program

3. Login to Uploader

* Go to https://uploader.dccn.nl
* Type in your DCCN username (firlas) and password in the correct fields and then push login

4. Upload Your Data Files

* Under the ``Select project`` field select the project number (if you are making up data, use ``3010000.05``)
* Under the ``Set subject label field`` insert the subject number from the calendar (or made up numbers if you are using made up data)
* For the ``Set session label`` insert the session number from the calendar (or ``01`` if using made up data)
* Under the ``Select data type field`` select the correct modality (or ``beh`` if using made up data)
* Open up File Explorer side-by-side the uploader window
* Go to the folder where the results are written (this is ``C:/Users/*/Downloads`` if using made up data) and locate ``MadeUpResults.csv``
* Drag ``MadeUpResults.csv`` and drop it in the ``Click or drag files to this area`` field in uploader.
* Push upload at the bottom right of your screen and close the window after the process has been completed