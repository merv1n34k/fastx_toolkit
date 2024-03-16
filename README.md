# FASTX-TOOLKIT

**This version of `fastx_toolkit` has been transferred to a modern version of Cmake, Perl scripts are *temporally* dropped from support.**

## Short Summary

The `fastx_toolkit` is a collection of command line tools for Short-Reads
FASTA/FASTQ files preprocessing.

## More Details

Next-Generation sequencing machines usually produce FASTA or FASTQ files,
containing multiple short-reads sequences (possibly with quality information).

The main processing of such FASTA/FASTQ files is mapping (aka aligning)
the sequences to reference genomes or other databases using specialized
programs.

Example of such mapping programs are *(many of them are unmaintained)*:
* [Blat](http://www.kentinformatics.com/index.asp),
* [SHRiMP](http://compbio.cs.toronto.edu/shrimp),
* [LastZ](http://www.bx.psu.edu/miller_lab),
* [MAQ](http://maq.sourceforge.net/)
* And many many others.

However,
It is sometimes more productive to preprocess the FASTA/FASTQ files before
mapping the sequences to the genome - manipulating the sequences to
produce better mapping results.

The `fastx_toolkit` tools perform some of these preprocessing tasks.

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

2. GCC (passing on 13.2.0), but probably >= 6 will be sufficient

3. Pkg-config (passing on 0.29.2)

4. The `libgtextutils` package is required to build `fasta_formatter` and `fastx_uncollapser` tools, see [this](https://github.com/merv1n34k/libgtextutils.git) GitHub repository.

## Installation

To install the tools one can do the following:

```bash
   $ git clone https://github.com/merv1n34k/fastx_toolkit
   $ cd fastx_toolkit
   $ mkdir build && cd build
   $ cmake ..
   $ make install
```

If you are on macOS *(and probably Linux)* you can use [Homebrew](https://brew.sh/):

```bash
   $ brew tap merv1n34k/tap
   $ brew install merv1n34k/tap/fastx_toolkit
```

## Command Line Usage

Most tools support "-h" argument to show a short help screen.
Better documentation is not available at this moment.

## LICENSE
Distributed under the Affero GPL version 3 or later (AGPLv3), see LICENSE.

## Notes from author

Assaf Gordon designed and implemented `fastx_toolkit`.

Many people have further contributed to `fastx_toolkit` by reporting problems,
suggesting various improvements, or submitting actual code. Here is
a list of these people. Help me keep it complete and exempt of errors.

Many Hannon-lab members at CSHL (who preferred to remain anonymous).

---

Please send all comments, suggestions, bug reports (or better yet - bug fixes)
to assafgordon@gmail.com.

## Notes from me
Feel free to open issues in this repository, PRs are appreciated :3

## Changes made

* Removed galaxy part of the `fastx_toolkit`
* Moved project from Autotools to Cmake
* Updated README
* Added Homebrew installation instruction
