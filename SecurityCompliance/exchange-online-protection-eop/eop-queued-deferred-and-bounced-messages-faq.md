---
title: "EOP queued, deferred, and bounced messages FAQ"
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
description: "This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Microsoft Exchange Online Protection (EOP) filtering process."
---

# EOP queued, deferred, and bounced messages FAQ

This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Microsoft Exchange Online Protection (EOP) filtering process.
  
 **Q. Why is mail queuing?**
  
A. Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery. It will not defer messages if a 500-series error is returned from the recipient network.
  
 **Q. How does a message become deferred?**
  
A. Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error. If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.
  
 **Q. How long does a message remain in deferral and what is the retry interval?**
  
A. Messages in deferral will remain in our queues for 2 days. Message retry attempts are based on the error we get back from the recipient's mail system. On average, messages are retried every 5 minutes.
  
 **Q. After your email server is restored, how are queued messages distributed?**
  
A. After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable. 
  

