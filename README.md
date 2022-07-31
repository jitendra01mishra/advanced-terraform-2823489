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



# Advanced Terraform
This is the repository for the LinkedIn Learning course Advanced Terraform. The full course is available from [LinkedIn Learning][lil-course-url].

![Advanced Terraform][lil-thumbnail-url] 
Terraform simplifies and accelerates the configuration of cloud-based environments. DevOps engineers looking to use Terraform in the real world can start by learning how to work with the Terraform CLI and the HashiCorp Configuration Language (HCL). In this course, David Swersky covers these concepts and more, helping you go beyond the basics with this powerful infrastructure as code solution. Using practical use cases, David shows how to manage and automate your infrastructure with Terraform. He steps through how to analyze an existing application running in a client's data center, and design a Terraform configuration that supports the application in AWS. He also goes over advanced concepts, including how to set the values of variables in a Terraform configuration. Plus, he steps through how to develop an application infrastructure with Terraform, create an infrastructure CI/CD pipeline using GitHub and Terraform Cloud, and more.

## Instructions
This repository has a folder for each of the videos in the course. The naming convention is [CHAPTER]_[NAME], e.g.: **01_05_base**


## Installing
1. To use these exercise files, you must have the following installed:
	- [list of requirements for course]
2. Fork this repository to your own account
3. Clone your fork to your local machine using the terminal (Mac), CMD (Windows), or a GUI tool like SourceTree.

### Instructor

**David Swersky**

_DevOps and Enterprise Architect with 20+ years of IT experience_

Check out some of my other courses on [LinkedIn Learning](https://www.linkedin.com/learning/instructors/david-swersky).

[lil-course-url]: https://www.linkedin.com/learning/advanced-terraform
[lil-thumbnail-url]: https://cdn.lynda.com/course/2823489/2823489-1604938909984-16x9.jpg
