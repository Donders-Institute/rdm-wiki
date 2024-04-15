BIDS Format
******

The :bdg-info:`Brain Imaging Data Structure format` (or BIDS format for short) is a standardized format for storing research data. 

Benefits of Using BIDS
=========

By keeping your files in :bdg-info:`BIDS format`, you make it easier for other researchers to understand your dataset when re-using it. 
Also, keeping files in :bdg-info:`BIDS format` allows you to use many softwares for analyzing data which exclusively support :bdg-info:`BIDS format`. 

BIDS at the DCCN
======

Automatic research data uploads from the MRI and MEG lab computers save data in :bdg-info:`BIDS format`. 
Manual research data uploads using :bdg-dark:`Uploader` also save data in :bdg-info:`BIDS format`.

However, when you preprocess the data and come up with results, you should try to maintain :bdg-info:`BIDS format`.

BIDS Formatting
=====

:bdg-info:`BIDS format` adheres to the following conventions: 

project/data/subject/session/modality/file.type

At the :bdg-danger:`DCCN` these are the following:

* Project - the 9 digit number you receive for your project (i.e. 123456789.01)
* Data - the type of data you will have in this folder (i.e. raw, preprocessed, or results)
* Subject - the subject number defined by the calendar booking (i.e. 001, 019, or 104)
* Session - the session number defined by the calendar booking (i.e. 01, 03, 10)
* Modality - the data modality you will save (i.e. mri, eeg, beh)

So if I am running project 3010000.05 and I want to save raw behavioral data (a file called behav_data.csv) from subject 010's second session, 
when I give these inputs into :bdg-dark:`Uploader` these would show up on the :bdg-primary:`HPC Cluster` as:

``/project/3010000.05/raw/sub-010/ses-02/beh/behav_data.csv``

and if I was collecting MRI data, these would appear in: 

``/project/3010000.05/raw/sub-010/ses-02/mri/``

.. dropdown:: Take Home Messages

    * :bdg-info:`BIDS format` is beneficial for improving the re-usability of your research data and opening the opportunity to use certain software packages
    * Complying with :bdg-info:`BIDS format` is made easier within the context of the :bdg-danger:`DCCN`
