---
title: "Microsoft Teams Direct Routing SIP ladder"
ms.reviewer: teddygyabaah
ms.date: 03/06/2025
ms.author: scottfrancis
author: sfrancis206
manager: pamgreen
audience: ITPro
ms.topic: how-to
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection: 
  - M365-voice
  - m365initiative-voice
  - Tier1
appliesto: 
  - Microsoft Teams
f1.keywords:
- NOCSH
description: "Analyze Microsoft Teams Direct Routing calls with SIP call flow feature"
---

# View Microsoft Teams Direct Routing calls with SIP Call Flow 

This article introduces the Teams admin center's **SIP call flow** tool and is intended for Teams telephony admins and IT Pros who are diagnosing call flow issues between your organization's Session Border Controller (SBC) and Microsoft's Session Initiation Protocol (SIP) Proxy in Direct Routing deployments.

Using the Teams admin center's **SIP call flow** tool, a visual, chronological sequence of the SIP signaling messages exchanged between SBC and SIP Proxy can be used to audit protocol actions.

### Prerequisites

Access to the Teams admin center is required, using one of the following [Teams administrator roles](using-admin-roles.md):

- Teams Administrator
- Teams Telephony Administrator

Your [Direct Routing](direct-routing-plan) environment must be correctly configured, with a properly connected and functioning SBC. For more information, see [Configure Direct Routing](direct-routing-configure.md).

### Access

To access the SIP call flow feature, log into the Microsoft Teams admin center https://admin.teams.microsoft.com.

- Navigate to the left side rail, select **Analytics & reports**
- Select **Usage reports**
- Generate a **PSTN usage** report
    - From the report drop-down, select **PSTN Usage** report, select a desired date range, and select **Run Report**.  
- In the generated report, select the **Direct Routing** tab.
- In the displayed records of Direct Routing calls, identify the desired call to audit, and select it.'
- From the list heading select **SIP call flow**.

Alternatively, after selecting your call, you can select the link below the 'Final SIP Code'.

> [!NOTE] 
> Please allow up to 30 minutes for the SIP call data to be processed and uploaded to the Teams Admin Center for reporting.
> Call records older than 30 days will not have SIP Ladder information available.  

### Understanding the SIP call flow view

The SIP call flow visually represents the call as a series of interactions between your organization’s SBC and Microsoft SIP Proxy. The visual representation is known as a ladder diagram.

Each "rung" of the ladder represents a SIP message.

The direction of the arrow indicates the sender and receiver of the message. Messages are displayed in chronological order from top to bottom, allowing you to follow the sequence of protocol events during the call.

To view additional detail about a SIP event, select the event and view the protocol details that pop out in the right-hand view.

For more information on SIP messages, see [Direct Routing protocols](direct-routing-protocols-sip.md).

### Troubleshooting with the SIP call flow

For guidance in diagnosing issues, see [Diagnose issues with Direct Routing](https://learn.microsoft.com/microsoftteams/troubleshoot/phone-system/direct-routing/diagnose-direct-routing-issues).

For referencing SIP response codes, see [Microsoft and SIP response codes](https://learn.microsoft.com/microsoftteams/troubleshoot/phone-system/direct-routing/microsoft-sip-response-codes).

## See also

[Plan Direct Routing](direct-routing-plan.md)

[Configure Direct Routing](direct-routing-configure.md)

[Direct Routing - SIP protocol](direct-routing-protocols-sip.md)