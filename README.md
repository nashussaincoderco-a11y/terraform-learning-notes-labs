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




### Current terraform workflow sequence 

1. Write .tf code (provider.tf and ec2.tf)
2. Run "terraform init" - This downloads the AWS provider plugin (hashicorp/aws) and sets up the .terrform working directory
3. Setting up the credentials using "aws configure" so terraform can talk to AWS.
4. terraform plan - Previews what resources will be created.
5. terrform apply - creates the actual infrastructure in AWS






## Input Variable



<img width="1140" height="860" alt="image" src="https://github.com/user-attachments/assets/655e982a-61ea-459d-a5f3-713f7ae8a6f3" />





<img width="942" height="230" alt="image" src="https://github.com/user-attachments/assets/c3d2eba5-21d9-4ba0-8b04-b744dfde1c33" />






## Input Variables - terraform.tfvars 

tfvars is a good practice method for engineers as you are able to easily change settings for different environments with editing your main code. 



A tfvar file is a configuration file used to supply actual, real world values to Terraform variables. A .tf file creates the blueprints and structure of your infrastructure, the .tfvars file simple holds the specific values like names or sizes to fill in that blueprint. 


<img width="1135" height="857" alt="image" src="https://github.com/user-attachments/assets/9765ec97-e43d-4553-b022-a591005b8608" />





<img width="1058" height="255" alt="image" src="https://github.com/user-attachments/assets/e019ad36-cb6a-40cb-ae09-dedc6a0cbe3d" />





<img width="1077" height="264" alt="image" src="https://github.com/user-attachments/assets/072e6d40-a0e8-41df-88f0-f8233e5e0b83" />




<img width="1126" height="434" alt="image" src="https://github.com/user-attachments/assets/ab190aec-2f9b-4b29-b65d-d088d75c284a" />





## Local Variables

A local variable in terraform is just an internal shortcut that is defined to a reuse a value throughout the infrastructure code without repeating it. 


In the example below, I set up a local.instance_ami in the code so it can easily be reused and I am able to manage the AMI ID from one central spot. 


A local variable is more private compared to an input variable as it is hardcoded inside the project so outside users can't touch or change it. Whereas an input variable lets users pass values in from the outside just like a setting you can change. 


<img width="1149" height="348" alt="image" src="https://github.com/user-attachments/assets/d8401489-8574-414f-ab3c-1afd8ab7bfa5" />



<img width="1112" height="648" alt="image" src="https://github.com/user-attachments/assets/910d59cd-6a5a-484f-9de5-16de815be110" />





## Output Variables 



<img width="634" height="368" alt="image" src="https://github.com/user-attachments/assets/fb1c7b6c-1fdb-4854-b9eb-edd93ffff931" />




<img width="1134" height="820" alt="image" src="https://github.com/user-attachments/assets/43e056e1-048a-4360-b689-e28daacd0a73" />









## Terraform Modules


I am going to modularise my EC2 instance configuration in the EC2.tf file. 





<img width="1267" height="256" alt="image" src="https://github.com/user-attachments/assets/7733b74c-a0fc-4da9-9144-f50ae10125c0" />





<img width="362" height="80" alt="image" src="https://github.com/user-attachments/assets/1c12822e-5508-49ec-99c9-4f629b720cd8" />






<img width="170" height="85" alt="image" src="https://github.com/user-attachments/assets/80ebef41-71e3-48df-ad9d-a55d24881332" />






<img width="1540" height="1020" alt="image" src="https://github.com/user-attachments/assets/d816161d-2577-4fab-b6f4-1afefbf6e0a9" />









<img width="1116" height="336" alt="image" src="https://github.com/user-attachments/assets/9547c411-5b14-4497-a8ea-13d55a1d0bba" />









<img width="971" height="534" alt="image" src="https://github.com/user-attachments/assets/d195ca83-bd92-4bbe-8fad-98121be82959" />







<img width="523" height="199" alt="image" src="https://github.com/user-attachments/assets/cbba8329-9e57-470e-b0b3-bc5a11b9e57d" />







<img width="1294" height="458" alt="image" src="https://github.com/user-attachments/assets/4f282474-d5d4-490b-ac75-08cb7f707d8c" />







<img width="808" height="411" alt="image" src="https://github.com/user-attachments/assets/f966daa0-59b7-4dae-afce-1f60f01c6eef" />






<img width="1100" height="824" alt="image" src="https://github.com/user-attachments/assets/5d98d657-3932-4aa6-8319-93ef1f392eb7" />








<img width="846" height="816" alt="image" src="https://github.com/user-attachments/assets/aaf92d4a-c39d-4610-8ee5-284392e7d2ab" />





## Terraform Destroy 





<img width="891" height="499" alt="image" src="https://github.com/user-attachments/assets/aec90b4b-8cb7-499c-ad46-a888518dcedf" />










