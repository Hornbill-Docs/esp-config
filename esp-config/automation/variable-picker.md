# Variable Picker

The variable picker is a tool that allows you to select variables that can dynamically insert data into workflow node fields. Instead of typing static text, you can use the variable picker to pull information such as a customer's name, a request ID, or a task outcome directly into a workflow node.

![Variable Picker](/_books/esp-config/images/workflow-variable-picker.png)

## Overview

You can use the variable picker in most workflow nodes, including:

* **Human Tasks**
* **Decision Nodes**
* **Integration Calls**
* **Automated Tasks**
* **Authorizations**

## How to Open the Variable Picker

### Steps

1. Open any workflow node configuration.
2. Locate the field where you want to add data.
3. Click the **Variable Picker** icon (`Σ`) located within the field.

**Expected Result:** A menu appears listing all available variable categories.

## Available Variable Types

The options available in the picker depend on the nodes you placed earlier in your workflow.

* **Global Inputs** - Contains system-wide variables, such as `requestId`.
* **Hornbill Automations** - Displays a list of Hornbill Automation nodes that preceeds the node being edited.  Each node can be expanded to access the variables provided.
* **Tasks** - Contains data from any tasks completed earlier in the current workflow stage, such as **Outcomes**, **Owner**, or **Completion Date**.
* **Integrations** - Contains output parameters returned from integration nodes that precede the node being edited.

---

## Inserting Variables: Inject vs. Overwrite

When you select a variable, you must choose how to place it into the field.

| Option | Action | Use Case |
| :--- | :--- | :--- |
| **Inject** | Adds the variable to the existing content without deleting anything. | Use this to combine multiple variables or add a variable to a sentence. |
| **Overwrite** | Deletes all current content in the field and replaces it with the variable. | Use this when you only need a single specific value in the field. |

*Note: To add multiple variables to one field, use the **Inject** option for each subsequent variable.*

---

## Choosing Value Types: Raw vs. Display

For certain variables, you can choose between two formats:

### Raw Value

The **Raw Value** is the underlying data stored in the system (e.g., a database ID or a language-neutral code).

* **Best for:** Branching logic in **Decision Nodes**, as this value remains constant even if you change the label later.

### Display Value

The **Display Value** is the "friendly" name shown to users (e.g., "Urgent" instead of "priority_level_1").

* **Best for:** Emails, task descriptions, and notifications where a human needs to read the information.
