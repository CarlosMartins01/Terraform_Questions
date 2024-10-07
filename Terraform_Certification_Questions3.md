
# Terraform - Simulado 3

<br>

### 131
How can a ticket-based system slow down infrastructure provisioning and limit the ability to scale? (Choose two.)<br>

A. A full audit trail of the request and fulfillment process is generated<br>
B. A request must be submitted for infrastructure changes<br>
C. As additional resources are required, more tickets are submitted<br>
D. A catalog of approved resources can be accessed from drop down lists in a request form<br>
 
<br>**#132**<br>
Which of the following statements about Terraform modules is not true?<br>

A. Modules must be publicly accessible<br>
B. Modules can be called multiple times<br>
C. Module is a container for one or more resources<br>
D. Modules can call other modules<br>
 
<br>**#133**<br>
Which Terraform collection type should you use to store key/value pairs?<br>

A. tuple<br>
B. set<br>
C. maׁ€<br>
D. list<br>

<br>**#134**<br>

You have used Terraform to create an ephemeral development environment in the cloud and are now ready to destroy all the infrastructure described by your Terraform configuration. To be safe, you would like to first see all the infrastructure that will be deleted by Terraform.<br>
Which command should you use to show all of the resources that will be deleted? (Choose two.)<br>

A. Run terraform plan -destroy<br>
B. Run terraform show -destroy<br>
C. Run terraform destroy and it will first output all the resources that will be deleted before prompting for approval<br>
D. Run terraform show -destroy<br>
 
<br>**#135**<br>
When do you need to explicitly execute terraform refresh?<br>

A. Before every terraform plan<br>
B. Before every terraform apply<br>
C. Before every terraform import<br>
D. None of the above<br>


<br>**#136**<br>
All Terraform Cloud tiers support team management and governance.<br>

A. True<br>
B. False<br>
 
<br>**#137**<br>
What advantage does an operations team that uses infrastructure as code have?<br>

A. The ability to delete infrastructure<br>
B. The ability to update existing infrastructure<br>
C. The ability to reuse best practice configurations and settings<br>
D. The ability to autoscale a group of servers<br>
 
<br>**#138**<br>
You have modified your Terraform configuration to fix a typo in the Terraform ID of a resource from aws_security_group.http to aws_security_group.http<br>

Which of the following commands would you run to update the ID in state without destroying the resource?<br>

A. terraform mv aws_security_group.htp aws_security_group.http<br>
B. terraform apply<br>
C. terraform refresh<br>
 
<br>**#139**<br>
You are creating a Terraform configuration which needs to make use of multiple providers, one for AWS and one for Datadog.<br>
Which of the following provider blocks would allow you to do this?<br>
A.

B.

C.


 
<br>**#140**<br>
Terraform variable names are saved in the state file.<br>

A. True<br>
B. False<br>
 
<br>**#141**<br>
Terraform Cloud is available only as a paid offering from HashiCorp.<br>

A. True<br>
B. False<br>
 
<br>**#142**<br>
Which of the following is not a way to trigger terraform destroy?<br>

A. Using the destroy command with auto-approve<br>
B. Running terraform destroy from the correct directory and then typing "yes" when prompted in the CLI<br>
C. Passing --destroy at the end of a plan request<br>
D. Delete the state file and run terraform apply<br>
 
<br>**#143**<br>
Which of the following is not an advantage of using infrastructure as code operations?<br>

A. Self-service infrastructure deployment<br>
B. Troubleshoot via a Linux diff command<br>
C. Public cloud console configuration workflows<br>
D. Modify a count parameter to scale resources<br>
E. API driven workflows<br>
 
<br>**#144**<br>
You're writing a Terraform configuration that needs to read input from a local file called id_rsa.pub.<br>
Which built-in Terraform function can you use to import the file's contents as a string?<br>

A. fileset("id_rsa.pub")<br>
B. filebase64("id_rsa.pub")<br>
C. templatefile("id_rsa.pub")<br>
D. file("id_rsa.pub")<br>
 
<br>**#145**<br>
What does Terraform use providers for? (Choose three.)<br>

A. Provision resources for on-premises infrastructure services<br>
B. Simplify API interactions<br>
C. Provision resources for public cloud infrastructure services<br>
D. Enforce security and compliance policies<br>
E. Group a collection of Terraform configuration files that map to a single state file<br>
 
<br>**#146**<br>
You can reference a resource created with for_each using a Splat (*) expression.<br>

A. True<br>
B. False<br>
 
<br>**#147**<br>
How does Terraform determine dependencies between resources?<br>

A. Terraform automatically builds a resource graph based on resources, provisioners, special meta-parameters, and the state file, if present.<br>
B. Terraform requires all dependencies between resources to be specified using the depends_on parameter<br>
C. Terraform requires resources in a configuration to be listed in the order they will be created to determine dependencies<br>
D. Terraform requires resource dependencies to be defined as modules and sourced in order<br>
 
<br>**#148**<br>
Which parameters does terraform import require? (Choose two.)<br>

A. Path<br>
B. Provider<br>
C. Resource ID<br>
D. Resource address<br>
 
<br>**#149**<br>
Once a new Terraform backend is configured with a Terraform code block, which command(s) is (are) used to migrate the state file?<br>

A. terraform apply<br>
B. terraform push<br>
C. terraform destroy, then terraform apply<br>
D. terraform init<br>
 
<br>**#150**<br>
What does this code do?<br>


A. Requires any version of the AWS provider >= 3.0 and < 4.0<br>
B. Requires any version of the AWS provider >= 3.0<br>
C. Requires any version of the AWS provider after the 3.0 major release, like 4.1<br>
D. Requires any version of the AWS provider > 3.0<br>


<br>**#151**<br>
What does terraform refresh modify?<br>

A. Your cloud infrastructure<br>
B. Your state file<br>
C. Your Terraform plan<br>
D. Your Terraform configuration<br>
 
<br>**#152**<br>
Which of the following is not valid source path for specifying a module?<br>

A. source = "./modulelversion=v1.0.0"<br>
B. source = "github.com/hashicorp/example?ref=v1.0.0"<br>
C. source = "./module"<br>
D. source = "hashicorp/consul/aws"<br>
 
<br>**#153**<br>
Which of the following is true about terraform apply? (Choose two.)<br>

A. It only operates on infrastructure defined in the current working directory or workspace<br>
B. You must pass the output of a terraform plan command to it<br>
C. Depending on provider specification, Terraform may need to destroy and recreate your infrastructure resources<br>
D. By default, it does not refresh your state file to reflect current infrastructure configuration<br>
E. You cannot target specific resources for the operation<br>
 
<br>**#154**<br>
Which of the following statements about local modules is incorrect?<br>

A. Local modules are not cached by terraform init command<br>
B. Local modules are sourced from a directory on disk<br>
C. Local modules support versions<br>
D. All of the above (all statements above are incorrect)<br>
E. None of the above (all statements above are correct)<br>
 
<br>**#155**<br>
Which of the following is true about Terraform's implementation of infrastructure as code? (Choose two.)<br>

A. It is only compatible with AWS infrastructure management<br>
B. You cannot reuse infrastructure configuration<br>
C. You can version your infrastructure configuration<br>
D. It requires manual configuration of infrastructure resources<br>
E. It allows you to automate infrastructure provisioning<br>
 
<br>**#156**<br>
You need to write some Terraform code that adds 42 firewall rules to a security group as shown in the example.<br>

What can you use to avoid writing 42 different nested ingress config blocks by hand?<br>

A. A count loop<br>
B. A for block<br>
C. A for each block<br>
D. A dynamic block<br>
 
<br>**#157**<br>
Which of the following is the safest way to inject sensitive values into a Terraform Cloud workspace?<br>

A. Write the value to a file and specify the file with the -var-file flag
B. Set a value for the variable in the UI and check the "Sensitive" check box<br>
C. Edit the state file directly just before running terraform apply<br>
D. Set the variable value on the command line with the -var flag<br>
 
<br>**#158**<br>
terraform apply will fail if you have not am terraform plan first to update the plan output.<br>

A. True<br>
B. False<br>
 
<br>**#159**<br>
How would you reference the attribute "name" of this fictitious resource in HCL?<br>


A. resource.kubernetes_namespace.example.name<br>
B. kubernetes_namespace.test.name<br>
C. kubernetes_namespace.example.name<br>
D. data.kubernetes_namespace.name<br>
E. None of the above<br>
 
<br>**#160**<br>
A Terraform output that sets the "sensitive" argument to true will not store that value in the state file.<br>

A. True<br>
B. False<br>
 
<br>**#161**<br>
Which are forbidden actions when the Terraform state file is locked? (Choose three.)<br>

A. terraform destroy<br>
B. terraform fmt<br>
C. terraform state list<br>
D. terraform apply<br>
E. terraform plan<br>
F. terraform validate<br>
 
<br>**#162**<br>
Terraform installs its providers during which phase?<br>

A. Plan<br>
B. Init<br>
C. Refresh<br>
D. All of the above<br>
 
<br>**#163**<br>
When does Sentinel enforce policy logic during a Terraform Enterprise run?<br>

A. Before the plan phase<br>
B. During the plan phase<br>
C. Before the apply phase<br>
D. After the apply phase<br>
 
<br>**#164**<br>
What is the purpose of a Terraform workspace in either open source or enterprise?<br>

A. Workspaces allow you to manage collections of infrastructure in state files<br>
B. A logical separation of business units<br>
C. A method of grouping multiple infrastructure security policies<br>
D. Provides limited access to a cloud environment<br>
 
<br>**#165**<br>
Which is the best way to specify a tag of v1.0.0 when referencing a module stored in Git (for example git::https://example.com/vpc.git)?<br>

A. Append ?ref=v1. 0. 0 argument to the source path<br>
B. Add version = "1.0.0" parameter to module block<br>
C. Nothing ג€" modules stored on GitHub always default to version 1.0.0<br>
D. Modules stored on GitHub do not support versioning<br>



<br>**#166**<br>
Changing the Terraform backend from the default "local" backend to a different one after doing your first terraform apply is:<br>

A. Mandatory<br>
B. Optional<br>
C. Impossible<br>
D. Discouraged<br>
 
<br>**#167**<br>
You have modified your local Terraform configuration and ran terraform plan to review the changes. Simultaneously, your teammate manually modified the infrastructure component you are working on. Since you already ran terraform plan locally, the execution plan for terraform apply will be the same.<br>

A. True<br>
B. False<br>

<br>**#168**<br>
terraform apply is failing with the following error. What next step should you take to determine the root cause of the problem?<br>
Error loading state: AccessDenied: Access Denied status code: 403, request id: 288766CE5CCA24A0, host id: FOOBAR<br>

A. Set TF_LOG=DEBUG<br>
B. Review syslog for Terraform error messages<br>
C. Run terraform login to reauthenticate with the provider<br>
D. Review /var/log/terraform.log for error messages<br>
 
<br>**#169**<br>
As a member of an operations team that uses infrastructure as code (IaC) practices, you are tasked with making a change to an infrastructure stack running in a public cloud.<br>
Which pattern would follow IaC best practices for making a change?<br>

A. Clone the repository containing your infrastructure code and then run the code<br>
B. Use the public cloud console to make the change after a database record has been approved<br>
C. Make the change programmatically via the public cloud CLI<br>
D. Make the change via the public cloud API endpoint<br>
E. Submit a pull request and wait for an approved merge of the proposed changes<br>
 
<br>**#170**<br>
What command can you run to generate DOT (Document Template) formatted data to visualize Terraform dependencies?<br>

A. terraform refresh<br>
B. terraform show<br>
C. terraform graph<br>
D. terraform output<br>
 
<br>**#171**<br>
Which provider authentication method prevents credentials from being stored in the state file?
<br>
A. Using environment variables<br>
B. Specifying the login credentials in the provider block<br>
C. Setting credentials as Terraform variables<br>
D. None of the above<br>
 
<br>**#172**<br>
Running terraform fmt without any flags in a directory with Terraform configuration files will check the formatting of those files without changing their contents.<br>

A. True<br>
B. False<br>
 
<br>**#173**<br>
terraform init retrieves the source code for all referenced modules.<br>

A. True<br>
B. False<br>
 
<br>**#174**<br>
You have a Terraform configuration that defines a single virtual machine with no references to it. You have run terraform apply to create the resource, and then removed the resource definition from your Terraform configuration file.<br>
What will happen when you run terraform apply in the working directory again?<br>

A. Nothing<br>
B. Terraform will destroy the virtual machine<br>
C. Terraform will error<br>
D. Terraform will remove the virtual machine from the state file, but the resource will still exist<br>
 
<br>**#175**<br>
Which configuration consistency errors does terraform validate report?<br>

A. A mix of spaces and tabs in configuration files<br>
B. Differences between local and remote state<br>
C. Terraform module isn't the latest version<br>
D. Declaring a resource identifier more than once<br>
 
<br>**#176**<br>
In Terraform HCL, an object type of object({ name=string, age=number }) would match this value:<br>
A.

B.


 
<br>**#177**<br>
Where can Terraform not load a provider from?<br>

A. Source code<br>
B. Plugins directory<br>
C. Official HashiCorp distribution on releases.hashicorp.com<br>
D. Provider plugin cache<br>
 
<br>**#178**<br>
Which of the following locations can Terraform use as a private source for modules? (Choose two.)<br>

A. Internally hosted SCM (Source Control Manager) platform<br>
B. Public Terraform Module Registry<br>
C. Private repository on GitHub<br>
D. Public repository on GitHub<br>
 
<br>**#179**<br>
Why should secrets not be hard coded into Terraform code? (Choose two.)<br>

A. It makes the code less reusable.<br>
B. Terraform code is typically stored in version control, as well as copied to the systems from which it's run. Any of those may not have robust security mechanisms.<br>
C. The Terraform code is copied to the target resources to be applied locally and could expose secrets if a target resource is compromised.<br>
D. All passwords should be rotated on a quarterly basis.<br>
 
<br>**#180**<br>
If a Terraform creation-time provisioner fails, what will occur by default?<br>

A. The resource will not be affected, but the provisioner will need to be applied again<br>
B. The resource will be destroyed<br>
C. The resource will be marked as "tainted"<br>
D. Nothing, provisioners will not show errors in the command line<br>



<br>**#181**<br>
When should Terraform configuration files be written when running terraform import on existing infrastructure?<br>

A. Infrastructure can be imported without corresponding Terraform code<br>
B. Terraform will generate the corresponding configuration files for you<br>
C. You should write Terraform configuration files after the next terraform import is executed<br>
D. Terraform configuration should be written before terraform import is executed<br>
 
<br>**#182**<br>
Which command lets you experiment with Terraform's built-in functions?<br>

A. terraform env<br>
B. terraform console<br>
C. terraform test<br>
D. terraform validate<br>
 
<br>**#183**<br>
Why does this backend configuration not follow best practices?<br>


A. You should not store credentials in Terraform Configuration<br>
B. You should use the local enhanced storage backend whenever possible<br>
C. An alias meta-argument should be included in backend blocks whenever possible<br>
D. The backend configuration should contain multiple credentials so that more than one user can execute terraform plan and terraform apply<br>
 
<br>**#184**<br>
Open source Terraform can only import publicly-accessible and open-source modules.<br>

A. True<br>
B. False<br>
 
<br>**#185**<br>
What does terraform destroy do?<br>

A. Destroy all infrastructure in the Terraform state file<br>
B. Destroy all Terraform code files in the current directory while leaving the state file intact<br>
C. Destroy all infrastructure in the configured Terraform provider<br>
D. Destroy the Terraform state file while leaving infrastructure intact<br>
 
<br>**#186**<br>
While attempting to deploy resources into your cloud provider using Terraform, you begin to see some odd behavior and experience sluggish responses. In order to troubleshoot you decide to turn on Terraform debugging. Which environment variables must be configured to make Terraform's logging more verbose?<br>

A. TF_LOG_LEVEL<br>
B. TF_LOG_FILE<br>
C. TF_LOG<br>
D. TP_LOG_PATH<br>
 
<br>**#187**<br>
If a DevOps team adopts AWS CloudFormation as their standardized method for provisioning public cloud resources, which of the following scenarios poses a challenge for this team?<br>

A. The team is asked to build a reusable code base that can deploy resources into any AWS region<br>
B. The team is asked to manage a new application stack built on AWS-native services<br>
C. The organization decides to expand into Azure and wishes to deploy new infrastructure using their existing codebase<br>
D. The DevOps team is tasked with automating a manual provisioning process<br>
 
<br>**#188**<br>
You cannot install third party plugins using terraform init.<br>

A. True<br>
B. False<br>
 
<br>**#189**<br>
Which of the following can you do with terraform plan? (Choose two.)<br>

A. Save a generated execution plan to apply later<br>
B. Execute a plan in a different workspace<br>
C. View the execution plan and check if the changes match your expectations<br>
D. Schedule Terraform to run at a planned time in the future<br>


<br>**#190**<br>
Which are examples of infrastructure as code? (Choose two.)<br>

A. Cloned virtual machine images<br>
B. Change management database records<br>
C. Versioned configuration files<br>
D. Docker files<br>


<br>**#191**<br>
FILL BLANK -<br>
You need to migrate a workspace to use a remote backend. After updating your configuration, what command do you run to perform the migration?
Type your answer in the field provided. The text field is not case-sensitive and all variations of the correct answer are accepted.<br>

 
<br>**#192**<br>
When using a module from the public Terraform Module Registry, the following parameters are required attributes in the module block. (Choose two.)<br>

A. Each of the module’s required inputs<br>
B. The module’s source address<br>
C. Terraform Module Registry account token<br>
D. Each of the module’s dependencies (example: submodules)<br>
E. The version of the module<br>
 
<br>**#193**<br>
As a developer, you want to ensure your plugins are up to date with the latest versions. Which Terraform command should you use?<br>

A. terraform init -upgrade<br>
B. terraform apply -upgrade<br>
C. terraform refresh -upgrade<br>
D. terraform providers -upgrade<br>
 
<br>**#194**<br>
You can access state stored with the local backend by using the terraform_remote_state data source.<br>

A. True<br>
B. False<br>

<br>**#195**<br>
You have been working in a Cloud provider account that is shared with other team members. You previously used Terraform to create a load balancer that is listening on port 80. After some application changes, you updated the Terraform code to change the port to 443.<br>

You run terraform plan and see that the execution plan shows the port changing from 80 to 443 like you intended, and step away to grab some coffee.<br>

In the meantime, another team member manually changes the load balancer port to 443 through the Cloud provider console before you get back to your desk.<br>

What will happen when you terraform apply upon returning to your desk?<br>

A. Terraform will fail with an error because the state file is no longer accurate.<br>
B. Terraform will change the load balancer port to 80, and then change it back to 443.<br>
C. Terraform will not make any changes to the Load Balancer and will update the state file to reflect any changes made.<br>
D. Terraform will change the port back to 80 in your code.<br>
