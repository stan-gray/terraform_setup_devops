Deploy the Code and access the webserver
Initialize the Terraform working directory, and download the required providers:

terraform init
Validate the code to look for any errors in syntax, parameters, or attributes within Terraform resources that may prevent it from deploying correctly:

terraform validate
You should receive a notification that the configuration is valid.

Review the actions that will be performed when you deploy the Terraform code:

terraform plan
In this case, it will create 7 resources as configured in the Terraform code.

Deploy the code:

terraform apply
When prompted, type yes, and press Enter.
