# Report - Custom Criteria Field
The custom criteria field allows you to specify static SQL test values. This requires properly structured SQL, as if you were writing part of a standard SQL statement. Therefore you should ensure strings are correctly escaped. 

Here are some examples...

When using "value equals" or "does not equal" :-
```
 when testing string value:- "some string based value 1"
 when testing numeric value:- 1
```

When using "value is like" or "is not like" enter test values in brackets:-
```
 when testing string values :- ("some string based value 1","some string based value 2")
 when testing numeric values :- (1,2,3)
```





