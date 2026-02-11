---
layout: article-toc
---
# Direct Outbound Email

Direct outbound email serves as a sent items folder for emails sent from Hornbill without using a configured mailbox. Use this list to monitor and review all outbound messages sent directly from the platform.

Types of Direct Outbound Emails

* [Workflow Authorizations](/esp-config/automation/authorization)
* [Workflow External Authorizations](/esp-config/automation/external-authorization)
* [Workflow Direct Messages](/esp-config/automation/hornbill-automations#email)
* [Report Delivery](/esp-config/reporting/reports#schedule)

## Delivery Status

The delivery status column shows the status of each individual email.  Using the filters, the list can be set to show only emails with a selected status, such as **Failed**

## Viewing the email

You can click on either the Message ID or the Subject to view the email.

### Recipient delivery status

When viewing the email the delivery status is displayed for each recipient as a colored envelope.

* White - pending
* Green - delivered
* Red - failed

You can click on each envelop and use the following options.

* **Delivery status:** This will display a detailed log of the delivery status.
* **Resend:** If an email has not been sent due to a temporary issue that has since been fixed, you can use the `Resend` option to try to send the email again. After selecting `Resend` the email status will change to pending.
