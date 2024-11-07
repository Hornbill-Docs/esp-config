---
layout: article-toc
---
# Dashboards
Dashboards are used to display widget content. You can:

* Customize dashboards to include multiple rows and columns, then add widgets to them.
* Share dashboards with specific users, roles, and groups.
* Display dashboards in slideshows or on large screens.

## Topics covered
* [Creating a dashboard](/advanced-analytics/dashboards#creating-a-dashboard)
* [Defining dashboard layouts](/advanced-analytics/dashboards#defining-dashboard-layouts)
* [Adding widgets to dashboard columns](/advanced-analytics/dashboards#adding-widgets-to-dashboard-columns)
* [Managing dashboard properties](/advanced-analytics/dashboards#managing-dashboard-properties)
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
As you create the layout for your dashboard, you can add rows and columns as necessary so that they are ready for you to then add widgets inside them.

**To add additional rows to the layout:**
1. In design mode, click the **+** button in the top left of the row you want to add a new row directly below.
1. For more rows, repeat.
1. Any time you have multiple rows, use the Percentage Height fields to ensure that each row is set to an equal height value and that the total of all the row heights equals 100% (or 99%, in the case of three rows).

**To add columns to a row:**
1. In design mode, click the **Add Column** button from the top right of the row.
1. For more columns, repeat.
1. Any time you have multiple columns, use the Percentage Width fields to ensure that each column is set to an equal width value and that the total of all the column widths on a single row equals 100% (or 99%, in the case of three columns).

## Adding widgets to dashboard columns
The widgets on a dashboard are contained in columns. Besides adding widgets to columns, you can also move columns between rows. Once you have a dashboard configured the way you like it, you may want to save a copy of it to use for displaying other business intelligence.

**To add a widget to a column:**
1. In the column, click the **Add Chart** button.
1. From the top dropdown, select the widget type you wish to add. The options are Chart, Scorecard, Target Counter, Data List, Itemized Count List, and Custom.
1. Based on the type of widget you chose, a list of defined widgets of that type is displayed. Choose one. (Only widgets marked as *Available for Use* will appear in the list.)
    The chosen widget appears in the column. 
    :::tip
    If you need to remove the widget, click the delete button on the widget (not the one on the column header).
    :::
1. (Optional) Add additional widgets to the column by repeating the steps above.

**To move columns between rows:**
1. Move columns between rows by dragging and dropping them.

**To create a copy of a dashboard layout:**
1. Click **Save As** from the dropdown next to the **Save** button, then give the new dashboard a name.

### About row and column heights and widths
For the dashboard to display correctly:
* Ensure that the total of all row heights equals 100% (or 99%, in the case of three rows).
* Ensure that the total of all columns widths per row equals 100% (or 99%, in the case of three columns).

## Managing dashboard properties
Once the dashboard's layout is configured and its widget content is in place, it's important to set its status and grant access to those you want to view it.

* **Title.** Here you can edit the name of the dashboard.
* **Description.** Describe the dashboard's purpose and its content.
* **Status.** By default, this is set to *In development*. Once the dashboard is configured, change the status to *Available for use*. Only dashboards marked as *Available for use* will appear when configuring the content of slides in slideshows.
* **Access Granted To.** You can grant access to individual users, groups, and roles. To grant access, use the **+** button. Specify the access type and enter or select a corresponding user's name, a role, or a group.

## About performance of dashboards
Dashboards are complementary to reports; they are not replacements for reports. Dashboards provide real-time insights and a visual representation of data that can be easily interpreted at a glance. However, it is important to note that an excessive number of widgets on a dashboard can sometimes lead to performance issues, particularly when dealing with complex queries or large datasets.

If you find that your dashboard is experiencing performance issues, Hornbill offers assistance in optimizing your dashboard to improve its efficiency. This may involve streamlining the layout, reducing the number of widgets, or fine-tuning the queries to ensure smoother operation.

In some cases, it may be necessary to explore alternative solutions, such as transitioning to our Enterprise platform, which is designed to handle more complex data processing and analysis tasks effectively. By working closely with Hornbill, you can ensure that your dashboard functions optimally and continues to provide valuable insights for your business operations.


<!-- https://wiki.hornbill.com/index.php?title=Dashboards -->
