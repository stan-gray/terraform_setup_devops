# Deploy the code and access the webserver
## Pre-req
1. Create a user in AWS and assign the appropriate permissions to interact with AWS components (EC2, SSM, etc)
2. Launch free tier EC2 instance in AWS
3. SSH to EC2 or connect directly from the AWS console
4. Install all dependencies and complete AWS configure with the previously created user

```bash
sudo yum update -y
```

```bash
ssh-keygen -t rsa
```

```bash
sudo yum install git -y
```

Install Terraform in EC2 instance
Follow the instructions at https://learn.hashicorp.com/tutorials/terraform/install-cli

## Steps
Pull the existing terraform code from the repo

```bash
git clone https://github.com/stan-gray/terraform_setup_devops.git
```

Navigate inside the project folder

```bash
cd terraform_setup_devops
```


Initialize the Terraform working directory, and download the required providers:

```bash
terraform init
```

Validate the code to look for any errors in syntax, parameters, or attributes within Terraform resources that may prevent it from deploying correctly.
You should receive a notification that the configuration is valid.



```bash
terraform validate
```

Review the actions that will be performed when you deploy the Terraform code.


```bash
terraform plan
```


In this case, it will create resources as configured in the Terraform code. When prompted, type yes, and press Enter.


```bash
terraform apply
```

In the output, you should see the public IP of the webserver.
Here is the example:

```bash
Outputs:

Webserver-Public-IP = "35.175.111.230"
```

Copy an IP address and add "/index.php" (35.175.111.230/index.php)
Paste it to the browser tab.
