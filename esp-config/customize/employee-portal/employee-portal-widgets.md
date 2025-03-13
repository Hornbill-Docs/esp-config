---
layout: article-toc
keywords: static content
---
# Employee Portal Widgets
Widgets are small, standalone applications that can be embedded into the employee portal pages to add interactivity or additional features. Widgets enhance the usability and provide quick access to information.

## General Widgets
### My Services
Add this widget to present users with a list of Services that they are subscribed to.

#### Configure
* **Filter By Service Domain**<br>Selecting this option will display a list of the available Domains. Once a Domain is selected, the list of services will be limited to that Domain.
* **Show Impacted Only**<br>Only subscribed services that are currently impacted will be displayed.
* **Show Favorites Only**<br>Only Services that have been marked as a favorite by the user will be displayed.
* **Automatically Select the Layout**<br>The layout of this widget will adapt automatically based on the space it has. It will switch between a tiled view and a list view depending on how many services there are to display and the number of columns it spans.
* **Display Layout as Tiles**<br>Displays the services as tiles with large icons.
* **Show Service Request Items**<br>Below each Service, display a list of its Request Catalog Items. Only available when not using tiles.

#### Style
* **Hide if no data is available**<br>The widget will not be included on the page if there is nothing to display.
* **Header**<br>Define the top banner of the widget.
* **Header Type**<br>Choose from Basic, Custom, or No Banner.
* **Body**<br>Configure the text and background colors of the widget. If no specific color preferences are set in the widget configuration, the style defined in the Employee Portal settings is applied.

### Bulletins
Add this widget to present Bulletins that have been published through their subscribed services.

#### Configure
* **Filter By Service Domain**<br>Selecting this option will display a list of the available Domains. Only Bulletins associated to the selected Domain will be displayed.
* **Transition Time**<br>Set how long each Bulletin will be displayed for.

#### Style
* **Hide if no data is available**<br>The widget will not be included on the page if there is nothing to display.
* **Header**<br>Define the top banner of the widget
* **Header Type**<br>Choose from Basic, Custom, or No Banner.
* **Body**<br>Configure the text and background colors of the widget. If no specific color preferences are set in the widget configuration, the style defined in the Employee Portal settings is applied.

### Links
Add this widget to create a list of custom links. Links to external web sites, cloud services, intranet, and other Employee Portal Pages.

#### Configure
* **Display as Tiles**<br>Selecting options lets you toggle between a list view and a tile view.
* **Icon**<br>Select an icon to accompany the name of the link.
* **Address**<br>Specify an address for the link - if referencing a Hornbill link which needs to be accessible from the Employee Portal or the Employee Mobile App, ensure to use the relative path in this field. For example, for an Intelligent Capture link `catalog/new-service-request/com.hornbill.servicemanager/1/1/` (where `1/1/` is replaced with the service ID and progressive capture ID.)
* **Image**<br>Use an image to represent the link.
* **Name**<br>Add a name for your link.
* **Description**<br>Add a description to display if you want a little more detail about the link.

#### Style
* **Header**<br>Define the top banner of the widget.
* **Header Type**<br>Choose from Basic, Custom, or No Banner.
* **Body**<br>Configure the text and background colors of the widget. If no specific color preferences are set in the widget configuration, the style defined in the Employee Portal settings is applied.

### Activities
Add this widget to give the user a list of their current activities that are assigned to them.

#### Configure
* **Show Activities**<br>Include Activities that are assigned to the user.
* **Show Authorizations**<br>Include authorizations assigned to the user.

#### Style
* **Header**<br>Define the top banner of the widget.
* **Header Type**<br>Choose from Basic, Custom, or No Banner.
* **Body**<br>Configure the text and background colors of the widget. If no specific color preferences are set in the widget configuration, the style defined in the Employee Portal settings is applied.
* **Information**<br>This widget should only be used on pages that are accessible to full users. Basic users will not have access to activities. Add to User Version pages only. It is also not available on the Mobile app.

### Recently Viewed
Add this widget to give users a way to quickly access Hornbill workspaces, apps, requests, projects, and more which they have recently viewed.

#### Style
* **Header**<br>Define the top banner of the widget
* **Header Type**<br>Choose from Basic, Custom, or No Banner.
* **Body**<br>Configure the text and background colors of the widget. If no specific color preferences are set in the widget configuration, the style defined in the Employee Portal settings is applied.

### Text
Add this widget to create a simple text based message board.

#### Configure
* **Title**<br>Add a main title within the text area.
* **Description**<br>Add the main content that you want to display. Format your text using Wiki Markup.
* **Text Centered**<br>Centers the Title within the widget.

#### Style
* **Header**<br>Define the top banner of the widget
* **Header Type**<br>Choose from Basic, Custom, or No Banner.
* **Body**<br>Configure the text and background colors of the widget. If no specific color preferences are set in the widget configuration, the style defined in the Employee Portal settings is applied.

### External Frame
The external frame, often referred to as an iframe, is used to embed content from an external web page into the Employee Portal. This can be used to display content from external sources, such as videos, maps, or entire web pages.

:::note
Not all web pages can be embedded into an iframe.  Tools are available on the internet to test if a URL is compatible with iframes before adding to the External Frame widget.
:::

#### Configure
* **URL**. Enter the URL of the web page that will be displayed in the widget.
* **Preferred Height**.  Set the number of pixels for the height of the widget.  Leave this blank to have it automatically adjust to an appropriate height.

## Service Manager Widgets
These widgets are available only when Service Manager is installed.  

### Search
The Search widget provides a unified search for users to find information on services, FAQs, service requests, known issues, the user's active requests, and knowledge articles.

![Search Widget](/_books/esp-config/customize/employee-portal/images/search-widget.png)

#### Configure
* **Filter by Service Domain**. Select a single service domain that the search will apply to.  
* **Filter by Types**. The search can be limited to only searching selected types of records.
    * Service
    * FAQ
    * Service Request
    * Known Issues
    * My Service Requests
    * Articles

### Knowledge Base Articles
This widget presents a list of knowledge base articles that are available to the user. A search and knowledge base filter allows the user to find a particular article. The search is based on the article's name.  Clicking on an article in the list will open the full article in the Knowledge Browser. 

![Knowledge Article Widget](/_books/esp-config/customize/employee-portal/images/knowledge-article-widget.png)

#### Configure
* **Knowledge Bases**. A list of selectable knowledges allows you to select which knowledge bases will be included when searched.
* **Knowledge Base Article Types**.  A list of selectable knowledge types can be used to control the types of knowledge articles that will be searched.

<!-- 
### RSS Feed


### Workspace
Add this widget to display the user's News Feed which shows the latest updates to all the workspaces that they follow. Or select a specific Workspace.

#### Configure
* **Show News Feed**<br>When selected, the widget will show the users News Feed. When not selected, you can select an individual workspace that you wish to show.

#### Style
* **Header**<br>Define the top banner of the widget
* **Header Type**<br>Choose from Basic, Custom, or No Banner.
* **Body**<br>Configure the text and background colors of the widget. If no specific color preferences are set in the widget configuration, the style defined in the Employee Portal settings is applied.

### Post
Add this widget to display a particular post or the last post from a selected workspace.

#### Configure
* **Show specific post**<br>If you have an important post that you want to always be displayed you can select this option and specify the ID of the post.
* **Post ID**<br>Add the ID of the post you would like to display. To get the post's ID you can do a right mouse-click on the timestamp (eg: 1 day ago) displayed on a post and get a copy of the link. Add this to the post ID field, removing the leading domain name, up to the URN.
* **Last post in a workspace**<br>This will only display the last post in the selected workspace. There is no option to scroll through previous posts.
* **Public Workspace**<br>Select the public workspace that you which to use.

#### Style
* **Header**<br>Define the top banner of the widget
* **Header Type**<br>Choose from Basic, Custom, or No Banner.
* **Body**<br>Configure the text and background colors of the widget. If no specific color preferences are set in the widget configuration, the style defined in the Employee Portal settings is applied.

### Search
Add this widget to present users with a Search box for finding Services, FAQs, Documents, Requests, and more.

#### Configure
* **Filter By Service Domain**<br>Selecting this option will display a list of the available Domains. Once a Domain is selected, the results will only come from information linked to that Domain.
* **Title**<br>Add a title which will be displayed to the user at the top of the widget.
* **Place Holder**<br>Add some text that will be displayed within the Search box.
* **Text Centered**<br>Centers the Title within the widget.

#### Style
* **Header**<br>Define the top banner of the widget
* **Header Type**<br>Choose from Basic, Custom, or No Banner.
* **Body**<br>Configure the text and background colors of the widget. If no specific color preferences are set in the widget configuration, the style defined in the Employee Portal settings is applied.

### My Team
Add this widget to view members of all or a specific organizational grouping, and where applicable their availability status. The default will show a user all other members of any teams, departments or companies they are members of.

#### Configure
* **Use a Specific Group**<br>Filter the widget to show only members of page viewers chosen group type - Team, Department, Company.
* **Exclude yourself**<br>Choose to exclude yourself from the member list.
* **Show availability and online status**<br>Choose if the widget should show member availability status and online presence indicator.
* **Show overall availability**<br>Add a title summary, which shows a count of available members in the group.
* **Show minimal layout**<br>Choose to hide member image, job title and replace availability status and presence with color indicator, icon and hover over options to maximize space.

#### Style
* **Header**<br>Define the top banner of the widget
* **Header Type**<br>Choose from Basic, Custom, or No Banner.
* **Body**<br>Configure the text and background colors of the widget. If no specific color preferences are set in the widget configuration, the style defined in the Employee Portal settings is applied.
-->