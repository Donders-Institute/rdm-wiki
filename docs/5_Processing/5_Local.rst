Using Local Storage
********

The :bdg-primary:`HPC cluster` is a powerful tool which enables researchers to improve their efficiency. 
However, users of the :bdg-primary:`HPC cluster` cannot always use certain packages which they might otherwise be able to with :bdg-primary:`Local Storage`.
On the :bdg-primary:`HPC cluster`, the installed version of R is not compatible with the ``effects`` package. 
We have created an ``lme`` object called ``fit`` which we want to plot the effects of using the ``effect`` function in the ``effects`` package to visualize the interaction between trial number and condition on reaction time. 
If you are using a Desktop PC in the DCCN, you can simply run your analysis on the local instance of RStudio (or whatever analysis platform you are using). 
However, if you are not in Trigon or do not have a hardwired connection, you can do so by following the exercises below.

Practice Using Local Storage
======

We've saved our workspace to ``RDM_Workshop_Analysis.RData`` and now we can download this from the HPC cluster and plot the ``fit`` object.

1. Connect to Trigon via eduVPN or a hardwired connnection

2. Connect to an Access Node

* Open Cyberduck
* Click ``Open Connection`` at the top left of the window
* Click on the dropdown menu (which defaults to ``File Transfer Protocol (FTP)``) and select ``SSH File Transfer Protocol (SFTP)`` 
* At the ``Server:`` field type in ``mentat001.dccn.nl``
* Enter your DCCN username (firlas@dccn.nl) and password and then click ``Connect`` at the bottom right side of the window

3. Locate the ``RDM_Workshop_Analysis.RData`` file

* Double-click on the ``project`` directory
* Double-click on the ``3010000.05`` directory
* Double-click on the ``XXXXXXX.XX`` directory
* Double-click on the ``results`` directory
* Single-click on the ``RDM_Workshop_Analysis.RData`` file

4. Download the ``RDM_Workshop_Analysis.RData`` file onto your DCCN or RU Managed device

* Click ``Action`` then ``Download To`` in the dropdown menu
* Single-click the folder you want to download the ``RDM_Workshop_Analysis.RData`` file to
* Push ``OK``

5. Disconnect

Now, if you want, you can open R on your Local PC, open the ``local_analysis.R`` file and open the ``RDM_Workshop_Analysis.RData`` workspace. 
Then, run the script. 
You should see a plot as an output.

.. Note::

    When a package is not available on the :bdg-primary:`HPC Cluster` or cannot be installed by the user, you can arrange this by contacting the DCCN TG. 