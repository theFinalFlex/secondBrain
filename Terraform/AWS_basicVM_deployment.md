### Spin up a VM in AWS using Terraform Workflow

in simple terms spinng up a instance and then destroy it just to get a feeling of the terraform commands.
Steps 
![alt text](https://github.com/theFinalFlex/secondBrain/blob/1f6bc445a3c1cca2668a546387b90db1fc60280d/Assets/image.png)
1. Log into your provider of chouce (I am using AWS for this lab)
2. Create and change directory into the newly created terraform dir
3. Create a main.tf file and then use vim or whatever code editor you want to edit the file
4. Build the provider module 
5. Create the resource of choice, in this lab we are spinning up a simple VM
![alt text](https://github.com/theFinalFlex/secondBrain/blob/38fa56f0a44b3133b7da9037bb4330b34e3bd96a/Assets/image-1.png)
6. Enter in infra details like AMI/subnet
7. run terraform init, terraform plan, terraform apply
8. Once review run terraform destroy to wipe the file

