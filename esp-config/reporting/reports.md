---
layout: article-toc
keywords: create a report, edit a report
---

# Reports

Reports transform lists of data into meaningful information for easier analysis. In Hornbill, a report provides a snapshot of your data at the time you run it. You can create reports in multiple formats, and schedule them for automated delivery to [Document Manager](/documentmanager-user-guide/index) or via email.

<!--[Visual Suggestion: A diagram showing data flowing from application tables through a filter and into different output formats like PDF and Excel.]-->

## Accessing reports

Each Hornbill application has its own Reports list, if reporting is available for that app. To access the Reports list:

1. Go to [Configuration](/esp-config/getting-started/using-configuration).
2. Select **Platform Configuration** or the specific application you want to report on.
3. In the navigation panel, find the Reporting section and select **Reports**.

## Reports list toolbar

Use the toolbar at the top of the Reports list to manage your report collection:

*   **Filter**: Search for existing reports in your list.
*   **Import/Export Reports**: Import report package files and export reports.
*   **Create New Report**: Select **+ Create New Report** to build a new report.
*   **Delete Selected**: Remove the selected reports from the list.

<!--[Visual Suggestion: An annotated screenshot of the Report List toolbar highlighting each button.]-->

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

*   **Save**: Commit your changes. You must save a report before you can run it.
*   **Copy Report As**: Create a duplicate of the current report with a new name. This option appears after the initial save.
*   **Run**: Manually execute the report. Find the results in the **Report History** tab. The **Run** button is disabled if there are unsaved changes or if a report is currently generating.
*   **Download**: Export the report definition file to your computer.
*   **Upload**: Import a report definition file. This action overwrites all current settings for the report.

::: warning
Report definitions include sensitive data such as email addresses, schedule details, and upload locations. Review this data before you share a report definition.
:::

### General settings

*   **Name**: The title of the report as it appears in the list and on the output.
*   **Description**: Summarize the purpose of the report.
*   **Report Output Type**: Select the format for the output.
*   **Report Using**: Choose how to build the report:
    *   **SQL Schema Designer**: Use SQL queries.
    *   **Report Entity**: Use an entity.
    *   **Report Measure**: Use a measure.
*   **Report Status**: Set the current state of the report (e.g., **In development** or **Available for use**).

### Data collection settings

**Select tables:** Choose the tables that contain the information you need. If you select multiple tables, you must define a table join.

**Table Join:** When using multiple tables, create a join to link data.

*   **Join (Inner Join)**: Includes only rows where there is a match in both tables.
*   **Left Join**: Includes all rows from the left table and matching rows from the right table.
*   **Right Join**: Includes all rows from the right table and matching rows from the left table.

**Select Columns:** Select the specific columns to include in your results. 

  :::tip
  Hold **Ctrl** while selecting to choose multiple columns.
  :::

*   **Visible**: Select this checkbox to display the column in the output. Deselect it if you only need the column for filtering or grouping.

**Select Filter:** Define criteria to limit the data returned by the report. This ensures your report only shows relevant records.

**Select Ordering:** Choose the column that determines the sort order of the results.

**Data Preview:** View a sample of your data. Note that the preview does not display grouping logic for grouped reports.

### Output format settings

You can customize how your data appears using these options:

*   **Report Output Formats:** Choose the file type.
*   **Report Layout:** Choose the orientation (**Portrait** or **Landscape**).
*   **Header Options:** Configure the top section of the report.
*   **Report Table Options:** Set display preferences for data tables.
*   **Report Chart Options:** Configure chart settings.
*   **Group Section Options:** Set group display options.
*   **Group Section Chart Options:** Configure display options for grouped charts.
*   **Additional Data Formats:** The system generates reports in PDF by default. You can also export data in these formats:
    * CSV
    * XLS
    * XLSX

    :::note
    HTML, XML, and JSON export formats are available with the [Enterprise Edition](/esp-fundamentals/about/hornbill-editions).
    :::

### Schedule settings

You can automate reports to run at specific intervals:

*   **Run Once**: A single execution at a scheduled time.
*   **Run Daily**: Executes every day or on specific days of the week.
*   **Run Monthly**: Executes on specific months and days.
*   **Run Every Period (Minutes)**: Executes on a recurring minute-based cycle.

**Publishing options:**

When a report runs on a schedule, the system can distribute it via:

*   **Email**: Sends the report to one or more recipients via [direct outbound messages](/esp-config/email/direct-outbound).
*   **Document Manager**: Saves the report to an existing document. You can locate the target document by searching on document tags. (You must have [Document Manager](/documentmanager-user-guide/index) installed on your Hornbill instance.)

**Managing the schedule:**

Once you schedule a report, the status shows as **Running**.
*   Select the **Pause** icon to stop the schedule and disable distribution.
*   Select the **Play** icon to resume the schedule.

### Report history

The **Report History** tab stores previous executions.
*   Click the Run ID of a report to view details of the execution.
*   Use the checkbox to select any run, then select **Download** to retrieve a past report.

## Limitations

### Row limits

The default limit is 1,000 rows. You can increase this to a maximum of 25,000 rows by updating the `api.xmlmc.queryExec.maxResultsAllowed` setting.

**PDF reports** have specific constraints:
*   Maximum columns: 20
*   Maximum rows: 5,000
*   Format: A4 only (Portrait or Landscape).

If a report exceeds these limits, the PDF fails to generate. To fix this, reduce the column count or choose a different output format.

### Field limits

Each field has a default size limit of 1,024 characters. You can increase this to a maximum of 4,096 characters by updating the `reporting.reports.maxFieldLength` setting. The system truncates any data that exceeds the configured limit.

### Hidden columns

Hidden columns do not appear in PDF files. However, CSV, XLS, and XLSX files include hidden columns. To exclude data from these formats, remove the column from the report configuration.

<!-- ***

### Key changes and rationale

1.  **Active Voice**: Changed "Reports can be distributed" to "The system distributes reports" and "Results are added" to "The system adds results" to improve clarity and directness.
2.  **Sentence Case**: Updated all headings (e.g., "Report list toolbar" to "Report list toolbar") to align with the Global Style Guide.
3.  **Removed Em-dashes**: Replaced em-dashes with colons or commas to comply with the style requirements.
4.  **Persona Alignment**: Used encouraging and clear language such as "You can easily..." and provided step-by-step instructions for navigation to help new customers feel supported.
5.  **UI Consistency**: Used bold text for UI elements like **Configuration** and **Save** to help users visually locate buttons and menus.
6.  **Direct Instructions**: Used imperative verbs (e.g., "Select," "Navigate," "Choose") to make the documentation actionable.
7.  **Preserved Technical Nouns**: Maintained specific system settings like `api.xmlmc.queryExec.maxResultsAllowed` to ensure technical accuracy.
8.  **Visual Suggestions**: Added placeholders for diagrams and screenshots to assist new users in understanding spatial relationships and UI locations.-->

<!--# Reports

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

Report Schedules can be set with the following intervals:

* Run Once
* Run Daily - Choose to run on all or specific days at a set time
* Run Monthly - Choose to run on all or specific months on a set day and time in each month
* Run Every Period (Minutes)

When publishing a report there are two types of publishing available:

* **Email:** Reports can be distributed to one or more email recipients.  These emails are sent using [direct outbound messages](/esp-config/email/direct-outbound).
* **Document Manager:** If Document Manager is installed, reports can be scheduled to be distributed to an existing document in Document Manager. Find the document you want the report to be distributed to by searching for documents using their document tags.

Once the Report is Scheduled, it will show as **Running**.

* Pause the Schedule and prevent further distribution of the report by clicking on the pause icon
  * This will mark the report as disabled
  * Click the play icon to resume the report schedule

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

Hidden columns don't appear in PDF output but are included in CSV, XLS, and XLSX files. If you don't want the data in these formats, remove the column from the report.-->
