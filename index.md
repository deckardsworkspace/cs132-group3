---
layout: default
title: G3 | Portfolio
---

![NeriTweet]({{ site.baseurl }}/public/images/logo.png)

We are **CS 132 Group 3** and this is our project, **NeriTweet: Time-Series Analysis on Tweets Regarding Neri Colmenares' Alleged Affiliation with the CPP-NPA-NDF.** It is a statistical analysis on the allegations of Neri Colmenares' affiliation with the CPP-NPA-NDF and possible correlations with the 2022 senatorial elections.

# Problem formulation

Here, we define the problem that we want to answer. In addition, we also form our hypothesis and null hypothesis.

## Research question

How likely were these allegations part of a smear campaign on Neri’s election?

## Null hypothesis

The allegations of Neri’s affiliation with the CPP-NPA-NDF had no significant correlation with the timing of the senatorial 2022 elections.

## Alternative hypothesis

The allegations of Neri’s affiliation with the CPP-NPA-NDF were part of a smear campaign launched in time to affect his chances during the 2022 senatorial elections.

## Action plan

Analyze the timestamps of the tweets linking Neri Colmenares with the CPP-NPA-NDF and inspect their proximity to key dates during the 2022 election season.


# Data exploration

Here, we explore the data that we have gathered. We also show the results of our analysis.

## Data gathering

We scraped Twitter for data surrounding tweets regarding Neri Colmenares' alleged ties to the CPP-NPA-NDF and submitted it for further validation. You can find the scripts we used for data gathering [here.](https://github.com/jareddantis/cs132-group3-scripts)

## Preprocessing

In data pre-processing, we examine the contents of the dataset and identify key features relevant to our project, handle missing values and outliers, and ensure consistent formatting throughout the dataset.

## Visualization

As part of our data exploration, we visualized the data through interactive plots that illustrate how the date a particular tweet was posted interacts with its type, poster, content, and other possible factors.


# Analysis and results

We performed statistical testing to check for the significance of the difference of tweet frequency between data groups of interest and created models that predicted the expected tweet frequency had no significant interference been made during the campaign period and beyond.

Take a look at our results [here.]({{ site.baseurl }}/2023/06/24/results.html)

## Statistical testing

To examine the behavior of the frequency of tweets surrounding significant dates in the 2022 elections, a two-sample t-test was done surrounding the campaign period and election date.

Mann-Whitney U testing shows a significant change (p ≤ 0.05) in average daily Tweet frequency before and after election dates, and in- and outside the official campaign period.

The dataset was shown to have some positive correlation in lags < 11 days (max 0.271 at k=1), suggesting that the results might not indicate a change as significant as the test suggests, presenting a limitation to these findings.

## Machine learning

Predictors based on the scikit-learn decision tree and gradient boosting regression models were trained from the first 45 days prior to the campaign period to observe their corresponding cumulative sums.

Both models predicted cumulative Tweet frequency sums lower than the actual cumulative Tweet frequency sum during and beyond the campaign period.


# Conclusion

Current results point towards a significant correlation between the timing (of the elections and the campaign period) and the shift in the frequency of tweets as seen in the results of the Mann-Whitney U test and basic predictors. While this doesn't confirm that a smear campaign caused this, some factor did.

The researchers recommend further analysis of the data as the Mann-Whitney U test does not explicitly account for temporal dependencies. Validating the assumptions of the test and incorporating additional variables that may impact the time series analysis could lead to more insights and provide clearer answers.
