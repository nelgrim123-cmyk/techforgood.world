---
layout: page
title: PharmaPlanTest
permalink: /planpharma/
description: "PharmaPlanTest: open prototype forecasting regional pharmaceutical demand in Italy from AIFA and ISTAT open data, with Holt-Winters and SARIMAX models."
---

<div class="about-hero">
  <div class="about-intro">
      <p class="about-tagline">Regional drug-demand forecasting for Italy, built on AIFA and ISTAT open data</p>
          <a href="https://pharmaplanning-techforgood.streamlit.app" target="_blank" rel="noopener" class="about-linkedin">Open PharmaPlanTest &rarr;</a>
            </div>
            </div>

## What it does

PharmaPlanTest is a working prototype that forecasts short-term regional demand for pharmaceutical distribution channels in Italy, using open data from AIFA (packages dispensed by region, category and distribution channel) and ISTAT (population and demographic trends).

- Category selection at two levels: AIFA/OsMed's official therapeutic area naming, and the specific ATC classification underneath it
- Statistical forecast, up to 12 months ahead, automatically chosen per region/category by backtest between Holt-Winters and a SARIMAX model with calendar, seasonal and regional demographic regressors
- Historical analysis: year-over-year trends, category mix shifts, and distribution channel breakdown
- Built entirely on public, open datasets (AIFA, ISTAT), no proprietary or patient data involved

## Why it matters

Demand planning in pharma distribution is still largely reactive. This tool explores whether a simple, transparent statistical model, built on data anyone can download, can give a useful directional signal for regional planning conversations.

## Try it

The app is free to use and requires no login.

<a href="https://pharmaplanning-techforgood.streamlit.app" target="_blank" rel="noopener" class="about-linkedin">Open PharmaPlanTest &rarr;</a>

*A prototype under active development, feedback welcome.*
