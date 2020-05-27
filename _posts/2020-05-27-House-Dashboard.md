---
layout: post
title: "House Dashboard Project Overview"
date: 2020-02-06
---

## Repos

### House Dashboard

React front-end, using Recharts to present graphs of rainfall, temperature and river level.

<https://github.com/alun1111/house-dashboard>

### House Dashboard Server

ASP.net server providing API access to raw and aggregated data.

<https://github.com/alun1111/house-dashboard-server>

### Rainfall scraper

Lambda function, written in Python. Reads from SEPA rainfall monitoring station API's.

<https://github.com/alun1111/rainfall-scraper>

### River levels

Lambda function, written in Python. Reads from the SEPA river levels API and writes to DynamoDB.

<https://github.com/alun1111/riverlevels>

### Weewx Data Extractor

Python script to read a local weewx sdb file and upload it using boto3 to DynamoDB.

<https://github.com/alun1111/weewx-data-extractor>

