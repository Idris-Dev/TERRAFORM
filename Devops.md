# CREATING AN ARCHITECTURE USING TERRAFORM ON AWS
## In this project, i will be using terraform on AWS to provision the following services;
* VPC with with 2 subnets and 1 instance in each subnet
* Attach Security groups, internet gateway and network interface to the instance.
* Apache2 will also be installed as the webserver.
## STEP1 CONFIGURE PROVIDER
* Having installed terraform on my Ubuntu terminal,
* i created a directory "terraform_proj" which will be initialized as my terraform working directory.
![image](https://user-images.githubusercontent.com/101482368/163332726-cc583754-4c90-4120-816c-8ac49783f0ab.png)
* Then i created a file "main.tf" which will be used to configure the provider i want to use which in this case is AWS
![image](https://user-images.githubusercontent.com/101482368/163334954-812d02c2-e970-4410-872b-50d9a33f0e0d.png)
* The code tells terraform to initialize AWS as provider and and resources will be created in US-east-1 region and also specifies my account using my access key and secret key
* Ran terraform init command again 
![image](https://user-images.githubusercontent.com/101482368/163335863-e311e543-2725-404b-b059-868d6f67e1bf.png)
## STEP 2 CREATE REQUIRED RESOURCES
* In the main.tf file, i created the resources/services needed for the architecture;
First i created resource_type VPC and also created 2 subnets inside the VPC
![image](https://user-images.githubusercontent.com/101482368/163342567-dae48c2d-dd6f-42d1-ab1f-658b6c92dbdb.png)
* The code creates a VPC and then create 2 subnets inside the VPC with the help of vpc_id which is specified on the codes
* I ran to terraform plan command to see the resources about to be created before applying the changes and got the following outputs
![image](https://user-images.githubusercontent.com/101482368/163340028-c1379af5-b6e4-45e4-8fbf-b2c1552b9403.png)
![image](https://user-images.githubusercontent.com/101482368/163340310-19ded532-960a-4c4f-95c2-343621d6132a.png)
![image](https://user-images.githubusercontent.com/101482368/163340467-2e7f0143-bf97-4614-8274-a8f876ecacc7.png)
![image](https://user-images.githubusercontent.com/101482368/163340543-cf2c5b00-663f-430c-8575-fb60cff3ba14.png)
Ran terraform apply after everything appear to be okay and the resources were created
![image](https://user-images.githubusercontent.com/101482368/163344278-d80999e3-dd88-4720-9405-002e2b7ce862.png)
![image](https://user-images.githubusercontent.com/101482368/163344433-c38d3375-48b9-43bb-9b79-ccbf6ca358ff.png)
* Checked the VPC resource from the console
![image](https://user-images.githubusercontent.com/101482368/163403755-c6af149f-3a74-4b3b-b77d-76122f63f0ab.png)
* Checked the subnet resource from the console
* ![image](https://user-images.githubusercontent.com/101482368/163404753-5c02e3e6-7df0-4edb-8a8f-a05e3dc0062a.png)
* Then i created one instance in each subnet with code below
![image](https://user-images.githubusercontent.com/101482368/163408668-1436efb4-cca6-499e-ad76-d98a088c70da.png)
* I ran terraform plan to see the resources to be created before applying the changes
* ![image](https://user-images.githubusercontent.com/101482368/163409196-99b6734e-d067-44d3-bf34-799fff8a9e4b.png)
* ![image](https://user-images.githubusercontent.com/101482368/163409300-d4842351-80ed-4eae-aea2-57fd8015da79.png)
* ![image](https://user-images.githubusercontent.com/101482368/163409583-20684500-dd59-47cd-b44d-83f75ec74bdf.png)

* Everything appears okay. Then proceeded to run terraform apply command
* ![image](https://user-images.githubusercontent.com/101482368/163417599-8608f570-7311-4c57-a56c-592165c54642.png)
* confirmed from the console
* ![image](https://user-images.githubusercontent.com/101482368/163418243-d5611e40-b926-43b2-8395-eff7b0edb519.png)
* I created security group to be attched to the instance
![image](https://user-images.githubusercontent.com/101482368/163424228-b6497824-d2b3-46e0-99a9-f9ef9fc6fe19.png)
* ran terraform plan to see execution plan
![image](https://user-images.githubusercontent.com/101482368/163424668-fd0d3177-c31e-4e8a-bcee-59ccabdace44.png)
* Then ran terraform apply
![image](https://user-images.githubusercontent.com/101482368/163425016-2bc6016d-a203-4e58-bd7b-88f36f530dbf.png)
* checked the console to verify resource
![image](https://user-images.githubusercontent.com/101482368/163425273-6a70a335-8f11-451d-a966-2e0b6d526e2d.png)
* Configured internet gateway to be attached to the instance and ran terraform apply
![image](https://user-images.githubusercontent.com/101482368/163429983-a72ff297-facd-4567-82b7-b301284d383b.png)
![image](https://user-images.githubusercontent.com/101482368/163430236-40a16ec9-2345-4465-956b-761a2698b6da.png)
![image](https://user-images.githubusercontent.com/101482368/163436640-ed81e5e3-18a4-4d99-97ba-95483f2578b0.png)

* Configured and attacjed network interface to the instance
![image](https://user-images.githubusercontent.com/101482368/163437334-bed55f71-fc8f-44b4-b418-db4c4f92a993.png)
* Ataached Network interface to the instance
![image](https://user-images.githubusercontent.com/101482368/163438471-ad2e6bd8-0c2b-4bc7-8037-51b34d342395.png)
* Destroyed the 2 previous instance and created 2 new instances with apache2 installed on both by creating script file "install.sh"
* ![image](https://user-images.githubusercontent.com/101482368/163442042-6b2868be-8380-4567-ade9-6268f62fb23e.png)
![image](https://user-images.githubusercontent.com/101482368/163441378-2c0f614e-3363-40d9-be8f-65fe00f25471.png)
![image](https://user-images.githubusercontent.com/101482368/163441541-f65f0d76-1b4b-43bd-9ec0-d9ffca658367.png)
* checked the webpage from the browser
* ![image](https://user-images.githubusercontent.com/101482368/163443956-f824e7a6-a116-40b4-ac67-d39ba36685c6.png)








*


* 

