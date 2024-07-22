Analyzing Data with the HPC Cluster
*********

Now that we have a complete data set, we can analyze our data on the :bdg-primary:`HPC Cluster`. 
Let's take look at how you can do that!

Practice Analyzing Data on the :bdg-primary:`HPC Cluster`
=======

Now that we have all of the data, we will run an analysis script. 

1. Identify subjects between 1 and 10 whose data should be excluded from the analysis

* Return to File Explorer (you should be in the ``/project/3010000.05/data`` directory)
* Open the ``excluded_subjects.txt`` file

2. Begin an RStudio session

* Click on ``Applications`` and select ``Terminal Emulator`` in the dropdown menu
* Type ``rstudio`` and push enter
* Push ``OK`` to take the default versions of R and RStudio
* Push ``OK`` to take the default time and memory specifications for your job

3. Edit your Analysis File

* Push Control and o together once RStudio has loaded
* Double-click ``project`` on the left panel
* Type ``3010000.05`` and push enter
* Double-click ``results``
* Double-click ``firlas`` where firlas is your DCCN username
* Double-click on the ``analysis.R`` file you uploaded
* At the top of the script, change the ``outfile`` variable to ``/project/3010000.05/results/firlas`` where firlas is your DCCN username
* On the next line, change the ``excluded_subjects`` variable to a numeric vector which includes only the subject numbers of excluded subjects (i.e. if ``sub-010`` is exlcuded, include ``10`` in this vector)

4. Select the entire document and push control and enter together to run the script

5. Save the workspace 

* Navigate to the ``Environment`` tab at the bottom right once the script has finished running
* Click the blue square in the ``Environment`` tab to save the workspace as, and save the workspace as ``RDM_Workshop_Analysis`` in the ``/project/3010000.05/results/firlas`` folder

6. Disconnect