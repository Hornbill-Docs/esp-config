---
layout: article-toc
---
# User Import and Synchronization
The most common way of managing accounts is by using an import and synchronization utility.  These include LDAP Import, Azure Import, Database Import, and Google Workspace User Import. 

These utilities provide a simple, safe, and secure way to create and update accounts in Hornbill and can be scheduled to run automatically using Windows Task Scheduler.

## Azure User Import Utility
The connects to Hornbill and Azure in the cloud over HTTPS/SSL using a standard internet connection without the need to make any firewall configuration changes. 

:::tip
This utility employs the Azure Graph API to query the contents of Azure AD. If you would like to know more about this API and its capabilities, please refer to the relevant Microsoft documentation.
:::

For more information on installing and configuration please see the [Azure User Import Utility documentation](https://wiki.hornbill.com/index.php?title=Azure_User_Import).

## LDAP User Import Utility
This utility is designed to run behind your corporate firewall to connect to your LDAP service.

The utility connects to Hornbill in the cloud over HTTPS/SSL using a standard internet connection without the need to make any firewall configuration changes.

:::tip
The LDAP Utility can be used as a stand-alone alternative to or supplement user auto-provisioning. While auto-provisioning requires Single Sign On (SSO) configuring, the LDAP import utility is completely independent of any SSO configuration.
:::

For more information on installing and configuration please see the [LDAP User Import Utility documentation](https://wiki.hornbill.com/index.php?title=LDAP_User_Import).

## SQL User Import Utility
This utility is designed to run behind your corporate firewall and connect to your database.

The utility connects to Hornbill in the cloud over HTTPS/SSL using a standard internet connection without the need to make any firewall configuration changes. 

For more information on installing and configuration please see the [SQL User Import Utility documentation](https://wiki.hornbill.com/index.php?title=SQL_User_Import).

## Google Workspace User Import Utility
This utility is designed to run behind your corporate firewall and securely connect to Google Workspace. 

The utility connects to Hornbill in the cloud over HTTPS/SSL using a standard internet connection without the need to make any firewall configuration changes.

For more information on installing and configuring, please see the [Google Workspace User Import Utility documentation](https://wiki.hornbill.com/index.php?title=Google_Workspace_User_Import).