## Test environments
* local OS X install, R 3.4.0
* ubuntu 12.04 (on travis-ci), R 3.3.3
* winbuilder (devel)

## R CMD check results
There were no ERRORs or WARNINGs on any platform.

There were 2 NOTEs on win-builder devel

https://win-builder.r-project.org/2DwcN806anz3/00check.log

relating to 2 issues:

1. Possibly mis-spelled words in DESCRIPTION:
  Wavemetrics (9:16)
  ibw (10:53)
  pxp (10:24, 12:13)

The first is a company name, the other two are file formats.

2. * checking R code for possible problems ... NOTE
Found the following assignments to the global environment:
File 'IgorR/R/ReadIgorBinary.R':
  assign(WaveName, rval, envir = .GlobalEnv)

This has been discussed in previous submissions and is not a default behaviour
but must be explicitly requested by the user by setting a documented argument
(?read.ibw). The rationale is that some users like to be able to replicate the
behaviour of Igor Pro in which individual records (aka waves) within a single
file are available as individual objects in the user environment. Once again
this must be explicitly requested.

## Downstream dependencies
There are presently no downstream dependencies on CRAN.
