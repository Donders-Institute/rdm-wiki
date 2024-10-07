Anonymizing Your Data
**********

Now that you have :bdg-warning:`archived` the raw data and your documentation of your analyses, you will aim to :bdg-warning:`publish` your processed data and final analysis scripts in a :bdg-primary:`DSC`. 
The :bdg-danger:`RU` policy on data sharing is to share data as openly as is possible, which often means that data sharing is :bdg-info:`Open Access`. 
However, participant privacy must be maintained, so certain precautions must be undertaken to ensure that you are not sharing any potentially identifying information in the research data.

At the :bdg-danger:`DCCN`, the most common kind of potentially identifying information in research data are structural images of participants. 
In these instances it is necessary to :bdg-warning:`de-face` and :bdg-warning:`de-ear` these images so that they cannot be used to identify participants. 
Some common algorithms used to do this include `Quickshear`_, `MRI_Deface`_, `FSL_Deface`_, and `Slant`_. 

.. _Quickshear: https://github.com/nipy/quickshear
.. _FSL_Deface: https://rdrr.io/github/muschellij2/fslr/man/fsl_deface.html
.. _MRI_Deface: https://surfer.nmr.mgh.harvard.edu/fswiki/mri_deface
.. _Slant: https://github.com/MASILab/SLANTbrainSeg

here are some other important ways that you can anonymize your data:

* :bdg-warning:`Pseudonymization Key` - removes the link to personal administrative data by replacing data with pseudonyms that, with a key, can link back to the original data
* :bdg-warning:`Data Minimization` - not :bdg-warning:`collecting`, :bdg-warning:`archiving`, or :bdg-warning:`publishing` more than necessary to achieve research goals or support research results
* :bdg-warning:`Data generalization` - reduces the level of detail in the data for variables that (in combination with others) are potentially identifiable, for instance by changing date of birth to birth year