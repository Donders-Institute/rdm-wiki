Donders Repository
******************

The idea is to have Cyberduck and repocli as generic data transfer tools (not having specific DCCN purpose). The Stager and Uploader are tools with DCCN datastructure and use cases in mind.

Another type of tool is for checking data integrity, using Manifest file and checksuming.

We should also make it explicit that the main data transfer protocol is WebDAV, and thus any 3rd party WebDAV client is in-principle working.

.. _Cyberduck: http://cyberduck.io
.. _Repocli: https://github.com/Donders-Institute/dr-tools/tree/main/cmd/repocli
.. _Stager: https://stager.dccn.nl
.. _Uploader: https://uploader.dccn.nl
.. _eduVPN: https://intranet.donders.ru.nl/index.php?id=eduvpn
.. _SSH tunnel: https://intranet.donders.ru.nl/index.php?id=remoteaccess

Overview of data transfer tools
===============================

.. table::
   :widths: auto

   +-------------------+----------------+----------------+-------------------------+--------------------------------+
   |                   | `Cyberduck`_   | `Repocli`_     |  `Stager`_              | `Uploader`_                    |
   +===================+================+================+=========================+================================+
   | *user Interface*  | graphical      | comamnd-line   |  web                    | web                            |
   +-------------------+----------------+----------------+-------------------------+--------------------------------+
   | *transfer routes* | local <-> DR   | | local <-> DR |  project storage <-> DR | local <-> project storage + DR |
   |                   |                | | HPC <-> DR   |                         |                                |
   +-------------------+----------------+----------------+-------------------------+--------------------------------+
   | | *access*        |                |                | | DCCN Trigon network   | | DCCN Trigon network          |
   | | *restriction*   |                |                | | or `eduVPN`_          | | or `eduVPN`_                 |
   +-------------------+----------------+----------------+-------------------------+--------------------------------+
   | *OS support*      | | Windows      | | Windows      | | Windows               | | Windows                      |
   |                   | | MacOSX       | | MacOSX       | | MacOSX                | | MacOSX                       |
   |                   |                | | Linux        | | Linux                 | | Linux                        |
   +-------------------+----------------+----------------+-------------------------+--------------------------------+
   | *key feature*     | ease-of-use    | scriptable     | efficient               | automatic data organization    |
   +-------------------+----------------+----------------+-------------------------+--------------------------------+
   | | *recommanded*   |                |                |                         |                                | 
   | | *usage*         |                |                |                         |                                |
   +-------------------+----------------+----------------+-------------------------+--------------------------------+

Cyberduck
=========

A graphical tool for transferring data between local computer and the Donders Repository.  It supports Windows and MacOSX.

Repocli
=======

A command-line tool for transferring data between local computer and the Donders Repository.  It supports Windows, MacOSX and Linux.

Think about scripts or cron-job examples around repocli to simplify user transfers.

Stager
======

Uploader
========

Data integrity checking
=======================

Idea is to provide some example script to efficiently compare the downloaded Manifest file against local dataset.

* result from `sha256sum` (useful for downloaded dataset from the DR)
* resolve files not yet uploaded in the repository (supplement information to detect whether data has been uploaded completely)
