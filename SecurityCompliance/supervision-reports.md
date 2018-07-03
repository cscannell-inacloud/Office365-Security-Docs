---
title: "Supervision reports"
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 5/12/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2a762db5-e1c9-4c09-aa8e-bef49ce97209
description: "Use supervision reports to see which emails need compliance review and who should perform it."
---

# Supervision reports

Supervision policies define which communications in your organization need review for compliance, and who will perform those reviews. Use the supervision reports to see the review activity at the policy and reviewer level. For each policy, you can also view live statistics on the current state of review activity. [Learn more about supervision policies ](configure-supervision-policies.md) . 
  
> [!NOTE]
> Using supervision policies requires an Office 365 E5 subscription for your organization. If you don't have that plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
You can use the supervision reports to:
  
- Verify that your policies are working as you intended. 
    
- Find out how many emails are being identified for review.
    
- Find out how many emails aren't compliant and which ones are passing review. This information can help you decide whether to fine-tune your policies or change the number of reviewers.
    
## View the Supervision report

1. Sign into the [Security &amp; Compliance Center](https://protection.office.com/) using the credentials for an admin account in your Office 365 organization that has permissions to view supervision reports.. 
    
2. Go to **Reports** \> **Dashboard**. You'll see a reporting widget for supervision and other reports you have access to.
    
3. Click the **Supervision** widget to open the detailed report page. 
    
> [!NOTE]
> If you aren't able to access the **Reports** page, check that you're a member of the Supervisory Review role group, as described in [Make supervision available in your organization](configure-supervision-policies.md#SRavailable). Being included in this role group lets you create and manage supervision polices and run the report. 
  
## How to use the report

When a supervision policy identifies an email for review, the email is delivered to the reviewer's Supervision folder in Outlook and Outlook web app. This report lists each policy's name and the number of communications at each stage in the review process.
  
Use the report to:
  
- View data for all or specific policies.
    
- View data grouped by tag type (such as Compliant, Questionable, etc.), reviewer, or message type.
    
- Export data to a CSV file.
    
- Filter data based on review activity date, tag type, reviewer, message type.
    
Here's a breakdown of the values you might see in the **Tag type** column. 
  
|**Tag type**|**What it means**|
|:-----|:-----|
|Not Reviewed  <br/> |The number of emails that have not been reviewed yet. These emails are awaiting review in the reviewer's supervision folder in Outlook.  <br/> |
|Compliant  <br/> |The number of emails reviewed and marked as compliant. No further action is needed.  <br/> |
|Questionable  <br/> |The number of emails reviewed and marked questionable. This acts as a flag; other reviewers can help check whether an email needs investigation for compliance.  <br/> |
|Non-Compliant (Active)  <br/> |The number of non-compliant emails that reviewers are currently investigating.  <br/> |
|Non-Compliant (Resolved)  <br/> |The number of non-compliant emails that reviewers investigated and resolved.  <br/> |
   
## More details

- Supervision policies must first be provisioned before they will appear in this report.
    
- If policies are deleted, historical data is still shown. However, they're indicated as a "Non-existent policy", and the **Export** function isn't available. 
    
- If the report doesn't show any data by default, it might be because the current date range doesn't have any data to show. In these cases, use the **Filters** control to change the date range. 
    

