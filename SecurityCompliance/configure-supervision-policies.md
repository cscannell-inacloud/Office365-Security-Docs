---
title: "Configure supervision policies for your organization"
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 5/12/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- 'ms.o365.cc.SupervisoryReview'
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: d14ae7c3-fcb0-4a03-967b-cbed861bb086
description: "Set up a supervisory review policies to capture employee communications for review."
---

# Configure supervision policies for your organization

Use supervision policies to capture employee communications for examination by internal or external reviewers.
  
> [!NOTE]
> Using supervision policies requires an Office 365 E5 subscription for your organization. If you don't have that plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Follow these steps to set up and use supervision in your Office 365 organization: 
  
- [Set up groups for Supervision](configure-supervision-policies.md#exampledist)
    
    Before you start using supervision, determine who will have their communications reviewed and who will perform those reviews. If you want to get started with just a few users to see how supervision works, you can skip setting up groups for now.
    
- [Make supervision available in your organization](configure-supervision-policies.md#SRavailable)
    
    Add yourself to the Supervisory Review role group so you can set up policies. Anyone who has this role assigned can access the **Supervision** page under **Data Governance** in the Security &amp; Compliance Center. 
    
- [Set up a supervision policy](configure-supervision-policies.md#setupsuper)
    
    You'll create supervision policies in the Security &amp; Compliance Center. These policies define which communications are subject to review in your organization, and specifies who should perform reviews. Communications include email as well as 3rd-party platform communications (such as Facebook, Twitter, etc.)
    
- [Use Outlook web app to review communications identified by a supervision policy](configure-supervision-policies.md#UseOutlook)
    
    The Supervision add-in gives reviewers access to the supervision functionality right within Outlook web app so they can assess and categorize each item. Support for the desktop version of Outlook is coming soon.
    
- **Run the supervision report**
    
    Use the supervision reports to see the review activity at the policy and reviewer level. For each policy, you can also view live statistics on the current state of review activity. For details, see [Supervision reports](supervision-reports.md).
    
## Set up groups for Supervision
<a name="exampledist"> </a>

 When you create a supervision policy, you'll determine who will have their communications reviewed and who will perform those reviews. In the policy, you'll use email addresses to identify individuals or groups of people. To simplify your setup, create groups for people who will have their communication reviewed and groups for people who will review those communications. If you're using groups, you might need several—for example, if you want to monitor communications between two distinct groups of people, or if you want to specify a group that isn't going to be supervised. See [Example distribution groups](configure-supervision-policies.md#GroupExample) for details about how this works. 
  
To supervise communications between or within groups in your organization, set up distribution groups in the Exchange admin center (go to **recipients** \> **groups**). For more information about setting up distribution groups, see [Manage distribution groups](http://go.microsoft.com/fwlink/?LinkId=613635)
  
> [!NOTE]
> You can also use dynamic distribution groups or security groups for supervision if you prefer. To help you decide if these better fit your organization needs, see [Manage mail-enabled security groups](http://go.microsoft.com/fwlink/?LinkId=627033), and [Manage dynamic distribution groups](http://go.microsoft.com/fwlink/?LinkId=627058). 
  
### Example distribution groups
<a name="GroupExample"> </a>

This example includes a distribution group that has been set up for a financial organization called Contoso Financial International. 
  
In Contoso Financial International, a sampling of communications between brokers in the United States must be supervised. However, compliance officers within that group do not require supervision. For this example, we can create the following groups:
  
|**Set up this distribution group**|**Group address (alias)**|**Description**|
|:-----|:-----|:-----|
|All US brokers  <br/> |US_Brokers@Contoso.com  <br/> |This group includes email addresses for all US-based brokers who work for Contoso.  <br/> |
|All US compliance officers  <br/> |US_Compliance@Contoso.com  <br/> |This group includes email addresses for all US-based compliance officers who work for Contoso. Because this group is a subset of all US-based brokers, you can use this alias to exempt compliance officers from a supervision policy.  <br/> |
   
The [Set up a supervision policy](configure-supervision-policies.md#setupsuper) section describes how you can use these groups when you configure the policy. 
  
## Make supervision available in your organization
<a name="SRavailable"> </a>

To make **Supervision** available as a menu option in the Security &amp; Compliance Center, you must be assigned the Supervisory Review Administrator role. 
  
To do this, you can either add yourself as a member of the Supervisory Review role group, or you can create a new role group.
  
### Add members to the Supervisory Review role group

1. Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization. 
    
2. In the Security &amp; Compliance Center, go to **Permissions**.
    
3. Select the **Supervisory Review** role group and then click the Edit icon. 
    
4. In the **Members** section, add the people who you want to manage supervision for your organization. 
    
### Create a new role group

1. Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization. 
    
2. In the Security &amp; Compliance Center, go to **Permissions** and then click Add ( **+**).
    
3. In the **Roles** section, click Add ( **+**) and scroll down to **Supervisory Review Administrator**. Add this role to the role group.
    
4. In the **Members** section, add the people who you want to manage supervision for your organization. 
    
For more information about role groups and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center ](permissions-in-the-security-and-compliance-center.md).
  
## Set up a supervision policy
<a name="setupsuper"> </a>

> [!IMPORTANT]
> Before creating a supervision policy, you must first remove any existing supervisory review policies. 
  
1. Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization. 
    
2. In the Security &amp; Compliance Center, go to click **Data governance** \> **Supervision**.
    
    > [!NOTE]
    > The previous version of the feature may show in the left-hand navigation as **Supervisory Review (retiring soon)**. This version will soon be deprecated and removed. The new version called **Supervision** will take its place. 
  
3. Click **Create** and then follow the wizard to set up the following pages of the policy. 
    
### Policy name and description

Enter a name and a description for your policy. For example purposes, we'll name the policy Contoso US Brokers.
  
### Choose users to supervise

- In the **Supervise these users or groups** box, choose the users or groups whose communications your want to supervise. Sticking with our example for Contoso US Brokers, we'll choose the group US_Brokers@Contoso.com here. 
    
- If you chose a group to supervise, you can use the **Exclude these users** box to choose members of the group who are exempt from supervision . Using the example , we'll exclude the group US_Compliance@Contoso.com here. 
    
### Choose communications to review
<a name="CommsToReview"> </a>

By default, the **Direction is** condition is displayed and can't be removed. If you want to scope the review further (such as only reviewing content that contains certain words or phrases), click **Add a condition**. You can specify multiple conditions if needed.
  
The conditions you choose will apply to communications from both email and 3rd-party sources in your organization (like from Facebook or DropBox). For details about importing 3rd-party communications into your Office 365 organization, see [Archiving third-party data in Office 365](https://technet.microsoft.com/EN-US/library/mt621583.aspx).
  
The following table explains more about each condition.
  
|**Condition**|**How to use this condition**|
|:-----|:-----|
|Direction is  <br/> |Choose **Inbound** to review communications that are sent **to** the people you chose to supervise **from** people not included in the policy.  <br/> Choose **Outbound** if you want to review communications that are sent **from** the people you chose to supervise ** to ** people not included in the policy.  <br/> Choose **Internal** to review communications sent **between** the people you identified in the policy.  <br/> |
|Message contains any of these words  <br/> Message contains none of these words  <br/> |To apply the policy when certain words or phrases are included or excluded in a message, enter each word or phrase on a separate line. Each line of words you enter will be applied separately (only one of these lines must apply for the policy to apply to the message). For more information about entering words or phrases, see the next section [Matching words and phrases to emails or attachments](configure-supervision-policies.md#Matchwords).  <br/> |
|Attachment contains any of these words  <br/> Attachment contains none of these words  <br/> |To apply the policy when certain words or phrases are included or excluded in a message attachment (such as a Word document), enter each word or phrase on a separate line. Each line of words you enter will be applied separately (only one line must apply for the policy to apply to the attachment). For more information about entering words or phrases, see the next section [Matching words and phrases to emails or attachments](configure-supervision-policies.md#Matchwords).  <br/> |
|Attachment is any of these file types  <br/> Attachment is none of these file types  <br/> |To supervise communications that include or exclude specific types of attachments, enter the file extensions (such as .exe or .pdf). If you want to include or exclude multiple file extensions, enter these on separate lines. Only one attachment extension needs to match for the policy to apply.  <br/> |
|Message size is larger than  <br/> Message size is not larger than  <br/> |To review messages based on a certain size, use these conditions to specify the maximum or minimum size a message can be before it is subject to review. For example, if you specify **Message size is larger than** \> **1.0 MB**, all messages that are 1.01 MB and larger will be subject to review. You can choose bytes, kilobytes, megabytes, or gigabytes for this condition.  <br/> |
|Attachment is larger than  <br/> Attachment is not larger than  <br/> |To review messages based on the size of their attachments, specify the maximum or minimum size an attachment can be before the message and its attachments are subject to review. For example, if you specify **Attachment is larger than** \> **2.0 MB**, all messages with attachments 2.01 MB and over will be subject to review. You can choose bytes, kilobytes, megabytes, or gigabytes for this condition.  <br/> |
   
#### Matching words and phrases to emails or attachments
<a name="Matchwords"> </a>

Each line of words you enter will be applied separately (only one line must apply for the policy condition to apply to the email or attachment). For example, let's use the condition, **Message contains any of these words**, with the keywords "banker" and "insider trading" on separate lines. The policy will apply to any messages that includes the word "banker" or the phrase "insider trading". Only one of these words or phrases must occur for this policy condition to apply. Words in the message or attachment must exactly match what you enter.
  
#### Entering multiple conditions
<a name="Matchwords"> </a>

If you enter multiple conditions, Office 365 uses all the conditions together to determine when to apply the policy to communication items. When you set up multiple conditions, they must all be met for the policy to apply, unless you enter an exception. For example, let's say you need to create a policy that should apply if a message contains the word "trade", and is larger than 2MB. However, if the message also contains the words "Approved by Contoso financial", the policy should not apply. Thus, in this case, the three conditions would be as follows: 
  
- **Message contains any of these words**, with the keywords "trade"
    
- **Message size is larger than**, with the value 2 MB
    
- **Message contains none of these words**, with the keywords "Approved by Contoso financial team".
    
### Specify percentage to review
<a name="CommsToReview"> </a>

If you want to reduce the amount of content to review, specify a percentage. We'll randomly select that amount of content from the total that matched the conditions you chose. If you want reviewers to review all items, enter **100%**.
  
### Choose reviewers
<a name="CommsToReview"> </a>

The users and groups you choose will use the Supervision app in Outlook web app to examine the communications that are returned by this policy. You can include email addresses for internal or external reviewers. 
  
### Review your settings
<a name="CommsToReview"> </a>

After you've completed all sections of the supervision policy, review your settings and then click **Finish** to save your policy. It might take a few hours for the policy to start capturing communications. Supervision delivers all communications for review into a shared folder that reviewers can access in Outlook web app. 
  
## Use Outlook web app to review communications identified by a supervision policy
<a name="UseOutlook"> </a>

Reviewers will use the Supervision add-in for Outlook web app to review communications. The add-in is installed automatically in Outlook web app for all reviewers you specified in the policy. Support for the desktop version of Outlook is coming soon.
  
 **Reviewing communications in Outlook web app**
  
1. In Outlook web app, expand the **Supervision - \<policy name\>** folder. 
    
2. In the **\<policy name\>** subfolder, reviewers will see all the communications identified by that supervision policy. 
    
    ![Supervision add-in in Outlook web app showing the supervision policy subfolder selected](media/eef329bf-2bd0-477e-a715-76ca19b3347f.jpg)
  
3. Open an item to review and click the **Supervision** add-in. 
    
4. Use the add-in to classify the item as **Compliant**, **Non-Compliant**, **Questionable,** or **Resolved**. After you've classified an item, it will be moved to the corresponding subfolder under the **\<policy name\>** folder. 
    

