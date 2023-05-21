# Data-Management-of-Bristol-Air-Quality
The air quality management area in Bristol has been declared as poor due to exceedance of Nitrogen Dioxide annual and hourly objectives and as a precautionary measure, exceedance of objectives for particulate matter (PM10).
This project uses both relational and non relational databases in the analysis and management of Bristol air quality.


# PROJECT BRIEF
# Context: Measuring Air Quality

Levels of various air borne pollutants such as Nitrogen Monoxide (NO), Nitrogen Dioxide (NO ) and particulate matter (also called particle pollution) are all major contributors to the measure of overall air quality.
For instance, NO is measured using micrograms in each cubic metre of air (㎍/m ). A microgram (㎍) is one millionth of a gram. A concentration of 1 ㎍/m means that one cubic metre of air contains one microgram of pollutant.

To protect our health, the UK Government sets two air quality objectives for NO in their Air Quality Strategy
1. The hourly objective, which is the concentration of NO in the air, averaged over a period of one hour.
2. The annual objective, which is the concentration of NO in the air, averaged over a period of a year.
The following table shows the colour encoding and the levels for Objective 1 above, the mean hourly ratio,
adopted in the UK.

![image](https://github.com/PillarBox-hub/Data-Management-of-Bristol-Air-Quality/assets/110098621/5e3ac520-0f8b-4d1d-9ae9-b08fd17e64f8)

Further details of colour encodings and health warnings can be found at the DEFRA Site.


# The Input Data(Overview and Description)

The ZIP file "bristol-air-quality-data"  provides data ranging from 2004 to 05 October 2022 taken from 19 monitoring stations in
and around Bristol.
The snippet below shows the header of 8 lines of the data cropped:

![image](https://github.com/PillarBox-hub/Data-Management-of-Bristol-Air-Quality/assets/110098621/01b6541d-d7c9-4957-b5e2-96ca1b381167)


Each line represents one reading from a specific detector. Detectors take one reading every hour. If you examine the file using a programming editor, (Notepad++ can handle the job), you can see that the first row gives headers and there are another 1520995 (1.52 million+) rows (lines). There are 23 data items (columns) per line.


# Below is the list of the 19 stations: 

188 => 'AURN Bristol Centre',
203 => 'Brislington Depot',
206 => 'Rupert Street',
209 => 'IKEA M32',
213 => 'Old Market',
215 => 'Parson Street School',
228 => 'Temple Meads Station',
270 => 'Wells Road',
271 => 'Trailer Portway P&R',
375 => 'Newfoundland Road Police Station',
395 => "Shiner's Garage",
452 => 'AURN St Pauls',
447 => 'Bath Road',
459 => 'Cheltenham Road \ Station Road',
463 => 'Fishponds Road',
481 => 'CREATE Centre Roof',
500 => 'Temple Way',
501 => 'Colston Avenue'
672 => 'Marlborough Street'





# Below is the Schema table:

| measure       | Description | unit            |
| ------------- | ------------- | -------------- |              
| Date Time      | Date and time of measurement|datetime |  
| NOx       | Concentration of oxides of nitrogen  |㎍/m  |
| NO2      | Concentration of nitrogen dioxide  |㎍/m |
| NO    | Concentration of nitric oxide | ㎍/m
| SiteID    | SiteID for the Station| Integer |
| PM10 | Concentration of particulate matter <10 micron diameter | ㎍/m  |
|NVPM10| Concentration of non - volatile particulate matter <10 micron diameter  |㎍/m |
|VPM10| Concentration of volatile particulate matter <10 micron diameter        |㎍/m |
|NVPM2.5| Concentration of non volatile particulate matter <2.5 micron diameter        |㎍/m |
|PM2.5| Concentration of particulate matter <2.5 micron diameter         | ㎍/m|
|VPM2.5|   Concentration of volatile particulate matter <2.5 micron diameter      |㎍/m |
|CO| Concentration of carbon monoxide     |mg/m |
|O3|   Concentration of ozone           |㎍/m |
|  SO2         | Concentration of sulphur dioxide                |㎍/m  |
|  Temperature         | Air temperature                                     | °C |
| RH           |   Relative Humidity                                   | % |
|  Air Pressure      |   Air Pressure                             | mbar   | 
|  Location      | Text description of location                    |   text |
| geo_point_2d       |   Latitude and longitude                    |  geo point   |
| DateStart       | The date monitoring started              | datetime   |
|  DateEnd      | The date monitoring ended                      | datetime   |
| Current       |  Is the monitor currently operating            | text    |
| Instrument       | Type Classification of the instrument       | text    |



# Code Description (Submission flies)

The zip file 21046899-dmf-assign-21.zip contains the following files with brief description of the task each one does. 

1. **CROP.py**  A python script that crops the file(bristol-ar-quality-data) to delete any records before 00:00 1 Jan 2010. This script makes use of in-built python functions as well as external libraries like pandas. 
2. **CLEAN.py** A python script that uses pandas and in-built functions helps filter for and remove any dud records where there is no value for SiteID or there is a mismatch between SiteID and Location. The script also prints to the console the line number and mismatch field values for each dud record. 
3. **Pollution.png**  The ER-diagram created from the use of MySQL Workbench to create a ER model in the third-normal form to hold the given data. 
4. **pollution.sql**  The Use of the forward engineer feature of MySQL Workbench to generate the SQL schema and implement the database (*pollution-db*).
5. **populate.py** A python script that uses pandas,sqlalchemy and in-built functions that takes the cleaned CSV file as input and creates a
new database instance (*pollution-db2*) and populates it. 
6. **insert-100.py** A python script that generates an SQL file (insert-100.sql) that holds the first 100 inserts to the main data table. 
7. **query-a.sql**  An SQL query statement that returns the date/time, station name and the highest recorded value of nitrogen oxide (NOx) found in the
dataset for the year 2019 from *polltion-db*. 
8. **query-b.sql** An SQL query statement that returns the mean values of PM2.5 (particulate matter <2.5 micron diameter) & VPM2.5 (volatile particulate
matter <2.5 micron diameter) by each station for the year 2019 for readings taken on or near 08:00 hours (peak traffic intensity) from *polltion-db*.
9. **query-c.sql** An SQL Query statement that extends the previous query to show these values for all stations in the years 2010 to 2019 from *polltion-db*.
10. **nosql.md** A markdown report detailing the modelling, implementation and querying of a NoSql database specifically *mongo-db*. 
11. **report.md** A short report in Markdown format (<1000 words) reflecting on the project, the problems encountered and the solutions found.


 
