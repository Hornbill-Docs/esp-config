# Date and Time Picker Help
This control allows typing the date and/or time and selecting the date from a calendar.

Valid formats:
- `Mar 25 2022`
- `25/3/2022`
- `25-03-2022`

In this case the correct date can be deduced because 25 cannot be a month, so it can determine that the format is mm/dd/yyyy or dd/mm/yyyy
- `3/25/2022`
- `25/3/2022`


However, when its not possible to correctly deduce the month and day elements, the user's profile date format setting will be used to establish the expected day/date order.
- `3/3/2022`

More generalized natural language date shortcuts:
- `today`
- `now`
- `tomorrow`
- `yesterday`
- `next week`
- `next year`
- `next Monday`
- `last Monday`
- `previous Monday`

Time format:
- `22:30`
- `10:30pm`
- `10:30pm`
- `10pm`

Where the input allows both a date and time input, you can use the above in combination
- `today at 22:30`
- `today at 10:30pm`
- `next week at 10:30pm`
- `Mar 25 2022 10pm`
