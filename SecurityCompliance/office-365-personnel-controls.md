---
title: "Office 365 Personnel Controls"
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
description: "Summary: An overview of Microsoft's personnel screening practices for Office 365."
---

# Office 365 Personnel Controls 

Personnel screening, which is the process of reviewing and validating a person's past behavior and status, is an important mitigation control to prevent Office 365 service compromise. While past behavior is not a perfect predictor of a person's future behavior, it does help to identify potential bad actors. Microsoft's Personnel Screening Standard applies to all Microsoft employees, interns, and contingent staff involved in the development, operation, or delivery of online services to government or commercial cloud customers. Screening standards for National Cloud environments that are not operated by Microsoft are defined by the operating partner personnel for each specific environment.

Microsoft's personnel screening practices for Office 365 are aligned with Microsoft's corporate standards and National Institute of Standards and Technology (NIST) controls for personnel screening. Microsoft staff who require access to the following are subject to Microsoft's Personnel Screening Standard:
- Physical access to datacenters, co-locations, secured rooms, cages, server racks, or edge sites that provide the infrastructure supporting online services for government or commercial cloud customers.
- Logical access to government or commercial cloud Customer Data provided through specific managed environments.
    - Network management access to devices and services that transport or store government or commercial cloud Customer Data.

Specific personnel-related events that trigger screening requirements include:
- New Microsoft staff placed in roles where screening is a defined requirement.
- Internal Microsoft staff transferring or moving to an existing role that currently includes screening as a defined requirement.
- Existing roles that change scope to include screening as a defined requirement.

To ensure that only approved personnel have access to Customer Data or environments that require screening, the following enforcement criteria applies:

United States Cloud Environments Only:
- Access to Customer Data or environments that require screening must only be permitted after adjudication is completed and screening requirements are passed.
- Microsoft staff who no longer require access to Customer Data or related environments must have access removed upon leaving Microsoft or moving to a new role.
- Microsoft staff must leave screened environment smart cards with management before leaving the United States.

National Cloud Environments:
- Third-party operator or data trustee personnel are responsible for managing and enforcing access for National Cloud environments.

Within Microsoft's cloud services environments, access is restricted based on a person's role and the type of data involved, as detailed in Table 1. Qualified or unqualified personnel physically located outside of the United States are not permitted to have access to Customer Data within a United States cloud. Access to National Cloud environments is restricted so that Microsoft personnel do not have technical access to Customer Data, or systems that contain Customer Data, without approval by the third-party operator or data trustee.

| Role | Access to Customer Data | Access to System Data |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------|---------------------------------|
| Qualified Personnel physically located in the United States | Permitted | Permitted |
| Qualified Personnel physically located outside of the United States | Not Permitted | Permitted |
| International Exception Access for Microsoft Staff –  Enables logical access for Microsoft staff who do not reside in the country where the government or commercial Customer Data is at rest | Not Permitted | Permitted |
| Unqualified Personnel (unscreened personnel that require an escort by qualified personnel) | Permitted with authorization | Permitted with escort oversight |

*Table 1 - Data access by role*

Where local law allows for it, Microsoft's Global Security Department conducts pre-employment screening. This is a formal background investigation that includes the following criteria:
- A check (e.g., for completeness and accuracy) of the applicant's resume
- Confirmation of academic and professional qualifications
- Investigation of any loss of professional credentials
- Verification of past three employers
- A check of police records for felony conviction
- Confirmation of identity from a government-issued identification
- Credit check where appropriate

Periodic rescreening and/or additional background checks may be required for certain management, security, or other roles, including but not limited to United States-based employees in roles that require access to Customer Data.
For contingent staff, the contract with the third-party specifies Microsoft's requirements for screening that must be conducted by the third-party. For background checks, the third-party company is responsible for providing to Microsoft verification that a background check has been performed. The results of the background check are typically received via email from the third-party's human resources department. International employees of contract staff may be exempt from the background screening process due to laws in countries that prohibit background checks.

## Microsoft Employment Screening
Since 2004, Microsoft has required individuals to pass a seven-year criminal record screen for felonies and misdemeanors, and to verify their education and employment history, as part of pre-employment screening in the United States for employees and interns.

In the United States, prior to assigning any Microsoft employee or any Microsoft-assigned subcontractor to provide Office 365-related services, Microsoft will conduct and cause its subcontractor to conduct a background check consisting of a [Social Security number trace](https://en.wikipedia.org/wiki/Social_Security_number) and criminal record check. The data from this background check is used as a factor in the hiring decision. The criminal record check includes a seven-year felony and misdemeanor criminal records check of federal, state, and county records (as applicable).

As a condition of employment, at the time of hire, all Microsoft employees are required to sign confidentiality and non-disclosure agreements, and to verify that they have reviewed the Microsoft Employee Handbook.

## Microsoft Cloud Background Check
A Microsoft Cloud Background Check is required for candidates to be hired as employees providing Office 365-related services in the United States. Microsoft employees in the United States with access to Customer Data must follow the Microsoft Cloud Background Check process, which is required by all Office 365 services. Outside of the United States, the process varies. For example, the Microsoft Cloud for Germany uses a Data Trustee approval model, which is designed to ensure that the Data Trustee (a German company), and not Microsoft, is in control of access to Customer Data. The Microsoft Cloud in Germany is delivered from datacenters in Germany, and the Operations Centers (OC) containing the technical staff of the Data Trustee are also in Germany. Both the datacenter and the OC facilities are operated, maintained and controlled by the Data Trustee.

The following table lists the checks that are performed as part of the Microsoft Cloud Background Check.

| Screening | Description |
|--------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| Social Security Number Search | Verifies that the provided Social Security number is valid. |
| Criminal History Check | Seven-year criminal records check for felony and misdemeanor offenses at the state, county, and local levels, and as appropriate, at the federal level. |
| Office of Foreign Assets Control List | Department of Treasury list of individuals and organizations with whom United States citizens and permanent residents are not allowed to do business. |
| Bureau of Industry and Security List | Department of Commerce list of individuals and entities barred from engaging in export activities. |
| Office of Defense Trade Controls Debarred Persons List (*added on July 1, 2010*) | Department of State list of individuals and entities barred from engaging in export activities related to the Defense industry. |

*Table 2 - Microsoft Cloud Background Check screening processes for employees hired within the United States*

The results from the Microsoft Cloud Background Check are stored in our employee database, which is connected to our datacenter access control systems. If the Microsoft Cloud Background Check expires and the employee does not renew it, then access to Office 365 services is revoked and no longer available until the Microsoft Cloud Background Check is completed again. When the employment relationship with Microsoft ends, any existing datacenter access is immediately revoked.

United States citizenship is verified for all employees with physical or logical access to the Office 365 United States Government services. To verify citizenship, employees and/or new hire candidates meet with a U.S. Citizenship Delegate who is trained to review documentation verifying U.S. citizenship. Employees or new hire candidates must bring the required documentation and sign an attestation form at a meeting with the Citizenship Delegate for their region. The meeting must be done in person. Once the individual has met with the Citizenship Delegate and provided the necessary documentation and signatures, the Citizenship Delegate forwards a copy of the documents to Microsoft Staffing Operations who submit the copy to record keeping.

Personnel with logical access to the Office 365 U.S. Government Community Cloud, or logical or physical access to the Azure U.S. government offerings, are required to comply with federal government requirements of the FBI's [Criminal Justice Information Services](https://www.fbi.gov/services/cjis) (CJIS), including personnel screening. CJIS screening in support of the Office 365 U.S. Government service includes a fingerprint-based criminal background check which is adjudicated by the CJIS system agency designated adjudicator in [states that have enrolled](https://blogs.office.com/2013/10/23/california-and-microsoft-sign-cjis-security-policy-agreement/) in the Microsoft Online Services CJIS support program.
