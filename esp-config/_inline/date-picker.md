# Date and Time Picker Help
This control allows typing the date and/or time and selecting the date from a calendar.

Valid formats:
```
Mar 25 2022
25/3/2022
25-03-2022
```


In this case the data is clear enough to asume the first digit is the month and the second is the day
```
3/25/2022
25/3/2022
```


However in more generic situations such this:
```
3/3/2022
```
The user's profile date format setting will dictate what comes first.


More flexible date formats:
```
today
now
tomorrow
yesterday
next week
next year
next Monday
last Monday
previous Monday
```


Time format:
```
22:30
10:30pm
10:30pm
10pm
```


Date and time can be used in combination if the control allows:
```
today at 22:30
today at 10:30pm
next week at 10:30pm
Mar 25 2022 10pm
```