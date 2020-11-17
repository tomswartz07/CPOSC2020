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

Other methods for dataset creation will be discussed, as well as the interesting
use cases for each and the challenges associated with maintaining these databases
will be discussed.


## Learning Objectives

The talk covers a number of topics and common issues observed by those who
frequently use databases, covering items such as: 
- pgMonitor/Grafana 
- PostGIS applications 
- Monitoring use cases 
- Cluster Replication 
- pgBackRest applications on low-end hardware 
- Resolving issues associated with large datasets

The ideal audience member is someone who is familiar with PostgreSQL or databases
in general, or someone who is interested in creating useful sample data for educational
purposes.

## Session Outline
- Introduction 
  - Brief explanation on how Software Defined Radio (SDR) works 
  - Overview of need which spurred this project 
  - Overview of software stack 
- Weather Data to PG 
  - Discussion about how the weather2pg app functions in depth 
  - Overview of database schema 
  - Demonstration of data visualization 
  - Presentation of issues encountered, resolutions 
  - Issues with duplicate source data 
  - Issues with long query times 
  - Issues with frontend design (Grafana quirks) 
- Airplane Tracking to PG 
  - Discussion about ADS/B tracking 
  - Overview of ADSB database schema 
  - Demonstration of data visualization 
  - Presentation of issues encountered, resolutions 
  - Issues with amount of data, ingestion volume 
  - Issues with speed-of-light and time-of-flight 
  - Issues with displaying large amounts of GIS location data
- PiHole Stats in PG
  - Discussion about need for PG with PiHole Stats
  - Overview of DB Schema
  - Demonstration of data visualization
  - Issues with data retention, data lifetime
  - Tuning autovacuum and fine-detail Postgres settings
- Coronavirus information in PG 
  - Discussion about need for COVID-19 tracking for Pennsylvania 
  - Overview of covid19 database 
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
