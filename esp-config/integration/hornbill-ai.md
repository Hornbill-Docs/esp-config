---
description: This guide covers the configuration and implementation of HAi (Hornbill AI) features within your environment. The document outlines step-by-step instructions on enabling HAi capabilities for your user account, specifying the necessary roles, and accessing the necessary settings in Hornbill.
coverImage: /_books/esp-config/images/hai-cover.jpg
layout: article-toc
---

# Hornbill AI

To manage any aspect of Hornbill AI on your instance, your User Account must be associated with the following roles:

|Role|Description|
|-|-|
|Admin|This role provides administrative functionality to the Hornbill platform and should only be granted to an administrator.|
|HAi Manager|This role should only be used for managing HAi configurations.|

**Note:** Applications may extend Hornbill AI functionality and have addition roles to manage application specific settings.

## Value Dashboard

The value dashboard shows real time metrics for monitoring the usage of Hornbill AI, each use calculates an approximate time saved value in minutes to represent how much time using the capabilities of Hornbill AI has saved the individual. The dashboard rolls this up into hours saved and using a setting for defining the hourly rate converts to a financial savings for your organizations. Time and Financial savings are then highlighted on the dashboard for the last 30 days with a comparison to the previous 30 days as well as being tracked monthly for the last 12 months.

### Savings Calculations

Every feature within Hornbill AI has a distinct savings calculation built in which is evaluated in real time and stored in the Usage Log, as minutes. An over simplification would be that based on each task i.e summarizing a request or generating a customer reply, and estimate of the time saved is calculated using the size of the request being summarized or the amount of text generated.

For example, a long request being summarized uses the length of text that makes up the request history being summarized and the average rate at which a human can read and understand text to get an approximate value for time saved.

### Settings

The following settings can be updated to customize the value dashboard;

|Setting|Description|Default|
|-|-|-|
|generativeAi.dashboard.currencySymbol|Currency to use when displaying value saved based on ratePerMinute.|£|
|generativeAi.dashboard.ratePerMinute|Lowest FTE cost per minute based on currency from currencySymbol.|0.2|
|generativeAi.dashboard.readingRate|Average characters per minute reading a document.|900|
|generativeAi.dashboard.typingRate|Average characters per minute when typing a document.|150|

## Usage Logs

The HAi Usage Logs show the last 30 days' usage with the latest first limited to 1000 rows. These logs can be filtered by User, Product Area, and Prompt. The Tokens Input/Output are an indication of the volume of input and text generated as an output when using prompts - and are the values that supply the dashboard with savings. Accepted is whether the output was accepted after generation or not. The Detailed Log allows you to view the unformatted input and output and is very useful for debugging output formatting errors.
![Hornbill AI Logs](/_books/esp-config/images/hai-cover.jpg)

The following information is highlighted in the usage log;

- **Action** - Label given to where in the Hornbill product the action was triggered from.
- **Prompt** - The function of Hornbill AI Triggered.
- **User** - The user who triggered the usage, for Auto Responder triggered actions or Business Process actions the System user will be displayed.
- **Tokens** - The size of the request and response in tokens.
- **Status** - The status of the action showing if it was returned to the end user and ignored or accepted/rejected or even if there was an error (Presented,Accepted,Rejected,Error).
- **Detailed Log** - Exact payload sent to the Service Provider and what was the response, System prompts to the provider are omitted from this log.

### Retention

Currently all log history is kept, the UI restricts logs to the last 30 days and in the future the input and output text will be pruned after 30 days leaving only the details of the request.

### Monitoring of Logs

Unlike AI-Assist which does not log its usage, HAi Usage is logged so customers can demonstrate the value being added to their business and debug issues. Hornbill will from time to time use these logs for both usage monitoring as well as improve the quality of the prompts output and to improve the overall service. Customer data confidentiality is maintained and any logs viewed by the Hornbill AI Team are anonymized before being removed from the customer Instance. Details can be found in section 6 of the [Hornbill Subscription agreement](https://www.hornbill.com/subscription-agreements).

## HAi Service Providers

The Hornbill provides seamless integration with available AI Service Providers, including OpenAI and Azure AI. Hornbill ESP's integration layer makes AI services available to applications and features in Hornbill in a way that is abstracted from any specific AI service provider.  This allows each customer to choose specific AI services providers and in some cases even specific AI models.  The Hornbill ESP platform makes integration with AI service providers a simple point and click exercise, we implement real time result streaming providing modern real-time service integrations for optimal user experience when making use of HAi features.  

### Available Providers

The Following HAi Service Providers are currently available (as of 11/2024):

|Provider|Usage|Description|
|:--|:--|:--|
|OpenAI (US International)|Free|Data is processed on OpenAI's international servers, which basically means in the US data centers. Hornbill picks up the bill for all usage for this service provider option|
|OpenAI (Customer Provided)|Premium|You can choose to provide credentials to your own registered OpenAI account, which gives you full access to the OpenAI services reporting, statistics and usage restrictions controls that the OpenAI service provides.|
|Microsoft Azure (US)|Premium|Integration with AI Services provided by Microsoft, with all data processing done in US data centers operated by Microsoft. Hornbill picks up the bill for all usage for this service provider option|
|Microsoft Azure (EU)|Premium|Integration with AI Services provided by Microsoft, with all data processing done in EU data centers operated by Microsoft. Hornbill picks up the bill for all usage for this service provider option|
|Microsoft Azure (Customer Provided)|Premium|You can choose to provide credentials to your own registered Microsoft Azure account, which gives you full access to the Microsoft Azure AI services reporting, statistics and usage restrictions controls that the Microsoft Azure AI service provides.|

You can find HAi Service Providers by selecting the Cog in the lower left, switching the drop down in the top right to **Platform Configuration** and selecting **HAi Services** under Integration, you will need the **Admin Role** or a custom role with **Mange Integrations System Rights** to access this view.

![HAi Service Providers](/_books/esp-config/images/hai-service-providers.png)

:::note
HAi Premium services (upcoming) will available for free, on request, only while the HAi Services and features are available in the beta program, please talk to your account manager when these services become available.
:::
