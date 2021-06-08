# API Reference
Our public data API provides access to all of our data at a national and state level. We provide data in both JSON and CSV format. You can also download CSV data directly.

Version 2 of our API is available.

You can view our current uptime and any known issues on our status page.
Our data is provided under our project-wide data license.
Fields may over time be marked as deprecated. These fields may remain static or change to null values after a period of two weeks.
New fields may be added without warning, but will not alter the structure of the data. If you are using CSV files, make sure to use the column names from the file to lookup data, not the column numbers, which can change.
All URLs in our API, including state codes, should be in lower-case.
We do not support cross-domain requests using CORS.
## API domain name
All API requests should be made to: https://api.covidtracking.com  


## Current US values ↑
The most recent COVID data for the US. The most recent data may not be from today.

View data sourcefor Current US values

### JSON format
/v1/us/current.json

**Example**: https://api.covidtracking.com/v1/us/current.json

### CSV format
/v1/us/current.csv

**Example**: https://api.covidtracking.com/v1/us/current.csv  

### The demo video
The feature track with the changes required for embedded postman was deployed on beta for a short period of time. And the changes will be reverted or changed as per the requirements of the postman app development. This may lead to the embedded postman content not render.

Adding the demo video snippet for reference of the PoC implementation.  
[![Embedded Postman(assets/alt_image.png)](https://drive.google.com/file/d/1syFEBCdaLlVkWQ-u6GtgbMCw8opS66AK/view)]


### Fiddle  

{% include preview.html %}  

#### date
Field type:integer
Date

Date on which data was collected by The COVID Tracking Project.

#### dateChecked
Field type:string
Deprecated. This is an old label for lastUpdateEt.

#### death
Field type:integer
Deaths (confirmed and probable)

Total fatalities with confirmed OR probable COVID-19 case diagnosis (per the expanded CSTE case definition of April 5th, 2020 approved by the CDC). In some states, these individuals must also have COVID-19 listed on the death certificate to count as a COVID-19 death. When states post multiple numbers for fatalities, the metric includes only deaths with COVID-19 listed on the death certificate, unless deaths among cases is a more reliable metric in the state.

Returns
null
if no data is available
#### deathIncrease
Field type:integer
New deaths

Daily increase in death, calculated from the previous day’s value.

Returns
null
if no data is available
#### hash
Field type:string
A hash for this record

#### hospitalized
Field type:integer
Deprecated. Old label for hospitalizedCumulative.

Returns
null
if no data is available
#### hospitalizedCumulative
Field type:integer
Cumulative hospitalized/Ever hospitalized

Total number of individuals who have ever been hospitalized with COVID-19. Definitions vary by state / territory, and it is not always clear whether pediatric patients are included in this metric. Where possible, we report patients hospitalized with confirmed or suspected COVID-19 cases.

Returns
null
if no data is available
#### hospitalizedCurrently
Field type:integer
Currently hospitalized/Now hospitalized

Individuals who are currently hospitalized with COVID-19. Definitions vary by state / territory, and it is not always clear whether pediatric patients are included in this metric. Where possible, we report patients hospitalized with confirmed or suspected COVID-19 cases.

Returns
null
if no data is available
#### hospitalizedIncrease
Field type:integer
New total hospitalizations

Daily increase in hospitalizedCumulative, calculated from the previous day’s value.

Returns
null
if no data is available
#### inIcuCumulative
Field type:integer
Cumulative in ICU/Ever in ICU

Total number of individuals who have ever been hospitalized in the Intensive Care Unit with COVID-19. Definitions vary by state / territory, and it is not always clear whether pediatric patients are included in this metric. Where possible, we report patients in the ICU with confirmed or suspected COVID-19 cases.

Returns
null
if no data is available
#### inIcuCurrently
Field type:integer
Currently in ICU/Now in ICU

Individuals who are currently hospitalized in the Intensive Care Unit with COVID-19. Definitions vary by state / territory, and it is not always clear whether pediatric patients are included in this metric. Where possible, we report patients in the ICU with confirmed or suspected COVID-19 cases.

Returns
null
if no data is available
#### lastModified
Field type:string
Deprecated. Old label for lastUpdateET.

#### negative
Field type:integer
Negative PCR tests (people)

Total number of unique people with a completed PCR test that returns negative. For states / territories that do not report this number directly, we compute it using one of several methods, depending on which data points the state provides. Due to complex reporting procedures, this number might be mixing units and therefore, at best, it should only be considered an estimate of the number of people with a completed PCR test that return negative.

Returns
null
if no data is available
#### negativeIncrease
Field type:integer
Increase in negative computed by subtracting the value of negative for the previous day from the value for negative from the current day.

Returns
null
if no data is available
#### onVentilatorCumulative
Field type:integer
Cumulative on ventilator/Ever on ventilator

Total number of individuals who have ever been hospitalized under advanced ventilation with COVID-19. Definitions vary by state / territory, and it is not always clear whether pediatric patients are included in this metric. Where possible, we report patients on ventilation with confirmed or suspected COVID-19 cases.

Returns
null
if no data is available
#### onVentilatorCurrently
Field type:integer
Currently on ventilator/Now on ventilator

Individuals who are currently hospitalized under advanced ventilation with COVID-19. Definitions vary by state / territory, and it is not always clear whether pediatric patients are included in this metric. Where possible, we report patients on ventilation with confirmed or suspected COVID-19 cases.

Returns
null
if no data is available
#### pending
Field type:integer
Pending

Total number of viral tests that have not been completed as reported by the state or territory.

Returns
null
if no data is available
#### posNeg
Field type:integer
Deprecated. Computed by adding positive and negative values.

Returns
null
if no data is available
#### positive
Field type:integer
Cases (confirmed plus probable)

Total number of confirmed plus probable cases of COVID-19 reported by the state or territory, ideally per the August 5, 2020 CSTE case definition. Some states are following the older April 5th, 2020 CSTE case definition or using their own custom definitions. Not all states and territories report probable cases. If a state is not reporting probable cases, this field will just represent confirmed cases.

Returns
null
if no data is available
#### positiveIncrease
Field type:integer
New cases

The daily increase in API field positive, which measures Cases (confirmed plus probable) calculated based on the previous day’s value.

Returns
null
if no data is available
#### recovered
Field type:integer
Recovered

Total number of people that are identified as recovered from COVID-19. States provide very disparate definitions on what constitutes a “recovered” COVID-19 case. Types of “recovered” cases include those who are discharged from hospitals, released from isolation after meeting CDC guidance on symptoms cessation, or those who have not been identified as fatalities after a number of days (30 or more) post disease onset. Specifics vary for each state or territory.

Returns
null
if no data is available
#### states
Field type:integer
States

Only available in national records. The number of states and territories included in the US dataset for this day.

#### total
Field type:integer
Deprecated. Computed by adding positive, negative, and pending values.

Returns
null
if no data is available
#### totalTestResults
Field type:integer
Total test results

At the national level, this metric is a summary statistic which, because of the variation in test reporting methods, is at best an estimate of US viral (PCR) testing. Some states/territories report tests in units of test encounters, some report tests in units of specimens, and some report tests in units of unique people. Moreover, some jurisdictions include antigen tests in their total test counts without reporting a separate total of viral (PCR) tests. Therefore, this value is an aggregate calculation of heterogeneous figures. Please consult each state or territory’s individual data page to see whether that jurisdiction lumps antigen and PCR tests together and to see what units that jurisdiction uses for test reporting.

In most states, the totalTestResults field is currently computed by adding positive and negative values because, historically, some states do not report totals, and to work around different reporting cadences for cases and tests. In Colorado, Delaware, the District of Columbia, Florida, Hawaii, Minnesota, Nevada, New York, North Dakota, Pennsylvania, Rhode Island, Virginia, Washington, and Wisconsin, where reliable testing encounters figures are available with a complete time series, we directly report those figures in this field. In Alaska, America Samoa, Arizona, Arkansas, California, Connecticut, Georgia, Illinois, Indiana, Kentucky, Maine, Maryland, Massachusetts, Michigan, Missouri, Montana, Nebraska, New Hampshire, New Mexico, North Carolina, Ohio, Oregon, South Dakota, Tennessee, Texas, Utah, Vermont, West Virginia, and Wyoming, where reliable specimens figures are available with a complete time series, we directly report those figures in this field. In Alabama and Idaho where reliable unique people figures are available with a complete time series, we directly report those figures in this field. We are in the process of switching all states over to use directly reported total figures, using a policy of preferring testing encounters, specimens, and people, in that order.

Returns
null
if no data is available
#### totalTestResultsIncrease
Field type:integer
New tests

Daily increase in totalTestResults, calculated from the previous day’s value. This calculation includes all the caveats associated with Total tests/totalTestResults, and we recommend against using it at the state/territory level.

Returns
null
if no data is available

## US Current and Historical Data

Historic US values ↑
All COVID data for the US.

View data sourcefor Historic US values

### JSON format
/v1/us/daily.json

**Example**: https://api.covidtracking.com/v1/us/daily.json

### CSV format
/v1/us/daily.csv

**Example**: https://api.covidtracking.com/v1/us/daily.csv

### Fields
#### date
**Field type**:integer
Date

Date on which data was collected by The COVID Tracking Project.

#### dateChecked
**Field type**:string
Deprecated. This is an old label for lastUpdateEt.

#### death
Field type:integer
Deaths (confirmed and probable)

Total fatalities with confirmed OR probable COVID-19 case diagnosis (per the expanded CSTE case definition of April 5th, 2020 approved by the CDC). In some states, these individuals must also have COVID-19 listed on the death certificate to count as a COVID-19 death. When states post multiple numbers for fatalities, the metric includes only deaths with COVID-19 listed on the death certificate, unless deaths among cases is a more reliable metric in the state.

Returns
null
if no data is available
#### deathIncrease
Field type:integer
New deaths

Daily increase in death, calculated from the previous day’s value.

Returns
null
if no data is available
#### hash
Field type:string
A hash for this record

#### hospitalized
Field type:integer
Deprecated. Old label for hospitalizedCumulative.

Returns
null
if no data is available
#### hospitalizedCumulative
Field type:integer
Cumulative hospitalized/Ever hospitalized

Total number of individuals who have ever been hospitalized with COVID-19. Definitions vary by state / territory, and it is not always clear whether pediatric patients are included in this metric. Where possible, we report patients hospitalized with confirmed or suspected COVID-19 cases.

Returns
null
if no data is available
#### hospitalizedCurrently
Field type:integer
Currently hospitalized/Now hospitalized

Individuals who are currently hospitalized with COVID-19. Definitions vary by state / territory, and it is not always clear whether pediatric patients are included in this metric. Where possible, we report patients hospitalized with confirmed or suspected COVID-19 cases.

Returns
null
if no data is available
#### hospitalizedIncrease
Field type:integer
New total hospitalizations

Daily increase in hospitalizedCumulative, calculated from the previous day’s value.

Returns
null
if no data is available
#### inIcuCumulative
Field type:integer
Cumulative in ICU/Ever in ICU

Total number of individuals who have ever been hospitalized in the Intensive Care Unit with COVID-19. Definitions vary by state / territory, and it is not always clear whether pediatric patients are included in this metric. Where possible, we report patients in the ICU with confirmed or suspected COVID-19 cases.

Returns
null
if no data is available
#### inIcuCurrently
Field type:integer
Currently in ICU/Now in ICU

Individuals who are currently hospitalized in the Intensive Care Unit with COVID-19. Definitions vary by state / territory, and it is not always clear whether pediatric patients are included in this metric. Where possible, we report patients in the ICU with confirmed or suspected COVID-19 cases.

Returns
null
if no data is available
#### lastModified
Field type:string
Deprecated. Old label for lastUpdateET.

#### negative
Field type:integer
Negative PCR tests (people)

Total number of unique people with a completed PCR test that returns negative. For states / territories that do not report this number directly, we compute it using one of several methods, depending on which data points the state provides. Due to complex reporting procedures, this number might be mixing units and therefore, at best, it should only be considered an estimate of the number of people with a completed PCR test that return negative.

Returns
null
if no data is available
#### negativeIncrease
Field type:integer
Increase in negative computed by subtracting the value of negative for the previous day from the value for negative from the current day.

Returns
null
if no data is available
#### onVentilatorCumulative
Field type:integer
Cumulative on ventilator/Ever on ventilator

Total number of individuals who have ever been hospitalized under advanced ventilation with COVID-19. Definitions vary by state / territory, and it is not always clear whether pediatric patients are included in this metric. Where possible, we report patients on ventilation with confirmed or suspected COVID-19 cases.

Returns
null
if no data is available
#### onVentilatorCurrently
Field type:integer
Currently on ventilator/Now on ventilator

Individuals who are currently hospitalized under advanced ventilation with COVID-19. Definitions vary by state / territory, and it is not always clear whether pediatric patients are included in this metric. Where possible, we report patients on ventilation with confirmed or suspected COVID-19 cases.

Returns
null
if no data is available
#### pending
Field type:integer
Pending

Total number of viral tests that have not been completed as reported by the state or territory.

Returns
null
if no data is available
#### posNeg
Field type:integer
Deprecated. Computed by adding positive and negative values.

Returns
null
if no data is available
#### positive
Field type:integer
Cases (confirmed plus probable)

Total number of confirmed plus probable cases of COVID-19 reported by the state or territory, ideally per the August 5, 2020 CSTE case definition. Some states are following the older April 5th, 2020 CSTE case definition or using their own custom definitions. Not all states and territories report probable cases. If a state is not reporting probable cases, this field will just represent confirmed cases.

Returns
null
if no data is available
#### positiveIncrease
Field type:integer
New cases

The daily increase in API field positive, which measures Cases (confirmed plus probable) calculated based on the previous day’s value.

Returns
null
if no data is available
#### recovered
Field type:integer
Recovered

Total number of people that are identified as recovered from COVID-19. States provide very disparate definitions on what constitutes a “recovered” COVID-19 case. Types of “recovered” cases include those who are discharged from hospitals, released from isolation after meeting CDC guidance on symptoms cessation, or those who have not been identified as fatalities after a number of days (30 or more) post disease onset. Specifics vary for each state or territory.

Returns
null
if no data is available
#### states
Field type:integer
States

Only available in national records. The number of states and territories included in the US dataset for this day.

#### total
Field type:integer
Deprecated. Computed by adding positive, negative, and pending values.

Returns
null
if no data is available
#### totalTestResults
Field type:integer
Total test results

At the national level, this metric is a summary statistic which, because of the variation in test reporting methods, is at best an estimate of US viral (PCR) testing. Some states/territories report tests in units of test encounters, some report tests in units of specimens, and some report tests in units of unique people. Moreover, some jurisdictions include antigen tests in their total test counts without reporting a separate total of viral (PCR) tests. Therefore, this value is an aggregate calculation of heterogeneous figures. Please consult each state or territory’s individual data page to see whether that jurisdiction lumps antigen and PCR tests together and to see what units that jurisdiction uses for test reporting.

In most states, the totalTestResults field is currently computed by adding positive and negative values because, historically, some states do not report totals, and to work around different reporting cadences for cases and tests. In Colorado, Delaware, the District of Columbia, Florida, Hawaii, Minnesota, Nevada, New York, North Dakota, Pennsylvania, Rhode Island, Virginia, Washington, and Wisconsin, where reliable testing encounters figures are available with a complete time series, we directly report those figures in this field. In Alaska, America Samoa, Arizona, Arkansas, California, Connecticut, Georgia, Illinois, Indiana, Kentucky, Maine, Maryland, Massachusetts, Michigan, Missouri, Montana, Nebraska, New Hampshire, New Mexico, North Carolina, Ohio, Oregon, South Dakota, Tennessee, Texas, Utah, Vermont, West Virginia, and Wyoming, where reliable specimens figures are available with a complete time series, we directly report those figures in this field. In Alabama and Idaho where reliable unique people figures are available with a complete time series, we directly report those figures in this field. We are in the process of switching all states over to use directly reported total figures, using a policy of preferring testing encounters, specimens, and people, in that order.

Returns
null
if no data is available
#### totalTestResultsIncrease
Field type:integer
New tests

Daily increase in totalTestResults, calculated from the previous day’s value. This calculation includes all the caveats associated with Total tests/totalTestResults, and we recommend against using it at the state/territory level.

Returns
null
if no data is available
