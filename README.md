# Ultra simple Declarative WAF demo

# Requirements:
1. Visual Studio Code
1. REST Client extension
   
   Should be proposed by Visual Studio while opening .rest file
1. AS3 installed
1. ASM provisioned
1. restjavad memory increased
   
   ```
   tmsh modify sys db provision.extramb value 1000
   tmsh modify sys db restjavad.useextramb value true
   tmsh save sys config
   ````
1. LAMP with hackazon
1. info.dat file created in the hackazon www directory
1. Basic BigIP configuration

    * Interfaces
    * SelfIPs
    * Routes
    * DNS
    * SNMP

# Demo flow
## Create initial policy and Virtual Server
1. `00_policy_operations.rest` up to request `# Apply policy`
1. Whole `01_AS3_definition.rest`

You should be able to access Hackazon via 10.1.10.20

## Inducing Learning Suggestion and reading Learning Suggestions
1. Navigate to http://10.1.10.20/info.dat or go through 02_invalid_request.rest
1. Go through `00_policy_operations.rest` from line `# Suggestions preview - do not copy to policy declaration`
1. Please note that exported Learning Suggestions contains a difference between `mod_policy.json` and `init_policy.json`

# References
* https://clouddocs.f5.com/products/waf-declarative-policy/