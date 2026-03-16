---
layout: article-toc
---
# Dashboards

Dashboards display widget content to help you visualize your data. You can customize layouts with multiple rows and columns, share dashboards with specific users, and display them in slideshows or on large screens.

## Before you begin

Ensure you have administrative permissions to access the **Configuration** menu.

## Creating a dashboard

Administrators can set up new dashboards within the platform configuration.

### Steps

1. Select the **Configuration** icon (the cog) at the bottom of the left-hand application menu bar.
2. Select **Platform Configuration** from the navigation dropdown.
3. Scroll to the **Advanced Analytics** section in the navigation panel.
4. Click **Dashboards**.
5. Click **+ Create New Dashboard** on the landing page.
6. Click the **Enter dashboard design mode** button (the edit icon).
7. Click the **Dashboard Properties** button.
8. Enter a name for your dashboard in the **Title** field.
9. Click **Save**.

### Expected result

The system saves the dashboard, and you can now begin designing the layout.

## Defining dashboard layouts

You can organize your dashboard by adding rows and columns to create a structure for your widgets.

### To add rows

1. In design mode, locate the row where you want to add a new row below.
2. Click the **+** button in the top left of that row.
3. Repeat this process for additional rows.
4. Set the **Percentage Height** fields for each row. Ensure the total of all row heights equals 100% (or 99% if you use three rows) to maintain an equal distribution.

### To add columns

1. In design mode, click the **Add Column** button in the top right of a row.
2. Repeat this process for additional columns.
3. Set the **Percentage Width** fields for each column. Ensure the total of all column widths in a single row equals 100% (or 99% if you use three columns).

## Adding widgets to dashboard columns

Widgets live inside columns. You can add multiple widgets to a single column or move columns to different rows to achieve your preferred look.

### To add a widget to a column

1. Click the **Add Chart** button within a column.
2. Select a widget type from the top dropdown. Options include:
    * Chart
    * Scorecard
    * Target Counter
    * Data List
    * Itemized Count List
    * Custom
3. Select a specific widget from the list. Only widgets marked as **Available for Use** appear here.
4. (Optional) Repeat these steps to add more widgets to the same column.

    :::tip
    If you need to remove the widget, click the delete button on the widget (not the one on the column header).
    :::

### To move columns

1. Click and drag a column to a new position or a different row.

### To copy a dashboard layout

1. Click the dropdown arrow next to the **Save** button.
2. Select **Save As**.
3. Enter a name for the new dashboard and click save.

### About row and column heights and widths

For the dashboard to display correctly:

* Ensure that the total of all row heights equals 100% (or 99%, in the case of three rows).
* Ensure that the total of all columns widths per row equals 100% (or 99%, in the case of three columns).

## Managing dashboard properties

After you configure the layout, use the properties settings to define who can see the dashboard and its current status.

* **Title**: Use this field to edit the dashboard name.
* **Description**: Provide a summary of the dashboard purpose and the data it contains.
* **Status**: New dashboards default to **In development**. Change this to **Available for use** when the dashboard is ready. Only dashboards with this status can be used in slideshows.
* **Access Granted To**: Use the **+** button to share the dashboard. You can grant access to specific users, roles, or groups.

## About performance of dashboards

Dashboards provide real-time insights and visual data summaries. They complement standard reports rather than replacing them.

Including a high number of widgets on a single dashboard can impact performance, especially when the widgets use complex queries or large datasets. If you notice slow loading times, consider the following optimizations:

* Streamline the layout by reducing the number of widgets.
* Fine-tune individual widget queries.
* Evaluate if the Enterprise platform is required for your data processing needs.

If you experience persistent performance issues, contact Hornbill for assistance in optimizing your dashboard configuration.
