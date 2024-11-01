---
layout: article-toc
---
# Dashboards
Dashboards are used to display widget content. You can:

* Customize dashboards to include multiple rows and columns, then add widgets to them.
* Shared dashboards with specific users and roles.
* Display dashboards on large screens or in slideshows.

## Topics covered
* [Creating a dashboard](/advanced-analytics/dashboards#creating-a-dashboard)
* [Defining dashboard layouts](/advanced-analytics/dashboards#defining-dashboard-layouts)
* []
* [About performance of dashboards](/advanced-analytics/dashboards#about-performance-of-dashboards)

## Creating a dashboard
Administrators can configure dashboards in Configuration.

**To access Dashboard Configuration:**
1. Select the **Configuration** cog at the bottom of the left-hand application menu bar.
1. In Configuration, from the navigation dropdown, select **Platform Configuration**.
1. In the navigation panel, scroll to locate the *Advanced Analytics* section.
1. Click **Dashboards**.

**To create a dashboard:**
1. In the Dashboards landing page, click **+ Create New Dashboard**.
1. Click the edit button (**Enter dashboard design mode**).
1. Click the **Dashboard Properties** button and in Dashboard Properties, give the dashboard a name.
1. Click **Save**.

## Defining dashboard layouts
You can add additional rows and columns, and add widgets.

**To add additional rows to the layout:**
1. In design mode, click the + button in the top left of the row you want to add a new row directly below.
1. For more rows, repeat.
1. Any time you have multiple rows, use the Percentage Height fields to ensure that each row is set to an equal height value and that the total of all the row heights equals 100%.

**To add columns to a row:**
1. In design mode, click the **Add Column** button from the top right of the row.
1. For more columns, repeat.
1. Any time you have multiple columns, use the Percentage Width fields to ensure that each column is set to an equal width value and that the total of all the column widths on a single row equals 100%.

## Adding widgets to dashboard columns
Before you can add a widget to a column on a row, there are two options that need to be configured:

* **Type of Widget.** This will be a dropdown of all available Widget types (Chart, Scorecard, Target Counter, Itemized Count List, Custom), select the type of Widget you wish to add.
* **Widget.** Based on the type of widget chosen above, a list of defined widgets of that type will be displayed and can be chosen from (Only widgets marked as 'Available for Use' will appear in the list.)

**To add widgets to columns:**

* The chosen widget will then appear in the column. If the wrong widget has been chosen, click the delete button on the widget (not the one on the column header) to remove the widget and allow for another widget to be selected.

**To add multiple widgets to a single column on a row:**
1. On the column, click the Charts button. on the column, this will add an additional widget to the row. Multiple widgets can be added to a single column.
* Configure the content of each widget in the row, as directed in the Adding Widgets to Column section above.
    * Remove widgets from a column by selecting the Dustbin button in the top right hand corner of widgets you wish to remove.

#### Row and column heights and widths
* Ensure that the total of all row heights equals 100% in order to correctly display on the Dashboard.
* Ensure that the total of all columns widths per row equals 100% in order to correctly display on the Dashboard.

**To move columns between rows:**
1. Move columns of widgets between rows by dragging and dropping the columns as required.
1. Ensure that the total width of all the columns on each row equals 100% to display correctly.

## Managing Dashboard Settings
Once the Dashboard layout, and widget content is configured it is important to complete the Dashboard Settings .

* **Title.** Name of the dashboard.
* **Description.** Describe the dashboard's purpose and or its content.
* **Status.** By default, this is set to *In development*. Once the dashboard is configured, change the status to *Available for use*. Only dashboards marked as *Available for use* will appear when configuring the content of slides in slideshows.
* **Access Granted To.** You can grant access ti the dashboard to multiple users and roles. Add additional users and roles by using the Add New option. Switch the context between user and role by clicking on the User / Role header and then selecting the user or role accordingly.
* **Save.** Click this to save the dashboard.
* **Copy.** Create a copy of the dashboard layout, select the **Save As** option from the dropdown next to the **Save** button, then give the new dashboard a name.

## About performance of dashboards
Dashboards are complementary to reports; they are not replacements for reports. Dashboards provide real-time insights and a visual representation of data that can be easily interpreted at a glance. However, it is important to note that an excessive number of widgets on a dashboard can sometimes lead to performance issues, particularly when dealing with complex queries or large datasets.

If you find that your dashboard is experiencing performance issues, Hornbill offers assistance in optimizing your dashboard to improve its efficiency. This may involve streamlining the layout, reducing the number of widgets, or fine-tuning the queries to ensure smoother operation.

In some cases, it may be necessary to explore alternative solutions, such as transitioning to our Enterprise platform, which is designed to handle more complex data processing and analysis tasks effectively. By working closely with Hornbill, you can ensure that your dashboard functions optimally and continues to provide valuable insights for your business operations.


<!-- https://wiki.hornbill.com/index.php?title=Dashboards -->
