<h1>Email Routing Rule - Expressions</h1>
<p>Each rule uses an expression to match information found within the email message being processed. Information from
    the email message is made accessible to the expression processor as variables. For convenience, these variables are
    available in the Rule Parameters selector located at the top right of the Rule Expression field.</p>
<p>Selecting any of these items from the list will insert that parameter into the Rule Expression field. Alternatively,
    as you become more familiar with the system you can simply type the correct variable names into the expression as
    needed. The following table lists the available variables and their purpose</p>

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
            <td noWrap><code>toAddress</code></td>
            <td>The email address(es) to which the message was sent.<br><br>If the email was sent to multiple
                recipients, this variable will contain a comma-separated list of all the addresses (e.g.
                support@hornbill.com, info@hornbill.com). When including the toAddress variable in an expression, the
                LIKE operator should be used. For example, the expression
                <code>toAddress LIKE '%support@hornbill.com%'</code> would match, even if there are multiple addresses.
            </td>
        </tr>
        <tr>
            <td noWrap><code>toDomain</code></td>
            <td>The email domain(s) to which the message sent.<br><br>If the email was sent to multiple recipients, this
                variable will contain a comma-separated list of all the domains (e.g.
                <code>hornbill.com, google.com</code>). When including the toDomain variable in an expression, the LIKE
                operator should be used. For example, the expression <code>toDomain LIKE '%hornbill.com%'</code> would
                match, even if there are multiple domains.</td>
        </tr>
        <tr>
            <td noWrap><code>ccAddress</code></td>
            <td>The CC email address(es) to which the message was sent.<br><br>If the email was sent to multiple CC
                recipients, this variable will contain a string of comma-separated addresses (e.g.
                <code>support@hornbill.com, info@hornbill.com</code>). When including the ccAddress variable in an
                expression, the LIKE operator should be used. For example, the expression
                <code>ccAddress LIKE '%support@hornbill.com%'</code> would match, even if there are multiple addresses.
            </td>
        </tr>
        <tr>
            <td noWrap><code>ccDomain</code></td>
            <td>The CC email domain(s) to which the message was sent.<br><br> If the email was sent to multiple CC
                recipients, this variable will contain a string of comma-separated domains (e.g.
                <code>hornbill.com, google.com</code>). When including the ccDomain variable in an expression, the LIKE
                operator should be used. For example, the expression<code>ccDomain LIKE '%hornbill.com%'</code> would
                match, even if there are multiple domains.</td>
        </tr>
        <tr>
            <td noWrap><code>fromAddress</code></td>
            <td>The full email address of the person who sent the message, for example
                <code>joe.bloggs@hornbill.com</code></td>
        </tr>
        <tr>
            <td noWrap><code>fromDomain</code></td>
            <td>The email domain of the person who sent the message, for example <code>hornbill.com</code></td>
        </tr>
        <tr>
            <td noWrap><code>subject</code></td>
            <td>The message subject text</td>
        </tr>
        <tr>
            <td noWrap><code>body</code></td>
            <td>The message body text. If the message was sent as HTML, this will be a html-stripped text string.</td>
        </tr>
        <tr>
            <td noWrap><code>mailbox</code></td>
            <td>The name of the mailbox on Hornbill to which the toAddress email was matched</td>
        </tr>
    </tbody>
</table>

<h3>Simple Example Expressions</h3>
<table class="doc-pretty-table">
    <thead>
        <tr>
            <th>Operator</th>
            <th>Example</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>LIKE</td>
            <td>subject LIKE ‘%abc’<br>subject LIKE ‘xyz%’<br>subject LIKE ‘%mno%’</td>
        </tr>
        <tr>
            <td>NOT</td>
            <td>subject != ‘abc’</td>
        </tr>
        <tr>
            <td>NOT IN</td>
            <td>subject NOT IN (‘abc’, ‘zyx’)</td>
        </tr>
        <tr>
            <td>IN</td>
            <td>subject IN (‘abc’, ‘mno’, ‘xyx’)</td>
        </tr>
        <tr>
            <td>=</td>
            <td>subject = ‘abcd’</td>
        </tr>
    </tbody>
</table>

<h3>Learn More</h3>

<ul>
    <li><a href="https://docs.hornbill.com/esp-config/email/routing-rules" target="_blank">Read about Routing
            Rules</a></a></li>
    <li><a href="https://docs.hornbill.com/esp-fundamentals/reference-guides/express-logic" target="_blank">ExpressLogic
            Reference</a></a></li>
</ul>