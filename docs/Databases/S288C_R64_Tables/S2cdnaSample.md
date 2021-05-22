# S2cdnaSample

Second Strand cDNA Table

There should be one entry per tube full of double-stranded DNA.  

Name                                            | Type     | Required  
------------------------------------------------|:--------:|:-----------:
[s1cDNASampleNumber](#s1cDNASampleNumber)       | int      | Yes
[s2cDNADate](#s2cDNADate)                       | datetime | Yes
[s2cDNAPreparer](#s2cDNAPreparer)               | string   | Yes
[s2Observations](#s2Observations)               | string   | Yes
[roboticS2Prep](#roboticS2Prep)                 | boolean  | Yes
[PooledSecondStrand](#PooledSecondStrand)       | boolean  | Yes

* * *

## s1cDNADate, s1cDNAPreparer, S1cDNASampleNumber

**[REQUIRED]** The entries in these three columns should exactly match the corresponding entries for one and only row of a [s1cDNASample](S1cdnaSample.md) table. See [general specifications](../GeneralSpecs.md) for format details.

## s2cDNADate

**[REQUIRED]** The date (e.g. 05.17.20) on which the second strand cDNA was prepared and ready for use. See [general specifications](../GeneralSpecs.md) for format details.

## s2cDNAPreparer

**[REQUIRED]** Name (e.g. M.BRENT) of the person who was in charge of the second strand cDNA preparation (try not to split these, or we will have to add more fields!). If more than one person was involved, just pick one. See [general specifications](../GeneralSpecs.md) for format details.

## s2cDNASampleNumber

**[REQUIRED]** Sequential positive integers uniquely identifying the double-stranded cDNA samples prepared by a given preparer on a given date.

## s2cDNAProtocol

**[REQUIRED]** Entries, to be defined, indicating the kit or protocol used for generating the second strand. Should be a single string of letters with no whitespace. Add any entries used below, with an explanation.

- SuperScriptIII
- E7420L -  NEBNext Ultra Directional RNA Library Prep Kit for Illumina
- If a concentration other than typical is used, list it as such: E7420L_0.5X

## PooledSecondStrand

**[REQUIRED]** Boolean. Make sure formatting of True/False value is appropriate for the program you are using

## roboticS2Prep

**[REQUIRED]** Boolean. Make sure formatting of True/False value is appropriate for the program you are using
