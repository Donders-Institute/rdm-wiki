Data Storage Facilities
********

The :bdg-danger:`DCCN` has many :bdg-primary:`data storage facilities` - each with their own advantages and disadvantages. 
It also relies on the :bdg-primary:`Radboud Data Repository`, which is used by the entire :bdg-danger:`RU`.
Knowing :bdg-primary-line:`where` data can and should be stored, as well as :bdg-warning-line:`when` it should be stored in certain locations is 
crucial for being an effective and efficient researcher.

Local Storage
=====

.. dropdown:: About

    :bdg-primary:`Local storage` includes the storage on any local devices such the :bdg-primary:`C:/` drive in your DCCN-issued PC,
    as well as the :bdg-primary:`D:/` drive in lab computers.

.. dropdown:: Advantages 

    Using :bdg-primary:`local storage` can be helpful in multiple :bdg-warning:`stages of the research cycle`. 
    One common use case is if you have a software package that cannot be downloaded on :bdg-primary:`High Performance Storage` - 
    in this case it is best to work with data on the :bdg-primary:`local storage` of the PC issued to you by the Technical Group. 
    Similarly, if you are collecting data in the lab and you are writing data while the experiment is running, you may wish to write the data to the 
    :bdg-primary:`local storage` of the lab computer. 
    Thus, some advantages are:

    * Easy to to access and work with data
    * Can change and update software freely
    * Requires no training

.. dropdown:: Disadvantages

    When conducting analyses on the PC issued to you by the Technical Group, you will need to download your research data onto 
    the :bdg-primary:`local storage` of your device. 
    In such cases, you **MUST** already have anonymized data in case of a data leak from your :bdg-primary:`local storage`. 
    Also, downloading all of the research data may take a long time depending on the size of the data set you are analyzing. 
    Similarly, such analyses generally can be run much faster on the :bdg-primary:`HPC cluster` and may require more RAM (i.e. working memory) than your PC has. 
    Finally, your PC can crash at any moment so all data in :bdg-primary:`local storage` can be lost; 
    thus you must constantly re-upload your data to :bdg-primary:`High Performance Storage` to mitigate potential data loss.
    Thus, some disadvantages are:

    * Constant involuntary risk of data loss
    * Potential for privacy breach
    * Downloading data is time-consuming
    * Requires :bdg-warning:`constant re-uploading` to mitigate potential data loss
    * Less RAM
    * Less storage space 
    * Files are not visible to any other :bdg-info:`research team members`

Ultimately, :bdg-primary:`local storage` is risky because data is not backed up anywhere and inefficient for several reasons. 
Nonetheless, it does have its use-cases though you always must be careful to prevent data loss and breaches in privacy.

High Performance Storage
====

.. dropdown:: About

    :bdg-primary:`High Performance Storage` includes several different drives: most notably
    the :bdg-primary:`Home` drive where your personal files may be kept, 
    the :bdg-primary:`Groupshare` drive where your lab group's shared files may be kept, 
    and the :bdg-primary:`Project` drive where your project files (including research data) is kept. 
    :bdg-primary:`High Performance Storage` consists of drives such as these, which are mounted on Network PC's in Trigon such as those in the Instruction and 
    Trainee rooms as well as all Lab PC's. 
    :bdg-primary:`High Performance Storage` is also compatible with the HPC cluster.

.. dropdown:: Advantages 

    * Larger storage space than :bdg-primary:`local storage` on PCs.
    * Easily accessible via both Network PC's and the HPC Cluster 
    * Easy to access and work with data
    * Set up to work with parallelization, making analysis many times faster
    * Much more working memory than :bdg-primary:`local storage`
    * Another layer of protection against data loss

.. dropdown:: Disadvantages 

    * Sometimes analysis packages/softwares cannot be user-downloaded (may require time for the TG to make these software available)
    * Storage is limited to the duration of the research project
    * Can only be accessed by :bdg-info:`research team members` who are checked into the :bdg-danger:`DCCN`

:bdg-primary:`High Performance Storage` is the workhorse of data analysis at the :bdg-danger:`DCCN`: 
for the vast majority of use cases it is the ideal :bdg-primary:`place` to store data that you will analyze since it 
offers ease-of-access to files and is set up to function with other :bdg-primary:`storage` infrastructure. 
However, due to limited space you cannot leave data on :bdg-primary:`High Performance Storage`.

Radboud Data Repository
=====

.. dropdown:: About

    The :bdg-primary:`Radboud Data Repository` is where data is backed up and ultimately :bdg-warning:`Archived`/ :bdg-warning:`Published`. 
    It includes three types of data collections which serve different purposes:

    * :bdg-primary:`Data Acquisition Collections` for raw data
    * :bdg-primary:`Research Documentation Collections` for scripts and logs outlining your intentions with your analyses
    * :bdg-primary:`Data Sharing Collections` for all data and analysis scripts used in creating the results reported in your manuscript

    The endpoint of :bdg-primary:`DAC` and :bdg-primary:`RDC` is :bdg-warning:`archiving`, which is intended only for internal use (i.e. amongst members of the project).
    The endopoint of a :bdg-primary:`DSC` is `publishing.
`
.. dropdown:: Advantages

    * (Basically) unlimited storage
    * Secure 
    * Facilitates compliance with Findable and Accessible principles of :bdg-info:`FAIR`, thereby meeting :bdg-info:`funder requirements`, many :bdg-info:`journal requirements`, and :bdg-info:`University guidelines`
    * Data for publication is reviewed for compliance with :bdg-info:`FAIR principles` and privacy laws by a data steward

.. dropdown:: Disadvantages

    * Cannot read/write files directly
    * Sometimes services are down for routine maintanence
    * Time investment needed for familiarizing with the platform, and uploading, archiving and publishing data for a project

The :bdg-primary:`Radboud Data Repository` is the :bdg-danger:`DCCN`'s vault where :bdg-warning:`data that is no longer being used is stored`. 

.. dropdown:: Take Home Messages

    * Different :bdg-primary:`storage locations` have different pros and cons which :bdg-danger:`DCCN` :bdg-warning:`policies` are built around 
    * :bdg-primary:`High Performance Storage` and the :bdg-primary:`Radboud Data Repository` are the main :bdg-primary:`storage locations` we will use but :bdg-primary:`Local Storage` and :bdg-primary:`Microsoft Teams` have certain use cases.
