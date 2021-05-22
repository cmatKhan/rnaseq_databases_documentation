# S1cdnaSample

First Strand cDNA sample Table  

If multiple aliquots of the first strand product made in a single pool or well are combined into different pools for second strand synthesis, they are the same first strand sample so only one entry is needed.  


Name                                                | Type       | Required  
----------------------------------------------------|:----------:|:-----------:
[rnaSampleNumber](#rnaSampleNumber)                 | int        | yes (Foreign Key)es
[s1cDNADate](#s1cDNADate)                           | datetime   | yes (Primary Key)
[s1cDNAPreparer](#s1cDNAPreparer)                   | string     | Yes
[s1Observations](#s1Observations)                   | string     | Yes
[polyAIsolationProtocol](#polyAIsolationProtocol)   | string     | Yes
[s1cDNAProtocol](#s1cDNAProtocol)                   | string     | Yes
[roboticS1Prep](#roboticS1Prep)                     | boolean    | Yes
[s1PrimerSeq](#s1PrimerSeq)                         | string     | Yes

* * *

## rnaSampleNumber

**[REQUIRED]** Foreign key to rnaSample Table

## s1cDNADate

**[REQUIRED]** The date (e.g. 05.17.20) on which the first strand cDNA was prepared and ready for use. See date format at the top of this document. See [general specifications](../GeneralSpecs.md) for format details.

## s1cDNAPreparer

**[REQUIRED]** Name of the person (e.g. M.BRENT) who was in charge of the first strand cDNA preparation (try not to split these, or we will have to add more fields!). If more than one person was involved, just pick one. See [general specifications](../GeneralSpecs.md) for format details.

## s1cDNASampleNumber

**[REQUIRED]** Sequential positive integers uniquely identifying the single-stranded cDNA or cDNA-RNA hybrid samples prepared by a given preparer on a given date.

## polyAIsolationProtocol

**[REQUIRED]** Entries, to be defined, indicating the kit or protocol used for isolating polyA+ rna from total RNA or for depleting unwanted RNAs such as ribosomal RNAs. Should be a single string of letters with no whitespace. Add any entries used below, with an explanation.

- E7490L -- NEBNext Poly(A) mRNA Magnetic Isolation Module, thermo catalog number E7490
- catcher -- mRNA Catcher Plus
- None -- if no polyA isolation was performed, as in BRBSeq

## s1cDNAProtocol

**[REQUIRED]** Entries, to be defined, indicating the kit or protocol used for generating the first strand. Should be a single string of letters with no whitespace. Add any entries used below, with an explanation.

- SuperScriptIII
- E7420L -  NEBNext Ultra Directional RNA Library Prep Kit for Illumina
- If a concentration other than typical is used, list it as such: E7420L_0.5X

## roboticS1Prep

**[REQUIRED]** Boolean. Make sure formatting of True/False value is appropriate for the program you are using

## s1PrimerSeq

**[REQUIRED]** The sequence (all caps) of the primer if an indexed primer is being used, or “random” if random primers are used.
