---
layout: article-toc
---
# Installing An App
Hornbill includes an App Store where apps can be installed, updated, and removed. Applications are categorized under Installed, Premium, and Free. By clicking on each available application you are able to view the details of that application.

## Topics Covered
* How to install an app.
* Providing access to an app using roles.
* Basic app management.

## Before You Begin
* Admin user access is required.
* General knowledge of using [Configuration](/esp-config/getting-started/using-configuration).

## Installing Apps In The App Store
The Hornbill App Store is a place where one can go to browse, install, and remove applications on Hornbill. Applications are categorized under Installed, Premium, and Free. By clicking on each available application you are able to view the details of that application.

1. Open [Configuration](/esp-config/getting-started/using-configuration) and search for *Hornbill App Store*.
1. Select one of the apps from the group of free apps.
1. Click on the `Install` button to start the installation.

![Hornbill App Store](/_books/esp-config/getting-started/images/app-store.png)

::: note
Premium apps can be installed at any time, however, subscription licenses must be applied before any users can be given access to the app.
:::

## Learn About Updates
Our platform and applications are continuously and automatically updated to ensure that all of our customers always have the latest features and fixes.  This is done automatically without any service downtime and we guarantee that all customizations and integrations will continue to work.

When a new update of an installed application is available, a notification will be displayed in the Hornbill App Store. Applications are automatically updated during the maintenance window (0530 UTC Mon-Fri). If you wish to apply the update before the maintenance window, you can proceed with applying the update immediately by clicking on the `Update` button.

1. Open [Configuration](/esp-config/getting-started/using-configuration) and search using the name of the application.  For example **[Hornbill Board Manager](/boardmanager-config/index)**.
1. In the results list under the section Hornbill App Store, select the application
1. Click on the `Update` button.

:::tip
The update button will only show if there is an available update to apply. If the update button is visible, you can expect the update to be automatically applied that same day during the maintenance window, without having to click on the `Update` button. 
:::

##  How To Manage Subscriptions
The Hornbill Solution Center provides information about your subscriptions for the different apps.  Here you can add and remove users from a selected app while keeping track of how many available subscriptions you have.

1. From the Configuration navigator, select Hornbill Solution Center.
1. Under Subscription select `Your Usage`.
1. Select `Application Subscriptions`.
1. Under the subscriptions column, click on the subscription counter to view and modify the list of subscribed users.

::: tip
Users can also be allocated subscriptions through role assignments.  If you assign a user to an application role that has a privilege level of **user** a subscription will be allocated to that user when they next log in.
:::

## Uninstalling An App
If you happen to have an application installed that you no longer need, it can be removed with a click of a button. Have you uninstalled it by mistake? Not a worry...your data is intact. Re-install and start from where you left off.

1. Search [Configuration](/esp-config/getting-started/using-configuration) for the application name.
1. In the results list under the section Hornbill App Store, select the application.
1. Click on the `Uninstall` button.

<!-- To Do -->
<!-- Setting to stop subscription to be automatically added when roles applied allocateOnLogin -->