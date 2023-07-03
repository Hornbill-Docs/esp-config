---
layout: article-toc
---
# Office Locations
Office locations can be configured to reflect the different physical locations that exist within an organization. Office locations are locations that generally have a street address or an identifiable location on a map. Office locations can be used to identify offices around the world or buildings within a single location.

## Topics covered
* How office locations are used
* Creating an office location
* Managing an office location

## Before you begin
* Requires admin access or a user with the office Manager role
* Access to addresses and location information for your office location

## How Office Locations are used
* A user can be associated with an office location to help identify the location of that user.
* Office locations can be associated with Company Groups defined within the organization structure. 
* Identify the location of an asset in Service Manager
* Office locations can be captured to identify the location of an incident in Service Manager
* Define office based services
* Create analytics based on office

## Creating an Office Location
Offices can be added manually or if you have an existing list of offices, these can be imported using a offices CSV import tool.

:::tip
To ensure the User-to-office associations can be managed automatically when using a user import utility, the name of the office specified in Hornbill must match the name of the office located in the source data. For example, if you are using the LDAP User Import Utility, the contents of the AD attribute that holds the office of a user must match the name of a office that exists in Hornbill. A good starting point in creating your offices may be to extract a list of distinct values from your information source (such as AD) and use these as your office names.
:::

### Manually create a office
To access office locations 
1. Open Configuration (Ctrl+Shift+s)
1. Search for **offices**
1. Select `Manage offices` from the results list
1. Click on the `+ Create New office` button

### Uploading multiple offices
The `Upload offices` option will allow you to upload multiple office records quickly and easily. To upload a list of offices, begin by clicking the `Upload` button. On the next screen, click the Download Template File button located on the right hand side. As with the manual creation of a office, only the office name is mandatory. Import the offices by using the Select CSV File To Upload option and selecting the file you have prepared.

#### CSV template key fields
|Field Name|CSV Column Name|Description|
|-|-|-|
|Name|h_office_name|This is the only mandatory field|
|office Code|h_alt_officeref|Some organizations identify their offices by reference numbers, codes, or abbreviations. These can be stored in this field.|
|Type|h_type|There may be a need to report on information relating to particular types of office, such as a distribution center, warehouse, shop, or office.|
|Company|h_company_id|The company id of the group that exists in your organization structure.|
|Building|h_building|The location may be in a particular shared building.|
|Floor|h_floor|The location may be on a particular floor in a shared building.|
|Address|h_address|The address of the office.|
|City|h_city|The town or city where the office is located.|
|State|h_state|The state or county where the office is located.|
|Post/ZIP Code|h_postal_code|The post or zip code of the office.|
|Country|h_country|The country where the office is located. The value expected is the ISO 3166 alpha 2 country code. For example United Kingdom = GB, United States = US.|
|Phone|h_phone_number|The main phone number for the office.|
|Fax|h_fax_number|The main fax number for the office.|
|Notes|h_notes|Any other information you feel is necessary to hold against a office record. This field as a maximum 2000 characters|

:::note
Please note that the CSV upload is designed to create new offices, and cannot be used to manage changes to existing offices.
:::

## Manage offices

### Additional details
* **Latitude and Longitude**<br>Add latitude and longitude values to create a map that shows the location of the office. When there are other offices nearby, these offices will also be displayed on the map. This map can be viewed by users that have access to the offices view, located under the Home menu.

* **Custom fields 0-9**<br>Use custom fields to store additional information about your office.
::: tip
 By using Translation Mode, you can quickly rename each label to describe the content of the field.  Translation Mode can be accessed through the User Profile menu by users that have the Translation role. 
:::

### Assigning users to a office

#### office Managers
To help with identifying and communicating with key people that manage an office, you can associate user accounts to one of the four available fields:

* Office Manager
* Regional Manager
* Area Manager
* Office Engineer

#### Office Users
Office users are people that are physically located at the selected office.  Users can be manually added to an office from the `Assigned Users` option or they may be added automatically as part of a user import.

:::note
A user can only belong to one office location.  If you add a user to a office and that user was already assigned to an office, their original office will be removed and replaced with the new office.
:::

## Office Location Roles
* **offices Manager**<br>This security role grants a user the right to be able to create and updated office locations.  This role can be used to delegate the management of offices to a non-admin user.

## Office View
The Office View is available to users within the main browser application under the `Home` menu.  Here, users can view information about offices such as the address and a list of coworkers located at that office. A user with the `Office Manager` also has options to update office information from this view. 

* Assign Members - Office Manager, Office Engineer, Area Manager, Regional Manager.
* Utilize Custom Fields
* Map Geo-Location (Long/Lat values) and View office, and nearby offices on an interactive map

In addition, it is possible using line of business applications such as Service Manager, and Document Manager to see:

* Requests Linked to the office location
* Services Subscribed to the office location
* Assets linked to the office location
* Documents linked to the office location