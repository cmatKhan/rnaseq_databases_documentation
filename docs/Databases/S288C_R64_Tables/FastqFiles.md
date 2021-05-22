# FastqFiles

Name                                          | Type     | Required
----------------------------------------------|:--------:|:-----------:
[librarySampleNumber](#librarySampleNumber)   | int      | Yes (Foreign Key)
[fastqFileNumber](#fastqFileNumber)           | int      | Yes (Primary Key)
[fastqObservations](#fastqObservations)       | string   | Yes
[runNumber](#runNumber)                       | string (in order to accommodate old runNumbers)   | Yes
[purpose](#purpose)                           | string   | Yes
[laneNumber](#laneNumber)                     | int      | Yes
[sequencerModel](#sequencerModel)             | string   | Yes
[flowcellType](#flowcellType)                 | string   | Yes
[tapestationConc](#tapestationConc)           | float    | Yes
[volumePooled](#volumePooled)                 | float    | Yes
[readsObtained](#readsObtained)               | large int   | Yes
[fastqFileName](#fastqFileName)               | string   | No

* * *

## librarySampleNumber

**[REQUIRED]** Foreign key to the [library table](./Library.md) [general specifications](https://github.com/BrentLab/database_files/wiki) for format details.

## fastqFileNumber

**[REQUIRED]** Primary key

## runNumber

**[REQUIRED]** The run number assigned by the sequencing core for the sequence run (not the spike-in run). This should be a positive integer

## laneNumber

**[REQUIRED]** The lane within the run. If run only contains one separate sample, enter 1. This should be a positive integer.

## sequencerModel

**[REQUIRED]**  

- MiSeq
- MiniSeq (all of our spike-ins are MiniSeq)
- NextSeq (all of our full runs are NextSeq)

## flowcellType

**[REQUIRED]**  

- V3
- Standard
- Nano
- MiniSeq (the only type of flow cell used during spike-ins)
- HighOutput (used for NextSeq when there are 400M read runs)
- MidOutput (used for NextSeq when there are 130M read runs)

## purpose

**[REQUIRED]**  

- Rebalancing
- spikein
- fullRNASeq
- fullgDNASeq
- fullChIPSeq
- ….

## tapestationConc

**[REQUIRED]** A decimal number indicating the nanomolar reading from the tapestation. 

## volumePooled

**[REQUIRED]** The volume that was put into the pool that became the lane. A decimal number.

## readsObtained

**[REQUIRED]** The number of reads obtained. A decimal number.

## manualAudit

**[REQUIRED]** Record of manual pass/fail. Entries are (0,1) only

## manualStatus

**[REQUIRED]** codes are as follows:

```text
  1: library_size (raw) less than 1 mil (retained as there are some that remain, added to other failures other than 2. see issue #12)
  2: unique_alignment (raw) less than 79% (retained as there are some that remain, added to other failures other than 2. see issue #12)
  4: failed_deletion (based on log2cpm FOW)
  8: marker_expression (old QA metric based)
 16: IQR failure (new as of 12/19/2020. previously mistakenly omitted)
 32: both markers expressed when they should not be (old QA metric based)
 64: over_expression fail (old QA metric based)
128: failed library
256: unexplained pattern of reads that don't match the other "good" replicates
512: manual confirmation of AUTO_AUDIT
1024: total_deduplicated_percent failure
```

## fastqFileName

**[OPTIONAL]** Generally, required. Optional in the event that a sample goes through other items in the fastqFiles fields, but is not sent to the sequencer. All file names must be named in the following format. There should be no exception to this without agreement and updates to the format itself -- the goal is to achieve a standardized fastq filename for all libraries moving forward.

Some care may need to be taken to ensure that the sequence facility follows our naming format.

The format as of 2/28/2019 is:

LabOwner_ arbitraryLibraryNumber_GTAC_index#_index1_index2_sequencer-stuff.fastq.gz

Example: BRENT_1_GTAC_1_AAGATTA_GTAACCA_S1_R1_001.fastq.gz

Within any given run, the index1 sequence must be unique. Please make sure that the indicies are in the correct order (i.e. index1 is unique to the run). To re-emphasize -- there should be no additional information in the filename and order matters.

There is a script in ./scripts that will extract the fastq filenames as a row from the email text which the sequencing center sends when a run is complete. From database_files, you can do this:

head ./scripts/extract_fastq_filename_as_column.py

To view instructions on how to use it. The purpose of the script is to avoid extra spaces or colons, which the sequencing center sometimes addes to the filenames