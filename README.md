# International-Migration-from-India-a-financial-perspective

## Introduction:

Looking at emigration from India across various countries in the world, what do you think India's foreign policy should be, as far as maintaining relations with diaspora is concerned? What are the countries where we need to work on our diaspora engagement more, in order to bring more remittances home, given that there is scope? Should it be the country already sending the highest remittances already? 

Also, from a hypothetical perspective, what if these international migrants would have stayed back in India and never migrated in the first place, what would their financial contribution to the nation be vis-a-vis their remittances today. Will comparing these two notions provide a valuable insight?

This project aims to analyse these ideas gathering data sets from World Bank for the year 2021 w.r.t. India. 

**The primary assumption this project is based on is as follows - Imagine that migrants never left India and instead worked in India contributing to its GDP (Gross Domestic Product). Comparing this contribution (with Purchasing Power Parity adjusted) to the remittances sent by migrants will give us a value of 'Net Loss' w.r.t. every country. This parameter will be utilized to form our questions.**

## Data sources:

1. Bilateral Migration Matrix - https://www.knomad.org/data/migration/emigration
2. Bilateral Remittance Matrix - https://www.knomad.org/data/remittances
3. GDP per Capita (PPP adjusted) - https://data.worldbank.org/indicator/NY.GDP.PCAP.CD

## Asking Questions:

Based on the datasets and the assumption of no migration case, where migrants never left the country and instead worked inside the country instead of sending remittances, we are interested to know the following:

1. Which 10 countries created the biggest net loss in terms of Remittances vs. Income earned in India (in zero migration case)
2. Which countries send the most remittances back home, while having highest net losses?
3. Which countries hold the most migrant stock, while having highest net losses?

## Data wrangling:

### Gather Data:

Data from the sources is gathered and ordered into separate excel sheets along with a main sheet for working on the datasets:

#### Bilateral Migration 2021:

![1](https://github.com/shantanu2693/International-Migration-from-India-a-financial-perspective/assets/148590969/83e7911d-433c-4fb6-bd9c-20f709e228bc)

#### Bilateral Remittances 2021:

![2](https://github.com/shantanu2693/International-Migration-from-India-a-financial-perspective/assets/148590969/69a6fc8c-39b5-4edc-8332-73c6b054450c)

#### GDP per capita (PPP adjusted):

![3](https://github.com/shantanu2693/International-Migration-from-India-a-financial-perspective/assets/148590969/ae9132e0-6797-4042-a438-a97d6ee09942)

### Cleaning Data and creating main table for analysis:

* The Bilateral migration Data is filtered for the country - "India":

![4](https://github.com/shantanu2693/International-Migration-from-India-a-financial-perspective/assets/148590969/4a601542-d9aa-424a-b0be-b60bcf364097)

* The data for India is used in the main table under the column - "Bilateral Migrant Stock":

![5](https://github.com/shantanu2693/International-Migration-from-India-a-financial-perspective/assets/148590969/7b2a271f-2109-4b59-96c1-c4997b8b38b4)

* Inserted 0 for empty values in the column using Replace all:

![6](https://github.com/shantanu2693/International-Migration-from-India-a-financial-perspective/assets/148590969/31f25771-c52f-4e2f-8dcf-e181cfcacbcc)

* The data for Bilateral Remittances is fetched using VLOOKUP and converted to Number format with 2 decimals in USD. Also, a few countries are renamed as they are named differently in datasets of Bilateral Migrants and Bilateral Remittances. Example - Guinea-Bissau (in Bilateral Remittances dataset and GuineaBissau (in Bilateral Migration dataset)). Also removed a few countries whose data is not available for the Bilateral remittances dataset (Example - Nauru):

![7](https://github.com/shantanu2693/International-Migration-from-India-a-financial-perspective/assets/148590969/8f6efb9a-7bb6-4be8-8b11-789fd902959d)

* GDP per capita (PPP adjusted) for India is fetched from the respective Excel sheet using VLOOKUP query for India:

![8](https://github.com/shantanu2693/International-Migration-from-India-a-financial-perspective/assets/148590969/7568b041-d3a1-4ab4-9437-0399ecb0b15d)

* A new column is created - "Added GDP for zero migration case". As the name says, this would have been the added GDP for the country had there been zero emigration and it is adjusted for Purchasing power parity so Remittances in USD can be reasonably compared to the added GDP. The calculation is a simple multiplication of the Bilateral migrant stock for 2021 to the GDP per capita for the same year:

![9](https://github.com/shantanu2693/International-Migration-from-India-a-financial-perspective/assets/148590969/93fd9350-b9f9-4cb8-a515-2f4376b9ecda)

* Lastly, a column of "Net Loss" is calculated as follows = Added GDP for zero migration case - Bilateral Remittances. This represents the financial loss, as already defined in the introduction of the project, w.r.t. every country holding Indian migrants:

![11](https://github.com/shantanu2693/International-Migration-from-India-a-financial-perspective/assets/148590969/c9a0ca0e-b26b-4fda-ae69-2c6d1a821a08)

## Exploratory Data Analysis:

Google Looker studio is used in the following analysis by fetching the data from the main table (in MS Excel) and uploading it in Looker to generate visualizations.

### 1. Which 10 countries created the biggest net loss in terms of Remittances vs. Income earned in India (in zero migration case)?

![12](https://github.com/shantanu2693/International-Migration-from-India-a-financial-perspective/assets/148590969/e8b873c3-3275-452c-a30d-47a9fd145be7)

As can be observed from the pie chart, Pakistan tops the list. The Gulf region is also heavily represented.

### 2. Which countries send the most remittances back home, while having highest net losses?

![13](https://github.com/shantanu2693/International-Migration-from-India-a-financial-perspective/assets/148590969/3bb039d0-2413-446d-b1c7-4ea9039c25c1)

UAE tops this list. This essentially determines that UAE sends the most remittances back home though it has scope for more. Pakistan is at the bottom as it sends 0 remittances back to India.

### 3. Which countries hold the most migrant stock, while having highest net losses?

![14](https://github.com/shantanu2693/International-Migration-from-India-a-financial-perspective/assets/148590969/36898897-34aa-43ae-bb6f-f412dcf8f569)

Again, UAE tops the list here. It holds the most number of Indian migrants and they send the highest remittances back home though had those same migrants worked in India and contributed to the GDP, the country would have benefitted financially.

## Conclusions:

![15](https://github.com/shantanu2693/International-Migration-from-India-a-financial-perspective/assets/148590969/054edfdf-d009-42ab-9cbb-077b7ac47898)

Following Conclusions can be derived from the analysis:

* 

## Caveats:
