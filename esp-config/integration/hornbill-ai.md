---
description: This guide covers the configuration and implementation of HAi (Hornbill AI) features within your environment. The document outlines step-by-step instructions on enabling HAi capabilities for your user account, specifying the necessary roles, and accessing the necessary settings in Hornbill.
coverImage: /_books/esp-config/images/hai-cover.jpg
layout: article-toc
---

# HAi Services

HAi (Hornbill AI) is a suite of generative AI tools built into the Hornbill platform. The platform integrates with AI service providers such as OpenAI and Azure AI to help you work more efficiently.

## Before you begin

To use HAi services, you must meet the following requirements:

* **Register for the closed beta program.** HAi features are currently in a closed beta. You can only access these features after you register. Contact your Hornbill customer success representative to join the program.
* **Review fundamentals.** Read the [HAi fundamentals](/esp-fundamentals/core-capabilities/integration/hai-services) documentation to understand the core concepts.

### Required roles

To manage HAi configurations on your instance, your user account must have the following roles:

| Role | Description |
| :--- | :--- |
| **Admin** | Provides administrative functionality for the Hornbill platform. Only grant this role to platform administrators. |
| **HAi Manager** | Provides permissions to manage HAi configurations. |

## Accessing HAi Services

### Steps

1. Select **Configuration** (cog icon) in the lower-left corner of the interface.
2. Select the dropdown menu in the top-right corner and choose **Platform Configuration**.
3. Locate the **Integration** section in the side menu and select **HAi Services**.

![HAi Services menu option](/_books/esp-config/integration/images/hai-services-menu-option.png)

## Dashboard

The dashboard provides real-time metrics to help you monitor how your organization uses Hornbill AI. For every interaction, the system calculates an approximate "time saved" value in minutes. The dashboard aggregates these minutes into hours and converts them into financial savings based on your organization's specific hourly rate.

The dashboard highlights time and financial savings for the last 30 days and provides a comparison to the previous 30-day period. You can also track usage trends through a monthly view covering the last 12 months.

### Savings calculations

Each Hornbill AI feature includes a specific savings calculation. When you use a feature, the system evaluates the time saved in real time and stores the value in the Usage Log as minutes.

The calculation logic depends on the specific task performed.  For example:

* **Summarizing requests:** The system calculates time saved based on the length of the request history and the average human reading rate.
* **Generating content:** The system calculates time saved based on the amount of text generated and the average human typing rate.

### Settings

You can customize the values on your dashboard by updating the following settings. These settings allow you to align the financial reporting with your local currency and internal costs.

| Setting | Description | Default |
| :--- | :--- | :--- |
| `generativeAi.dashboard.currencySymbol` | The currency symbol used to display financial savings. | £ |
| `generativeAi.dashboard.ratePerMinute` | The lowest Full Time Equivalent (FTE) cost per minute based on your currency. | 0.2 |
| `generativeAi.dashboard.readingRate` | The average number of characters a user reads per minute. | 900 |
| `generativeAi.dashboard.typingRate` | The average number of characters a user types per minute. | 150 |

## Usage Log

The HAi Usage Log provides a record of your organization's AI activity over the last 30 days. The log displays the most recent 1,000 entries to help you track performance, monitor volume, and manage costs. You can filter these logs by **User**, **Product Area**, and **Prompt**.

The **Tokens** values for input and output indicate the volume of text processed and generated. These values populate your dashboard to help calculate business savings. Use the **Detailed Log** to view unformatted input and output payloads, which is helpful when you need to troubleshoot formatting errors.

### Log details

The usage log includes the following information:

* **Action**: The specific location in the Hornbill product where the action started.
* **Prompt**: The specific Hornbill AI function that was triggered.
* **User**: The individual who triggered the action. For actions triggered by the **Auto Responder** or a **Business Process**, the log displays **System** as the user.
* **Tokens**: The size of the request (input) and response (output) measured in tokens.
* **Status**: The outcome of the action. Statuses include **Presented**, **Accepted**, **Rejected**, or **Error**. This shows if the result was returned to the user and whether they used or ignored it.
* **Detailed Log**: The exact payload sent to the Service Provider and the resulting response. System prompts sent to the provider are not included in this log.

### Retention

The user interface currently displays logs from the last 30 days. Although the system currently retains all log history, future updates will change how data is stored. In the future, the system will prune the input and output text after 30 days and only the specific details of the request will remain.

### Monitoring

HAi logs usage data so you can demonstrate the value added to your business and troubleshoot technical issues. Hornbill occasionally reviews these logs to monitor usage trends and improve the quality of prompt outputs.

Hornbill maintains customer data confidentiality. The Hornbill AI Team anonymizes any logs they review before removing them from your customer instance. For more information, see section 6 of the [Hornbill Subscription agreement](https://www.hornbill.com/subscription-agreements).

## Providers

Hornbill integrates with AI service providers such as OpenAI and Microsoft Azure. The Hornbill ESP integration layer connects these AI services to Hornbill applications and features. This architecture allows you to choose specific providers and models that meet your organization's requirements.

The Hornbill ESP platform provides a point and click interface to configure these integrations. The platform uses real-time result streaming to ensure a responsive experience when you use HAi features.

### Available providers

The following HAi service providers are available for selection:

| Provider | Usage | Description |
| :--- | :--- | :--- |
| OpenAI (US International) | Free | Data is processed in OpenAI data centers located in the United States. Hornbill manages the costs for all usage with this provider. |
| OpenAI (Customer Provided) | Premium | You provide credentials for your own OpenAI account. This option provides full access to OpenAI service reporting, statistics, and usage controls. |
| Microsoft Azure (US) | Premium | Data is processed in Microsoft Azure data centers located in the United States. Hornbill manages the costs for all usage with this provider. |
| Microsoft Azure (EU) | Premium | Data is processed in Microsoft Azure data centers located in the European Union. Hornbill manages the costs for all usage with this provider. |
| Microsoft Azure (Customer Provided) | Premium | You provide credentials for your own Microsoft Azure account. This option provides full access to Microsoft Azure AI reporting, statistics, and usage controls. |
