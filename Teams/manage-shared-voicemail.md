---
title: "Manage Shared Voicemail"
author: mkbond007
ms.author: mabond
manager: pamgreen
ms.reviewer: vijurtse
ms.date: 03/03/2025
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
  - M365-voice
  - m365initiative-voice
  - Tier1
audience: Admin
appliesto:
  - Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
  - Phone System
description: "Learn how to configure and manage Shared Voicemail for Auto Attendants and Call Queues."
---

# Manage Shared Voicemail for Auto Attendants and Call Queues

This article describes how to configure and manage Shared Voicemail for Auto Attendants and Call Queues. Shared Voicemail allows multiple users to access a single voicemail inbox.

For information about personal voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).

## Overview

Shared Voicemail is a specialized type of voicemail. While personal voicemail is sent to a single user, allowing only that individual to access the message automatically, shared voicemail is delivered to a group, enabling any member of that group to access the message.

Shared Voicemail integrates with Microsoft 365 Groups and can be accessed in Outlook or through the Calls section in a Microsoft Teams channel associated with the group. Although it can also connect to a distribution list or a mail-enabled security group, we recommend using a Microsoft 365 Group. Please refer to the table below for a comparison of the available options.

||Microsoft 365 Groups|Distribution groups|Mail-enabled security groups|
|:----|:----|:----|:----|
|**Shared Voicemails are visible in Outlook/Exchange**|Yes|Yes|Yes|
|**Shared Voicemail are visible in Teams**|Yes*|No|No|
|**Dynamic membership in Microsoft Entra ID**|Yes|No|No|

* Only if M365 Group is connected to a Call Queue via 365 Group associated channel.
  
With an M365 Group, Shared Voicemails are delivered to the group's associated folder. In contrast, when using a distribution list or a mail-enabled security group, each user receives a copy of the voicemail in their individual Inbox.

Your users can receive Shared Voicemail only through the redirection logic from Auto Attendants or Call Queues. For more information about Auto Attendants and Call Queues, see [Plan for Teams Auto attendants and Call queues](plan-auto-attendant-call-queue.md).

## Prerequisites

To manage Shared Voicemail, you must configure either a Microsoft 365 group, a distribution list, or a mail-enabled security group. We recommend using a Microsoft 365 group, so the documentation below focuses on this option.

Both private and public groups can be used with Shared Voicemail. However, if a group is public, anyone in your organization can get access the group and its associated information, including voicemails. 

There are several ways to create Microsoft 365 groups. We recommend one of the following methods:

**Create a Microsoft 365 group in the Admin Center**. Ensure that the group has both a mailbox and Teams support enabled.

**Create a Microsoft 365 group in Outlook**. Outlook groups have a mailbox enabled by default, but they might lack Teams support. For more information, see [Create a group in Outlook](https://support.microsoft.com/office/04d0c9cf-6864-423c-a380-4fa858f27102).

If your organization plans to view and manage Shared Voicemails in Microsoft Teams chats or other applications, make sure the Microsoft 365 group you are using has Teams support. Voicemails that are stored in Teams-supported groups are accessible via Microsoft Teams.

**Create a Microsoft 365 group in Microsoft Teams**. Note that Teams-based groups might have their mailbox hidden by default. To make the mailbox visible, use the [Set-UnifiedGroup](/powershell/module/exchange/set-unifiedgroup) cmdlet with the `-HiddenFromExchangeClientsEnabled` parameter to make a mailbox visible.

  ```powershell
  Set-UnifiedGroup -Identity <GUID> -HiddenFromExchangeClientsEnabled:$false
  ```

If you select a Microsoft 365 group that isn't supported by Teams, then your organization can only manage voicemails addressed to this group only in Outlook.

For more information about creating a group in Teams, see [Microsoft 365 Groups and Microsoft Teams](/microsoftteams/office-365-groups). For information about creating a group in Outlook, see [Create a group in Outlook](https://support.microsoft.com/office/04d0c9cf-6864-423c-a380-4fa858f27102).

For more information about groups, see [Overview of Microsoft 365 Groups for administrators](/microsoft-365/admin/create-groups/office-365-groups)

## Configure Shared Voicemail

As an administrator, you can configure Shared Voicemail for both Auto Attendants and Call Queues. We recommend using Microsoft 365 groups for these setups to ensure seamless integration with Shared Voicemail.

Only members of the designated Microsoft 365 group can access its associated Shared Voicemail. Each Shared Voicemail is linked to a single Microsoft 365 group.

To prevent oversharing of information, each specific Call Queue or Auto Attendant should have its own Microsoft 365 group for Shared Voicemail. If you configure call redirection so that multiple Call Queues with different agents share a common Shared Voicemail group, every user in that group will have permission to manage voicemails. This model can inadvertently lead to oversharing sensitive information. For this reason, we recommend creating a separate Shared Voicemail group for each individual Call Queue or Auto Attendant.

For more information, see [manage-your-call-queue-and-auto-attendant-settings-in-microsoft-teams](https://support.microsoft.com/office/52c741c6-8577-4faf-aa5a-c7853e0ab8f8).

### Auto Attendants

For Auto attendants, you can set up redirection rules to forward calls to a Shared Voicemail. For example, you might want to configure a rule to forward out-of-office hours calls to Shared Voicemail or to forward calls within a certain category directly to Shared Voicemail.

For Auto Attendant calls that are sent to Shared Voicemail, you can enable or suppress a system greeting. Custom greetings aren't available yet for auto attendants.

For more information about Auto Attendants, see [Set up a Microsoft Teams Auto attendant](create-a-phone-system-auto-attendant.md).

### Call Queues

Administrators or [Authorized users](create-a-phone-system-call-queue.md?tabs=authorized-users#tabpanel_1_authorized-users) of a Call Queue can set up custom Shared Voicemail greetings for the following features:

- Call overflow
- Call timeout
- No agents

You can also turn off custom greetings for call queues. Avoid including any special characters in the greeting messages of Shared Voicemail.

For more information about creating greetings for call queues, see [manage-voice-applications-policies](manage-voice-applications-policies.md).

For more information about redirecting Call Queues to Shared Voicemail, see [Call queue call exception handling](create-a-phone-system-call-queue.md?tabs=call-exception-handling) and [Additional messaging on Call queue call exception handling](create-a-phone-system-call-queue.md?tabs=call-exception-handling-additional-messaging).

## Location of Shared Voicemails

Shared Voicemails are accessible in both Microsoft Outlook and Microsoft Teams, although the Teams interface currently offers a more limited user experience.

### Microsoft Outlook

In Outlook, Shared Voicemails are stored either in the **Microsoft 365 group's folder** or in the **Inbox**, depending on the group type. For a Microsoft 365 group, users can find Shared Voicemails in the group's associated folder. For a distribution list or mail-enabled security group, a copy of each Shared Voicemail is delivered to every user's **Inbox**. Personal voicemails are typically found in user's **Inbox** or, in older versions of Outlook, under the **Voice mail** Search Folder.

Voicemails in Outlook are essentially regular emails containing specific voicemail data, an audio file attachment with the recorded message and message transcription. All voicemails are categorized with the type *Voicemail*, which enables you to apply rules specifically to these messages. For example, you can create a rule to move all emails with the *Voicemail* type to a separate folder. The standard functionality available for regular emails—such as deleting, marking as read/unread, applying message protection settings, categorizing, and flagging—is also available for voicemails.

For a more accurate automatic summary of voicemails using **Outlook Copilot**, consider organizing all voicemails in a separate folder. This allows you to instruct Copilot to summarize only the new messages in that specific folder.

For more information about organizing emails, setting rules, categories, flags, or reminders in Outlook, see the following articles:

- [Set categories, flags, or reminders](https://support.microsoft.com/office/a894348d-b308-4185-840f-aff63063d076)
- [Organize email by using folders in Outlook](https://support.microsoft.com/office/0616c259-4bc1-4f35-807d-61eb59ac79c1)
- [Set up rules in Outlook](https://support.microsoft.com/office/75ab719a-2ce8-49a7-a214-6d62b67cbd41)

### Microsoft Teams

In Microsoft Teams, Shared Voicemails are located under the **Calls** section of the Microsoft 365 group's associated Teams channel, while personal voicemails appear in your personal **Calls** tab. Note that you can only view Shared Voicemails that have been forwarded by a Call Queue connected to the Microsoft 365 Group channel, and the Call Queue's Microsoft 365 group must match the Voicemail's Microsoft 365 group.

## Related articles

[Set up Cloud Voicemail](set-up-phone-system-voicemail.md)

[Microsoft 365 Groups and Microsoft Teams](/microsoftteams/office-365-groups)

[Set-UnifiedGroup](/powershell/module/exchange/set-unifiedgroup)

[Create a group in Outlook](https://support.microsoft.com/office/04d0c9cf-6864-423c-a380-4fa858f27102)

[Plan for Teams Auto attendants and Call queues](plan-auto-attendant-call-queue.md)
