# Network Rules

:::info
This feature is only available on the [Enterprise Edition](/esp-fundamentals/about/hornbill-editions#enterprise-edition-architecture).
:::

The Network Rules option within Hornbill Administration allows Enterprise customers to control the access to the Hornbill instance.

## Settings
Rules can be added to allow or deny access. A mixture of the two could also be used. For example, to allow access to an instance via the company's office network only and deny access to the rest of the world.

When configuring a rule, the IP address including the subnet mask is required. When more than one rule exists, the order of the rules can be updated using the drag-and-move option on the left-hand side. The rules will be processed in the order that they are listed, starting at rule 1. If a rule doesn't match the criteria, the next rule is then considered.

### Configuration
The company's office network's IP address is usually a single IP (/32).
To allow a Hornbill instance to communicate with other Hornbill services, add an entry to allow access to 10.4.0.0/16, 10.5.0.0/16, 10.11.0.0/16, 10.10.0.0/16 and 84.207.237.38
To deny access to the rest of the world, create a deny rule with the value 0.0.0.0/0.

![Network Rules](/_books/esp-config/security/images/network-rules.png)