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

Here are some other important ways that you can anonymize your data:

* :bdg-warning:`Pseudonymization Key` deletion - deleting the pseudonymization key removed the link between research data and personal administrative data.
* :bdg-warning:`Data Minimization` - not :bdg-warning:`collecting`, :bdg-warning:`archiving`, or :bdg-warning:`publishing` more personal data than necessary to achieve research goals or support research results
* :bdg-warning:`Data generalization` - reduces the level of detail in the data for variables that (in combination with others) are potentially identifiable, for instance by changing date of birth to birth year

If you want to learn more about these anonymization practices, you can `read more here`_.
For now, let's practice de-facing T1 images.

Defacing A T1 Image with FSL_Deface
======

To deface images, fsl_deface will likely be the most convenient option as FSL is - by default - installed on the :bdg-primary:`HPC Cluster`. 
Thus, you can deface an example T1 image *file.nii* by using the following command.

::
    fsl_deface file.nii defaced_file.nii

In your example project, each subject will have a non-defaced T1 image at ``/project/3010000.05/XXXXXXX.XX/raw/sub-XXX/ses-mri01/002-t1_mprage_sag_ipat2_1p0iso/00001_1.3.12.2.1107.5.2.19.45416.2025010100000000000000000.nii``. 
Let's deface the first subject's T1 image, and save it in the same folder, appended with the word "defaced". 
Of course, please replace XXXXXXX.XX with your assigned project number.
After de-facing the image, you will have to unzip it.


.. dropdown:: Answer

    ::

        fsl_deface /project/3010000.05/XXXXXXX.XX/raw/sub-001/ses-mri01/001-t1_mprage_sag_ipat2_1p0iso/00001_1.3.12.2.1107.5.2.19.45416.2025010100000000000000000.nii /project/3010000.05/XXXXXXX.XX/raw/sub-001/ses-mri01/001-t1_mprage_sag_ipat2_1p0iso/defaced_00001_1.3.12.2.1107.5.2.19.45416.2025010100000000000000000.nii
        gunzip /project/3010000.05/XXXXXXX.XX/raw/sub-001/ses-mri01/001-t1_mprage_sag_ipat2_1p0iso/defaced_00001_1.3.12.2.1107.5.2.19.45416.2025010100000000000000000.nii

After defacing and unzipping, compare both images in your preferred Nifti viewing software. 

Advanced Example: Defacing a Dataset
======

Now let's apply this process recursively, such that we anonymize all T1 images for all subjects. 
Create a file in ``/project/3010000.05/XXXXXXX.XX/scripts/`` called ``defaceAllT1.sh``. 
Open this file and write a script which defaces all T1 images.

.. dropdown:: Hint 1: Find all T1 images

    ::

        #!/bin/bash
        raw="/project/3010000.05/XXXXXXX.XX/raw"
        find "$subject/ses-mri01" -type f -path "*/mprage*/*.nii"

.. dropdown:: Answer

    ::

        #!/bin/bash
        raw="/project/3010000.05/XXXXXXX.XX/raw"

        for subject in "$raw"/sub-*; do
            find "$subject/ses-mri01" -type f -path "/*mprage*/*.nii" | while read -r nii_file; do
                if [[ $(basename "$nii_file") == defaced_* ]]; then
                    continue
                fi

                anat_dir=$(dirname "$nii_file")
                file_name=$(file_name "$nii_file")
                output="$anat_dir/defaced_${file_name}"

                fsl_deface "$nii_file" "$output"
                gunzip -f "${output}.gz"
            done
        done

Now save this file and run it in the terminal by typing the following:

::

    cd /project/3010000.05/XXXXXXX.XX/scripts
    chmod +x defaceAllT1.sh
    ./defaceAllT1.sh "/project/3010000.05/XXXXXXX.XX/raw/"