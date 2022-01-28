# PT-VI Measurement file format

## protobuf file format

*PT6* files are in fact [protocol buffers](https://developers.google.com/protocol-buffers/). It's message formats are defined in [measurementfileformat.proto](measurementfileformat.proto) which describes a generic way of storing celldata with corresponding cell variables and metadata like *DateTime* and *MeasurementInfo*.

## PT-IV file composition

Any *PT6* file could be either just a protobuf file, indicating a standard measurement, or a ZIP file containing a protobuf file and an additional *xlsx* file. *PT6* file readers thus need to check which case is relevant. When present, an included *xlsx* describes a non-standard measurement template according to which the inspection has been executed.

## File format variables

The protobuf schema describes *CellData* as a part of *CellVariable*s which are addressed with their corresponding *GroupID* and *VarID*s.

| groupID |	varID  |  name
| ------: | -----: | -------|
| 0	|	0			|	DATE
| 0	|	1			|	TIME
| 0	|	4			|	NOTES
| 0	|	5			|	SAMPLE_FREQUENCY
| 0	|	6			|	VACUUM_UNITS
| 0	|	7			|	PRODUCT_NUMBER
| 1	|	0			|	USER_NAME
| 2	|	0			|	FARM_ID
| 2	|	1			|	FARM_NAME
| 2	|	2			|	FARM_NUMBER
| 2	|	3			|	FARM_ADDRESS
| 2	|	4			|	FARM_ZIP_CODE
| 2	|	5			|	FARM_CITY
| 2	|	6			|	FARM_COUNTRY
| 2	|	7			|	FARM_PHONE
| 3	|	0			|	DEALER_NAME
| 3	|	1			|	DEALER_STREET_1
| 3	|	2			|	DEALER_STREET_2
| 3	|	3			|	DEALER_STREET_3
| 3	|	4			|	DEALER_CITY
| 3	|	5			|	DEALER_POSTAL_CODE
| 3	|	6			|	DEALER_TELEPHONE
| 3	|	7			|	DEALER_EMAIL
| 3	|	8			|	DEALER_WEBSITE
| 9	|	17		    |   PT_LIMP_MS
| 9	|	20		    |   PT_LIMP_PERC
| 9	|	65536 + 0   |   PT_1_DESC
| 9	|	65536 + 1   |   PT_1_UUID
| 9	|	65536 + 2   |   PT_1_A_MS
| 9	|	65536 + 3   |	PT_1_A_PERC
| 9	|	65536 + 4   |	PT_1_B_MS
| 9	|	65536 + 5   |	PT_1_B_PERC
| 9	|	65536 + 6   |	PT_1_AB_MS
| 9	|	65536 + 7   |	PT_1_AB_PERC
| 9	|	65536 + 8   |	PT_1_C_MS
| 9	|	65536 + 9   |	PT_1_C_PERC
| 9	|	65536 + 10	|	PT_1_D_MS
| 9	|	65536 + 11	|	PT_1_D_PERC
| 9	|	65536 + 12	|	PT_1_CD_MS
| 9	|	65536 + 13	|	PT_1_CD_PERC
| 9	|	65536 + 14	|	PT_1_PULSE_MS
| 9	|	65536 + 15	|	PT_1_MAX_PRESSURE
| 9	|	65536 + 16	|	PT_1_MEAN_VACUUM
| 9	|	65536 + 18	|	PT_1_DATA
| 9	|	65536 + 19	|	PT_1_PULSE_PM
| 9	|	131072 + 0	|	PT_2_DESC
| 9	|	131072 + 1	|	PT_2_UUID
| 9	|	131072 + 2	|	PT_2_A_MS
| 9	|	131072 + 3	|	PT_2_A_PERC
| 9	|	131072 + 4	|	PT_2_B_MS
| 9	|	131072 + 5	|	PT_2_B_PERC
| 9	|	131072 + 6	|	PT_2_AB_MS
| 9	|	131072 + 7	|	PT_2_AB_PERC
| 9	|	131072 + 8	|	PT_2_C_MS
| 9	|	131072 + 9	|	PT_2_C_PERC
| 9	|	131072 + 10 |	PT_2_D_MS
| 9	|	131072 + 11 |	PT_2_D_PERC
| 9	|	131072 + 12 |	PT_2_CD_MS
| 9	|	131072 + 13 |	PT_2_CD_PERC
| 9	|	131072 + 14 |	PT_2_PULSE_MS
| 9	|	131072 + 15 |	PT_2_MAX_PRESSURE
| 9	|	131072 + 16 |	PT_2_MEAN_VACUUM
| 9	|	131072 + 18 |	PT_2_DATA
| 9	|	131072 + 19 |	PT_2_PULSE_PM
