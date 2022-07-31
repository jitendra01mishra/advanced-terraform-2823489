Some of the important notes : 

terraform command :
git@github.com:LinkedInLearning/advanced-terraform-2823489.git

	terraform init 
	terraform plan -out=<out_file_path>.tfplan
	terraform plan -var <variable_that_you_want_to_pass> 
	terraform graph 
	<you can copy this digraph and past it www.webgraphviz.com>
	terraform show <out_file_path>.tfplan
	terraform show -json <out_file_path>.tfplan
	terraform apply <out_file_path>.tfplan
	terraform show
	terraform destroy ---> Never use in production. Just remove those resources from the tf file and it will be destroyed. 


you can view the state file which is in Json formate which will explains what has changed 
also in case we wanted to login to terraform
Just give execute permission
	chmod 400 tf_key.pem
	ssh -i “tf_key.pem” ec2-user@<your_instance_name>

few aws CLI commands : 

export AWS_PAGER="" # -- this is resturn the out put the console .. by it aws cli send the output to the page out 

aws ec2 describe-instances --query "Reservations[].Instances[].InstanceId" --output table 

Terraform Support following variable types : 

	a) String: Development, t2.micro 
	b) boolean: true/false 
	c) Number: integers and fractional values
	d) List: ["DEV","QA","STG","PROD"], [1,15,23,44], var.environment_list[2]
	e) Set: like a list, but unordered 
	f) Map: key-values pairs of the same types with unique key. example : variable "config_value" {type=map(string)}
	g) Object: KEY=VALUE; value can be of any type; for example variable "instance_settings"
	     object({instance_type=string, monitoring=bool})
	h) Tuple: similar to object, stricter type-conversion rules 


setting up variable Values : 

	Files : terraform.tfvars, terraform.tfvars.json, *.auto.tfvars 

	environment variables : export TF_VAR_aws_access_key=[ACCESS_KEY]

	command line : terraform plan -var aws_access_key=[ACCESS_KEY]

Precedence of execution : 

	1. Environment variables 
	2. terraform.tfvars
	3. terraform.tfvars.json
	4. *.auto.tfvars
	5. -var or -var-file command-line options 



