# WarpedLMM

#### A python package implementing warped linear mixed models.

Genome-wide association studies, now routine, still have many remaining methodological open problems. Among the most successful models for GWAS are linear mixed models, also used in several other key areas of genetics, such as phenotype prediction and estimation of heritability. However, one of the fundamental assumptions of these models-that the data have a particular distribution (i.e., the noise is Gaussian-distributed)-rarely holds in practice. As a result, standard approaches yield sub-optimal performance, resulting in significant losses in power for GWAS, increased bias in heritability estimation, and reduced accuracy for phenotype predictions.

This repository contains a python implementation of the warped linear mixed model. WarpedLMM automatically learns an optimal "warping function" for the phenotype simultaneously as it models the data. Our approach effectively searches through an infinite set of transformations, using the principles of statistical inference to determine an optimal one. 

#### Installation

WarpedLMM is available from the python package index. 

```shell
pip install warpedlmm
```

#### Getting started

* [Paper] http://dx.doi.org/10.1038/ncomms5890

To run WarpedLMM, open a terminal and execute:

```shell
python -m warpedlmm SNP_file phenotype_file
```

`SNP_file` is a [plink](http://pngu.mgh.harvard.edu/~purcell/plink/data.shtml) BED fileset (e.g. you must have SNP_file.bed, SNP_file.fam, SNP_file.bim).
`pheno_file` is a tab-delimited consisting of 3 columns: individual ID, family ID, phenotype value. For example (look at the [test files]() for more details):

```shell
per0	per0	-1.19539
per1	per1	-0.186557
per2	per2	0.561226
per3	per3	-0.808649
per4	per4	0.0214292
per5	per5	-0.471555
per6	per6	-0.456994
per7	per7	-0.740775
```
 
It's also possible to specify covariates, write the transformed phenotype values to disk, etc.
A list of all the command line options can be accessed using

```shell
python -m warpedlmm --help
```

#### Citing WarpedLMM

Please cite WarpedLMM in your publications if it helps your research:

    @article{fusi2014genetic,
             title={Warped linear mixed models for the genetic analysis of transformed phenotypes.},
             author={Fusi, Nicolo and Lippert, Christoph and Lawrence, Neil D and Stegle, Oliver},
             journal={Nature Communications (in press)},
             doi={10.1038/ncomms5890},
             year={2014}}               

#### Contacting us 

You can submit bug reports using the github issue tracker. 
If you have any other question please contact: fusi [at] microsoft com, stegle [at] ebi ac uk