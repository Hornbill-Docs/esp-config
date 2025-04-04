---
layout: article-toc
keywords: data profiles, data profile codes, request profile codes, closure profile codes, resolution categories, request category level, resolution category level
---
# Profiles
Profiles provide hierarchical tree structures that you can use to *categorize* your requests. In fact, *categories* is another commonly used name for profiles. This kind of categorization can help with your analytics and reporting. With profiles, you can group the service areas in which requests are being made; this can be useful, for example, when you want to identify possible reasons for recurrent issues.

Each profile has a code to identify it. There are profiles that can be assigned when a request is opened (a *request profile*) and when it is closed (a *closure profile*). In Service Manager Configuration, the corresponding views are **Request Profile Codes** and **Closure Profile Codes**.

By categorizing requests using profiles and their lower-level items (sub-categories), you can record information at different levels of granularity. For example, for a request in the IT service, you can report on the IT profile, or go more granular into Hardware and then down to the level of Laptop.

In Service Manager Configuration > Administration, you can create profiles as well as import and export profiles. Each time you create a profile, it is given a profile code.

## Topics covered
* [Editor](/esp-config/data/profiles#editor)
* [Profile settings](/esp-config/data/profiles#profile-settings)
* [Adding profiles](/esp-config/data/profiles#adding-profiles)
* [Deleting profiles](/esp-config/data/profiles#deleting-profiles)
* [Importing profiles](/esp-config/data/profiles#importing-profiles)
* [Exporting profiles](/esp-config/data/profiles#exporting-profiles)

## Editor

You can find and configure profiles by navigating to **Configuration > Service Manager > Administration > Request Profile Codes** or **Closure Profile Codes**.

This main view shows all of the existing profiles (categories). Some profiles may have been automatically added through the installation of an application; these are pre-configured and ready for use.

You can use the editor to create the hierarchical structure contained within each profile.

## Profile settings
Click the **Profile Settings** button to specify how your organization's profiles are created. In the *Import Profiles* dialog, you can configure the following settings:
* **Name.** This is preset based on whether the profiles you're configuring are for opening requests or closing them.<br>
**Case-insensitive ordering.** If you want ordering of profile names to happen regardless of lowercase or uppercase, select the checkbox under the Name field.
* **Code Separator.** This separates the hierarchy levels. For example, `IT:Software:Install` uses the colon character as a separator to distinguish the *IT* profile as top-level, with *Software* under it, and with *Install* under *Software*.
* **Name Separator.** This is shown in the UI to users when viewing a request. For example, using the characters `->` as a separator, **IT`->`Software`->`Install`->`Action Taken** could be a closure category assigned to a request when it has been updated.
* **Maximum Code Length.** This specifies the maximum number of characters a code can be created with.
* **Maximum Levels.** This specifies the maximum number of hierarchy levels that can be used when creating codes.
* **Minimum Code Length.** This specifies the minimum number of characters a code can be created with.
* **Code Allowed Chars.** This specifies which characters can be used to create profile codes.

## Adding profiles
Click **+ Top Level Item** to start the process of creating a new profile.

To add a new profile within (under) an existing one, click **+ Item**. This creates what is essentially a subcategory.

## Deleting profiles
Select an existing profile and then in the properties box, click **Delete**.
::: warning
The existing profiles may be in use and deleting them could have an unintended impact.
:::

## Importing profiles

You can use a template (a Microsoft Excel file) to bulk import or bulk update a set of profile codes into your instance.

::: note
When you import profiles, your existing profiles will be overwritten with what's in the code set spreadsheet you're importing from. If you want to add or append new profile codes to your existing code set, you must export your current set, add the new codes to that spreadsheet, then import from that.
:::

The import scheme assumes the data to import will be on the sheet named *Data*. Make sure the data is static data. The data import routines do not consider expressions; nor do they run scripts or formulas in cells to get the resultant data.

**To get the profile code set template:**
1. Click the down arrow attached to the **Import Profiles** button.
1. Select **Download xlsx template**.
1. Follow the guidance provided in the *Information* sheet of the workbook.

**To import profiles:**
1. Once you have made changes to the import template to suit your needs, click **Import Profiles**.
1. In the Import Profiles dialog, click **Upload and import**.
1. Browse for the template you have saved changes to, and click **Open**. 

## Exporting profiles
**To export profiles:**
1. Click the down arrow attached to the **Import Profiles** button.
1. Select your preferred export option for output.