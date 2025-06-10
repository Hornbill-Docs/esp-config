---
layout: article-toc
---
# Webhooks
Webhooks are a great way to integrate Hornbill with other applications that are accessible over the internet. Webhooks can send information from Hornbill to another application as soon as a record is updated, rather than relying on scheduled imports or continually polling for data.

A webhook is the opposite of an API call; a webhook is a call over HTTP from your Hornbill instance to a web endpoint of your choosing. Most application actions on a Hornbill instance can trigger an action-specific event when an action is performed. Hornbill can be configured to call to a web endpoint passing the action-specific data to the web service being invoked. This is a very powerful mechanism that enables true, near real-time integration with other business systems.

## Before you begin
* Read and understand the [fundamentals of webhooks](/esp-fundamentals/core-capabilities/integration/web-hooks).

## Available event sources
Each application defines the webhook event sources it wants to make available, and each event source will include a data payload that is driven by the application's specific data model.  Therefore, to understand what data should be available for each event source, you need to refer to the specific application's configuration documentation. 

## Basic information
* **Name.** Unique name used to identify the webhook in the list. This is a mandatory field. No spaces allowed.
* **Description.** Enter a description to allow others to understand the use of this particular webhook.
* **Application.** Select the Hornbill application where the event is coming from.
* **Event Source.** Select the event.
* **Enabled.** Enable or disable this webhook. This can also be done from the main list of webhooks.
* **Authentication.** If the webhook endpoint you are calling requires authentication, then you need to create the required credentials in your KeySafe. Then, when configuring your webhook, you can select the credentials here.

::: important
Hornbill Webhooks only support **HTTP Basic** type authentication, so you will only be able to select Keysafe Keys of type **HTTP Basic Authentication (Username + Password)** against your webhooks.
:::

## Webhook target
* **URL.** The target URL for the webhook. The URL depends on whichever system or platform where your webhook resides. 
* **Payload Format.** This defines the format of how you would like the data to be received. This can either be XML or JSON.
* **Post Mode.**
    * **Asynchronous.** Call the webhook in the background.  If you do not need to act on the response from the webhook being called, this is the recommended mode to use because any latency or performance issues in the webhook being called will not be reflected in the Hornbill user interface. 
    * **Synchronous.** Use this mode if the webhook you call needs to return a response. If a response code other than 200 is returned from the webhook URL, then the action/API call that originated the event may fail.  If there is a non-200 response code, and, if the webhook endpoint returns a response body, and the content-type=text/plain, the response body text will be returned as the error message to the caller that fired the webhook. 
    * **Synchronous Critical.** This is the same as Synchronous but it is also mandatory that the webhook being called returns a 200 success response.  If not, then whatever caused this event to be fired will fail and throw an error. 

## HTTP protocol information
Your webhook must accept a POST verb with either XML or JSON content as the payload (set by webhook properties). For pre-action hooks such as OnCreate, OnUpdate, and OnDelete, Synchronous Critical types, it is possible to send an error message from your webhook back to the user's screen. To do this, simply respond with a 403 response code, set the Content-type: header to text/plain and the actual text message you want to return to the user's display in the response body. The response body should be returned as UTF-8 encoded bytes if non-ASCII content is required.

## Testing your webhook
### RequestBin test
The [RequestBin](https://pipedream.com/requestbin) website is a third-party tool that generates a temporary URL that allows you to collect requests made to it and lets you inspect them in a human-friendly way. Use RequestBin to see what your HTTP client is sending from Hornbill.

:::note
As RequestBin is a third-party tool, Hornbill is not responsible for the availability, quality, security, or any other aspect of this tool.
:::

After creating your webhook in Hornbill, you can test it using RequestBin.

**To test your webhook:**
1. Go to the website https://pipedream.com/requestbin
1. Click the **Create a RequestBin** button.
1. Copy the bin URL and save it under the URL field in the Webhook Target section of your Hornbill webhook configuration.
1. In Hornbill Service Manager, create a new request.
1. Refresh the RequestBin webpage.
1. The information from your request should be visible in the format you configured.

## Example integration
An example of reading the JSON payload from a webhook can be found on GitHub. The code is available for use under the Hornbill Community License.

<!-- References>
<!-- https://wiki.hornbill.com/index.php?title=Webhooks>

<!-- To Do>
<!-- Links to github for example>