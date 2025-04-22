Wiz Principals
1. Eventual Consistency
2. Asynchronous 
3. Resilient 

Phases 
1. API connection
2. Discover
3. Enrich
4. Refine
5. Analyze and Prioritize 
6. Automate

Wiz works by graphQL API
Scans every 24 hours by default, can be increased or decreased based on spending budget
double scans affect your bill (two connectors scanning the same thing, you can detect this)


Observes
- Linux packages and versions
- Windows installed programes
- Hashes of all files
- git metadata


You deploy wiz on a 
- Account level for AWS
- Tenant level for Azure
- Project level for GCP 

AWS roles required 
- ViewOnlyAccess
- SecurityAudit
- WuzDataSecurity

How to connect AWS
1. Define Scope
2. Create Wiz-Access Role
3. Attach Role
4. Connect wiz scanner
5. Input ARN to wiz portal