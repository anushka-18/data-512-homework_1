## Analysing popular dinosaur searches over the years

Through this analysis, we have tried to examine the popularity of different dinosaur Wikipedia pages based on monthly views from July 2015 to September 2022. <br><br>
The dataset (which is a subset of Dinosaur related Wiki pages) is taken from the following location - <br>
[Dinosaur Wiki List Subset](https://docs.google.com/spreadsheets/d/1zfBNKsuWOFVFTOGK8qnTr2DmHkYK4mAACBKk1sHLt_k/edit#gid=1345871712)

To measure article traffic from 2015-2022, we collect data from the Pageviews API. The Pageviews API provides access to desktop, mobile web, and mobile app traffic data from July 2015 through the previous complete month. <br>

### API Documentation and End-points Description

API documentation and the endpoint can be found here - <br>
[API Documentation](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews) <br>
[API Endpoints Description](https://wikimedia.org/api/rest_v1/#/Pageviews_data/get_metrics_pageviews_aggregate_project_access_agent_granularity_start_end)

<br>

### Terms and Conditions and LICENSE of Source Data - 

The terms and conditions to the Wikimedia Foundation REST API terms of use are: <br> 
[Terms and Conditions for API use](https://www.mediawiki.org/wiki/REST_API#Terms_and_conditions)
<br>
License of the source data used from the Wikimedia REST API is as follows: <br>
[Creative Commons Attribution-ShareAlike License](https://creativecommons.org/licenses/by-sa/3.0/)

<br>
The code for invoking the API to gather relevant metrics such as the timestamps and monthly view counts has been taken from the following source - <br>
[Python code reference for API Call](https://colab.research.google.com/drive/1gtFZAjRoOShsqZKuNhiiSn9Ko4ky-CSC#scrollTo=OROH-g2L-4Ei)

<br><br>
We collect monthly access data from different access media such as desktop access and mobile access. The mobile access view count is the sum of mobile-app and mobile-web access view count. We pass the granularity (monthly), to and from timestamps (2015/07 to 2022/09), the article name (taken from the excel list), and the access method (desktop, mobile, etc) to gather the data which is then used to perform the analysis. <br>

### Intermediate files - <br>
In the process, we create three JSON files: <br>
* dino_monthly_mobile_201507-20220.json - Monthly mobile (both web and app) page traffic for each article
* dino_monthly_cumulative_201507-202209.json - Monthly cumulative data (sum of all mobile, and all desktop traffic) per article
* dino_monthly_desktop_201507-202209.json - Monthly desktop page traffic for each article

<br>

### Relevant Visualization - <br>
We then proceed to find the relevant metrics such as the highest average page requests and the lowest average page requests for desktop access and mobile access, top 10 article pages by largest (peak) page views over the entire time duration, and pages that have the fewest months of available data.

These are then plotted as three time series visualizations, which help us analyse the popularity of the dinosaur articles over the years. <br>
* Max_Min_Avg_View_Count.png
* Fewest_Months_of_View_Count.png
* Top_10_Articles.png
