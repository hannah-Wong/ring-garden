## ACL on Layer3 switches and routers

routers and layer3 switches provide basic traffic filtering capabilities with ACLs

- Filter by **IP, subnet, port number**
- If not match with any condition, the packet will loss.
- Cannot have two inbound in one interface. Each interface only can have one inbound and one outbound.
- ACL order **top-down**, one there is one statement matched, it will ignore/skip other statements.

### standard IP ACLs

- Only can filter the source IP
- Actions: permit, deny and remark
- Applied to
- Wildcard mask
- **#access-list access-list-number {deny/|/permit} source \[source-wildcard\]  \[log\]**

- #### inbound
- Router check the packet before routing

- #### outbound
- Router check the routing table, than check the packet.
- As there is no destination add, place close to destination side

💡**~={magenta}When attach ACL to VLAN interface, 
 An ACL applied outbound to a VLAN interface filters traffic *GOING TO* machines on that VLAN;
 An ACL applied inbound to a VLAN interface filters traffic *COMING FROM* machines on that VLAN.=~**


### extended ACLs

- Based on **source and destination address, protocols and port numbers**
- Access-list-number 100 to 199
- **#access-list access-list-number {deny|permit}  protocol source \[source-mask destination destination-mask operator operand\] \[established\]**

- Operator operand

- Apply the seque number

### reflexive access lists

- Create a temperory
- #### Layer3
- #### router

### New firewalls(NGFW)