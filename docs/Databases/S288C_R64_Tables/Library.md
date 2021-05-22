# Library

Each entry denotes one library, even if multiple aliquots are made and sequenced at different times. A library means something with Illumina sequencing primers, indices or barcodes as needed, and ready to pool and put into a lane.

Name                                            | Type     | Required
------------------------------------------------|:--------:|:-----------:
[s2cDNASampleNumber](#s2cDNASampleNumber)       | int      | Yes (Foreign Key)
[libraryDate](#libraryDate)                     | datetime | Yes (Primary Key)
[libraryPreparer](#libraryPreparer)             | string   | Yes
[libraryObservations](#libraryObservations)     | string   | Yes
[index1Sequence](#index1Sequence)               | string   | Yes
[libraryProtocol](#libraryProtocol)             | string   | Yes
[index1Name](#index1Name)                       | string   | Yes
[index2Name](#index2Name)                       | string   | Yes
[index2Sequence](#index2Sequence)               | string   | Yes
[roboticLibraryPrep](#roboticLibraryPrep)       | boolean  | Yes

* * *

## s2cDNASampleNumber

Foreign key to s2 table

## libraryDate

The date (e.g. 05.17.20) on which the sequencing library was prepared and ready for use. Provide the date when the library was completed. See [general specifications](https://github.com/BrentLab/database_files/wiki) for format details.

## libraryPreparer

Name (e.g. M.BRENT) of the person who was in charge of the sequencing library preparation. If more than one person was involved, just pick one. See [general specifications](https://github.com/BrentLab/database_files/wiki) for format details.

## librarySampleNumber

Sequential positive integers uniquely identifying the libraries prepared by a given preparer on a given date.

## index1Name

E.g. “Index1_2”.

## index1Sequence

The sequence of index one (all caps), used to help distinguish samples pooled into a single lane. “NA” if no indices are used.

## index2Name

- SIC_Index2_06
- universal

## index2Sequence

The sequence of index two (all caps), used to help distinguish samples pooled into a single lane. “NA” if zero or one indices are used.

## libraryProtocol

Use only the first part of the descrition below, eg E7420L. Datatype must be a single string of letters with no whitespace.

- SolexaPrep - homebrew kit used prior to 10-25-2015 (best current estimate)
- E7420L -  NEBNext Ultra Directional RNA Library Prep Kit for Illumina
- If a concentration other than typical is used, list it as such: E7420L_0.5X

## roboticLibraryPrep

“True” (with that capitalization) if the robot was used, “False” if not.
