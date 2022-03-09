---
author: Mobius5150
description: This document provides details on the support policy for the Quantinuum provider in Azure Quantum
ms.author: mblouin
ms.date: 02/24/2022
ms.service: azure-quantum
ms.subservice: computing
ms.topic: reference
title: Support Policy for Quantinuum in Azure Quantum
uid: microsoft.quantum.providers.quantinuum.support
---

# Support Policy for Quantinuum in Azure Quantum

This article describes the Microsoft support policy that applies when you use the Honeywell provider in Azure Quantum. The article applies to any of the targets under this provider.

If you are using the Honeywell provider and hit unexpected issues, you can contact the Azure Support team for help by [creating an Azure support case](/azure/azure-portal/supportability/how-to-create-azure-support-request).

In some situations, the Azure Support team will need to redirect you to Honeywell's support team, or where you may receive a quicker response by reaching out to Honeywell directly. This article details this process and answers some frequently asked questions.

## Quantinuum Support Policy - Public Preview

The goal of Support is to identify and remedy defects or malfunctions causing the Quantum Computer to fail to perform in accordance with the agreed specifications and documentation (“Problems”). Support only covers the current released version generally available to customers.  Although our quantum experts can help you troubleshoot algorithm issues, we are not responsible for any issues, problems, or defects with your algorithm. To minimize programming issues, users are able to run their algorithms through the syntax validator prior to running on hardware.  

### 1.1	Contacting Technical Support within Quantinuum

To create a support request with Quantinuum, submit an incident report via email to <a href="mailto:QCsupport@quantinuum.com">QCsupport@quantinuum.com</a>. The on-call engineer will respond within the appropriate SLA (Table 2). Note that only incident reports that contain all of the following information will notify the Quantinuum team and have the appropriate SLA resolution window. Reports without the necessary information will not trigger this response. All requests must be provided in the English language and will be answered in the English language.

_Table 1: Support Contact information and Standard Operating Hours_
| Email | Standard Operating Hours |
| - | - |
| <a href="mailto:QCsupport@quantinuum.com">QCsupport@quantinuum.com</a> | 8am – 5pm MST on Business Days<sup>1</sup> |

_<sup>1</sup> “Business Days” means Monday to Friday but excluding national, legal, or bank holidays._

The incident report will require the following information:

- Description: A detailed description of the issue you are facing, what you are observing, and any steps you have already taken to triage/understand the issue
- Primary contact: A primary contact name and phone number in case we require more information
- Incident Severity: the severity of the incident, according to our severity definitions

Once a report is filed, the Quantinuum team will be notified and will respond within the required SLA window. You will receive an acknowledgement of the issue once it has been received and the on-call engineer has been notified. The on-call engineer may request more information, or may call you at the contact number listed in the report depending on the severity. 

During Reserved (dedicated) Sessions, Quantinuum will provide at least one quantum specialist available to you for customer support for the entirety of your dedicated session. Quantinuum reserves the right to change out the specialist during your session, but will use commercially reasonable efforts to ensure the new specialist is prepared to continue providing support.     

During Queued Runs, if your job is running in the general queue and you encounter an issue, you may submit your issue request online at: <a href="mailto:QCsupport@quantinuum.com">QCsupport@quantinuum.com</a>. You can expect to receive an answer within three (3) business days.  

### 1.2	Quantinuum severity index and response SLA

If the Quantinuum engineer determines that the issue does not fall within the bounds of our incident response commitments, or does not have the right severity classification, they may opt at their sole discretion to adjust the severity and/or end support if the new severity does not require it.

Certain problems may be easier to address than others, and we may not be able to completely resolve the problem with our initial response. If we are unable to reasonably resolve the problem, we will make a good faith effort to give an assessment of the issue and an estimated time for resolution. 

_Table 2: Definition of Severity Index_

| Severity	| Meaning | Description |
| - | - | - |
| Severity 1| 	Significant Impact | System performance degraded below minimum accepted level |
| Severity 2| 	Urgent or high impact | Job status has not updated; issues retrieving data |
| Severity 3| 	Not urgent | Miscellaneous  |

The following table shows the Response SLA that will be adhered to by Quantinuum for incident reports of the corresponding severity. Note that these define how fast we will respond to issues – resolution times are not guaranteed.

_Table 3: Response SLA for Various Severity_
| Severity	| Response SLA |
| - | - |
| Severity 1	| Business hours response within 1 hour |
| Severity 2	| Business hours response within 1 business day |
| Severity 3	| Business hours response within 3 business days |


## Frequently asked questions

#### Q: What happens if I raise a support issue with the Azure support team and it turns out that a third party provider (like Quantinuum) needs to troubleshoot the issue further?

The support engineer will create a redirection package for you. This is a PDF document that contains information about your case which you can provide to the Quantinuum support team.
The support engineer will also give you advice and guidance on how to reach out to Quantinuum to continue troubleshooting.

#### Q: What happens if I raise a support issue with the Quantinuum team and it turns out that there is an issue with the Azure Quantum service?

The Quantinuum support team will help you reach out to Microsoft and provide you with a redirection package. This is a PDF document that you can use when continuing your support enquiry with the Azure support team.

### Third-party information disclaimer

The third-party products that this article discusses are manufactured by companies that are independent of Microsoft. Microsoft makes no warranty, implied or otherwise, about the performance or reliability of these products.

### Third-party contact disclaimer

Microsoft provides third-party contact information to help you find additional information about this topic. This contact information may change without notice. Microsoft does not guarantee the accuracy of third-party contact information.