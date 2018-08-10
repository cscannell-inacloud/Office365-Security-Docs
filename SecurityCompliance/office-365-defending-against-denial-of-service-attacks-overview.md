---
title: "Office 365 Defending Against Denial-of-Service Attacks Overview"
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: "An overview of Denial-of-Service (DoS) attacks."
---

# Defending Against Denial-of-Service Attacks Overview

## Introduction
Microsoft delivers a trustworthy infrastructure for more than 200 cloud services, including Microsoft Azure, Microsoft Bing, Microsoft Office 365, Microsoft Dynamics 365, Microsoft OneDrive, Skype, and Xbox Live that are hosted in our global cloud infrastructure of more than 100 datacenters.

As a global organization with a significant Internet presence and many prominent Internet properties that provide cloud services, Microsoft is a large, common target for hackers and other malicious individuals. The network--the communication layer between clients and the Microsoft Cloud--is one of the biggest targets of malicious attacks. In fact, for many years, Microsoft has been continuously and persistently under some form of network-based cyberattack. At almost all times, at least one of Microsoft's Internet properties is experiencing some form of attack. Without reliable and persistent mitigation systems that can defend against these attacks, Microsoft's cloud services would be offline and unavailable to customers.

Microsoft uses defense-in-depth security principles to protect its cloud services and networks. 

## Definition and Symptoms of Denial-of-Service Attacks
One way to attack network services is to create many requests against a service's hosts to overwhelm the network and servers to deny service to legitimate users. This is referred to as a denial-of-service (DoS) attack. When the attack is performed by multiple actors, endpoints, and/or vectors, it is referred to as a distributed denial-of-service (DDoS) attack. Although the means, motives, and targets vary, DoS and DDoS attacks generally consist of the efforts of a person or persons to prevent an Internet site or service from functioning correctly or at all, either temporarily or indefinitely.

The [United States Computer Emergency Readiness Team](https://www.us-cert.gov/) (US-CERT) defines symptoms of DoS attacks to include:
- Unusually slow network performance (when opening files or accessing Internet sites)
- Unavailability of a Web site
- Inability to access a Web site
- Dramatic increase in received spam
- Disconnection of a wireless or wired Internet connection
- Long-term loss of access to the Web or any Internet services

## Related Topics
- [Core Principles of Defense Against Denial-of-Service Attacks](office-365-core-principles-of-defense-against-dos-attacks.md)
- [Microsoft's Denial-of-Service Defense Strategy](office-365-microsoft-dos-defense-strategy.md)
- [Defending Microsoft Cloud Services Against Denial-of-Service Attacks](office-365-defending-cloud-services-against-dos-attacks.md)
