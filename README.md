# otl-metromerger
Simulate the merger of smaller polygon areas into larger regions, with Leaflet thematic hover map

## Link
https://ontheline.github.io/otl-metromerger/index.html

## TO DO: Embed in book
https://ontheline.trincoll.edu

## Data
CT Open Data, Municipal Fiscal Indicators 2021 https://data.ct.gov/Local-Government/Municipal-Fiscal-Indicators-Economic-and-Grand-Lis/jrwx-mxhm/about_data
  - Town
  - Population
  - Income per capita
  - Equalized Net Grand List (ENGL) as "taxable property"

### For annual updates
1. Locate the appropriate dataset on Socrata (https://data.ct.gov/)
1. Identify the dataset's API endpoint by clicking `Export` > `API Endpoint`
1. Identify appropriate column names for town name (`town` in 2021), population (`july_1_2021_population` in 2021), per capita income (`per_capita_income_calendar` in 2021), and equalized net grand list (`equalized_net_grand_list_fye_2021` in 2021)
1. Modify `index.html` (see lines 299-308) with all these details
1. Just in case, consider making a backup copy of the JSON file returned by Socrata so you can always switch to a local version. For 2021 data (as of March 2024), the URL is https://data.ct.gov/resource/jrwx-mxhm.json?$select=town,july_1_2021_population,per_capita_income_calendar,equalized_net_grand_list_fye_2021 and the data is saved to `data/data.20240302.backup.json`. It is printed in the Console (see index.html, line 311). Alternate code line 311 would be:
```
$.getJSON('.data/data/20240302.backup.json', function (apiData) {
```

## Credits
- @ilyankou Ilya Ilyankou for redesigning code to pull data directly from Socrata, 2024
- @kitzj Joe Kitz for redesigning code and interface, 2024
- @erose Eli Rose for assisting with JavaScript logic, 2015
- @nav10003 Natalia Vorotyntseva at UConn MAGIC (http://magic.lib.uconn.edu) for code to toggle on/off polygons, display results for multiple regions, and export results
- @alvinschang Alvin Chang for creating functions to display info window data, based on examples such as http://projects.ctmirror.org/content/2014/05/raceSchools/
