---
layout: post
title: "Azure DevOps: Visual Studio Team Services Build Agent"
date: 2017-03-28
---

When you sign up for Visual Studio Team Services you are allocated a given amount of build/release hours for free.  After this you will have to either buy more or create your own Build Agent.

- Select Windows based Build Agent for VSTS from the Azure Marketplace
![](/images/New-Windows-Build-Agent-01-01.png)

*I wont walk through creating a VM.  But the significant screen is below.*

- Get hold of your _[Personal Access Token](https://docs.microsoft.com/en-us/vsts/organizations/accounts/use-personal-access-tokens-to-authenticate?view=vsts)_

- Which you can then put into the VSTS Settings.

![](/images/New-Windows-Build-Agent-02.png)