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

### Security Settings

* **Single Sign On Profile**<br>The Customer Portal by default uses basic authentication provided by Hornbill. It is possible to enable the use of a third-party identity provider. See Single Sign On Profiles for more information on creating SSO profiles.

* **Anonymous Role**<br>The Anonymous Role provides a level of access that is available prior to a contact logging into the Service Portal. In most cases, the role called Anonymous Guest will be used and recommended. It is possible to create your own role. Any role used here must have a privilege level of guest.

* **Authorized Role**<br>The Authorized Roles are applied to all contacts once they have logged into the Service Portal. There are several apps in Hornbill that can extend out the available features in the Customer Portal. Each of those apps supplies guest privilege roles that can be granted to the Customer Portal.

### Options

* **Session Timeout**<br>The number of seconds until a user's session automatically ends after no activity.  The default is set to 900 seconds (15 minutes).  

* **Permissions**<br>Permissions are available to control self-registration and profile updates. 
    * **Allows contacts to register themselves on this portal**<br>A new visitor to the customer portal will be able to register themselves and have immediate access to the Customer Portal.  This will create a new contact record in Hornbill.
    * **Allow contacts to select their organization as part of online registration**<br>When enabled the customer registration form on the portal will show an organization select box. The select list is populated with organization records that are marked as being visible on the registration page. Click on the ? icon for instruction on how to make an orgianization available in the select box.
    * **Allow contacts to reset their password**<br>Following registration, a temporary generated password may be provided to the contact. Enabling this will allow the contact to change this password.
    * **New guest registrations require authorization before they can log on**<br>Select this option if you require any registration to be authorized before allowing them to log in.
    * **Allow contacts to update their profile**<br>Turning this option `ON` will allow a contact to view and update their profile information.

## Customize
* **Settings**<br>Set images and colors for Self Service
    * **Logo**<br>Add your company logo to the top banner of the Customer Portal. This field needs to contain a secure URL (https) to the image, which must be either a .png or .jpg.
    * **Logo Height**<br>Adjust the height of your logo for a perfect fit in the top banner.
    * **Home Page Image**<br>Using a URL, include a Home Page image. This URL must be public facing in order for external contacts to see this image. This field needs to contain a secure URL (https) to the image, which must be either a .png or .jpg. For best fit, the size of the image should be around 1024 x 768.
    * **Home Page Image background color**<br>Can be used in either in place of an image or the background for a transparent image.
    * **Header color**<br>The color of the top navigation bar.
    * **Second Head color**<br>The color of the space between the navigation bar and the Home Page Image.
    * **Navbar Text color**<br>Text color for any text that appears in the top navigation bar.
    * **Home Page Background color**<br>This applies to the middle section of the page, below the image.

* **Home Page Text**<br>Main Image Text.
    * **Main Image Text**<br>
    * **Section Title (When not logged in)**<br>Set to 0 (zero) if you do not wish to include this title.
    * **Section Title (When not logged in)**<br>Set to 0 (zero) if you do not wish to include this title.
    * **Section Text**<br>Set to 0 (zero) if you do not wish to include this title.

* **Social Information**<br>This section lets you include links to your company's social media sites. Each included entry will be represented on the portal by is associated logo.
    * **Twitter ID**<br>Add your company's Twitter ID. Enter 0 (zero) to hide.
    * **Linkedin ID**<br>Add your company's LinkedIn ID. Enter 0 (zero) to hide
    * **YouTube ID**<br>Add your company's YouTube Channel link. Enter 0 (zero) to hide
    * **Facebook ID**<br>Add your company's Facebook page. Enter 0 (zero) to hide
    * **Social Links Background color**<br>Sets the background color of this section.
    * **Social Links Text color**<br>Sets the color of the social media logos.
    * **Social Text color**<br>Sets the color of the social media text
    
:::tip
If all Social Information Fields contain a 0 (zero), this section will be completely removed
:::

* **Contact Information**<br>Add contact information for your users on how to contact your Service Desk. Set any field to 0 (zero) in order to hide it from view. Added 0 (zero) to all fields will hide this entire section.
    * **Contact Title**<br>Contact Us.
    * **Phone Number**<br>+44 (0)20 8582 8282
    * **Email**<br>support@hornbill.com
    * **Address**<br>Hornbill, Apollo - Odyssey Business Park, West End Road, Ruislip, HA4 6QD, United Kingdom

* **About Details**
    * **About Title**<br>Hornbill Customer Portal
    * **About Text**<br>The Customer Portal can be used to view and update requests.

* **Login Details**<br>
    * **Auto Login**<br>If you have SSO configured for the Customer Portal, setting this to `ON` will bypass the login screen and automatically log the customer into the portal.
    * **Splash Image**
    * **Show About Details**
    * **Show Footer**
    * **Terms and Conditions**

        |Option|Description|
        |-|-|
        |None|Terms and Conditions are not displayed on the Login screen|
        |Show|This will display the Terms and Conditions on the Login screen. When selected, a field is available to enter or edit the terms and conditions text|
        |Show and make mandatory|This will display the Terms and Conditions on the Login Screen. The customer must select the option, agreeing to these conditions before proceeding. When selected, a field is available to enter or edit the terms and conditions text|

## Translations

## Contact Access
The Contact Access list shows the contacts or Guest Accounts that have been associated with the Customer Portal and have been given permission to log in to the Customer Portal.

### Add Contact
Add an existing contact to the Customer Portal Account

* **Set Access**<br>Change the access a contact has to the Customer Portal
* **Remove Access**<br>Selecting this will remove the contact from the Customer Portal Account
* **Approved**<br>Set the contact to be approved for access to the Customer Portal. This is automatically set when a contact is manually added to the Customer Portal Account
* **Suspended**<br>Temporarily suspend a contact's access to the Customer Portal. A contact can be automatically set to suspended after multiple failed password attempts.

<!-- References -->
<!-- https://wiki.hornbill.com/index.php?title=Customer_Portal -->
<!-- https://wiki.hornbill.com/index.php?title=Customize_Customer_Portal -->
<!--  https://wiki.hornbill.com/index.php?title=Managing_Contact_Visibility_of_Organisation%27s_Requests_on_the_Customer_Portal 
<!-- https://wiki.hornbill.com/index.php?title=Customize_Customer_Portal -->

<!-- To Do -->
<!-- Unique email addresess -->
<!-- unathenticated Guests -->
<!-- auto register -->