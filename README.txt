OncoGPS for analyzing IO gene signatures, by Brendan J. Lee

Introduction

This project aims to modify the OncoGPS Paper Analysis performed by Pablo Tamayo's group at UCSD, in order to enable the method to analyze results of clinical trials. To learn more about the OncoGPS method, refer to README_original.md and the link to the journal article on OncoGPS.

Changes to Original OncoGPS Code

Referring to the original OncoGPS Paper Analysis code (link below), Chapters 3 and 5 were modified to allow for the analysis of experimental data. Two major changes to the method were made. First, the gene signature was changed from the KRAS oncogenic activation signature to several Immuno-Oncology (IO) therapy signatures. Two different genesets were used to make this replacement: Positive Hits from CRISPR IO Screens (resistor genes), and negative hits from CRISPR IO Screens (sensitizer genes). This approach enables the discovery of complex cancer phenotypes in the context of the samples' response to IO therapy. Second, the gene expression vs. sample table used in Chapters 3 and 5 was changed from the Cancer Cell Line Encyclopedia (CCLE) Gene Expression Table to the gene expression table of the B9991003 clinical study (link below). Since the samples from the clinical study represent whole tumors in real patients rather than in-vitro cell lines, this change enables OncoGPS to better characterize complex disease states in terms of how well tumors respond to IO therapy. 

Additional Features Added

Other clinical study gene expression tables (from the Braun et. al. clinical trial, link below), similar to the B9991003 study in that all samples were from renal carcinoma (RCC) patients, were used to validate the effectiveness of the NMF and the sample clustering performed by OncoGPS. Using the H Matrix and the W Matrix for the B9991003 study created in this project's Chapter 3 Notebooks, the NMF Matrices of the other samples could be produced by essentially predicting all of the component scores in each new matrix. Then, a nearest centroid classifier was built to predict the phenotypes (or sample states) of the samples from the other clinical trials, using the H matrix and phenotypes of the B9991003 samples (outputted from Chapter 5) as the training data, and the predicted H matrices of the other studies as the test data. The phenotypes of the B9991003 samples and those of the other samples, predicted by the nearest centroid classifier, were compared to one another to ensure similarity between the sets of samples. This allows us to evaluate the accuracy and stability of the OncoGPS NMF and sample clustering methods.

Impact of Results

The phenotypes (sample states) of the B9991003 samples predicted from OncoGPS were uploaded to Data4Cure.com to further analyze the differences between phenotypes, using various B9991003 metadata. These analyses of phenotypes, which especially include the comparison of sample phenotypes in terms of average response to several treatments, are presented in FinalPresentation.pptx in the root directory.

Navigating the File System

The "code" folder contains the modified Chapter 3 and Chapter 5 notebooks, with three notebooks each that correspond to the three different gene signatures chosen for the method. It also contains the nearest centroid classification notebooks for all three genesets, and all necessary input and output files (other than the NMF results in the "output" folder). Inside the "code" folder is the folder "additional notebooks (move out of this folder to use)", which includes all other OncoGPS Chapters (besides 3 and 5) as well as some other notebooks that attempt to change the parameters of the original code, but were not as important in terms of ability to discover novel results.

How to Run This Project

1. set up your computer's environment (follow step 1 in README_original.md, ignore "spro" because this package doesn't seem to exist anymore)
2. clone this repository by typing "git clone <url to this repo>" in the command prompt
3. make sure you are using python 3.6, set up your environment, and run the jupyter notebook application (see "Docker" below)
4. navigate to "code" folder; first run the Chapter 3 notebooks and then the Chapter 5 notebooks
5. modify the code to run it on your own gene signatures and expression tables

Running Code on a Docker

This makes sure that the code is run in the desired environment (i.e. proper python version and packages). The instructions for this process are to be added here in the near future, as I am still figuring out those instructions.

Links
Original OncoGPS Paper Analysis Code: https://github.com/UCSD-CCAL
Full Article on OncoGPS: http://www.cell.com/cell-systems/fulltext/S2405-4712(17)30335-6
B9991003 Study: https://clinicaltrials.gov/ct2/show/NCT02684006
Braun et. al. Study: https://www-nature-com.eu1.proxy.openathens.net/articles/s41591-020-0839-y