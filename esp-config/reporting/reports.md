---
layout: article-toc
keywords: create a report, edit a report
---

# Reports

Reports transform lists of data into meaningful information for easier analysis. In Hornbill, a report provides a snapshot of your data at the time you run it. You can create reports in multiple formats, and schedule them for automated delivery to [Document Manager](/documentmanager-user-guide/index) or via email.

## Accessing reports

Each Hornbill application has its own Reports list, if reporting is available for that app. To access the Reports list:

1. Go to [Configuration](/esp-config/getting-started/using-configuration).
2. Select **Platform Configuration** or the specific application you want to report on.
3. In the navigation panel, find the Reporting section and select **Reports**.

## Reports list toolbar

Use the toolbar at the top of the Reports list to manage your report collection:

* **Filter**: Search for existing reports in your list.
* **Import/Export Reports**: Import report package files and export reports.
* **Create New Report**: Select **+ Create New Report** to build a new report.
* **Delete Selected**: Remove the selected reports from the list.

## Report configuration

To edit a report, select the report name from the list. To build a new one, select **+ Create New Report**.

When configuring a report, there are one or more tabs available, depending on the Hornbill application:

* [General](/esp-config/reporting/reports#general-settings)
* [Data Collection](/esp-config/reporting/reports#data-collection-settings)
* [Output Formats](/esp-config/reporting/reports#output-format-settings)
* [Schedule](/esp-config/reporting/reports#schedule-settings)
* [Report History](/esp-config/reporting/reports#report-history)

### Report configuration toolbar

![Toolbar options](/_books/esp-config/images/report-toolbar-options.png)

The following actions are available in the toolbar when a report is open:

* **Save**: Commit your changes. You must save a report before you can run it.
* **Copy Report As**: Create a duplicate of the current report with a new name. This option appears after the initial save.
* **Run**: Manually execute the report. Find the results in the **Report History** tab. The **Run** button is disabled if there are unsaved changes or if a report is currently generating.
* **Download**: Export the report definition file to share with another Hornbill instance. Available after you save the report. A drop-down allows you to export with or without Schedule or Delivery options (see Warning).
* **Upload**: Import a report definition file. This action overwrites all current settings for the report.

 :::warning
  Report definitions include schedule and delivery information, such as email addresses and upload locations. Before downloading or uploading a report, review this data to ensure it's appropriate for sharing. If you do not wish to export the report with the Schedule information such as recipients email address or SFTP details, then you should choose from the drop-down list **Download without sensitive information**.
  :::

### General settings

* **Name**: The title of the report as it appears in the list and on the output.
* **Description**: Summarize the purpose of the report.
* **Report Output Type**: Select the format for the output.
* **Report Using**: Choose how to build the report:
  * **SQL Schema Designer**: Use SQL queries.
  * **Report Entity**: Use an entity.
  * **Report Measure**: Use a measure.
* **Report Status**: Set the current state of the report (e.g., **In development** or **Available for use**).

### Data collection settings

**Select Tables:** Choose the tables that contain the information you need. If you select multiple tables, you must define a table join.

**Table Join:** When using multiple tables, create a join to link data.

* **Join (Inner Join)**: Includes only rows where there is a match in both tables.
* **Left Join**: Includes all rows from the left table and matching rows from the right table.
* **Right Join**: Includes all rows from the right table and matching rows from the left table.

**Select Columns:** Select the specific columns to include in your results.

  :::tip
  Hold **Ctrl** while selecting to choose multiple columns.
  :::

* **Visible**: Select this checkbox to display the column in the output. Deselect it if you only need the column for filtering or grouping.

**Select Filter:** Define criteria to limit the data returned by the report. This ensures your report only shows relevant records.

**Select Ordering:** Choose the column that determines the sort order of the results.

**Data Preview:** View a sample of your data. Note that the preview does not display grouping logic for grouped reports.

#### Using aliases

If you create a report that pulls information from multiple tables — such as **Assets**, **Requests**, and **Asset Types** — you may find that some of these tables share column names (e.g. `h_name`). This can make a report confusing to read, since it's not obvious which table a given field actually belongs to.

**Table and column aliases** let you assign clearer, shorter, or more descriptive names to tables and fields so your reports are easier to build and read.

This example uses SQL Schema Designer with four tables:

* `h_itsm_requests`
* `h_cmdb_assets`
* `h_cmdb_asset_types`
* `h_cmdb_links`

##### Adding a table alias

You might want to alias a table simply because its name is long and you'd like a shorter reference for use elsewhere in the report.

1. On the **Select Tables** tab, double-click the table you want to alias (e.g. `h_cmdb_asset_types`).
2. Choose **Add Alias** from the options shown (you'll also see the option to **Remove Table** here).
3. Enter your preferred alias — for example, aliasing `h_cmdb_asset_types` to **AssetTypes**.

##### Adding a column alias

Some tables share column names. For example:

* `h_cmdb_assets` has a column called `h_name`
* `h_cmdb_asset_types` also has a column called `h_name`

Without aliasing, a report combining both tables could easily confuse **Asset Name** (`h_cmdb_assets.h_name`) with the asset type's name (`h_cmdb_asset_types.h_name`).

Once the table alias **AssetTypes** has been applied (see above), the field appears in the schema diagram as:

: `AssetTypes -> TypeName (AssetTypes.h_name)`

To add a column alias:

1. Click the **Edit** icon (pencil) on **Edit Report Columns**.
2. Enter an alias for the field name — e.g. rename `h_name` to **TypeName** for clarity.

##### Results

With both table and column aliases applied, your finished report clearly distinguishes between fields that would otherwise share the same name — for example, **Asset Name** vs. **TypeName** — making the report much easier to read and maintain.

### Output format settings

You can customize how your data appears using these options:

* **Report Output Formats:** Choose the file type.
* **Report Layout:** Choose the orientation (**Portrait** or **Landscape**).
* **Header Options:** Configure the top section of the report.
* **Report Table Options:** Set display preferences for data tables.
* **Report Chart Options:** Configure chart settings.
* **Group Section Options:** Set group display options.
* **Group Section Chart Options:** Configure display options for grouped charts.
* **Additional Data Formats:** The system generates reports in PDF by default. You can also export data in these formats:
  * CSV
  * XLS
  * XLSX

    :::note
    HTML, XML, and JSON export formats are available with the [Enterprise Edition](/esp-fundamentals/about/hornbill-editions).
    :::

### Schedule settings

You can automate reports to run at specific intervals:

* **Run Once**: A single execution at a scheduled time.
* **Run Daily**: Executes every day or on specific days of the week.
* **Run Monthly**: Executes on specific months and days.
* **Run Every Period (Minutes)**: Executes on a recurring minute-based cycle.

**Publishing options:**

When a report runs on a schedule, the system can distribute it via:

* **Email**: Sends the report to one or more recipients via [direct outbound messages](/esp-config/email/direct-outbound).
* **Document Manager**: Saves the report to an existing document. You can locate the target document by searching on document tags. (You must have [Document Manager](/documentmanager-user-guide/index) installed on your Hornbill instance.)

**Managing the schedule:**

Once you schedule a report, the status shows as **Running**.

* Select the **Pause** icon to stop the schedule and disable distribution.
* Select the **Play** icon to resume the schedule.

### Report history

The **Report History** tab stores previous executions.

* Click the Run ID of a report to view details of the execution.
* Use the checkbox to select any run, then select **Download** to retrieve a past report.

## Limitations

### Row limits

The default limit is 1,000 rows. You can increase this to a maximum of 25,000 rows by updating the `api.xmlmc.queryExec.maxResultsAllowed` setting.

**PDF reports** have specific constraints:

* Maximum columns: 20
* Maximum rows: 5,000
* Format: A4 only (Portrait or Landscape).

If a report exceeds these limits, the PDF fails to generate. To fix this, reduce the column count or choose a different output format.

### Field limits

Each field has a default size limit of 1,024 characters. You can increase this to a maximum of 4,096 characters by updating the `reporting.reports.maxFieldLength` setting. The system truncates any data that exceeds the configured limit.

### Hidden columns

Hidden columns do not appear in PDF files. However, CSV, XLS, and XLSX files include hidden columns. To exclude data from these formats, remove the column from the report configuration.
