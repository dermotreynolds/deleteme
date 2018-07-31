---
layout: post
title: "Azure DevOps: #7 Terraform deployment via command line."
date: 2017-05-12
---

So far the provisioning of infrastructure was manual through the portal.

There are a number of issues with this:

1. There is no documentation of the state of the infrastructure.

2. There is no repeatability.  Most organisations have multiple environments which are identical to one another apart from scale.  Maintaining through manual means is difficult.

3. There is no repeatable means by which the security posture can be maintained - apart from rigorous manual reviews.

Infrastructure As Code(IaC) is a means by which the intended state of an infrastructure can be codified.

We will first show how this can be achieved through the command line and then do so via Visual Studio Team Services.

-  Create your terraform file

        #Create a resource group to put our resources into
        resource "azurerm_resource_group" "nft_resource_group" {
        name     = "TestWebAppRG"
        location = "West Europe"
        }

        #Create an App Service Plan
        resource "azurerm_app_service_plan" "nft_app_service_plan" {
        name                = "some-app-service-plan"
        location            = "${azurerm_resource_group.nft_resource_group.location}"
        resource_group_name = "${azurerm_resource_group.nft_resource_group.name}"

        sku {
            tier = "Standard"
            size = "S1"
        }
        }

        #Create an App Service
        resource "azurerm_app_service" "nft_app_service" {
        name                = "TestWebApp0101"
        location            = "${azurerm_resource_group.test.location}"
        resource_group_name = "${azurerm_resource_group.test.name}"
        app_service_plan_id = "${azurerm_app_service_plan.test.id}"

        site_config {
            default_documents = [
            "index.html",
            ]
        }
        }

