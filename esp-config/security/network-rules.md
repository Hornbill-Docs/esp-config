# Network Rules


The Network Rules option within Hornbill Administration allows customers to control the access to the Hornbill instance.

## Settings
Rules can be added to allow or deny access. A mixture of the two could also be used. For example, to allow access to an instance via the company's office network only and deny access to the rest of the world.

When configuring a rule, the IP address including the subnet mask is required. When more than one rule exists, the order of the rules can be updated using the drag-and-move option on the left-hand side. The rules will be processed in the order that they are listed, starting at rule 1. If a rule doesn't match the criteria, the next rule is then considered.

Adding a single Rule means that ALL other IPs that do not match the Rule will be blocked. 

### Configuration
The company's office network's IP address is usually a single IP (/32).

![Network Rules](/_books/esp-config/security/images/network-rules.png)
