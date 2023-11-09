# Auto Value Definition Reference

### Quick Start Examples

<table>
<thead>
<tr>
<th style="text-align:left">Definition nowrap</th>
<th style="text-align:left">Result</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left; white-space: nowrap;"><code>IN{seq(8)}</code></td>
<td style="text-align:left">This would generate an auto val of <strong>IN00000001</strong>, <strong>IN00000002</strong>, <strong>IN00000003</strong>, and so on…</td>
</tr>
<tr>
<td style="text-align:left; white-space: nowrap;"><code>PO{date(year2)}-{seqy(4)}</code></td>
<td style="text-align:left">Assuming the year 2023, this would generate an auto val of <strong>PO230001</strong>, <strong>PO230002</strong> … <strong>PO230003</strong>, and so on… then, from 1st Jan 2024, would generate an auto val of <strong>PO240001</strong>, <strong>PO240002</strong> … <strong>PO240003</strong>, and so on…</td>
</tr>
</tbody>
</table>

### Function Reference
<table>
    <thead>
        <tr>
        <th style="text-align:left; white-space: nowrap;">Function</th>
        <th style="text-align:left">Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="text-align:left; white-space: nowrap;"><strong><code>seq(<em>z</em>, <em>[r=10]</em>)</code></strong></td>
            <td style="text-align:left">Will generate a sequential decimal number. The <code>z</code> parameters sets the number of decimal digits to include in the generated string.  <br><br>The optional <code>r</code> parameter, which defaults to 10, sets the number base to generate, allowing, octal (8), decimal (10) and hexadecimal (16) number formats.  The sequence value will increment by one each time the AutoVal is generated, and is guaranteed to be unique for the lifetime of the AutoVal definition. If the generated number is a value that exceeds the number of digits specified in the <code>z</code> param, the number will still be generated, but the resultant string of characters will be longer than expected.</td>
        </tr>
        <tr>
            <td style="text-align:left; white-space: nowrap;"><strong><code>seqd(<em>z</em>, <em>[r=10]</em>)</code></strong></td>
            <td style="text-align:left">Will generate a sequential decimal number, but this sequence value will reset back to 1 each day. See the description for the seq() function above for details about the <code>z</code> and <code>r</code> parameters</td>
        </tr>
        <tr>
            <td style="text-align:left; white-space: nowrap;"><strong><code>seqm(<em>z</em>, <em>[r=10]</em>)</code></strong></td>
            <td style="text-align:left">Will generate a sequential decimal number, but this sequence value will reset back to 1 each month on the 1st of the month. See the description for the seq() function above for details about the <code>z</code> and <code>r</code> parameters</td>
        </tr>
        <tr>
            <td style="text-align:left; white-space: nowrap;"><strong><code>seqy(<em>z</em>, <em>[r=10]</em>)</code></strong></td>
            <td style="text-align:left">Will generate a sequential decimal number, but this sequence value will reset back to 1 each year on Jan 1st of each year. See the description for the seq() function above for details about the <code>z</code> and <code>r</code> parameters</td>
        </tr>
        <tr>
            <td style="text-align:left; white-space: nowrap;"><strong><code>date(<em>[part]</em>)</code></strong></td>
            <td style="text-align:left">Will generate a decimal number derived from the point in time (in default server local time) when an AutoVal sequence number is generated.
                <table>
                <tbody><tr bgcolor="#e0e0e0">
                <td>Part
                </td>
                <td><b>Description</b>
                </td></tr>
                <tr>
                <td nowrap="1"><i>not specified</i>
                </td>
                <td>The current local time in ISO8601 date/time format
                </td></tr>
                <tr>
                <td nowrap="1"><b>year</b>
                </td>
                <td>The current four-digit year (e.g. 2008)
                </td></tr>
                <tr>
                <td nowrap="1"><b>year2</b>
                </td>
                <td>The current two-digit year (e.g. 08)
                </td></tr>
                <tr>
                <td nowrap="1"><b>month</b>
                </td>
                <td>The current two-digit month (01-12)
                </td></tr>
                <tr>
                <td nowrap="1"><b>day</b>
                </td>
                <td>The current two-digit day of the month (01-31)
                </td></tr>
                <tr>
                <td nowrap="1"><b>hour</b>
                </td>
                <td>The current two-digit hour (00-23)
                </td></tr>
                <tr>
                <td nowrap="1"><b>hour12</b>
                </td>
                <td>The current two-digit hour (01-12)
                </td></tr>
                <tr>
                <td nowrap="1"><b>min</b>
                </td>
                <td>The current two-digit minute (00-59) at the point in time of invocation based on the analysts current time zone settings
                </td></tr>
                <tr>
                <td nowrap="1"><b>sec</b>
                </td>
                <td>The current two-digit second (00-59) at the point in time of invocation based on the analysts current time zone settings
                </td></tr></tbody></table> 
            </td>
        </tr>
        <tr>
            <td style="text-align:left; white-space: nowrap;"><strong><code>udate(<em>[part]</em>)</code></strong></td>
            <td style="text-align:left">Will generate a decimal number derived from the point in time (in UTC time) when an AutoVal sequence number is generated.
                <table>
                <tbody><tr bgcolor="#e0e0e0">
                <td>Part
                </td>
                <td><b>Description</b>
                </td></tr>
                <tr>
                <td nowrap="1"><i>not specified</i>
                </td>
                <td>The current UTC time in ISO8601 date/time format
                </td></tr>
                <tr>
                <td nowrap="1"><b>year</b>
                </td>
                <td>The current four-digit year (e.g. 2008)
                </td></tr>
                <tr>
                <td nowrap="1"><b>year2</b>
                </td>
                <td>The current two-digit year (e.g. 08)
                </td></tr>
                <tr>
                <td nowrap="1"><b>month</b>
                </td>
                <td>The current two-digit month (01-12)
                </td></tr>
                <tr>
                <td nowrap="1"><b>day</b>
                </td>
                <td>The current two-digit day of the month (01-31)
                </td></tr>
                <tr>
                <td nowrap="1"><b>hour</b>
                </td>
                <td>The current two-digit hour (00-23)
                </td></tr>
                <tr>
                <td nowrap="1"><b>hour12</b>
                </td>
                <td>The current two-digit hour (01-12)
                </td></tr>
                <tr>
                <td nowrap="1"><b>min</b>
                </td>
                <td>The current two-digit minute (00-59) at the point in time of invocation based on the analysts current time zone settings
                </td></tr>
                <tr>
                <td nowrap="1"><b>sec</b>
                </td>
                <td>The current two-digit second (00-59) at the point in time of invocation based on the analysts current time zone settings
                </td></tr></tbody></table> 
            </td>
        </tr>
        <tr>
            <td style="text-align:left; white-space: nowrap;"><code>uuid(<em>[type]</em>)</code></td>
            <td style="text-align:left">Will generate a UUID value.  If type=normal this will generate a UUID that is unique.  Of type=secure then this will generate a UUID that cannot be traced to specific system attributes such as the Ethernet address of the computer on which it was generated.</td>
        </tr>
        <tr>
            <td style="text-align:left; white-space: nowrap;"><code>sess(<em>prop_name</em>)</code></td>
            <td style="text-align:left">Will generate a string who's value is obtained from a the named session variable.</td>
        </tr>
        <tr>
            <td style="text-align:left; white-space: nowrap;"><code>param(<em>param_name</em>)</code></td>
            <td style="text-align:left">Will generate a string who's value is obtained from a parameter passed into the API being called that causes the autoVal to be generated.</td>
        </tr>
        <tr>
            <td style="text-align:left; white-space: nowrap;"><code>rec(<em>column_name</em>)</code></td>
            <td style="text-align:left">Will generate a string who's value is obtained from a the database column related to the table where this auto-val is being used.</td>
        </tr>
    </tbody>
</table>