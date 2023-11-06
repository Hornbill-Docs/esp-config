# Form Field - Data Binding

The data binding property allows you to specify another custom form field that you want to overwrite when setting this fields value. 

So for example if you have a custom form with id of "FormA" and in it a field with id of "CustomerID". To overwrite the value captured in that form you would set the databinding in this field to FormA.CustomerID


Example Setup
```
 Create a Form called "FormA" with a field "CustomerID".
 
 Create a Form called "FormB" with a field "AltCustomerID".

 In FormB for the field "AltCustomerID" set its data binding to "FormA->CustomerID"
```


Example Runtime
```
 FormA is displayed. The user types in a value of "Mork" into the CustomerID field.
 
 They click Next. 

 FormB is display and the AltCustomerID field is displayed and already has the value of "Mork" because it is databound to FormA.CustomerID.

 The user changes the value in FormB to "Mindy".

 They click Previous.

 FormA is displayed again and the CustomerID field is displayed but now has value of "Mindy" as its value was changed through the databinding on FormB.
```



