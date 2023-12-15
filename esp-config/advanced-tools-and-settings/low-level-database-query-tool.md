---
layout: article-toc
---
# Low-Level Database Query Tool
The Low-Level Database Query Tool is an advanced debugging feature of the Hornbill Platform which allows you to query the underlying application database using Structured Query Language (SQL) statements. Every Hornbill instance incorporates this feature however it is not enabled by default and its use is not encouraged. This feature is intended for advanced users only to support diagnostics of issues and problems. 

:::warning
This function of the Hornbill platform is disabled and protected behind a super-user privilege level because it exposes some inherent security risks with regards to accessing data a user may not be authorized to access.  As a result this feature is likely to be depreciated in the future.  The platform, and our cloud operations and support capabilities have matured beyond the point where this is beneficial, there are no use-0cases where its really necessary to access the underlying database in this way. 
:::

## Enabling the Low-Level Database Query Tool
The visibility of Low-Level Database Query Tool is governed by a system setting `security.database.allowSqlQueryOperation`. Any user wishing to use the Low-Level Database Query Tool must be assigned the "Super User Role".

Once the application setting has been enabled, it may be necessary to refresh your browser to allow this change in this setting to be acknowledged. If the association of a role is also required, it will be necessary for the user to log out and then log in again to ensure the user's session is aware of the recent association of the Super User role.

## Using Low-Level Database Query Tool
Once enabled, Low-Level Database Query Tool can be found via Home > System > Data > Low-Level Database Query Tool. The key features are outlined below.

* **Query Editor**<br>Type your SQL query here
* **Data Format**<br>Choose whether raw data values are displayed (e.g. boolean flags will appear as 0 or 1) or if data formatters are to be applied (e.g. No or Yes). Not all data is subject to data formatting.
* **Clear**<br>Clears the current query in the query pane and result set.
* **Execute**<br>Execute the query that exists in the query pane
* **Execute Selected Text**<br>If more than one query exists in the query pane, highlighting the query and using this button will execute the highlighted query.
* **Table filter**<br>Filter the list of Hornbill tables by typing in text.
* **Table List**<br>Shows all the tables available based on the applications you have installed on your instance.
* **Manage Saved Queries**<br>If you have saved any queries, you can manage them here.
* **Show/Hide Query Editor**<br>Toggle whether the query editor is displayed or not. This may be useful when examining larger result sets.
* **Show/Hide Table List**<br>Toggle whether the table list is displayed or not. This may be useful when examining larger result sets.
* **Save Query**<br>Saves the current content of the Query Editor
* **Query Limit**<br>All queries executed in the Low-Level Database Query Tool are subject to a limit, adjust the number of records returned here.
* **Result Quick Filter**<br>Filter the results set currently displayed.
* **Column Display**<br>When examining your result set, choose to display friendly column display names or raw column database names.
* **Export**<br>Export your result set to a variety of formats including CSV.
* **Result Set**<br>The set of results returned by the last query you executed.
<!-- References>
<!-- https://wiki.hornbill.com/index.php?title=Database_Direct>