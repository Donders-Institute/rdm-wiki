The Purposes of Research Documentation Collections
**********

You may be wondering, if :bdg-primary:`DACs` are for backing up raw data and :bdg-primary:`DSCs` are for sharing results, what do I need an :bdg-primary:`RDC` for?
Well, :bdg-primary:`RDCs` are intended to internally archive documentation of the research process as well as intermediate data representations that are not directly relevant for the published manuscript (and therefore not made publicly available through the :bdg-primary:`DSC`).
Thus, :bdg-primary:`RDCs` may contain (a) intermediate analysis files, (b) in-progress results, (c) documentation files, and (d) preliminary manuscript versions.

Documentation Files
=========

.. _this intranet page: https://intranet.donders.ru.nl/index.php?id=6800

In addition to intermediate and processed data, :bdg-primary:`RDCs` should ideally contain additional information. 
On `this intranet page`_ you can find detailed guidance on what specific kinds of data should be placed in :bdg-primary:`RDCs`. 
Generally, however, you :bdg-primary:`RDCs` should house files pertaining to how:

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
    This will help improve the :bdg-primary:`FAIR`-ness of your research data, primarily by increasing its *Reusability*: adding this documentation will allow others who come after you to pick up where you left off. 
    Additionally, the :bdg-primary:`RDC` houses information on the context of your data, which also benefits future users. 
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

.. _this page: https://rdm.dccn.nl/docs/3_Planning/3_Analyzing.html#private-collection-with-repocli
.. _read how to do that here: https://intranet.donders.ru.nl/index.php?id=vnc00&no_cache=1&sword_list%5B%5D=tigerVNC

* After login, the folders in the DCCN Project Storage are displayed on the left side of the screen.
* Input your RDR data access credentials in the fields under the ``Radboud Data Repository`` section (revist `this page`_ if you don't remember where to find these)

4. Select the Directories to Upload 

* On the Project Storage side, double click ``/3010000.05/`` 
* On the Project Storage side, double click ``/XXXXXXX.XX/`` 
* On the Project Storage side, check the boxes next to the ``results`` and ``scripts`` directories: these are all of the folders we want to share to our :bdg-primary:`RDC`

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

.. _read how to do that here: https://intranet.donders.ru.nl/index.php?id=vnc00&no_cache=1&sword_list%5B%5D=tigerVNC

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
