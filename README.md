[![Build Status](https://travis-ci.org/tseemann/varion.svg?branch=master)](https://travis-ci.org/tseemann/varion)
[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
![Don't judge me](https://img.shields.io/badge/Language-Perl_5-steelblue.svg)

:warning: This software is still in early development

# Varion

Find genomiic variantts such as 
substitutons,  small insertions, 
and deletions in  a reference genome 
from short read sequences. 

Combine variant calls from
many isolates into robust alignments
to build phylogenomic trees.

## Introduction

After years of developing my SNP caller
[Snippy](https://github.com/tseemann/snippy)
I wanted to write a new version of it
which utulises recent advances in the 
pipeline components.

## Quick Start

```
% varion version
varion 0.0.1

% varion check
All dependencies installed.

% varion call -o dirA -r ref.fa -1 A_R1.fq.gz -2 A_R2.fq.gz 
Found 43 variants.

% varion call -o dirB -r ref.fa -1 B_R1.fq.gz -2 B_R2.fq.gz 
Found 9 variants.

% varion combine -o AB dirA dirB
Combined 2 runs into 31 variants.

% vsrion tree -c 0.95 -iAB
Wrote tree to AB.nwk
```

## Installation

### Conda
Install [Conda](https://conda.io/docs/) or [Miniconda](https://conda.io/miniconda.html):
```
conda install -c conda-forge -c bioconda -c defaults varion # COMING ONE DAY
```

### Homebrew
Install [HomeBrew](http://brew.sh/) (Mac OS X) or [LinuxBrew](http://linuxbrew.sh/) (Linux).
```
brew install brewsci/bio/varion # COMING ONE DAY
```

### Source

This will install the latest version direct from Github.  You'll need to add
the varion `bin` directory to your `$PATH`, and also ensure all the
[dependencies](#Dependencies) are installed.

```
cd $HOME
git clone https://github.com/tseemann/varion.git
$HOME/varion/bin/varion -h
```

## Dependencies

* `perl` >= 5.26
* `samtools` >= 1.10
* `bcftools` >= 1.10
* `minimap2` >= 2.17

## Etymology

The name `varion` comes from
the noun "variant", the 
class of genomic
feature we are attempting
to identify using this software.

## License

varion is free software, released under the
[GPL 3.0](https://raw.githubusercontent.com/tseemann/varion/master/LICENSE).

## Issues

Please submit suggestions and bug reports to the
[Issue Tracker](https://github.com/tseemann/varion/issues)

## Author

* [Torsten Seemann](https://tseemann.github.io/)
