---  
title: "Facilitator in Teams Rooms"  
author: mstonysmith
ms.author: tonysmit  
manager: pamgreen
ms.reviewer:   
ms.date: 03/11/2025  
ms.topic: article
audience: admin  
ms.service: msteams  
ms.subservice: itpro-rooms  
ms.localizationpriority: Medium
ms.collection:
ms.custom: QuickDraft  
search.appverid: MET150  
f1.keywords:
- NOCSH 
ai-usage: ai-assisted
description: This user guide provides comprehensive instructions on utilizing Facilitator within Teams Rooms, highlighting its role as a collaborative communication tool during meetings conducted through Teams Rooms.

---  

# Using Facilitator in Microsoft Teams Rooms

[!INCLUDE [Preview feature](../includes/preview-feature.md)]

The facilitator feature in Microsoft Teams Rooms enhances collaborative communication during in-person and hybrid meetings by using large language models (LLMs) to capture notes and improve productivity. This article provides a comprehensive guide on utilizing the facilitator feature.

The facilitator feature in Microsoft Teams Rooms enhances collaborative communication during in-person and hybrid meetings by using large language models (LLMs) to capture notes and improve productivity. This guide provides comprehensive instructions on utilizing the facilitator feature.

## Overview of Facilitator in Microsoft Teams Rooms

Facilitator is a collaborative communication agent available in Teams meetings. It combines the power of LLMs and Teams data to record notes and help users stay productive during a meeting. The feature is currently available in public preview.

## Using Facilitator for Offline/Ad Hoc Meetings

Teams Rooms on Windows and Teams Rooms on Android can convert offline or unplanned in-person discussions to rich AI notes with summaries, action items, and speaker attribution.

### Discovery Experience

When the presence detector on Teams Rooms wakes up, a banner is displayed on the room display, informing users that they can invite the facilitator agent to take notes for their in-person meeting. This banner appears when there's no scheduled meeting in the room for at least the next 10 minutes.

:::image type="content" source="./media/facilitator/facilitator-1-low-res.png" alt-text="Screenshot of the discovery experience." lightbox="./media/facilitator/facilitator-1-hi-res.png":::

### Inviting Facilitator for Note Taking

To invite the facilitator agent to take notes:

- Scan the QR code on the top left of the display,
- Press the **Facilitator** button on the home screen of the console and scan the QR code shown.

:::image type="content" source="./media/facilitator/facilitator-2-low-res.png" alt-text="Screenshot of the invitation experience." lightbox="./media/facilitator/facilitator-2-hi-res.png":::

After scanning the QR code on your mobile device, the Teams app will show an option to invite the facilitator with the room as the attendee. You can choose to drop off from the meeting on your phone to focus on your in-room discussion.

:::image type="content" source="./media/facilitator/facilitator-3-low-res.png" alt-text="Screenshot of the QR code experience." lightbox="./media/facilitator/facilitator-3-hi-res.png":::

### Meeting Experience

The meeting starts with the room invited and transcription turned on. The room display indicates that the facilitator is listening to the conversation and taking notes. After a few minutes, the screen will display notes summarizing the discussion. These notes continue to automatically update based on the ongoing conversation.

:::image type="content" source="./media/facilitator/facilitator-4-low-res.png" alt-text="Screenshot of the mobile experience." lightbox="./media/facilitator/facilitator-4-hi-res.png":::

To end the meeting, use the **End** button on the console. You can also invite remote participants by looking them up on the console.

:::image type="content" source="./media/facilitator/facilitator-5-low-res.png" alt-text="Screenshot of the listening experience." lightbox="./media/facilitator/facilitator-5-hi-res.png":::

:::image type="content" source="./media/facilitator/facilitator-6-low-res.png" alt-text="Screenshot of the meeting notes experience." lightbox="./media/facilitator/facilitator-6-hi-res.png":::

### Accessing Notes

To access the notes after the meeting, navigate to the **Recap** section in your Teams calendar or chat. The meeting is titled **Discussion with AI-generated notes in**.

:::image type="content" source="./media/facilitator/facilitator-7-low-res.png" alt-text="Screenshot of accessing notes experience." lightbox="./media/facilitator/facilitator-7-hi-res.png":::

### Known Limitations

Currently, only the user who scans the QR code to start the meeting is attributed in the transcription and notes. All other meeting participants in the room are identified as generic speakers (For example, Speaker 1, Speaker 2). This issue will be addressed in a future update.

## Using Facilitator in Scheduled Meetings

In a scheduled meeting with Teams Rooms on Windows or Teams Rooms on Android invited, you can view notes generated by the facilitator agent by turning on the **Notes** button on the console.

:::image type="content" source="./media/facilitator/facilitator-8-low-res.png" alt-text="Screenshot of the faciliator in scheduled meetings experience." lightbox="./media/facilitator/facilitator-8-hi-res.png":::

## Prerequisites for IT Admins

To enable the facilitator feature for meetings, follow these steps:

- Turn on Facilitator for meetings: [Set up Facilitator in Microsoft Teams](/microsoftteams/facilitator-teams)

:::image type="content" source="./media/facilitator/facilitator-10-low-res.png" alt-text="Screenshot of turning on facilitator in Teams Rooms Pro Management portal." lightbox="./media/facilitator/facilitator-10-hi-res.png":::

- Enable Loop experiences in Teams for AI-generated notes: [Manage Loop components in your organization](/microsoft-365/loop/loop-components-configuration)
- Enable public preview of Microsoft Teams Rooms in the Pro Management portal: [Pro Management Portal](/microsoftteams/rooms/rooms-pro-management)

:::image type="content" source="./media/facilitator/facilitator-9-low-res.png" alt-text="Screenshot of turning on public preview in Teams Rooms Pro Management portal" lightbox="./media/facilitator/facilitator-9-hi-res.png":::

## Frequently Asked Questions
- **Question** How do I turn on/off the facilitator agent feature in Rooms?  
**Answer** Navigate to **Room** -\> **Settings** -\> **Meeting** -\> **Facilitator QR Code** in the Teams Rooms Pro Management portal.
- **Question** How do I turn on/off public preview in Teams Rooms?  
**Answer** Navigate to **Room** -\> **Settings** -\> **Account** -\> **Enable public preview toggle** in the Teams Rooms Pro Management portal.
- **Question** Is this feature available in both Teams Rooms on Windows and Android?  
**Answer**This feature is available only as public preview on Teams Rooms on Windows starting late March 2025 and on Teams Rooms on Android in late April.
- **Question** Where do I access the notes after the meeting?  
**Answer** On your Teams calendar, navigate to the meeting -\> **Recap** section -\> **Notes**.
- **Question** Can I turn off facilitator during the discussion?  
**Answer** You can mute the microphone in the room to ensure the facilitator or transcription doesn't capture any content. You can also remove facilitator from the console by tapping it on the roster.
- **Question** Is the Facilitator agent recording the meeting?  
**Answer**The Facilitator agent only turns on transcription during the meeting. The meeting won't be recorded.
- **Question** How are the meeting room participants identified and attributed in AI notes and transcription?  
**Answer** Currently, only the person who scans the QR code to invite Facilitator is identified and attributed if they've enrolled their profile. Identity and attribution support for other room participants is coming soon.

## Related Articles

- [What is Responsible AI?](https://support.microsoft.com/topic/what-is-responsible-ai-33fc14be-15ea-4c2c-903b-aa493f5b8d92)
- [Frequently Asked Questions: AI, Microsoft Copilot, and Microsoft Designer](https://support.microsoft.com/topic/frequently-asked-questions-ai-microsoft-copilot-and-microsoft-designer-987b275d-f6f2-4d5d-94c5-e927cffae705)
- [Providing Feedback about Microsoft Copilot with Microsoft 365 Apps](https://support.microsoft.com/topic/providing-feedback-about-microsoft-copilot-with-microsoft-365-apps-c481c26a-e01a-4be3-bdd0-aee0b0b2a423?ocid=CopilotLab_SMC_Privacy_Feedback)