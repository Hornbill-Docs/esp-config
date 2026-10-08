---
layout: article-toc
---
# Employee Portal Configuration

The Employee Portal is a highly configurable environment where you can add widgets and enable features for your employees to be able to access their services, communicate with the Service Desk, submit and view requests, chat with support staff, and access shared documents.

## Topics covered

* Basic configuration for the employee portal.
* How to enable the portal.
* Different company configurations.

## Accessing

* Open [Configuration](/esp-config/getting-started/using-configuration) and search for ***Employee Portal***

or

1. Open [Configuration](/esp-config/getting-started/using-configuration) and select `Platform Configuration`
1. In the navigation panel locate the section titled ***Customize***
1. Select `Employee Portal`

Each area of configuration is accessed using the options across the top of the page.

![Employee Portal Customization](/_books/esp-config/customize/employee-portal/images/customize-options.png)

## Page sections

The Employee Portal pages are split into three sections: header, body, and footer.

![Employee Portal Sections](/_books/esp-config/customize/employee-portal/images/header-body-footer.png)

### Header

* **Logo:** Add your company logo to the Employee Portal to give it some branding. Your logo will be displayed on the left side of the header. Adjust the size, background style, and color of your logo to fit in with the Header Background. The height can be between 80 and 200 pixels and the width between 80 and 300 pixels. It can be in any web image format, but PNG or SVG is recommended.
* **Background:** The Header Background can be configured to set the height and color, or to add a background image. The recommended size is 1024 x 300 pixels; however, the ideal size depends on factors such as whether the background is a pattern and what details are included in the design. It can be in any web image format, such as JPEG or PNG.
* **Text:** The color settings apply to the header text, which includes the Name, the Short Description of the page, and the list of different Service Domains that are displayed within the menu bar. The background color of the domain menu bar can also be set here. (The displayed text can be configured when [designing the Employee Portal](/esp-config/customize/employee-portal/employee-portal-design)).

::: tip
Images used for the logo and header background require a URL or link to an image that is stored in a location that is accessible by all users, such as a company web server or the [Hornbill Image Library](/esp-config/customize/image-library).
:::

### Body

* **Background:** Options to either set a background color or apply an image to the main body of the portal. The recommended image size is 1024 x 768 pixels; however, the ideal size depends on factors such as whether the background is a pattern and what details are included in the design. It can be in any web image format, such as JPEG or PNG.
* **Section:** Sets the default colors for the widgets that are added to the page.
* **Popup:** Sets the default colors for popup boxes.

### Footer

* **Style:** Set the color and font options to use within the page footer.
* **Social Information:** This section allows you to specify your social media accounts for Twitter, LinkedIn, YouTube, and Facebook. Only the account ID is needed; the links are created automatically. These are displayed with the appropriate social media logo. For any logo that you do not want to display, leave the account ID blank. If you would like to completely remove this section, deselect the checkbox next to the Social Information title.
* **Contact Information:** Add the contact details to let users know who to contact if they have questions about the page. Leave blank any field that you do not want to display. If you would like to completely remove this section, deselect the checkbox next to the Contact Information title.
* **About Details:** Add a bit of information for your users to describe this page. If you would like to completely remove this section, deselect the checkbox next to the About Details title.

::: tip
By deselecting all three checkboxes, you can completely remove the footer from the page.
:::

## Company

When a company is made up of several subsidiary companies, you can define this structure within the [Organization configuration](/esp-config/organizational-data/organization) using company groups.

Each defined company group can have its own Employee Portal settings applied to provide its unique branding.

At the top of the Header, Body, and Footer configuration sections, you can select the company to be configured.

![Company Customization](/_books/esp-config/customize/employee-portal/images/company-customization.png)

* **Primary Company:** This is the main configuration for the Employee Portal. It will also be used as a starting template for any company that is defined within the organization structure. Settings here will be automatically applied to all other companies unless a company has specified a different setting from the Primary Company.

::: tip
A new attribute called Home Organization has been added to the [User Account](/esp-config/organizational-data/user-accounts/about-user-accounts) which can be set on the Organizations tab for that user. Setting the Home Organization for a user will have them directed to the appropriately branded page for their company. When a Home Organization is not configured for a user, the Primary Company settings will be used. User imports can also be configured to automatically set the Home Organization.
:::

## Mobile

Hornbill provides a Progressive Web App (PWA) to give users a fast, UI-rich way of accessing the Employee Portal. The mobile app can be accessed by opening a browser on the mobile device and navigating to `mcatalog.hornbill.com/<Your_Instance>/`.

## Settings

Additional [Core Settings](/esp-config/advanced-tools-and-settings/core-settings) can be configured to further change how the Employee Portal functions and looks.

### Core Settings

|Setting|Description|Default Value|
|-|-|-|
|app.view.core.header.autoHideHeaderForBasicUsers|When set to `ON`, the Employee Portal header menu bar will be collapsed. A small tab is displayed at the top-center of the page which will expose the menu bar when hovered over. This only applies to basic users.|ON|
