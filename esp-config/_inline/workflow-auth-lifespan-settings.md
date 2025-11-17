# Workflow Authorization Lifespan Settings

The **authorisation lifespan** begins the moment the **authorisation node** is reached in the workflow process.  
This timestamp is known as the **authorisation creation date/time**.



### Due After Duration

The **Due After** duration represents the amount of **days**, **hours**, or **minutes** after the creation date/time that the authorisation is due.

- If you use a **variable reference**, the variable may contain:
  - an **xs:duration** formatted string, or  
  - a **datetime ISO** string.



### Expires After Duration

The **Expires After** duration represents the amount of **days**, **hours**, or **minutes** after the creation date/time when the authorisation expires.

- A **validation error** will be shown if the **Expires After** duration is **less than** the **Due After** duration.  
  (An authorisation cannot be configured to expire before its due date/time.)

- If you use a **variable reference**, the variable may contain:
  - an **xs:duration** formatted string, or  
  - a **datetime ISO** string.
