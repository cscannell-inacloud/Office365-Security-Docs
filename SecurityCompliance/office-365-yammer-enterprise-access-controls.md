---
title: "Office 365 Yammer Enterprise Access Controls"
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 5/18/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
ms.collection: Strat_O365_Enterprise
description: "Summary: A brief summary about Yammer Enterprise Access Controls in the production environment."
---

# Yammer Enterprise Access Controls 

Both physical and logical access to the Yammer production environment is restricted to a very small set of people (infrastructure and operations). As with other Office 365 engineers, Yammer engineers have zero standing access to Customer Data. Access must be requested using an approval-based just-in-time access control system similar to Lockbox, and there is a limited number of approvers. Approvers verify the request (e.g., they verify whether the request is legitimate based on need, business case, time, etc.), and then approve or deny the request. If the request is approved, JIT access is granted for a defined and limited time, after which it automatically expires. 

As with other Office 365 services, all access to the Yammer production environment leverages multi-factor authentication. All access and command history is attributed to a user, and logged and reviewed regularly by the Yammer security team.