The Purposes of Research Documentation Collections
**********

You may be wondering, if :bdg-primary:`DACs` are for backing up raw data and :bdg-primary:`DSCs` are for sharing results, what do I need an :bdg-primary:`RDC` for?
Well, :bdg-primary:`RDCs` are intended to internally archive documentation of the research process as well as intermediate data representations that are not directly relevant for the published manuscript (and therefore not made publicly available through the :bdg-primary:`DSC`).
Thus, :bdg-primary:`RDCs` may contain (a) intermediate analysis files, (b) in-progress results, (c) documentation files, and (d) preliminary manuscript versions.

Documentation Files
=========

In addition to intermediate and processed data, :bdg-primary:`RDCs` should ideally contain information about:

1. How analyses may have changed over time
2. What you learned through changing analyses over time
3. Why each version is the way that it is

Therefore, each time you tinker with your script to try something new out, you should save the version of that script as something new and add to your logs about:

1. What you changed
2. Why you changed it
3. What the results were
4. Your thoughts about what the results mean

You should save this documentation in a .txt file. You can also save it in a .docx file, but .txt files can be viewed in any format. 
Documentation files should be put in a folder called ``docs``, which is in your :bdg-primary:`Project Folder` and should be named by the date

.. Note::
    This will help improve the :bdg-primary:`FAIR`-ness of your research data, primarily by increasing its *Interoperability*: adding this documentation will allow others who come after you to pick up where you left off. 
    Additionally, it will increase the *Reusability* of your data, as the :bdg-primary:`RDC` houses information on the context of your data. 
    :bdg-primary:`RDCs` are for (internal) :bdg-warning:`archiving`, meaning that only people given access by one of the collection :bdg-info:`managers` can view this data.

Manuscript Files
======

:bdg-primary:`RDCs` can also be used to house the various versions of your manuscript to ensure that these are recorded and traceable after you finish the project. Note that final published versions of manuscripts should not be archived in the RDR, because these are usually copyrighted by a journal.

Using Stager to Upload Documentation
============

1. Create a documentation file

* In file explorer, navigate to ``/project/3010000.05/XXXXXXX.XX/``
* Create a folder called ``docs``
* In this folder, create a txt file with today's date: ``DD_MM_YYYY.txt``
* In this file, write something

2. Establish a connection to the Trigon Network using either eduVPN or a hardwired connection

.. _this page: https://rdm.dccn.nl/docs/3_Planning/3_Analyzing.html#private-collection-with-repocli

3. Login to Stager

* Go to https://stager.dccn.nl
* In the Project Storage side, enter your DCCN username (for Firstname Lastname this is ``firlas@dccn.nl``) and password, and push ``Login``
* In the Radboud Data Repository side, enter your RU username (``u1234567@ru.nl``) and your Radoud Data Repository password, and push ``Login`` 

* Input your DCCN username in the following format ``firlas@dccn.nl`` and your DCCN password in the fields under the ``Project Storage`` section
* Input your RU username in the following format ``u1234567@ru.nl`` and your Radboud Data Repository password in the fields under the ``Radboud Data Repository`` section (revist `this page`_ if you don't remember how to get your password)

4. Select the Directories to Upload 

* On the Project Storage side, double click ``/3010000.05/`` 
* On the Project Storage side, double click ``/XXXXXXX.XX/`` 
* On the Project Storage side, check the boxes next to the ``results`` and ``scripts`` directories: these are all of the folders we want to share to our :bdg-primary:`RDC`

.. Warning::

    At this stage, you must be **certain** that none of the data in these folders contains sensitive or potentially identifying information if you are sharing your data openly.  

5. Select the Latest Day Directory to Upload to in the Radboud Data Repository

* On the Radboud Data Repository side, double click ``dccn``
* On the Radboud Data Repository side, double click ``RDC_3010000.05_469``
* On the Radboud Data Repository side, double click ``XXXXXXX.XX`` 
* In the Dialog box, type today's date in this format ``DD_MM_YYYY`` and push ``Create``
* On the Radboud Data Repository side, check the box next to the directory you have just created

6. Select the Directories to Upload into Today's Directory

* On the Project Storage side, double click ``/3010000.05/`` 
* On the Project Storage side, double click ``/XXXXXXX.XX/`` 
* On the Project Storage side, double click ``/docs/`` 
* On the Project Storage side, check the box next to the ``DD_MM_YYYY.txt`` file

.. Warning::

    At this stage, you must be **certain** that none of the data in these folders contains sensitive or potentially identifying information if you are sharing your data openly.  

7. Select the Dcoumentation Directory to Upload to in the Radboud Data Repository

* On the Radboud Data Repository side, double click ``dccn``
* On the Radboud Data Repository side, double click ``RDC_3010000.05_469`` 
* On the Radboud Data Repository side, double click ``XXXXXXX.XX`` 
* In the Dialog box, type  ``docs`` and push ``Create``
* On the Radboud Data Repository side, check the box next to the directory you have just created

8. Upload the data to your Research Documentation Collection

* Push the ``Upload`` button

Using Repocli to Upload Documentation
=========

1. Create a documentation file

* In file explorer, navigate to ``/project/3010000.05/XXXXXXX.XX/``
* Create a folder called ``docs``
* In this folder, create a txt file with today's date: ``DD_MM_YYYY.txt``
* In this file, write something

2. Establish a connection to the Trigon Network using either eduVPN or a hardwired connection

.. _this page: https://rdm.dccn.nl/docs/3_Planning/3_Analyzing.html#private-collection-with-repocli

3. Open a TigerVNC session (`read how to do that here`_)

4. Login to the :bdg-primary:`Radboud Data Repository`

* Open TigerVNC
* Open the terminal application
* Type ``repocli shell`` and then push ``enter``
* Type ``config`` and then push ``enter``
* Enter your RU username (u1234567@ru.nl) and then push ``enter``
* Enter the RDR password you retreived in step 2, then push ``enter``

5. Make subdirectories for your files

* Type ``mkdir /dccn/RDC_3010000.05_469/XXXXXXX.XX/DD_MM_YYYY/`` and push ``enter``
* Type ``mkdir /dccn/RDC_3010000.05_469/XXXXXXX.XX/docs/`` and push ``enter``

6. Upload to the Research Documentation Collection 

* Type ``put /project/3010000.05/XXXXXXX.XX/results/ dccn/DAC_3010000.05_873/XXXXXXX.XX/DD_MM_YYYY/`` 
* Type ``put /project/3010000.05/XXXXXXX.XX/scripts/ dccn/DAC_3010000.05_873/XXXXXXX.XX/DD_MM_YYYY/`` 
* Type ``put /project/3010000.05/XXXXXXX.XX/docs/DD_MM_YYYY.txt dccn/DAC_3010000.05_873/XXXXXXX.XX/docs/`` 
