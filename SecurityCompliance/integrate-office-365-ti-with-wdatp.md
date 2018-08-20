---
title: "Integrate Office 365 Threat Intelligence with Windows Defender Advanced Threat Protection"
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 3/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
description: "Integrate Office 365 Advanced Threat Protection with Windows Defender Advanced Threat Protection to see more detailed threat management information."
---

# Integrate Office 365 Threat Intelligence with Windows Defender Advanced Threat Protection

If you are part of your organization's security team, you can integrate Office 365 with Windows Defender Advanced Threat Protection (ATP). This can help you quickly understand if users' machines are at risk when you are investigating threats in Office 365. For example, once integration is enabled, you will be able to see a list of machines that are used by the recipients of a detected email message, as well as how many recent alerts those machines have in Windows Defender ATP.
  
The following image shows the **Devices** tab that you'll see when have Windows Defender ATP integration enabled: 
  
![When Windows Defender ATP is enabled, you can see a list of machines with alerts.](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
In this example, you can see that the recipients of the email message have four machines and one has an alert in Windows Defender ATP. Clicking the link to a machine opens the machine page in Windows Defender ATP in a new tab.
  
## Requirements

- Your organization must have Office 365 Threat Intelligence and Windows Defender ATP.
    
- You must be an Office 365 global administrator or have a security administrator role assigned in the Security &amp; Compliance Center. (See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))
    
- You must have access to both Office 365 Threat Intelligence and the Windows Defender ATP portal.
    
## To integrate Office 365 Threat Intelligence with Windows Defender ATP

Integrating Office 365 Threat Intelligence with Windows Defender ATP is set up both in Office 365 and in the Windows Defender ATP portal.
  
1. As an Office 365 global or a security administrator, go to [https://portal.office.com](https://portal.office.com) and sign in with your work or school account for Office 365. 
    
2. Choose **Threat management** \> **Threat explorer**.
    
3. On the **More** menu, choose **WDATP Settings**.
    
4. Select **Connect to Windows ATP**.
    
After you have changed the settings in Office 365, you must enable the connection from Windows Defender ATP. To do that, see [Use the Windows Defender Advanced Threat Protection portal](https://go.microsoft.com/fwlink/?linkid=859690).
  
## Related topics

[Office 365 Threat Intelligence](office-365-ti.md)
  
[Office 365 Advanced Threat Protection](office-365-atp.md)
  

