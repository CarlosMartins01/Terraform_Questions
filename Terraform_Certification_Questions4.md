
# Terraform - Simulado 4

### 196

In a Terraform Cloud workspace linked to a version control repository, speculative plan runs start automatically when you merge or commit changes to version control.<br>

**A**. True<br>
B. False<br>

<br>

### 197

You have some Terraform code and a variable definitions file named dev.auto.tfvars that you tested successfully in the dev environment. You want to deploy the same code in the staging environment with a separate variable definition file and a separate state file.<br>

Which two actions should you perform? (Choose two.)<br>

A. Copy the existing terraform.tfstate file and save it as staging.terraform.tfstate<br>
B. Write a new staging.auto.tfvars variable definition file and run Terraform with the var-file=”staging.auto.tfvars” flag<br>
C. Create a new Terraform workspace for staging<br>
D. Create a new Terraform provider for staging<br>
E. Add new Terraform code (*.tf files) for staging in the same directory<br>

<br>

### 198

The ________ determines how Terraform creates, updates, or deletes resources.<br>

A. Terraform configuration<br>
B. Terraform core<br>
C. Terraform provider<br>
D. Terraform provisioner<br>

<br>

### 199

Terraform destroy is the only way to remove infrastructure.<br>

A. True<br>
B. False<br>

<br>

### 200

Which of the following is the correct way to pass the value in the variable num_servers into a module with the input servers in HCL2?<br>

A. servers - var.num_servers<br>
B. servers - num_servers<br>
C. servers - var(num_servers)<br>
D. $(var.num_servers)<br>


<br>

### 201

Which of the fallowing commands would you use to access all of the attributes and details of a resource managed by Terraform?<br>

A. terraform state list<br>
B. terraform state show<br>
C. terraform get<br>
D. terraform state list<br>


<br>

### 202

How would you be able to reference an attribute from the vsphere_datacenter data source for use with the datacenter_id argument within the vsphere_folder resource in the following configuration?<br>
```
data "vsphere_datacenter" "dc" {}

resource "vsphere_folder" "parent" {
  path          = "Production"
  type          = "vm"
  datacenter id = _______________
}
```
A. data.dc.id<br>
B. data.vsphere_datacenter.dc<br>
C. vsphere_datacenter.dc.id<br>
D. data.vsphere_datacenter.dc.id<br>


<br>

### 203

You decide to move a Terraform state file to Amazon S3 from another location. You write the code below into a file called backend.tf.<br>
```
terraform {
  backend "s3" {
    bucket = "my-tf-bucket"
    region = "us-east-1"
  }
}
```
Which command will migrate your current state file to the new S3 remote backend?<br>

A. terraform state<br>
B. terraform init<br>
C. terraform refresh<br>
D. terraform push<br>


<br>

### 204

You want to tag multiple resources with a string that is a combination of a generated random_id and a variable.<br>

How should you use the same value in all these resources without repeating the random_id and variable in each resource?<br>

A. Local values<br>
B. Data source<br>
C. Modules<br>
D. Outputs<br>


<br>

### 205

Which of the following is not a benefit of adopting infrastructure as code?<br>

A. Interpolation<br>
B. Reusability of code<br>
C. Versioning<br>
D. Automation<br>


<br>

### 206

Module version is required to reference a module on the Terraform Module Registry.<br>

A. True<br>
B. False<br>


<br>

### 207

While deploying a virtual machine, the first launch user_data script fails due to race condition with another resource deployed during the same Terraform run.<br>

What is the least disruptive method to correct the issue?<br>

A. Run terraform taint against the virtual machine’s resource name, then terraform apply<br>
B. Restart the virtual machine from the cloud portal<br>
C. Run terraform apply again<br>
D. Run terraform destroy then terraform apply<br>


<br>

### 208

The public Module Registry is free to use.<br>

A. True<br>
B. False<br>


<br>

### 209

Both Terraform Cloud and Terraform Enterprise support policy as code (Sentinel).<br>

A. True<br>
B. False<br>


<br>

### 210

You want to define multiple data disks as nested blocks inside the resource block for a virtual machine.<br>

What Terraform feature would help you define the blocks using the values in a variable?<br>

A. Local values<br>
B. Collection functions<br>
C. Dynamic blocks<br>
D. Count arguments<br>


<br>

### 211

Which of the following module source paths does not specify a remote module?<br>

A. source = “./modules/consul”<br>
B. source = “git@github.com:hashicorp/example.git”<br>
C. source = “github.com/hashicorp/example”<br>
D. source = “hashicorp/consul/aws”<br>


<br>

### 212

You have a list of numbers that represents the number of free CPU cores on each virtual cluster:<br>

numcpus = [ 18, 3, 7, 11, 2 ]<br>

What Terraform function could you use to select the largest number from the list?<br>

A. max(numcpus)<br>
B. ceil(numcpus)<br>
C. top(numcpus)<br>
D. high[numcpus]<br>


<br>

### 213

Variables declared within a module are accessible outside of the module.<br>

A. True<br>
B. False<br>

<br>

### 214

Which of the following is not a valid Terraform variable type?<br>

A. list<br>
B. map<br>
C. array<br>
D. string<br>

<br>

### 215

What is a key benefit of the Terraform state file?<br>

A. A state file can be used to schedule recurring infrastructure tasks<br>
B. A state file represents a source of truth for resources provisioned with a public cloud console<br>
C. A state file represents the desired state expressed by the Terraform code files<br>
D. A state file represents a source of truth for resources provisioned with Terraform<br>

<br>

### 216

Which of these statements about Terraform Enterprise workspaces is false?<br>

A. They can securely store cloud credentials<br>
B. You must use the CLI to switch between workspaces<br>
C. Plans and applies can be triggered via version control system integrations<br>
D. They have role-based access controls<br>

<br>

### 217

Define the purpose of state in Terraform.<br>

A. State is used to map real world resources to your configuration and keep track of metadata<br>
B. State is a method of codifying the dependencies of related resources<br>
C. State is used to enforce resource configurations that relate to compliance policies<br>
D. State is used to store variables and quickly reuse existing code<br>

<br>

### 218

Which backend does the Terraform CLI use by default?<br>

A. API<br>
B. Remote<br>
C. Terraform Cloud<br>
D. Local<br>
E. HTTP<br>

<br>

### 219

Using the terraform state rm command against a resource will destroy it.<br>

A. True<br>
B. False<br>

<br>

### 220

Which method for sharing Terraform configurations keeps them confidential within your organization, supports Terraform’s semantic version constraints, and provides a browsable directory?<br>

A. Generic git repository<br>
B. Terraform Cloud/Terraform Enterprise private module registry<br>
C. Public Terraform Module Registry<br>
D. Subfolder within a workspace<br>

<br>

### 221

You are writing a child Terraform module which provisions an AWS instance. You want to make use of the IP address returned in the root configuration. You name the instance resource “main”.<br>

Which of these is the correct way to define the output value using HCL2?<br>

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
output "instance_ip_addr" {
  value = "${aws_instance.main.private_ip}"
}
```
D.
```
ouput "instance_ip_addr" {
  return aws_instance.main.private_ip
}
```

<br>

### 222

How would you refer to the indexing instance from the below configuration?<br>

```
resource "aws_instance" "web" {
  ...
  for_each = {
    "terraform": "value1",
    "resource" : "value2",
    "indexing" : "value3",
    "example"  : "value4",
  }
}
```

A. aws_instance[“web”][“indexing”]<br>
B. aws_instance.web.indexing<br>
C. aws_instance-web[“indexing”]<br>
D. aws_instance.web[“indexing”]<br>

<br>

### 223

Which feature is not included in Terraform Cloud’s free tier?<br>

A. Workspace<br>
B. Remote state management<br>
C. Audit logging<br>
D. Private module registry<br>

<br>

### 224

When should you run terraform init?<br>

A. After you run terraform apply for the first time in a new Terraform project and before you run terraform plan<br>
B. After you run terraform plan for the first time in a new Terraform project and before you run terraform apply<br>
C. After you start coding a new Terraform project and before you run terraform plan for the first time<br>
D. Before you start coding a new Terraform project<br>

<br>

### 225

Terraform configuration (including any module references) can contain only one Terraform provider type.<br>

A. True<br>
B. Falsev<br>

<br>

### 226

You are making changes to existing Terraform code to add some new infrastructure.<br>

When is the best time to run terraform validate?<br>

A. After you run terraform plan so you can validate that your state file is consistent with your infrastructure<br>
B. Before you run terraform plan so you can validate your code syntax<br>
C. Before you run terraform apply so you can validate your infrastructure changes<br>
D. After you run terraform apply so you can validate that your infrastructure is reflected in your code<br>

<br>

### 227

How does Terraform manage most dependencies between resources?<br>

A. By defining dependencies as modules and including them in a particular order<br>
B. The order that resources appear in Terraform configuration indicates dependencies<br>
C. Using the depends_on parameter<br>
D. Terraform will automatically manage most resource dependencies<br>

<br>

### 228

What does running a terraform plan do?<br>

A. Imports all of your existing cloud provider resources to the state file<br>
B. Compares the state file to your Terraform code and determines if any changes need to be made<br>
C. Imports all of your existing cloud provider resources to your Terraform configuration file<br>
D. Compares your Terraform code and local state file to the remote state file in a cloud provider and determines if any changes need to be made<br>

<br>

### 229

What are some benefits of using Sentinel with Terraform Cloud/Terraform Enterprise? (Choose three.)<br>

A. Policy-as-code can enforce security best practices<br>
B. You can restrict specific configurations on resources like "CIDR=0.0.0.0/0" not allowed<br>
C. You can enforce a list of approved AWS AMIs<br>
D. Sentinel Policies can be written in HashiCorp Configuration Language (HCL)<br>
E. You can check out and check in cloud access keys<br>

<br>

### 230

You want to share Terraform state with your team, store it securely, and provide state locking.<br>

How would you do this? (Choose three.)<br>

A. Using the remote Terraform backend with Terraform Cloud / Terraform Enterprise.<br>
B. Using the local backend.<br>
C. Using the s3 terraform backend. The dynamodb_field option is not needed.<br>
D. Using an s3 terraform backend with an appropriate IAM policy and dynamodb_field option configured.<br>
E. Using the consul Terraform backend.<br>

<br>

### 231

From which of these sources can Terraform import modules?<br>

A. Local path<br>
B. GitHub Repository<br>
C. Terraform Module Registry<br>
D. All of the above<br>

<br>

### 232s

How would you output returned values from a child module?<br>

A. Declare the output in the root configuration<br>
B. Declare the output in the child module<br>
C. Declare the output in both the root and child module<br>
D. None of the above<br>

<br>

### 233

You have decided to create a new Terraform workspace to deploy a development environment.<br>

What is different about this workspace?<br>

A. It has its own state file<br>
B. It pulls in a different terraform.tfvars file<br>
C. It uses a different branch of code<br>
D. It uses a different backend<br>

<br>

### 234

Any user can publish modules to the public Terraform Module Registry.<br>

A. True<br>
B. False<br>

<br>

### 235

Which of these commands makes your code more human readable?<br>

A. terraform validate<br>
B. terraform output<br>
C. terraform plan<br>
D. terraform fmt<br>

<br>

### 236

Infrastructure as Code (IaC) can be stored in a version control system along with application code.<br>

A. True<br>
B. False<br>

<br>

### 237

Select the command that doesn’t cause Terraform to refresh its state.<br>

A. terraform apply<br>
B. terraform destroy<br>
C. terraform plan<br>
D. terraform state list<br>

<br>

### 238

Sentinel policy-as-code is available in Terraform Enterprise.<br>

A. True<br>
B. False<br>

<br>

### 239

Before you can use Terraform’s remote backend, you must first execute terraform init.<br>

A. True<br>
B. False<br>

<br>

### 240

Which two steps are required to provision new infrastructure in the Terraform workflow? (Choose two.)<br>

A. Plan<br>
B. Apply<br>
C. Import<br>
D. Init<br>
E. Validate<br>

<br>

### 241

You are working on some new application features and you want to spin up a copy of your production deployment to perform some quick tests. In order to avoid having to configure a new state backend, what open source Terraform feature would allow you create multiple states but still be associated with your current code?<br>

A. Terraform data sources<br>
B. Terraform local values<br>
C. Terraform modules<br>
D. Terraform workspaces<br>
E. None of the above<br>

<br>

### 242

Which provisioner invokes a process on the machine running Terraform?<br>

A. remote-exec<br>
B. file<br>
C. local-exec<br>
D. null-exec<br>

<br>

### 243

____________ backends support state locking.<br>

A. Some<br>
B. No<br>
C. Only local<br>
D. All<br>

<br>

### 244

Which of the following methods, used to provision resources into a public cloud, demonstrates the concept of infrastructure as code?<br>

A. curl commands manually run from a terminal<br>
B. A sequence of REST requests you pass to a public cloud API endpoint<br>
C. A script that contains a series of public cloud CLI commands<br>
D. A series of commands you enter into a public cloud console<br>

<br>

### 245

Which of the following should you put into the required_providers block?<br>

A. version >= 3.1<br>
B. version = “>= 3.1”<br>
C. version ~> 3.1<br>

<br>

### 246

When should you write Terraform configuration files for existing infrastructure that you want to start managing with Terraform?<br>

A. Before you run terraform import<br>
B. You can import infrastructure without corresponding Terraform code<br>
C. Terraform will generate the corresponding configuration files for you<br>
D. After you run terraform import<br>

<br>

### 247

Which command should you run to check if all code in a Terraform configuration that references multiple modules is properly formatted without making changes?<br>

A. terraform fmt -write=false<br>
B. terraform fmt -list -recursive<br>
C. terraform fmt -check -recursive<br>
D. terraform fmt -check<br>

<br>

### 248

What features stops multiple users from operating on the Terraform state at the same time?<br>

A. Provider constraints<br>
B. Remote backends<br>
C. State locking<br>
D. Version control<br>

<br>

### 249

You are creating a reusable Terraform configuration and want to include a billing_dept tag so your Finance team can track team-specific spending on resources. Which of the following billing_dept variable declarations will allow you to do this?<br>

A.
```
variable "billing_dept" {
  optional = true
}
```
B.
```
variable "billing_dept" {
  type = optional(string_)
}
```
C.
```
variable "billing_dept" {
  default = ""
}
```
D.
```
variable "billing_dept" {
  type = default
}
```

<br>

### 250

Which of these are secure options for storing secrets for connecting to a Terraform remote backend? (Choose two.)<br>

A. Inside the backend block within the Terraform configuration<br>
B. Defined in Environment variables<br>
C. Defined in a connection configuration outside of Terraform<br>
D. A variable file<br>

<br>

### 251

You want to define a single input variable to capture configuration values for a server. The values must represent memory as a number, and the server name as a string.<br>

Which variable type could you use for this input?<br>

A. List<br>
B. Object<br>
C. Map<br>
D. Terraform does not support complex input variables of different types<br>

<br>

### 252

What does Terraform not reference when running a terraform apply -refresh-only?<br>

A. Credentials<br>
B. State file<br>
C. Terraform resource definitions in configuration files<br>
D. Cloud provider<br>

<br>

### 253

Multiple team members are collaborating on infrastructure using Terraform and want to format their Terraform code following standard Terraform-style convention. How could they automatically ensure the code satisfies conventions?<br>

A. Run the terraform fmt command during the code linting phase of your CI/CD process<br>
B. Manually apply two spaces indentation and align equal sign "=" characters in every Terraform file (*.tf)<br>
C. Run the terraform validate command prior to executing terraform plan or terraform apply<br>

<br>

### 254

When using a remote backend or Terraform Cloud integration, where does Terraform save resource state?<br>

A. On the disk<br>
B. In memory<br>
C. In an environment variable<br>
D. In the remote backend or Terraform Cloud<br>

<br>

### 255

In Terraform HCL, an object type of object({ name=string, age=number }) would match this value:<br>

A.
```
{
  name = "John"
  age  = fifty two
}
```
B.
```
{
  name = "John"
  age  = 52
}
```
C.
```
{
  name = John
  age  = fifty two
}
```
D.
```
{
  name = John
  age  = 52
}

```

<br>

### 256

You add a new resource to an existing Terraform configuration, but do not update the version constraint in the configuration. The existing and new resources use the same provider. The working directory contains a .terraform-lock.hcl file.<br>

How will Terraform choose which version of the provider to use?<br>

A. Terraform will use the latest version of the provider for the new resource and the version recorded in the lock file to manage existing resources<br>
B. Terraform will use the version recorded in your lock file<br>
C. Terraform will check your state file to determine the provider version to use<br>
D. Terraform will use the latest version of the provider available at the time you provision your new resource<br>

<br>

### 257

You must use different Terraform commands depending on the cloud provider you use.<br>

A. True<br>
B. False<br>

<br>

### 258

Define the purpose of state in Terraform.<br>

A. State stores variables and lets you quickly reuse existing code<br>
B. State lets you enforce resource configurations that relate to compliance policies<br>
C. State codifies the dependencies of related resources<br>
D. State maps real world resources to your configuration and keeps track of metadata<br>

<br>

### 259

Which of these actions will prevent two Terraform runs from changing the same state file at the same time?<br>

A. Refresh the state after running Terraform<br>
B. Delete the state before running Terraform<br>
C. Configure state locking for your state backend<br>
D. Run Terraform with parallelism set to 1<br>

<br>

### 260

While attempting to deploy resources into your cloud provider using Terraform, you begin to see some odd behavior and experience slow responses. In order to troubleshoot you decide to turn on Terraform debugging. Which environment variables must be configured to make Terraform’s logging more verbose?<br>

A. TF_LOG_PATH<br>
B. TF_VAR_log_level<br>
C. TF_LOG<br>
D. TF_VAR_log_path<br>

<br>
