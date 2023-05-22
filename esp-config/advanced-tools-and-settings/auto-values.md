---
layout: article-toc
---
# Auto Values
The Auto Values feature lets an administrator define how auto-generated values, such as reference IDs, are constructed. Places where more than a sequence number (000001234) is required, an Auto Value can be modified to include dates, time, location, teams, user IDs and more. There are many situations where this type of sequence is much more preferable over a simple numeric sequences. Some examples include:

Shipment numbers
Document or Article Reference Numbers
Stock Item Codes
Asset ID's
Access Code numbers
Auto Value Configuration
Description
Add Auto Value Component
Current Value
Daily Increment
Monthly Increment
Yearly Increment
Time last generated
Available Auto Value Component Parts
The following lists of component parts are available to construct an auto value.

seq( z, r )	
Description
A number starting at 1 when the sequence is first used and incremented by one each time the sequence is used and will never be reset for the entire life of the sequence.

seqd( z, r )	
Description
A number starting at 1 at the beginning of each day, and incremented by one each time the sequence is used. This is the daily incremental value for this specific sequence instance.

seqm( z, r )	
Description
A number starting at 1 at the beginning of each month, and incremented by one each time the sequence is used. This is the monthly incremental value for this specific sequence instance.

seqy( z, r )	
Description	
Will be translated into a number starting at 1 at the beginning of each year, and incremented by one each time the sequence is used. This is the yearly incremental value for this specific sequence instance.
The 'z' parameter is optional but if specified indicates the number of leading zero's to display, if not specified then ZERO is assumed. If the number of digits in the resultant value exceeds the number of places defined here, then the left-most digits will be discarded.
The 'r' parameter allows you to specify the base to use when converting the numeric value to a string. The default value if not specified is ten (10), any value between 2 and 36 is valid.

date( [part] )	

Part	Description
year	The current four-digit year (e.g. 2008)
year2	The current two-digit year (e.g. 08)
month	The current two-digit month (01-12)
day	The current two-digit day of the month (01-31)
hour	The current two-digit hour (00-23)
hour12	The current two-digit hour (01-12)
min	The current two-digit minute (00-59) at the point in time of invocation based on the analysts current time zone settings
sec	The current two-digit second (00-59) at the point in time of invocation based on the analysts current time zone settings

udate( [part] )	
Part	Description
not specified	The current UTC time in ISO8601 date/time format
year	The current four-digit year (e.g. 2008)
year2	The current two-digit year (e.g. 08)
month	The current two-digit month (01-12)
day	The current two-digit day of the month (01-31)
hour	The current two-digit hour (00-23)
hour12	The current two-digit hour (01-12)
min	The current two-digit minute (00-59) at the point in time of invocation based on the analysts current time zone settings
sec	The current two-digit second (00-59) at the point in time of invocation based on the analysts current time zone settings
epoch	The UTC time as a unix EPOCH time which is a positive number representing the number of seconds elapsed since the 1st January 1970 at 12:00.

uuid( [type] )	
Type	Description
normal	This generates a UUID that is unique to the system its being generated on
secure	This generates a UUID that cannot be traced to the Ethernet address of the computer on which it was generated
not specified	The same as 'normal'.
sess( prop_name )	
The current user’s session property.
param(param_name)	
A value passed into the function when invoking the sequence.
rec( column_name )	
Use a value that is stored in the database record.
