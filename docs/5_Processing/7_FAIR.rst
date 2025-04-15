Best Practices for FAIR Research Data
*******

Now, you know how to navigate the :bdg-warning:`infrastructure` of the :bdg-danger:`DCCN` in order to complete your reasearch. 
However, there are some ways that you can improve your :bdg-success:`RDM` practices to increase how :bdg-info:`FAIR` your data is. 
Remember, :bdg-info:`FAIR` is an acronym that stands for *Findable*, *Accessible*, *Interoperable*, and *Reusable*. 
Let's talk through some simple ways that you can go above and beyond the minimum requirements to make your data more :bdg-info:`FAIR`.

Shell Scripting
================

.. Note:: 
    The :bdg-danger:`DCCN` :bdg-primary:`HPC` cluster runs on a distribution of Linux, which you can interact with through the terminal. 
    Shell scripting is, therefore, useful to automate and document processing that you run in a Linux environment

Shell Scripting is a process which involves telling a computer to run certain analysis scripts routinely rather than doing so by manually running scripts in an interactive environment like VSCode, RStudio, MatLab, or a Python IDE (i.e. Spyder or Pycharm). 
Shell Scripting enables increased processing speed, since you can split up iterated processes into different jobs that the :bdg-primary:`HPC Cluster` can run simaltaneously instead of sequentially, like these interactive environments would. 
However, it also eliminates the possibility for human error by running scripts in an incorrect order for instance. 
Furthermore, it also increases the *Interoperability* of your research data: instead of relying on directions from metadata about which sub-directories in your :bdg-primary:`DSC` or :bdg-primary:`Project Folder`, a reader can find a single shell script which tells them:

1. Which files (i.e. scripts) are being used to analyze the data
2. Where these files (i.e. scripts) are located
3. In what order the steps in the processing pipeline are applied
4. Which raw data files are processed

.. _HPC wiki: https://hpc.dccn.nl/docs/bash/index.html

A good convention to save the shell script as ``/project/Scripts/masterPipeline.sh``. 
You can learn a bit about how to automate a script from the bash tutorial on the `HPC wiki`_, however, with a tool such as ChatGPT the learning curve is minimal.

Output to HTML
===============

A relatively simple way to make your data :bdg-info:`FAIR` is to output the analysis scripts to HTML. 
In R and Python, you can do this by creating Notebooks (.Rmd and .ipynb) that contain the endpoints of your analysis pipelines. 
The equivalent in MatLab is a Live Script (.mlx).

Essentially, these notebooks should contain the lines of code which directly produce any Tables or Figures that you report in your manuscript as well as any statistical tests that you report. 
In between these lines of code that you write, you should explain the purpose of each test (i.e. 'Now I want to see if Group A and Group B are different' or 'Now I want to visualize the difference between Group A and Group B'). 
Then, you will want to export these notebooks to .html format and publish them on GitHub. 
This will make your analysis scripts visible as a website which readers can view by visting the URL. 
By doing this, you make your research data more *Interoperable* for those who are interested in how you arrived at your conclusions.

Document Versioning
================

Another important way that you can improve the :bdg-info:`FAIR`-ness of your research data is to version your analysis scripts and other documents. 
As you've just read on the previous page, you should version your analysis scripts and log the changes in a document so that the thought process underlying changes to your analyses are tracked. 
Doing these extra steps can not only save you time (i.e. by documenting the results of different approaches, you can avoid repeating analyses because you forgot the result), 
but also make your data more *Reusabe* since others can see everything that you tried and continue from there. 

Enrich with Documentation
================

A final, basic ways that you can improve the :bdg-info:`FAIR`-ness of your research data is to provide additional documentation. 
Of course, it is necessary to provide basic documentation to indicate how files are organized and which files contain the relevant analysis scripts. 
However, more documentation is always better so you may wish to include these kinds of documentation to improve the *Reusability*:

* Logs from :bdg-secondary:`Data Collection` 
* Plain text descriptions of the function files in a folder
* Plain text descriptions of the procedure of an analysis scripts
* Supplementary information about your storage structure