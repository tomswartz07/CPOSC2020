# Sample Datasets

This folder contains sample datasets, with data from recent COVID19 statistics
for the state of Pennsylvania.

There are several tables in this dump file, which will be described below.

## Loading and using this data

Provided you have a working PostgreSQL installation, you can simply import this
data with `psql`.

```
psql -h $hostname -d $dbname -f covid19.sql
```

## Data Overview

- covid19.covid19pa: Table containing PA daily case counts, fatality data, and computed values
- covid19.covid19us: Table containing per-county case/fatality data for entire US. Obtained from NYTimes data source
- covid19.pa_events: Table containing notable PA-specific events throughout the timeline of the pandemic.


## Interesting Queries

1. Listing new daily cases, per county:
  ```sql
  SELECT
  date,
  county,
  avg(cases) - lag(avg(cases)) OVER (PARTITION BY county ORDER BY floor(extract(epoch from date::timestamptz)/3600)*3600) AS "New Daily Cases"
  FROM covid19.covid19us
  WHERE
  date BETWEEN now() - interval '31 days' AND now()
  AND state = 'Pennsylvania'
  GROUP BY 1,2
  ORDER BY 1,2
  ;
  ```

2. List statewide new cases, by day:
  ```sql
  SELECT
    date,
    new_cases AS "New Cases"
  FROM covid19.covid19pa
  WHERE
    date BETWEEN now() - INTERVAL '31 days' AND now()
  ORDER BY 1
  ;
  ```

3. List most recent fatalities, by county:
  ```sql
  SELECT distinct on (county)
    county AS "County",
    date AS "Date",
    deaths - lag(deaths, 1) OVER (PARTITION BY county ORDER BY date) AS "New Deaths"
  FROM covid19.covid19us
  WHERE
    state = 'Pennsylvania'
    AND
    county NOT LIKE 'Unknown'
  ORDER BY 1,2 DESC
  ;
  ```
