# Terraform Learning Notes + Labs
My hands-on journey learning Infrastructure as Code with Terraform—featuring core concepts, lab configurations, and project builds.



## Terraform Registry

<img width="1445" height="899" alt="image" src="https://github.com/user-attachments/assets/d4780dbb-83a0-4c9b-9e45-d11c37bfca16" />



<img width="1566" height="967" alt="image" src="https://github.com/user-attachments/assets/d3561c1d-c5d8-4a95-a959-2cdb8546b974" />



## Creating an EC2 Instance 



<img width="1127" height="457" alt="image" src="https://github.com/user-attachments/assets/14bde519-a6aa-4b57-a1be-e99061fec796" />



Will use the documentation on Terrform registry to get the resource block for an EC2 instance. 



<img width="501" height="610" alt="image" src="https://github.com/user-attachments/assets/33dce618-b318-4e81-bf9a-16d432a21a8a" />



<img width="1744" height="309" alt="image" src="https://github.com/user-attachments/assets/07023f6a-3fb5-4d4b-acb6-c705a18f0a3a" />


### Created ec2.tf to provision an AWS virtual machine using a t3.micro instance size running an Ubuntu Linux AMI in the London (eu-west-2) region.



<img width="1549" height="193" alt="image" src="https://github.com/user-attachments/assets/98d633fc-adb3-464c-91ec-b1e2365c61d2" />


I then ran "terraform init" to initialize and prepare the directory for terraform to work. 


### Created a dedicated IAM user (naseem_terraform) with AdministratorAccess permissions and programmatic access keys to allow Terraform to deploy infrastructure safely.



<img width="1854" height="850" alt="image" src="https://github.com/user-attachments/assets/9d8f8b04-4bbd-416f-ae22-3a198c3245f4" />



<img width="838" height="118" alt="image" src="https://github.com/user-attachments/assets/e1766214-4606-4535-9e0d-b7cc27acadd2" />




### Previewing the infrastructure plan with terraform plan and executing terraform apply to successfully provision the VPC and EC2 instance in AWS. 


#### Running "terraform plan"


<img width="1154" height="951" alt="image" src="https://github.com/user-attachments/assets/043b4c2c-311e-44d4-8010-6bed088b5a2d" />




#### Running "terraform apply"



<img width="707" height="982" alt="image" src="https://github.com/user-attachments/assets/2b190170-3b5a-4973-a2d3-0f527dda57c5" />







### AWS Console View: Instance summary confirming active state (Running), t3.micro instance type, and network details in the London region.



<img width="1868" height="892" alt="image" src="https://github.com/user-attachments/assets/49211ac8-dabc-4e69-b522-c022e9aba3ba" />








