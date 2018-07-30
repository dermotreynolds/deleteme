---
layout: post
title: "Basic CI/CD on Azure"
date: 2017-03-28
---

The purpose of this series is to walk through how to create a CI/CD pipeline using:
- Visual Studio
- Visual Studio Team Services
- Azure
- Terraform

Before we get started you need to install some software and create some accounts:
- Install Visual Studio Community Edition
 __[Visual Studio](https://visualstudio.microsoft.com/vs/community/)__
- Create a free account on Visual Studio Team Services
 __[VSTS](https://visualstudio.microsoft.com/team-services/)__
- Create a free account on Azure 
 __[Azure](https://azure.microsoft.com/en-us/)__
- Create a free account on GitHub
 __[GITHUB](https://github.com/)__
- Download Terraform
 __[Terraform](https://www.terraform.io/downloads.html)__

As a consistent naming convention we are going to call:

| Element | Name |
| ------ | ----------- |
| Resource Group   |TestWebAppRG |
| App Service   |TestWebApp0101 |

__Step 1 Create GitHub Reponsitory__

![Minion](/images/Create-GitHub-Repo-01.png)


