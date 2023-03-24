Data Storage Facilities at the DCCN
************************

This is an overview of the storage facilities of the DCCN. 
This documentation is given primarily for new users of the DCCN who do not have experience with the system. 
However, for experienced users, this will be redundant and can be skipped. 

Local Storage
=================================

Using local storage is highly risky. 
Computers can crash and data can accidentally be deleted at any time. 
When using a Windows PC in the Trigon Network, you are able to drag and drop files from Local Storage (i.e. from the ``C:/`` drive and ``D:/`` drive) to Central Storage. 
You also have read-write access to files in the Central Storage. 
This means that you can directly edit and write files on Central Storage. 
Central Storage is much, much less risky than local storage. 
Therefore, it is important to be aware of when you are using local storage and when you are using Central Storage. 

Lab Computers
-----------
Lab Computers include all of the computers located in the various laboratories at the DCCN (i.e. behavioral, MRI, EEG, MEG, etc.). 
Formerly, Lab Computers were not connected to the Trigon network. 
This has recently changed. 
Therefore, Lab Computers have network access to the Central Storage facilities at the DCCN. 
However, by default data will be written to local storage on Lab Computers.

Network Desktops
-----------
Network Desktops are the Windows Desktops which are located at Flex Desks, the Instruction Room, and the Trainee Room. 
All Network Desktops are connected to the Trigon Network and therefore have access to the Central Storage facilities at the DCCN. 
However, by default data will be written to local storage on Lab Computers.

TG Issued Laptops
-----------
TG Issued Laptops are the DELL Laptops issued by the TG. 
When Docked at the DCCN, TG Issued Laptops are connected to the Trigon Network and therefore have access to the Central Storage facilities at the DCCN. 
However, by default data will be written to local storage on the Laptop.

Personal Computer
-----------
Under no circumstances can your personal computer be connected to the Trigon Network.

Central Storage
=================================

Central Storage is accessible via the Trigon Network or the High Performance Computing (HPC) Cluster. 
Central Storage is sometimes referred to as High Performance Storage. 
There are three Drives/Directories on the Central Storage which are relevant for Research Data Management. 

Project
-----------
For Windows PCs connected to the Trigon Network, this is the ``P:/`` drive (look under "Network" in File Explorer). 
For VNC Sessions on the HPC Cluster, this is the ``\project\`` folder. 

Research at DCCN is organized by projects. 
Projects are assigned numbers after the Project Proposal Form is completed and approved. 
Project numbers are given in the format ``1234567.89``. 
Your project's data will be located at ``P:/1234567.89/`` on Windows PCs connected to the Trigon and the ``\project\1234567.89\`` on the HPC Cluster. 
Based on the storage you request in the Project Proposal Form, you will be given a quota of storage which cannot be exceeded in your project's folder.
Each research project, once approved, will be provided with a quota on the DCCN central storage allowing researchers to store and process the research data related to the project. 

**Further Reading**

- https://intranet.donders.ru.nl/index.php?id=projectstorage
- https://intranet.donders.ru.nl/index.php?id=quota
- https://hpc.dccn.nl/docs/project_storage/access_management.html

Home
-----------
For Windows PCs connected to the Trigon Network, this is the ``H:/`` drive (look under "Network" in File Explorer). 
For VNC Sessions on the HPC Cluster, this is the ``\home\`` folder. 

After you have signed in at the DCCN, you will be given 5 GB of storage space on in your home directory. 
Your home directory is located within your laboratory group's directory under your DCCN username (Firstname Lastname is firlas).
Your home directory will be located at ``H:/groupname/firlas/`` on Windows PCs connected to the Trigon and the ``\home\groupname\firlas\`` on the HPC Cluster. 

Group
-----------
For Windows PCs connected to the Trigon Network, this is the ``G:/`` drive (look under "Network" in File Explorer). 
For VNC Sessions on the HPC Cluster, this is the ``\group\`` folder. 

The Group directory enables passive data sharing between members of a laboratory group. 
All lab group members have read-write access, meaning that they can read, create, delete, move, copy, and edit files located in the group directory. 
Your home directory will be located at ``G:/groupname/`` on Windows PCs connected to the Trigon and the ``\group\groupname\`` on the HPC Cluster. 

Donders Repository
=================================

The Donders Repository is a data repository for researchers of the the Donders Institute to archive and/or publish their research data. 
Data on the Donders Repository more difficult to access than data on Central or Local Storage. 
Therefore, it serves the purpose of backing up data so that, in the case of accidental deletion on Central Storage, it can still be retrieved. 
Additionally, it serves the purpose of improving research documentation for better reproducibility. 
Finally, it also serves the purpose of hosting data after the completion of the project. 
It is hosted at https://data.donders.ru.nl/. 
Importantly, you do not get access to any of the three collections by default - even if you have access to the Project Folder. 
Access must be granted by the Manager of the collection: usually, this is the PI.

Data Acquisition Collections
-----------
Data Acquisition Collections contain raw data. 
Its purpose is to ensure that data are archived without any manipultions which limit the potential for future.
Additionally, it ensures that in the event of accidental deletion of data in the project folder, this data is not lost. 
Consequently, it enables researchers to delete the raw files of data in the project folder after these files are processed. 
Researchers may wish to delete the raw files in the project folder to ensure that they stay under their storage quota.

Data Acquisition Collections can be found at the Donders Repository with the following identifier:

``di.dccn.DAC_1234567.89_XXX``

Here DAC refers to Data Acquisition Collection, 1234567.89 refers to the Project Number, and XXX can be any three random digits.


Research Documentation Collections
-----------

Research Documentation Collections contain documents. 
Its purpose is to memorandize the process by which raw data came to lead to your published results. 
You must request a Research Documentation Collection for your project.

Research Documentation Collections can be found at the Donders Repository with the following identifier:

``di.dccn.RDC_1234567.89_XXX``

Here RDC refers to Research Documentation Collection, 1234567.89 refers to the Project Number, and XXX can be any three random digits. 
These are not the same random digits as those in the Data Acquistion Collection identifier for the same project.

Data Sharing Collections
-----------

Data Sharing Collections contain processed data and analysis scripts. 
Its purpose is to enable researchers to reanalyze the data with new methods and/or address new research questions with this data. 
There are two kinds of Data Sharing Collections: private and public. 
Public Data Sharing Collections are available for download for all researchers at https://data.donders.ru.nl. 
These collections must be completely anonymized and may not contain any potentially identifying information. 
Access to private Data Sharing Collections, like Data Acquisition Collections and Research Documentation Collections, must be granted by the collection's manager.

Data Acquisition Collections can be found at the Donders Repository with the following identifier:

``di.dccn.DSC_1234567.89_XXX``

Here DSC refers to Data Sharing Collection, 1234567.89 refers to the Project Number, and XXX can be any three random digits. 
These are not the same random digits as those in the Data Acquistion Collection identifier or the Research Documentation Collection identifier for the same project.

Data Managegment Workflow with the Donders Repository
-----------
.. figure:: images/RDM_Workflow_DI-1.png
    :figwidth: 100%
    :align: center

    Figure: Data Managegment Workflow with the Donders Repository

----

Throughout the life cycle of your project, you will have to move data between storage facilities. 
You are encouraged to think about how you will do this with a Data Management Plan.