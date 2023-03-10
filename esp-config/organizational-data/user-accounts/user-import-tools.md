---
layout: article-toc
---
# User import and synchronization tools
The most common way of managing accounts is by using an import and synchronization tool.  These include LDAP Import, Azure Import, Database Import, and Google User Import.

## Azure User Import Utility
The utility provides a simple, safe and secure way to create user accounts on the Hornbill platform by synchronizing with accounts held in your Azure AD. The tool is designed to run behind your corporate firewall, connect to your Azure instance, query the required account information, transform and load into the Hornbill instance. The tool connects to the Hornbill and Azure instances in the cloud over HTTPS/SSL so as long as you have standard internet access then you should be able to use tool without the need to make any firewall configuration changes. The tool supports both the initial bulk import as well as incremental adds and updates. You can schedule the tool to run periodically to perform the import/update tasks as required.

The utility employs the Azure Graph API to query the contents of Azure AD. If you would like to know more about this API and it's capabilities, please refer to the relevant Microsoft documentation

## LDAP User Import Utility
The utility provides a simple, safe and secure way to create new Hornbill User Accounts and update existing ones by synchronizing with accounts held in your Active Directory or other industry standard LDAP capable directory service. The tool is designed to run behind your corporate firewall, connect to your LDAP service, query the required account information, transform and load into the Hornbill instance. The utility does not write back to your directory, it is purely designed to read data from the directory and use this to populate Hornbill user information during the creation of new and update of existing Hornbill User accounts.

The tool connects to the Hornbill instance in the cloud over HTTPS/SSL so as long as you have standard internet access then you should be able to use tool without the need to make any firewall configuration changes. The tool supports both the initial bulk import as well as incremental adds and updates. You can schedule the utility to run periodically to perform the import/update tasks as required.

The LDAP Utility can be used as a stand-alone alternative to, or supplement user auto-provisioning. While auto-provisioning requires Single Sign On (SSO) configuring, the LDAP import utility is completely independent of any SSO configuration.

## SQL User Import Utility
The utility provides a simple, safe and secure way to create user accounts on the Hornbill platform by synchronizing with accounts held in your Database. The tool is designed to run behind your corporate firewall, connect to your database, query the required account information, transform and load into the Hornbill instance. The tool connects to the Hornbill instance in the cloud over HTTPS/SSL so as long as you have standard internet access then you should be able to use tool without the need to make any firewall configuration changes. The tool supports both the initial bulk import as well as incremental adds and updates. You can schedule the tool to run periodically to perform the import/update tasks as required.

## Google Workspace User Import Utility
The utility provides a simple, safe and secure way to create user accounts on the Hornbill platform by synchronizing with accounts held in your Google Workspace domains. The tool is designed to run behind your corporate firewall, safely and securely connect to Google via your Hornbill instance, query the required account information, transform and load into the Hornbill instance. The tool connects to the Hornbill in the cloud over HTTPS/SSL so as long as you have standard internet access then you should be able to use tool without the need to make any firewall configuration changes. The tool supports both the initial bulk import as well as incremental adds and updates. You can schedule the tool to run periodically to perform the import/update tasks as required.