# Data-Management-of-Bristol-Air-Quality
The air quality management area in Bristol has been declared due to exceedance of Nitrogen Dioxide annual and hourly objectives and as a precautionary measure, exceedance of objectives for particulate matter (PM10).
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
| Date Time      | Unique ID of loan Application |
| Gender        | Gender of Loan Applicant |
| Married       | Marital Status of the Applicant |
| Dependents    | Number of Children of Applicant |
| Education     | Education Status of the Applicant|
| Self_Employed | Employment status of the Applican|
|ApplicantIncome| Income earned by the Applicant   |
|CoapplicantIncome| Income of Coapplicant          |
|LoanAmount|   Amount of loan Applied for          |
|Loan_Amount_Term| Loan Repayment Duration         |
|Credit_History|   Applicants Credit History       |
|Property_Area|    Area of Applicants Property     |
|Loan_Status|   Status of loan applicant           |


