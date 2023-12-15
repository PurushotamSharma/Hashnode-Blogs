---
title: "TerraWeek Day 2 Challange"
datePublished: Tue Jun 06 2023 09:41:09 GMT+0000 (Coordinated Universal Time)
cuid: clik3cekj000m09l27yqp0rr6
slug: terraweek-day-2-challange
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1686044497603/0b205afa-d8de-498a-9abe-f761c0aa94b9.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1686044421869/c86ce87b-47f7-474d-bfba-0d74748db255.png
tags: trends, devops, infrastructure, terraform, trainwithshubham

---

# **📍**Introduction

I'm thrilled to say that I've signed up for the TWS TerraWeek Challenge! I'm eager to begin this exciting journey into the world of infrastructure automation because it looks to be a fantastic experience.

I'll be taking part in the Terraform Challenge Programme over the next week, which is meant to test the extent of my abilities. This challenge has much to offer everyone, whether you're an expert player or just putting your feet into the world of Terraform. We'll examine the fundamentals of IaC in this article, discover why Terraform is a popular option, discover its essential ideas and elements, and set up Terraform on our local system to produce our first configuration.

## **📍** HCL

HCL Stand for the HashiCrop Configuration Language is a unique configuration language. It was designed to be used with HashiCorp tools, notably Terraform, but HCL has expanded as a more general configuration language. It’s visually similar to JSON with additional data structures and capabilities built-in.

HCL consists of three sub-languages:

* Structural
    
* Expression
    
* Templates
    

### .

# **📍** HCL Blocks, Arguments, and Parameters

HCL blocks, parameters, and arguments are all important concepts in HashiCorp Configuration Language (HCL).

* **Blocks** are used to group together related configuration data. For example, a block could be used to define the properties of a resource, such as its name, type, and attributes.
    
* **Parameters** are variables that can be used to pass values into blocks. Parameters are defined at the top of a block, and their values can be specified either inline or in a separate file.
    
* **Arguments** are values that are passed into blocks or functions. Arguments are specified inline, and they can be either literal values or expressions.
    

The following is an example of an HCL block that defines a resource with two parameters:

**Code snippet**

```bash
resource "aws_instance" "example" {
  ami = "ami-abc123"
  instance_type = parameter.instance_type
  tags = {
    Name = parameter.name
  }
}

parameter "instance_type" {
  type = string
}

parameter "name" {
  type = string
}
```

In this example, the `aws_instance` block defines a resource named `example`. The `ami` and `instance_type` parameters are used to pass values into the block. The `tags` parameter is used to define a map of tags for the resource.

The `parameter` blocks define the types and default values of the parameters. The `type` argument can be used to specify the type of the parameter, such as `string`, `number`, or `list`. The `default` argument can be used to specify a default value for the parameter.

When an HCL file is parsed, the parameters are evaluated and their values are passed into the blocks. The blocks are then executed, and their output is returned.

HCL blocks, parameters, and arguments are a powerful way to define and configure resources. They can be used to create complex configurations that are easy to understand and maintain.

Terraform is an infrastructure as code (IaC) tool that allows you to define and provision infrastructure resources across various cloud providers and services. It provides a wide range of resource types and data sources to interact with the infrastructure and manage its lifecycle. Let's explore the different types of resources and data sources available in Terraform.

## **📍**Resource Types

* **Compute Resources**: These resources are used to provision compute instances, virtual machines, or containers. Examples include `aws_instance`, `azure_virtual_machine`, or `google_compute_instance`.
    
* **Networking Resources**: These resources are used to manage networking components such as virtual networks, subnets, load balancers, and firewall rules. Examples include `aws_vpc`, `azure_subnet`, or `google_compute_network`.
    
* **Storage Resources**: These resources handle persistent storage like disks, object storage, or databases. Examples include `aws_ebs_volume`, `azure_storage_account`, or `google_sql_database`.
    
* **Security Resources**: These resources help manage security-related components like IAM roles, security groups, or access control policies. Examples include `aws_iam_role`, `azure_security_group`, or `google_project_iam_binding`.
    
* **Monitoring Resources**: These resources facilitate monitoring and logging of infrastructure and applications. Examples include `aws_cloudwatch_metric_alarm`, `azure_log_analytics_workspace`, or `google_logging_metric`.
    
* **Container Resources**: These resources are specific to container orchestration platforms and manage containers and related resources. Examples include `aws_ecs_task_definition`, `azure_container_registry`, or `google_container_cluster`.
    
* **Provider-Specific Resources**: Each cloud provider often has its own specific resources, such as `aws_lambda_function`, `azure_cosmosdb_account`, or `google_bigquery_dataset`.
    

## **📍**Data Sources

Data sources allow you to fetch information from external systems or existing infrastructure for use in your Terraform configuration. Some common data sources are:

* **Cloud Provider Metadata**: These data sources provide information about the cloud provider account, regions, availability zones, or current user details. Examples include `aws_region`, `azure_subscription`, or `google_project`.
    
* **Network Information**: These data sources allow you to fetch information about networks, subnets, or IP addresses. Examples include `aws_subnet_ids`, `azure_virtual_network`, or `google_compute_addresses`.
    
* **AMI and Image Information**: These data sources provide information about machine images, such as the latest available AMI for a specific operating system or region. Examples include `aws_ami`, `azure_virtual_machine_image`, or `google_compute_image`.
    
* **External Data Sources**: Terraform also supports fetching data from external systems using APIs or other methods. Examples include `external`, `http`, or `templatefile`.
    

These are just a few examples of the resource types and data sources available in Terraform. The actual availability and naming of resources and data sources may vary depending on the cloud provider and the specific Terraform provider being used. You can refer to the documentation of the respective cloud providers and the Terraform providers for a comprehensive list of available resources and data sources.

## **📍**Understand variables, data types, and expressions in HCL

In HashiCorp Configuration Language (HCL), which is used by Terraform, variables, data types, and expressions play important roles in defining and manipulating configurations. Let's explore each of these concepts:

1. **Variables:** Variables in HCL allow you to parameterize your configuration, making it more flexible and reusable. Variables can be defined and assigned values within a configuration file or provided externally via input files, command-line arguments, or environment variables. Some key points about variables in HCL are:
    
    * Variables are declared using the `variable` block within a Terraform configuration file (usually with a `.tf` extension).
        
    * Variables can have default values or be defined as required.
        
    * Variables can be of different types, such as strings, numbers, lists, maps, or boolean values.
        
    * You can reference variables using interpolation syntax `var.<variable_name>` within your configuration.
        
2. Data Types: HCL supports various data types that you can use to define and manipulate values within your configurations. Some common data types in HCL include:
    
    * **String**: Represents a sequence of characters. Example: `"Hello, World!"`.
        
    * **Number**: Represents numeric values, including integers and floating-point numbers. Example: `42`, `3.14`.
        
    * **Boolean**: Represents either `true` or `false` values.
        
    * **List**: Represents an ordered collection of values. Example: `["item1", "item2", "item3"]`.
        
    * **Map**: Represents a set of key-value pairs. Example: `{"key1" = "value1", "key2" = "value2"}`.
        
    * **Object**: Represents a complex structure with nested attributes. Example: `{ attribute1 = "value1", attribute2 = "value2" }`.
        
3. Expressions: Expressions in HCL allow you to perform computations, transformations, and evaluations within your configurations. They can be used to dynamically generate values or make decisions based on conditions. Some key aspects of expressions in HCL are:
    
    * Expressions can be used within resource blocks, variable assignments, or function arguments.
        
    * Expressions support operators for arithmetic, string manipulation, logical operations, and comparisons.
        
    * You can use functions provided by Terraform or custom functions to perform more complex operations.
        
    * Interpolation syntax `${...}` is used to embed expressions within your configuration.
        
    * Conditional expressions, like the `if` and `for` constructs, allow you to control the flow of your configurations based on conditions.
        

By leveraging variables, data types, and expressions in HCL, you can create dynamic and reusable configurations in Terraform. They provide flexibility and allow you to handle different use cases by parameterizing your infrastructure code.

### Create a [variable.tf](http://variables.tf) file and define a variable:

Here we created a [`variables.tf`](http://variables.tf) file where we define a variable named `region` of type string with a default value of "us-west-2":

```bash
variable "region" {
  type    = string
  default = "us-west-2"
}
```

Let's use the variable `region` in a [`main.tf`](http://main.tf) file to create a `local_file` resource.

```bash
variable "region" {
  type    = string
  default = "us-west-2"
}

resource "local_file" "example_file" {
  filename = "variable.txt"
  content  = "This file was created in the ${var.region} region."
}
```

In this task , we first declare the `region` variable with its type and default value in the [`variables.tf`](http://variables.tf) file. Then, in the [`main.tf`](http://main.tf) file, we use the `local_file` resource to create a file named `variable.txt`. The content of the file includes the value of the `region` variable interpolated using `${var.region}`.

When you run `terraform apply`, it will create a file named `variable.txt` with the content "This file was created in the us-west-2 region." You can modify the value of the `region` variable in the [`variables.tf`](http://variables.tf) file or provide a new value via command-line flags, environment variables, or input files to change the region dynamically.

Remember to run `terraform init` to initialize the Terraform working directory before applying this configuration.

## **📍**HCL Syntax

The syntax of Terraform configurations is called HashiCorp Configuration Language (HCL). It is meant to strike a balance between human-readable and editable as well as being machine-friendly. For machine-friendliness, Terraform can also read JSON configurations. For general Terraform configurations, however, we recommend using the HCL Terraform syntax.

&lt;block&gt; &lt;arguments&gt; {

}

blocks- resources, provider, terraform..

### **📍Conclusion**

In this blog we had understand the what is HCL and How to write a Hcl and what are variables and how to define the variables and what are the data type and what are the resources and many more. If you like the blog then like and comment any suggestion if you have.

Happy Learning......