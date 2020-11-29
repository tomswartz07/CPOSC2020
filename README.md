# CPOSC 2020: Surfing the Radio Waves with PostgreSQL

## About

This repository contains the information and details related to
the CPOSC 2020 talk:

**Surfing the Radio Waves with PostgreSQL**

This talk is a beginner-friendly introduction to creating useful ongoing sample
datasets for PostgreSQL.
The talk will focus on how to use Postgres, Raspberry Pis, and Software Defined
Radios to capture and store long-term radio data; particularly weather stations
and aircraft.

Other non-radio based methods for dataset creation will also be discussed.
Additional topics include interesting use cases for the data and challenges
associated with maintaining the various databases.

This code is hosted on both [GitHub](https://github.com/tomswartz07/CPOSC2020)
and [GitLab](https://gitlab.com/tom.swartz07/CPOSC2020).

## Learning Objectives

The ideal audience member is someone who is familiar with PostgreSQL or
databases in general, or someone who is interested in creating useful sample
data for educational purposes.

The talk covers a number of topics and common issues observed by those who
frequently use databases, such as:
- PostGIS applications for sample data
- Resolving issues associated with large datasets
- Grafana data visualizations
- Database maintenance issues

## Session Outline
- Introduction
  - Overview of need which spurred this project
  - Brief explanation on how Software Defined Radio (SDR) works
  - Overview of software stack
- Weather Data to PG
  - Discussion about how the weather2pg app functions in depth
  - Overview of database schema
  - Demonstration of data visualization uses
  - Presentation of issues encountered, resolutions
  - Issues with duplicate source data
  - Issues with long query times
  - Issues with frontend design (Grafana quirks)
- Airplane Tracking to PG
  - Discussion about ADS/B tracking
  - Overview of ADSB database schema
  - Demonstration of data visualization uses
  - Presentation of issues encountered, resolutions
  - Issues with amount of data, ingestion volume
  - Issues with displaying large amounts of GIS location data
- PiHole Stats in PG
  - Discussion about need for long term storage of PiHole stats
  - Overview of DB Schema
  - Demonstration of data visualizations
  - Issues with data retention, data lifetime
  - Tuning autovacuum and fine-detail Postgres settings
- Coronavirus information in PG
  - Discussion about need for COVID-19 tracking for Pennsylvania
  - Overview of covid19 database
  - Discussion of different data sources
  - Presentation of the dataset and analysis methods


## Expectations for Attendees
Attendees will gain knowledge necessary to create their own sample datasets
for PostgreSQL databases (or databases in general) and learn about some interesting
challenges associated with building and maintaining their own datasets.

## Files in this Repository:

- `presentation/cposc2020.tex`: LaTeX Beamer presentation files

## Making the presentation

Assuming you have `pdflatex` installed, or TeXLive
simply run the following command:

```sh
cd presentation
pdflatex cposc2020.tex
```

The PDF document will be generated and viewable for you.

## External Resources

There are a number of projects and external resources which were referenced in this
presentation.
They can be found here:

- [ADSB Live View](https://globe.adsbexchange.com/)
- [RTL SDR Blog](https://www.rtl-sdr.com/)
- [RTL 433](https://github.com/merbanan/rtl_433)
- [Weather Dashboard](https://github.com/tomswartz07/grafana-sdr-weather)
- [Dump1090](https://github.com/tomswartz07/dump1090)
- [ADSB Ingest Python Script](https://github.com/tomswartz07/grafana-sdr-weather/tree/master/dump1090)
- [PiHole API Script](https://github.com/tomswartz07/pihole-stats-postgres)
- [COVID-19 Dataset](https://github.com/tomswartz07/covid19-pennsylvania)
