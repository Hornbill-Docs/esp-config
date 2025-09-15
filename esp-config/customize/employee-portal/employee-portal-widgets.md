---
layout: article-toc
keywords: static content
---
<!--
**Visible to all users**
My Services
Bulletins
Links
Recently Viewed
Text
External Frame
RSS Feed
Search
**Knowledge Base Articles**
**HR Search**
**HR Links**
**Most Popular**
**Quick Links**
**Announcements**
**My Requests**

**Visible to basic users**
My Services
Bulletins
Links
Recently Viewed
Text
External Frame
RSS Feed
Search

**Visible to full users**
My Services
Bulletins
Links
**Activities**
Recently Viewed
**Workspace**
**Post**
Text
**My Team**
External Frame
RSS Feed

-->

# General Widgets
Widgets are small, stand-alone applets that can be embedded into the Employee Portal pages to add interactivity and additional features. Widgets enhance the usability and provide quick access to information.

![General Widgets](/_books/esp-config/images/employee-portal-general-widgets.png)

The **General** widgets are provided with the Hornbill platform. Each installed application can provide additional widgets. For more information on these widgets, see the application-specific documentation.

<!-- JAMES: Cammy added the note below-->
::: note
Some widgets are only available to *Users* (i.e. full users). If you have the page's visibility set to *All Users*, then only  widgets that *all* users can see are shown. Widgets that do not provide visibility to basic users are excluded. These widgets include Activities and My Team, among others.
:::

<!-- JAMES: Cammy added the subheading links below-->
This article provides reference information on the following widgets:
* [My Services](/esp-config/customize/employee-portal/employee-portal-widgets#my-services)
* [Bulletins](/esp-config/customize/employee-portal/employee-portal-widgets#bulletins)
* [Links](/esp-config/customize/employee-portal/employee-portal-widgets#links)
* [Activities](/esp-config/customize/employee-portal/employee-portal-widgets#activities)
* [Recently Viewed](/esp-config/customize/employee-portal/employee-portal-widgets#recently-viewed)
* [Text](/esp-config/customize/employee-portal/employee-portal-widgets#text)
* [External Frame](/esp-config/customize/employee-portal/employee-portal-widgets#external-frame)
* [RSS Feed](/esp-config/customize/employee-portal/employee-portal-widgets#rss-feed)
* [Workspace](/esp-config/customize/employee-portal/employee-portal-widgets#workspace)
* [Post](/esp-config/customize/employee-portal/employee-portal-widgets#post)
* [My Team](/esp-config/customize/employee-portal/employee-portal-widgets#my-team)

## My Services
Add this widget to present users with a list of services that they are subscribed to. Each sevice can be clicked on to show the details of the service.
<!-- JAMES: Cammy added the visibility info below. Please check this for all widgets.-->
![My Services Widget](/_books/esp-config/images/services-widget.png)

**[User visibility versions](/esp-config/customize/employee-portal/employee-portal-design#edit-page-details):** All Users, Basic Users, Full Users.

### Configure
* **Items per page.**
* **Filter by service domain.** This option displays a list of the available domains. Once a domain is selected, the list of services is limited to that domain.
* **Include services without domain.** 
* **Show impacted only.** This option displays only subscribed services that are currently impacted.
* **Show impacted indicator only.** 
* **Show favorites only.** Only services that have been marked as a favorite by the user are displayed.
* **Automatically select the layout.** The layout of this widget will adapt automatically based on the space it has. It will switch between a tiled view and a list view depending on how many services there are to display and the number of columns it spans.
* **Display layout as tiles.** Displays the services as tiles with large icons.
* **Show Service Request Items.** Below each service, display a list of its request catalog Items. Only available when not using tiles.
* **Align to the center.**
* **Service icon color.**

### Style
* **Use content height.**
* **Hide if no data is available.** This option hides the widget from the page if there is nothing to display.
* **Header.** Define the top banner of the widget.
    * **Header Type.** Choose from Basic, Custom, or No Header.
* **Body.** Configure the text and background colors of the widget. If no specific color preferences are set in the widget configuration, the style defined in the Employee Portal settings is applied.

## Bulletins
Add this widget to present bulletins that have been published through the logged on user's subscribed services. This widget is a slide deck that works its way through all of the available bulletins.

![Bulletins Widget](/_books/esp-config/images/employee-portal-bulletin-widget.png)

**Visibility:** basic users, full users

### Configure
* **Filter By Service Domain.** This option displays a list of the available domains. Only bulletins associated to the selected domain are displayed.
* **Transition Time.** Set how long each bulletin will be displayed for.
* **Hide Link to Service.**
* **Set Height.**

### Style
* **Use Content Height.**
* **Hide if no data is available** This option hides the widget from the page if there is nothing to display.
* **Header.** Define the top banner of the widget.
    * **Header Type.** Choose from Basic, Custom, or No Header.
    * **Label.**
    * **Link.**
* **Body.** Configure the text and background colors of the widget. If no specific color preferences are set in the widget configuration, the style defined in the Employee Portal settings is applied.

## Links
Add this widget to create a list of custom links. Links to external web sites, cloud services, intranet, and other Employee Portal pages.

**Visibility:** basic users, full users

### Configure
* **Display as Tiles.** This options lets you toggle between a list view and a tile view.
* **Add Link.**
    * **Address.** Specify an address for the link. If referencing a Hornbill link that needs to be accessible from the Employee Portal or the Employee mobile app, make sure to use the relative path in this field. For example, for an Intelligent Capture link `catalog/new-service-request/com.hornbill.servicemanager/1/1/` (where `1/1/` is replaced with the service ID and Intelligent Capture ID.)
    * **Image, Icon, None.** Select an image or icon to accompany the name of the link, or select **None**.
    * **Name.** Add a name for the link.
    * **Description.** Add a description to display if you want to provide more detail about the link.
    * **Text Color.**
    * **Background Color.**
    * **Use Border.**
    * **Add Padding.**
    * **Visibility.**

### Style
* **Use Content Height.**
* **Hide if no data is available** This option hides the widget from the page if there is nothing to display.
* **Header.** Define the top banner of the widget.
    * **Header Type.** Choose from Basic, Custom, or No Header.
    * **Label.**
    * **Link.**
* **Body.** Configure the text and background colors of the widget. If no specific color preferences are set in the widget configuration, the style defined in the Employee Portal settings is applied.

## Activities
Add this widget to give the user a list of the activities and approvals currently assigned to them.

![Activities Widget](/_books/esp-config/images/employee-portal-activity-widget.png)

**Visibility:** full only
::: note
This widget should only be used on pages that are accessible to full users. Basic users do not have access to activities. This widget is also not available on the mobile app.
:::

### Configure
* **Show Activities.** Select this option to include activities that are assigned to the user.
* **Show Approvals.** Select this option to include approvals (authorizations) assigned to the user.
* **Show Overdue Activities/Approvals.** Show both activities and approvals that have passed their due date. These will be displayed in a column called Overdue.
* **Show Future Activities/Approvals.** Show activities and approvals that have a due date that is more than two days away.  These will be displayed in a column called Later.
* **Show No Due Date (Someday).** Show activities that don't have a due date. These will be displayed in a column called Someday.
* **Maximum items per list.** This setting will help control the layout within the Employee Portal and display a set number of activities per list. A `More` button will be displayed when the number of activities exceeds this value. Clicking on the `More` button will open the [My Activities](/esp-user-guide/my-activities/overview) view. 

### Style
* **Use Content Height.**
* **Header.** Define the top banner of the widget.
    * **Header Type.** Choose from Basic, Custom, or No Header.
    * **Label.**
    * **Link.**
* **Body.** Configure the text and background colors of the widget. If no specific color preferences are set in the widget configuration, the style defined in the Employee Portal settings is applied.

## Recently Viewed
Add this widget to give users a way to quickly access Hornbill workspaces, apps, requests, projects, and other items they have recently viewed.

**Visibility:** basic users, full users

### Style
* **Use Content Height.**
* **Hide if no data is available** This option hides the widget from the page if there is nothing to display.
* **Header.** Define the top banner of the widget.
    * **Header Type.** Choose from Basic, Custom, or No Header.
    * **Label.**
    * **Link.**
* **Body.** Configure the text and background colors of the widget. If no specific color preferences are set in the widget configuration, the style defined in the Employee Portal settings is applied.

## Text
Add this widget to create a simple text based message board.

**Visibility:** basic users, full users

### Configure
* **Title.** Add a main title within the text area.
* **Description.** Add the main content that you want to display. Format your text using wiki markup.
* **Text Centered.** Centers the title within the widget.

### Style
* **Use Content Height.**
* **Header.** Define the top banner of the widget.
    * **Header Type.** Choose from Basic, Custom, or No Header.
    * **Label.**
    * **Link.**
* **Body.** Configure the text and background colors of the widget. If no specific color preferences are set in the widget configuration, the style defined in the Employee Portal settings is applied.

## External Frame
The external frame, often referred to as an iframe, is used to embed content from an external web page into the Employee Portal. This can be used to display content --- such as videos, maps, or entire web pages --- from external sources

:::note
Not all web pages can be embedded into an iframe.  Tools are available on the Internet to test if a URL is compatible with iframes before adding to the External Frame widget.
:::

**Visibility:** basic users, full users

### Configure
* **URL.** Enter the URL of the web page to display in the widget.
* **Preferred Height.**  Set the number of pixels for the height of the widget.  Leave this blank to have it automatically adjust to an appropriate height.

### Style
* **Use Content Height.**
* **Header.** Define the top banner of the widget.
    * **Header Type.** Choose from Basic, Custom, or No Header.
    * **Label.**
    * **Link.**
* **Body.** Configure the text and background colors of the widget. If no specific color preferences are set in the widget configuration, the style defined in the Employee Portal settings is applied.

## RSS Feed
<!-- JAMES: I added this one.-->
**Visibility:** basic users, full users

### Configure
* **URL.** Enter the URL of the RSS feed to display in the widget.
* **Display Header.**

### Style
* **Use Content Height.**
* **Hide if no data is available** This option hides the widget from the page if there is nothing to display.
* **Header.** Define the top banner of the widget.
    * **Header Type.** Choose from Basic, Custom, or No Header.
    * **Label.**
    * **Link.**
* **Body.** Configure the text and background colors of the widget. If no specific color preferences are set in the widget configuration, the style defined in the Employee Portal settings is applied.

## Workspace
Add this widget to display the user's News Feed which shows the latest updates to all the workspaces that they follow. Or select a specific Workspace.

**Visibility:** full users only

### Configure
* **Show News Feed.** This option lets you show the users news feed. When not selected, you can select an individual workspace to show instead.

### Style
* **Use Content Height.**
* **Hide if no data is available** This option hides the widget from the page if there is nothing to display.
* **Header.** Define the top banner of the widget.
    * **Header Type.** Choose from Basic, Custom, or No Header.
    * **Label.**
    * **Link.**
* **Body.** Configure the text and background colors of the widget. If no specific color preferences are set in the widget configuration, the style defined in the Employee Portal settings is applied.

## Post
Add this widget to display a particular post or the last post from a selected workspace.

**Visibility:** full users only

### Configure
* **Show specific post.** If you have an important post that you want to always be displayed, select this option and specify the ID of the post.
* **Last post in a workspace.** This option displays only the last post in the selected workspace. There is no option to scroll through previous posts.
* **Post ID.** Add the activity ID of the post you would like to display. To get the post's ID, right-click on the timestamp (e.g.: *1 day ago*) displayed on a post and get a copy of the link. Add this to the Post ID field, removing the leading domain name, up to the URN.
* **Public Workspace.** Select the public workspace you want to use.

### Style
* **Use Content Height.**
* **Header.** Define the top banner of the widget.
    * **Header Type.** Choose from Basic, Custom, or No Header.
    * **Label.**
    * **Link.**
* **Body.** Configure the text and background colors of the widget. If no specific color preferences are set in the widget configuration, the style defined in the Employee Portal settings is applied.

## My Team
Add this widget to view members of all or a specific organizational grouping, and where applicable their availability status. The default shows a user all other members of any teams, departments, or companies they are members of.

**Visibility:** full users only

### Configure
* **Use a specific group.** This option filters the widget to show only members of the page viewer's chosen group type (Team, Department, Company).
* **Exclude myself.** Choose to exclude yourself from the member list.
* **Show availability and online status.** Choose if the widget should show member availability status and online presence.
* **Show overall availability.** Add a title summary, which shows a count of available members in the group.
* **Show minimal layout.** Choose to hide member image and job title, and replace availability status and online presence with a color indicator, icon, and hover-over options to maximize space.
* **Refresh automatically to get status updates.**

### Style
* **Use Content Height.**
* **Hide if no data is available** This option hides the widget from the page if there is nothing to display.
* **Header.** Define the top banner of the widget.
    * **Header Type.** Choose from Basic, Custom, or No Header.
    * **Label.**
    * **Link.**
* **Body.** Configure the text and background colors of the widget. If no specific color preferences are set in the widget configuration, the style defined in the Employee Portal settings is applied.