# survey-batch
Import survey data to DB and generate report and sent report via email
Flow
=========================================
![alt tag](https://raw.githubusercontent.com/le-tri-mulodo/survey-batch/master/Survey.jpg)
Set up, build & run
=========================================
**survey-batch** use `Spring Batch` & `Maven` to minimize spend coding time.

## Setup
Open `config.properties` and config.
  + Config values for the datasource:
    + `ds.driver`: JDBC driver for datasource
    + `ds.url.survey`: URL of survey data schema
    + `ds.url.job_repo`: URL of job repository schema
    + `ds.username` & `ds.password`: User name & password to access datasource
  + Config values for the data folder: 
    + `zip_folder`: Folder contain all ZIP files send by fieldworkers
    + `csv_folder`: The temp folder contain CSV files decompressed and use data in them to import into DB
    + `backup_folder`: Contain ZIP files backuped by date
  + Config values for mail:
    + `email.host`: Host of mail service
    + `email.port`: Port of mail service
    + `email.username` & `email.password`: User name & password to access mail service

## Initialize DB
  + Create schemas for store survey data and job repository
  + Execute `survey_create.sql` script to create tables need to run program

## Build
To build, execute from the top level directory:

  `$ mvn clean install`
## Run

  `$ java -Djava.awt.headless=true -jar target/survey.jar`
