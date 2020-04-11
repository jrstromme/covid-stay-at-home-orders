# covid-stay-at-home-orders
Database of U.S. Stay at Home Orders at the State, County, and City Level

## Intro

This is a compilation of government mandated stay-at-home/shelter-in-place orders at the state, county and city level.

Thus far I did not notice any online databases at the COUNTY level. All available databases only referenced state level stay-at-home orders.

The goal of this dataset is to be available to use for inference at a finer level than state mandates.

## Data Collection

This data was aggregated from the New York Times's page on stay-at-home orders:
https://www.nytimes.com/interactive/2020/us/coronavirus-stay-at-home-order.html

The NYT only lists the latest most comprehensive order and updates the page often, therefore the wayback machine was used to gather older county-level orders. The last screenshot available on each day in the archive was used.

A pdf record of each order is in the Documentation folder. When an order could not be easily located, a news-release or other semi-official document is saved. The vast majority of orders have official documents.

The NYT often list the enactment time of the order. If the time is listed and the enactment time is after the typical workday, e.g. 5pm or later, then the "effective" date is listed as the following day. This is chosen because the point of this dataset is to be used with other data to make inferences, and thus seems more important to list when mandates are *effective*, rather than *enacted*. If an order is enacted late in the day, it really only becomes effective on the following day. There is likely some measurement error where effective times were late in the day but not listed on the NYT, although this should be found with a more thorough analysis of the source documentation.

The NYT listed orders from states, counties, and cities. However, this compiled dataset should be considered well-represented yet incomplete. There are likely some county/city orders that are missing in this dataset, as it is somewhat difficult to source these orders.

## Codebook

state:      State Name. Available for all rows
postalcode: State Postal Code
statefips:  State FIPS Code
county:     Name of county
countyfips: County FIPS CODE, lists as "NA" string for state rows. Is missing for cities. This is because cities tend to overlap into many counties, so it is left up to the user if they want to classify this data or not.
city:       City Name. This field should be missing for counties and states    
effectivedate: "Effective" date of the stay-at-home order, in dd/mm/yy format




