
# Terraform - Simulado 5

### 261

The Terraform binary version and provider versions must match each other in a single configuration.<br>

A. True<br>
B. False<br>

<br>

### 262

The .terraform.lock.hcl file tracks module versions.<br>

A. True<br>
B. False<br>

<br>

### 263

You can develop a custom provider to manage its resources using Terraform.<br>

A. True<br>
B. False<br>

<br>

### 264

Which of these is not a benefit of remote state?<br>

A. Keeping unencrypted sensitive information off disk<br>
B. Easily share reusable code modules<br>
C. Working in a team<br>
D. Delegate output to other teams<br>

<br>

### 265

When using multiple configurations of the same Terraform provider, what meta-argument must be included in any non-default provider configurations?<br>

A. depends_on<br>
B. alias<br>
C. id<br>
D. name<br>

<br>

### 266

A developer accidentally launched a VM (virtual machine) outside of the Terraform workflow and ended up with two servers with the same name. They don’t know which VM Terraform manages but do have a list of all active VM IDs.<br>

Which of the following methods could you use to discover which instance Terraform manages?<br>

A. Run terraform taint/code on all the VMs to recreate them<br>
B. Update the code to include outputs for the ID of all VMs, then run terraform plan to view the outputs<br>
C. Run terraform state list to find the names of all VMs, then run terraform state show for each of them to find which VM ID Terraform manages<br>
D. Use terraform refresh/code to find out which IDs are already part of state<br>

<br>

### 267

Which of the following is not considered a safe way to inject sensitive values into a Terraform Cloud workspace?<br>

A. Edit the state file directly just before running terraform apply<br>
B. Set the variable value on the command line with the -var flag<br>
C. Write the value to a file and specify the file with the -var-file flag<br>

<br>

### 268

If you update the version constraint in your Terraform configuration, Terraform will update your lock file the next time you run terraform init.<br>

A. True<br>
B. False<br>

<br>

### 269

You must initialize your working directory before running terraform validate.<br>

A. True<br>
B. False<br>

<br>

### 270

If you manually destroy infrastructure, what is the best practice reflecting this change in Terraform?<br>

A. Manually update the state fire<br>
B. Remove the resource definition from your file and run terraform apply -refresh-only<br>
C. Run terraform import<br>
D. It will happen automatically<br>

<br>

### 271

You created infrastructure outside of the Terraform workflow that you now want to manage using Terraform. Which command brings the infrastructure into Terraform state?<br>

A. terraform init<br>
B. terraform get<br>
C. terraform refresh<br>
D. terraform import<br>

<br>

### 272

When using Terraform to deploy resources into Azure, which scenarios are true regarding state files? (Choose two.)<br>

A. When you change a Terraform-managed resource via the Azure Cloud Console, Terraform updates the state file to reflect the change during the next plan or apply<br>
B. Changing resources via the Azure Cloud Console records the change in the current state file<br>
C. When you change a resource via the Azure Cloud Console, Terraform records the changes in a new state file<br>
D. Changing resources via the Azure Cloud Console does not update current state file<br>

<br>

### 273

Which statement describes a goal of infrastructure as code?<br>

A. A pipeline process to test and deliver software<br>
B. Defining a vendor-agnostic API<br>
C. Write once, run anywhere<br>
D. The programmatic configuration of resources<br>

<br>

### 274

terraform validate confirms the syntax of Terraform files.<br>

A. True<br>
B. False<br>

<br>

### 275

Which command adds existing resources into Terraform state?<br>

A. terraform init<br>
B. terraform plan<br>
C. terraform refresh<br>
D. terraform import<br>
E. All of these<br>

<br>

### 276

It is best practice to store secret data in the same version control repository as your Terraform configuration.<br>

A. True<br>
B. False<br>

<br>

### 277

Which of the following commands would you use to access all of the attributes and details of a resource managed by Terraform?<br>

A. terraform state list ‘provider_type.name’<br>
B. terraform state show ‘provider_type.name’<br>
C. terraform get ‘provider_type.name’<br>
D. terraform state list<br>

<br>

### 278

terraform validate confirms that your infrastructure matches the Terraform state file.<br>

A. True<br>
B. False<br>

<br>

### 279

A senior admin accidentally deleted some of your cloud instances. What does Terraform do when you run terraform apply?<br>

A. Build a completely brand new set of infrastructure<br>
B. Tear down the entire workspace infrastructure and rebuild it<br>
C. Rebuild only the instances that were deleted<br>
D. Stop and generate an error message about the missing instances<br>

<br>

### 280

terraform init creates an example main.tf file in the current directory.<br>

A. True<br>
B. False<br>

<br>

### 281

Which argument helps prevent unexpected updates when calling Terraform Registry modules?<br>

A. count<br>
B. source<br>
C. version<br>
D. lifecycle<br>

<br>

### 282

Setting the TF_LOG environment variable to DEBUG causes debug messages to be logged into stdout.<br>

A. True<br>
B. False<br>

<br>

### 283

How would you output returned values from a child module in the Terraform CLI output?<br>

A. Declare the output in the root configuration<br>
B. Declare the output in the child module<br>
C. Declare the output in both the root and child module<br>
D. None of the above<br>

<br>

### 284

What is the Terraform resource name of the following resource block?<br>
```
resource "azurerm_resource_group" "dev" {
  name = "test"
  location = "westus"
}
```

A. azurerm_resource_group<br>
B. azurerm<br>
C. test<br>
D. dev<br>

<br>

### 285

When do you need to explicitly execute terraform refresh-only?<br>

A. Before every terraform plan<br>
B. Before every terraform apply<br>
C. Before every terraform import<br>
D. None of the above<br>

<br>

### 286

How is the Terraform cloud integration differ from other state backends such as S3, Consul, etc.?<br>

A. It can execute Terraform runs on dedicated infrastructure in Terraform Cloud<br>
B. It doesn't show the output of a terraform apply locally<br>
C. It is only available to paying customers<br>
D. All of the above<br>

<br>

### 287

Which of the following are advantages of using infrastructure as code (IaC) instead of provisioning with a graphical user interface (GUI)? (Choose two.)<br>

A. Secures your credentials<br>
B. Lets your version, reuse, and share infrastructure configuration<br>
C. Provisions the same resources at a lower cost<br>
D. Reduces risk of operator error<br>
E. Prevents manual modifications to your resources<br>

<br>

### 288

One cloud configuration always maps to a single remote workspace.<br>

A. True<br>
B. False<br>

<br>

### 289

Multiple team members are collaborating on infrastructure using Terraform and want to format their Terraform code following standard Terraform-style convention.<br>

How could they automatically ensure the code satisfies conventions?<br>

A. Replace all tabs with spaces<br>
B. Terraform automatically formats configuration on terraform apply<br>
C. Run terraform validate prior to executing terraform plan or terraform apply<br>
D. Use terraform fmt<br>

<br>

### 290

Which backend does the Terraform CLI use by default?<br>

A. Depends on the cloud provider configured<br>
B. Remote<br>
C. Terraform Cloud<br>
D. Local<br>
E. HTTP<br>

<br>

### 291

The Terraform CLI will print output values from a child module after running terraform apply.<br>

A. True<br>
B. False<br>

<br>

### 292

What does terraform refresh-only modify?<br>

A. Your cloud infrastructure<br>
B. Your Terraform plan<br>
C. Your Terraform configuration<br>
D. Your state file<br>

<br>

### 293

What does terraform import do?<br>

A. Imports existing resources into the state file<br>
B. Imports all infrastructure from a given cloud provider<br>
C. Imports a new Terraform module<br>
D. Imports clean copies of tainted resources<br>
E. None of the above<br>

<br>

### 294

Which of the following is the correct way to pass the value in the variable num_servers into a module with the input server?<br>

A. servers = var(num_servers)<br>
B. $(var.num_servers)<br>
C. servers = num_servers<br>
D. servers = var.num_servers<br>

<br>

### 295

A developer on your team is going to tear down an existing deployment managed by Terraform and deploy a new one. However, there is a server resource named aws_instance.ubuntu[1] they would like to keep. What command should they use to tell Terraform to stop managing that specific resource?<br>

A. terraform destroy aws_instance.ubuntu[l]<br>
B. terraform apply rm aws_instance.ubuntu[l]<br>
C. terraform state rm aws_instance.ubuntu[l]<br>
D. terraform plan rm aws_instance.ubuntu[l]<br>

<br>

### 296

Before you can use a remote backend, you must first execute terraform init.<br>

A. True<br>
B. False<br>

<br>

### 297

What does running a terraform plan do?<br>

A. Compares your Terraform code and local state file to the remote state file in a cloud provider and determines if any changes need to be made<br>
B. Imports all of your existing cloud provider resources to the state file<br>
C. Installs all providers and modules referenced by configuration<br>
D. Compares the state file to your Terraform code and determines if any changes need to be made<br>

<br>

### 298

Which of the following statements about Terraform modules is not true?<br>

A. Modules must be publicly accessible<br>
B. You can call the same module multiple times<br>
C. A module is a container for one or more resources<br>
D. Modules can call other modules<br>

<br>

### 299

How can a ticket-based system slow down infrastructure provisioning and limit the ability to scale? (Choose two.)<br>

A. End-users have to request infrastructure changes<br>
B. Ticket based systems generate a full audit trail of the request and fulfillment process<br>
C. Users can access a catalog of approved resources from drop down lists m a request form<br>
D. The more resources your organization needs, the more tickets your infrastructure team has to process<br>

<br>

### 300

How do you specify a module's version when publishing it to the public Terraform Module Registry?<br>

A. Configure it in the module's Terraform code<br>
B. Mention it on the module s configuration page on the Terraform Module Registry<br>
C. The Terraform Module Registry does not support versioning modules<br>
D. Tag a release in the associated repo<br>

<br>

### 301

What Terraform command always causes a state file to be updated with changes that might have been made outside of Terraform?<br>

A. terraform plan -refresh-only<br>
B. terraform show -json<br>
C. terraform apply -lock-false<br>
D. terraform plan -target-state<br>

<br>

### 302

Which command must you first run before performing further Terraform operations in a working directory?<br>

A. terraform plan<br>
B. terraform workspace<br>
C. terraform init<br>
D. terraform import<br>

<br>

### 303

Which command lets you experiment with Terraform expressions?<br>

A. terraform console<br>
B. terraform validate<br>
C. terraform env<br>
D. terraform test<br>

<br>

### 304

What kind of configuration block will create an infrastructure object with settings specified within the block?<br>

A. provider<br>
B. state<br>
C. data<br>
D. resource<br>

<br>

### 305

When do changes invoked by terraform apply take effect?<br>

A. After Terraform has updated the state file<br>
B. Once the resource provider has fulfilled the request<br>
C. Immediately<br>
D. None of the above are correct<br>

<br>

### 306

What is the workflow for deploying new infrastructure with Terraform?<br>

A. Write Terraform configuration, run terraform init to initialize the working directory or workspace, and run terraform apply<br>
B. Write Terraform configuration, run terraform show to view proposed changes, and terraform apply to create new infrastructure<br>
C. Write Terraform configuration, run terraform apply to create infrastructure, use terraform validate to confirm Terraform deployed resources correctly<br>
D. Write Terraform configuration, run terraform plan to initialize the working directory or workspace, and terraform apply to create the infrastructure<br>

<br>

### 307

Which of these are features of Terraform Cloud? (Choose two.)<br>

A. Remote state storage<br>
B. A web-based user interface (UI)<br>
C. Automatic backups<br>
D. Automated infrastructure deployment visualization<br>

<br>

### 308

Which option can not keep secrets out of Terraform configuration files?<br>

A. A shared credential file<br>
B. Mark the variable as sensitive<br>
C. Environment Variables<br>
D. A -var flag<br>

<br>

### 309

Which of the following is not true of Terraform providers?<br>

A. An individual person can write a Terraform Provider<br>
B. A community of users can maintain a provider<br>
C. HashiCorp maintains some providers<br>
D. Cloud providers and infrastructure vendors can write, maintain, or collaborate on Terraform providers<br>
E. None of the above<br>

<br>

### 310

Which Terraform command checks that your configuration syntax is correct?<br>

A. terraform fmt<br>
B. terraform validate<br>
C. terraform init<br>
D. terraform show<br>

<br>

### 311

terraform validate uses provider APIs to verify your infrastructure settings.<br>

A. True<br>
B. False<br>

<br>

### 312

You add a new provider to your configuration and immediately run terraform apply in the CLI using the local backend. Why does the apply fail?<br>

A. Terraform needs you to format your code according to best practices first<br>
B. Terraform requires you to manually run terraform plan first<br>
C. The Terraform CLI needs you to log into Terraform Cloud first<br>
D. Terraform needs to install the necessary plugins first<br>

<br>

### 313

Which of these statements about Terraform Cloud workspaces is false?<br>

A. They can securely store cloud credentials<br>
B. They have role-based access controls<br>
C. You must use the CLI to switch between workspaces<br>
D. Plans and applies can be triggered via version control system integrations<br>

<br>

### 314

What value does the Terraform Cloud private registry provide over the public Terraform Module Registry?<br>

A. The ability to restrict modules to members of Terraform Cloud or Enterprise organizations<br>
B. The ability to share modules publicly with any user of Terraform<br>
C. The ability to tag modules by version or release<br>
D. The ability to share modules with public Terraform users and members of Terraform Cloud Organizations<br>

<br>

### 315

Terraform providers are part of the Terraform core binary.<br>

A. True<br>
B. False<br>

<br>

### 316

Which of the following is not a benefit of adopting infrastructure as code?<br>

A. Reusability of code<br>
B. Automation<br>
C. Graphical User Interface<br>
D. Versioning<br>

<br>

### 317

Where does the Terraform local backend store its state?<br>

A. In the terraform.tfstate file<br>
B. In the .terraform directory<br>
C. In the terraform.tfstate directory<br>
D. In the .terraform.lock.hcl file<br>

<br>

### 318

Which of these is true about Terraform's plugin-based architecture?<br>

A. Terraform can only source providers from the internet<br>
B. You can create a provider for your API if none exists<br>
C. Every provider in a configuration has its own state file for its resources<br>
D. All providers are part of the Terraform core binary<br>

<br>

### 319

Your risk management organization requires that new AWS S3 buckets must be private and encrypted at rest. How can Terraform Cloud automatically and proactively enforce this security control?<br>

A. Auditing cloud storage buckets with a vulnerability scanning tool<br>
B. With a Sentinel policy, which runs before every apply<br>
C. With an S3 module with proper settings for buckets<br>
D. By adding variables to each Terraform Cloud workspace to ensure these settings are always enabled<br>

<br>

### 320

If you don't use the local backend, where does Terraform save resource state?<br>

A. In the remote backend or Terraform Cloud<br>
B. On the disk<br>
C. In memory<br>
D. In an environment variable<br>

<br>

### 321

You are writing a child Terraform module that provisions an AWS instance. You want to reference the IP address returned by the child module in the root configuration. You name the instance resource "main".<br>

Which of these is the correct way to define the output value?<br>

A.
```
output "instance_ip_addr" {
  value = aws_instance.main.private_ip
}
```
B. 
```
output "aws_instance.instance_ip_addr" {
  value = "${main.private_ip}
}
```
C.
```
ouput "instance_ip_addr" {
  return aws_instance.main.private_ip
}
```
D.
```
output "aws_instance.instance_ip_addr" {
  return aws_instance.main.private_ip
}
```

<br>

### 322

When does Sentinel enforce policy logic during a Terraform Cloud run?<br>

A. Before the plan phase<br>
B. During the plan phase<br>
C. Before the apply phase<br>
D. After the apply phase<br>

<br>

### 323

What is terraform refresh-only intended to detect?<br>

A. Empty state files<br>
B. Corrupt state files<br>
C. Terraform configuration code changes<br>
D. State file drift<br>

<br>

### 324

You should run terraform fmt to rewrite all Terraform configurations within the current working directory to conform to Terraform-style conventions.<br>

A. True<br>
B. False<br>

<br>

### 325

Why would you use the -replace flag for terraform apply?<br>

A. You want to force Terraform to destroy a resource on the next apply<br>
B. You want Terraform to ignore a resource on the next apply<br>
C. You want to force Terraform to destroy and recreate a resource on the next apply<br>
D. You want Terraform to destroy all the infrastructure in your workspace<br>
