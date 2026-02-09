# Decision Node

A Decision Node within a workflow enables it to branch into different paths based on the results of previous nodes within the workflow stage. Default outcomes are available to evaluate the results of the node that directly precedes the decision node.

![Decision Outcomes](/_books/esp-config/images/workflow-decision.png)

The outcomes available will depend on the node that precedes the decision node and may include:

* **Failure** - The previous node encountered an error.
* **Success** - The previous node completed as intended.
* **No Match** - No specific criteria were met.  
* **Expired** - The previous node timed out.
* **Task or Authorization outcomes** - Specific results like "Approved" or "Rejected".
* **Custom Expression** - A custom defined expression to evaluate the outcomes of any node that precedes the decision node, within the same stage.

## Custom Expressions

Custom Expressions allow you to build complex logic. Unlike default outcomes, Custom Expressions can evaluate data from any node within the same workflow stage, not just the one immediately before the Decision Node.

### Create a custom expression

Follow these steps to set up your first Custom Expression:

1. In the Workflow Designer, draw a connector line from a **Decision Node** to a subsequent node.
2. Select the `??` label located on the connector line.
3. In the **Goto If** dialog box, select **Custom Expression** from the **Outcome is** dropdown list.
4. Enter a **Display Name** for your expression. This will replace the `??` label displayed on the connector line.
5. Select **Edit Expression**, then select the `+` button to add your first expression.

![Custom Expression](/_books/esp-config/images/workflow-custom-expression.png)

### Configure an expression

When you build an expression, you define what the workflow should look for before following that path.

1. **Select a variable** - Select the [Variable Picker](/esp-config/automation/variable-picker) icon (`Σ`) to choose the data you want to evaluate (e.g., a node outcome or a task status).
1. **Choose an operator** - Select a logical operator to be used when evaluating the variable, such as:
    * `==` (Equals)
    * `Contains`
    * `<` (Less than)
    * `>` (Greater than)
1. Select the value to evaluate against:
    * **Static value** - Manually type a specific value to evaluate against.
    * **Variable** - Use the **Variable Picker** (`Σ`) to select a value stored in a variable to evaluate against.
1. Select **Apply** to save the expression.

:::tip
When using the Variable Picker, some variables contain both a raw value and a display value. When selecting the **Overwrite** button, you will have an option to select which one of these you wish to use.
:::

### Add multiple conditions

You can add multiple conditions to a single Custom Expression to create more advanced logic.

1. Select the `+` icon within the Expression Builder to add another condition.
1. Use **AND / OR** logical operators to determine how the compounded conditions are evaluated:
    * **AND**: All conditions must be true for the workflow to follow this path.
    * **OR**: Only one of the conditions must be true.
1. Use **Groupings ( )** to organize complex "if/then" scenarios.

## Manage Expressions

* **Edit a condition** -  Select an existing condition to load that condition into the expression builder and make the necessary changes.
* **Delete a condition** - Select an existing condition to enable the **Delete selected condition** button.
* **Delete all conditions** - Use the `Delete All` option to delete all the conditions within the expression and start over.
* **Add a grouping bracket**
  * Select an existing condition, then select the `Add (...` button to add an opening bracket to the left of the condition.
  * Select an existing condition, then select the `Add ...)` button to add a closing bracket to the right of the condition.
  * Brackets without a matching open or close bracket will be highlighted in red.  
* **Delete grouping brackets**
  * Select a grouping bracket to delete it. Its matching bracket will also be highlighted.
  * Select the `Delete (...)` button to delete both brackets.
  * Select the `Delete (...` button to only delete the opening bracket.
  * Select the `Delete ...)` button to only delete the closing bracket.
