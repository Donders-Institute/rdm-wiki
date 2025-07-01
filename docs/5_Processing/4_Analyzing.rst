Analyzing Data with the HPC Cluster
*********

Now that we have a complete data set, we can analyze our data on the :bdg-primary:`HPC Cluster`. 
Let's take look at how you can do that!

Practice Analyzing Data on the :bdg-primary:`HPC Cluster`
=======

Now that we have all of the data, we will run an analysis script. 

1. Identify subjects between 1 and 10 whose data should be excluded from the analysis

* Return to File Explorer (you should be in the ``/project/3010000.05/XXXXXXX.XX/raw/`` directory)

2. Begin an RStudio session

* Click on ``Applications`` and select ``Terminal Emulator`` in the dropdown menu
* Type ``rstudio`` and push enter
* Push ``OK`` to take the default versions of R and RStudio
* Push ``OK`` to take the default time and memory specifications for your job

3. Edit your Analysis File

* Push Control and o together once RStudio has loaded
* Double-click ``project`` on the left panel
* Type ``3010000.05`` and push enter
* Type ``XXXXXXX.XX`` and push enter
* Double-click ``results``
* Double-click on the ``analysis.R`` file you uploaded
* At the top of the script, change the ``outfile`` variable to ``/project/3010000.05/XXXXXXX.XX/results``

4. Select the entire document and push control and enter together to run the script

5. Save the workspace 

* Navigate to the ``Environment`` tab at the bottom right once the script has finished running
* Click the blue square in the ``Environment`` tab to save the workspace as, and save the workspace as ``RDM_Workshop_Analysis`` in the ``/project/3010000.05/XXXXXXX.XX/results`` folder

6. Disconnect

.. _HPC wiki: https://hpc.dccn.nl/docs/bash/exercise_script.html

To read more about how to run analyses on the :bdg-primary:`HPC Cluster` and to get more practice, visit these pages on the `HPC wiki`_.