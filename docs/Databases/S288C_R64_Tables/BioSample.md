# BioSample

The primary key for this table is bioSampleNumber

- If multiple aliquots of cells are taken at the same time from the same culture (e.g. tube or colony on an agarose plate) then they are aliquots of a single biosample, so only one entry is needed in the biosample table.  

- If you are entering data, or using data, from this table, and you notice a column that is poorly defined in any way (eg, it is never used, should have defined choices and does not, etc), then post an issues report on the appropriate github repository.

Name                                 | Type                 | Required  
:------------------------------------|:--------------------:|:---------:
bioSampleNumber                      | int                  | Yes (Primary Key)
harvestDate                          | datetime             | Yes
harvester                            | string               | Yes
experimentDesign                     | string               | Yes
experimentObservations               | string               | Yes
bioSampleObservations                | string               | No
baseStrain                           | string               | Yes
strain                               | string               | Yes
genotype1                            | string               | Yes
perturbation1                        | string               | Yes
marker1                              | string               | Yes, if applicable
genotype2                            | string               | Yes, if applicable
perturbation2                        | string               | Yes, if applicable
marker2                              | string               | Yes, if applicable
medium                               | string               | Yes
temperature                          | float                | Yes
atmosphere                           | string               | Yes
treatment                            | string               | Yes
treatmentConc                        | float                | Yes
treatmentConcUnit                    | string               | Yes
otherConditions                      | string               | Yes
pH                                   | float                | Yes
timePoint                            | float                | Yes
floodmedia                           | string               | Yes
inductionDelay                       | string               | Yes

* * *
**[KEY]** and **[REQUIRED]** columns should be included in every sheet. **[OPTIONAL]** columns must be included when there are samples which would have non-empty entries in those columns.

## bioSampleNumber

**[KEY]** Sequential positive integers uniquely identifying the samples taken by a given harvester on a given date. Numbers can be reused as long as the harvester and date are different.

## harvestDate

**[REQUIRED]** The date (e.g. 05.17.20) on which the cells were taken out of culture and growth was stopped. See [general specifications](https://github.com/BrentLab/database_files/wiki) for format details.

## harvester

**[REQUIRED]** Name of the person (e.g. J.PLAGGENBERG)  who was in charge of the experiment. If more than one person was involved, just pick one. See [general specifications](https://github.com/BrentLab/database_files/wiki) for format details.

## experimentDesign

**[REQUIRED]** This should be a short string with no spaces that refers to a design which is actually explained in some other document. E.g. ZEVNeg1_10_15_20_90_SCGal_plates. Do not use something that could be mistaken for a number, such as “20.20”. This doesn’t have to be so descriptive -- you could even use ZEV1, since it will be explained elsewhere. The other document should have the same name as the table entry. It should describe the experiment and list the relevant fields needed to keep all the treatments and samples separate. An example can be found here. 

## bioSampleObservations

**[OPTIONAL]** This is a free text entry field meant to record anything about this sample, specifically pertaining to this table's data, that does not fit into other fields. This __should not be used for storing any information pertinent to experimental design__.

## baseStrain

**[REQUIRED]** The parent strain from which a given strain is made

## strain

**[REQUIRED]** The actual collection of cells used to inoculate. Usually corresponds to a tube or well in the freezer. There can be multiple strains of a given genotype -- typically when multiple independent mutants are made. But also each time a new batch of the wild type laboratory strain is grown or obtained from a source it should be given a new strain number. Format should conform to literature standard and be consistent (e.g. ZEV is always ZEV and not sometimes ZeV).

## genotype\#

**[REQUIRED]** Eg CNAG_00000. There must be at least the column genotype1, and may be more. The genotype used should be defined in the experimental design doc. This must conform to a standard and be consistent. If there is a double knockout, then there will be 4 genotype related columns: genotype1, perturbation1, genotype2, perturbation2

## perturbation\#

**[REQUIRED]** The perturbation class related to the corresponding genotype (eg perturbation1 describes genotype1. If there is a genotype2, then perturbation2 corresponds to it). Currently, acceptable entires are [None, deletion, over, geneSwap] where None is simply an **empty cell**. This is what should be done for wildtype samples.

## marker\#

**[REQUIRED IF PRESENT]** Currently accepted entries are either NAT or G418. NOTE: DO NOT ADD CNAG\_ . A column to record the resistance cassette (colloquially, "drug marker"). If there are no markers, do not add this column. If in the bioSample sheet, there are only single perturbation, then only marker_1 should be added. If there is at least one double pertubation, then add both marker_1 and marker_2.

## medium

**[REQUIRED]** Current acceptable entries are DMEM, YPD, RPMI, PBS, mouseSerum

## temperature

**[REQUIRED]** A integer or decimal value (eg 37 or 37.5), on the Celsius scale

## atmosphere

**[OPTIONAL]** Current acceptable entries are ambient, CO2

## floodmedia

**[OPTIONAL]** String, no whitespace and consistent. Current options are. If more are needed, they must be added here and published/publicized before use:
        - SCGal
        - SCGlu

## treatment

**[OPTIONAL]** Currently, cAMP is the only known acceptable entry. PLEASE ASK prior to entering anything in this column -- it needs to be better determined. This is especially true for yeast

## otherConditions

**[OPTIONAL]** This is where items that are uncommon across samples should be entered. Currently, pH is included in this column. Once again, it is better to discuss prior to entering a value rather than entering a value that may be inconsistently applied due to lack of documentation.

## timePoint

**[OPTIONAL]** A decimal number in minutes (if whole minutes, there is no need to add the decimal point).
The time between the treatment and the sample collection. Use -1 (neg1 as an integer) for samples collected immediately before the treatment is applied.

## inductionDelay

**[OPTIONAL]** For ZEV experiments, the time between resuspending the cells and adding the inducer or mock inducer. A decimal number in minutes (if whole minutes, there is no need to add the decimal point).
