# External Authorization
The external authorisation node can be used to allow an email recipient to receive an authorisation decision, provide an outcome and automatically progress a business process

## Configuring An External Authorisation
* **To:**<br>Specify a single email address, this can be a static email address or using the variable picker, a variable email address can be used
* **Subject:**<br>Configure the subject line for the outbound email, where required use the variable picker to include the relevant entity data
* **Authorisation Details:**<br>Include the information that is relevant to the recipient, which will give them the information for the decision they are being asked to authorize, again use the variable picker to inject relevant entity data (1024 Character Limit).
* **Outcomes:**<br>By default two outcomes are provided :- Authorize and Reject, one additional outcome can be added if required (3 Max). Optionally configure each outcome:
    * To change the display label
    * To change the color of the outcome button
    * To mandate if a supporting reason is required when a specific outcome is chosen
* **Expire After:**<br>Configure a period in Days, Minutes, Hours after which the node will expire if an outcome has not been received from the recipient.
    * The default setting is 3 Days
    * An expiry value has to be defined, if it is left blank, 3 Days will be used.

## External Authorisation Delivery
The external authorization email will be sent to the recipient using a preset email and using direct outbound.

* The From address can be configured on the node
* If the From address is not specified, the node will use the from address as <INSTANCENAME>-mail@live.hornbill.com
* It is not possible to choose or configure the email template
* The email is available in English only

:::tip
Please ensure you have the live.hornbill.com domain set up in your outbound routing rules:
Admin console > System > Email > Outbound Routing Rules
:::

## Completing An External Authorisation
When a recipient receives an external email authorisation, the email will contain a link to a web page, where the recipient can review the details contained in the Authorisation Details, and will be presented with the configured outcomes.

![External Authorization](/_books/esp-config/images/external-authorization-email.png)

* The recipient does not need to login to any interface to complete their external authorization
* The web page is currently available in English
* The recipient needs to select an outcome to progress the external authorisation
* If a reason has been mandated for the chosen outcome, the recipient will be required to provide the reason before completing the external authorization
* On submission of the outcome, the recipient will see confirmation of their decision, and the business process will resume. It is critical to follow an external authorization with a Decision node, which is subsequently configured with branches which cater for all possible outcomes including Expired. If you have used the option to have an additional outcome you will need 2 chained Decision nodes to cater for all possible outcomes.
* The outcome of an external authorization is not automatically written to the entity activity stream, which the process it is used in, is running against. In the case of a request in Service Manager, the process designer can use a Update Request > Post to Timeline node after an external authorisation and use the variable picker to include values such as the external authorization outcome, and any supporting reasons as output params from the External Authorisation node.

![External Authorization](/_books/esp-config/images/completing-external-authorization.png)

<!-- https://wiki.hornbill.com/index.php?title=External_Authorisation -->