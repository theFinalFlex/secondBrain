Incident Reponse
Detection and Analysis - > Containment/Recovery -> Post incident


**ENTRA**

![](../../Assets/Pasted%20image%2020250421203246.png)

Microsoft Entra ID 
Make sure the right people have the right access

Microsoft Entra Verified ID 
For B2B 
mainly for setting entra up for customers

Microsoft Entra Permissions Management
Helps you manage permissions over AWS, GCP and Azure

Microsoft Entra Workload ID
too many identities for infrastructure, helps you manage them 

Microsoft Entra Internet Access
its a proxy, helps you secure internet access for employees

Microsoft Entra Private Access
VPN replacement, provides private access to on-prem resources aka application proxy 

![](../../Assets/Pasted%20image%2020250421212516.png)

Use Entra connect to sync on-prem identities with azure cloud 

guest identities = 3rd party identities (Facebook, google, apple ID etc)

How to create users in entra ID
1. go to users
2. create new users
3. give principle name
4. add display name 
5. add roles & groups (Global admin, etc)
6. Hit review and create

Managed Identities = identities for azure resources 

system assigned basically creates the identity with the resource
manually assigned needs to be audited manually 

How to leverage Managed Identities
1. Create resource group
2. Create Virtual Machine 
3. Create SQL database, select same resource group
4. Select the VM, go to security blade
5. Select system assigned, switch the status from off to on
6. Go to SQL server
7. Go to IAM blade
8. Go to Role assignments
9. Add new role assignment 
10. Select SQL server DB contributor 
11. Assign access to managed identity 
12. Select the members, click on the VM that you created
13.  Create user assigned managed identity, deploy it, do the same, go back to the VM and link it
14. if you delete the VM at that point the user managed identity will still stay while the system managed identity will disappear

Role based groups are a lot more efficient, than individual role based identities 

assigned = adding people to roles manually
dynamic = automation, if the user/resource matches this criteria, then they fall under this group
dynamic device = same thing but for devices
![](../../Assets/Pasted%20image%2020250421214724.png)
example of properties 

How to create group
1. go to groups
2. create group
3. create memebership type "assigned"
4. add azure role assignments

Administrative units helps you restrict permissions based on how you define it
ie - soc analysts from us are only allowed to triage us based alerts

Entra ID External Identities 
leverage 3rd party identities to access on-prem business resources
B2C 

you can configured guest access, guest invite settings, collaboration settings

Entra ID protection 
helps you figure out identity based risks
- leaked credentials
- password spray attacks
- anonymous ip address usage 

**Alerts**
Risky Sign-in
Anamalous Token
Suspicious Browser usage (Tor for example)
Unfamiliar Sign-in Properties 

How to manage identity protection in Entra
1. Under Protect blade
2. you can set up conditial access
3. sign in risk policy 
4. check risky users
5. check risky sign-ins
6. check risk detections 
7. 90% of protection is based off of conditional access | policies 

Entra ID Authentication Methods
1. password
2. sms 
3. voice 
4. Oauth tokens 
5. Microsoft Authenticator Application 
6. Windows Hello for Business, tied to TPM 
7. FIDO2 Key
8. Certificate-based Authentication

![](../../Assets/Pasted%20image%2020250422100753.png)

Passwordless Deployment
1. Click on entra ID authN methods
2. change authenticator app settings
3. switch status to Microsoft managed, all users

Entra ID Password Protection 
1. Smart Password Policies 
2. Real-time password validation
3. Protection across hybrid environments 

Entra Connect Sync (old)
Entra Connect Cloud sync
Entra Connect Health (provides monitoring on the sync)

![](../../Assets/Pasted%20image%2020250422105032.png)

How to create hybrid identity
1. Create resource group 
2. Create Virtual network
3. Create VM 
   


Setup Custom Domain
1. Go to app service domain
2. fill up contact information for ICANN
3. Use godaddy or namecheap for cheaper domain
4. Go to entra ID
5. go to custom domain names
6. add domain, add the domain
7. copy the txt record
8. go to app service domains
9. verify your domain in app service


How to setup AD
1. Go to the VM
2. click the rdp connect file
3. enter the password you setup
4. add roles and features
5. select the server
6. server roles - select active directory domain services
7. Hit install
8. Add a new forest
9. for root domain name give the domain you bought
10. provide password
11. netbios domain name is ur domain minus net
12. Hit install
13. Login back again

Installing Entra Connect
1. Go to EntraConnect VM
2. Connect with RDP
3. go to settings
4. Go to change adapter options
5. go to ethernet properties
6. for IPV4, use the following dns serer address
7. put in the domain controller address
8. go back to server manager
9. change workgroup
10. add it to the domain
11. login
12. you will be welcomed, restart the server
13. download entra connect onto the server
14. install it
15. configure how users will authN
16. provide global admin
17. authenticate as global admin
18. provide forest name
19. at this point it will sync

