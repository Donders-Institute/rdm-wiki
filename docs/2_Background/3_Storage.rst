Data Storage Facilities
********

Typical data flow at :bdg-danger:`DCCN` uses three main types of :bdg-primary:`data storage facilities` - each with their own functionality, advantages and disadvantages. 
Knowing :bdg-primary-line:`where` data can and should be stored, as well as :bdg-warning-line:`when` it should be stored in certain locations is 
crucial for being an effective and efficient researcher.

Local Storage
=====

.. dropdown:: About

    :bdg-primary:`Local storage` includes the storage on any local devices such the :bdg-primary:`C:/` drive in your DCCN-issued PC,
    as well as the :bdg-primary:`D:/` drive in lab computers.

.. dropdown:: Advantages 

    Using :bdg-primary:`local storage` can be helpful in multiple :bdg-warning:`stages of the research cycle`. 
    If you are collecting data in the lab and you are writing data while the experiment is running, you may likely first write the data to the 
    :bdg-primary:`local storage` of the lab computer. 
    Another common use case is if you have a software package that cannot be installed on the :bdg-primary:`HPC cluster` - 
    in this case it is optional to work with data on the :bdg-primary:`local storage` of the PC issued to you by the Technical Group. 
    Thus, some advantages are:

    * Easy to access and work with data
    * Can change and update software freely
    * Requires no training

.. dropdown:: Disadvantages

    When conducting analyses on the PC issued to you by the Technical Group, you will need to download your research data onto 
    the :bdg-primary:`local storage` of your device. In such cases, your research data **MUST** be pseudonymized. 
    Also, downloading all of the research data may take a long time depending on the size of the data set you are analyzing. 
    Similarly, such analyses generally can be run much faster on the :bdg-primary:`HPC cluster` and may require more RAM (i.e. working memory) than your PC has. 
    Finally, your PC can crash at any moment so data in :bdg-primary:`local storage` can be lost; 
    thus you must constantly re-upload your data to :bdg-primary:`High Performance Storage` to mitigate potential data loss.
    Thus, some disadvantages are:

    * Constant involuntary risk of data loss
    * Potential for data breach
    * Downloading data is time-consuming
    * Requires :bdg-warning:`constant re-uploading` to mitigate potential data loss
    * Less RAM
    * Less storage space 
    * Files are not visible to any other :bdg-info:`research team members`

Ultimately, :bdg-primary:`local storage` is risky because data is not backed up anywhere and inefficient for several reasons. 
Nonetheless, it does have its use-cases though you always must be careful to prevent data loss and breaches in data security and privacy.

High Performance Storage
====

.. dropdown:: About

    :bdg-primary:`High Performance Storage` includes several different drives (or volumes): most notably
    the :bdg-primary:`Home` drive where your private work-related files may be kept, 
    the :bdg-primary:`Groupshare` drive where your lab group's shared files may be kept, 
    and the :bdg-primary:`Project` drive where your project's research data must be kept. 
    :bdg-primary:`High Performance Storage` consists of drives such as these, which are mounted on Network PC's in Trigon such as those in the Instruction and 
    Trainee rooms as well as all Lab PC's.
    :bdg-primary:`High Performance Storage` is also directly connected to the :bdg-primary:`HPC cluster`.

.. dropdown:: Advantages 

    * Larger storage space than :bdg-primary:`local storage` on PCs.
    * Easily accessible via both Network PC's and the :bdg-primary:`HPC cluster` 
    * Easy to access and work with data
    * Set up to work with parallelization and large working memory on the :bdg-primary:`HPC cluster`, making analysis many times faster
    * Protected against data loss and backed-up

.. dropdown:: Disadvantages 

    * Sometimes analysis packages/softwares cannot be user-downloaded (may require time for the TG to make these software available)
    * Storage is limited to the duration of the research project
    * Can only be accessed by :bdg-info:`research team members` who are checked into the :bdg-danger:`DCCN`

:bdg-primary:`High Performance Storage` is directly connected to the :bdg-primary:`HPC cluster`, the workhorse of data analysis at the :bdg-danger:`DCCN`. 
For the vast majority of use cases it is the ideal :bdg-primary:`place` to store data that you will analyze since it 
offers ease-of-access to files and is set up to function with other :bdg-primary:`storage` infrastructure.
It is the primary storage facility for research data when a project is in progress, but  due to limited space you cannot leave research data
on the :bdg-primary:`High Performance Storage` after the project has finished.

Radboud Data Repository
=====

.. dropdown:: About

    The :bdg-primary:`Radboud Data Repository` is an on-campus research data repository where data is backed up
    and ultimately :bdg-warning:`Archived`/ :bdg-warning:`Published` for long-term preservation and sharing. 
    It includes three types of data collections which serve different purposes:

    * :bdg-primary:`Data Acquisition Collections` for raw (unprocessed) data
    * :bdg-primary:`Research Documentation Collections` for scripts, logs, and intermediate data representations describing the research process
    * :bdg-primary:`Data Sharing Collections` for all data and analysis scripts used in creating the results reported in your manuscript

    The endpoint of :bdg-primary:`DAC` and :bdg-primary:`RDC` is :bdg-warning:`archiving`, which is intended only for internal use (i.e. amongst members of the project).
    The endopoint of a :bdg-primary:`DSC` is :bdg-warning:`publishing`.

.. dropdown:: Advantages

    * (Basically) unlimited storage
    * Secure 
    * Facilitates compliance with Findable and Accessible principles of :bdg-info:`FAIR`, thereby meeting :bdg-info:`funder requirements`, many :bdg-info:`journal requirements`, and :bdg-info:`University policy`
    * Data for publication is reviewed for compliance with :bdg-info:`FAIR principles` and privacy risks by a data steward

.. dropdown:: Disadvantages

    * Cannot read/write files directly
    * Platform under continuous development, sometimes services are down for routine maintanence
    * Time investment needed for familiarizing with the platform, and uploading, archiving and publishing data for a project

The :bdg-primary:`Radboud Data Repository` is the :bdg-danger:`DCCN`'s vault where :bdg-warning:`data of finished projects is preserved`. 

.. dropdown:: Take Home Messages

    * Different :bdg-primary:`storage locations` have different use cases, pros and cons and are used in various :bdg-danger:`DCCN` :bdg-warning:`procedures` for data management 
    * :bdg-primary:`High Performance Storage` and the :bdg-primary:`Radboud Data Repository` are the main :bdg-primary:`storage locations` we will use but :bdg-primary:`Local Storage` has certain use cases.
