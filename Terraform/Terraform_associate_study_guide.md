### Purpose
Document Terraform functionality for future use and to act as a study guide for the Terraform Associate 003  

### Training used :
- [Freecodecamp Terraform Associate Training](https://www.youtube.com/watch?v=SPcwo0Gq9T8) (First 4 hours are good, quality lacks after that)
- [acloudguru terraform associate training with labs](https://learn.acloud.guru/course/hashicorp-certified-terraform-associate-1/dashboard)
- Udemy practice exams

### Notes

3 stages of a Terraform Workflow 
write -> plan -> apply
provisionin -> deploying -> orchestration

Infrastructure as a code is a blue print for your stack  
Terraform is declaritive code vs python, js are imperative  
Every time you run a terraform file it is idempotent meaning, it runs fresh, it doesn't update the pre-exisitng environment it refreshes it.  
You don't change the environment using terraform, you change the file and then create a new deployment to apply changes    

Process  
Project lifecycle  
code -> init -> plan -> validate -> apply -> destroy  

Provisioners are used for post-deployment software installation that can be run. 
local-exec vs remote-exec  

```
connection {
  ssh: examplessh
  hostname:examplehostname
  IP: exampleip
}
```

### Commands
null_resource as a placeholder
terraform init -> download connection provider
terraform providers
terraform alias

### Terraform Modules
pre-configs for terraform IaaC
```
<BLOCK TYPE><BLOCKLABEL>{
  argument = expression
}
```

```
variable "variableName"{
  type = variableType
}
```
File Formats
.tfvars


Semantic Versionins
| Major | Minor | Patch |


How to rename (you are technically moving the file to a new file)
``terraform state mv item1 item2

terraform state commands
- list
- mv
- pull
- push
- replace -provider
- rm
- show

How to install on linux
- download the terraform zip files
- unzip the terraform binary
- move terraform to the /bin folder
- ![image](https://github.com/user-attachments/assets/b0eb7fab-53ea-479d-a57d-6122f6a28022)

  For centOS/Redhat
- copy the commands from the terraform compiled source instllation instructions, seems easy

  Terraform State Mechanism contains metadata about the deployment, always backup, keep it secured.
Varibles are stored in terraform.tfvars

You can apply validation block too using validation {}

  
