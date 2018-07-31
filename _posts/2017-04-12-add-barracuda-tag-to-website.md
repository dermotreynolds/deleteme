---
layout: post
title: "Azure Security: #7 Adding Barracuda scan against Azure App Service"
date: 2017-03-28
---


- Enabling Barracuda Vulnerability Manager

![](/images/New-Vulerability-Scan-01.png)

- The report shows the vulnerabilities.  

![](/images/New-Vulerability-Scan-02.png)

- Vulnerabilities including SSL certs for Azure App Service being Untrusted!
      The following problems were found with the certificate chain supplied by the server: 

      Unable to get issuer cert locally
      Subject: /ST=Washington/C=US/OU=Microsoft IT/CN=Microsoft IT TLS CA 4/L=Redmond/O=Microsoft Corporation
      Issuer: /CN=Baltimore CyberTrust Root/O=Baltimore/C=IE/OU=CyberTrust
      Certificate depth: 1