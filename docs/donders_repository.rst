Donders Repository
******************

The idea is to have Cyberduck and repocli as generic data transfer tools (not having specific DCCN purpose). The Stager and Uploader are tools with DCCN datastructure and use cases in mind.

Another type of tool is for checking data integrity, using Manifest file and checksuming.

We should also make it explicit that the main data transfer protocol is WebDAV, and thus any 3rd party WebDAV client is in-principle working.

Cyberduck
=========

Repocli
=======

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