# Contacts
This view of the contact provides an extra administrative layer to the [Contacts View](/esp-user-guide/customers/contacts) that is available to platform users.

These two views share these same options.
* Add contacts.
* Archive contacts.
* Update contact records.

## Customer Portal Access
Unique to the contact view in Configuration is the ability to manage contact access to the [Customer Portal](/esp-config/customize/customer-portal/configure-customer-portal).

![Contact Access Options](/_books/esp-config/images/contact-guest-access-options.png)

* **Associate to Portal**. Associate the selected contact records to the Customer Portal. This is required for the contact to login to the customer portal. 
* **Set Login ID**. Set a unique ID that the contact will use to login to the customer portal. To login to the Customer Portal, the contact must have a Login ID. Once a contact has been provided a Login ID, the email address that is specified on their contact record can also be used to login. When adding a Login ID, it will validate that it is unique against existing Login IDs and Email Addresses of all contacts.
* **Set Password**. This includes an option to generate a random password.  Passwords should be communicated securely to the contacts. Alternatively, the contact can use the **Forgot Password** option on the Customer Portal login screen.
* **Set Two-factor Authentication**. Each contact can be set to use either email or the Microsoft Authenticator app for two-factor authentication.  

:::tip
These actions can also be done from the [Customize Customer Portal](/esp-config/customize/customer-portal/configure-customer-portal#contact-access) page.
:::