Data Transfer Tools
******

Defining Data Transfer Tools
==========

:bdg-dark:`Data Transfer Tools` are computer programs which support moving data from :bdg-primary:`Storage Facility` to :bdg-primary:`Storage Facility`. 

.. Warning::

      You may be wondering, *Why can't I just use a removable thumb drive or just email data to myself?* 
      Using either of these approaches increases the likelihood of losing or misplacing data, data breaches, and security risks (e.g. introducing malware into our systems). 
      Besides, the tools introduced below are much more efficient when moving large amounts of data from place to place. 
      Therefore, these :bdg-dark:`Data Transfer Tools` are necessary for data security and are beneficial for user efficiency.

      Using alternative methods to transfer data is only possible when there are no other alternatives available and should only be done in consultation with the DCCN data steward and DCCN IT helpdesk.

Supported Tools
======

At the :bdg-danger:`DCCN`, we primarily support four :bdg-dark:`Data Transfer Tools`. 
Each of these four :bdg-dark:`tools` have their advantages and disadvantages: :bdg-danger:`DCCN` :bdg-warning:`procedures` are shaped around these to maximize ease-of-use and efficiency.

There is no need to memorize the specifics of each of these :bdg-dark:`tools` - just know that there are multiple tools which have different forms and different function!

.. _Cyberduck: http://cyberduck.io
.. _Repocli: https://github.com/Donders-Institute/dr-tools/tree/main/cmd/repocli
.. _Stager: https://stager.dccn.nl
.. _Uploader: https://uploader.dccn.nl

Tools at a Glance
========

:bdg-dark:`Cyberduck` and :bdg-dark:`Repocli` are both generic tools which support the transfer of data to-and-from all of our main :bdg-primary:`Storage Facilities`. 
:bdg-dark:`Cyberduck` is easier to use while :bdg-dark:`Repocli` offers more scriptability.

In contrast, :bdg-dark:`Stager` and :bdg-dark:`Uploader` are :bdg-danger:`DCCN` specific :bdg-dark:`tools` which serve very case-specific functions. 
:bdg-dark:`Uploader` is used to simultaneously move raw data from :bdg-primary:`Local storage` into the :bdg-primary:`Project Folder` and the :bdg-primary:`Data Acquisition Collection` 
(the :bdg-primary:`RDR` collection that saves raw data) 
which automatically saves these data in a standardized, easy-to-use format (this is called :bdg-info:`BIDS format`, more on this in a second as well).
:bdg-dark:`Stager` moves data between the :bdg-primary:`Project Folder` and the :bdg-primary:`RDR`, enabling researchers to efficiently restore lost data (or use existing data) or archive data.

.. table::
   :widths: auto

   +-------------------+-----------------+-----------------+--------------------------+--------------------------------+
   |                   | `Cyberduck`_    | `Repocli`_      |  `Stager`_               | `Uploader`_                    |
   +===================+=================+=================+==========================+================================+
   | *User Interface*  | Graphical       | Comamnd-Line    |  Web                     | Web                            |
   +-------------------+-----------------+-----------------+--------------------------+--------------------------------+
   | *Transfer Routes* | | Local <=> RDR | | Local <=> RDR | | Project <=> RDR        | | Local => Project             |
   |                   | | Local <=> HPC | | HPC <=> RDR   |                          | | Local => RDR                 |
   +-------------------+-----------------+-----------------+--------------------------+--------------------------------+
   | | *Access*        |                 |                 | | Trigon Network         | | Trigon Network               |
   | | *Restriction*   |                 |                 | | (wired or via eduVPN)  | | (wired or via eduVPN)        |
   +-------------------+-----------------+-----------------+--------------------------+--------------------------------+
   | *OS Support*      | | Windows       | | Windows       | | Windows                | | Windows                      |
   |                   | | MacOSX        | | MacOSX        | | MacOSX                 | | MacOSX                       |
   |                   |                 | | Linux         | | Linux                  | | Linux                        |
   +-------------------+-----------------+-----------------+--------------------------+--------------------------------+
   | *Key Feature*     | Ease-of-use     | Scriptable      | Efficient                | Data Organization              |
   +-------------------+-----------------+-----------------+--------------------------+--------------------------------+

.. dropdown:: Take Home Messages

    * :bdg-dark:`Data Transfer Tools` are necessary to ensure data security and to maximize efficiency
    * Some :bdg-dark:`Data Transfer Tools` are better than others in certain situations
