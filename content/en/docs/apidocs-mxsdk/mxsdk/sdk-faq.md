---
title: "SDK FAQ and Troubleshooting"
url: /apidocs-mxsdk/mxsdk/sdk-faq/
category: "Mendix Platform SDK"
weight: 3
---

## 1 General Questions

### 1.1 Which Mendix Versions Are Supported?

Mendix 6.0.0 and above.

### 1.2 Where Does the Model API Run?

The Model API service is hosted in the European Union.

### 1.3 How Long Do Online Working Copies Exist?

Online working copies are automatically removed 24 hours after they have been created. It is not possible to extend their lifetime - you need to create a new online working copy.

### 1.4 What Are the Limits on App Size?

The initial app *.mpk* file that is uploaded is not allowed to exceed 250 Mb (with the app *.mpk* file and other files combined).

### 1.5 What Are the Limits on Working Copy Size?

The maximum number of files allowed in a working copy is 10,000.

### 1.6 What Apps Can I Access With the Model API?

You can access all apps stored on [Mendix Team Server](/developerportal/general/team-server/). Apps stored elsewhere, for example in your on-premises Git server, cannot be accessed with the model API.

## 2 Common Error Messages

### 2.1 Delta Rejected, Delta Queue Connection Has Closed

This error message is shown when making changes on a model, but the connection to the Online Working Copy on the Model Server has already been closed. This sometimes happens if your script executes a commit too quickly, without waiting until all model updates have been run.

### 2.2 JS Allocation Failed, Process Out of Memory

This can happen when you open a huge model and then load a lot of documents (for example, pages, microflows). You can increase the memory available to your script by running it using the `max-old-space-size` flag and an appropriate memory size in MB:

`node --max-old-space-size=4096 script.js`
