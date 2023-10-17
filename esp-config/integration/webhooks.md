---
layout: article-toc
---
# Webhooks
Webhooks are a great way to integrate Hornbill with other applications that are accessible over the internet. webhooks can send information from Hornbill to another application as soon as a record is updated, rather than relying on scheduled imports or continually polling for data.

A webhook is the opposite of an API call, a webhook is a call over HTTP from your Hornbill instance to a web endpoint of your choosing. Most application actions on a Hornbill instance can trigger an action-specific event when an action is performed. Hornbill can be configured to call to a web endpoint passing the action-specific data to the web service being invoked. This is a very powerful mechanism that enables true, near real-time integration with other business systems.

## Before You Begin
* Read and understand the [fundaments of Web Hooks](/esp-fundamentals/core-capabilities/integration/web-hooks)

## Basic Information
* **Name**<br>Unique name used to identify the Web Hook in the list. This is a mandatory field. No spaces allowed.
* **Description**<br>Enter a description to allow others to understand the use of this particular Webhook.
* **Application**<br>Select the Hornbill application where the event is coming from
* **Event Source**<br>Select the event
* **Enabled**<br>Enable or disable this Webhook. This can also be done from the main list of Webhooks
* **Authentication**<br>If the webhook endpoint you are calling requires authentication then you need to create the required credentials in your KeySafe, then, when configuring you web hood you can select the credentials here. 

## Web Hook Target
* **URL**<br>The target URL for the Web Hook. The URL depends on whichever system or platform where you webhook resides. 
* **Payload Format**<br>This defines the format of how you would like the data to be received. This can either be XML or JSON
* **Post Mode**
    * **Asynchronous**<br>Call the webhook in the background.  If you do not need to act on the response from the webhook being called, this is the recommended mode to ues because any latency or performance issues in the webhook being called will nor be reflected in the Hornbill User Interface. 
    * **Synchronous**<br>Use this mode if the webhook you call needs to return a response. If a response code other than 200 is returned from the webhook URL, then the action/api call that originated the event may fail.  If there is a non-200 response code, and, if the webhook endpoint returns a response body, and the content-type=text/plain, the response body text will be returned as the error message to the caller that fired the webhook. 
    * **Synchronous Critical**<br>This is the same as Synchronous but it also mandatory that the webhook being called returns a 200 success response.  If not, then whatever caused this event to be fired will fail and throw an error. 

## HTTP Protocol Information
Your web hook must accept a POST verb with either XML or JSON content as the payload (set by webhook properties). For pre-action hooks such as OnCreate, OnUpdate and OnDelete asyncCritical types it is possible to send an error message from your web hook back to the user's screen. To do this simply respond with a 403 response code, set the Content-type: header to text/plain and the actual text message you want to return to the user's display in the response body, the response body should be returned as UTF-8 encoded bytes if non-ascii content is required.

## Testing and Examples
### RequestBin Test
The [RequestBin] web site is a third party tool that generates a temporary URL that allows you to collect requests made to it and lets you inspect them in a human-friendly way. Use RequestBin to see what your HTTP client is sending from Hornbill.

:::note
As RequestBin is a third party tool, Hornbill is not responsible for the availability, quality, security, or any other aspect of this tool
:::

#### Create a Request Bin
After creating your Webhook in Hornbill you can test it using the following steps:
1. Go to the web site http://requestb.in
1. Click on the Create a RequestBin button
1. Copy the Bin URL and save it under the URL field in the Web Hook target section of your Hornbill Webhook configuration.
1. Create a new Request in Hornbill Service Manager
1. Refresh the RequestBin page
1. The information from your request should be visible in the format you configured.

### Example Integration
An example to reading the JSON payload from a webhook can be found on GitHub - The code is available for use under the Hornbill Community License.

<!-- References>
<!-- https://wiki.hornbill.com/index.php?title=Webhooks>

<!-- To Do>
<!-- Links to github for example>