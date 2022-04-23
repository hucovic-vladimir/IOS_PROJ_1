# corona
A shell script for applying various filters on CSV files containing records of COVID infections

## Usage

./corona [SWITCH] [COMMAND] [FILE1 [FILE2]...] 

If no input file is specified, the script takes input from STDIN

### [SWITCH] can be a combination of the following:
-h : displays usage information (in Czech) 

-a DATETIME: Only records with date AFTER (and including) DATETIME will appear in the output. DATETIME must be a valid date in this format: YYYY-MM-DD 

-b DATETIME: Only records with date BEFORE (and including) DATETIME will appear in the output. DATETIME must be a valid date in this format: YYYY-MM-DD 

-g GENDER: Only records of people of a gender specified by GENDER will appear in the output (M = MALE, Z = FEMALE) 

-d DISTRICT_FILE: Replaces the code of the district in the output with its name. Code-Name mapping is specified in the DISTRICT_FILE. 

-r REGIONS_FILE: Replaces the code of the region in the output with its name. Code-Name mapping is specified in the REGIONS_FILE. 

-s [WIDTH]: With commands gender, age, daily, monthly, yearly, countries, districts and regions, it transforms numeric outputs to a graphical format. 

If WIDTH is specified, the row with the most records will have a width of WIDTH. If WIDTH is not set, each # sign has an implicit value according to the 
following table: 

    gender   : 100 000 
    age      : 10 000 
    daily    : 500 
    monthly  : 10 000 
    yearly   : 100 000 
    countries: 100 
    districts: 1 000 
    regions  : 10 000 

### [COMMAND] can be one of the following:
infected : Counts the number of infections 

merge    : Merges multiple record files into once. This is the implicit command. 

gender   : Outputs the number of records grouped by gender. 

age      : Outputs the number of records grouped by age group. 

daily    : Outputs the infection statistic for each day. 

monthly  : Outputs the infection statistic for each month. 

yearly   : Outputs the infection statistic for each year. 

countries: Outputs the infection statistic for each country. 

districts: Outputs the infection statistic for each district. 

regions  : Outputs the infection statistic for each region. 
