# Workflow Human Task Lifespan Settings

The **Human Task lifespan** begins the moment the **task node** is reached in the workflow process.  
This timestamp is known as the **task creation date/time**.

### Start Duration

The **Start** duration represents the number of **days**, **hours**, or **minutes** after the creation date/time when the task is assigned for work to begin.

- If you use a **variable reference**, the variable may contain:  
  - an **xs:duration** formatted string, or  
  - a **datetime ISO** string.

### Due Duration

The **Due** duration represents the number of **days**, **hours**, or **minutes** after the creation date/time when the task is due.

- A **validation error** will be displayed if the **Due** duration is **less than** the **Start** duration.  
  (A task cannot be configured to be due before the start-work date/time.)

- If you use a **variable reference**, the variable may contain:  
  - an **xs:duration** formatted string, or  
  - a **datetime ISO** string.

### Expires After Duration

The **Expires After** duration represents the number of **days**, **hours**, or **minutes** after the creation date/time when the task will expire.

- A **validation error** will be displayed if the **Expires After** duration is **less than** the **Start** duration.  
  (A task cannot be configured to expire before the start-work date/time.)

- A **validation error** will be displayed if the **Expires After** duration is **less than** the **Due** duration.  
  (A task cannot be configured to expire before the due date/time.)

- If you use a **variable reference**, the variable may contain:  
  - an **xs:duration** formatted string, or  
  - a **datetime ISO** string.



