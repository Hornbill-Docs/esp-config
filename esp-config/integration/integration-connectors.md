---
layout: article-toc
---
# Integration Connectors
Hornbill provides an Integration Connector with HP Operations Orchestration. This allows you to plugin an existing flow from with your 'HPOO instance from our Cloud Automation Node allowing for your Business Process to run Orchestration flows within your network. Any number of HPOO Connectors are currently supported so if you multiple HP OO Servers you need to connect to these can all be added just make sure to give each one an identifiable title so that they are easily selected from the Integration Node.

## HP Operations Orchestration Content Pack
Configuration
You can configure the connection to your HP Operations Orchestration instance/s in the admin tool under System > Settings > BPM Integrations and the + icon

text-right
When creating a new Integration Connector if you chose the type HP Open Orchestrator you will get the following:

HTTP Endpoint - API Endpoint for HPP which contains a publicly accessible domain name i.e hp.mydomain.com, the port must be 8443 as we send all connectors through this port followed by /oo/rest/v2
Username - HPOO Basic Authentication Username
Password - HPOO Basic Authentication Password
SSL Verify Host / Peer - Occasionally when testing a machine that only has a self signed certificate these need to be unchecked.
Once created a Test Connection button will appear allowing you to test the connection details before using them inside an Cloud Automation Node.

Firewall
Typically a Firewall change will be needed for your Instance to communicate back to your HPOO instance:

Our outbound IP address:
European Data Center - 87.117.243.10
North American Data Center - 69.174.241.48
Port: 8443
Invoking Orchestration Flows
Using the Business Process Designer and the Cloud Automation node you can invoke any of your defined Orchestration Flows from your configured HP Operations Orchestration instances within your business processes

Content Pack
As well as having the option to invoke your Runbooks from a business process we have provided a Content Pack for HPE Operations Orchestration 10.50+, to demonstrate integration with the Hornbill Collaboration platform and Service Manager application.

This can be used to enable HPEOO administrators to include Hornbill Collaboration and Service Manager automations in their flow orchestrations.
Download the Hornbill Content Pack following the instructions in the HP Operations Orchestration Content Pack from the Related Articles Section.