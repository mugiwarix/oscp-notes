SNMPv1 message
|version|community string| # community string is used for authentication

Windows SNMP MIB table
|OID|Description|
|---|----|
|1.3.6.1.2.1.25.1.6.0 |System Processes|
|1.3.6.1.2.1.25.4.2.1.2 |Running Programs|
|1.3.6.1.2.1.25.4.2.1.4 |Processes Path|
|1.3.6.1.2.1.25.2.3.1.4 |Storage Units|
|1.3.6.1.2.1.25.6.3.1.2 |Software Name|
|1.3.6.1.4.1.77.1.2.25 |User Accounts|
|1.3.6.1.2.1.6.13.1.3 |TCP Local Ports|

- onesixtyone # SNMP scanner

```
echo "public\nprivate\nmanager" > community_strings
onesixtyone -c community_strings -i ips
```

- snmpwalk # query SNMP

```
# common values for community string are public, private, manager
snmpwalk -c COMMUNITY_STRING -v1 -t TIMEOUT IP_ADDR
snmpwalk -c COMMUNITY_STRING -v1 -t TIMEOUT IP_ADDR OID
#-Oa convert HEX strings to ASCII
```
