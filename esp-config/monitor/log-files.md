---
layout: article-toc
---
# Log Files

For all the activity that takes place on Hornbill, including interaction by the users and the processing done by the platform on your instance. This is the perfect place to go to when investigating either the success of an action taking place or for troubleshooting when things don't go right.

There are a number of different log files that are available for different aspects or areas of Hornbill.

* **api.log**<br>View this log to see the different APIs that are being used and see how fast they are responding.
* **EspCrawler.log**<br>
* **EspDbTool.log**<br>
* **EspEventService.log**<br>
* **EspFileService.log**<br>
* **EspIndexerService.log**<br>View this log to see events and activities with the Indexes that are on your instance.
* **EspInsightService.log**<br>
* **EspMailImporter.log**<br>View this log to monitor events related to connecting to your email server and the importing of emails from this service into Hornbill
* **EspMailService.log**<br>View this log to monitor events related to your mailboxes and the processing of incoming and outgoing emails
* **EspServerService.log**<br>View this log to monitor the main activity and events performed by users in the Hornbill Client

## View Log Files
Clicking on any of the available log files will give you access to all the transactions being recorded for that particular log file.

## Filters
The log files can be filled with important information that includes both successful transactions as well as errors.

## Severity
A number of Severity Levels are provide to allow you to filter down on the type of transactions that are important to you.
* Emergency
* Alert
* Critical
* Error
* Warning
* Notice
* Information
* Debug
* Settings

## Archiving
There are a number of settings that will archive the log files when the associated Service is restarted on the instance. These settings are accessible in Configuration under Advanced System Settings.

|Setting|Description|
|-|-|
|logging.EspEventService.archiveOnStart|Set this to 'true' if you want the EspEventService log file to be archived when the service is started.|
|logging.EspFileService.archiveOnStart|Set this to 'true' if you want the EspFileService log file to be archived when the service is started.|
|logging.EspIndexerService.archiveOnStart|Set this to 'true' if you want the EspIndexerService log file to be archived when the service is started.|
|logging.EspInsightService.archiveOnStart|Set this to 'true' if you want the EspInsightService log file to be archived when the service is started.
|logging.EspMailService.archiveOnStart|Set this to 'true' if you want the EspMailService log file to be archived when the service is started.|
|logging.EspServerService.archiveOnStart|Set this to 'true' if you want the EspServerService log file to be archived when the service is started.|

<!-- https://wiki.hornbill.com/index.php?title=Log_Files -->