Document Terraform functionality for future use and to act as a study guide for the Terraform Associate 003
Training used :
- Freecodecamp Terraform Associate Training[(https://www.youtube.com/watch?v=SPcwo0Gq9T8)] (First 4 hours are good, quality lacks after that)
- acloudguru terraform associate training with labs[(https://learn.acloud.guru/course/hashicorp-certified-terraform-associate-1/dashboard)]
- udemy practice exams

Notes

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

Execution
local-exec vs remote-exec

connection {
  ssh: examplessh
  hostname:examplehostname
  IP: exampleip
}

null_resource as a placeholder
terraform init -> download connection provider
