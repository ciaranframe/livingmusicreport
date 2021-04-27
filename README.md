# Living Music Report
### :musical_note: The open dataset for the Living Music Report

Welcome to the open dataset for the Living Music Report. Fact-checking, investigation and re-use of the data found within is all welcome!

This dataset is made available under the [Open Database License](http://opendatacommons.org/licenses/odbl/1.0/). Any rights in individual contents of the database are licensed under the [Database Contents License](http://opendatacommons.org/licenses/dbcl/1.0/).


## Repository format
* LMR
	* `MPAsummary.csv` (what MPAs contained in datase)
	* SSO (subfolders for every MPA)
		* `SSO2019summary.csv` (season summary)
		* SSO2019 (season subfolder)
			* `SSO2019001.csv` (individual series)
			* `SSO2019002.csv`
			* ...
	* ...


## Top folder (LMR)

#### Master List
A simple master list of MPAs in the report (`MPAsummary.txt`)

| Attribute     | Pos.   |Format|Description |
|:------------- |:------:| :-----:|:-------------|
|`MPAinit` | 1 | A | The initialism for the MPA, used as the general reference in this datas et for any mention of the MPA |
|`MPAname` | 2 | A | The full name of the MPA |

#### A subfolder for each MPA

Named `MPAInit`  (e.g. SSO)


## MPA subfolder 

Contains the following folders and files:

#### MPA season summary file
Summarises all _series_ performed by the MPA in a given year. Note that this is the concert series, not the performance (i.e. the series may have been performed more than one time, noted in `SeriesPerfs`).

Named `MPAInit` + YYYY + summary.csv (e.g. `MSO2019summary.csv`)

| Attribute     | Pos.   |Format|Description | Example|
|:------------- |:------:| :-----:|:-------------|:--------|
|`SeriesId` | 1 | AN | Unique arbitrary identifier of a concert series | ACO2019004 |
|`SeriesName` | 2 | A | The full name of the series as per the program | Theres a Sea in My Bedroom |
|`SeriesDate` | 3 | ISO8601 | The month (or estimate) of the series, based on the date of the first performance, in the format YYYY-MM |  2019-05 |
|`SeriesPerfs` | 4 | N | The number of times the series was performed (if Digital, 1) |  15 |
|`SeriesVenue` | 5 | A | The location of the series (if multiple, "Various" is used; if online, "Digital" is used) | Sydney's Opera House's Utzon Room |
|`SeriesEd` | 6 | Binary | Was the series part of an education program? (Y/N) | Y |
|`SeriesInt` | 6 | Binary | Did the series have an interval? (Y/N) | N |

#### MPA season detail subfolder

Named `MPAInit` + YYYY (e.g. MSO2019)


## MPA season detail subfolder
Contains individual .csv files for each concert series outlined in the MPA season summary file.

Named after referenced `SeriesId` (e.g. `ACO2019004.csv`)

Individual series outline every work performed in the series as per the criteria in the report. Structured as follows:

| Attribute     | Pos.   |Format|Description | Example|
|:------------- |:------:| :-----:|:-------------|:--------|
|`CompName` | 1 | A | Full name of the composer | Peter Sculthorpe |
|`CompBirth` | 2 | YYYY | Year of birth of the composer | 1929 |
|`CompLiving` | 3 | Binary | Was the composer alive on 31 December the year of report? (Y/N) |  N |
|`CompNation` | 4 | A | The citizenship of the composer at time of composition |  Australian |
|`CompGender` | 5 | A | The gender of the composer out of list as per report definitions (Male=M/Female=F/Non-binary=NB/Gender diverse=X) | M |
|`CompCald` | 6 | Binary | Was/is the composer a CALD Australian as per report definitions? (Y/N) | N |
|`CompFn` | 7 | Binary | Was/is the composer First Nations as per report definitions? (Y/N) | N |
|`WorkTitle` | 8 | A | The title of the work performed | Djilile |
|`WorkLength` | 9 | N | The length of the work in minutes | 5 |
|`WorkYear` | 10 | N | The year the work was written | 1986 |
|`WorkAp` | 11 | Binary | Was the work an Australian Premiere? (Y/N) | N |
|`WorkWp` | 12 | Binary | Was the work a World Premiere? (Y/N) | N |
|`WorkInst` | 13 | A | Instrumentation of the work | Chamber orchestra |


