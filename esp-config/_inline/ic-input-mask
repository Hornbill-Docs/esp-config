# Defining Input Mask

Adding masking to input will enforce user to provide value in expected format.

## Default masking definitions

Mask special characters:
|Name                | Description |
|--------------------|-------------|
|**9**           | numeric |
|**A**           | alphabetical |
|**\***           | alphanumeric |
|**[]**           | optional |

Any other character is just displayed in pattern.
There are also predefined ready to use mask aliases:

|Name                | Description |
|--------------------|-------------|
|**decimal**           | allow to enter number eg. 123 or 123.12 |
|**integer**           | allow to enter integer number eg. 123 |
|**email**           | enforce to enter only valid email |
|**ip**           | ip address eg. 123.123.123.123 |
|**percentage**           | only number from 0 to 100 is allowed |
|**url**           | enforce valid url address that starts with http(s) |


## Examples:

Full phone number leading with country number: <br />
``+(99[9]) 999-999-999[9]`` <br />
[] means that content inside it optional. 

Valid values: <br />
**+(44) 123-456-789** <br />
**+(044) 123-456-789** <br />
**+(44) 123-456-7890** <br />
**+(044) 123-456-7890**

Another example with UK number plates: <br />
``AA99 AAA``

Valid values: <br />
**BD51 SMR** <br />
**ZY13 XYZ**
