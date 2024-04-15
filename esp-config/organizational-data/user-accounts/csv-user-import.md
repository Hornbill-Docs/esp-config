---
layout: article-toc
---
# CSV user import
From the list of users, a simple CSV import is provided. This is only for the creation of new accounts and does not provide updates to existing accounts.

## Topics covered
This document looks at the requirements and steps used to create multiple user accounts using a CSV Upload in Hornbill. When a large number of user accounts need to be created, a CSV file can be a quick and simple way to achieve this. A CSV template is provided which includes some of the standard fields that are required to create a new user account.

## Before you begin
* Administrative access to Configuration
* Access to a list of the users that you want to add to the CSV file for import

## Quick Steps
1. Open Configuration and select Platform Configuration
1. In the navigation panel under Organizational Data select `Users`
1. From the User List tool bar, select the Upload Users button.
1. Click on the Download Template File button
1. Populate the CSV Template File with the users that you wish to upload
1. Click on the Select CSV File to Upload button
1. View and check upload results

## CSV Template Download
The CSV template consists of the following fields:

|Field name|Description|Mandatory|
|-|-|-|
|userId|The User Id should ideally be made up of alphanumeric characters although full stops (.) and underscores (_) are permissible. The User Id plays a key role in the database relationships so once it is created, it is not possible to amend.|Yes|
|name|This field will form the "Handle" for the User. This is what will be visible when posting to a Workspace or Request Timeline eg: "Harry Hornbill posted on Workspace Hornbill Collaboration Discussion". In this example, Harry Hornbill would be the Handle. This field can be amended at any time.The Handle must be a unique value, however the setting api.xmlmc.uniqueUserHandle.enable can be enabled to allow duplicates.|Yes|
|password|The password which the User will use to log on to the Hornbill Platform.|Yes|
|firstName|The first name of the User.|Yes|
|lastName|The last name of the User. |Yes|
|jobTitle|The Users Job Title. |No|
|phone|The Users telephone number. |No|
|email|The email address of the User.|Yes|
|mobile|The mobile number of the User. |No|
|role|The Hornbill roles that this user requires to perform their day to day duties within Hornbill should be specified here. All those who will access the Platform require the "Collaboration Role" as a minimum. In addition, if they are a Support Desk Analyst, then they may also require the "Incident Management User" role. When specifying multiple roles in this field they should be separated by a colon (:). e.g. to associate the two roles mentioned here, the contents of the role field will look like: Collaboration Role:Incident Management User. The following wiki page will help provide background to the various Platform and Application Roles available.|No|
|userType|The User Type is used to specify whether the User will be an Application User (full platform access based on the Subscriptions) or a Basic User (access is restricted to the Hornbill Service Portal). This field should contain either "user" or "basic" which is case-sensitive. If nothing is specified in this field, the User account created will default to that of an Application User.|No|
|site|While a "Site" column doesn't appear in the downloaded template, the CSV mechanism is aware of this concept. An additional column can be added after "userType" (titled "site") and where a valid site ID is specified the CSV upload mechanism will make the site association successfully to the user. Of course, a list of sites must exist in your instance in order for you to identify and use the appropriate ID which can be found in the URL when viewing a site record. See Sites for more information on importing a list of sites.|No|


:::tip
If you plan on using a third-party automation tool to generate the CSV, the letter case of the field headings is important. The CSV upload function is expecting the field headings in the order and format shown in the above table.
:::