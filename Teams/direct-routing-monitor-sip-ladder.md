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
description: "Analyze Microsoft Teams Direct Routing call flows with SIP ladder feature"
---

# Troubleshoot Microsoft Teams Direct Routing with SIP Call Flow 

The SIP Ladder, accessible within the Microsoft Teams Admin Center, provides a visual, chronological representation of the SIP signaling messages exchanged during Direct Routing calls. This tool aids administrators in diagnosing and resolving call flow issues by presenting a clear sequence of interactions between your organization's Session Border Controller (SBC) and the Microsoft SIP Proxy. 

https://learn.microsoft.com/en-us/microsoftteams/direct-routing-protocols-sip 



### Prerequisites

Permissions: You must have the appropriate administrative roles (e.g., Teams Administrator) to access the Teams Admin Center and view Direct Routing reports.

Direct Routing Configuration: Your Direct Routing environment must be correctly configured, with a properly connected and functioning SBC. 

### Access

Accessing SIP Ladder in Teams Admin Center

Sign In: Log in to the Microsoft Teams Admin Center (https://admin.teams.microsoft.com). 

Navigate to Usage Reports: In the left-hand navigation menu, go to Analytics & reports > Usage reports. 

Generate PSTN Report: Select 'PSTN Usage' report and select a desired timeframe and click on “Run Report”.  In the generated report, select “Direct Routing” tab. This report will list call records. 

View SIP Ladder: You can either select the desired call and click on the 'SIP Call Flow' button at the top left of the report or you can Click on the link below the 'Final SIP Code'. 

> [!NOTE] 
> Please allow up to 30 minutes for the SIP call data to be processed and uploaded to the Teams Admin Center for reporting.
> Call records older than 30 days will not have SIP Ladder information available.  

### Understanding the SIP Ladder Diagram 

The SIP Ladder visually represents the call flow as a series of interactions between your organization’s SBC and Microsoft SIP Proxy. Each "rung" of the ladder represents a SIP message (e.g., INVITE, 100 Trying, 180 Ringing, 200 OK, ACK, BYE) with the direction of the arrow indicating the sender and receiver of the message. Messages are displayed in chronological order from top to bottom, allowing you to follow the sequence of events during the call. 

For a comprehensive understanding of SIP messages and the SIP protocol used in Teams Phone Direct Routing, refer to the Direct Routing Protocols (SIP) documentation. 

Troubleshooting with the SIP Call Flow 

The SIP Ladder is invaluable for diagnosing a variety of Direct Routing issues. Here are a couple of common scenarios: 

Reference to this article will help -> SBC connectivity issues - Microsoft Teams | Microsoft Learn 

Call Setup Failures: If a call fails to connect, the SIP Ladder can quickly reveal the point of failure. For example: 

If an INVITE message is sent from the SBC but no response (e.g., 100 Trying, 180 Ringing, or 200 OK) is received, this indicates a problem between the SBC and the Microsoft SIP Proxy. Possible causes include network connectivity issues, SBC misconfiguration, or firewall problems. 

If a 200 OK is sent from the SIP Proxy to the SBC, but is not shown on the SIP Ladder, then this points to an issue where the SBC is not processing the 200 OK. 

If error responses like 4xx, 5xx, and 6xx are displayed, then more investigation will need to be done by clicking on the specific message to learn more. 

One-Way Audio: If users experience audio only in one direction, the SIP Ladder can help determine if the Session Description Protocol (SDP) information, which contains media details, was exchanged correctly. Examine the INVITE and 200 OK messages to verify that the SDP offer and answer was properly negotiated. Mismatched codecs or incorrect IP addresses in the SDP can lead to one-way audio. 

## See also

[Plan Direct Routing](direct-routing-plan.md)

[Configure Direct Routing](direct-routing-configure.md)
