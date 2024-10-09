
# Terraform - Simulado 6

### 326

You can configure Terraform to log to a file using the TF_LOG environment variable.<br>

A. True<br>
**B**. False<br>

<br>

### 327

When does Terraform create the .terraform.lock.hcl file?<br>

A. After your first terraform plan<br>
**B**. After your first terraform apply<br>
C. After your first terraform init<br>
D. Whenever you enable state locking<br>

<br>

### 328

You have been working in a Cloud provider account that is shared with other team members. You previously used Terraform to create a load balancer that is listening on port 80. After some application changes, you updated the Terraform code to change the port to 443.<br>

You run terraform plan and see that the execution plan shows the port changing from 80 to 443 like you intended, and step away to grab some coffee.<br>

In the meantime, another team member manually changes the load balancer port to 443 through the Cloud provider console before you get back to your desk.<br>

What will happen when you terraform apply upon returning to your desk?<br>

A. Terraform will fail with an error because the state file is no longer accurate.<br>
B. Terraform will change the load balancer port to 80, and then change it back to 443.<br>
C. Terraform will not make any changes to the Load Balancer and will update the state file to reflect any changes made.<br>
D. Terraform will recreate the load balancer.<br>

<br>

### 329

Which of the following is not an action performed by terraform init?<br>

A. Create template configuration files<br>
B. Initialize a configured backend<br>
C. Retrieve the source code for all referenced modules<br>
D. Load required provider plugins<br>

<br>

### 330

In a HCP Terraform/Terraform Cloud workspace linked to a version control repository, speculative plan runs start automatically when you merge or commit change to version control.<br>

A. True<br>
B. False<br>

<br>

### 331

Before you can use a new backend or HCP Terraform/Terraform Cloud integration, you must first execute terraform init.<br>

A. True<br>
B. False<br>

<br>

### 332
```
resource "googlt_compute_instance" "main" {
  name = "test"
}
```
A resource block is shown in the Exhibit space of this page. What is the Terraform resource name of the resource block?<br>

A. test<br>
B. main<br>
C. google<br>
D. compute_instance<br>

<br>

### 333

A module block is shown in the Exhibit space of this page.<br>
```
module "consul" {
  source = "hashicorp/consul/aws"
}
```
When you use a module block to reference a module from the Terraform Registry such as the one in the example, how do you specify version 1.0.0 of the module?<br>

A. You cannot. Modules stored on the public Terraform Registry do not support versioning.<br>
B. Add a version = “1.0.0” attribute to the module block.<br>
C. Nothing. Modules stored on the public Terraform module Registry always default to version 1.0.0.<br>
D. Append ?ref=v1.0.0 argument to the source path.<br>

<br>

### 334

Which syntax check errors when you run terraform validate?<br>

A. The code contains tabs for indentation instead of spaces.<br>
B. There is a missing value for a variable.<br>
C. The state file does not match the current infrastructure.<br>
D. None of the above.<br>

<br>

### 335

Terraform encrypts sensitive values stored in your state file.<br>

A. True<br>
B. False<br>

<br>

### 336

When should you run terraform init?<br>

A. Every time you run terraform apply<br>
B. After you run terraform plan for the first time in a new Terraform project and before you run terraform apply<br>
C. After you start coding a new Terraform project and before you run terraform plan for the first time<br>
D. Before you start coding a new Terraform project<br>

<br>

### 337

You are making changes to existing Terraform code to add some new infrastructure.<br>

When is the best time to run terraform validate?<br>

A. After you run terraform plan so you can validate that your state file is consistent with your infrastructure<br>
B. Before you run terraform plan so you can validate your code syntax<br>
C. Before you run terraform apply so you can validate your infrastructure<br>
D. After you run terraform apply so you can validate your provider credentials<br>

<br>

### 338

Which of these commands makes your code more human readable?<br>

A. terraform validate<br>
B. terraform output<br>
C. terraform show<br>
D. terraform fmt<br>

<br>

### 339

Terraform configuration can only import from the public registry.<br>

A. True<br>
B. False<br>

<br>

### 340

What is the Terraform resource name of the following resource block?<br>
```
mainresource "google_compute_instance" "main" {
  name = "test"
}
```
A. test<br>
B. google<br>
C. main<br>
D. compute_instance<br>

<br>

### 341

terraform init retrieves and caches the configuration for all remote modules.<br>

A. True<br>
B. False<br>

<br>

### 342

Terraform configuration can only call modules from the public registry.<br>

A. True<br>
B. False<br>

<br>

### 343
```
resource "kubernetes_namespace" "example" {
  name = "test"
}
```
A resource block is shown in the Exhibit section of this page. How would you reference the attribute name of this resource in HCL?<br>

A. data.kubernetes_namespace.name<br>
B. resource.kubernetes_namespace.example.name<br>
C. kubernetes_namespace.test.name<br>
D. kubernetes_namespace.example.name<br>

<br>

### 344

You want to use API tokens and other secrets within your team’s Terraform workspaces. Where does HashiCorp recommend you store these sensitive values? (Choose three.)<br>

A. In a terraform.tfvars file, securely managed and shared with your team.<br>
B. In HashiCorp Vault.<br>
C. In a terraform.tfvars file, checked into your version control system.<br>
D. In a plaintext document on a shared drive.<br>
E. In an HCP Terraform/Terraform Cloud variable, with the sensitive option checked.<br>

<br>

### 345

What happens when you execute terraform plan?<br>

A. Imports all of your existing cloud provider resources to the state.<br>
B. Installs all providers and modules referenced by configuration.<br>
C. Compares your Terraform code and local state file to the remote state file in a cloud provider and determines if any changes need to be made.<br>
D. Refreshes your state, then compares your state file to your Terraform configuration and creates an execution plan if any changes need to be made.<br>

<br>

### 346

What does terraform destroy do?<br>

A. Destroys the Terraform state file, leaves the infrastructure intact.<br>
B. Destroys all Terraform code files in the current directory, leaves the state file intact.<br>
C. Destroy all infrastructure in the Terraform state file.<br>
D. Destroys all infrastructure in the configured Terraform provider.<br>


