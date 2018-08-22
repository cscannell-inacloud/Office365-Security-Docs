---
title: "Set up a custom do-not-rewrite URLs list using Office 365 ATP Safe Links"
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
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
description: "When you set up your ATP safe links policies, you can include a do-not-rewrite' list of URLs to enable some people in your organization to visit sites that you include in your list."
---

# Set up a custom do-not-rewrite URLs list using Office 365 ATP Safe Links

With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a [custom blocked URLs](set-up-a-custom-blocked-urls-list-wtih-atp.md), such that when people click on web addresses (URLs) in email messages or certain Office documents, they are prevented from going to those URLs. Your organization can also have custom "do not rewrite" lists for specific groups in your organization. A "do not rewrite" list enables some people to visit URLs that are otherwise blocked by [ATP Safe Links in Office 365](atp-safe-links.md). 
  
This article describes how to specify a list of URLs that are excluded from ATP Safe Links scanning, and a few important points to keep in mind.
    
## Important points to keep in mind

- Any URLs that you specify in the "do not rewrite" list are excluded from ATP Safe Links scanning for the recipients that you specify.
    
- When you specify a "do not rewrite" list for an ATP Safe Links policy, you can include up to three wildcard asterisks (\*). Wildcards (\*) are assumed for entries such as `contoso.com`, which do not explicitly include prefixes or subdomains, like `http://` or `https://`. This means an entry, such as `contoso.com` is similar to `\*contoso.com\*` for your "do not rewrite" list.
    
    The following table lists examples of what you can enter and what effect those entries have.
    
|**Example Entry**|**What It Does**|
|:-----|:-----|
|`\*contoso.com\*`  <br/> |Allows specific recipients to visit a domain, subdomains, and paths, such as `http://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `http://www.contoso.com/a`  <br/> |
|`http://contoso.com/a`  <br/> |Allows specific recipients to visit a site like `http://contoso.com/a`, but not subpaths like `http://contoso.com/a/b`  <br/> |
|`http://contoso.com/a\*`  <br/> |Allows specific recipients to visit a site like `http://contoso.com/a` and subpaths like `http://contoso.com/a/b`  <br/> |
   
- If you already have a list of URLs in your "do not rewrite" list, make sure to review that list and add wildcards as appropriate. For example, if your existing list has an entry like `http://contoso.com/a` and you want to include subpaths like `http://contoso.com/a/b` in your policy, add a wildcard to your entry so it looks like `http://contoso.com/a\*`.
    
- Do not include a forward slash (/) in the URLs that you specify in your "do not rewrite" list. For example, rather than enter `contoso.com/` in your "do not rewrite" list, enter `contoso.com`.
    
## Set up a "do not rewrite" list for specific groups

ATP Safe Links protection uses several lists, including your organization's blocked URLs list and the "do not rewrite" lists for exceptions. If you have the necessary permissions, you can set up your custom "do not rewrite" lists. You do this when you add or edit Safe Links policies that apply to specific recipients in your organization. 
  
1. Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account. 
    
2. In the left navigation, under **Threat management** \> **Policy** \> **Safe Links**.
    
3. In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)) to create a new policy. (Alternatively, you can edit an existing policy.)
    
    ![Choose New to add a Safe Links policy for specific email recipients](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
4. Specify a name and description for your policy.
    
5. In the **Do not rewrite the following URLs** section, select the **Enter a valid URL** box, and then type a URL, and then choose the plus sign (+). 
    
6. In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy. Choose **Add**, and then choose **OK**.
    
7. When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.
    
> [!NOTE]
> Make sure to review your organization's custom list of blocked URLs. See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md). 
  
## Related topics

[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[ATP Safe Links in Office 365](atp-safe-links.md)
  
[Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md)
  
[Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md)

[View reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md)

[Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)
  

