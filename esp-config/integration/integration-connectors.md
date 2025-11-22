---
layout: article-toc
---
# Integration Connectors
Hornbill provides integration connectors with HP Operations Orchestration and Microsoft Orchestrator. This allows you to plugin with your 'HP Operations Orchestration or Microsoft Orchestrator from a Hornbill workflow using the Cloud Automation node.

## HP Operations Orchestration Content Pack
### Configuration
You can configure the connection to your HP Operations Orchestration instance/s in the admin tool under System > Settings > BPM Integrations and the + icon

When creating a new Integration Connector if you chose the type HP Open Orchestrator you will get the following:

* **HTTP Endpoint**<br>API Endpoint for HPP which contains a publicly accessible domain name i.e hp.mydomain.com, the port must be 8443 as we send all connectors through this port followed by /oo/rest/v2
* **Username**<br>HPOO Basic Authentication Username
* **Password**<br>HPOO Basic Authentication Password
* **SSL Verify Host / Peer**<br>Occasionally when testing a machine that only has a self signed certificate these need to be unchecked.

Once created a Test Connection button will appear allowing you to test the connection details before using them inside an Cloud Automation Node.

### Firewall
Typically a Firewall change will be needed for your Instance to communicate back to your HPOO instance:

|Hornbill Data Center|Outbound IP Address|Port|
|-|-|-|
|Europe|87.117.243.10|8443|
|North American|69.174.241.48|8443|

### Invoking Orchestration Flows
Using the Business Process Designer and the Cloud Automation node you can invoke any of your defined Orchestration Flows from your configured HP Operations Orchestration instances within your business processes.

### Content Pack download
As well as having the option to invoke your Runbooks from a business process we have provided a Content Pack for HPE Operations Orchestration 10.50+, to demonstrate integration with the Hornbill Collaboration platform and Service Manager application.

This can be used to enable HPEOO administrators to include Hornbill Collaboration and Service Manager automations in their flow orchestrations.

#### Installation
1. Download the zipped content pack from the [Hewlett Packard Enterprise ITOM Marketplace](https://marketplace.opentext.com/itom/content/hornbill-service-manager-and-collaboration-integration).
1. Extract the JAR file from the ZIP, and import as a Content Pack in to the Operations Orchestration Studio.

The flows within the Content Pack use three System Properties to identify the Hornbill instance and API key to use to invoke Hornbill API calls. These properties should be populated as so:

* **Configuration\System Properties\APIKey**: This is the API key for the user account that should be used to perform the Hornbill API calls.
* **Configuration\System Properties\Instance**: This is the (case sensitive) ID of your Hornbill instance (the yourinstancename part of your Hornbill URL: `https://live.hornbill.com/yourinstancename`).
* **Configuration\System Properties\InstanceZone**: This is the zone where your Hornbill instance resides:
    * eur - If your instance resides in the European zone.
    * nam - If your instance resides in the North American zone.

Once the Content Pack has been imported, and the System Properties have been configured, please see the description against each flow for more information about the flow, its inputs/outputs, and the APIs that they use.

:::note
Any number of HPOO Connectors are currently supported so if you multiple HP OO Servers you need to connect to these can all be added just make sure to give each one an identifiable title so that they are easily selected from the Integration Node.
:::

## Microsoft Orchestrator
### Configuration
When creating a new Integration Connector if you chose the type Microsoft System Center Orchestrator you will get the following:

* **HTTP Endpoint**<br>API Endpoint for Orchestrator which contains a publicly accessible domain name i.e mydomain.com, the port must be 8443 as we send all connectors through this port followed by /Orchestrator2012/Orchestrator.svc
* **Username**<br>Orchestrator Basic Authentication Username typically with the domain or machine name preceding the username
* **Password**<br>Orchestrator Basic Authentication Password
* **SSL Verify Host / Peer**<br>Occasionally when testing a machine that only has a self signed certificate these need to be unchecked.

Once created a Test Connection button will appear allowing you to test the connection details before using them inside an Cloud Automation Node.

### Firewall
Typically a Firewall change will be needed for your Instance to communicate back to your Microsoft Orchestrator instance:

|Hornbill Data Center|Outbound IP Address|Port|
|-|-|-|
|Europe|87.117.243.10|8443|
|North American|69.174.241.48|8443|

### Invoking Microsoft Orchestrator Runbooks
Using the Business Process Designer and the Cloud Automation node you can invoke any of your defined Runbooks from your configured Microsoft Orchestrator instances within your business processes

### Content Pack download
As well as having the option to invoke your Runbooks from a business process, we have also provided a collection of our own runbooks for Microsoft System Center Orchestrator 2012 R2, to demonstrate runbook automation and integration with the Hornbill Collaboration platform and Service Manager application.

#### Installation
Download the [Runbook Export](https://github.com/hornbill/SCOrchHornbillIntegration/blob/master/Hornbill_Integration_Runbooks.ois_export) from the [Github repository](https://github.com/hornbill/SCOrchHornbillIntegration), and place on your System Center server.

The file supplied is an export of a collection of runbooks, developed in SCOrch 2012 R2. This can be imported in to SCOrch by right-clicking on the Runbooks folder of your choice within the Orchestrator Runbook Designer, and click Import.

The runbooks use three global variables to identify the Hornbill instance and API key to use to invoke Hornbill API calls. These variables should be populated as so:

* **Hornbill\Hornbill API Key**: This is the API key for the user account that should be used to perform the Hornbill API calls
* **Hornbill\Hornbill Instance ID**: This is the (case sensitive) ID of your Hornbill instance (the yourinstancename part of your Hornbill URL: `http://live.hornbill.com/yourinstancename`)
* **Hornbill\Hornbill Instance Zone**: This is the zone where your Hornbill instance resides:
    * eur - If your instance resides in the European zone
    * nam - If your instance resides in the North American zone

Once the runbooks have been imported, and the global variables have been configured, please see the description against each for more information about the runbook, and the APIs that they use.