---
permalink: "trade-leads.html"
layout: body
title: Trade Leads API
published: true
---

#<a href="trade-leads.html">Trade Leads API</a>

The Trade Leads API provides contract opportunities for U.S. businesses selling their products and services overseas. These leads come from a variety of sources:

The State Department’s Business Information Database System (BIDS)
: A portal built to help U.S. businesses learn about significant international commercial opportunities, subject to their [open government license](https://github.com/USStateDept/bids).

The United Kingdom
: The [UK Government](https://www.contractsfinder.businesslink.gov.uk/) provides procurement information for their government opportunities, subject to their [open government license](http://www.nationalarchives.gov.uk/doc/open-government-licence/).

Canada
: The [Canadian Government](https://buyandsell.gc.ca/procurement-data/) provides procurement information for their government opportunities, subject to their [open government license](http://data.gc.ca/eng/open-government-licence-canada).

Developers can use this API to keep businesses aware of the latest leads in particular industries or locations. They can also enhance the value of the leads by incorporating reports from ITA’s [Market Research Library](http://developer.trade.gov/market-research-library.html) or [Trade News & Articles](http://developer.trade.gov/trade-news-articles.html) APIs.

The output format for this API is JSON.

##Resource URL

<div><a href="http://api.trade.gov/trade_leads/search"><pre>http://api.trade.gov/trade_leads/search</pre></a></div>

##Search Parameters

###keyword

Searches for a match within the title and description fields.

    http://api.trade.gov/trade_leads/search?q={term}

#####Example:

<div><a href="http://api.trade.gov/trade_leads/search?q=electrical"><pre>http://api.trade.gov/trade_leads/search?q=electrical</pre></a></div>

###industries

Returns industry that the lead relates to.  Note:  This method allows you to search for multiple industries (plural) but will only return one industry (singular) per lead.  Also, this method will soon be updated to limit the search to controlled industry names.

    http://api.trade.gov/trade_leads/search?industries={term}

#####Example:

<div><a href="http://api.trade.gov/trade_leads/search?industries=agribusiness"><pre>http://api.trade.gov/trade_leads/search?industries=agribusiness</pre></a></div>

###countries

Returns location of lead based on ISO [alpha-2 country codes](http://www.iso.org/iso/home/standards/country_codes/country_names_and_code_elements.htm).  Note:  This method allows you to search for multiple countries (plural) but will only return one country (singular) per lead.  

    http://api.trade.gov/trade_leads/search?countries={country code}

#####Example:

<div><a href="http://api.trade.gov/trade_leads/search?countries=MX,CA,GB"><pre>http://api.trade.gov/trade_leads/search?countries=MX,CA,GB</pre></a></div>

###size + offset

The size parameter allows you to configure the maximum amount of hits to be returned. The offset parameter defines the offset from the first result you want to fetch.

#####Example:

<div><a href="http://api.trade.gov/trade_leads/search?country=BR&size=1&offset=1"><pre>http://api.trade.gov/trade_leads/search?country=BR&size=1&offset=1</pre></a></div>


## Return Values

### Generic Return Values

Every returned lead will have the following fields:

| Field | Description |
| ------| ------------|
| description | Description of the opportunity |
| industry | Industry category assigned to the opportunity |
| procurement_organization | Agency responsible for the contract |
| publish_date | Date lead was posted |
| specific_location | Location of the opportunity |
| status | Status of the lead (note this API only shows open leads) |
| url | URL that pertain to the bid |
| type | Trade lead source|

### Additional Return Values for Canadian leads

In addition to the Generic Return Values, Canada leads will have the following fields:

| Field	| Description |
| ------| ------------|
| bid_type | The criteria for the contract  |
| competitive_procurement_strategy | Bidding criteria for respondents |
| contract_number | Contract Number for the opportunity |
| country | Canada |
| end_date | Closing date for the lead |
| implementing_entity | Agency responsible for the implementation |
| non_competitive_procurement_strategy | States whether it is a competitive procurement |
| notice_type | Type of contract |
| procurement_organization | Agency responsible for the contract |
| trade_agreement | Relevant trade agreement for the contract |
| contact | Point of contact |

### Additional Return Values for United Kingdom leads

In addition to the Generic Return Values, United Kingdom leads will have the following fields:

| Field	| Description |
| ------| -------------|
| contact | Point of contact |
| country | Great Britain |
| id | ID of the trade lead |
| max_contract_value  | Maximum value of the lead (in pounds) |
| min_contract_value | Minimum value of the lead (in pounds) |
| notice_type | Type of contract |
| procurement_organization 	| Agency responsible for the contract |
| reference_number | Reference number for the opportunity |
| status | Status of the lead (note this API only shows open leads) |
| title| Title of the opportunity |

### Additional Return Values for State Department leads

In addition to the Generic Return Values, State Department leads will have the following fields:

| borrowing_entity | Bank funding the project|
| comments | comments about the project|
| contract_number | Contract Number for the opportunity|
| end_date | Closing date for the lead|
| funding_source | Funding source of the project|
| id | ID of the trade lead|
| project_number | Number for the opportunity|
| project_pocs | Point of contact|
| project_size | Industry category assigned to the opportunity|
| reference_number | Reference number for the opportunity|
| source | Source of the trade lead, typically an organization|
| submitting_officer | Contract officer name|
| submitting_officer_contact | Contract officer email|
| tags | Keywords of the opportunity|
| title | Title of the opportunity (Canadian Leads) State
