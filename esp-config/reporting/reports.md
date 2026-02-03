---
layout: article-toc
---
# Reports

Use reports to gather the data you need. Reports show a snapshot of your data at the time you run them, which makes them ideal for analyzing lists of data. You can create reports in multiple formats and schedule them to be delivered to [Document Manager](/documentmanager-user-guide/index) or by email. See the sections below to learn about your report options.

## Report list

Each Hornbill application has its own Report List. To access it, go to [Configuration](/esp-config/getting-started/using-configuration), then select either Platform Configuration or the application you want to report on. A reporting section appears if reporting is available for that app.

### Report list toolbar

* **Filter** - Find reports you've already created.
* **Import/Export Reports** - Import a report package file or export listed reports.
* **Create New Report** - Create a new report.
* **Delete Selected** - Remove selected reports from your list.

## Creating and editing a report

To create or edit a report, select **Create New Report** or select an existing report name from the list. You can then configure the report settings.

### Report toolbar

* **Save** - Save the report after entering its name. You must save a report before you can run it.
* **Copy Report As** - Create a duplicate report with a different name. Available after you save the report for the first time.
* **Run** - Manually run the report. Results are added to the Report History. Not available when there are unsaved changes or if a report is already generating.
* **Download** - Export the report definition file to share with another Hornbill instance. Available after you save the report.
* **Upload** - Import a report definition file from another Hornbill instance. This overwrites your current report settings.

    :::warning
    Report definitions include schedule and delivery information, such as email addresses and upload locations. Before downloading or uploading a report, review this data to ensure it's appropriate for sharing.
    :::

### General

* **Name** - The report name. This appears in the report list and as the title on report output.
* **Description** - Add a description for the report.
* **Report Output Type** - Select the format for the report output.
* **Report Using** - Choose how to build the report:
  * **SQL Schema Designer** - Use SQL queries to define the report.
  * **Report Entity** - Use report entities.
  * **Report Measure** - Use report measures.
* **Report Status** - Set the status for the report.

### Data Collection

#### Select Tables

* **Select Tables** - Select one or more tables for the report.
* **Table Join** - Create a join to link data when you use multiple tables.
  * ***Join (Inner Join)*** - Keep only the matching rows from both tables and drop everything else.
  * ***Left Join*** - Keep all of the rows from the left table and the matched rows from the right. Drop the rows in the right table that don't have a match in the left.
  * ***Right Join*** - Keep all of the rows from the right table and the matched rows from the left.  Drop the rows in the left table that don't have a match in the right.
* **Select Columns** - Select which columns to include in the report. Click **Select Column** for each column you want.
    :::tip
    Hold Ctrl while selecting to choose multiple columns at once.
    :::

  * **Visible** - Check this option to display the column in the report. You can also include columns for grouping or filtering without displaying them.

#### Select Filter

Create filters to include only specific data in your reports.

#### Select Ordering

Choose which column to sort the report by when you have multiple columns.

#### Data Preview

View a sample of the data that will appear in your report. This preview doesn't show grouping for grouped reports.

### Output Formats

Choose how to format and display your report:

* **Report Output Formats** - Select the output format.
* **Report Layout** - Customize the layout of the report.
* **Header Options** - Configure report headers.
* **Report Table Options** - Set table display options.
* **Report Chart Options** - Configure chart settings.
* **Additional Data Formats** - Reports are output in PDF by default. You can also export in these formats:
  * CSV
  * XLS
  * XLSX

    :::note
    HTML, XML, and JSON export formats are available with the [Enterprise Edition](/esp-fundamentals/about/hornbill-editions).
    :::

### Schedule

In addition to running reports manually, you can schedule reports to run and distribute them at regular intervals.

* **Report Schedule** - Set when and how often the report runs.
* **Publishing** - Configure how and where the report is delivered.

### Report History

* **Download** - Download a previously run report from the history.

## Report limitations

### Row limits

By default, the row limit is 1000. You can increase this to a maximum of 25,000 rows by setting: `api.xmlmc.queryExec.maxResultsAllowed`

PDF reports have different limits:

* Maximum columns: 20
* Maximum rows: 5,000

If you exceed these limits, the PDF fails to generate. PDF reports are only available in A4 format (portrait or landscape). Because of this, some columns might not fit depending on the data. To resolve this, reduce the number of columns or choose a different output format.

### Field limits

Each field has a default size limit of 1,024 characters. You can increase this to a maximum of 4,096 characters by setting: `reporting.reports.maxFieldLength`. Fields that exceed the configured limit are truncated.

### Hidden columns

Hidden columns don't appear in PDF output but are included in CSV, XLS, and XLSX files. If you don't want the data in these formats, remove the column from the report.
