# Introduction
Elections are often a turbulent time in the Philippines with a history of violence, black propaganda, and smear campaigns.  The growing influence of the internet and social media on politics has made the situation a lot more complex. In recent years, the opposition has been steadily organizing into a united front and so have the counterpropaganda thereof. One of the most consistent proponents of what is perceived to be the opposition is Neri Colmenares, with a political career spanning more than a decade advocating for mass-oriented reforms and human rights, who was a candidate in the 2022 Senatorial Elections.

In the recent elections, allegations of Neri being affiliated with the CPP-NPA-NDF have become more prominent. While this is a common tactic to discredit the opposition, it’s hard to prove whether or not these allegations are part of a smear campaign to delegitimize Colmenares’ bid for office. However, one of the ways we could see if this is likely to have happened is to check whether there is a correlation between the frequency of tweets accusing Colmenares of being in cahoots with the CPP-NPA-NDF and the campaign period.

All that information allows us to set up our project of finding out whether it’s likely that these allegations were part of a smear campaign by looking at how key periods surrounding the 2022 elections affected the frequency of tweets red-tagging Neri Colmenares.

# Materials and methods
We collected Twitter tweets from accounts by using a twitter scrape bot. We specifically selected tweets that fell under  December 25, 2021 (45 days before start of campaign period) to June 23, 2022 (45 days after elections) and using the following keywords:
- cpp neri
- npa neri
- npa colmenares
- npa neri
- cpp colmenares
- neri colmenares cadre
- neri colmenares joma sison
Afterwards, a total of 1316 tweets were collected. After combing through all the tweets, a total of 249 valid tweets were then used for the time series analysis (removed duplicates, tweets that were not relevant, etc.).

The data was then preprocessed to take a look at certain aspects such as the general sentiment of the tweets as well as data visualization techniques (histograms, heat maps, bar plots, line graphs, etc.) using different features (ID, account type, tweet type, etc.)

To further our research and findings, we looked more specifically at a time series analysis. A time series hypothesis test was initially done as well as tests for stationarity and normality (Shapiro-Wilk test). Afterwards, we proceeded with the Mann-Whitney U test for before and after the elections, and during and not during the campaign period.

We also ran a Time Series Forecasting to predict the expected number of tweets in a day based on the previous day. This was then used to compare with the actual number of tweets on that day.

# Results and discussion
The Mann-Whitney U test performed shows that there is a significant change (p < 0.05) in the average daily frequency of tweets before and after the election date as well as in and outside of the official campaign period. This points toward a significant correlation between the timing of the elections and the campaign period and the shift in the frequency of tweets. While this doesn't confirm that a smear campaign caused this, some factor did influence the frequency significantly.

It is also worth noting that autocorrelation testing shows some positive autocorrelation in lags < 11 days (max 0.271 at k = 1), which may indicate that the results of the Mann-Whitney U test might not indicate a change as significant as the test suggests.

Findings such as this would go greatly to help inform the public. Evidence of heightened tweets provide evidence-based insights into the prevalence of misinformation and how it can affect public perception of a political candidate. Moreso, it could help indicate the  effectiveness of a candidates’ political campaign strategies. These time series analyses could also help in identifying influential or significant events that could trigger an increase or decrease in discourse regarding misinformation of a candidate.

Overall, the findings of this research show that there was a significant  increase in the misinformation tweets regarding Neri Colmenares’ alleged affiliation with the CPP-NPA-NDF during the campaign period. Furthermore, it shows confirmation that there is a perception of the Senatorial candidate being affiliated with the CPP-NPA-NDF, when there is none. This perception could have then influenced the results of the senatorial election, where, as we know, Neri Colmenares was not able to get a seat.

# Implications and future work

While our findings point towards a significant difference across key time periods of the 2022 elections, it’s not conclusive enough for us to determine whether a smear campaign was involved. One of the possible alternative implications of these results is an increase in discourse surrounding Neri Colmenares’ alleged affiliation with the CPP-NPA-NDF – which could be a result of the expected general increase in discourse during the campaign period and before the elections.

To help ascertain the involvement of a smear campaign, future work could look into the types of accounts posting these allegations to see the likelihood that troll farms were employed and to look into the rest of the tweets that this study did not account for  to look at whether the difference found in this project is proportionate to the behavior of tweets about Neri Colmenares in general.

# Conclusion