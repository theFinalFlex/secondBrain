- Log into Cloud Shell
![image](https://github.com/user-attachments/assets/41379440-4662-44de-8d98-00fe9d82bee6)

- configure or download terraform deployment file

```
#Create and bootstrap webserver
resource "aws_instance" "webserver" {
  ami                         = data.aws_ssm_parameter.webserver-ami.value
  instance_type               = "t3.micro"
  key_name                    = aws_key_pair.webserver-key.key_name
  associate_public_ip_address = true
  vpc_security_group_ids      = [aws_security_group.sg.id]
  subnet_id                   = aws_subnet.subnet.id
  provisioner "remote-exec" {
    inline = [
      "sudo yum -y install httpd && sudo systemctl start httpd",
      "echo '<h1><center>skibidi rizz ong fanum tax ohio</center></h1>' > index.html",
      "sudo mv index.html /var/www/html/"
    ]
    connection {
      type        = "ssh"
      user        = "ec2-user"
      private_key = file("~/.ssh/id_rsa")
      host        = self.public_ip
    }
  }
  tags = {
    Name = "webserver"
  }
}

```

- run terraform init
- run terraform validate
- run terraform apply
- aws will output the IP address you can copy and paste into browser to access the webpage you hosted/deployed using apache

![image](https://github.com/user-attachments/assets/c2c731bb-34ef-40bc-b8fb-8e7834435493)

![image](https://github.com/user-attachments/assets/1ac40d79-ea4d-4b98-9f4c-1be3ca839c8f)

