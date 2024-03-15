# FASTX-Toolkit

```
FASTX TOOLKIT is unmaintained software.
No new features have been added since 2010.

There are many better alternatives for low-level FASTQ/FASTA manipulation. Use at your own risk.
```

## Short Summary

The FASTX-Toolkit is a collection of command line tools for Short-Reads
FASTA/FASTQ files preprocessing.

## More Details

Next-Generation sequencing machines usually produce FASTA or FASTQ files,
containing multiple short-reads sequences (possibly with quality information).

The main processing of such FASTA/FASTQ files is mapping (aka aligning)
the sequences to reference genomes or other databases using specialized
programs.

Example of such mapping programs are:
* [Blat](http://www.kentinformatics.com/index.asp),
* [SHRiMP](http://compbio.cs.toronto.edu/shrimp),
* [LastZ](http://www.bx.psu.edu/miller_lab),
* [MAQ](http://maq.sourceforge.net/)
* And many many others.

However,
It is sometimes more productive to preprocess the FASTA/FASTQ files before
mapping the sequences to the genome - manipulating the sequences to
produce better mapping results.

The FASTX-Toolkit tools perform some of these preprocessing tasks.

## Available Tools

* `fastq_to_fasta` - Converts a FASTQ file to a FASTA file.

* `fastx_quality_stats` - scans a FASTQ file, and produces some statistics about the
	quality and the sequences in the file.

* `fastq_quality_converter` - Converts from ASCII to numeric quality scores.

* `fastq_quality_filter` - removes low-quality sequences from FASTQ files.

* `fastx_artifacts_filter` - removes some sequencing artifacts from FASTA/Q files.

* `fastx_clipper` - Adapters (aka Linkers) are added to the library (before
	sequencing), and should be removed from the resulting FASTA/Q file.
	This tool removes (clips) adapters.

* `fastx_reverse_complement` - Produces a reverse-complement of FASTA/Q file.
	If a FASTQ file is given, the quality scores are also reversed.

* `fastx_trimmer` - Extract sub-seqeunces from FASTA/Q file. Two examples are:
	Removing barcodes from the 5'-end of all sequences in a FASTQ file;
	Cutting 7 nucleotides from the 3'-end of all sequences in a FASTA file.

### Other programs exist, but their description is not provided *(yet)*

* `fastx_uncollapser` - ?

* `fastx_renamer` - ?

* `fastx_collapser` - ?

* `fastq_quality_trimmer` - ?

* `fasta_nucleotide_changer` - ?

* `fasta_formatter` - ?

* `seqalign_test` - ?


## Software Requirements

1. Cmake >= 3.15

2. GCC is required to compile most tools.

3. The `libgtextutils` package is required to build `fasta_formatter` and `fastx_uncollapser` required, see [this](https://github.com/merv1n34k/libgtextutils.git) GitHub repository.


## Installation

To install the tools one can do the following:

```bash
   $ git clone https://github.com/merv1n34k/fastx_toolkit
   $ cd fastx_toolkit
   $ git checkout homebrew
   $ mkdir build && cd build
   $ cmake ..
   $ make install
```

If you are on macOS *(and probably Linux)* you can use [Homebrew](https://brew.sh/):

```bash
   $ brew install merv1n34k/homebrew-tap/fastx_toolkit
```

## Command Line Usage

Most tools support "-h" argument to show a short help screen.
Better documentation is not available at this moment.

## Special configuration for Barcode-Splitter

When running the barcode-splitter tool from the command line you specify a
prefix direcotry - the output files will be written to that directory (similar
to GNU's split program usage).

## LICENSE
FASTX-Toolkit is distributed under the Affero GPL version 3 or later (AGPLv3),

*(notes from author)*

While IANAL, these licenses basically mean that:
1. You're free to use FASTX-toolkit,

2. If you modify the FASTX-toolkit tools, and make those modifications
   publicly available (either as downloadable tools, part of another product),
   or as a web-based server - you must make the modified source code freely
   available (free as in speech).

See the [LICENSE](LICENSE) file for the full Affero GPL.

```
Please remember:
  THERE IS NO WARRANTY FOR THE PROGRAM, TO THE EXTENT PERMITTED BY
APPLICABLE LAW.  EXCEPT WHEN OTHERWISE STATED IN WRITING THE COPYRIGHT
HOLDERS AND/OR OTHER PARTIES PROVIDE THE PROGRAM "AS IS" WITHOUT WARRANTY
OF ANY KIND, EITHER EXPRESSED OR IMPLIED, INCLUDING, BUT NOT LIMITED TO,
THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR
PURPOSE.  THE ENTIRE RISK AS TO THE QUALITY AND PERFORMANCE OF THE PROGRAM
IS WITH YOU.  SHOULD THE PROGRAM PROVE DEFECTIVE, YOU ASSUME THE COST OF
ALL NECESSARY SERVICING, REPAIR OR CORRECTION.
```

---
Please send all comments, suggestions, bug reports (or better yet - bug fixes)
to assafgordon@gmail.com.

## Changes made

* Removed galaxy part of the fastx_toolkit
* Moved project from Autotools to Cmake
* Updated README
* Added Homebrew installation instruction
