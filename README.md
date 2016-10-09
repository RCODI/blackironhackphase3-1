README
======

Travel Risk Evaluation
----------------------

[REDACTED]

Keywords
--------
* travel
* relative risk
* vector-borne zoonotic disease

Datasets
--------
* NOAA Climate Normals Monthly
    - http://www.ncdc.noaa.gov/cdo-web/api/v2/
    - JSON data
    - Normal annual precipitation, temperature, and growing degree day information is used to assess the suitability of the climate for mosquitoes
    - Data is available for the entire US

* Zika Cases Reported in the United States
    - http://www.cdc.gov/zika/intheus/maps-zika-us.html 
    - Table data
    - The number of cases for the corresponding state is used
    - Data is available for the entire US

* 2015 American Community Survey Subject Tables
    - http://api.census.gov/data/2015/acs1
    - JSON data
    - The population of the corresponding county or state is used
    - Data is available for the entire US

* Compressed Mortality File 1999-2014 on CDC WONDER Online Database
    - http://wonder.cdc.gov/cmf-icd10.html
    - Table data
    - Annual deaths per 1,000,000 in the USA by several causes is used
    - Data is available for the entire US

* Y The primary dataset "online climate data" from data.gov is used

* Y All datasets used are from the US government

Description
-----------
This website provides travelers with information and context about the risk of contracting Zika virus and other mosquito-borne diseases while traveling within the United States.
The user provides their destination and date of travel.
The website shows the destination on a map and estimates the disease risk on that date.

* Map View
    1. Y The map is centered on the travel destination
    2. Y The map has a marker for the travel destination
    3. y The map will have a label for the travel destination
    4. y The map will have an InfoWindow
    5. y The map will have visual indicators of heat, precipitation, and population density

* Data Visualization
    1. Y The page uses a color-coded table to show risk components and a Plot.ly graph to show risk of Zika virus in context of other risks
    2. N The chart has hover but no click interaction

* Interaction Form
    1. Y Information about climate, mosquito activity, and cases of Zika in the state is output
    2. y The user will be able to change the date and destination of travel to see how risk is changed
    3. Y The user inputs their date of travel and destination
    4. Y If the user changes the date and destination of travel, the map is updated based on the location
    5. y If the user changes the date and destination of travel, the charts are be updated based on the risk

Build Case
----------
* Dependencies
    - python
    - gunicorn
    - flask
    - flask-cors
    - numpy
    - beautifulsoup4

* Building

    sudo apt-get install python python-flask python-pip

    sudo pip install -r requirements.txt

* Usage
    1. Start the flask server with `python server.py`
    2. Open Google Chrome and go to 127.0.0.1:5000
    3. Enter data into the form and click 'Submit'

Testing
-------
This website was tested on Ubuntu 14.04 using Google Chrome version 53.0.2785.116

Additional Information
----------------------
In the description section, items marked with an uppercase Y are functional while items marked with a lowercase y have not been implemented.

The URL provided for climate data online was not detailed enough to easily find the REST API. This is largely due to poor design of the NOAA website. I did not know the REST API existed until I saw it in another participant's README.
