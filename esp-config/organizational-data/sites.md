---
layout: article-toc
---
# Sites
Sites can be configured to reflect the different physical locations that exist within an organization. 

## Topics covered
* How sites are used
* Creating a site
* Managing a site

## Before you begin

## How sites are used
* A user can be associated to a site to help identify the location of that user.
* Sites can be associated to Company Groups defined within the organization structure. 
* Identify the location of an asset in Service Manager
* Sites can be captured to identify the location of an incident in Service Manager
* Define site based services
* Create analytics based on site

## Creating a site
Sites can be added manually or if you have an existing list of Sites, these can be imported using a Sites CSV import tool.

:::tip
In ensure the User-to-Site associations can be managed automatically when using a user import utility, the name of the site specified in Hornbill must match the name of the site located in the source data. For example, if you are using the LDAP User Import Utility, the contents of the AD attribute that holds the site of a user must match the name of a site that exists in Hornbill. A good starting point in creating your sites may be to extract a list of distinct values from your information source (such as AD) and use these as your site names.
:::

### Manually create a site
To access sites 
1. Open Configuration (Ctrl+Shift+s)
1. Search for **Sites**
1. Select `Manage Sites` from the results list
1. Click on the `+ Create New Site` button

### Uploading multiple sites
The `Upload Sites` option will allow you to upload multiple site records quickly and easily. To upload a list of sites, begin by clicking the `Upload` button. On the next screen, click the Download Template File button located on the right hand side. As with the manual creation of a site, only the site name is mandatory. Import the Sites by using the Select CSV File To Upload option and selecting the file you have prepared.

#### CSV template key fields
|Field Name|CSV Column Name|Description|
|-|-|-|
|Name|h_site_name|This is the only mandatory field|
|Site Code|h_alt_siteref|Some organizations identify their sites by reference numbers, codes, or abbreviations. These can be stored in this field.|
|Type|h_type|There may be a need to report on information relating to particular types of site, such as a distribution center, warehouse, shop, or office.|
|Company|h_company_id|The company id of the group that exists in your organization structure.|
|Building|h_building|The location may be in a particular shared building.|
|Floor|h_floor|The location may be on a particular floor in a shared building.|
|Address|h_address|The address of the site.|
|City|h_city|The town or city where the site is located.|
|State|h_state|The state or county where the site is located.|
|Post/ZIP Code|h_postal_code|The post or zip code of the site.|
|Country|h_country|The country where the site is located. The value expected is the ISO 3166 alpha 2 country code. For example United Kingdom = GB, United States = US.|
|Phone|h_phone_number|The main phone number for the site.|
|Fax|h_fax_number|The main fax number for the site.|
|Notes|h_notes|Any other information you feel is necessary to hold against a site record. This field as a maximum 2000 characters|

:::note
Please note that the CSV upload is designed to create new sites, and cannot be used to manage changes to existing sites.
:::

## Manage sites

### Additional details
* **Latitude and Longitude**<br>Add latitude and longitude values to create a map that shows the location of the site. When there are other sites nearby, these sites will also be displayed on the map. This map can be viewed by users that have access to Sites app accessed through the Home menu.

* **Custom fields 0-9**<br>Use custom fields to store additional information about your site.
::: tip
 By using Translation Mode, you can quickly rename each label to describe the content of the field.  Translation Mode can be accessed through the User Profile menu by users that have the Translation role. 
:::

### Assigning users to a site

#### Site Managers
To help with identifying and communicating with key people that manage a site, you can associated user accounts to one of the four available fields:

* Site Manager
* Regional Manager
* Area Manager
* Site Engineer

#### Site Users
Site users are people that are physically located at the selected site.  Users can be manually added to a site from the `Assigned Users` option or they may be added automatically as part of a user import.

:::note
A user can only belong to one site.  If you add a user to a site and that user was already assigned to a site, their original site will be removed and replaced with the new site.
:::

## Site View
In the User app, it is possible to further customize the data associated to a site:

* Assign Members - Site Manager, Site Engineer, Area Manager, Regional Manager
* Utilize Custom Fields
* Map Geo-Location (Long/Lat values) and View site, and nearby sites on an interactive map

In addition, it is possible using line of business applications such as Service Manager, and Document Manager to see

* Requests Linked to the Site
* Services Subscribed to the Site
* Assets linked to the Site
* Documents linked to the Site