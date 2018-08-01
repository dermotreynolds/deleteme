---
layout: post
title: "Azure DevOps: #7 Terraform deployment via command line."
date: 2017-05-12
---

When we run terraform from VSTS we need to ensure that we maintain the state file - and its backup - in a central location.

terraform supports storing state in blob storage.

- To enable state to be persisted to blob we need to add a provider block to main file

        main.tf

        terraform {
           backend "azurerm" {
             storage_account_name = "statefile01012"
             container_name       = "statefile01012"
             key                  = "prod.terraform.tfstate"
           }
        }

- We can then push this to github

For consistency lets push it to the GitHub repository TestWebTerraform.

- Create a new blank release - we will add some steps later

![](/images/New-IaC-Release-01.png)

- Specify that it will run on our newly created Azure-Hosted-Agents

![](/images/New-IaC-Release-02.png)

- Add a new Terraform Task - you may need to add this to your VSTS.

![](/images/New-IaC-Release-03.png)

- Configure this task as our terraform init.

You will note that we are passing a parameter into init.  This is set via an environment variable and is used to allow us to connect to our blob storage.

The parameters are:
init -backend-config="access_key=$(v_access_key)"

![](/images/New-IaC-Release-04.png)

- Create another task as our terraform plan

![](/images/New-IaC-Release-05.png)

- Create another task as our terraform apply

![](/images/New-IaC-Release-06.png)

- Lets set that variable

![](/images/New-IaC-Release-07.png)

- Lets attach the GitHub repo

![](/images/New-IaC-Release-08.png)


Import-Module AzureRM