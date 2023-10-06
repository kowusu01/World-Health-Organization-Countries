# World-Health-Organization-Countries
 Repo for dataset containing World Health Organization countries and regions to help Data Analysts,
 
## Description
The dataset is meant for data anylsis specifically related to World Health Organization Malaria data set shared via this link: [Malaria Dataset](https://www.kaggle.com/datasets/imdevskp/malaria-dataset/data)

## Sources:

- https://www.kaggle.com/datasets/imdevskp/malaria-dataset/data
- https://en.wikipedia.org/wiki/List_of_ISO_3166_country_codes
- https://en.wikipedia.org/wiki/List_of_WHO_regions

## How the data was obtained
The World Health Organization(WHO) groups the countries it works with into regions. See https://en.wikipedia.org/wiki/List_of_WHO_regions.
Tne malaria dataset includes the number of malaria cases, number of deaths, and the WHO region that the data is reported from. 

My focus was more on data quality rather than analysis of the Malaria cases, I wanted to be able to verify that each data row reported was valid and the data as a whole is reliable. For instance, I wanted to make sure that the countries reported were valid and that the countries are also placed in the correct region.


This can be very crucial for organization that depends on data feeds from various sources on a regular basis.

To achieve this, the following approach was followed:

1. scrape the wikipedia site https://en.wikipedia.org/wiki/List_of_ISO_3166_country_codes for list of countries
2. scrape the wikipedia site https://en.wikipedia.org/wiki/List_of_WHO_regions for list of who regions and countries
3. merge the two together to get a dataset with the following fields:

## Data Fields
CountryName

- the name generally used by WHO to refer to the country

LongName

- the official long name the country is often referred to

IsWHOCountry

- a boolean whether or not this country is a WHO country, i.e. a country WHO workds with

WHORegion

- if the country is a WHO country, this field will have the WHO region for the country, e.g. 'Amreicas'

WHORegionCode

- the region code for the WHO region - e.g. 'AMR' for the America regions

WHORegionName

- the full name that can be used in reporting e.g. Region of the Americas

ISO2

- two letter iso code for the country, e.g. 'US' for the United States

ISO3

- three letter iso code for the country, e.g. 'USA' for the United States

ISONum

- the three digit numeric iso number for the country, e.g. '840' for the United States

## Note
1. Some countries may not appear in the country list, espcially countries that are not WHO countries.

## Gotchas
- In the dataset, the country Namibia has a country iso code as "NA". In some cases R reads this as NA. You may have to verify after reading the data to make sure Namibia has two digit iso code as string "NA" not NA or Null.

