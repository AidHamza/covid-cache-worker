# Original API :
This repo is a modified version of the COVID API by NovelCOVID https://github.com/NovelCOVID/API

Thank you guys for the API

# Overview :
This repo presents a COVID worker crawling the statistics from Worldometers and Johns Hopkins CSSE

The result is stored in AWS S3 JSON files, and served by a Cloudfront distribution for a better performance, the cache is invalidated after each performed crawl

# Requests Limits :
No limits, feel free to query and use it as you wish

# Data sources
We don't overwrite the past days data, instead it is archived inside S3 folders with the following date format `YYYY-MM-DD`

Base URL : https://covid-data.appsdoc.com

# Data Endpoints
|  GET Request  | Output  |
| ------------ | ------------ |
|  https://covid-data.appsdoc.com/overall.json | Returns all total cases, recovery, and deaths. |
|  https://covid-data.appsdoc.com/world.json | Returns data of all countries that has COVID-19 |
|  https://covid-data.appsdoc.com/{COUNTRY_CODE}.json | Returns data of a country using country code ISO 3166-1, example "MA.json" "ES.json" "US.json" |
|  https://covid-data.appsdoc.com/states.json | Returns data of all the states in the USA |
|  https://covid-data.appsdoc.com/jhucss.json | Return data from the John Hopkins CSSE Data Repository (Provinces and such) |
| https://covid-data.appsdoc.com/historical.json | Get historical data from the start of 2020. (JHU CSSE GISand Data) |

To retrieve data for a specific day, you can use the following format :
`https://covid-data.appsdoc.com/2020-03-22/overall.json`

This format is valid for all the data endpoints in the table

**Start date (We will populate the previous dates tomorrow) : 2020-03-22**

**Note**
Since `data.updated` returns milliseconds, you can do `new Date(data.updated)` as it returns an **ISO Date**

You can read more about **new Date()** [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date)

### Source: 
> https://www.worldometers.info/coronavirus/ 

> https://github.com/CSSEGISandData/COVID-19
