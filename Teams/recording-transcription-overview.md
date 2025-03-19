---
title: Overview- Recording and transcription for Teams meetings and calls
ms.reviewer: lisma, harinlee, wanqincao, yujin1
ms.date: 3/19/2025
ms.topic: article
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.service: msteams
ms.subservice: meetings
ms.custom: intro-overview
audience: admin
f1.keywords:
- NOCSH
ms.collection: 
- M365-collaboration
- remotework
- m365initiative-meetings
- m365initiative-meetings-enabler
- m365initiative-voice
- enabler-strategic
- highpri
ms.localizationpriority: medium
search.appverid: MET150
appliesto: 
  - Microsoft Teams
description: Understand recording and transcription policies available for meetings and calls in Microsoft Teams.
---

# Overview: Recording and transcription for Teams meetings and calls

**APPLIES TO:** ![Image of a checkmark for yes](/office/media/icons/success-teams.png) Meetings ![Image of a checkmark for yes](/office/media/icons/success-teams.png) Webinars ![Image of a checkmark for yes](/office/media/icons/success-teams.png) Town halls ![Image of a checkmark for yes](/office/media/icons/success-teams.png) Group and 1:1 calls

In Microsoft Teams, your users can record and transcribe their meetings, events, and calls. Transcription automatically turns spoken dialogue into written text, making it easy to review or share key discussions later.  Recording captures audio, video, and screen-sharing activities, allowing users to revisit or share the full meeting experience as needed.  The user's ability to control whether their meetings and calls are recorded is known as convenience recording. To understand the different types of recordings in Teams, see [Introduction to recording Microsoft Teams calls and meetings](teams-recording-policy.md). As an admin, you can manage convenience recording and transcription for meetings and calls in your organization through policy settings.

Teams meeting policies control the user permissions for recording and transcription in meetings, events, and group calls, while Teams voice calling policies control the same permissions, but for 1:1 calls. 1:1 calls include both internal and external native Teams calls and Public Switched Telephone Network (PSTN) calls. If your users use both Teams meetings and Teams calls, it’s important to consider matching the policy settings for both meeting and calling scenarios.

For example, let’s say your organization’s finance team shouldn’t record or transcribe calls and meetings. You turn off recording and transcription in the calling policy and assign it to users in the finance team. However, because you didn’t update or assign a specific meeting policy to those users, their meeting settings default to the global policy, where recording and transcription for meetings and group calls are on by default. This means that while the finance team can’t record or transcribe 1:1 calls, they can still record and transcribe meetings and group calls because a custom meeting policy wasn’t created and assigned to them. For consistent recording and transcription settings across both meetings and 1:1 calls, it’s important to configure and assign both meeting and calling policies appropriately.

To learn more about assigning policies to both users and groups in your organization, see [Assign policies to users and groups](assign-policies-users-and-groups.md).

The following sections outline the policy settings and features you can use to manage recording and transcription in your organization.

> [!NOTE]
> When you make changes to the Global policy, they apply to everyone in your organization, except for users with an assigned custom meeting or calling policy.

## Manage recording and transcription for meetings and group calls

|Feature/setting|Admin controls|Documentation|
|:------|:-----|:---------|
|Recording|Allow or prevent meeting and group call recording for users, groups, or your entire organization.|No control|
|[Anonymous participants](anonymous-users-in-meetings.md)|Manage how anonymous attendees access Teams meetings in your org.|**(Public preview)** can prevent anonymous users from joining specific meetings if admin allows.|
|[Anonymous users can join a meeting after verifying (Teams Premium- Public preview)](anonymous-users-in-meetings.md#anonymous-users-can-join-a-meeting-after-verifying-with-an-email-code-public-preview-for-teams-premium)|**(Public preview)** Manage whether anonymous users can verify themselves with a one-time passcode to join meetings in your org.|**(Public preview)** If admin allows, can require anonymous to verify themselves with a one-time passcode to join specific meetings.|
|[Attendance and engagement reports](/microsoftteams/teams-analytics-and-reports/meeting-attendance-report)|Can enforce on or off or allow organizer to choose.|Can turn on or off if allowed by admin.|
|[Audio and video](meeting-policies-audio-and-video.md)|Can set audio and video modes and network settings.|Can allow or prevent attendee mic and cameras.|
|[Best practice configurations dashboard](best-practice-dashboard.md)|Manage and monitor your environment for Teams meetings and highlight locations that aren't following best practice configurations.|No control.|
|[Breakout rooms](https://support.microsoft.com/office/use-breakout-rooms-in-microsoft-teams-meetings-7de1f48a-da07-466c-a5ab-4ebace28e461)|No control|Can create and manage breakout rooms.|
|[CART captions](https://support.microsoft.com/office/use-cart-captions-in-a-microsoft-teams-meeting-human-generated-captions-2dd889e8-32a8-4582-98b8-6c96cf14eb47)|No control|Can set up and offer Communication access real-time translation(CART) captioning to participants instead of the Microsoft Teams built-in live captions that are automatically generated.|
|[Channel meeting scheduling](https://support.microsoft.com/office/schedule-a-meeting-in-microsoft-teams-943507a9-8583-4c58-b5d2-8ec8265e04e5)|No control|Can schedule meetings from channels.|
|[Chat](manage-meeting-chat.md)|Can manage whether users in the org can read and write chat messages. You can also manage chat messages in Teams meetings hosted by other organizations that you don’t have a trusted relationship with.|Can manage whether chat is available for their meetings.|
|[Choose co-organizers](https://support.microsoft.com/office/schedule-a-meeting-in-microsoft-teams-943507a9-8583-4c58-b5d2-8ec8265e04e5)|No control|Can assign different meeting roles in a Teams meeting to give users specific permissions.|
|[Collaboration features](meeting-policies-content-sharing.md)|Can control the availability of PowerPoint Live, whiteboard, and shared notes.|No control|
|[Compliance recording](teams-recording-policy.md)|Can implement an admin policy for automatic recording.|No control|
|[Content sharing](meeting-who-present-request-control.md)|Can control sharing mode and who can request control and can set a default for who can present.|Can control who can present.|
|[Convenience recording](meeting-recording.md)|Can allow or prevent meeting recording and set recording expiration time.|If the admin allows recording, organizers can manage who can record (Teams Premium) and automatic recording.|
|[Custom backgrounds (Teams Premium)](custom-meeting-backgrounds.md)|Can upload images for your users to display in the background of their video feed during meetings.|Can use backgrounds the admin uploaded.|
|[Decorate my background (Teams Premium)](https://adoption.microsoft.com/microsoft-teams-premium/decorate-your-background/)|No control|Organizers and participants can use AI to decorate their backgrounds.|
|[eCDN for view-only meetings](streaming-ecdn-enterprise-content-delivery-network.md)|Can manage and configure the availability of eCDN for organizers. Admins can also turn off the Microsoft eCDN for view-only meeting organizers with a Premium license and switch to a partner eCDN provider.| No control|
|[End-to-end encryption (Teams Premium)](end-to-end-encrypted-meetings.md) |Can allow or prevent end-to-end encryption.|Can enforce end-to-end encryption if allowed by the admin.|
|[Feedback surveys for anonymous participants](meeting-surveys-anonymous-participants.md)| Manage whether anonymous participants who join meetings hosted in your org can rate their meeting experience through surveys.  |No control|
|[Green room](https://support.microsoft.com/office/5b744652-789f-42da-ad56-78a68e8460d5)|No control|Can choose if green room is used for a meeting. Can use the **End meeting** button to end the meeting for attendees while allowing organizers and presenters to stay in the green room until they're ready to leave.|
|[Hide attendee names (Teams Premium)](hide-attendee-names.md) |Can control whether organizers with a Premium license can hide the names and photos of attendees from other attendees in the stage, roster, and chat. | Can hide attendee names during meetings to protect identities and privacy. |
|[Intelligent meeting recap (Teams Premium and Microsoft 365 Copilot)](intelligent-recap-calls-meetings.md) |Assigned licenses and transcription policies control this feature.|No control. Organizers, co-organizers, presenters, and participants can access intelligent recap after the meeting ends.|
|[Join verification check](join-verification-check.md) | Can require human verification checks for anonymous users to join meetings in your org.|No control|
|[Language interpretation](https://support.microsoft.com/office/use-language-interpretation-in-microsoft-teams-meetings-b9fdde0f-1896-48ba-8540-efc99f5f4b2e) |No control |Can turn on language interpretation settings for a meeting, add interpreters before the meeting, and designate interpreters during the meeting.|
|[Limit presenter role permissions](presenter-role-reduction.md) |Can limit presenter role permissions for the tenant. |No control|
|[Live translated captions (Teams Premium)](meeting-transcription-captions.md) |Can control whether organizers with a Premium license can have live translated captions for their meetings. |Can turn on live translated captions for themselves; attendees can always turn on live translated captions. |
|[Live translated transcription (Teams Premium)](meeting-transcription-captions.md) |Can control whether organizers with a Premium license can have live translated transcription for their meetings. |Can enable live translated transcription for themselves; attendees can always turn on live translated transcription. |
|[Manage what attendees see (Teams Premium)](https://support.microsoft.com/office/manage-what-attendees-see-in-teams-meetings-19bfd690-8122-49f4-bc04-c2c5f69b4e16)|No control|Can decide whose avatars or video feeds to spotlight during the town hall.|
|[Manage who can present and request control](meeting-who-present-request-control.md) |Control who can present in meetings and whether participants and external participants can request control of the presentation.|Can manage who can present in their meeting options.|
|[Meeting join and lobby](who-can-bypass-meeting-lobby.md)|Can set the defaults for new meetings.|Can choose meeting join and lobby settings for each meeting.|
|[Meeting themes (Teams Premium)](meeting-themes.md)|Can define meeting themes, including colors, images, and logo.|Can turn the admin-defined theme on or off.|
|[Microsoft Teams Rooms (Windows) can join as a presenter](https://support.microsoft.com/office/microsoft-teams-rooms-windows-e667f40e-5aab-40c1-bd68-611fe0002ba2)|No control.| Can add Microsoft Teams Rooms on Windows with a Pro license as a presenter when they set **Who can present** to **Organizer or co-organizer only** or **Specific people**. Microsoft Teams Rooms see, but can't send chat messages. Organizers must add Microsoft Teams Rooms from external organizations as external presenters.|
|[Outlook add-in](outlook-add-in-authentication-policy-requirements.md)|Can control whether users can schedule meetings from Outlook.|If admin allows, can schedule meetings from Outlook.|
|[Prevent copying or forwarding chat, captions, and transcripts (Teams Premium)](manage-chat-sensitive-meetings.md#prevent-copying-or-forwarding-chat-captions-and-transcripts)|Can prevent copying or forwarding of chat contents by using a meeting template or sensitivity label.|Can manage options if admin doesn't lock label or template settings. |
|[Prevent users from joining external meetings](external-meeting-join.md)|Can control which types of Microsoft Teams meetings your users can join.|No control|
|[Prevent users from sharing content in external meetings (Teams Premium)](block-external-content-share.md)|Can control which types of external Microsoft Teams meetings your users share content in.|No control|
|[Q&A](manage-qna-for-teams.md)|Can manage if organizers can use Q&A in meetings.|Can decide if Q&A is available for their meetings if allowed by admins.|
|[Quality of service (QoS)](meetings-real-time-media-traffic.md)|Can prioritize real-time network traffic that's sensitive to network delays over traffic that's less sensitive.|No control|
|[Reactions](manage-reactions-meetings.md)| Manage whether reactions can be used in meetings created by organizers with this policy. |Can control whether reactions can be used in their meetings. |
|[Recording storage and permissions](manage-reactions-meetings.md)| Manage recording storage and permissions. |Permissions depend on admin settings. |
|[Real time telemetry](use-real-time-telemetry-to-troubleshoot-poor-meeting-quality.md)|Can look at your users’ scheduled meetings and see audio, video, content sharing, and network-related issues. You can use this telemetry to investigate these issues during meetings and troubleshoot in real time.|No control|
|[Restrict who can record and transcribe (Teams Premium)](manage-meeting-recording-options.md#manage-who-can-record-and-transcribe-meetings-teams-premium)| Can restrict which users can record by using a meeting template or sensitivity label. |Can manage options if admin doesn't lock label or template settings. |
|[RTMP-In (Teams Premium)](meetings-rtmp-in.md)|Can control whether organizers can use RTMP-In for their meetings. |Can produce their Teams meetings directly from an external hardware or software-based encoder to integrate different types of media. To start streaming from the encoder, organizers can choose RTMP-In from their meeting options and then access the RTMP link and key. |
|[Scheduling](manage-who-can-schedule-meetings.md)|Can define who can schedule private and channel meetings.|Can schedule meetings if allowed by admin.|
|[Sensitivity labels](manage-who-can-schedule-meetings.md)|Can create sensitivity labels for Teams meetings.|Can apply your sensitivity label to meeting invites from Outlook or Teams. Recipients in your organization see the sensitivity label and all recipients see any headers or footers as configured content markings. Optionally, the meeting invite can be encrypted so only authorized people can see it and access the meeting link. Usage rights can further restrict access, for example, preventing the invite from being forwarded.|
|[Speaker Coach](meeting-speaker-coach.md)|Manage whether users in your organization can use Speaker Coach during meetings and events.|No control- all participants can use Speaker Coach if the admin allows.|
|[Transcription and captions](meeting-transcription-captions.md)|Can allow or prevent transcription and closed captions for attendees.|Can enable captions.|
|[Video effects](meeting-policies-audio-and-video.md#participants-can-use-video-effects)|Control whether users can customize their video background.|If the admin allows, organizers and meeting participants can blur their video background, choose from the default set of images, or upload custom images to use as their background.|
|[View-only](view-only-meeting-experience.md)|Allow organizers to host large meetings where after the meeting reaches around 900 users, additional attendees join with a view-only experience.|No control|
|[Voice isolation](voice-isolation.md)|Can control whether users can use voice isolation in meetings and calls.|Can enable voice isolation.|
|[Watermarks (Teams Premium)](watermark-meeting-content-video.md)|Can allow or prevent watermarks for attendee video and shared content|Can enforce watermarks if the admin allows.|

## Related articles

- [Meetings, webinars, and town halls feature comparison](meeting-webinar-town-hall-feature-comparison.md)

- [Plan for Teams webinars](plan-webinars.md)

- [Plan for Teams town halls](plan-town-halls.md)

- [Overview of meetings, webinars, and town halls](quick-start-meetings-live-events.md)
