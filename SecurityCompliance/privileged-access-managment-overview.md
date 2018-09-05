---
title: "Privileged access management in Office 365"
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Strat_O365_IP
ms.custom: Ent_Solutions
ms.assetid: 
description: "Use this topic to learn more about privileged access management in Office 365"
---

# Privileged access management in Office 365

> [!IMPORTANT]
> This topic covers deployment and configuration guidance for features only currently available in Office 365 E5 and Advanced Compliance SKUs.

Privileged access management allows granular access control over privileged admin tasks in Office 365.  It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings. After enabling privileged access management, users will need to request just-in-time access to complete elevated and privileged tasks through an approval workflow that is highly scoped and time-bound. This gives users just-enough-access to perform the task at hand, without risking exposure of sensitive data or critical configuration settings. Enabling privileged access management in Office 365 will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access. 

## Getting help and providing feedback
We recognize that during the public beta you may come across an occasional bug or have feedback and suggestions on how we can improve privileged access management. We value your feedback and encourage you to share it with us:
- Post your feedback ad suggestions in the [Office Preview Yammer Group](https://www.yammer.com/officeenterprisenda/#/threads/inGroup?type=in_group&feedId=14435206).
- File your bug reports under area path “Office 365 Privileged Access Management” on the [Office Preview VSO](https://office-previews.visualstudio.com/previews).

## Frequently asked questions

### What SKUs do I need to use privileged access in Office 365?
Privileged access management in Office 365 is currently only available for customers with E5 and Advanced Compliance SKUs.

### When will privileged access be available for Office 365 workloads beyond Exchange?
We plan to offer this feature in other Office 365 workloads soon. When we’re ready to share a timeline, it will be available through the Office 365 roadmap.

### How is this different from Azure Active Directory’s Privileged Identity Management?
Privileged access management in Office 365 and [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) complement each other by providing access control with just-in-time access at different scopes. Together they provide a robust set of controls for protecting your data.

Privileged access management in Office 365 can be defined and scoped at the task level, while Azure AD Privileged Identity Management applies at the role level with the ability to execute multiple tasks.  Azure AD Privileged Identity Management primarily allows managing accesses for AD roles and role groups while privileged access management in Office 365 is applied at the task level.

 - **Enabling privileged access management in Office 365 while already using Azure AD Privileged Identity Management:** Adding privileged access management in Office 365 can provide another granular layer of protection and audit capabilities for privileged access to Office 365 data.

- **Enabling Azure AD Privileged Identity Management while already using privileged access management in Office 365:**  Adding Azure AD Privileged Identity Management to privileged access management in Office 365 can extend privileged access to data outside of Office 365 that’s primarily defined by a user’s role or identity. 

### Do I need to be a Global Admin to manage privileged access in Office 365?
During the preview you need to have Global Admin privilege to be able to manage privileged access in Office 365. Users who are included in an approvers’ group don't need to be a Global Admin to review and approve requests. 

### How is privileged access management in Office 365 related to Customer Lockbox?
[Customer Lockbox](https://support.office.com/article/Office-365-Customer-Lockbox-Requests-36f9cdd1-e64c-421b-a7e4-4a54d16440a2) allows a level of access control for organizations for access to to data by their service provider, i.e. Microsoft. Privileged access management in Office 365 allows granular access control within an organization for all Office 365 privileged tasks.