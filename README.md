# Coronavirus (Covid-19) Prevalence by US County

[View Notebook](https://github.com/OptumCS/coronav2/blob/master/coronav2.ipynb)

The New York Times released a data file with cumulative counts of coronavirus cases in the United States county level, over time.

This Jupyter Notebook combines that daily data with county level 2019 population estimates from the US Census Bureau and calculates the prevalence for each county.

The New York Times Data (and licensing) can be found here: [https://github.com/nytimes/covid-19-data](https://github.com/nytimes/covid-19-data)

The coronavirus data is automatically fetched directly by URL (i.e., no need to download the daily data by hand).

Population used is included in this repository as [`co-est2019-alldata_sd.csv`](https://github.com/OptumCS/coronav2/blob/master/co-est2019-alldata_sd.csv)

### Output Data Format
The data output format is as follows:

```
date,county,state_name,fips,cases,deaths,state,pop2010,2019,prev2019
2020-04-04,Montgomery,Maryland,24031.0,640,9,MD,971777,1050688,0.060912
...
```
where:

* date = reporting date
* county = US County
* state_name = Full state name
* fips = FIPS code (geographic area identifier)
* cases = number of cases (cummulative)
* deaths = number of reported deaths (cummulative)
* state = two letter state identifier
* pop2010 = Census population for 2010
* pop2019 = Estimated population for 2019
* prev2019 = Coronavirus prevalence as a percent of 2019 population

Prevalence is calculated by:

```
(cases/pop2019) * 100
```
Sample data output is in this repository as [`cv_pop_county.csv`](https://github.com/OptumCS/coronav2/blob/master/cv_pop_county.csv)

Additional data clean-up and processing is noted with comments in the notebook.
