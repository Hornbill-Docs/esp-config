---
layout: article-toc
---
# Employee Portal Design
The main Employee Portal page and the pages associated with each domain offer a wide variety of widgets and configurations that allow you to build the perfect experience for your users.

## Roles and Rights
The configuration of each page within the Employee Portal can be governed by granting users specific roles or ownership.

* **User Role**<br>This role includes the application right CanManagePage. This right grants the general ability to manage pages. This will be required for Service Domain Owners who will have the ability to create and manage a Service Domain page.
* **Home Page Manager Role**<br>This Role grants the rights to manage the main Company Home Page. It includes the application rights CanManagePage and canManageCompanyPages.
* **Domain Owner**<br>A user who is configured as the owner of a domain will have the rights to add, edit and remove Domain Pages for that domain.

## Design Mode
A user who has the Home Page Manager role or has been added as the owner of a Service Domain will have a Cog button available within the header of the page. Clicking on this cog will take the user into the Design Mode for that page. Once in Design Mode, the following information is displayed.

![Design Mode](/_books/esp-config/images/employee-portal-design-mode.png)

* **Exit Design Mode**. Clicking this option will return you to the originating page.
* **Domains**. This drop-down option will display a list of all the [service domains](/esp-config/customize/service-domains) that have been created. Selecting a domain will open the configuration for that domain in the right-hand sidebar. From here you can choose to either design the page or add a redirect to another URL.
* **Status**
    * **Draft**. Changes have been made to the page but, are not yet published. These changes will not be visible to users until published
    * **Published**. All changes made to the page have been saved and published.
* **Visibility**. A page can be made visible to different types of users. Basic Users, Users, or All Users. This shows the current visibility version that is being viewed.
    
## Page Details
Once in Design Mode the Page Details configuration box is made available on the right hand pop-out panel.

### Edit Page Details
* **Name**<br>This is the main title in the header of the page. If this is left blank, the user is presented with a friendly greeting in its place.
This field will accept User Variables
* **Short Description**<br>This will be displayed in a small font, under the page name.
This field will accept User Variables
* **User Visibility Versions**<br>A single page can have different configurations based on the types of users accessing the page. The [available widgets](/esp-config/customize/employee-portal/employee-portal-design#add-widgets) for a page will vary, depending on if they were designed to be seen or used by **All Users**, **Basic Users**, or **Full Users**.  
    * **Current user visibility versions**<br>These are the currently used visibility versions for this page. Selecting a version from this list will switch to the design mode to this selected version.
    * **Add new user visibility version**<br>Add a user visibility version to the list of Current user visibility versions
    * **Remove this user visibility version**<br>This removes all the configuration for the currently selected version.
    * **Revert to Published Version**<br>If you have made a number of changes and you would like to revert back to the published version, selecting this will clear the current draft version.

    ::: tip
    If All Users is one of your selected visibility versions, this will supersede both User and Basic User versions.
    :::

### User Variables
Some fields such as Page Name and Short Description allow using variables with data from the current user.

For example: Hello {{user.firstName}}

Will display as: Hello John

These are the available variables:

* user.firstName
* user.middleName
* user.lastName
* user.userId
* user.email
* user.handle
* user.jobTitle
And these needs to be wrapped in double curly braces {{ }}.

## Add Widgets
* **Available Widgets**<br>This displays a list of available widgets for the currently selected application. From this section you can use your mouse to drag and drop the widget to the Page Widgets section to add the widget to the current page.
* **Application Selector**<br>Select each application to see the widgets that they offer.

    :::important
    The list of available widgets will vary, depending on the [User Visibility Version](/esp-config/customize/employee-portal/employee-portal-design#edit-page-details) that the page has been set to.  (Please refer to the documentation for each widget to determine the compatible User Visibility Version.)
    :::

## Page Widgets
This lists the widgets that have aready been added to the page.  From here, each widget can be configured, sized, and if needed hidden by using the displayed options when hovering over each widget.

### Hide Widget
Use the eye icon to decide if the widget should be visible on the page. This feature is useful if you are editing your page and you don't want to delete and remove a widget from the page, but you also don't want it visible.

### Edit Widgets
* **Configure**<br>Each widget will include a number of options to set the information that will be displayed. These will vary from widget to widget.
* **Style**<br>Configure the margins, colors, and background. Some colors may default to the settings in the Page Body
* **Widget Width**<br>The body of each page is divided into four columns. Each widget can be set to span across one or more of these columns. Reducing the width will allow for more than one widget to be displayed in a row.