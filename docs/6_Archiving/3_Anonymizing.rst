Anonymizing Your Data
**********

Now that you have :bdg-warning:`archived` the raw data and your documentation of your analyses, you will aim to :bdg-warning:`publish` your processed data and final analysis scripts in a :bdg-primary:`DSC`. 
The :bdg-danger:`RU` policy on data sharing is to share data as open as is possible, as closed as necessary. This means that sharing data :bdg-info:`Open Access` is the standard, but that there can be valid reasons (e.g. legal, ethical, privacy) to put restrictions on access to or reuse of the data. 
To protect participant privacy, certain precautions must be undertaken to ensure that you are removing any (potentially) identifying information in the research data as much as possible.

At the :bdg-danger:`DCCN`, one of the most common kind of potentially identifying information in research data are structural MR images of participants. 
In these instances it is necessary to :bdg-warning:`de-face` and :bdg-warning:`de-ear` these images so that they cannot be used to identify participants. 
Some common algorithms used to do this include `Quickshear`_, `MRI_Deface`_, `FSL_Deface`_, and `Slant`_. 

.. _Quickshear: https://github.com/nipy/quickshear
.. _FSL_Deface: https://rdrr.io/github/muschellij2/fslr/man/fsl_deface.html
.. _MRI_Deface: https://surfer.nmr.mgh.harvard.edu/fswiki/mri_deface
.. _Slant: https://github.com/MASILab/SLANTbrainSeg
.. _read more here: https://intranet.donders.ru.nl/index.php?id=6800

here are some other important ways that you can anonymize your data:

* :bdg-warning:`Pseudonymization Key` deletion - eleting the pseudonymization key removed the link between research data and personal administrative data.
* :bdg-warning:`Data Minimization` - not :bdg-warning:`collecting`, :bdg-warning:`archiving`, or :bdg-warning:`publishing` more personal data than necessary to achieve research goals or support research results
* :bdg-warning:`Data generalization` - reduces the level of detail in the data for variables that (in combination with others) are potentially identifiable, for instance by changing date of birth to birth year

If you want to learn more about these anonymization practices, you can `read more here`_.
