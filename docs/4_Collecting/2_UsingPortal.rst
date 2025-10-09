Using the DCCN Portal
**********

The :bdg-warning:`DCCN Portal` is where you manage all of your projects and book laboratories. 
In order to log into https://portal.dccn.nl/, you will need to establish a connection to the Trigon network. 

Managing Your Project
=========

1. Go to the top right of the portal and click on your name, then select ``My Profile`` on the dropdown
2. Go to the ``Owned Projects`` tab at the bottom of the screen and choose the project you want to view
3. You can add experimenters, view lab bookings, monitor used project storage, and edit :bdg-warning:`Data Access Roles`

.. _command-line tools: https://hpc.dccn.nl/docs/project_storage/access_management.html

.. Note::
    Data-access roles modified in the :bdg-warning:`DCCN Portal` will not be applied recursivly on existing files/directories within the :bdg-primary:`Project Folder`. For applying the changes to existing files/directories, use the `command-line tools`_ on the :bdg-primary:`HPC Cluster`.

Making a Calendar Booking
========

1. Go to ``Calendars`` in the top banner
2. Tap the ``DCCN`` dropdown on the left side of the screen, then the correct modality dropdown(s), then the correct lab(s)
3. Navigate to the correct date and time and ensure that the lab(s) are not yet booked
4. Click ``New booking`` and fill in the correct information

Subject Numbers
=========

When you make your booking, you will assign a project-specific subject-session number to the booking. 
When using the MRI and MEG labs, you will collect your booking under the project-subject-session numbers for the slot that you booked. 
This will be enable the data to automatically be saved to your :bdg-primary:`Project Folder`. 

When saving data from other modalities, you should use this combination of project-subject-session numbers to upload data via the Uploader. 
You should also log your :bdg-info:`Case Report Forms` in castor using the same subject number, as this will make it easier for you to backtrack if data goes missing or you are trying to figure out if something happened during a specific session.
In addition, adopting the subject-session numbers facilitates pseudonymization of the research data - a requirement to protect participant privacy.

.. Warning::

    A key file linking the subject numbers to administrative information of participants (identifiable information) should always be stored separate from research data.
    These key files must be kept in a secure location that can only be accessed by project members who need to use it.
