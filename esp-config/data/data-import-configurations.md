---
layout: article-toc
---
# Data Import Configurations
Hornbill Administration provides an interface which allows you to quickly and easily configure your data import utilities. The configuration is securely stored and access to modify the configuration is governed by Hornbill's range of security roles. Where applicable, any details required to connect to your data sources are stored in Hornbill's KeySafe, adding an extra layer of protection when storing server/database credentials.

Currently, the LDAP user import is configured using this interface. Over the coming months, new versions of Hornbill's open-source import utilities will be released meaning that ultimately, all data import configurations will be managed from this interface.

## Creating a New Data Import Configuration
While the various data import utilities require you to download an executable to be located, scheduled, and run from within your environment, the configuration is held securely in your Hornbill instance and is created and managed using Hornbill Administration. To begin creating a new configuration, login to Hornbill administration and navigate to Home > System > Data > Data Import Configurations.

Click the button located to the top right of the list to create a new import.
Give your import configuration a name.
Select the type of import to which this configuration will relate.
Add a description to indicate the specific purpose of the import. It is possible to have multiple import configurations for the same type so the description can be a useful reminder as to the specific purpose.

## Types of Data Import Configuration
The type of Data Import configuration that is selected determines the interface that is presented to you. Currently, only the LDAP user import utility (version 3.0 or later) supports this new interface.

Read the [LDAP Import Utility Documentation](/data-imports-guide/users/ldap/overview) for more information.