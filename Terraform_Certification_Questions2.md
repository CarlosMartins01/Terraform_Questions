
# Terraform - Simulado 2

### 66

All standard backend types support state storage, locking, and remote operations like plan, apply and destroy.<br>

A. True<br>
**B**. False<br>

**B. False**

Not all standard backend types in tools like Terraform support state storage, locking, and remote operations such as plan, apply, and destroy. Some backends only support basic state storage and retrieval, while others, such as the remote backend, support additional features like state locking and remote operations.<br>

<br>

### 67

How can terraform plan aid in the development process?<br>

**A**. Validates your expectations against the execution plan without permanently modifying state<br>
B. Initializes your working directory containing your Terraform configuration files<br>
C. Formats your Terraform configuration files<br>
D. Reconciles Terraform's state against deployed resources and permanently modifies state using the current status of deployed resources<br>

**A. Validates your expectations against the execution plan without permanently modifying state**

terraform plan helps in the development process by showing you what changes will be made without actually making any changes to your infrastructure or state. It helps validate whether the resources and configurations you intend to modify, add, or remove align with your expectations.<br>

<br>

### 68

You would like to reuse the same Terraform configuration for your development and production environments with a different state file for each.<br>
Which command would you use?<br>

A. terraform import<br>
**B**. terraform workspace<br>
C. terraform state<br>
D. terraform init<br>

<br>

### 69

What is the name assigned by Terraform to reference this resource?<br>
```
mainresource "google_compute_instance" "main" {
  name = "test"
}
```
A. compute_instance<br>
**B**. main<br>
C. google<br>
D. teat<br>
 
<br>**#70**<br>
You're building a CI/CD (continuous integration/ continuous delivery) pipeline and need to inject sensitive variables into your Terraform run.<br>
How can you do this safely?<br>

**A**. Pass variables to Terraform with a -var flag<br>
B. Copy the sensitive variables into your Terraform code<br>
C. Store the sensitive variables in a secure_vars.tf file<br>
D. Store the sensitive variables as plain text in a source code repository<br>

<br>

### 71

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

<br>

### 72

In contrast to Terraform Open Source, when working with Terraform Enterprise and Cloud Workspaces, conceptually you could think about them as completely separate working directories.<br>

**A**. True<br>
B. False<br>

<br>

### 73

You want to know from which paths Terraform is loading providers referenced in your Terraform configuration (*.tf files). You need to enable debug messages to find this out.<br>
Which of the following would achieve this?<br>

**A**. Set the environment variable TF_LOG=TRACE<br>
B. Set verbose logging for each provider in your Terraform configuration<br>
C. Set the environment variable TF_VAR_log=TRACE<br>
D. Set the environment variable TF_LOG_PATH<br>

<br>

### 74

How is terraform import run?<br>

A. As a part of terraform init<br>
B. As a part of terraform plan<br>
C. As a part of terraform refresh<br>
**D**. By an explicit call<br>
E. All of the above<br>

<br>

### 75

You have a simple Terraform configuration containing one virtual machine (VM) in a cloud provider. You run terraform apply and the VM is created successfully.
What will happen if you delete the VM using the cloud provider console, and run terraform apply again without changing any Terraform code?<br>

A. Terraform will remove the VM from state file<br>
B. Terraform will report an error<br>
C. Terraform will not make any changes<br>
**D**. Terraform will recreate the VM<br>

<br>

### 76

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

<br>

### 77

Your DevOps team is currently using the local backend for your Terraform configuration. You would like to move to a remote backend to begin storing the state file in a central location.<br>
Which of the following backends would not work?<br>

A. Amazon S3<br>
B. Artifactory<br>
**C**. Git<br>
D. Terraform Cloud<br>

<br>

### 78

Which backend does the Terraform CLI use by default?<br>

A. Terraform Cloud<br>
B. Consul<br>
C. Remote<br>
**D**. Local<br>

<br>

### 79

When you initialize Terraform, where does it cache modules from the public Terraform Module Registry?<br>

A. On disk in the /tmp directory<br>
B. In memory<br>
**C**. On disk in the .terraform sub-directory<br>
D. They are not cached<br>

<br>

### 80

You write a new Terraform configuration and immediately run terraform apply in the CLI using the local backend.<br>
Why will the apply fail?<br>

A. Terraform needs you to format your code according to best practices first<br>
**B**. Terraform needs to install the necessary plugins first<br>
C. The Terraform CLI needs you to log into Terraform cloud first<br>
D. Terraform requires you to manually run terraform plan first<br>

<br>

### 81

What features stops multiple admins from changing the Terraform state at the same time?<br>

A. Version control<br>
B. Backend types<br>
C. Provider constraints<br>
**D**. State locking<br>

<br>

### 82
A fellow developer on your team is asking for some help in refactoring their Terraform code. As part of their application's architecture, they are going to tear down an existing deployment managed by Terraform and deploy new. However, there is a server resource named aws_instance.ubuntu[1] they would like to keep to perform some additional analysis.<br>
What command should be used to tell Terraform to no longer manage the resource?<br>

A. terraform apply rm aws_instance.ubuntu[1]<br>
**B**. terraform state rm aws_instance.ubuntu[1]<br>
C. terraform plan rm aws_instance.ubuntu[1]<br>
D. terraform delete aws_instance.ubuntu[1]<br>

<br>

### 83

Terraform can only manage resource dependencies if you set them explicitly with the depends_on argument.<br>

A. True<br>
**B**. False<br>

<br>

### 80

A terraform apply can not _________ infrastructure.<br>

A. change<br>
B. destroy<br>
C. provision<br>
**D**. import<br>

<br>

### 85

You need to constrain the GitHub provider to version 2.1 or greater.<br>
Which of the following should you put into the Terraform 0.12 configuration's provider block?<br>

A. version >= 2.1<br>
B. version ~> 2.1<br>
C. version = ג€<= 2.1ג€<br>
**D**. version = ג€>= 2.1ג€<br>

<br>

### 86

You just scaled your VM infrastructure and realized you set the count variable to the wrong value. You correct the value and save your change.<br>
What do you do next to make your infrastructure match your configuration?<br>

**A**. Run an apply and confirm the planned changes<br>
B. Inspect your Terraform state because you want to change it<br>
C. Reinitialize because your configuration has changed<br>
D. Inspect all Terraform outputs to make sure they are correct<br>

<br>

### 87

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

<br>

### 88

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

<br>

### 89

Which of the following is allowed as a Terraform variable name?<br>

A. count<br>
**B**. name<br>
C. source<br>
D. version<br>

<br>

### 90

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

<br>

### 91

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

<br>

### 92

If writing Terraform code that adheres to the Terraform style conventions, how would you properly indent each nesting level compared to the one above it?<br>

A. With four spaces<br>
B. With a tab<br>
C. With three spaces<br>
**D**. With two spaces<br>

<br>

### 93

Which of the following is not an action performed by terraform init?<br>

**A**. Create a sample main.tf file<br>
B. Initialize a configured backend<br>
C. Retrieve the source code for all referenced modules<br>
D. Load required provider plugins<br>

<br>

### 94

HashiCorp Configuration Language (HCL) supports user-defined functions.<br>

A. True<br>
**B**. False<br>

<br>

### 95

How can you trigger a run in a Terraform Cloud workspace that is connected to a Version Control System (VCS) repository?<br>

A. Only Terraform Cloud organization owners can set workspace variables on VCS connected workspaces<br>
**B**. Commit a change to the VCS work
A. Sources all providers present in the configuration and ensures they are downloaded and available locally<br>
B. Connects to the backend<br>
C. Sources any modules and copies the configuration locally<br>
D. Validates all required variables are present<br>
 
**B. Commit a change to the VCS working directory and branch that the Terraform Cloud workspace is connected to**<br>

When a Terraform Cloud workspace is connected to a Version Control System (VCS) repository, committing a change to the repository in the specific branch that the workspace is tracking will trigger a run. This allows Terraform Cloud to automatically detect changes and apply them based on the configuration stored in the VCS.<br>

B is correct because when Terraform runs the next plan or apply operation, it will detect changes made outside of Terraform (e.g., in the Azure Cloud Console) and will update the state file accordingly to reflect the actual infrastructure.<br>

C is correct because Terraform's state file is only updated when Terraform runs a command (such as plan or apply). Changes made directly in Azure without running Terraform will not automatically update the state file.<br>

The other options are incorrect:<br>

A is false because changes made directly in the Azure Cloud Console are not automatically recorded in the Terraform state file until Terraform is run again.<br>
D is false for the same reason, as changes are not immediately reflected in the current state file when made outside of Terraform.<br>

<br>

### 96

Terraform and Terraform providers must use the same major version number in a single configuration.<br>

A. True<br>
**B**. False<br>

<br>

### 97

Which statement describes a goal of infrastructure as code?<br>

A. An abstraction from vendor specific APIs<br>
B. Write once, run anywhere<br>
C. A pipeline process to test and deliver software<br>
**D**. The programmatic configuration of resources<br>

<br>

### 98

When using Terraform to deploy resources into Azure, which scenarios are true regarding state files? (Choose two.)<br>

A. When a change is made to the resources via the Azure Cloud Console, the changes are recorded in a new state file<br>
B. When a change is made to the resources via the Azure Cloud Console, Terraform will update the state file to reflect them during the next plan or apply<br>
**C**. When a change is made to the resources via the Azure Cloud Console, the current state file will not be updated<br>
D. When a change is made to the resources via the Azure Cloud Console, the changes are recorded in the current state file<br>

<br>

### 99

You need to deploy resources into two different cloud regions in the same Terraform configuration. To do that, you declare multiple provider configurations as follows:<br>
```
provider "aws" {
   region = "us-west"
}

provider "aws" {
   alias = "west"
   region = "us-west-2"
}
```
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

<br>

### 100

You have declared an input variable called environment in your parent module. What must you do to pass the value to a child module in the configuration?<br>

A. Add node_count = var.node_count<br>
B. Declare the variable in a terraform.tfvars file<br>
**C**. Declare a node_count input variable for child module<br>
D. Nothing, child modules inherit variables of parent module<br>
C. Declare a node_count input variable for the child module<br>

To pass an input variable from a parent module to a child module, you must declare the input variable in the child module's variables.tf file (or inline) and then pass the parent's variable when calling the child module in the configuration. For example:<br>

In the parent module, you would pass the variable like this:<br>

>hcl<br>
```
module "child_module" {
  source      = "./child_module"
  environment = var.environment
}
```
In the child module, you would need to declare the environment variable:<br>

>hcl<br>
```
variable "environment" {
  type = string
}
```
Child modules do not automatically inherit variables from the parent module, so you need to explicitly pass them.<br>

<br>

### 101

If a module declares a variable with a default, that variable must also be defined within the module.<br>

A. True<br>
**B**. False<br>

<br>

### 102

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

<br>

### 103

Which of the following arguments are required when declaring a Terraform output?<br>

A. sensitive<br>
B. description<br>
C. default<br>
**D**. value<br>

<br>

### 104

Your risk management organization requires that new AWS S3 buckets must be private and encrypted at rest. How can Terraform Enterprise automatically and proactively enforce this security control?<br>

**A**. With a Sentinel policy, which runs before every apply<br>
B. By adding variables to each TFE workspace to ensure these settings are always enabled<br>
C. With an S3 module with proper settings for buckets<br>
D. Auditing cloud storage buckets with a vulnerability scanning tool<br>

<br>

### 105

Most Terraform providers interact with ____________.<br>

**A**. API<br>
B. VCS Systems<br>
C. Shell scripts<br>
D. None of the above<br>

<br>

### 106

terraform validate validates that your infrastructure matches the Terraform state file.<br>

A. True<br>
**B**. False<br>

<br>

### 107
What does terraform import allow you to do?<br>

A. Import a new Terraform module<br>
B. Use a state file to import infrastructure to the cloud<br>
**C**. Import provisioned infrastructure to your state file<br>
D. Import an existing state file to a new Terraform workspace<br>

<br>

### 108

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

<br>

### 102

How would you reference the Volume IDs associated with the ebs_block_device blocks in this configuration?<br>

```
resource "aws_instance" "example" {
   ami = "ami-abc123
   instance_type = "t2.micro"

ebs_block_device {
   device_name = "sda2"
   volume_size = 16
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

<br>

### 110

What does state locking accomplish?<br>

A. Copies the state file from memory to disk<br>
B. Encrypts any credentials stored within the state file<br>
**C**. Blocks Terraform commands from modifying the state file<br>
D. Prevents accidental deletion of the state file<br>

<br>

### 111

You just upgraded the version of a provider in an existing Terraform project. What do you need to do to install the new provider?<br>

A. Run terraform apply -upgrade<br>
**B**. Run terraform init -upgrade<br>
C. Run terraform refresh<br>
D. Upgrade your version of Terraform<br>

<br>

### 112

A module can always refer to all variables declared in its parent module.<br>

A. True<br>
**B**. False<br>

**B. False**<br>

A module cannot automatically refer to all variables declared in its parent module. Variables must be explicitly passed from the parent module to the child module. Each module has its own variable scope, and values from the parent module need to be provided to the child module through the module block using var.<variable_name>. There is no automatic inheritance of variables between modules.<br>

<br>

### 113

When you use a remote backend that needs authentication, HashiCorp recommends that you:<br>

**A**. Use partial configuration to load the authentication credentials outside of the Terraform code<br>
B. Push your Terraform configuration to an encrypted git repository<br>
C. Write the authentication credentials in the Terraform configuration files<br>
D. Keep the Terraform configuration files in a secret store<br>

<br>

### 114

You have a simple Terraform configuration containing one virtual machine (VM) in a cloud provider. You run terraform apply and the VM is created successfully.
What will happen if you terraform apply again immediately afterwards without changing any Terraform code?<br>

A. Terraform will terminate and recreate the VM<br>
B. Terraform will create another duplicate VM<br>
**C**. Terraform will apply the VM to the state file<br>
D. Nothing<br>

**C. Rebuild only the instances that were deleted**

When you run terraform apply, Terraform compares the current state of the infrastructure with the desired state defined in the configuration files. If any resources (such as cloud instances) were accidentally deleted, Terraform will recreate only those resources to bring the infrastructure back in line with the desired state. It does not rebuild everything from scratch or tear down the entire infrastructure unless explicitly instructed to do so.<br>

<br>

### 115

A junior admin accidentally deleted some of your cloud instances. What does Terraform do when you run terraform apply?<br>

A. Build a completely brand new set of infrastructure<br>
B. Tear down the entire workspace infrastructure and rebuild it<br>
**C**. Rebuild only the instances that were deleted<br>
D. Stop and generate an error message about the missing instances<br>

<br>

### 116

You have created a main.tf Terraform configuration consisting of an application server, a database, and a load balancer. You ran terraform apply and all resources were created successfully. Now you realize that you do not actually need the load balancer so you run terraform destroy without any flags What will happen?<br>

A. Terraform will destroy the application server because it is listed first in the code<br>
**B**. Terraform will prompt you to confirm that you want to destroy all the infrastructure<br>
C. Terraform will destroy the main.tf file<br>
D. Terraform will prompt you to pick which resource you want to destroy<br>
E. Terraform will immediately destroy all the infrastructure<br>

<br>

### 117

Which type of block fetches or computes information for use elsewhere in a Terraform configuration?<br>

A. provider<br>
B. resource<br>
C. local<br>
**D**. data<br>

<br>

### 118

You have just developed a new Terraform configuration for two virtual machines with a cloud provider. You would like to create the infrastructure for the first time.<br>
Which Terraform command should you run first?<br>

A. terraform apply<br>
B. terraform plan<br>
C. terraform show<br>
**D**. terraform init<br>

<br>

### 119

All modules published on the official Terraform Module Registry have been verified by HashiCorp.<br>

A. True<br>
**B**. False<br>

<br>

### 120

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

<br>

### 121

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

<br>

### 122

A Terraform backend determines how Terraform loads state and stores updates when you execute ___________.<br>

A. apply<br>
B. taint<br>
C. destroy<br>
**D**. All of the above<br>
E. None of the above<br>

<br>

### 123

What does Terraform use .terraform.lock.hcl file for?<br>

**A**. Tracking provider dependencies<br>
B. There is no such file<br>
C. Preventing Terraform runs from occurring<br>
D. Storing references to workspaces which are locked<br>

**A. Tracking provider dependencies**<br>

The .terraform.lock.hcl file is used by Terraform to track provider dependencies and their versions. This file ensures that the exact versions of providers used in your Terraform configuration are locked, so that future runs of Terraform will use the same versions, even if newer versions of those providers are available. This helps maintain consistency across different environments and prevents unexpected changes caused by provider updates.<br>

For example, when you run terraform init, this file is created or updated to lock the provider versions specified in your configuration.<br>

<br>

### 124

You've used Terraform to deploy a virtual machine and a database. You want to replace this virtual machine instance with an identical one without affecting the database. What is the best way to achieve this using Terraform?<br>

A. Use the terraform state rm command to remove the VM from state file<br>
**B**. Use the terraform taint command targeting the VMs then run terraform plan and terraform apply<br>
C. Use the terraform apply command targeting the VM resources only<br>
D. Delete the Terraform VM resources from your Terraform code then run terraform plan and terraform apply<br>

<br>

### 125

How do you specify a module's version when publishing it to the public Terraform Module Registry?<br>

A. The module's configuration page on the Terraform Module Registry<br>
B. Terraform Module Registry does not support versioning modules<br>
**C**. The release tags in the associated repo<br>
D. The module's Terraform code<br>

<br>

### 126

Terraform plan updates your state file.<br>

A. True<br>
**B**. False<br>

<br>

### 127

To check if all code in a Terraform configuration with multiple modules is properly formatted without making changes, what command should be run?<br>

**A**. terraform fmt -check<br>
B. terraform fmt -write-false<br>
C. terraform fmt ג€"list -recursive<br>
D. terraform fmt -check -recursive<br>

**A. terraform fmt -check**

The terraform fmt -check command checks if all the code in the Terraform configuration is properly formatted without making any changes. It reports whether the formatting is correct but doesn't automatically reformat the code.<br>

For configurations with multiple modules, you can also add the -recursive flag to apply the check across all subdirectories:<br>

If you want to include all subdirectories (like modules), you can add the -recursive flag:<br>

**bash**
```
terraform fmt -check -recursive
This will check formatting in all the modules and subdirectories within your configuration.
```

<br>

### 128

As a member of the operations team, you need to run a script on a virtual machine created by Terraform. Which provision is best to use in your Terraform code?<br>

A. null-ex׀µׁ<br>
B. local-exec<br>
**C**. remote-exec<br>
D. file<br>

<br>

### 129

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

<br>

### 130

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
