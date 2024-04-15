Data Storage Facilities
********

The :bdg-danger:`DCCN` has many :bdg-primary:`data storage facilities` - each with their own advantages and disadvantages. 
Knowing :bdg-primary-line:`where` data can and should be stored, as well as :bdg-warning-line:`when` it should be stored in certain locations is crucial in generating a plan of how you will manage data.

:bdg-primary:`Local Storage`
=====

:bdg-primary:`Local storage` includes the storage on any local devices such the :bdg-primary:`C:/` drive in your DCCN-issued PC or your personal laptop,
as well as the :bdg-primary:`D:/` drive in lab computers.

.. dropdown:: Advantages 

    Using :bdg-primary:`local storage` can be helpful in multiple :bdg-warning:`stages of the research cycle`. 
    One common use case is if you have a software package that cannot be downloaded on :bdg-primary:`High Performance Storage` - 
    in this case it is best to work with data on the :bdg-primary:`local storage` of your personal PC or on the PC issued to you by the Technical Group. 
    Similarly, if you are collecting data in the lab and you are writing data while the experiment is running, you may wish to write the data to the 
    :bdg-primary:`local storage` of the lab computer. 
    Thus, some advantages are:

    * Easy to to access and work with data
    * Can change and update software freely
    * Requires no training

.. dropdown:: Disadvantages

    When conducting analyses on your personal PC or the PC issued to you by the Technical Group, you will need to download your research data onto 
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
    * Requires constant re-uploading to mitigate potential data loss
    * Less RAM
    * Less storage space 

Ultimately, :bdg-primary:`local storage` is risky because data is not backed up anywhere and inefficient for several reason. 
Nonetheless, it does have its use-cases though you always must be careful to prevent data loss and breaches in privacy.

:bdg-primary:`High Performance Storage`

:bdg-primary:`High Performance Storage` includes several different drives: most notably
the :bdg-primary:`Home`drive where your personal files may be kept, 
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

.. dropdown:: Disdvantages 

    * Sometimes analysis packages/softwares cannot be user-downloaded
    * Not suitable for long-term storage

