---
title: "Office 365 Isolation Controls"
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 5/18/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: "Summary: An explanation of isolation controls within Office 365."
---

# Office 365 Isolation Controls 

Microsoft continuously works to ensure that the multi-tenant architecture of Office 365 supports enterprise-level security, confidentiality, privacy, integrity, and availability [standards](https://www.microsoft.com/en-us/TrustCenter/Compliance?service=Office#Icons), as well as local and international standards. Given the scale and the scope of services provided by Microsoft, it would be difficult and non-economical to manage Office 365 if significant human interaction were required. Office 365 services are provided through multiple globally-distributed datacenters, in a highly-automated fashion, where extremely few datacenter operations require a human touch, and even fewer operations require access to customer content. Our staff supports these services and datacenters using automated tools and highly secure remote access. (For some of the details about how large-scale services are operated in Office 365, see [Behind The Curtain: How We Run Exchange Online](http://engineering.microsoft.com/2015/10/29/running-exchange-online/) and [A behind the scenes look at Office 365 for IT Pros](https://channel9.msdn.com/Events/SharePoint-Conference/2014/SPC202).)

Office 365 is composed of multiple services that provide important business functionality and contribute to the entire Office 365 experience. Each of these services is designed to be self-contained and to integrate with one another. Office 365 is designed with the principles of a [Service-Oriented Architecture](https://msdn.microsoft.com/en-us/library/aa480021.aspx), which is defined as designing and developing software in the form of interoperable services providing well-defined business functionality, and [Operational Security Assurance](http://www.microsoft.com/en-us/download/details.aspx?id=40872), a framework that incorporates the knowledge gained through a variety of capabilities that are unique to Microsoft, including the Microsoft [Security Development Lifecycle](https://www.microsoft.com/en-us/sdl/default.aspx), the [Microsoft Security Response Center](https://technet.microsoft.com/en-us/library/dn440717.aspx), and deep awareness of the cybersecurity threat landscape.

Office 365 services interoperate with each other, but they are designed and implemented so that they can be deployed and operated as autonomous services, independent of each other. Microsoft segregates duties and areas of responsibility for Office 365 to reduce opportunities for unauthorized or unintentional modification or misuse of the organization's assets. Office 365 teams have defined roles as part of a comprehensive role-based access control mechanism.

## Customer Content Isolation
All customer content belonging to a tenant is isolated from other tenants and from the operations and systems data used in the management of Office 365. Multiple forms of protection have been implemented throughout Office 365 to minimize the risk of compromise of any Office 365 service or application, or any gaining of unauthorized access to the information of tenants or the Office 365 system itself. For information about how Microsoft implements logical isolation of tenant data within Office 365, see [Tenant Isolation in Office 365](http://aka.ms/Office365TI).
