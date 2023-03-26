Research Initiation
*******************

This offers some examples of research data management practices which should be followed in the period prior to data acquisition.

What data would I need to manage before I collect my own?
=========================================================

Prior to data acquisition, you might have these kinds of data

* Experiment Materials
* Exisiting Datasets
* Analysis Scripts

We will talk about best practices in terms of data management during this period and how data should be transferred once your Project Folder has been issued. 
However, we will start with a guide on how to access data from the Donders Repository. 

How do I access existing datasets from previous Donders Institute studies?
==========================================================================

During this period, you may wish to analyze data from previous studies. 
If one of these previous studies was conducted by a member of the Donders Institute, you can request access to view the raw data - or Data Acquisition Collections (DACs). 
If this study was conducted by a fellow member of the DCCN, you can see the DAC but you cannot view or download the files. 
If the study was conducted by a member of the DCC, DCN, or DCMN, you cannot see the DAC. 
Since you are a member of the Donders Institute, you can request access to privately available DACs, Research Documentation Collections (RDCs), and Data Sharing Collections (DSCs).

Exercise 2: Creating a Donders Repository Account
-------------------------------------------------

In order to access any Donders Repository Collections, you must create a Donders Repository account.

* Open your internet browser of choice
* Go to https://data.donders.ru.nl
* Login with your SURFcontext account
* Accept the terms

How to Obtain Access to Donders Repository Collections
------------------------------------------------------

To obtain access to Collections in the Donders Repository, you must contact one of the managers of that collection. 
For all DCCN Collections, you can see who the manager(s) are for each collection of each project: you should contact any one of those people and request to be added. 

For DCN, DCC, and DCMN Collections, you will only be able to see who the manager(s) are for each collection if that collection is a publicly available DSC. 
Importantly, not all researchers publish their collections as publicly DSCs. 
Therefore, if you have become aware of a data set collected by a member of the Donders Institute which you would like to analyze, you should just contact a member of that project to ask about if/how you might receive access. 

Exercise 3: Download data from a collection you have been added to with Repocli
-------------------------------------------------------------------------------

Once you have been added to a collection, you will receive an email to the email account you used when you signed up to the Donders Repository stating that you have been added. 
We have added you to the ``DSC_3010000.05_519`` collection - a private DSC - so that you can get practice downloading privately shared data. 
You should never download private DSCs onto your personal computer to ensure that - if the researchers made a mistake - there are no chances of data leakages. 
We will practice downloading this DSC onto your Home Drive (replace groupname with your lab group's name and firlas with your DCCN username)

*Requires a VNC and VPN Connection*

* Open TigerVNC
* Open the terminal application
* Type ``repocli shell`` and then push ``enter``
* Type ``repocli login`` and then push ``enter``
* Enter your RU username (u1234567@ru.nl) and then push ``enter``
* Enter your RU password and then push ``enter``
* Push ``y`` and then push ``enter``
* Type ``get dccn/DSC_3010000.05_519 /home/groupname/firlas``

Exercise 4: Download data from a DSC you have not been added to with Cyberduck
------------------------------------------------------------------------------

*Does not require a VNC or VPN Connection*

* Open Cyberduck
* Click ``Open Connection`` at the top left of the window
* Click on the dropdown menu (which defaults to ``File Transfer Protocol (FTP)``) and select ``WebDAV (HTTPS)`` 
* At the ``Server:`` field type in ``public.data.donders.ru.nl``
* Click the box next to ``Anonymous Login`` and then click ``Connect`` at the bottom right side of the window
* Double click on the ``dccn`` directory 
* Single click on the ``DSC_3010000.11_518_v1`` directory 
* Locate and click on ``Action`` at the top of the window and then select ``Download To`` on the dropdown menu
* Select the folder you want to download the data to and then push ``Ok``
* Select the disconnect button at the top right of the window

How do I access publicly available data sets from external institutions?
========================================================================

Thus far we have tackled retrieving publicly and privately available DSCs from the Donders Repository. 
But you may want to download data from other public research data repositories. 

This data can be downloaded by simply selecting the Download button on websites. 
If you use some web browser, you can for instance find data in repositories (for a list look at https://neuinfo.org/rin/suggested-data-repositories?p1=SCR_006770). 

However, these data sets are obviously quite large (often >100 GB). 
Downloading 100 GB of files will take quite some time. 
More importantly, you might not have the memory required to download this much data: therefore, you should only download it if you need it. 
It can be tedious and prone to errror to download this by "pointing and clicking". 
Let's try using Repocli to selectively download a subset of data files from one such repository into our Home Folder.

Exercise 6: Download a subset of data from OpenNeuro Using Repocli
------------------------------------------------------------------

How should I move files from my local computer into my (newly issued) Project folder?
=====================================================================================

If your computer is a part of the Trigon Network, you can simply drag and drop files into the Project folder. 


However, if you are working remote or you want to transfer files on your personal PC, you should NOT use a flash drive. 
Instead, you should upload these files using approved file transfer protocols. 
Using Uploader is not recommended since these files are not experimental data. 
Instead we recommend uploading files to the DAC and Project Folder with Cyberduck.

Exercise 7: Uploading analysis files to my new DAC from my local computer with Cyberduck
----------------------------------------------------------------------------------------

*Does not require a VNC or VPN Connection*

* Open Cyberduck
* Click ``Open Connection`` at the top left of the window
* Click on the dropdown menu (which defaults to ``File Transfer Protocol (FTP)``) and select ``WebDAV (HTTPS)`` 
* At the ``Server:`` field type in ``webdav.data.donders.ru.nl``
* Enter your RU username (u1234567@ru.nl) and password and then click ``Connect`` at the bottom right side of the window
* Double click on the ``dccn`` directory 
* Double click on the ``DAC_3010000.05_873`` directory 
* Double click on the ``scripts`` directory
* Locate and click on ``Action`` at the top of the window and then select ``New Folder`` on the dropdown menu
* Type your DCCN username (firlas) in the Field and push ``Create``
* You should be in the folder just created: if not navigate to that folder and select ``Upload`` at the top center of the window
* Navigate to the ``Downloads`` folder in your local drive, select the **unzipped** ``RDM_Workshop Materials`` directory and push ``choose``
* Select the disconnect button at the top right of the window

Exercise 8: Uploading analysis files to the Project Folder from my local computer with Cyberduck
------------------------------------------------------------------------------------------------

*Does require a VPN Connection*

* Open Cyberduck
* Click ``Open Connection`` at the top left of the window
* Click on the dropdown menu (which defaults to ``File Transfer Protocol (FTP)``) and select ``SSH File Transfer Protocol (SFTP)`` 
* At the ``Server:`` field type in ``mentat001.dccn.nl``
* Enter your DCCN username (firlas@dccn.nl) and password and then click ``Connect`` at the bottom right side of the window
* Click on the directory field which should say ``/home/groupname/firlas`` and select ``/``
* Double click on the ``project`` directory 
* Double click on the ``3010000.05`` directory 
* Double click on the ``scripts`` directory
* Locate and click on ``Action`` at the top of the window and then select ``New Folder`` on the dropdown menu
* Type your DCCN username (firlas) in the Field and push ``Create``
* You should be in the folder just created: if not navigate to that folder and then select ``Upload`` at the top center of the window
* Navigate to the ``Downloads`` folder in your local drive, select the **unzipped** ``RDM_Workshop Materials`` directory and push ``choose``
* Select the disconnect button at the top right of the window

How can I move files from my home drive into my (newly issued) Project folder?
==============================================================================

This is as simple as dragging and dropping files (or however you usually move files around locally)