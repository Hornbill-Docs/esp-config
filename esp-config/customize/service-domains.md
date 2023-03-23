---
layout: article-toc
---
# Service Domains
Service Domains are used to define business areas where related services will be made available to users who will consume the services. Different Hornbill Apps have the ability to define their own Service Portfolio and the services that can be offered. Each of these services can then be allocated to a Service Domain. Examples of Service Domains may include IT, HR, and Facilities.

## Role
Users will need the Service Domain Administrator role, in order to manager Service Domains

## Details

### Name/Description
* **Service Domain ID**<br>This is a unique identifier for the Service Domain. When adding a new Service Domain, this cannot be the same value as any other existing Service Name
* **Language**<br>This is to provide translations into different languages. This will provide translations to a user, based on the language specified in their user profile. The Default language is used in the situation where a user has a language set in their profile, but translations for that language have not been provided.
* **Name**<br>This is the Name of the Service Domain which will be displayed to the users within the Header of the home page.
* **Description**<br>The Description field can be used to make a note about the use or purpose of the Domain. At the moment this is not displayed to the customer on any of the pages.

### Settings
* **Catalog**<br>This setting allows you to link the Service Domain to an existing Catalog.
* **Icon**<br>This associates an icon to this particular Domain. This icon maybe be visible within some of the different company pages
* **Enabled**<br>Once enabled, this Service Domain will be available on the company page. However, it will not become visible until there is a Domain Page created for it.
* **Public**<br>If marked as public, the domain page linked to the domain, will be visible to all employee irrespective if they are subscribed to services linked to the domain.
If not marked as public, the linked domain page will only be visible to employees who are subscribed to services which are linked to the domain
* **System Domain**<br>This a read only setting that distinguishes between Service Domains that are provided by Hornbill and those that are manually created by you. System Domains cannot be deleted.

## Domain Categories
A domain category allows you to associate one or more services to the category. This will allow for improved organization and navigation of Services when there are a large number of services available under a Service Domain. Each Category has the following options

* **Language**<br>This is only displayed after the category has been created. When a category is first created it populates the Default Language with the Name and Description. After the category has been saved, you can edit the category to create the language variations that are needed.
* **Name**<br>The name displayed to the users on the company pages
* **Description**<br>Hint text that is displayed to users on the company pages

## Domain Owners
Domain Owners are given the rights to create and manage the pages that are displayed under this domain.

* **Add Owners**<br>Type the name of the user that you with to make the owner. More than one owner can be assigned to a service domain. Admin users also need to be added if they wish to manage pages for this domain.
* **Remove Owners**<br>Remove owners who are no longer needed access to manage the domain page.

::: tip
Any service that exist in an application such as Hornbill Service Manager can be associated to a service domain using the appropriate fields that appear in the service details when creating or managing a service via the Service Portfolio. It's also possible to set a "Service Domain Category" too.
:::