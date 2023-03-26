Data Sharing
************

This is a guide on what to do with data when the project is over. 


Now, you have fully finished with you analysis and write up. 
Perhaps your article has been accepted for publication or perhaps you have decided that it is no longer worth pursuing. 

Either way, your goal at this stage is to ensure that the work you have done is archived to the Donders Repository. 
The space available on Central Storage is finite and, therefore, if you are not using the data anymore all files should be removed from the project folder. 
Therefore, you will need to move your analysis scripts, processed data, and results into a Data Sharing Collection (DSC).

When do I make data publicly available?
=======================================

In the spirit of open science - achieved by making research FAIR - many researchers aim to make their data publicly available. 
Research data should only be made publicly available if potentially identifying information has been removed. 
Some examples of how this is to be done are as follows: 

1. Use anonymized labels (subject numbers assigned via the calendar)
2. De-face and de-ear MRI files

Often, researchers will make 2 DSCs - one to be made publicly available and one which is private. 
Importantly, even the private data may not contain any potentially identifying information: this must be kept apart from the experimental data at all times. 

How to make a Data Sharing Collection
======================================

Request a Data Sharing Collection
---------------------------------

To request a DSC, fill out this form https://intranet.donders.ru.nl/index.php?id=donders-repository-request-form&no_cache=1&sword_list%5B%5D=collection

Exercise 12: Staging Data from the Project Folder to the Data Sharing Collection
--------------------------------------------------------------------------------

Once you have made a DSC, you can stage files from your Project Folder to the DSC. 
In this exercise, we will use multiple directories within both the ``project/proc`` and the ``DSC_project/proc`` directories

* Go to https://stager.dccn.nl
* In the Project Storage side, enter your DCCN username (for Firstname Lastname this is ``firlas@dccn.nl``) and password, and push ``Login``
* In the Donders Repository side, enter your RU username (``u1234567@ru.nl``) and password, and push ``Login``
* On the Project Storage side, navigate to ``/3010000.05/proc`` and click on the box next to the ``yourname`` directory
* On the Donders Repository side, go to the ``/dccn/DSC_3010000.05_873/proc`` directory and click on the box next to the ``yourname`` directory
* Now, you can push the ``Upload`` button (the left-facing arrow) to move all of the files in the ``/3010000.05/proc/yourname`` directory into the ``/dccn/DSC_3010000.05_873/proc/yourname`` directory.

How to Publish Your Data Sharing Collection
-------------------------------------------

1. Prepare the Collection

    * Ensure that there is no personal information, the collection is properly documented, and the collection is complete

2. Switch to Reviewable Internal

    * Log into the Donders Repository and select the collection you wish to publish
    * Select ``Switch to 'reviewable internal'`` near the top left of the screen and click confirm

    .. figure:: images/publish_review_internal.png
    :figwidth: 100%
    :align: center

    Figure: Switch to review internal

3. Switch to Reviewable External

    * Select ``Switch to 'reviewable external'`` near the top left of the screen and click confirm

    .. figure:: images/publish_review_external.png
    :figwidth: 100%
    :align: center

    Figure: Switch to review external

4. Grant Reviewer Access

    * Select ``Get reviewer access URL'`` near the top left of the screen and copy the link
    * Share the URL with the editor of the journal you have submitted your article to (this grants anyone with this link the right to view a collection)

    .. figure:: images/publish_review_URL.png
    :figwidth: 100%
    :align: center

    Figure: Switch to review external

5. Switch to Publish

    * If your article has been accepted for publication, log into the Donders Repository and select the collection you wish to publish
    * Select ``Switch to 'published'`` near the top lefft of the screen and click confirm
    * Your article is now irreversibly published: the process will be complete within a few hours but you cannot undo this


How to Publish to the Donders Public Repository
-----------------------------------------------

