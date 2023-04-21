---
layout: article-toc
---
# Design the user profile
The user profile is made up of a number of sections, each containing a collection of related fields.  These fields can be customized to your requirements.

## Topics covered
* Accessing the user profile designer
* How to design the user profile
* The different types of sections
* Field properties

## Section access
The user profile is separated into 5 sections with the default names of:  
* Basic Details
* Job Details
* Contact Details
* Interests & Expertize
* Personal Details

The bottom three sections have an option that allows a user to decide if they want to share this information to other users when they view their profile.  Each user can select if these sections are public, accessible by followers, or private.

This is important when designing this form as any field that must be displayed to all users needs to be in the top two sections.

::: note
Despite the visibility of the information in these bottom three sections being controlled by the user, apps may have access and the ability to use this information outside of the user's profile.
:::

## Designing the form
To start designing the form, a single button called `Design` needs to be clicked on.

### Moving fields
To change the order or location of a field on a form, use the mouse by pressing and holding the left mouse button on any part of a field and then drag and drop the field to a new location.

Because the visibility of the bottom 3 sections can be controlled by the user, there may be a need to move a field from one of these sections into the top two sections.  Using the mouse, press and hold the left mouse button on any part of the field and drag and drop the field onto a different section.

### Changing field properties
Each field on the user profile has a number of properties that can be changed.  These properties are accessed by clicking on the cog icon located on each field when in design mode.

* Hide or show the field
* Make it mandatory
* Make it read-only
* Add input validation

![User profile field properties](_books/esp-config/customize/images/user-profile-field-properties.png)

### Labels and Translations
As part of designing the user profile form, you may want to change some of the labels or provide translations into different languages.  There are three different ways to achieve this.

* Within the properties of a field you can change the field label.  This change will apply only to the language that you are currently using.  By changing your session language you can update the translations for that language.
* Enable Translation Mode.  This give you a more flexible means to change the field label into other languages directly on the user interface.  This method also provides an option for suggested translations.
* Update the translations using the [User Interface Translations](esp-config/internationalization/user-interface-translations#translations)

:::tip
Many aspects of the user interface are cached for performance.  In some cases a browser refresh may be required to see these changes.
:::  