Data Sharing
************

This is a guide on what to do with data when the project is over. 


Now, you have fully finished with you analysis and write up. 
Perhaps your article has been accepted for publication or perhaps you have decided that it is no longer worth pursuing. 

Either way, your goal at this stage is to ensure that the work you have done is archived to the Donders Repository. 
The space available on Central Storage is finite and, therefore, if you are not using the data anymore all files should be removed from the project folder. 
Therefore, you will need to move your analysis scripts, processed data, and results into a Data Sharing Collection (DSC).

When and how do I make data publicly available?
==============================================

In the spirit of open science - achieved by making research FAIR - many researchers aim to make their data publicly available. 
Research data should only be made publicly available if potentially identifying information has been removed. 
Some examples of how this is to be done are as follows: 

1. Use anonymized labels (subject numbers assigned via the calendar)
2. De-face and de-ear MRI files

Often, researchers will make 2 DSCs - one to be made publicly available and one which is private. 
Importantly, even the private data may not contain any potentially identifying information: this must be kept apart from the experimental data at all times. 

Exercise 12: Making a Data Sharing Collection
---------------------------------------------

Exercise 13: Staging Data from the Project Folder to the Data Sharing Collection
--------------------------------------------------------------------------------

Once you have made a DSC, you can stage files from your Project Folder to the DSC. 
In this exercise, we will use multiple directories within both the ``project/proc`` and the ``DSC_project/proc`` directories

1. Go to https://stager.dccn.nl
2. In the Project Storage side, enter your DCCN username (for Firstname Lastname this is ``firlas@dccn.nl``) and password, and push ``Login``
3. In the Donders Repository side, enter your RU username (``u1234567@ru.nl``) and password, and push ``Login``
4. On the Project Storage side, navigate to ``/3010000.05/proc`` and click on the box next to the ``yourname`` directory
5. On the Donders Repository side, go to the ``/dccn/DSC_3010000.05_873/proc`` directory and click on the box next to the ``yourname`` directory
6. Now, you can push the ``Upload`` button (the left-facing arrow) to move all of the files in the ``/3010000.05/proc/yourname`` directory into the ``/dccn/DSC_3010000.05_873/proc/yourname`` directory.