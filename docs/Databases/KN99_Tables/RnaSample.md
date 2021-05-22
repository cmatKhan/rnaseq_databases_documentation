# RnaSample

If multiple aliquots of RNA are made from a single tube or well, they are the same RNA sample, so only one entry is needed.

Name                                            | Type     | Required  
------------------------------------------------|:--------:|:-----------:
[bioSampleNumber](#bioSampleNumber)             | int      | yes (Foreign Key)
[rnaSampleNumber](#rnaSampleNumber)             | string   | yes (Primary Key)
[rnaDate](#rnaDate)                             | datetime | Yes
[rnaPreparer](#rnaPreparer)                     | string   | Yes
[rnaSampleObservations](#rnaSampleObservations) | string   | Yes
[rnaPrepMethod](#rnaPrepMethod)                 | string   | Yes
[roboticRnaPrep](#roboticRnaPrep)               | boolean  | Yes
[ribosomalBand](#ribosomalBand)                 | boolean  | No
[ribosomalBandShape](#ribosomalBandShape)       | string   | No
[smallRNABands](#smallRNABands)                 | string   | No
[rin](#rin)                                     | float    | No

* * *

## bioSampleNumber

Foreign key to bioSample Table

## rnaSampleNumber

Primary key of rnaSample table

## rnaDate

The date (e.g. 05.17.20) on which the total rna was prepared and ready for use. See [general specifications](https://github.com/BrentLab/database_files/wiki) for format details.

## rnaPreparer

Name of the person (e.g. M.BRENT) who was in charge of the total RNA isolation. If more than one person was involved, just pick one. See [general specifications](https://github.com/BrentLab/database_files/wiki) for format details.

## rnaSampleObservations

**[OPTIONAL]** This is a free text entry field meant to record anything about this sample, specifically pertaining to this table's data, that does not fit into other fields. This __should not be used for storing any information pertinent to experimental design__.

## rnaPrepMethod

One of the following. If anything other than these is entered, it should be added to the list below with an explanation. For each entry, there should be a detailed protocol document with the same name. Any time the protocol is changed, a new document should be made up describing the differences relative to an older document. Older documents should never be deleted.

- __DirectZol__ -- DirectZol kit from Zymo, per instructions
- __RiboPure0.5X__ -- RiboPure Yeast kit from Ambion, using 0.5 times volume and reagents in instructions.
- __RiboPure0.25X__ -- RiboPure Yeast kit from Ambion, using 0.25 times volume and reagents in instructions.
- __RiboPure0.125X__ -- RiboPure Yeast kit from Ambion, using 0.125 times volume and reagents in instructions.
- __ComboA__ -- uses a combination of RNA prep methods, homogenize RNA following the Directzol kit from Zymo, and purify RNA using the RiboPure Yeast kit from Ambion (using 0.25 times volume and reagents).
- __ComboB__ -- uses a combination of RNA prep methods, homogenize RNA following the RiboPure Yeast kit from Ambion (using 0.25 times volume and reagents), and purify RNA using the Directzol kit from Zymo.
- __TRIzol__

## rnaPrepProtocol

The name of a file in the protocols directory under the experimenter directory. Can be reused in multiple files -- no need to rename as long as the protocol is unchanged.

## roboticRnaPrep

**[REQUIRED]** Boolean, True of False (be sure to use the correct formatting for whatever program you're using for this)

## ribosomalBand (TRUE or FALSE)

**[OPTIONAL]** Boolean, True of False (be sure to use the correct formatting for whatever program you're using for this)

## ribosomalBandShape

**[OPTIONAL]** ChoiceS: straight, smile, or NA

## smallRNABands

**[OPTIONAL]** Boolean, True of False (be sure to use the correct formatting for whatever program you're using for this)

## rin
**[OPTIONAL]** A value assigned by the Bioanalyzer between 0 and 10
