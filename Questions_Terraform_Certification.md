
	**Terraform exam questions**


<br>**#1**<br>
The terraform.tfstate file always matches your currently built infrastructure.<br>

A. True<br>
**B**. False<br>

<br>**#2**<br>
One remote backend configuration always maps to a single remote workspace.<br>

A. True<br>
**B**. False<br>
 
<br>**#3**<br>

How is the Terraform remote backend different than other state backends such as S3, Consul, etc.?<br>

**A**. It can execute Terraform runs on dedicated infrastructure on premises or in Terraform Cloud<br>
B. It doesn't show the output of a terraform apply locally<br>
C. It is only available to paying customers<br>
D. All of the above<br>
 
<br>**#4**<br>
What is the workflow for deploying new infrastructure with Terraform?<br>

A. terraform plan to import the current infrastructure to the state file, make code changes, and terraform apply to update the infrastructure.<br>
B. Write a Terraform configuration, run terraform show to view proposed changes, and terraform apply to create new infrastructure.<br>
C. terraform import to import the current infrastructure to the state file, make code changes, and terraform apply to update the infrastructure.<br>
**D**. Write a Terraform configuration, run terraform init, run terraform plan to view planned infrastructure changes, and terraform apply to create new infrastructure.<br>
 
<br>**#5**<br>
A provider configuration block is required in every Terraform configuration.<br>
Example:<br>
```
provider "provider_name" {
...
}
```

**A**. True<br>
B. False<br>
 
Um bloco de configuração do provider não é sempre necessário em cada configuração do Terraform. O Terraform pode herdar configurações de provider de outros lugares, como de um módulo ou de variáveis de ambiente configuradas para autenticação. Em casos onde há blocos de configuração compartilhados ou onde o provider é especificado em outro lugar, o bloco provider pode não ser explicitamente necessário.<br>

A provider configuration block is not required in every Terraform configuration. Terraform can inherit provider configurations from other sources, such as modules, environment variables, or default configuration files. If the provider configuration is already defined elsewhere or is managed externally, the provider block may not be necessary in that specific configuration.<br>

<br>**#6**<br>
You run a local-exec provisioner in a null resource called null_resource.run_script and realize that you need to rerun the script.<br>
Which of the following commands would you use first?<br>

**A**. terraform taint null_resource.run_script<br>
B. terraform apply -target=null_resource.run_script<br>
C. terraform validate null_resource.run_script<br>
D. terraform plan -target=null_resource.run_script<br>

A. **terraform taint null_resource.run_script**<br>

The terraform taint command marks a resource for recreation on the next terraform apply. In this case, marking null_resource.run_script as tainted ensures that the local-exec provisioner will run again when you next apply the changes. This is necessary because null resources, by default, are not re-executed unless explicitly tainted or the resource itself has changed.<br>

Here’s why the other options are not suitable:<br>

B. **terraform apply -target=null_resource.run_script**: This would apply changes, but if the resource is not marked as tainted, the script won't rerun.<br>
C. **terraform validate null_resource.run_script**: This checks the syntax of your configuration but doesn't trigger any execution or rerun the script.<br>
D. **terraform plan -target=null_resource.run_script**: This shows what changes would be applied, but it doesn't rerun the provisioner unless the resource is marked tainted.<br>
 

<br>**#7**<br>
Which provisioner invokes a process on the resource created by Terraform?<br>

**A**. remote-exec<br>
B. null-exec<br>
C. local-exec<br>
D. file<br>
 
<br>**#8**<br>
Which of the following is not true of Terraform providers?<br>

A. Providers can be written by individuals<br>
B. Providers can be maintained by a community of users<br>
C. Some providers are maintained by HashiCorp<br>
D. Major cloud vendors and non-cloud vendors can write, maintain, or collaborate on Terraform providers<br>
**E**. None of the above<br>
 
<br>**#9**<br>
What command does Terraform require the first time you run it within a configuration directory?<br>

A. terraform import<br>
**B**. terraform init<br>
C. terraform plan<br>
D. terraform workspace<br>
 
<br>**#10**<br>
You have deployed a new webapp with a public IP address on a cloud provider. However, you did not create any outputs for your code.<br>
What is the best method to quickly find the IP address of the resource you deployed?<br>

A. Run terraform output ip_address to view the result<br>
B. In a new folder, use the terraform_remote_state data source to load in the state file, then write an output for each resource that you find the state file<br>
**C**. Run terraform state list to find the name of the resource, then terraform state show to find the attributes including public IP address<br>
D. Run terraform destroy then terraform apply and look for the IP address in stdout<br>
 
<br>**#11**<br>
Which of the following is not a key principle of infrastructure as code?<br>

A. Versioned infrastructure<br>
**B**. Golden images<br>
C. Idempotence<br>
D. Self-describing infrastructure<br>
 
<br>**#12**<br>
Terraform variables and outputs that set the "description" argument will store that description in the state file.<br>

**A**. True<br>
B. False<br>

When you set the description argument for variables and outputs in Terraform, the description is indeed stored in the state file. This is primarily useful for providing context or documentation for the variables and outputs when inspecting or reviewing the state.<br>

<br>**#13**<br>
What is the provider for this fictitious resource?<br>
>resource "aws_vpc" "main" {<br>
>	name = "test"	<br>
>}<br>

A. vpc<br>
B. main<br>
**C**. aws<br>
D. test<br>
 
<br>**#14**<br>
If you manually destroy infrastructure, what is the best practice reflecting this change in Terraform?<br>

A. Run terraform refresh<br>
B. It will happen automatically<br>
**C**. Manually update the state fire<br>
D. Run terraform import<br>

A. **Run terraform refresh**<br>

When you manually destroy infrastructure, the best practice is to run terraform refresh. This command updates the Terraform state by comparing the actual infrastructure with the state file. It will detect that the resources were destroyed manually and update the state file accordingly, reflecting the current state of the infrastructure.<br>

Here's why the other options are not correct:<br>

B. **It will happen automatically**: Terraform does not automatically update the state when changes are made outside of Terraform. You need to manually trigger this with a command like terraform refresh.<br>
C. **Manually update the state file**: It's not recommended to manually edit the state file, as this can lead to errors and inconsistencies.<br>
D. **Run terraform import**: This command is used to import existing resources into the Terraform state, not for updating the state after resources have been destroyed.<br>

<br>**#15**<br>
What is not processed when running a terraform refresh?<br>

A. State file<br>
**B**. Configuration file<br>
C. Credentials<br>
D. Cloud provider<br>

<br>**#16**<br>
What information does the public Terraform Module Registry automatically expose about published modules?<br>

A. Required input variables<br>
B. Optional inputs variables and default values<br>
C. Outputs<br>
**D**. All of the above<br>
E. None of the above<br>
 
<br>**#17**<br>
If a module uses a local values, you can expose that value with a terraform output.<br>

**A.** True<br>
B. False<br>
 
<br>**#18**<br>
You should store secret data in the same version control repository as your Terraform configuration.<br>

A. True<br>
**B**. False<br>
 
<br>**#19**<br>
Which of the following is not a valid string function in Terraform?<br>

A. split<br>
B. join<br>
**C**. slice<br>
D. chomp<br>

**C. slice**<br>

The slice function is not a valid string function in Terraform. While split, join, and chomp are valid Terraform string functions, slice is not used in Terraform's string manipulation functions.<br>

Here’s a brief overview of the valid functions:<br>

A. **split**: Splits a string into a list based on a delimiter.<br>
B. **join**: Joins elements of a list into a single string with a specified separator.<br>
D. **chomp**: Removes the trailing newline from a string.<br>
There is no slice function for strings in Terraform; however, there is a slice function for lists in certain programming languages or tools, but not for Terraform strings.<br>

<br>**#20**<br>
You have provisioned some virtual machines (VMs) on Google Cloud Platform (GCP) using the gcloud command line tool. However, you are standardizing with
Terraform and want to manage these VMs using Terraform instead.<br>
What are the two things you must do to achieve this? (Choose two.)<br>

A. Provision new VMs using Terraform with the same VM names<br>
**B**. Use the terraform import command for the existing VMs<br>
**C**. Write Terraform configuration for the existing VMs<br>
D. Run the terraform import-gcp command<br>
 
<br>**#21**<br>
You have recently started a new job at a retailer as an engineer. As part of this new role, you have been tasked with evaluating multiple outages that occurred during peak shopping time during the holiday season. Your investigation found that the team is manually deploying new compute instances and configuring each compute instance manually. This has led to inconsistent configuration between each compute instance.<br>
How would you solve this using infrastructure as code?<br>

A. Implement a ticketing workflow that makes engineers submit a ticket before manually provisioning and configuring a resource<br>
B. Implement a checklist that engineers can follow when configuring compute instances<br>
C. Replace the compute instance type with a larger version to reduce the number of required deployments<br>
**D**. Implement a provisioning pipeline that deploys infrastructure configurations committed to your version control system following code reviews<br>
 
<br>**#22**<br>
terraform init initializes a sample main.tf file in the current directory.<br>

A. True<br>
**B**. False<br>
 
<br>**#23**<br>
Which two steps are required to provision new infrastructure in the Terraform workflow? (Choose two.)<br>

A. Destroy<br>
**B**. Apply<br>
C. Import<br>
**D**. Init<br>
E. Validate<br>
 
<br>**#24**<br>
Why would you use the terraform taint command?<br>

A. When you want to force Terraform to destroy a resource on the next apply<br>
**B**. When you want to force Terraform to destroy and recreate a resource on the next apply<br>
C. When you want Terraform to ignore a resource on the next apply<br>
D. When you want Terraform to destroy all the infrastructure in your workspace<br>
 
<br>**#25**<br>
Terraform requires the Go runtime as a prerequisite for installation.<br>

A. True<br>
**B**. False<br>
 
<br>**#26**<br>
When should you use the force-unlock command?<br>

A. You see a status message that you cannot acquire the lock<br>
B. You have a high priority change<br>
**C**. Automatic unlocking failed<br>
D. You apply failed due to a state lock<br>

**C. Automatic unlocking failed**

The terraform force-unlock command is used when Terraform’s automatic unlocking of the state file has failed. Normally, when you run Terraform commands, it acquires a lock on the state to avoid concurrent modifications. If something goes wrong (e.g., an apply or plan command is interrupted), Terraform may not automatically release the lock, and in this case, you would need to use terraform force-unlock to manually release the lock.

Here’s why the other options are not correct:

A. **You see a status message that you cannot acquire the lock**: Before using force-unlock, it’s better to ensure no other operations are running. This message doesn't immediately indicate a need to force unlock.
B. **You have a high priority change**: Urgency doesn’t justify using force-unlock. It's only used when the lock is stuck.
D. **You apply failed due to a state lock**: Instead of using force-unlock right away, first investigate why the lock exists. Use force-unlock only if the lock cannot be automatically released.

<br>**#27**<br>
Terraform can import modules from a number of sources `" which of the following is not a valid source?<br>

**A**. FTP server
B. GitHub repository
C. Local path
D. Terraform Module Registry
 
<br>**#28**<br>
Which of the following is available only in Terraform Enterprise or Cloud workspaces and not in Terraform CLI?<br>

**A**. Secure variable storage<br>
B. Support for multiple cloud providers<br>
C. Dry runs with terraform plan<br>
D. Using the workspace as a data source<br>
 
<br>**#29**<br>
terraform validate validates the syntax of Terraform files.<br>

**A**. True<br>
B. False<br>

<br>**#30**<br>
You have used Terraform to create an ephemeral development environment in the cloud and are now ready to destroy all the infrastructure described by your Terraform configuration. To be safe, you would like to first see all the infrastructure that will be deleted by Terraform.<br>
Which command should you use to show all of the resources that will be deleted? (Choose two.)<br>

**A**. Run terraform plan -destroy.<br>
B. This is not possible. You can only show resources that will be created.<br>
C. Run terraform state rm *.<br>
**D**. Run terraform destroy and it will first output all the resources that will be deleted before prompting for approval.<br>

A. Run **terraform plan -destroy**. D. Run **terraform destroy** and it will first output all the resources that will be deleted before prompting for approval.<br>

Explanation:<br>

A. **terraform plan -destroy**: This command shows a detailed plan of what resources will be destroyed, giving you an opportunity to review them before taking action.<br>
D. **terraform destroy**: When you run this command, it will show all resources scheduled for deletion and prompt you for approval before proceeding with the actual destruction.<br>
The other options are incorrect:<br>

B. **This is not possible**: This is false. Terraform can show resources that will be destroyed using the plan -destroy command.<br>
C. Run **terraform state rm * :/** This command removes resources from the state file but doesn't destroy them. This is not what you want when reviewing deletions.<br>


<br>**#31**<br>
Which of the following is the correct way to pass the value in the variable num_servers into a module with the input servers?<br>

A. servers = num_servers<br>
B. servers = variable.num_servers<br>
C. servers = var(num_servers)<br>
**D**. servers = var.num_servers<br>
 
<br>**#32**<br>
A Terraform provisioner must be nested inside a resource configuration block.<br>

**A**. True<br>
B. False<br>

**A. True**

A Terraform provisioner must be nested inside a resource configuration block.
Provisioners are used to execute scripts or commands on a resource once it's created or destroyed, and they must be associated with a specific resource to function. They cannot exist outside of a resource block.<br>

<br>**#33**<br>
Terraform can run on Windows or Linux, but it requires a Server version of the Windows operating system.<br>

A. True<br>
**B**. False<br>
 
<br>**#34**<br>
What does the default "local" Terraform backend store?<br>

A. tfplan files<br>
B. Terraform binary<br>
C. Provider plugins<br>
**D**. State file<br>
 
<br>**#35**<br>
You have multiple team members collaborating on infrastructure as code (IaC) using Terraform, and want to apply formatting standards for readability.<br>
How can you format Terraform HCL (HashiCorp Configuration Language) code according to standard Terraform style convention?<br>

**A**. Run the terraform fmt command during the code linting phase of your CI/CD process<br>
B. Designate one person in each team to review and format everyone's code<br>
C. Manually apply two spaces indentation and align equal sign "=" characters in every Terraform file (*.tf)<br>
D. Write a shell script to transform Terraform files using tools such as AWK, Python, and sed<br>
 
<br>**#36**<br>
What value does the Terraform Cloud/Terraform Enterprise private module registry provide over the public Terraform Module Registry?<br>

A. The ability to share modules with public Terraform users and members of Terraform Enterprise Organizations<br>
B. The ability to tag modules by version or release<br>
**C**. The ability to restrict modules to members of Terraform Cloud or Enterprise organizations<br>
D. The ability to share modules publicly with any user of Terraform<br>
 
<br>**#37**<br>
Which task does terraform init not perform?<br>

A. Sources all providers present in the configuration and ensures they are downloaded and available locally<br>
B. Connects to the backend<br>
C. Sources any modules and copies the configuration locally<br>
**D**. Validates all required variables are present<br>
 
**D. Validates all required variables are present**<br>

The terraform init command does not validate required variables. That task is typically performed during the terraform plan or terraform apply phases.<br>

Here’s what the other options do:<br>

A. **Sources all providers present in the configuration and ensures they are downloaded and available locally**: terraform init installs the necessary providers.<br>
B. **Connects to the backend**: terraform init sets up the backend configuration, enabling state storage and management.<br>
C. **Sources any modules and copies the configuration locally**: terraform init downloads and sets up modules as specified in the configuration.<br>


<br>**#38**<br>
You have declared a variable called var.list which is a list of objects that all have an attribute id.<br>
Which options will produce a list of the IDs? (Choose two.)<br>

A. { for o in var.list : o => o.id }<br>
**B**. var.list[*].id<br>
C. [ var.list[*].id ]<br>
D. [ for o in var.list : o.id ]<br>

B. var.list[*].id
**D**. [ for o in var.list : o.id ]

B. **var.list[*].id**: This uses Terraform’s splat expression to extract the id attribute from each object in var.list.<br>
D. **[ for o in var.list : o.id ]*: This uses a for expression to iterate over each object in var.list and extract the id attribute, returning a list of the IDs.<br>
The other options are incorrect:<br>

A. **{ for o in var.list : o => o.id }**: This creates a map with the object o as the key and o.id as the value, not a list of IDs.<br>
C. **[ var.list[*].id ]**: This would wrap the list of IDs in another list, resulting in a list of lists, which is not the desired output.<br>

<br>**#39**<br>
Which argument(s) is (are) required when declaring a Terraform variable?<br>

A. type<br>
B. default<br>
C. description<br>
D. All of the above<br>
**E**. None of the above<br>

**E. None of the above**

None of the arguments (type, default, description) are strictly required when declaring a Terraform variable. You can declare a variable with just the variable name like this:

>hcl<br>
>variable "example" {}

However, these arguments are optional and can be used to enhance the variable declaration:<br>

- type: Specifies the type of the variable (e.g., string, list, map).<br>
- default: Provides a default value for the variable.<br>
- description: Provides documentation or context for the variable.<br>
But none of them are mandatory for declaring a variable in Terraform. If no default value is provided, the variable will be required at runtime.<br>


<br>**#40**<br>
When using a module block to reference a module stored on the public Terraform Module Registry such as:<br>
>module "consul" {<br>
>	source = "hashicorp/consul/aws<br>
>}<br>

How do you specify version 1.0.0?<br>

A. Modules stored on the public Terraform Module Registry do not support versioning<br>
B. Append ?ref=v1.0.0 argument to the source path<br>
**C**. Add version = "1.0.0" attribute to module block<br>
D. Nothing ג€" modules stored on the public Terraform Module Registry always default to version 1.0.0<br>
 
<br>**#41**<br>
What features does the hosted service Terraform Cloud provide? (Choose two.)<br>

A. Automated infrastructure deployment visualization<br>
B. Automatic backups<br>
**C**. Remote state storage<br>
**D**. A web-based user interface (UI)<br>
 
<br>**#42**<br>
Where does the Terraform local backend store its state?<br>

A. In the /tmp directory<br>
B. In the terraform file<br>
**C**. In the terraform.tfstate file<br>
D. In the user's terraform.state file<br>
 
<br>**#43**<br>
Which option can not be used to keep secrets out of Terraform configuration files?<br>

A. A Terraform provider<br>
B. Environment variables<br>
C. A -var flag<br>
**D**. secure string<br>

D. **secure string**<br>

Terraform does not have a built-in secure string data type. Although you can use various methods to protect sensitive data, such as providers, environment variables, or passing variables securely, there is no specific secure string type in Terraform.<br>

Here’s why the other options are valid:<br>

A. **A Terraform provider**: Some providers, such as those for cloud services, can retrieve secrets from secure sources like a vault or secret management service.<br>
B. **Environment variables**: You can use environment variables to store sensitive information like API keys or passwords.<br>
C. **A -var flag**: You can pass variables securely at runtime using the -var flag to avoid hardcoding secrets in configuration files.<br>
Therefore, secure string is not a valid option in Terraform.<br>

<br>**#44**<br>
What is one disadvantage of using dynamic blocks in Terraform?<br>

A. They cannot be used to loop through a list of values<br>
B. Dynamic blocks can construct repeatable nested blocks<br>
**C**. They make configuration harder to read and understand<br>
D. Terraform will run more slowly<br>
 
<br>**#45**<br>
Only the user that generated a plan may apply it.<br>

A. True<br>
**B**. False<br>


<br>**#46**<br>
Examine the following Terraform configuration, which uses the data source for an AWS AMI.<br>
What value should you enter for the ami argument in the AWS instance resource?<br>

>data "aws_ami" "ubuntu" {<br>
>	...<br>
>}<br>
>
>resource "aws_instance" "web" { <br>
>	ami = <br>
>	instance_type = "t2.micro"<br>
>
>	tags = {<br>
>		Name = "HelloWorld"<br>
>   }<br>
>}<br>

A. aws_ami.ubuntu<br>
B. data.aws_ami.ubuntu<br>
**C**. data.aws_ami.ubuntu.id<br>
D. aws_ami.ubuntu.id<br>

C. **data.aws_ami.ubuntu.id**

In Terraform, when you reference a data source, you need to include the full path to the specific attribute you're using. In this case, the correct attribute for the AMI ID is id.<br>

So, the correct syntax for the ami argument in the aws_instance resource would be:<br>

>hcl<br>
>ami = data.aws_ami.ubuntu.id<br>
>Here’s why the other options are incorrect:<br>

A. **aws_ami.ubuntu**: This references the data source but does not access a specific attribute, such as id.<br>
B. **data.aws_ami.ubuntu**: This references the data source, but you need to specifically access the id attribute.<br>
D. **aws_ami.ubuntu.id**: This omits the data. prefix, which is required when referencing data sources in Terraform.<br>


<br>**#47**<br>
FILL BLANK -<br>
You need to specify a dependency manually.<br>
What resource meta-parameter can you use to make sure Terraform respects the dependency?<br>
Type your answer in the field provided. The text field is not case-sensitive and all variations of the correct answer are accepted.<br>

**depends_on**

 
<br>**#48**<br>
You have never used Terraform before and would like to test it out using a shared team account for a cloud provider. The shared team account already contains 15 virtual machines (VM). You develop a Terraform configuration containing one VM, perform terraform apply, and see that your VM was created successfully.<br>
What should you do to delete the newly-created VM with Terraform?<br>

A. The Terraform state file contains all 16 VMs in the team account. Execute terraform destroy and select the newly-created VM.<br>
**B**. The Terraform state file only contains the one new VM. Execute terraform destroy.<br>
C. Delete the Terraform state file and execute Terraform apply.<br>
D. Delete the VM using the cloud provider console and terraform apply to apply the changes to the Terraform state file.<br>

**B. The Terraform state file only contains the one new VM. Execute terraform destroy.**<br>

Terraform only manages the infrastructure that is defined in its configuration files and tracked in its state file. Since you created just one VM using Terraform, the state file will only include that newly created VM. When you run terraform destroy, it will only affect resources that are in the state file—in this case, the single VM that you created with Terraform.<br>

Here’s why the other options are incorrect:<br>

A. **The Terraform state file contains all 16 VMs**: This is incorrect. Terraform only manages resources it creates and tracks in the state file, so the state file will not include the other 15 VMs that were created outside of Terraform.<br>
C. **Delete the Terraform state file and execute Terraform apply**: This would recreate the VM, not destroy it, as Terraform would assume no resources exist.<br>
D. **Delete the VM using the cloud provider console and terraform apply**: This is not recommended because deleting the resource outside of Terraform would leave the state file in an inconsistent state. You should always use Terraform to manage resources it created.<br>


<br>**#49**<br>
What is the name assigned by Terraform to reference this resource?<br>
>resource "azurerm_resource_group" "dev" {<br>
>    name = "test"<br>
>    location - "westus"<br>
>}<br>

**A**. dev<br>
B. azurerm_resource_group<br>
C. azurerm<br>
D. test<br>
 
<br>**#50**<br>
Setting the TF_LOG environment variable to DEBUG causes debug messages to be logged into syslog.<br>

A. True<br>
**B**. False<br>

**B. False**<br>

Setting the TF_LOG environment variable to DEBUG will output debug messages to the terminal (standard output), not to syslog. Terraform logs debug information directly to the console or wherever the output is directed, such as a file if you choose to redirect it. It does not automatically log to syslog.<br>

If you need to send logs to syslog, you would need to configure this redirection manually.<br>


<br>**#51**<br>
Where in your Terraform configuration do you specify a state backend?<br>

**A**. The terraform block<br>
B. The resource block<br>
C. The provider block<br>
D. The datasource block<br>


<br>**#52**<br>
In Terraform 0.13 and above, outside of the required_providers block, Terraform configurations always refer to providers by their local names.<br>

**A**. True<br>
B. False<br>

**A. True**<br>

In Terraform 0.13 and above, outside of the required_providers block, providers are always referred to by their local names. The local name is the alias or identifier you assign to a provider in your configuration, which allows you to reference the provider throughout your configuration without needing to specify its source or version every time. The required_providers block is where you specify the full source address and version constraints for the provider.<br>


<br>**#53**<br>
What command should you run to display all workspaces for the current configuration?<br>

A. terraform workspace<br>
B. terraform workspace show<br>
**C**. terraform workspace list<br>
D. terraform show workspace<br>
 
<br>**#54**<br>
Terraform providers are always installed from the Internet.<br>

A. True<br>
**B**. False<br>

**B. False**<br>

Terraform providers are not always installed from the Internet. While the default behavior is to download providers from Terraform’s provider registry, you can also install providers from other sources. For example, you can configure Terraform to use:<br>

**- Local provider binaries** stored on your system.<br>
**- Private provider registries** within your organization.<br>
**- Mirror directories** to cache providers locally for offline use.<br>
These options provide flexibility, especially in environments with restricted Internet access or when using custom providers.<br>

<br>**#55**<br>
Which of these is the best practice to protect sensitive values in state files?<br>
A. Sources all providers present in the configuration and ensures they are downloaded and available locally<br>
B. Connects to the backend<br>
C. Sources any modules and copies the configuration locally<br>
**D**. Validates all required variables are present<br>
 
**D. Validates all required variables are present**<br>

<br>**#58**<br>
A Terraform provider is not responsible for:<br>

A. Understanding API interactions with some service<br>
**B**. Provisioning infrastructure in multiple clouds<br>
C. Exposing resources and data sources based on an API<br>
D. Managing actions to take based on resource differences<br>
 
<br>**#59**<br>
Terraform provisioners can be added to any resource block.<br>

**A**. True<br>
B. False<br>
 
<br>**#60**<br>
What is terraform refresh intended to detect?<br>

A. Terraform configuration code changes<br>
B. Empty state files<br>
**C**. State file drift<br>
D. Corrupt state files<br>

**C. State file drift**<br>

terraform refresh is intended to detect state file drift, which occurs when the actual infrastructure has changed (e.g., manually modified or updated outside of Terraform) but the Terraform state file does not reflect those changes. Running terraform refresh updates the state file to reflect the current state of the real infrastructure without making any changes to the infrastructure itself.<br>

Here’s why the other options are incorrect:<br>

A. **Terraform configuration code changes**: terraform refresh doesn't detect configuration changes; terraform plan does.<br>
B. **Empty state files**: terraform refresh is not designed to handle empty state files.<br>
D. **Corrupt state files**: It does not repair or detect corrupt state files.<br>

<br>**#61**<br>
FILL BLANK -<br>
Which flag would you add to terraform plan to save the execution plan to a file?<br>
Type your answer in the field provided. The text field is not case-sensitive and all variations of the correct answer are accepted.<br>

**-out=FILE_NAME**<br>
 
The flag you would add to terraform plan to save the execution plan to a file is:<br>

**-out**<br>

For example, the command would look like this:<br>

>bash<br>
>terraform plan -out=planfile<br>

<br>**#62**<br>
FILL BLANK -<br>
What is the name of the default file where Terraform stores the state?<br>
Type your answer in the field provided. The text field is not case-sensitive and all variations of the correct answer are accepted.<br>

**terraform.tfstate**
 
<br>**#63**<br>
A Terraform local value can reference other Terraform local values.<br>

**A**. True<br>
B. False<br>

**A. True**<br>

In Terraform, a local value can reference other local values. This allows for organizing and simplifying complex expressions by breaking them into smaller, more manageable pieces. However, the order of the local values matters, and Terraform will resolve them accordingly.<br>

<br>**#64**<br>
Which of the following is not a valid Terraform collection type?<br>

A. list<br>
B. map<br>
**C**. tree<br>
D. set<br>
 
<br>**#65**<br>
When running the command terraform taint against a managed resource you want to force recreation upon, Terraform will immediately destroy and recreate the resource.<br>

A. True<br>
**B**. False<br>


<br>

---

---
<br>




<br>**#66**<br>
All standard backend types support state storage, locking, and remote operations like plan, apply and destroy.<br>

A. True<br>
**B**. False<br>

**B. False**

Not all standard backend types in tools like Terraform support state storage, locking, and remote operations such as plan, apply, and destroy. Some backends only support basic state storage and retrieval, while others, such as the remote backend, support additional features like state locking and remote operations.<br>

<br>**#67**<br>
How can terraform plan aid in the development process?<br>

**A**. Validates your expectations against the execution plan without permanently modifying state<br>
B. Initializes your working directory containing your Terraform configuration files<br>
C. Formats your Terraform configuration files<br>
D. Reconciles Terraform's state against deployed resources and permanently modifies state using the current status of deployed resources<br>

**A. Validates your expectations against the execution plan without permanently modifying state**

terraform plan helps in the development process by showing you what changes will be made without actually making any changes to your infrastructure or state. It helps validate whether the resources and configurations you intend to modify, add, or remove align with your expectations.<br>

<br>**#68**<br>
You would like to reuse the same Terraform configuration for your development and production environments with a different state file for each.<br>
Which command would you use?<br>

A. terraform import<br>
**B**. terraform workspace<br>
C. terraform state<br>
D. terraform init<br>
 
<br>**#69**<br>
What is the name assigned by Terraform to reference this resource?<br>
>mainresource "google_compute_instance" "main" {<br>
>  name = "test"<br>
>}<br>

A. compute_instance<br>
**B**. main<br>
C. google<br>
D. teat<br>
 
<br>**#70**<br>
You're building a CI/CD (continuous integration/ continuous delivery) pipeline and need to inject sensitive variables into your Terraform run.<br>
How can you do this safely?<br>

**A**. Pass variables to Terraform with a ג€"var flag<br>
B. Copy the sensitive variables into your Terraform code<br>
C. Store the sensitive variables in a secure_vars.tf file<br>
D. Store the sensitive variables as plain text in a source code repository<br>
 
<br>**#71**<br>
Your security team scanned some Terraform workspaces and found secrets stored in a plaintext in state files.<br>
How can you protect sensitive data stored in Terraform state files?<br>

A. Delete the state file every time you run Terraform<br>
**B**. Store the state in an encrypted backend<br>
C. Edit your state file to scrub out the sensitive data<br>
D. Always store your secrets in a secrets.tfvars file.<br>

**B. Store the state in an encrypted backend**

Storing the Terraform state in an encrypted backend (such as using an encrypted S3 bucket, HashiCorp Vault, or other secure backends) ensures that sensitive data is protected. Terraform state can contain sensitive information like secrets, and encryption helps mitigate risks of exposure.<br>

Here’s why other options are incorrect:<br>

A. **Delete the state file every time you run Terraform**: Deleting the state file would cause Terraform to lose track of resources, potentially leading to unmanaged infrastructure.<br>
C. **Edit your state file to scrub out the sensitive data**: Manually editing the state file is error-prone and does not provide a secure, automated solution.<br>
D. **Always store your secrets in a secrets.tfvars file**: While storing secrets in a separate file can be a good practice, it does not solve the issue of secrets being stored in the state file itself.<br>

<br>**#72**<br>
In contrast to Terraform Open Source, when working with Terraform Enterprise and Cloud Workspaces, conceptually you could think about them as completely separate working directories.<br>

**A**. True<br>
B. False<br>
 
<br>**#73**<br>
You want to know from which paths Terraform is loading providers referenced in your Terraform configuration (*.tf files). You need to enable debug messages to find this out.<br>
Which of the following would achieve this?<br>

**A**. Set the environment variable TF_LOG=TRACE<br>
B. Set verbose logging for each provider in your Terraform configuration<br>
C. Set the environment variable TF_VAR_log=TRACE<br>
D. Set the environment variable TF_LOG_PATH<br>
 
<br>**#74**<br>
How is terraform import run?<br>

A. As a part of terraform init<br>
B. As a part of terraform plan<br>
C. As a part of terraform refresh<br>
**D**. By an explicit call<br>
E. All of the above<br>
 
<br>**#75**<br>
You have a simple Terraform configuration containing one virtual machine (VM) in a cloud provider. You run terraform apply and the VM is created successfully.
What will happen if you delete the VM using the cloud provider console, and run terraform apply again without changing any Terraform code?<br>

A. Terraform will remove the VM from state file<br>
B. Terraform will report an error<br>
C. Terraform will not make any changes<br>
**D**. Terraform will recreate the VM<br>


<br>**#76**<br>
Which of these options is the most secure place to store secrets for connecting to a Terraform remote backend?<br>

A. Defined in Environment variables<br>
B. Inside the backend block within the Terraform configuration<br>
**C**. Defined in a connection configuration outside of Terraform<br>
D. None of above<br>

The most secure place to store secrets for connecting to a Terraform remote backend is:<br>

**A. Defined in Environment variables**<br>

Storing secrets in environment variables is generally considered more secure because it avoids hardcoding sensitive information directly in your Terraform configuration files, which could be exposed in version control systems or shared between team members.<br>

Here's why other options are less secure:<br>

B. **Inside the backend block within the Terraform configuration**: Storing secrets directly in the backend block exposes them in plain text within the configuration, which is less secure, especially if the files are committed to version control.<br>
C. **Defined in a connection configuration outside of Terraform**: This depends on the security of that external configuration, but it can introduce complexity and risks if not handled carefully. Proper secret management systems should be used for external configurations.<br>
D. **None of the above**: This option isn't correct since environment variables are a valid and secure method when used properly.<br>

<br>**#77**<br>
Your DevOps team is currently using the local backend for your Terraform configuration. You would like to move to a remote backend to begin storing the state file in a central location.<br>
Which of the following backends would not work?<br>

A. Amazon S3<br>
B. Artifactory<br>
**C**. Git<br>
D. Terraform Cloud<br>
 
<br>**#78**<br>
Which backend does the Terraform CLI use by default?<br>

A. Terraform Cloud<br>
B. Consul<br>
C. Remote<br>
**D**. Local<br>
 
<br>**#79**<br>
When you initialize Terraform, where does it cache modules from the public Terraform Module Registry?<br>

A. On disk in the /tmp directory<br>
B. In memory<br>
**C**. On disk in the .terraform sub-directory<br>
D. They are not cached<br>
 
<br>**#80**<br>
You write a new Terraform configuration and immediately run terraform apply in the CLI using the local backend.<br>
Why will the apply fail?<br>

A. Terraform needs you to format your code according to best practices first<br>
**B**. Terraform needs to install the necessary plugins first<br>
C. The Terraform CLI needs you to log into Terraform cloud first<br>
D. Terraform requires you to manually run terraform plan first<br>
 
<br>**#81**<br>
What features stops multiple admins from changing the Terraform state at the same time?<br>

A. Version control<br>
B. Backend types<br>
C. Provider constraints<br>
**D**. State locking<br>
 
<br>**#82**<br>
A fellow developer on your team is asking for some help in refactoring their Terraform code. As part of their application's architecture, they are going to tear down an existing deployment managed by Terraform and deploy new. However, there is a server resource named aws_instance.ubuntu[1] they would like to keep to perform some additional analysis.<br>
What command should be used to tell Terraform to no longer manage the resource?<br>

A. terraform apply rm aws_instance.ubuntu[1]<br>
**B**. terraform state rm aws_instance.ubuntu[1]<br>
C. terraform plan rm aws_instance.ubuntu[1]<br>
D. terraform delete aws_instance.ubuntu[1]<br>
 
<br>**#83**<br>
Terraform can only manage resource dependencies if you set them explicitly with the depends_on argument.<br>

A. True<br>
**B**. False<br>
 
<br>**#84**<br>
A terraform apply can not _________ infrastructure.<br>

A. change<br>
B. destroy<br>
A. Sources all providers present in the configuration and ensures they are downloaded and available locally<br>
B. Connects to the backend<br>
C. Sources any modules and copies the configuration locally<br>
**D**. Validates all required variables are present<br>
 
**D. Validates all required variables are present**<br>
dates. This ensures that the provider version is at least 2.1, but it also allows for automatic updates as long as the version remains within the 2.x range (e.g., 2.1, 2.2, etc.).<br>

Here’s a breakdown of why this is the correct answer:<br>

A. **version >= 2.1**: This is not valid syntax. While the intent is correct, Terraform uses ~> for version constraints rather than >=.<br>
C. **version = ג€<= 2.1ג€ and D. version = ג€>= 2.1ג€**: Both are invalid because of incorrect formatting and the use of non-standard characters.
The correct way to specify a version constraint for the GitHub provider in Terraform would look like this:<br>

**hcl**<br>
```
provider "github" {
  version = "~> 2.1"
}
```

<br>**#86**<br>
You just scaled your VM infrastructure and realized you set the count variable to the wrong value. You correct the value and save your change.<br>
What do you do next to make your infrastructure match your configuration?<br>

**A**. Run an apply and confirm the planned changes<br>
B. Inspect your Terraform state because you want to change it<br>
C. Reinitialize because your configuration has changed<br>
D. Inspect all Terraform outputs to make sure they are correct<br>
 
<br>**#87**<br>
Terraform provisioners that require authentication can use the ______ block.<br>

**A**. connection<br>
B. credentials<br>
C. secrets<br>
D. ssh<br>

**A. connection**

Terraform provisioners that require authentication, such as when using SSH or WinRM to connect to remote machines, use the connection block. The connection block allows you to specify authentication details like username, password, private keys, or other required information.

Example of a connection block for SSH:

hcl
```
resource "null_resource" "example" {
  provisioner "remote-exec" {
    connection {
      type     = "ssh"
      user     = "ubuntu"
      private_key = file("~/.ssh/id_rsa")
      host     = self.public_ip
    }

    script = "some_script.sh"
  }
}
```
This block provides the necessary authentication to connect to the remote resource.

br>**#88**<br>
Terraform validate reports syntax check errors from which of the following scenarios?<br>

A. Code contains tabs indentation instead of spaces<br>
B. There is missing value for a variable<br>
C. The state files does not match the current infrastructure<br>
**D**. None of the above<br>

**D. None of the above**<br>

terraform validate checks for syntax errors and verifies that the configuration is syntactically correct and internally consistent, but it does not cover the scenarios listed in the options:<br>

A. **Code contains tabs indentation instead of spaces**: Terraform is generally agnostic to whether you use tabs or spaces for indentation.<br>
B. **There is missing value for a variable**: terraform validate will not catch this error; it will only be caught during terraform plan or terraform apply if the variable is not provided.<br>
C. **The state file does not match the current infrastructure**: terraform validate only checks configuration files, not the state of the infrastructure. Any discrepancies between the state and the infrastructure are detected during terraform plan or terraform apply.<br>
Therefore, none of these scenarios would trigger an error in terraform validate.<br>

<br>**#89**<br>
Which of the following is allowed as a Terraform variable name?<br>

A. count<br>
**B**. name<br>
C. source<br>
D. version<br>
 
<br>**#90**<br>
What type of block is used to construct a collection of nested configuration blocks?<br>

A. for_each<br>
B. repeated<br>
C. nesting<br>
**D**. dynamic<br>

**D. dynamic**<br>

The dynamic block is used to construct a collection of nested configuration blocks in Terraform. It allows you to generate multiple nested blocks based on the results of an expression, such as a list or map, and is commonly used when the exact number of nested blocks needed is not known ahead of time.<br>

Example of a dynamic block:<br>

**hcl**<br>
```
resource "aws_security_group" "example" {
  dynamic "ingress" {
    for_each = var.ingress_rules
    content {
      from_port   = ingress.value.from_port
      to_port     = ingress.value.to_port
      protocol    = ingress.value.protocol
      cidr_blocks = ingress.value.cidr_blocks
    }
  }
}
```
In this example, the dynamic block creates multiple ingress blocks based on the ingress_rules variable.<br>

<br>**#91**<br>
Module variable assignments are inherited from the parent module and do not need to be explicitly set.<br>

A. True<br>
**B**. False<br>

**B. False**

Module variable assignments in Terraform are not inherited from the parent module. You must explicitly set variables for each module when you call it. The parent module's variables do not automatically pass down to child modules unless you explicitly assign them.<br>

When defining a module, you need to pass the required variables from the parent module like this:<br>

**hcl**<br>
```
module "example" {
  source = "./module_path"
  
  variable_name = var.parent_variable_name
}
```
This ensures that the module gets the correct values, and they won't be inherited automatically.<br>

<br>**#92**<br>
If writing Terraform code that adheres to the Terraform style conventions, how would you properly indent each nesting level compared to the one above it?<br>

A. With four spaces<br>
B. With a tab<br>
C. With three spaces<br>
**D**. With two spaces<br>
 
<br>**#93**<br>
Which of the following is not an action performed by terraform init?<br>

**A**. Create a sample main.tf file<br>
B. Initialize a configured backend<br>
C. Retrieve the source code for all referenced modules<br>
D. Load required provider plugins<br>
 
<br>**#94**<br>
HashiCorp Configuration Language (HCL) supports user-defined functions.<br>

A. True<br>
**B**. False<br>
 
<br>**#95**<br>
How can you trigger a run in a Terraform Cloud workspace that is connected to a Version Control System (VCS) repository?<br>

A. Only Terraform Cloud organization owners can set workspace variables on VCS connected workspaces<br>
**B**. Commit a change to the VCS work
A. Sources all providers present in the configuration and ensures they are downloaded and available locally<br>
B. Connects to the backend<br>
C. Sources any modules and copies the configuration locally<br>
**D**. Validates all required variables are present<br>
 
**D. Validates all required variables are present**<br>


**C. When a change is made to the resources via the Azure Cloud Console, the current state file will not be updated**<br>

Explanation:<br>

B is correct because when Terraform runs the next plan or apply operation, it will detect changes made outside of Terraform (e.g., in the Azure Cloud Console) and will update the state file accordingly to reflect the actual infrastructure.<br>

C is correct because Terraform's state file is only updated when Terraform runs a command (such as plan or apply). Changes made directly in Azure without running Terraform will not automatically update the state file.<br>

The other options are incorrect:<br>

A is false because changes made directly in the Azure Cloud Console are not automatically recorded in the Terraform state file until Terraform is run again.<br>
D is false for the same reason, as changes are not immediately reflected in the current state file when made outside of Terraform.<br>

<br>**#99**<br>
You need to deploy resources into two different cloud regions in the same Terraform configuration. To do that, you declare multiple provider configurations as follows:<br>

>provider "aws" {<br>
>   region = "us-west"<br>
>}<br>
>
>provider "aws" {<br>
>   alias = "west"<br>
>   region = "us-west-2"<br>
>}

What meta-argument do you need to configure in a resource block to deploy the resource to the `us-west-2` AWS region?<br>

A. alias = west<br>
B. provider = west<br>
**C**. provider = aws.west<br>
D. alias = aws.west<br>

**C. provider = aws.west**<br>

In Terraform, when you define multiple provider configurations (with different regions in this case), you need to specify which provider configuration to use in a resource block by referencing the provider's alias. The correct way to reference the provider with an alias is using the provider meta-argument in the form of provider = aws.alias.<br>

Example of how it should be configured in a resource block:<br>

**hcl**<br>
```
resource "aws_instance" "example" {
  ami           = "ami-123456"
  instance_type = "t2.micro"

  provider = aws.west  # This specifies the provider configuration with alias "west"
}
```
This ensures that the resource is deployed in the us-west-2 region, as defined by the aws provider with the alias west.<br>

<br>**#100**<br>
You have declared an input variable called environment in your parent module. What must you do to pass the value to a child module in the configuration?<br>

**A**. Add node_count = var.node_count<br>
B. Declare the variable in a terraform.tfvars file<br>
C. Declare a node_count input variable for child module<br>
D. Nothing, child modules inherit variables of parent module<br>

**A. Add node_count = var.node_count**<br>

To pass the value of an input variable from the parent module to a child module, you need to explicitly assign it in the module block where you call the child module. Terraform does not automatically inherit variables from the parent module into the child module.<br>

For example, if your parent module has a variable called environment, and you want to pass it to the child module, you would do something like this:<br>

**hcl**<br>
```
module "child_module" {
  source = "./child_module"
  
  environment = var.environment
}
```
In this case, you are passing the environment variable from the parent module to the child module by referencing var.environment.<br>

Here's why other options are incorrect:<br>

B. **Declare the variable in a terraform.tfvars file**: While this can be used to set values for variables, it does not automatically pass the variable to child modules.<br>
C. **Declare a node_count input variable for child module**: This is necessary, but it's not enough by itself. You must still pass the value from the parent module when calling the child module.<br>
D. **Nothing, child modules inherit variables of parent module**: This is false. Variables are not inherited automatically; they must be explicitly passed.<br>

<br>**#101**<br>
If a module declares a variable with a default, that variable must also be defined within the module.<br>

A. True<br>
**B**. False<br>
 
<br>**#102**<br>
Which option cannot be used to keep secrets out of Terraform configuration files?<br>

A. Environment Variables<br>
B. Mark the variable as sensitive<br>
**C**. A Terraform provider<br>
D. A -var flag<br>

**C. A Terraform provider**<br>

A Terraform provider cannot be used to keep secrets out of Terraform configuration files. Providers are used to interact with specific APIs and services, but they do not have a mechanism for managing or protecting sensitive data directly. Instead, secrets should be managed using other methods such as environment variables, flags, or marking variables as sensitive.<br>

Here's why the other options can be used to keep secrets out of configuration files:<br>

A. **Environment Variables**: Secrets can be stored in environment variables and referenced in the Terraform configuration, keeping them out of the code.<br>
B. **Mark the variable as sensitive**: Marking a variable as sensitive in Terraform helps prevent it from being displayed in logs or output.<br>
D. **A -var flag**: You can pass sensitive values to Terraform via the -var flag when running commands like terraform apply, keeping them out of the configuration files.<br>

<br>**#103**<br>
Which of the following arguments are required when declaring a Terraform output?<br>

A. sensitive<br>
B. description<br>
C. default<br>
**D**. value<br>
 
<br>**#104**<br>
Your risk management organization requires that new AWS S3 buckets must be private and encrypted at rest. How can Terraform Enterprise automatically and proactively enforce this security control?<br>

**A**. With a Sentinel policy, which runs before every apply<br>
B. By adding variables to each TFE workspace to ensure these settings are always enabled<br>
C. With an S3 module with proper settings for buckets<br>
D. Auditing cloud storage buckets with a vulnerability scanning tool<br>
 
<br>**#105**<br>
Most Terraform providers interact with ____________.<br>

**A**. API<br>
B. VCS Systems<br>
C. Shell scripts<br>
D. None of the above<br>


<br>**#106**<br>
terraform validate validates that your infrastructure matches the Terraform state file.<br>

A. True<br>
**B**. False<br>
 
<br>**#107**<br>
What does terraform import allow you to do?<br>

A. Import a new Terraform module<br>
B. Use a state file to import infrastructure to the cloud<br>
**C**. Import provisioned infrastructure to your state file<br>
D. Import an existing state file to a new Terraform workspace<br>
 
<br>**#108**<br>
FILL BLANK -<br>
In the below configuration, how would you reference the module output vpc_id?<br>

```
module "vpc" {
   source = "terraform-and-modules/vpc/aws"
   cidr = "10.0.0.0/16"
   name = "test-vpc"
}
```

Type your answer in the field provided. The text field is not case sensitive and all variations of the correct answer are accepted.<br>

**module.vpc.vpc_id**<br>

In Terraform, you reference a module's outputs by using the module.<module_name>.<output_name> syntax. In this case, vpc is the module name and vpc_id is the output.<br>


<br>**#109**<br>
How would you reference the Volume IDs associated with the ebs_block_device blocks in this configuration?<br>

```
resource "aws_instance" "example" {
   ami = "ami-abc123
   instance_type = "t2.micro"

ebs_block_device {
   device_name = "sda2"
}

ebs_block_device {
   device_NAME = "sda3"
   volume_size = 20
   }
}
```

A. aws_instance.example.ebs_block_device.[*].volume_id<br>
**B**. aws_instance.example.ebs_block_device.volume_id<br>
C. aws_instance.example.ebs_block_device[sda2,sda3].volume_id<br>
D. aws_instance.example.ebs_block_device.*.volume_id<br>

**B. aws_instance.example.ebs_block_device.volume_id**<br>

In Terraform, you can reference the volume IDs associated with ebs_block_device blocks by using the correct path to the resource's attributes. Since ebs_block_device is nested within the aws_instance resource, the proper way to reference the volume_id is through the aws_instance.example.ebs_block_device.volume_id.<br>

Options like [].volume_id or using indexes would not apply directly in this case unless you're explicitly indexing a list of ebs_block_device blocks.<br>

<br>**#110**<br>
What does state locking accomplish?<br>

A. Copies the state file from memory to disk<br>
B. Encrypts any credentials stored within the state file<br>
**C**. Blocks Terraform commands from modifying the state file<br>
D. Prevents accidental deletion of the state file<br>
 
<br>**#111**<br>
You just upgraded the version of a provider in an existing Terraform project. What do you need to do to install the new provider?<br>

A. Run terraform apply -upgrade<br>
**B**. Run terraform init -upgrade<br>
C. Run terraform refresh<br>
D. Upgrade your version of Terraform<br>
 
<br>**#112**<br>
A module can always refer to all variables declared in its parent module.<br>

A. True<br>
**B**. False<br>

**B. False**<br>

A module cannot automatically refer to all variables declared in its parent module. Variables must be explicitly passed from the parent module to the child module. Each module has its own variable scope, and values from the parent module need to be provided to the child module through the module block using var.<variable_name>. There is no automatic inheritance of variables between modules.<br>

<br>**#113**<br>
When you use a remote backend that needs authentication, HashiCorp recommends that you:<br>

**A**. Use partial configuration to load the authentication credentials outside of the Terraform code<br>
B. Push your Terraform configuration to an encrypted git repository<br>
C. Write the authentication credentials in the Terraform configuration files<br>
D. Keep the Terraform configuration files in a secret store<br>
 
<br>**#114**<br>
You have a simple Terraform configuration containing one virtual machine (VM) in a cloud provider. You run terraform apply and the VM is created successfully.
What will happen if you terraform apply again immediately afterwards without changing any Terraform code?

A. Terraform will terminate and recreate the VM<br>
B. Terraform will create another duplicate VM<br>
C. Terraform will apply the VM to the state file<br>
**D**. Nothing<br>
 
<br>**#115**<br>
A junior admin accidentally deleted some of your cloud instances. What does Terraform do when you run terraform apply?<br>

A. Build a completely brand new set of infrastructure<br>
B. Tear down the entire workspace infrastructure and rebuild it<br>
**C**. Rebuild only the instances that were deleted<br>
D. Stop and generate an error message about the missing instances<br>
 
<br>**#116**<br>
You have created a main.tf Terraform configuration consisting of an application server, a database, and a load balancer. You ran terraform apply and all resources were created successfully. Now you realize that you do not actually need the load balancer so you run terraform destroy without any flags What will happen?<br>

A. Terraform will destroy the application server because it is listed first in the code<br>
**B**. Terraform will prompt you to confirm that you want to destroy all the infrastructure<br>
C. Terraform will destroy the main.tf file<br>
D. Terraform will prompt you to pick which resource you want to destroy<br>
E. Terraform will immediately destroy all the infrastructure<br>
 
<br>**#117**<br>
Which type of block fetches or computes information for use elsewhere in a Terraform configuration?<br>

A. provider<br>
B. resource<br>
C. local<br>
**D**. data<br>
 
<br>**#118**<br>
You have just developed a new Terraform configuration for two virtual machines with a cloud provider. You would like to create the infrastructure for the first time.<br>
Which Terraform command should you run first?<br>

A. terraform apply<br>
B. terraform plan<br>
C. terraform show<br>
**D**. terraform init<br>
 
<br>**#119**<br>
All modules published on the official Terraform Module Registry have been verified by HashiCorp.<br>

A. True<br>
**B**. False<br>
 
<br>**#120**<br>
You have to initialize a Terraform backend before it can be configured.<br>

A. True<br>
**B**. False<br>

**B. False**<br>

You do not need to initialize a Terraform backend before configuring it. Instead, you configure the backend in your Terraform configuration file, and then when you run terraform init, Terraform will initialize the backend based on that configuration. The initialization happens after you define the backend in the configuration, not before.<br>

**hcl**<br>
```
terraform {
  backend "s3" {
    bucket = "my-terraform-state"
    key    = "path/to/my/key"
    region = "us-west-2"
  }
}
```
After defining the backend in your configuration, running terraform init will set up and initialize the backend.<br>

<br>**#121**<br>
Which of the following does terraform apply change after you approve the execution plan? (Choose two.)<br>

**A**. Cloud infrastructure<br>
B. The .terraform directory<br>
C. The execution plan<br>
**D**. State file<br>
E. Terraform code<br>

**A. Cloud infrastructure**
**D. State file**

When you run terraform apply and approve the execution plan, Terraform makes changes to the cloud infrastructure based on the plan, and it also updates the state file to reflect the current state of the infrastructure after those changes.<br>

**A. Cloud infrastructure***: Terraform applies the changes to the actual infrastructure, creating, modifying, or destroying resources as specified in the plan.<br>
**D. State file**: The state file is updated to reflect the current status of the resources after the changes are applied.<br>
The other options are incorrect:<br>

B. **The .terraform directory**: This directory contains plugins and modules but is not directly changed by terraform apply.<br>
C. **The execution plan**: The plan is a temporary artifact used to apply changes and does not change after execution.<br>
E. **Terraform code**: Terraform code does not change during terraform apply. The code is only executed as is.<br>

<br>**#122**<br>
A Terraform backend determines how Terraform loads state and stores updates when you execute ___________.<br>

A. apply<br>
B. taint<br>
C. destroy<br>
**D**. All of the above<br>
E. None of the above<br>
 
<br>**#123**<br>
What does Terraform use .terraform.lock.hcl file for?<br>

**A**. Tracking provider dependencies<br>
B. There is no such file<br>
C. Preventing Terraform runs from occurring<br>
D. Storing references to workspaces which are locked<br>

**A. Tracking provider dependencies**<br>

The .terraform.lock.hcl file is used by Terraform to track provider dependencies and their versions. This file ensures that the exact versions of providers used in your Terraform configuration are locked, so that future runs of Terraform will use the same versions, even if newer versions of those providers are available. This helps maintain consistency across different environments and prevents unexpected changes caused by provider updates.<br>

For example, when you run terraform init, this file is created or updated to lock the provider versions specified in your configuration.<br>

<br>**#124**<br>
You've used Terraform to deploy a virtual machine and a database. You want to replace this virtual machine instance with an identical one without affecting the database. What is the best way to achieve this using Terraform?<br>

A. Use the terraform state rm command to remove the VM from state file<br>
**B**. Use the terraform taint command targeting the VMs then run terraform plan and terraform apply<br>
C. Use the terraform apply command targeting the VM resources only<br>
D. Delete the Terraform VM resources from your Terraform code then run terraform plan and terraform apply<br>
 
<br>**#125**<br>
How do you specify a module's version when publishing it to the public Terraform Module Registry?<br>

A. The module's configuration page on the Terraform Module Registry<br>
B. Terraform Module Registry does not support versioning modules<br>
**C**. The release tags in the associated repo<br>
D. The module's Terraform code<br>
 
<br>**#126**<br>
Terraform plan updates your state file.<br>

A. True<br>
**B**. False<br>
 
<br>**#127**<br>
To check if all code in a Terraform configuration with multiple modules is properly formatted without making changes, what command should be run?<br>

**A**. terraform fmt -check<br>
B. terraform fmt -write-false<br>
C. terraform fmt ג€"list -recursive<br>
D. terraform fmt -check -recursive<br>

**A. terraform fmt -check**

The terraform fmt -check command checks if all the code in the Terraform configuration is properly formatted without making any changes. It reports whether the formatting is correct but doesn't automatically reformat the code.<br>

For configurations with multiple modules, you can also add the -recursive flag to apply the check across all subdirectories:<br>

**bash**
```
terraform fmt -check -recursive
This will check formatting in all the modules and subdirectories within your configuration.
```
<br>**#128**<br>
As a member of the operations team, you need to run a script on a virtual machine created by Terraform. Which provision is best to use in your Terraform code?<br>

A. null-ex׀µׁ<br>
B. local-exec<br>
**C**. remote-exec<br>
D. file<br>
 
<br>**#129**<br>
You are using a networking module in your Terraform configuration with the name label my_network. In your main configuration you have the following code:<br>
```
output: "net_id" {
	value = module.my_network.vnet_id
}
```
When you run terraform validate, you get the following error:<br>

```
Error: Reference to undeclared output value

   on main.tf line 12, in output "net_id":
   12:   value = module.my_network.vnet_id
```

What must you do to successfully retrieve this value from your networking module?<br>

A. Define the attribute vnet_id as a variable in the networking module<br>
B. Change the referenced value to module.my_network.outputs.vnet_id<br>
**C**. Define the attribute vnet_id as an output in the networking module<br>
D. Change the referenced value to my_network.outputs.vnet_id<br>
 
<br>**#130**<br>
You are writing a child Terraform module which provisions an AWS instance. You want to make use of the IP address returned in the root configuration. You name the instance resource "main".<br>
Which of these is the correct way to define the output value using HCL2?<br>

**A**.
```
output "instance_ip_addr" {
	value = "${aws_instance.main.private_ip}"
}
```
B.
```
output "instance_ip_addr" {
	return aws_instance.main.private_ip
}
```
<br>

---

---
<br>

<br>**#131**<br>
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
<br>

---

---
<br>
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

---

<br>**#196**<br>
In a Terraform Cloud workspace linked to a version control repository, speculative plan runs start automatically when you merge or commit changes to version control.

A. True
B. False
 
<br>**#197**<br>
You have some Terraform code and a variable definitions file named dev.auto.tfvars that you tested successfully in the dev environment. You want to deploy the same code in the staging environment with a separate variable definition file and a separate state file.<br>

Which two actions should you perform? (Choose two.)<br>

A. Copy the existing terraform.tfstate file and save it as staging.terraform.tfstate<br>
B. Write a new staging.auto.tfvars variable definition file and run Terraform with the var-file=”staging.auto.tfvars” flag<br>
C. Create a new Terraform workspace for staging<br>
D. Create a new Terraform provider for staging<br>
E. Add new Terraform code (*.tf files) for staging in the same directory<br>
 
<br>**#198**<br>
The ________ determines how Terraform creates, updates, or deletes resources.<br>

A. Terraform configuration<br>
B. Terraform core<br>
C. Terraform provider<br>
D. Terraform provisioner<br>
 
<br>**#199**<br>
Terraform destroy is the only way to remove infrastructure.<br>

A. True<br>
B. False<br>
 
<br>**#200**<br>
Which of the following is the correct way to pass the value in the variable num_servers into a module with the input servers in HCL2?<br>

A. servers - var.num_servers<br>
B. servers - num_servers<br>
C. servers - var(num_servers)<br>
D. $(var.num_servers)<br>
 
<br>**#201**<br>
Which of the fallowing commands would you use to access all of the attributes and details of a resource managed by Terraform?<br>

A. terraform state list<br>
B. terraform state show<br>
C. terraform get<br>
D. terraform state list<br>
 
<br>**#202**<br>
How would you be able to reference an attribute from the vsphere_datacenter data source for use with the datacenter_id argument within the vsphere_folder resource in the following configuration?<br>



A. data.dc.id<br>
B. data.vsphere_datacenter.dc<br>
C. vsphere_datacenter.dc.id<br>
D. data.vsphere_datacenter.dc.id<br>
 
<br>**#203**<br>
You decide to move a Terraform state file to Amazon S3 from another location. You write the code below into a file called backend.tf.<br>



Which command will migrate your current state file to the new S3 remote backend?<br>

A. terraform state<br>
B. terraform init<br>
C. terraform refresh<br>
D. terraform push<br>
 
<br>**#204**<br>
You want to tag multiple resources with a string that is a combination of a generated random_id and a variable.<br>

How should you use the same value in all these resources without repeating the random_id and variable in each resource?<br>

A. Local values<br>
B. Data source<br>
C. Modules<br>
D. Outputs<br>
 
<br>**#205**<br>
Which of the following is not a benefit of adopting infrastructure as code?<br>

A. Interpolation<br>
B. Reusability of code<br>
C. Versioning<br>
D. Automation<br>
 
<br>**#206**<br>
Module version is required to reference a module on the Terraform Module Registry.<br>

A. True<br>
B. False<br>
 
<br>**#207**<br>
While deploying a virtual machine, the first launch user_data script fails due to race condition with another resource deployed during the same Terraform run.<br>

What is the least disruptive method to correct the issue?<br>

A. Run terraform taint against the virtual machine’s resource name, then terraform apply<br>
B. Restart the virtual machine from the cloud portal<br>
C. Run terraform apply again<br>
D. Run terraform destroy then terraform apply<br>
 
<br>**#208**<br>
The public Module Registry is free to use.<br>

A. True<br>
B. False<br>
 
<br>**#209**<br>
Both Terraform Cloud and Terraform Enterprise support policy as code (Sentinel).<br>

A. True<br>
B. False<br>

<br>**#210**<br>
You want to define multiple data disks as nested blocks inside the resource block for a virtual machine.<br>

What Terraform feature would help you define the blocks using the values in a variable?<br>

A. Local values<br>
B. Collection functions<br>
C. Dynamic blocks<br>
D. Count arguments<br>


<br>**#211**<br>
Which of the following module source paths does not specify a remote module?<br>

A. source = “./modules/consul”<br>
B. source = “git@github.com:hashicorp/example.git”<br>
C. source = “github.com/hashicorp/example”<br>
D. source = “hashicorp/consul/aws”<br>
 
<br>**#212**<br><br>
You have a list of numbers that represents the number of free CPU cores on each virtual cluster:<br>

numcpus = [ 18, 3, 7, 11, 2 ]<br>

What Terraform function could you use to select the largest number from the list?<br>

A. max(numcpus)<br>
B. ceil(numcpus)<br>
C. top(numcpus)<br>
D. high[numcpus]<br>
 
<br>**#213**<br>
Variables declared within a module are accessible outside of the module.<br>

A. True<br>
B. False<br>
 
<br>**#214**<br>
Which of the following is not a valid Terraform variable type?<br>

A. list<br>
B. map<br>
C. array<br>
D. string<br>
 
<br>**#215**<br>
What is a key benefit of the Terraform state file?<br>

A. A state file can be used to schedule recurring infrastructure tasks<br>
B. A state file represents a source of truth for resources provisioned with a public cloud console<br>
C. A state file represents the desired state expressed by the Terraform code files<br>
D. A state file represents a source of truth for resources provisioned with Terraform<br>
 
<br>**#216**<br>
Which of these statements about Terraform Enterprise workspaces is false?<br>

A. They can securely store cloud credentials<br>
B. You must use the CLI to switch between workspaces<br>
C. Plans and applies can be triggered via version control system integrations<br>
D. They have role-based access controls<br>
 
<br>**#217**<br>
Define the purpose of state in Terraform.<br>

A. State is used to map real world resources to your configuration and keep track of metadata<br>
B. State is a method of codifying the dependencies of related resources<br>
C. State is used to enforce resource configurations that relate to compliance policies<br>
D. State is used to store variables and quickly reuse existing code<br>
 
<br>**#218**<br>
Which backend does the Terraform CLI use by default?<br>

A. API<br>
B. Remote<br>
C. Terraform Cloud<br>
D. Local<br>
E. HTTP<br>
 
<br>**#219**<br>
Using the terraform state rm command against a resource will destroy it.<br>

A. True<br>
B. False<br>
 
<br>**#220**<br>
Which method for sharing Terraform configurations keeps them confidential within your organization, supports Terraform’s semantic version constraints, and provides a browsable directory?<br>

A. Generic git repository<br>
B. Terraform Cloud/Terraform Enterprise private module registry<br>
C. Public Terraform Module Registry<br>
D. Subfolder within a workspace<br>
 
<br>**#221**<br>
You are writing a child Terraform module which provisions an AWS instance. You want to make use of the IP address returned in the root configuration. You name the instance resource “main”.<br>

Which of these is the correct way to define the output value using HCL2?<br>

A. 
B. 
C. 
D. 
 
<br>**#222**<br>
How would you refer to the indexing instance from the below configuration?<br>



A. aws_instance[“web”][“indexing”]<br>
B. aws_instance.web.indexing
C. aws_instance-web[“indexing”]<br>
D. aws_instance.web[“indexing”]<br>

<br>**#223**<br>
Which feature is not included in Terraform Cloud’s free tier?<br>

A. Workspace<br>
B. Remote state management<br>
C. Audit logging<br>
D. Private module registry<br>
 
<br>**#224**<br>
When should you run terraform init?<br>

A. After you run terraform apply for the first time in a new Terraform project and before you run terraform plan<br>
B. After you run terraform plan for the first time in a new Terraform project and before you run terraform apply<br>
C. After you start coding a new Terraform project and before you run terraform plan for the first time<br>
D. Before you start coding a new Terraform project<br>
 
<br>**#225**<br>
Terraform configuration (including any module references) can contain only one Terraform provider type.<br>

A. True<br>
B. Falsev<br>



<br>**#226**<br>
You are making changes to existing Terraform code to add some new infrastructure.<br>

When is the best time to run terraform validate?<br>

A. After you run terraform plan so you can validate that your state file is consistent with your infrastructure<br>
B. Before you run terraform plan so you can validate your code syntax<br>
C. Before you run terraform apply so you can validate your infrastructure changes<br>
D. After you run terraform apply so you can validate that your infrastructure is reflected in your code<br>
 
<br>**#227**<br>
How does Terraform manage most dependencies between resources?<br>

A. By defining dependencies as modules and including them in a particular order<br>
B. The order that resources appear in Terraform configuration indicates dependencies<br>
C. Using the depends_on parameter<br>
D. Terraform will automatically manage most resource dependencies<br>
 
<br>**#228**<br>
What does running a terraform plan do?<br>

A. Imports all of your existing cloud provider resources to the state file<br>
B. Compares the state file to your Terraform code and determines if any changes need to be made<br>
C. Imports all of your existing cloud provider resources to your Terraform configuration file<br>
D. Compares your Terraform code and local state file to the remote state file in a cloud provider and determines if any changes need to be made<br>
 
<br>**#229**<br>
What are some benefits of using Sentinel with Terraform Cloud/Terraform Enterprise? (Choose three.)<br>

A. Policy-as-code can enforce security best practices<br>
B. You can restrict specific configurations on resources like "CIDR=0.0.0.0/0" not allowed<br>
C. You can enforce a list of approved AWS AMIs<br>
D. Sentinel Policies can be written in HashiCorp Configuration Language (HCL)<br>
E. You can check out and check in cloud access keys<br>
 
<br>**#230**<br>
You want to share Terraform state with your team, store it securely, and provide state locking.<br>

How would you do this? (Choose three.)<br>

A. Using the remote Terraform backend with Terraform Cloud / Terraform Enterprise.<br>
B. Using the local backend.<br>
C. Using the s3 terraform backend. The dynamodb_field option is not needed.<br>
D. Using an s3 terraform backend with an appropriate IAM policy and dynamodb_field option configured.<br>
E. Using the consul Terraform backend.<br>
 
<br>**#231**<br>
From which of these sources can Terraform import modules?<br>

A. Local path<br>
B. GitHub Repository<br>
C. Terraform Module Registry<br>
D. All of the above<br>
 
<br>**#232**<br>
How would you output returned values from a child module?<br>

A. Declare the output in the root configuration<br>
B. Declare the output in the child module<br>
C. Declare the output in both the root and child module<br>
D. None of the above<br>
 
<br>**#233**<br>
You have decided to create a new Terraform workspace to deploy a development environment.<br>

What is different about this workspace?<br>

A. It has its own state file<br>
B. It pulls in a different terraform.tfvars file<br>
C. It uses a different branch of code<br>
D. It uses a different backend<br>
 
<br>**#234**<br>
Any user can publish modules to the public Terraform Module Registry.<br>

A. True<br>
B. False<br>
 
<br>**#235**<br>
Which of these commands makes your code more human readable?<br>

A. terraform validate<br>
B. terraform output<br>
C. terraform plan<br>
D. terraform fmt<br>

<br>**#236**<br>
Infrastructure as Code (IaC) can be stored in a version control system along with application code.<br>

A. True<br>
B. False<br>
 
<br>**#237**<br>
Select the command that doesn’t cause Terraform to refresh its state.<br>

A. terraform apply<br>
B. terraform destroy<br>
C. terraform plan<br>
D. terraform state list<br>
 
<br>**#238**<br>
Sentinel policy-as-code is available in Terraform Enterprise.<br>

A. True<br>
B. False<br>
 
<br>**#239**<br>
Before you can use Terraform’s remote backend, you must first execute terraform init.<br>

A. True<br>
B. False<br>
 
<br>**#240**<br>
Which two steps are required to provision new infrastructure in the Terraform workflow? (Choose two.)<br>

A. Plan<br>
B. Apply<br>
C. Import<br>
D. Init<br>
E. Validate<br>



<br>**#241**<br>
You are working on some new application features and you want to spin up a copy of your production deployment to perform some quick tests. In order to avoid having to configure a new state backend, what open source Terraform feature would allow you create multiple states but still be associated with your current code?<br>

A. Terraform data sources<br>
B. Terraform local values<br>
C. Terraform modules<br>
D. Terraform workspaces<br>
E. None of the above<br>
 
<br>**#242**<br>
Which provisioner invokes a process on the machine running Terraform?<br>

A. remote-exec<br>
B. file<br>
C. local-exec<br>
D. null-exec<br>
 
<br>**#243**<br>
____________ backends support state locking.<br>

A. Some<br>
B. No<br>
C. Only local<br>
D. All<br>
 
<br>**#244**<br>
Which of the following methods, used to provision resources into a public cloud, demonstrates the concept of infrastructure as code?<br>

A. curl commands manually run from a terminal<br>
B. A sequence of REST requests you pass to a public cloud API endpoint<br>
C. A script that contains a series of public cloud CLI commands<br>
D. A series of commands you enter into a public cloud console<br>
 
<br>**#245**<br>
Which of the following should you put into the required_providers block?<br>

A. version >= 3.1<br>
B. version = “>= 3.1”<br>
C. version ~> 3.1<br>
 
<br>**#246**<br>
When should you write Terraform configuration files for existing infrastructure that you want to start managing with Terraform?<br>

A. Before you run terraform import<br>
B. You can import infrastructure without corresponding Terraform code<br>
C. Terraform will generate the corresponding configuration files for you<br>
D. After you run terraform import<br>
 
<br>**#247**<br>
Which command should you run to check if all code in a Terraform configuration that references multiple modules is properly formatted without making changes?<br>

A. terraform fmt -write=false<br>
B. terraform fmt -list -recursive<br>
C. terraform fmt -check -recursive<br>
D. terraform fmt -check<br>
 
<br>**#248**<br>
What features stops multiple users from operating on the Terraform state at the same time?<br>

A. Provider constraints<br>
B. Remote backends<br>
C. State locking<br>
D. Version control<br>
 
<br>**#249**<br>
You are creating a reusable Terraform configuration and want to include a billing_dept tag so your Finance team can track team-specific spending on resources. Which of the following billing_dept variable declarations will allow you to do this?<br>

A. 
B. 
C. 
D. 
 
<br>**#250**<br>
Which of these are secure options for storing secrets for connecting to a Terraform remote backend? (Choose two.)<br>

A. Inside the backend block within the Terraform configuration<br>
B. Defined in Environment variables<br>
C. Defined in a connection configuration outside of Terraform<br>
D. A variable file<br>
 
<br>**#251**<br>
You want to define a single input variable to capture configuration values for a server. The values must represent memory as a number, and the server name as a string.<br>

Which variable type could you use for this input?<br>

A. List<br>
B. Object<br>
C. Map<br>
D. Terraform does not support complex input variables of different types<br>
 
<br>**#252**<br>
What does Terraform not reference when running a terraform apply -refresh-only?<br>

A. Credentials<br>
B. State file<br>
C. Terraform resource definitions in configuration files<br>
D. Cloud provider<br>
 
<br>**#253**<br>
Multiple team members are collaborating on infrastructure using Terraform and want to format their Terraform code following standard Terraform-style convention. How could they automatically ensure the code satisfies conventions?<br>

A. Run the terraform fmt command during the code linting phase of your CI/CD process<br>
B. Manually apply two spaces indentation and align equal sign "=" characters in every Terraform file (*.tf)<br>
C. Run the terraform validate command prior to executing terraform plan or terraform apply<br>
 
<br>**#254**<br>
When using a remote backend or Terraform Cloud integration, where does Terraform save resource state?<br>

A. On the disk<br>
B. In memory<br>
C. In an environment variable<br>
D. In the remote backend or Terraform Cloud<br>
 
<br>**#255**<br>
In Terraform HCL, an object type of object({ name=string, age=number }) would match this value:<br>

A. 
B. 
C. 
D. 

<br>

---

---

<br>

<br>**#256**<br>
You add a new resource to an existing Terraform configuration, but do not update the version constraint in the configuration. The existing and new resources use the same provider. The working directory contains a .terraform-lock.hcl file.<br>

How will Terraform choose which version of the provider to use?<br>

A. Terraform will use the latest version of the provider for the new resource and the version recorded in the lock file to manage existing resources<br>
B. Terraform will use the version recorded in your lock file
C. Terraform will check your state file to determine the provider version to use<br>
D. Terraform will use the latest version of the provider available at the time you provision your new resource<br>
 
<br>**#257**<br>
You must use different Terraform commands depending on the cloud provider you use.<br>

A. True<br>
B. False<br>
 
<br>**#258**<br>
Define the purpose of state in Terraform.<br>

A. State stores variables and lets you quickly reuse existing code<br>
B. State lets you enforce resource configurations that relate to compliance policies<br>
C. State codifies the dependencies of related resources<br>
D. State maps real world resources to your configuration and keeps track of metadata<br>
 
<br>**#259**<br>
Which of these actions will prevent two Terraform runs from changing the same state file at the same time?<br>

A. Refresh the state after running Terraform<br>
B. Delete the state before running Terraform<br>
C. Configure state locking for your state backend<br>
D. Run Terraform with parallelism set to 1<br>
 
<br>**#260**<br>
While attempting to deploy resources into your cloud provider using Terraform, you begin to see some odd behavior and experience slow responses. In order to troubleshoot you decide to turn on Terraform debugging. Which environment variables must be configured to make Terraform’s logging more verbose?<br>

A. TF_LOG_PATH<br>
B. TF_VAR_log_level<br>
C. TF_LOG<br>
D. TF_VAR_log_path<br>
 
<br>**#261**<br>
The Terraform binary version and provider versions must match each other in a single configuration.<br>

A. True<br>
B. False<br>
 
<br>**#262**<br>
The .terraform.lock.hcl file tracks module versions.<br>

A. True<br>
B. False<br>
 
<br>**#263**<br>
You can develop a custom provider to manage its resources using Terraform.<br>

A. True<br>
B. False<br>
 
<br>**#264**<br>
Which of these is not a benefit of remote state?<br>

A. Keeping unencrypted sensitive information off disk<br>
B. Easily share reusable code modules<br>
C. Working in a team<br>
D. Delegate output to other teams<br>
 
<br>**#265**<br>
When using multiple configurations of the same Terraform provider, what meta-argument must be included in any non-default provider configurations?<br>

A. depends_on<br>
B. alias<br>
C. id<br>
D. name<br>
 
<br>**#266**<br>
A developer accidentally launched a VM (virtual machine) outside of the Terraform workflow and ended up with two servers with the same name. They don’t know which VM Terraform manages but do have a list of all active VM IDs.<br>

Which of the following methods could you use to discover which instance Terraform manages?<br>

A. Run terraform taint/code on all the VMs to recreate them<br>
B. Update the code to include outputs for the ID of all VMs, then run terraform plan to view the outputs<br>
C. Run terraform state list to find the names of all VMs, then run terraform state show for each of them to find which VM ID Terraform manages<br>
D. Use terraform refresh/code to find out which IDs are already part of state<br>
 
<br>**#267**<br>
Which of the following is not considered a safe way to inject sensitive values into a Terraform Cloud workspace?<br>

A. Edit the state file directly just before running terraform apply<br>
B. Set the variable value on the command line with the -var flag<br>
C. Write the value to a file and specify the file with the -var-file flag<br>
 
<br>**#268**<br>
If you update the version constraint in your Terraform configuration, Terraform will update your lock file the next time you run terraform init.<br>

A. True<br>
B. False<br>
 
<br>**#269**<br>
You must initialize your working directory before running terraform validate.<br>

A. True<br>
B. False<br>

<br>**#270**<br>
If you manually destroy infrastructure, what is the best practice reflecting this change in Terraform?<br>

A. Manually update the state fire<br>
B. Remove the resource definition from your file and run terraform apply -refresh-only<br>
C. Run terraform import<br>
D. It will happen automatically<br>


<br>**#271**<br>
You created infrastructure outside of the Terraform workflow that you now want to manage using Terraform. Which command brings the infrastructure into Terraform state?<br>

A. terraform init<br>
B. terraform get<br>
C. terraform refresh<br>
D. terraform import<br>
 
<br>**#272**<br>
When using Terraform to deploy resources into Azure, which scenarios are true regarding state files? (Choose two.)<br>

A. When you change a Terraform-managed resource via the Azure Cloud Console, Terraform updates the state file to reflect the change during the next plan or apply<br>
B. Changing resources via the Azure Cloud Console records the change in the current state file<br>
C. When you change a resource via the Azure Cloud Console, Terraform records the changes in a new state file<br>
D. Changing resources via the Azure Cloud Console does not update current state file<br>
 
<br>**#273**<br>
Which statement describes a goal of infrastructure as code?<br>

A. A pipeline process to test and deliver software<br>
B. Defining a vendor-agnostic API<br>
C. Write once, run anywhere<br>
D. The programmatic configuration of resources<br>
 
<br>**#274**<br>
terraform validate confirms the syntax of Terraform files.<br>

A. True<br>
B. False<br>
 
<br>**#275**<br>
Which command adds existing resources into Terraform state?<br>

A. terraform init<br>
B. terraform plan<br>
C. terraform refresh<br>
D. terraform import<br>
E. All of these<br>
 
<br>**#276**<br>
It is best practice to store secret data in the same version control repository as your Terraform configuration.<br>

A. True<br>
B. False<br>
 
<br>**#277**<br>
Which of the following commands would you use to access all of the attributes and details of a resource managed by Terraform?<br>

A. terraform state list ‘provider_type.name’<br>
B. terraform state show ‘provider_type.name’<br>
C. terraform get ‘provider_type.name’<br>
D. terraform state list<br>
 
<br>**#278**<br>
terraform validate confirms that your infrastructure matches the Terraform state file.<br>

A. True<br>
B. False<br>
 
<br>**#279**<br>
A senior admin accidentally deleted some of your cloud instances. What does Terraform do when you run terraform apply?<br>

A. Build a completely brand new set of infrastructure<br>
B. Tear down the entire workspace infrastructure and rebuild it<br>
C. Rebuild only the instances that were deleted<br>
D. Stop and generate an error message about the missing instances<br>
 
<br>**#280**<br>
terraform init creates an example main.tf file in the current directory.<br>

A. True<br>
B. False<br>
 
<br>**#281**<br>
Which argument helps prevent unexpected updates when calling Terraform Registry modules?<br>

A. count<br>
B. source<br>
C. version<br>
D. lifecycle<br>
 
<br>**#282**<br>
Setting the TF_LOG environment variable to DEBUG causes debug messages to be logged into stdout.<br>

A. True<br>
B. False<br>
 
<br>**#283**<br>
How would you output returned values from a child module in the Terraform CLI output?<br>

A. Declare the output in the root configuration<br>
B. Declare the output in the child module<br>
C. Declare the output in both the root and child module<br>
D. None of the above<br>
 
<br>**#284**<br>
What is the Terraform resource name of the following resource block?<br>


A. azurerm_resource_group<br>
B. azurerm<br>
C. test<br>
D. dev<br>
 
<br>**#285**<br>
When do you need to explicitly execute terraform refresh-only?<br>

A. Before every terraform plan<br>
B. Before every terraform apply<br>
C. Before every terraform import<br>
D. None of the above<br>


<br>**#286**<br>
How is the Terraform cloud integration differ from other state backends such as S3, Consul, etc.?<br>

A. It can execute Terraform runs on dedicated infrastructure in Terraform Cloud<br>
B. It doesn't show the output of a terraform apply locally<br>
C. It is only available to paying customers<br>
D. All of the above<br>
 
<br>**#287**<br>
Which of the following are advantages of using infrastructure as code (IaC) instead of provisioning with a graphical user interface (GUI)? (Choose two.)<br>

A. Secures your credentials<br>
B. Lets your version, reuse, and share infrastructure configuration<br>
C. Provisions the same resources at a lower cost<br>
D. Reduces risk of operator error<br>
E. Prevents manual modifications to your resources<br>
 
<br>**#288**<br>
One cloud configuration always maps to a single remote workspace.<br>

A. True<br>
B. False<br>
 
<br>**#289**<br>
Multiple team members are collaborating on infrastructure using Terraform and want to format their Terraform code following standard Terraform-style convention.<br>

How could they automatically ensure the code satisfies conventions?<br>

A. Replace all tabs with spaces<br>
B. Terraform automatically formats configuration on terraform apply<br>
C. Run terraform validate prior to executing terraform plan or terraform apply<br>
D. Use terraform fmt<br>
 
<br>**#290**<br>
Which backend does the Terraform CLI use by default?<br>

A. Depends on the cloud provider configured<br>
B. Remote<br>
C. Terraform Cloud<br>
D. Local<br>
E. HTTP<br>
 
<br>**#291**<br>
The Terraform CLI will print output values from a child module after running terraform apply.<br>

A. True<br>
B. False<br>
 
<br>**#292**<br>
What does terraform refresh-only modify?<br>

A. Your cloud infrastructure<br>
B. Your Terraform plan<br>
C. Your Terraform configuration<br>
D. Your state file<br>
 
<br>**#293**<br>
What does terraform import do?<br>

A. Imports existing resources into the state file<br>
B. Imports all infrastructure from a given cloud provider<br>
C. Imports a new Terraform module<br>
D. Imports clean copies of tainted resources<br>
E. None of the above<br>
 
<br>**#294**<br>
Which of the following is the correct way to pass the value in the variable num_servers into a module with the input server?<br>

A. servers = var(num_servers)<br>
B. $(var.num_servers)<br>
C. servers = num_servers<br>
D. servers = var.num_servers<br>
 
<br>**#295**<br>
A developer on your team is going to tear down an existing deployment managed by Terraform and deploy a new one. However, there is a server resource named aws_instance.ubuntu[1] they would like to keep. What command should they use to tell Terraform to stop managing that specific resource?<br>

A. terraform destroy aws_instance.ubuntu[l]<br>
B. terraform apply rm aws_instance.ubuntu[l]<br>
C. terraform state rm aws_instance.ubuntu[l]<br>
D. terraform plan rm aws_instance.ubuntu[l]<br>
 
<br>**#296**<br>
Before you can use a remote backend, you must first execute terraform init.<br>

A. True<br>
B. False<br>
 
<br>**#297**<br>
What does running a terraform plan do?<br>

A. Compares your Terraform code and local state file to the remote state file in a cloud provider and determines if any changes need to be made<br>
B. Imports all of your existing cloud provider resources to the state file<br>
C. Installs all providers and modules referenced by configuration<br>
D. Compares the state file to your Terraform code and determines if any changes need to be made<br>
 
<br>**#298**<br>
Which of the following statements about Terraform modules is not true?<br>

A. Modules must be publicly accessible<br>
B. You can call the same module multiple times<br>
C. A module is a container for one or more resources<br>
D. Modules can call other modules<br>
 
<br>**#299**<br>
How can a ticket-based system slow down infrastructure provisioning and limit the ability to scale? (Choose two.)<br>

A. End-users have to request infrastructure changes<br>
B. Ticket based systems generate a full audit trail of the request and fulfillment process<br>
C. Users can access a catalog of approved resources from drop down lists m a request form<br>
D. The more resources your organization needs, the more tickets your infrastructure team has to process<br>
 
<br>**#300**<br>
How do you specify a module's version when publishing it to the public Terraform Module Registry?<br>

A. Configure it in the module's Terraform code<br>
B. Mention it on the module s configuration page on the Terraform Module Registry<br>
C. The Terraform Module Registry does not support versioning modules<br>
D. Tag a release in the associated repo<br>


<br>**#301**<br>
What Terraform command always causes a state file to be updated with changes that might have been made outside of Terraform?<br>

A. terraform plan -refresh-only<br>
B. terraform show -json<br>
C. terraform apply -lock-false<br>
D. terraform plan -target-state<br>
 
<br>**#302**<br>
Which command must you first run before performing further Terraform operations in a working directory?<br>

A. terraform plan<br>
B. terraform workspace<br>
C. terraform init<br>
D. terraform import<br>
 
<br>**#303**<br>
Which command lets you experiment with Terraform expressions?<br>

A. terraform console<br>
B. terraform validate<br>
C. terraform env<br>
D. terraform test<br>
 
<br>**#304**<br>
What kind of configuration block will create an infrastructure object with settings specified within the block?<br>

A. provider<br>
B. state<br>
C. data<br>
D. resource<br>

<br>**#305**<br>
When do changes invoked by terraform apply take effect?<br>

A. After Terraform has updated the state file<br>
B. Once the resource provider has fulfilled the request<br>
C. Immediately<br>
D. None of the above are correct<br>
 
<br>**#306**<br>
What is the workflow for deploying new infrastructure with Terraform?<br>

A. Write Terraform configuration, run terraform init to initialize the working directory or workspace, and run terraform apply<br>
B. Write Terraform configuration, run terraform show to view proposed changes, and terraform apply to create new infrastructure<br>
C. Write Terraform configuration, run terraform apply to create infrastructure, use terraform validate to confirm Terraform deployed resources correctly<br>
D. Write Terraform configuration, run terraform plan to initialize the working directory or workspace, and terraform apply to create the infrastructure<br>
 
<br>**#307**<br>
Which of these are features of Terraform Cloud? (Choose two.)<br>

A. Remote state storage<br>
B. A web-based user interface (UI)<br>
C. Automatic backups<br>
D. Automated infrastructure deployment visualization<br>
 
<br>**#308**<br>
Which option can not keep secrets out of Terraform configuration files?<br>

A. A shared credential file<br>
B. Mark the variable as sensitive<br>
C. Environment Variables<br>
D. A -var flag<br>
 
<br>**#309**<br>
Which of the following is not true of Terraform providers?<br>

A. An individual person can write a Terraform Provider<br>
B. A community of users can maintain a provider<br>
C. HashiCorp maintains some providers<br>
D. Cloud providers and infrastructure vendors can write, maintain, or collaborate on Terraform providers<br>
E. None of the above<br>
 
<br>**#310**<br>
Which Terraform command checks that your configuration syntax is correct?<br>

A. terraform fmt<br>
B. terraform validate<br>
C. terraform init<br>
D. terraform show<br>
 
<br>**#311**<br>
terraform validate uses provider APIs to verify your infrastructure settings.<br>

A. True<br>
B. False<br>
 
<br>**#312**<br>
You add a new provider to your configuration and immediately run terraform apply in the CLI using the local backend. Why does the apply fail?<br>

A. Terraform needs you to format your code according to best practices first<br>
B. Terraform requires you to manually run terraform plan first<br>
C. The Terraform CLI needs you to log into Terraform Cloud first<br>
D. Terraform needs to install the necessary plugins first<br>
 
<br>**#313**<br>
Which of these statements about Terraform Cloud workspaces is false?<br>

A. They can securely store cloud credentials<br>
B. They have role-based access controls<br>
C. You must use the CLI to switch between workspaces<br>
D. Plans and applies can be triggered via version control system integrations<br>
 
<br>**#314**<br>
What value does the Terraform Cloud private registry provide over the public Terraform Module Registry?<br>

A. The ability to restrict modules to members of Terraform Cloud or Enterprise organizations<br>
B. The ability to share modules publicly with any user of Terraform<br>
C. The ability to tag modules by version or release<br>
D. The ability to share modules with public Terraform users and members of Terraform Cloud Organizations<br>
 
<br>**#315**<br>
Terraform providers are part of the Terraform core binary.<br>

A. True<br>
B. False<br>

<br>

---

---

<br>
<br>**#316**<br>
Which of the following is not a benefit of adopting infrastructure as code?<br>

A. Reusability of code<br>
B. Automation<br>
C. Graphical User Interface<br>
D. Versioning<br>
 
<br>**#317**<br>
Where does the Terraform local backend store its state?<br>

A. In the terraform.tfstate file<br>
B. In the .terraform directory<br>
C. In the terraform.tfstate directory<br>
D. In the .terraform.lock.hcl file<br>
 
<br>**#318**<br>
Which of these is true about Terraform's plugin-based architecture?<br>

A. Terraform can only source providers from the internet<br>
B. You can create a provider for your API if none exists<br>
C. Every provider in a configuration has its own state file for its resources<br>
D. All providers are part of the Terraform core binary<br>
 
<br>**#319**<br>
Your risk management organization requires that new AWS S3 buckets must be private and encrypted at rest. How can Terraform Cloud automatically and proactively enforce this security control?<br>

A. Auditing cloud storage buckets with a vulnerability scanning tool<br>
B. With a Sentinel policy, which runs before every apply<br>
C. With an S3 module with proper settings for buckets<br>
D. By adding variables to each Terraform Cloud workspace to ensure these settings are always enabled<br>
 
<br>**#320**<br>
If you don't use the local backend, where does Terraform save resource state?<br>

A. In the remote backend or Terraform Cloud<br>
B. On the disk<br>
C. In memory<br>
D. In an environment variable<br>
 
<br>**#321**<br>
You are writing a child Terraform module that provisions an AWS instance. You want to reference the IP address returned by the child module in the root configuration. You name the instance resource "main".<br>

Which of these is the correct way to define the output value?<br>

A. 
B. 
C. 
D. 
 
<br>**#322**<br>
When does Sentinel enforce policy logic during a Terraform Cloud run?<br>

A. Before the plan phase<br>
B. During the plan phase<br>
C. Before the apply phase<br>
D. After the apply phase<br>
 
<br>**#323**<br>
What is terraform refresh-only intended to detect?<br>

A. Empty state files<br>
B. Corrupt state files<br>
C. Terraform configuration code changes<br>
D. State file drift<br>
 
<br>**#324**<br>
You should run terraform fmt to rewrite all Terraform configurations within the current working directory to conform to Terraform-style conventions.<br>

A. True<br>
B. False<br>
 
<br>**#325**<br>
Why would you use the -replace flag for terraform apply?<br>

A. You want to force Terraform to destroy a resource on the next apply<br>
B. You want Terraform to ignore a resource on the next apply<br>
C. You want to force Terraform to destroy and recreate a resource on the next apply<br>
D. You want Terraform to destroy all the infrastructure in your workspace<br>
 
<br>**#326**<br>
You can configure Terraform to log to a file using the TF_LOG environment variable.<br>

A. True<br>
B. False<br>
 
<br>**#327**<br>
When does Terraform create the .terraform.lock.hcl file?<br>

A. After your first terraform plan<br>
B. After your first terraform apply<br>
C. After your first terraform init<br>
D. Whenever you enable state locking<br>
 
<br>**#328**<br>
You have been working in a Cloud provider account that is shared with other team members. You previously used Terraform to create a load balancer that is listening on port 80. After some application changes, you updated the Terraform code to change the port to 443.<br>

You run terraform plan and see that the execution plan shows the port changing from 80 to 443 like you intended, and step away to grab some coffee.<br>

In the meantime, another team member manually changes the load balancer port to 443 through the Cloud provider console before you get back to your desk.<br>

What will happen when you terraform apply upon returning to your desk?<br>

A. Terraform will fail with an error because the state file is no longer accurate.<br>
B. Terraform will change the load balancer port to 80, and then change it back to 443.<br>
C. Terraform will not make any changes to the Load Balancer and will update the state file to reflect any changes made.<br>
D. Terraform will recreate the load balancer.<br>
 
<br>**#329**<br>
Which of the following is not an action performed by terraform init?<br>

A. Create template configuration files<br>
B. Initialize a configured backend<br>
C. Retrieve the source code for all referenced modules<br>
D. Load required provider plugins<br>
 
<br>**#330**<br>
In a HCP Terraform/Terraform Cloud workspace linked to a version control repository, speculative plan runs start automatically when you merge or commit change to version control.<br>

A. True<br>
B. False<br>



<br>**#331**<br>
Before you can use a new backend or HCP Terraform/Terraform Cloud integration, you must first execute terraform init.<br>

A. True<br>
B. False<br>
 
<br>**#332**<br>


A resource block is shown in the Exhibit space of this page. What is the Terraform resource name of the resource block?<br>

A. test<br>
B. main<br>
C. google<br>
D. compute_instance<br>
 
<br>**#333**<br>
A module block is shown in the Exhibit space of this page.<br>

When you use a module block to reference a module from the Terraform Registry such as the one in the example, how do you specify version 1.0.0 of the module?<br>

A. You cannot. Modules stored on the public Terraform Registry do not support versioning.<br>
B. Add a version = “1.0.0” attribute to the module block.<br>
C. Nothing. Modules stored on the public Terraform module Registry always default to version 1.0.0.<br>
D. Append ?ref=v1.0.0 argument to the source path.<br>
 
<br>**#334**<br>
Which syntax check errors when you run terraform validate?<br>

A. The code contains tabs for indentation instead of spaces.<br>
B. There is a missing value for a variable.<br>
C. The state file does not match the current infrastructure.<br>
D. None of the above.<br>
 
<br>**#335**<br>
Terraform encrypts sensitive values stored in your state file.<br>

A. True<br>
B. False<br>
 
<br>**#336**<br>
When should you run terraform init?<br>

A. Every time you run terraform apply<br>
B. After you run terraform plan for the first time in a new Terraform project and before you run terraform apply<br>
C. After you start coding a new Terraform project and before you run terraform plan for the first time<br>
D. Before you start coding a new Terraform project<br>
 
<br>**#337**<br>
You are making changes to existing Terraform code to add some new infrastructure.<br>

When is the best time to run terraform validate?<br>

A. After you run terraform plan so you can validate that your state file is consistent with your infrastructure<br>
B. Before you run terraform plan so you can validate your code syntax<br>
C. Before you run terraform apply so you can validate your infrastructure<br>
D. After you run terraform apply so you can validate your provider credentials<br>
 
<br>**#338**<br>
Which of these commands makes your code more human readable?<br>

A. terraform validate<br>
B. terraform output<br>
C. terraform show<br>
D. terraform fmt<br>
 
<br>**#339**<br>
Terraform configuration can only import from the public registry.<br>

A. True<br>
B. False<br>
 
<br>**#340**<br>
What is the Terraform resource name of the following resource block?<br>

A. test<br>
B. google<br>
C. main<br>
D. compute_instance<br>
 
<br>**#341**<br>
terraform init retrieves and caches the configuration for all remote modules.<br>

A. True<br>
B. False<br>
 
<br>**#342**<br>
Terraform configuration can only call modules from the public registry.<br>

A. True<br>
B. False<br>
 
<br>**#343**<br>


A resource block is shown in the Exhibit section of this page. How would you reference the attribute name of this resource in HCL?<br>

A. data.kubernetes_namespace.name<br>
B. resource.kubernetes_namespace.example.name<br>
C. kubernetes_namespace.test.name<br>
D. kubernetes_namespace.example.name<br>
 
<br>**#344**<br>
You want to use API tokens and other secrets within your team’s Terraform workspaces. Where does HashiCorp recommend you store these sensitive values? (Choose three.)<br>

A. In a terraform.tfvars file, securely managed and shared with your team.<br>
B. In HashiCorp Vault.<br>
C. In a terraform.tfvars file, checked into your version control system.<br>
D. In a plaintext document on a shared drive.<br>
E. In an HCP Terraform/Terraform Cloud variable, with the sensitive option checked.<br>
 
<br>**#345**<br>
What happens when you execute terraform plan?<br>

A. Imports all of your existing cloud provider resources to the state.<br>
B. Installs all providers and modules referenced by configuration.<br>
C. Compares your Terraform code and local state file to the remote state file in a cloud provider and determines if any changes need to be made.<br>
D. Refreshes your state, then compares your state file to your Terraform configuration and creates an execution plan if any changes need to be made.<br>


<br>**#346**<br>
What does terraform destroy do?<br>

A. Destroys the Terraform state file, leaves the infrastructure intact.<br>
B. Destroys all Terraform code files in the current directory, leaves the state file intact.<br>
C. Destroy all infrastructure in the Terraform state file.<br>
D. Destroys all infrastructure in the configured Terraform provider.<br>


