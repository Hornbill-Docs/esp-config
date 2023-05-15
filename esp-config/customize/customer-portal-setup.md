---
layout: article-toc
---
# Customer Portal setup
The Customer Portal is provided as an entry point for guest users, giving them a window into Hornbill and access to selected Hornbill applications.  

## Topics Covered
* Designing the Customer Portal
* Giving access to the Customer Portal
* Advanced settings

## Before you begin
* Knowledge of adding contacts and organizations
* Administrative access to Configuration

## Details

### Regional Settings
The Regional Settings are the defaults for the Customer Portal on the login page and when contacts do not have any regional information set against their contact record.
* **Language**<br>The default language that is displayed to users when accessing the login page and subsequent pages if a language has not been set against their contact record.
* **Time Zone**<br>The default time zone for contacts. All visible date and time fields will be displayed based on this setting. The default is set to (GMT) Greenwich Mean Time : Dublin, Edinburgh, Lisbon, London.
* **Date Time Format**<br>The format of fields that contain both a date and a time. The default is set to 2020-02-21 16:10:30.
* **Date Format**<br>The format of fields that contain just a date. The default is set to 2020-02-21.
* **Time Format**<br>The format of fields that contain just a time. The default is set to 23:30:35.
* **Currency**<br>This is not currently used.
## Security Settings

### Single Sign On Profile
The Customer Portal by default uses basic authentication provided by Hornbill. It is possible to enable the use of a third-party identity provider. See Single Sign On Profiles for more information on creating SSO profiles.

### Anonymous Role
In most cases, the role called Anonymous Guest will be used and recommended. It is possible to create your own role. Any role used here must have a privilege level of guest. Individual contact records do not maintain their own individual roles. All contacts that log in to the customer portal will use the role applied here.

### authorized Role
There are several apps in Hornbill that can extend out the available features in the Customer Portal. Each of those apps supplies guest privilege roles that can be granted to the Customer Portal.

## Options

### Session Timeout
The number of seconds until a user's session automatically ends after no activity

### Permissions
* Allows contacts to register themselves on this portal
* A new visitor to the customer portal will be able to register themselves and have immediate access to the Customer Portal
* Allow contacts to select their organization as part of online registration
* organization records have the option to allow the organization name to be available during the registration where the new contact can select from a list of organizations.
* Allow contacts to reset their password
* Following registration, a temporary generated password may be provided to the contact. Enabling this will allow the contact to change this password.
New guest registrations require authorization before they can log on
Select this option if you require any registration to be authorized before allowing them to log in.

## Customize
### Settings
#### Allow Profile Update
Turning this option ON will allow a contact to view and update their profile information
#### Logo
Add your company logo to the top banner of the Customer Portal. This field needs to contain a secure URL (https) to the image, which must be either a .png or .jpg.
#### Logo Height
Adjust the height of your logo for a perfect fit in the top banner
Home Page Image
Using a URL, include a Home Page image. This URL must be public facing in order for external contacts to see this image. This field needs to contain a secure URL (https) to the image, which must be either a .png or .jpg. For best fit, the size of the image should be around 1024 x 768
Home Page Image background color
Can be used in either in place of an image or the background for a transparent image
Header color
The color of the top navigation bar
Second Head color
The color of the space between the navigation bar and the Home Page Image
Navbar Text color
Text color for any text that appears in the top navigation bar
Home Page Background color
This applies to the middle section of the page, below the image.
Home Page Text
Main Image Text
Section Title (When not logged in)
Set to 0 (zero) if you do not wish to include this title
Section Title (When not logged in)
Set to 0 (zero) if you do not wish to include this title
Section Text
Set to 0 (zero) if you do not wish to include this title
Social Information
This section lets you include links to your company's social media sites. Each included entry will be represented on the portal by is associated logo.

PortalSocialInformation.png
Twitter ID
Add your company's Twitter ID. Enter 0 (zero) to hide
Linkedin ID
Add your company's LinkedIn ID. Enter 0 (zero) to hide
YouTube ID
Add your company's YouTube Channel link. Enter 0 (zero) to hide
Facebook ID
Add your company's Facebook page. Enter 0 (zero) to hide
Social Links Background color
Sets the background color of this section
Social Links Text color
Sets the color of the Social Media logos
Social Text color
Information
If all Social Information Fields contain a 0 (zero), this section will be completely removed
Contact Information
Add contact information for your users on how to contact your Service Desk. Set any field to 0 (zero) in order to hide it from view. Added 0 (zero) to all fields will hide this entire section.

PortalContactUS.png
Contact Title
Contact Us
Phone Number
+44 (0)20 8582 8282
Email
support@hornbill.com
Address
Hornbill, Apollo - Odyssey Business Park, West End Road, Ruislip, HA4 6QD, United Kingdom
About Details
About Title
Hornbill Customer Portal
About Text
The Customer Portal can be used to view and update requests.
Login Details
Auto Login
If you have SSO configured for the Customer Portal, this will bypass the login screen and automatically log the customer into the portal
Terms and Conditions
None
Terms and Conditions are not displayed on the Login screen
Show
This will display the Terms and Conditions on the Login screen. When selected, a field is available to enter or edit the terms and conditions text
Show and make mandatory
This will display the Terms and Conditions on the Login Screen. The customer must select the option, agreeing to these conditions before proceeding. When selected, a field is available to enter or edit the terms and conditions text
Translations
Contact Access
Contact Access
The Contact Access list shows the contacts or Guest Accounts that have been associated with the Customer Portal.

## Add Contact
Add an existing contact to the Customer Portal Account
Set Access
Change the access a contact has to the Customer Portal
Remove Access
Selecting this will remove the contact from the Customer Portal Account
Approved
Set the contact to be approved for access to the Customer Portal. This is automatically set when a contact is manually added to the Customer Portal Account
Suspended
Temporarily suspend a contact's access to the Customer Portal. A contact can be automatically set to suspended after multiple failed password attempts.

<!-- References -->
<!-- https://wiki.hornbill.com/index.php?title=Customer_Portal -->
<!-- https://wiki.hornbill.com/index.php?title=Customize_Customer_Portal -->
<!--  https://wiki.hornbill.com/index.php?title=Managing_Contact_Visibility_of_Organisation%27s_Requests_on_the_Customer_Portal 
<!-- https://wiki.hornbill.com/index.php?title=Customize_Customer_Portal -->

<!-- To Do -->
<!-- Unique email addresess -->
<!-- unathenticated Guests -->
<!-- auto register -->