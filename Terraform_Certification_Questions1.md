
# Terraform - Simulado 1

### 1

The terraform.tfstate file always matches your currently built infrastructure.<br>

A. True<br>
**B**. False<br>

<br>

### 2

One remote backend configuration always maps to a single remote workspace.<br>

A. True<br>
**B**. False<br>

<br>

### 3

How is the Terraform remote backend different than other state backends such as S3, Consul, etc.?<br>

**A**. It can execute Terraform runs on dedicated infrastructure on premises or in Terraform Cloud<br>
B. It doesn't show the output of a terraform apply locally<br>
C. It is only available to paying customers<br>
D. All of the above<br>

<br>

### 4

What is the workflow for deploying new infrastructure with Terraform?<br>

A. terraform plan to import the current infrastructure to the state file, make code changes, and terraform apply to update the infrastructure.<br>
B. Write a Terraform configuration, run terraform show to view proposed changes, and terraform apply to create new infrastructure.<br>
C. terraform import to import the current infrastructure to the state file, make code changes, and terraform apply to update the infrastructure.<br>
**D**. Write a Terraform configuration, run terraform init, run terraform plan to view planned infrastructure changes, and terraform apply to create new infrastructure.<br>

<br>

### 5

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

<br>

### 6

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

<br>

### 7

Which provisioner invokes a process on the resource created by Terraform?<br>

**A**. remote-exec<br>
B. null-exec<br>
C. local-exec<br>
D. file<br>

<br>

### 8

Which of the following is not true of Terraform providers?<br>

A. Providers can be written by individuals<br>
B. Providers can be maintained by a community of users<br>
C. Some providers are maintained by HashiCorp<br>
D. Major cloud vendors and non-cloud vendors can write, maintain, or collaborate on Terraform providers<br>
**E**. None of the above<br>

<br>

### 9

What command does Terraform require the first time you run it within a configuration directory?<br>

A. terraform import<br>
**B**. terraform init<br>
C. terraform plan<br>
D. terraform workspace<br>

<br>

### 10

You have deployed a new webapp with a public IP address on a cloud provider. However, you did not create any outputs for your code.<br>
What is the best method to quickly find the IP address of the resource you deployed?<br>

A. Run terraform output ip_address to view the result<br>
B. In a new folder, use the terraform_remote_state data source to load in the state file, then write an output for each resource that you find the state file<br>
**C**. Run terraform state list to find the name of the resource, then terraform state show to find the attributes including public IP address<br>
D. Run terraform destroy then terraform apply and look for the IP address in stdout<br>

<br>

### 11

Which of the following is not a key principle of infrastructure as code?<br>

A. Versioned infrastructure<br>
**B**. Golden images<br>
C. Idempotence<br>
D. Self-describing infrastructure<br>

<br>

### 12

Terraform variables and outputs that set the "description" argument will store that description in the state file.<br>

**A**. True<br>
B. False<br>

When you set the description argument for variables and outputs in Terraform, the description is indeed stored in the state file. This is primarily useful for providing context or documentation for the variables and outputs when inspecting or reviewing the state.<br>

<br>

### 13

What is the provider for this fictitious resource?<br>
>resource "aws_vpc" "main" {<br>
>	name = "test"	<br>
>}<br>

A. vpc<br>
B. main<br>
**C**. aws<br>
D. test<br>

<br>

### 14

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

<br>

### 15

What is not processed when running a terraform refresh?<br>

A. State file<br>
**B**. Configuration file<br>
C. Credentials<br>
D. Cloud provider<br>

<br>

### 16

What information does the public Terraform Module Registry automatically expose about published modules?<br>

A. Required input variables<br>
B. Optional inputs variables and default values<br>
C. Outputs<br>
**D**. All of the above<br>
E. None of the above<br>

<br>

### 17

If a module uses a local values, you can expose that value with a terraform output.<br>

**A.** True<br>
B. False<br>

<br>

### 18

You should store secret data in the same version control repository as your Terraform configuration.<br>

A. True<br>
**B**. False<br>

<br>

### 19

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

<br>

### 20

You have provisioned some virtual machines (VMs) on Google Cloud Platform (GCP) using the gcloud command line tool. However, you are standardizing with
Terraform and want to manage these VMs using Terraform instead.<br>
What are the two things you must do to achieve this? (Choose two.)<br>

A. Provision new VMs using Terraform with the same VM names<br>
**B**. Use the terraform import command for the existing VMs<br>
**C**. Write Terraform configuration for the existing VMs<br>
D. Run the terraform import-gcp command<br>

<br>

### 21

You have recently started a new job at a retailer as an engineer. As part of this new role, you have been tasked with evaluating multiple outages that occurred during peak shopping time during the holiday season. Your investigation found that the team is manually deploying new compute instances and configuring each compute instance manually. This has led to inconsistent configuration between each compute instance.<br>
How would you solve this using infrastructure as code?<br>

A. Implement a ticketing workflow that makes engineers submit a ticket before manually provisioning and configuring a resource<br>
B. Implement a checklist that engineers can follow when configuring compute instances<br>
C. Replace the compute instance type with a larger version to reduce the number of required deployments<br>
**D**. Implement a provisioning pipeline that deploys infrastructure configurations committed to your version control system following code reviews<br>

<br>

### 22

terraform init initializes a sample main.tf file in the current directory.<br>

A. True<br>
**B**. False<br>

<br>

### 23

Which two steps are required to provision new infrastructure in the Terraform workflow? (Choose two.)<br>

A. Destroy<br>
**B**. Apply<br>
C. Import<br>
**D**. Init<br>
E. Validate<br>

<br>

### 24

Why would you use the terraform taint command?<br>

A. When you want to force Terraform to destroy a resource on the next apply<br>
**B**. When you want to force Terraform to destroy and recreate a resource on the next apply<br>
C. When you want Terraform to ignore a resource on the next apply<br>
D. When you want Terraform to destroy all the infrastructure in your workspace<br>

<br>

### 25

Terraform requires the Go runtime as a prerequisite for installation.<br>

A. True<br>
**B**. False<br>

<br>

### 26

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

<br>

### 27

Terraform can import modules from a number of sources `" which of the following is not a valid source?<br>

**A**. FTP server
B. GitHub repository
C. Local path
D. Terraform Module Registry

<br>

### 28

Which of the following is available only in Terraform Enterprise or Cloud workspaces and not in Terraform CLI?<br>

**A**. Secure variable storage<br>
B. Support for multiple cloud providers<br>
C. Dry runs with terraform plan<br>
D. Using the workspace as a data source<br>

<br>

### 29

terraform validate validates the syntax of Terraform files.<br>

**A**. True<br>
B. False<br>

<br>

### 30

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

<br>

### 31

Which of the following is the correct way to pass the value in the variable num_servers into a module with the input servers?<br>

A. servers = num_servers<br>
B. servers = variable.num_servers<br>
C. servers = var(num_servers)<br>
**D**. servers = var.num_servers<br>

<br>

### 32

A Terraform provisioner must be nested inside a resource configuration block.<br>

**A**. True<br>
B. False<br>

**A. True**

A Terraform provisioner must be nested inside a resource configuration block.
Provisioners are used to execute scripts or commands on a resource once it's created or destroyed, and they must be associated with a specific resource to function. They cannot exist outside of a resource block.<br>

<br>

### 33

Terraform can run on Windows or Linux, but it requires a Server version of the Windows operating system.<br>

A. True<br>
**B**. False<br>

<br>

### 34

What does the default "local" Terraform backend store?<br>

A. tfplan files<br>
B. Terraform binary<br>
C. Provider plugins<br>
**D**. State file<br>

<br>

### 35

You have multiple team members collaborating on infrastructure as code (IaC) using Terraform, and want to apply formatting standards for readability.<br>
How can you format Terraform HCL (HashiCorp Configuration Language) code according to standard Terraform style convention?<br>

**A**. Run the terraform fmt command during the code linting phase of your CI/CD process<br>
B. Designate one person in each team to review and format everyone's code<br>
C. Manually apply two spaces indentation and align equal sign "=" characters in every Terraform file (*.tf)<br>
D. Write a shell script to transform Terraform files using tools such as AWK, Python, and sed<br>

<br>

### 36

What value does the Terraform Cloud/Terraform Enterprise private module registry provide over the public Terraform Module Registry?<br>

A. The ability to share modules with public Terraform users and members of Terraform Enterprise Organizations<br>
B. The ability to tag modules by version or release<br>
**C**. The ability to restrict modules to members of Terraform Cloud or Enterprise organizations<br>
D. The ability to share modules publicly with any user of Terraform<br>

<br>

### 37

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

<br>

### 38

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

<br>

### 39

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

<br>

### 40

When using a module block to reference a module stored on the public Terraform Module Registry such as:<br>
```
module "consul" {<br>
	source = "hashicorp/consul/aws<br>
}<br>
```
How do you specify version 1.0.0?<br>

A. Modules stored on the public Terraform Module Registry do not support versioning<br>
B. Append ?ref=v1.0.0 argument to the source path<br>
**C**. Add version = "1.0.0" attribute to module block<br>
D. Nothing ג€" modules stored on the public Terraform Module Registry always default to version 1.0.0<br>

<br>

### 41

What features does the hosted service Terraform Cloud provide? (Choose two.)<br>

A. Automated infrastructure deployment visualization<br>
B. Automatic backups<br>
**C**. Remote state storage<br>
**D**. A web-based user interface (UI)<br>

<br>

### 42

Where does the Terraform local backend store its state?<br>

A. In the /tmp directory<br>
B. In the terraform file<br>
**C**. In the terraform.tfstate file<br>
D. In the user's terraform.state file<br>

<br>

### 43

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

<br>

### 44

What is one disadvantage of using dynamic blocks in Terraform?<br>

A. They cannot be used to loop through a list of values<br>
B. Dynamic blocks can construct repeatable nested blocks<br>
**C**. They make configuration harder to read and understand<br>
D. Terraform will run more slowly<br>

<br>

### 45

Only the user that generated a plan may apply it.<br>

A. True<br>
**B**. False<br>

<br>

### 46

Examine the following Terraform configuration, which uses the data source for an AWS AMI.<br>
What value should you enter for the ami argument in the AWS instance resource?<br>
```
data "aws_ami" "ubuntu" {
	...
}

resource "aws_instance" "web" {
	ami = 
	instance_type = "t2.micro"

	tags = {
		Name = "HelloWorld"
   }
}
```

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

<br>

### 47

FILL BLANK -<br>
You need to specify a dependency manually.<br>
What resource meta-parameter can you use to make sure Terraform respects the dependency?<br>
Type your answer in the field provided. The text field is not case-sensitive and all variations of the correct answer are accepted.<br>

**depends_on**

<br>

### 48

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

<br>

### 49

What is the name assigned by Terraform to reference this resource?<br>
```
resource "azurerm_resource_group" "dev" {
    name = "test"
    location - "westus"
}
```

**A**. dev<br>
B. azurerm_resource_group<br>
C. azurerm<br>
D. test<br>

<br>

### 50

Setting the TF_LOG environment variable to DEBUG causes debug messages to be logged into syslog.<br>

A. True<br>
**B**. False<br>

**B. False**<br>

Setting the TF_LOG environment variable to DEBUG will output debug messages to the terminal (standard output), not to syslog. Terraform logs debug information directly to the console or wherever the output is directed, such as a file if you choose to redirect it. It does not automatically log to syslog.<br>

If you need to send logs to syslog, you would need to configure this redirection manually.<br>

<br>

### 51

Where in your Terraform configuration do you specify a state backend?<br>

**A**. The terraform block<br>
B. The resource block<br>
C. The provider block<br>
D. The datasource block<br>

<br>

### 52

In Terraform 0.13 and above, outside of the required_providers block, Terraform configurations always refer to providers by their local names.<br>

**A**. True<br>
B. False<br>

**A. True**<br>

In Terraform 0.13 and above, outside of the required_providers block, providers are always referred to by their local names. The local name is the alias or identifier you assign to a provider in your configuration, which allows you to reference the provider throughout your configuration without needing to specify its source or version every time. The required_providers block is where you specify the full source address and version constraints for the provider.<br>

<br>

### 53

What command should you run to display all workspaces for the current configuration?<br>

A. terraform workspace<br>
B. terraform workspace show<br>
**C**. terraform workspace list<br>
D. terraform show workspace<br>

<br>

### 54

Terraform providers are always installed from the Internet.<br>

A. True<br>
**B**. False<br>

**B. False**<br>

Terraform providers are not always installed from the Internet. While the default behavior is to download providers from Terraform’s provider registry, you can also install providers from other sources. For example, you can configure Terraform to use:<br>

**- Local provider binaries** stored on your system.<br>
**- Private provider registries** within your organization.<br>
**- Mirror directories** to cache providers locally for offline use.<br>
These options provide flexibility, especially in environments with restricted Internet access or when using custom providers.<br>

<br>

### 55

Which of these is the best practice to protect sensitive values in state files?<br>

A. Blockchain<br>
B. Secure Sockets Layer (SSL)<br>
**C**. Enhanced remote backends<br>
D. Signed Terraform providers<br>

<br>

### 56

When does terraform apply reflect changes in the cloud environment?<br>

A. Immediately<br>
**B**. However long it takes the resource provider to fulfill the request<br>
C. After updating the state file<br>
D. Based on the value provided to the -refresh command line argument<br>
E. None of the above<br>

<br>

### 57

How would you reference the "name" value of the second instance of this fictitious resource?<br>
```
resource "aws_instance" "web" {
  count = 2
  name  = "terraform-${count.index}
}
```
A. element(aws_instance.web, 2)<br>
**B**. aws_instance.web[1].name<br>
C. aws_instance.web[1]<br>
D. aws_instance.web[2].name<br>
E. aws_instance.web.*.name<br>

<br>

### 58

A Terraform provider is not responsible for:<br>

A. Understanding API interactions with some service<br>
**B**. Provisioning infrastructure in multiple clouds<br>
C. Exposing resources and data sources based on an API<br>
D. Managing actions to take based on resource differences<br>

<br>

### 59

Terraform provisioners can be added to any resource block.<br>

**A**. True<br>
B. False<br>

<br>

### 60

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

<br>

### 61

FILL BLANK -<br>
Which flag would you add to terraform plan to save the execution plan to a file?<br>
Type your answer in the field provided. The text field is not case-sensitive and all variations of the correct answer are accepted.<br>

**-out=FILE_NAME**<br>
 
The flag you would add to terraform plan to save the execution plan to a file is:<br>

**-out**<br>

For example, the command would look like this:<br>

>bash<br>
>terraform plan -out=planfile<br>

<br>

### 62

FILL BLANK -<br>
What is the name of the default file where Terraform stores the state?<br>
Type your answer in the field provided. The text field is not case-sensitive and all variations of the correct answer are accepted.<br>

**terraform.tfstate**
https://www.terraform.io/docs/language/state/index.html

<br>

### 63

A Terraform local value can reference other Terraform local values.<br>

**A**. True<br>
B. False<br>

**A. True**<br>

In Terraform, a local value can reference other local values. This allows for organizing and simplifying complex expressions by breaking them into smaller, more manageable pieces. However, the order of the local values matters, and Terraform will resolve them accordingly.<br>

<br>

### 64

Which of the following is not a valid Terraform collection type?<br>

A. list<br>
B. map<br>
**C**. tree<br>
D. set<br>

<br>

### 65

When running the command terraform taint against a managed resource you want to force recreation upon, Terraform will immediately destroy and recreate the resource.<br>

A. True<br>
**B**. False<br>

