# Webhook Expressions

Each webhook can use an expression to match information found in the data record associated with the WebHook. Information from the data record is made accessible to the expression processor as variables. For convenience, these variables are available in the editor when typing `record.`

Typing "record." in the Trigger Expression field will list the available variables that can be used in the expression

  
Selecting any of these items from the list will insert that parameter into the Rule Expression field. Alternatively, as you become more familiar with the system you can simply type the correct variable names into the expression as needed. 

The following table lists the available variables and their purpose</p>

:::tip
These variable names are CASE-SENSITIVE and must be entered in exactly the same way they are documented here.  Use the variable selector, or make sure you type them in as shown
:::

<table class="doc-pretty-table">
    <thead>
        <tr>
            <th noWrap>Variable</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td noWrap><code>record.*</code></td>
            <td>The record-specific field values, they use the samne names/data types as defined in the database.
            </td>
        </tr>
        <tr>
            <td noWrap><code>eventSource</code></td>
            <td>The ID of the event source that triggered the webhook.</td>
        </tr>
        <tr>
            <td noWrap><code>actionBy</code></td>
            <td>
              The person that performed the action that led to this webhook being triggered.
            </td>
        </tr>
        <tr>
            <td noWrap><code>entity</code></td>
            <td>The name of the entity that triggered the webhook.</td>
        </tr>
    </tbody>
</table>

<h3>Learn More</h3>
<ul>
    <li><a href="https://docs.hornbill.com/esp-fundamentals/core-capabilities/integration/web-hooks" target="_blank">Read about WebHooks</a></a></li>
    <li><a href="https://docs.hornbill.com/esp-fundamentals/reference-guides/express-logic" target="_blank">ExpressLogic
            Reference</a></a></li>
</ul>
