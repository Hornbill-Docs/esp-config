# Decision Node
A Decision Node within a Workflow allows the workflow to branch down different paths based on the outcomes of previous nodes within the workflow stage. Default outcomes are available to test the outcomes of the node that immediately precedes the decision node.

![Decision Outcomes](/_books/esp-config/images/workflow-decision.png)

The outcomes available will depend on the node that precedes the decision node and may include:
* Failure
* Success
* No Match
* Expired
* Task or Authorisation outcomes

In addition to these default options, you can also build your own custom expressions using the Custom Expression Builder. Custom Expressions will allow you to evaluate the outcomes of any node that precedes the decision node within the same stage.

## What is a Custom Expression
A Custom Expression consists of one or more tests that evaluate the outcomes of nodes within the current stage. If the tests within the expression are met, that path out of the decision node will be followed. To add a Custom Expression, click on the description box of a connector that exits a Decision Node and in the Goto If dialog box, select Custom Expression from the list of outcomes.

## Building Expressions
The custom expression builder allows you to create one or more tests which can be evaluated when a workflow reaches the decision node.

### Adding your first Expression
Following a decision node, draw out a line and add a new node. On the line you have drawn out you will see ?? icons. Click on the icons and a pop up window is presented, this will contain a drop down with default outcomes and an option for Custom Expression.
* Provide a display name for the Custom Expression
* Select Edit Expression and + to add

![Custom Expression](/_books/esp-config/images/workflow-custom-expression.png)

### Options
By default the rule question will be presented in the Selected Test Setup section, picked up from the node proceeding the decision node. This can be left the same or using the Variable Picker Icon you can change what you want to evaluate by choosing from the list of available variables (See the variable picker to understand what options can be presented here)
* **Operators**<br>Choose what condition for the chosen question you are looking to test ( ==, Contains, <,> etc)
* **Value**<br>Choose to insert:
    * ***Static Value***<br>Here you can manually insert a value to evaluate against
    * ***Variable***<br>Here you can choose to use the variable picker to look up a value to evaluate against, examples maybe an answer to a progressive capture question, a customers custom field value or a custom filed on a task.
    * ***Value to evaluate***<br>Choose to use either the raw value or display value for the variable - the raw value is unlikely to change so maybe more consistent to use, compared with the display value which may be changed or different language variants of the variable may exist.

If only one rule (expression) is required click apply to save.

## Adding Additional Rules
It is possible to add multiple rules (expressions) to a single custom expression and you can do so by simply selecting the + icon and repeating the steps above.

When more than one rule (expression) exists you can add conditions which can be evaluated:
* AND / OR - Decide if the defined rules (expressions) must all match or if there is a combination of AND or OR conditions
* Groupings ( ) - Use the expression groupings to build out more complex (rule / expressions)

## Administration
* Select a rule (expression) to either edit or delete it
* Select a grouping bracket to delete it
*Use the `Delete All` option to delete all the rules (expressions)

<!-- https://wiki.hornbill.com/index.php?title=Custom_Expression_Builder -->