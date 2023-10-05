---
layout: article-toc
---
# Locations
Locations can be configured to reflect the different physical locations that exist within an organization. Locations are places that generally have a street address or an identifiable location on a map. Locations can be used to identify locations around the world or buildings within a single location.

## Topics Covered
* How locations are used
* Creating a location
* Managing a location

## Before You Begin
* Requires admin access or a user with the Location Manager role
* Access to addresses and location information for your location

## How Locations are Used
* A user can be associated with a location to help identify the location of that user.
* Locations can be associated with Company Groups defined within the organization structure. 
* Identify the location of an asset in Service Manager.
* Locations can be captured to identify the location of an incident in Service Manager.
* Define location based services.
* Create analytics based on a location.

## Creating a Location
Locations can be added manually or if you have an existing list of locations, these can be imported using the `Upload Locations` tool using a CSV file.

:::tip
To ensure the User-to-location associations can be managed automatically when using a user import utility, the name of the location specified in Hornbill must match the name of the location in the source data. For example, if you are using the [LDAP User Import Utility](/data-imports-guide/users/ldap/overview/), the contents of the AD attribute that holds the location of a user must match the name of a location that exists in Hornbill. A good starting point in creating your locations may be to extract a list of distinct values from your information source (such as AD) and use these as your location names.
:::

### Manually Create a Location
To access locations 
1. Open Configuration (Ctrl+Shift+s).
1. Search for **locations**.
1. Select `Manage Locations` from the results list.
1. Click on the `+ Create New Location` button.

### Upload Locations
The `Upload Locations` option will allow you to upload multiple location records quickly and easily. To upload a list of locations, begin by clicking the `Upload Locations` button. On the next screen, click the Download Template File button located on the right hand side. As with the manual creation of a location, only the location name is mandatory. Import the locations by using the Select CSV File To Upload option and selecting the file you have prepared.

#### CSV Template Key Fields
|Field Name|CSV Column Name|Description|
|-|-|-|
|Name|h_site_name|This is the only mandatory field|
|Code|h_alt_siteref|Some organizations identify their locations by reference numbers, codes, or abbreviations. These can be stored in this field.|
|Type|h_type|There may be a need to report on information relating to particular types of locations, such as a distribution center, warehouse, shop, or office.|
|Company|h_company_id|The company id of the group that exists in your organization structure.|
|Building|h_building|The location may be in a particular shared building.|
|Floor|h_floor|The location may be on a particular floor in a shared building.|
|Address|h_address|The address of the location.|
|City|h_city|The town or city where the location is.|
|State|h_state|The state or county where the location is.|
|Post/ZIP Code|h_postal_code|The post or zip code of the location.|
|Country|h_country|The country where the location is. The value expected is the ISO 3166 alpha 2 country code. For example United Kingdom = GB, United States = US.|
|Phone|h_phone_number|The main phone number for the location.|
|Fax|h_fax_number|The main fax number for the location.|
|Notes|h_notes|Any other information you feel is necessary to hold against a location record. This field as a maximum 2000 characters|

:::note
Please note that the `Upload Locations` is designed to create new locations, and cannot be used to manage changes to existing locations.
:::

## Manage Locations

### Additional Details
* **Latitude and Longitude**<br>Add latitude and longitude values to create a map that shows the location. When there are other nearby locations, these will also be displayed on the map. This map can be viewed by users who have access to the Locations view, located under the Home menu.

* **Custom fields 0-9**<br>Use custom fields to store additional information about your location.
::: tip
 By using [Translation Mode](/esp-config/internationalization/translation-mode), you can quickly rename each label to describe the content of the field.  Translation Mode can be enabled or disabled through the User Profile menu by users that have the Translation role. 
:::

### Assigning Users to a Location

#### Location Managers
To help with identifying and communicating with key people who manage a location, you can associate user accounts to one of the four available fields:

* Location Manager
* Regional Manager
* Area Manager
* Location Engineer

#### Location Users
Location users are people that are physically located at the selected location.  Users can be manually added to a location from the `Assigned Users` option or they may be added automatically as part of a user import.

:::note
A user can only belong to one location.  If you add a user to a location and that user was already assigned to a location, their original location will be removed and replaced with the new location.
:::

## Location Roles
* **Locations Manager**<br>This security role grants a user the right to be able to create and update locations.  This role can be used to delegate the management of locations to a non-admin user.

## Location View
The Location View is available to users within the main browser application under the `Home` menu.  Here, users can view information about locations such as the address and a list of coworkers located at that location. A user with the `Location Manager` also has options to update location information from this view. 

* Assign Members - Location Manager, Location Engineer, Area Manager, Regional Manager.
* Utilize Custom Fields
* Map Geo-Location (Long/Lat values) and View location, and nearby locations on an interactive map

In addition, it is possible using line of business applications such as Service Manager, and Document Manager to see:

* Requests Linked to the location.
* Services Subscribed to the location.
* Assets linked to the location.
* Documents linked to the location.

<!-- https://wiki.hornbill.com/index.php?title=Sites -->