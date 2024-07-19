Using Uploader
********

For your MRI and MEG data, files will be automatically transferred to both your :bdg-primary:`Project Folder` and its :bdg-primary:`Data Acquisition Collection`. 
However, for all other modalities, you will have to upload your data to these locations manually: the best way to do this is with :bdg-dark:`Uploader`. 
Just like the automatic data transfer protocol, :bdg-dark:`Uploader` saves data in :bdg-info:`BIDS format`. 

In order to demonstrate how to use :bdg-dark:`Uploader`, let's do an example that mimics what you will have to do in the laboratory after your participant has completed the experiment.

Practice Using Uploader
==========

.. _download a zip file: https://github.com/Donders-Institute/rdm-wiki/blob/main/RDM_Workshop_Materials.zip

1. Get Experimental Data

During your actual experiment, you will obviously do this by running your participant but if you want to practice, open the following link to `download a zip file`_ which contains a file which will make up some data for you to practice with. 

* Open MatLab
* Go to the location where you unzipped ``RDM_Workshop Materials`` on your local PC
* Open the file ``MakeDataUp.m`` (this would be a stimulus presentation program that behavioral responses)
* Run the program

2. Login to Uploader

* Go to https://uploader.dccn.nl
* Type in your DCCN username (firlas) and password in the correct fields and then push login

3. Upload Your Data Files

* Under the ``Select project`` field select the project number (if you are making up data, use ``3010000.05``)
* Under the ``Set subject label field`` insert the subject number from the calendar (or made up numbers if you are using made up data)
* For the ``Set session label`` insert the session number from the calendar (or ``01`` if using made up data)
* Under the ``Select data type field`` select the correct modality (or ``beh`` if using made up data)
* Open up File Explorer side-by-side the uploader window
* Go to the folder where the results are written (this is ``C:/Users/*/Downloads`` if using made up data) and locate ``MadeUpResults.csv``
* Drag ``MadeUpResults.csv`` and drop it in the ``Click or drag files to this area`` field in uploader.
* Push upload at the bottom right of your screen and close the window after the process has been completed