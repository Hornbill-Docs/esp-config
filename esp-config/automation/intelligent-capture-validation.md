# Intelligent Capture Design Validation and Errors
The Intelligent Capture Design Canvas offers the ability to validate a capture flow on or before activation. Any warnings or errors will be displayed in the bottom right of the design canvas. General information messages may also be displayed in certain circumstances.

## Information Messages

![Information messages are light blue](/_books/esp-config/images/form-option-updates.jpg)

Information messages will be displayed in light blue.

### Form Option Updates
Message Content: "Some form setups are out of sync with the latest schema. They have been automatically modified, but you are required to manually save and activate the process for the modifications to go live."

What it means: This message refers to default progressive capture forms (blue nodes) shipped with each Hornbill application. It does not concern custom forms (purple nodes). It indicates that there have been enhancements made to the default forms in a previous application update, but to take advantage of these changes, the flow must be saved and activated.

## Warning Messages

![Warning messages are yellow](/_books/esp-config/images/process-warnings.jpg)

Warning messages will be displayed in yellow. A warning message may not have a detrimental effect on a progressive capture design but it's important to identify the reason for the warning and understand if any corrective action is necessary. Some warnings will prevent the flow from being activated, however, others will still allow activation.

## Error Messages
Error messages will be displayed in red. Errors indicate a problem with the design, and a flow cannot be made active when errors exist.