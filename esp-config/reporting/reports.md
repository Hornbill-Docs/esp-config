---
layout: article-toc
---
# Reports

Reports are used to collect specific data for your reporting needs. The reports in Hornbill are a point in time, meaning that the data is accurate at the point when the report is run. These types of reports are best used for reporting on lists of data. There are various options with reports, which will be explored in more detail below. Reports can be created in various formats and can be scheduled for distribution to documents in Document Manager or by email.

## Report list

Each Hornbill application will have its own Report List. These can be accessed by browsing the Admin tool starting at Home -> Applications and then selecting the application that you with to report on. A reports section will be displayed if reporting is available for the app.

### Report list toolbar

* **Filter**. A filter allows you to locate reports that you have already created.
* **Create New Report**. This option starts the process of creating a new report.
* **Delete Selected**. This option will only be available when one or more reports have been selected within the Report List.

## Creating and editing a report

By either selecting the Create New Report or by clicking on the name of an existing report from within your Report List, you are presented with the options to define your report.

### Report toolbar

* **Save**. Once the name of the report has been entered within the Report Details, the save option will become available. For both new and existing reports, they must be saved before you can run the report.
* **Copy Report As**. This allows you to create a copy of this report and add it to your list of reports under a different name. This option is only available after the new report has been saved for the first time.
* **Run**. This starts a manual running of the report. The results of the Run are added to the Report History. This option will not be available when there are unsaved changes on a report. It will also not be available while a report generation is already running.
* **Download**. Download a definition file for the report. This allows you to share a report definition with another Hornbill instance. This option is only available after the new report has been saved for the first time.
* **Upload**. Upload a definition file for the report. This allows you to take a report that has been shared with you and upload it to your Hornbill instance. Uploading a definition file will overwrite any settings that you have previously set for that report, including the name.

    :::warning
    Downloading a Report definition will include any configured schedule or delivery information, which may contain email addresses or details of the upload location. Similarly, uploading a saved report definition file will import this saved scheduled or delivery information. You should therefore ensure that, on downloading or uploading a report, you check to ensure that this data does not exist if not required.
    :::

### General

* **Name**. The name of the report. This is displayed in the list of reports as well as providing the default title on the report output.
* **Description**. Use this area to describe the report.
* **Report Output Type**
* **Report Using**
  * **SQL Schema Designer**
  * **Report Entity**
  * **Report Measure**
* **Report Status**

### Data Collection

#### Select Tables

* **Select Tables**. Select one or more tables that will be used in the report.
* **Table Join**.  When more than one table has been selected, a join can be created to link related data.
* **Select Columns**. A list of the available columns that can be included in the report.  Select a column and click on `Select Column`.
    :::tip
    Holding down the Ctrl key on your keyboard while selecting allows you to select more than one column at a time.
    :::

  * ***Visible***.  When selected, the content of this column will be displayed on the report.  A column can be added for grouping or filtering purposes, and it may not need to be made visible in the report.

#### Select Filter

A filter can be created to only include specific data in the reports.

* **Select Ordering**. When there is more than one column, you can select which column the report is ordered by.
* **Data Preview**.  This provides a sample of the data that will be included in your report.  The grouping provided in the grouped reports will not be represented in the preview.

### Output Formats

* **Report Output Formats**
* **Report Layout**
* **Header Options**
* **Report Table Options**
* **Report Chart Options**
* **Additional Data Formats**. Reports are output by default in PDF format. In the Output Formats , you can also choose to output the report in the following additional formats.
  * CSV
  * XLS
  * XLSX

    :::note
    HTML, XML and JSON export formats are available with the [Enterprise Edition](/esp-fundamentals/about/hornbill-editions).
    :::

### Schedule

As well as running reports manually, you can also schedule the reports to run and be distributed on definable intervals.

* **Report Schedule**
* **Publishing**

### Report History

* **Download**

## Report limitations

### Row limits

When creating reports, the max row limit is set by default on instances to 1000, this can be increased to a maximum of 25000 rows using the following system setting: api.xmlmc.queryExec.maxResultsAllowed

The only exception to this is for the creation of PDF reports output, which is limited to the following max outputs:

* reporting.display.maxcolumns = 20
* reporting.display.maxrows=5000

If either of these limits is exceeded when trying to generate a PDF output, the PDF generation will fail. PDF reports can only be generated in A4 format (either portrait or landscape). Because of this restriction, there could be a scenario where not all included columns will be visible in a PDF report, depending on the data contained in these columns. In this scenario, we can only advise reducing the number of columns or opting for a different output type.

### Field limits

An individual field in a report output has a default size limit of 1024.  This can be updated to a maximum value of 4096 using the system setting reporting.reports.maxFieldLength.  Fields on a report that exceed the length specified in this setting will be truncated to the set value.

### Hidden columns

Any hidden columns will only be excluded from the visual PDF output, with the data being included in the CSV, XLS and XLSX outputs. If you do not wish the data to be included in these output formats, the column should be removed from the report.
