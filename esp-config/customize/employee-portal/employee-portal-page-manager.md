# Employee Portal Page Manager
A dedicated view to manage pages on the employee portal. View and manage pages for domains you manage, as well as view the entire employee portal page structure even if pages are managed by others. Manage widgets and redirect pages, as well as add and manage child pages as needed.

## Roles and Rights
The configuration of each page within the Employee Portal can be governed by granting users specific roles.

* **Collaboration Role**. This role has been updated to include the application right CanManagePage. This right grants the general ability to manage pages. This will be required for Service Domain Owners who will have the ability to create and manage a Service Domain page. In the future, this right will also give any collaboration user the ability create and manage a personal page. Basic Users will not have this ability.
* **Home Page Manager**. This Role grants the rights to manage the main Company Home Page. It includes the application rights CanManagePage and canManageCompanyPages
* **Domain Owner**. Whilst not strictly a role, a user who is configured to own a domain will have the rights to add, edit and remove Domain Pages for Domains they are an owner of, on the Employee Portal.


## Navigation
By default, you will see only the pages (or subpages) of domains that you have the right to manage.

The All Pages button allows you to view all the pages and subpages that exist in the employee portal (even if you don't have the rights to manage them).

To return to only viewing the pages you can manage, click the All Pages button again.

The pages of the employee portal are presented in a tree format.

### Catalog
This will show a list of domains that have a page and or sub-pages defined against them
* A domain page or a child of a domain page can be either a configurable page, or simply a redirect to a specific service.
* If a page is simply a redirect to a specific service, the URL to the specific service will be shown.

### Not defined yet
A list of enabled domains, which do not currently have a page or redirect defined against them.

Clicking on a domain will present a pop-up, which can be used to create a page.
* Provide the page name
* Optional short description
* Decide what the first version of the page will be
    * All users - Has priority over Users and Basic Users versions
    * Users - Only visible to users of type User
    * Basic - Only visible to users of type Basic
* Clicking Create Page will create the page and allow for it to be configured or defined as a redirect only and the URL for the redirect added. The page will not be visible to its intended audience until it is published.

## Page Management
Firstly, select the page you wish to manage from the tree on the left by clicking on it. All pages in the tree menu include a link icon, which will take you to the specific page / redirect on the employee portal

## Domain Page Options
* **Current Status**. Shows the status of the page, whether it is published or in draft and not visible to the extended audience.
* **User Visibility**. This shows you a drop-down of the configured and or available versions of the page which can be configured. This also allows you to view which version of the page you are managing and editing. Swap the drop-down to the version of the page you want to manage, and or use the drop down to add another available version of the page.
If a version of the page is no longer needed, use the delete icon to permanently remove the version of the page.
* **Design Widgets**. This option will take you into the widget designer/page details
* **Edit**. This will allow you to edit the details of the page.
    * Language version.
    * User version.
    * Page name and short description for the chosen user version and language.
In order to publish any changes, first save the changes and then use the Publish button.
* **Add a Child Page**. Use this option to create a child page from the domain page.
    * Selecting this choice will allow you to follow the steps for creating a child page
    * Name, Short Description, Slug - this will be the URL of the child page, which is prefixed with the path of the parent page and a definable end point (by default, the name of the child page, but this can be set as needed). Set the first user visibility level for the child page. 
    * A child page works like any other type of domain page, and can be configured by designing the required widgets and then publishing when ready.
    * Child pages can also have its own child pages by repeating the process above from a child page in the page navigation on the right.
    * Links to child pages will not automatically appear on the parent page, so as a designer of the page, if links are needed from a parent to a child page and vice versa, these will need to be added via link widgets on the appropriate pages.
* **Delete**. Use this option to permanently delete a page.