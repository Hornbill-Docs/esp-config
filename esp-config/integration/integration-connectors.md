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

### Content Pack
As well as having the option to invoke your Runbooks from a business process we have provided a Content Pack for HPE Operations Orchestration 10.50+, to demonstrate integration with the Hornbill Collaboration platform and Service Manager application.

This can be used to enable HPEOO administrators to include Hornbill Collaboration and Service Manager automations in their flow orchestrations.

Download the Hornbill Content Pack following the instructions in the HP Operations Orchestration Content Pack from the Related Articles Section.

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

### Content Pack
As well as having the option to invoke your Runbooks from a business process, we have also provided a collection of our own runbooks for Microsoft System Center Orchestrator 2012 R2, to demonstrate runbook automation and integration with the Hornbill Collaboration platform and Service Manager application.

Download the Hornbill Runbooks following the instructions in the Microsoft Orchestrator Content Pack from the Related Articles Section.