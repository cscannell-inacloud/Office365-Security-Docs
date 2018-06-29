---
title: "Set up a custom blocked URLs list using Office 365 ATP Safe Links"
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 5/30/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
description: "Read this article to learn how to set up a list of blocked URLs for your organization using Office 365 Advanced Threat Protection. The blocked URLs will apply to email messages and Office documents according to your ATP safe links policies."
---

# Set up a custom blocked URLs list using Office 365 ATP Safe Links

With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked. When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image: 
  
![This site is blocked](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
The blocked URLs list is defined by your organization's Office 365 security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies. 
  
Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).
  
> [!NOTE]
> The ATP Safe Links features are only available in Office 365 ATP, which is included in subscriptions, such as Office 365 Enterprise E5 and Office 365 Education A5, and, as of April 30, 2018, also [Microsoft 365 Business security features](https://support.office.com/article/c123694a-1efb-459e-a8d5-2187975373dc). If your organization has an Office 365 subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on. For more information, see [Office 365 Advanced Threat Protection Service Description](https://technet.microsoft.com/library/exchange-online-advanced-threat-protection-service-description.aspx). > Make sure your organization is using the latest version of Office 365 ProPlus on Windows to take advantage of extended ATP Safe Links features. 
  
## View or edit a custom list of blocked URLs

[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list. If you have the necessary [permissions assigned in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md), you can set up your organization's custom list. You do this by editing your organization's default Safe Links policy.
  
1. Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account. 
    
2. In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.
    
3. In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil). 
    
    ![Click Edit to edit your default policy for Safe Links protection](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
    This is where you go to view your list of blocked URLs. Note that at first, you won't have any URLs listed.
    
    ![The Blocked URLs list is in the default Safe Links policy that applies to your entire organization.](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)
  
4. Select the **Enter a valid URL** box, and then type a URL, and then choose the plus sign (+). Here are a few things to keep in mind: 
    
  - You can specify a domain-only URL (like contoso.com or tailspintoys.com). This will block clicks on any URL that contains the domain.
    
  - Do not include a forward slash ( **/**) at the end of the URL. For example, instead of entering http://www.contoso.com/, enter http://www.contoso.com.
    
  - You can include up to three wildcard asterisks (\*) per URL. The following table lists some examples of what you can enter and what effect those entries have.
    
|**Example Entry**|**What It Does**|
|:-----|:-----|
|contoso.com or \*contoso.com\*  <br/> |Blocks the domain, subdomains, and paths, such as https://www.contoso.com, http://sub.contoso.com, and http://contoso.com/abc  <br/> |
|http://contoso.com/a  <br/> |Blocks a site http://contoso.com/a but not additional subpaths like http://contoso.com/a/b  <br/> |
|http://contoso.com/a\*  <br/> |Blocks a site http://contoso.com/a and additional subpaths like http://contoso.com/a/b  <br/> |
   
5. When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.
    
## What if I want to define exceptions for certain users in my organization?

If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients. See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).
  
## Related topics

[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[ATP Safe Links in Office 365](atp-safe-links.md)
  
[Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md)
  
[ATP Safe Attachments in Office 365](atp-safe-attachments.md)
  

