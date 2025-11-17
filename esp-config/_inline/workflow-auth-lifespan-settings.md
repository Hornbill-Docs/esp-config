# Workflow Authorization Lifespan Settings

The **authorisation lifespan** begins the moment the **authorisation node** is reached in the workflow process.  
This timestamp is known as the **authorisation creation date/time**.



### Due On Duration

The **Due On** duration represents the amount of **days**, **hours**, or **minutes** after the creation date/time that the authorisation is due.

- If you use a **variable reference**, the variable may contain:
  - an **xs:duration** formatted string, or  
  - a **datetime ISO** string.



### Expires On Duration

The **Expires On** duration represents the amount of **days**, **hours**, or **minutes** after the creation date/time when the authorisation expires.

- A **validation error** will be shown if the **Expires On** duration is **less than** the **Due On** duration.  
  (An authorisation cannot be configured to expire before its due date/time.)

- If you use a **variable reference**, the variable may contain:
  - an **xs:duration** formatted string, or  
  - a **datetime ISO** string.
