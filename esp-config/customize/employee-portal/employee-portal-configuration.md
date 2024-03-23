---
layout: article-toc
---
# Employee Portal Configuration
The Employee Portal is a highly configurable environment where you can add widgets and enable features for your employees to be able to access their services, communicate with the Service Desk, submit and view requests, chat with support staff, and access shared documents.

## Topics covered
* Basic configuration for the employee portal
* How to enable the portal
* Different company configurations


## Accessing
* Open [Configuration](/esp-config/getting-started/using-configuration) and search for ***Employee Portal***

or

1. Open [Configuration](/esp-config/getting-started/using-configuration) and select `Platform Configuration`
1. In the navigation panel locate the section titled ***Customize***
1. Select `Employee Portal`

Each area of configuration is accessed using the options across the top of the page.

![Employee Portal Customization](_books/esp-config/customize/employee-portal/images/customize-options.png)

## Page sections
The Employee Portal pages are split into three sections: header, body, and footer.

![Employee Portal Sections](_books/esp-config/customize/employee-portal/images/header-body-footer.png)

### Header
* **Logo**<br>Add your company logo to the Employee Portal to give it some branding. Your logo will be displayed on the left side of the header. Adjust the size, background style, and color of your logo to fit in with the Header Background. The size depends on many factors but to give general an idea; The height can be between 80 and 200 pixels and the width between 80 and 300 pixels. It can be of any web format but PNG or SVG is recommended.
* **Background**<br>The Header Background can be configured to set the height and the color, or add a background image. The size depends on many factors like if the background is a pattern or if it has details, but to give general an idea; 1024 x 300 pixels. It can be of any web format such as JPEG or PNG
* **Text**<br>The Text on this page includes the main title of the page and the list of different Service Domains which are displayed within the menu bar.

::: tip
Images used for the logo and header background require a URL or link to an image that is stored in a location that is accessible by all users, such as a company web server or the Hornbill Image Library.
:::

### Body
* **Background**<br>Options to either set a background or apply an image to the main body of the portal. The size depends on many factors like if the background is a pattern or if it has details, but to give general an idea; 1024 x 768 pixels. It can be of any web format such as JPEG or PNG.
* **Section**<br>Sets the default colors for the widgets that are added to the page
* **Popup**<br>Sets the default colors for popup boxes

### Footer
* **Style**<br>Set the color and font options to use within the page footer
* **Social Information**<br>This section allows you to specify your social media accounts Twitter, LinkedIn, YouTube, and Facebook. Only the account ID is needed. We'll take care of the links. These are displayed with the appropriate social media logo. Any logo that you do not want to display, leave the account name blank. If you would like to completely remove this section, deselect the checkbox next to the Social Information title.
* **Contact Information**<br>Add the contact details to let you users know who to contact if they have questions about the page. Any field that you do not want to display, leave blank. If you would like to completely remove this section, deselect the checkbox next to the Contact Information title.
* **About Details**<br>Add a bit of information for your users to describe this page. If you would like to completely remove this section, deselect the checkbox next to the About Details title.

::: tip
By deselecting all three checkboxes, you can completely remove the footer from the page.
:::

## Company
When a company is made up from of a number of subsidiary companies, you are able to define this structure within the [Organization configuration](/esp-config/organizational-data/organization) using company groups. 


Each defined company group can have its own settings applied in order to provide there own unique branding. On the top of the settings form, you can select one of the available companies that you have defined in Hornbill.

* **Primary Company**<br>This is the main configuration for the Employee Portal. It will also be used as a template for any Company that is defined within the organization structure. Settings here will be automatically applied to all other companies unless a company has specified a different setting from the Primary Company.

::: tip
A new attribute called Home Organization has been added to the User Account which can be set on the Organizations tab for that user. Setting the Home Organization for a user will have them directed to the appropriately branded page for their company. When a Home Organization is not configured for a user, the Primary Company settings will be used. User imports can also be changed to automatically set the home organization
:::

## Settings
These setting can plan a key role in how you first introduce the Employee Portal to your users. Make sure you are familiar with these settings and when to use them.
* **Users to preview the Employee Portal**<br>This is an important first step to setting up your Employee Portal. This setting allows you to add a list of comma-separated user names of people you want to have access to the Employee Portal. This gives you the opportunity to have one or more people to test and feedback on the Employee Portal design before you open it up to all users. Changing this setting will also be one of your last steps. Once you have completed your configuration and you are ready to make it available to all users, simply remove these names. Once the list of names is empty, it becomes available to everyone.
* **Enable Employee Portal**<br>Turning this setting to On will make a new navigation menu item `My Company` available in the Home menu on the main Hornbill web app. If you have provided one or more names in the previous setting, only those users will see the menu item.

