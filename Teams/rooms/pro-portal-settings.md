---
title: Managing Teams Rooms on Windows settings
author: mstonysmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: kimmatlock
ms.date: 2/21/2025
ms.topic: article
audience: Admin
ms.service: msteams
ms.subservice: itpro-rooms
appliesto: 
  - Microsoft Teams
ms.collection: 
  - M365-collaboration
  - teams-rooms-devices
  - Tier1
ai-usage: ai-assisted  
ms.localizationpriority: medium
search.appverid: MET150
description: This article provides guidance on how to manage your Teams Rooms on Windows devices. It outlines the application settings that can be applied directly on the device and synchronized with the Teams Rooms Pro management portal, or alternatively, configured from the Teams Rooms Pro management portal to the device.
---

# Managing Microsoft Teams Rooms on Windows Devices Using Teams Rooms Pro Management Portal

In the Teams Rooms Pro management portal, you can configure application settings for individual Teams Rooms on Windows devices, provided you have the necessary role-based access control permissions for Rooms Management. For more information, see [role-based access control in the Microsoft Teams Rooms Pro Management portal](/microsoftteams/rooms/rooms-pro-rbac).

## How it Works

Teams Rooms devices have application settings that can either be applied on the device and synchronized with the Teams Rooms Pro management portal, or applied from the Teams Rooms Pro management portal to the device.

In the Teams Rooms Pro management portal, certain Teams Rooms application settings can be changed from the **Rooms detail settings** pane. Applying these changes require restarting the Teams Rooms application on the device to apply the setting change.

The Microsoft Teams Rooms on Windows application uses a SkypeSettings.XML configuration file to manage application settings on the device. When settings are changed on the device, a synchronization task updates the Teams Rooms Pro management portal settings for that device. Synchronization may take up to 15 minutes to reflect the changes.

## Changing Settings

After changing a setting and pressing the **Apply** button, a dialog box will present two options:

- **Apply Now** - Queues a job to apply the setting and restarts the device as soon as possible to apply the setting changes. This process can take several minutes. A banner is displayed to indicate that a settings change has been initiated, along with the number of settings changes jobs that are queued. The **Apply Now** option won't be available for devices actively in use.
- **Schedule Later** - Schedules the settings change to be applied during the nightly maintenance window to avoid disrupting scheduled meetings during business hours.

## Settings Job History

Since setting changes from the Teams Rooms Pro management portal to the Teams Rooms device aren't in real-time, there will be a delay. An indicator is visible next to any setting that is pending a change as a visual cue that a job has started to make the change to the device.

To provide visibility to the Teams Rooms Pro management technician, there's a **Settings Job History** activity under the **Activity** tab on the Rooms detail panel. This indicates the stage of settings change. An entry is made for every setting change initiated by a user or by the Teams Rooms Pro management service.

### Device Settings Job History Detail

By clicking on a Settings Job history row, a Device settings job panel is displayed with details about the device settings changes.

| Field Name   | Description                                                                                                       |
|--------------|-------------------------------------------------------------------------------------------------------------------|
| Job ID       | A unique ID assigned to the settings job                                                                          |
| Status       | Contains one of the following values: Submitted, Running, Completed, Completed with errors, Canceled, or Failed  |
| Submitted On | Date and Time when the job was submitted                                                                          |
| Submitted by | Indicates the individual who initiated the settings change or the Teams Rooms Pro systems' Managed Rooms Service. |
| Settings     | Displays the name of the settings that were changed                                                               |
| Reason       | SEE TABLE BELOW                                                                                                   |

### Settings Job Reasons

| Status                | Reason                | Reason Description                                                                                                                                                  | Action                                                                                                                                                                                                                                                  |
|-----------------------|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Submitted             | PENDING CONNECTION    | Device is disconnected, will execute the job after the device reconnects.                                                                                           | Ensure that the device is connected.                                                                                                                                                                                                                    |
| Submitted             | SCHEDULED             | Job was successfully created.                                                                                                                                       | None. The job is scheduled and will run when the device is available or in the nightly maintenance window.                                                                                                                                              |
| Running               | IN PROGRESS           | Job was sent down to the agent, and is pending a response back.                                                                                                     |                                                                                                                                                                                                                                                         |
| Completed             | SUCCESS               | Job successfully completed on the agent, and verification of settings application was done.                                                                         | Settings validation can take up to 10 minutes to reflect in the Teams Rooms Pro management portal.                                                                                                                                                      |
| Canceled             | CANCELLED             | User canceled the Job.                                                                                                                                             | Coming soon.                                                                                                                                                                                                                                            |
| Completed With Errors | APP RESTART FAILED    | XML with new settings has been written to the correct location, but an issue occurred in the app restart process. To complete the process, the device was rebooted. | Reapply the settings.                                                                                                                                                                                                                                  |
| Completed With Errors | VERIFICATION FAILED   | XML with new settings has been written, and the app was successfully restarted, but the settings weren't applied correctly.                                        | The settings change couldn't be verified. Check that the settings changed. A retry will be scheduled by the Managed room service for the nightly maintenance window.                                                                                   |
| Failed                | EXISTING XML FOUND    | An existing XML was found on the device and the agent was unable to create a new XML due to conflicts.                                                              | Restart the device to apply the existing SkypeSettings.XML on the device or remove it. See [Remotely manage Microsoft Teams Rooms device settings](/microsoftteams/rooms/remotely-manage-teams-rooms-device-settings). |
| Failed                | FAILED TO WRITE XML   | The agent failed to write an XML to the correct location.                                                                                                           | Reapply the settings change.                                                                                                                                                                                                                           |
| Failed                | FAILED                | General failures outside of the specified error codes.                                                                                                              | Reapply the settings change.                                                                                                                                                                                                                           |
| Failed                | SETTINGS FETCH FAILED | Unable to fetch the new settings from the service.                                                                                                                  | Reapply the settings change.                                                                                                                                                                                                                           |
| Failed                | DEVICE IN MEETING     | Device is currently in a meeting.                                                                                                                                   | Try again later.                                                                                                                                                                                                                                        |
| Failed                | DEVICE DISCONNECTED   | Device was disconnected when we attempted to execute the settings change, so no changes occurred.                                                                   | Reapply the settings change.                                                                                                                                                                                                                           |

## Settings Available

Teams Rooms devices have settings that can either be applied on the device and synchronized with the Teams Rooms Pro management portal or from the Teams Rooms Pro management portal to the device. Here are the settings that are visible in the portal:

### About

- Device ID: Unique device identifier (Information Only)
- Agent version: Current Pro Management Agent version (Information Only)
- Last agent activity: Last known time Pro Management agent connected with the Service (Information Only)
- OS Version: Current Windows operating system build (Information Only)
- IP Address: Device IP address detected (Information Only)
- BIOS Manufacturer: Name of BIOS manufacturer (Information Only)
- BIOS Name: BIOS Update name (Information Only)
- Latitude: Coordinates of the device derived by Windows location settings on device (Information Only)
- Longitude: Coordinates of the device derived by Windows location settings on device (Information Only)
- Time Zone: Provided by Microsoft for use with Windows and the .NET TimeZoneInfo class (Information Only)
- Time Zone (IANA): Time zones provided by IANA (Information Only)

### Account

- Exchange Sign in address: Device's resource account sign-in address (Information Only)
- Supported Meeting Mode: Teams Only are displayed (Information Only)
- Public Preview: Enrolls device into Teams Ring3.6. Enabling this setting enables Public Preview features on your Teams Rooms device. Use caution as devices in early preview rings aren't supported by Microsoft Support.

### Meetings

- Default content layout in single display mode: Set the default content layout for single display mode. Meeting participants can change the default content layout during meetings.
- Show Meeting Chat: Enabled by default. If disabled, meeting chat functionality (including chat bubbles and chat selection) isn't available in any meeting layout on the Teams Rooms device.
- Open Chat by Default: Enabled by default. Checkbox won't be visible if Show Meeting Chat is disabled. If disabled, chat panel won't show by default in meetings using Gallery view.
- Front Row Experience: Enabled by default. If false, Front row is disabled. For more information, see [Set front row as the default layout](/microsoftteams/rooms/set-front-row-as-default-layout).
- Default Layout Experience: Select the default meeting join layout as Gallery or Front Row.
- Front Row Video Size: Sets the size of Front row to provide more or less space for remote participant video and shared content.
- Right front row panel: Configure the position of the raised hand and chat components in the meeting panels to the left and right of meeting content on front-of-room displays.
- Left front row panel: Configure the position of the raised hand and chat components in the meeting panels to the left and right of meeting content on front-of-room displays.
- Automatic Screen sharing: Disabled by default. If true, a connected HDMI ingest will be automatically shared on the Front of Room display and when in a Teams Meeting it's automatically shared to remote participants. If false, a connected HDMI ingest will be automatically shared on the Front of Room display in and out of a Teams meeting but it will not be shared to remote participants in the meeting automatically, users need to select the share icon to shared content to remote participants.
- Show meeting name: Enabled by default. If disabled, the meeting name is hidden from the console and Front of Room calendar displays.
- Autoleave if everyone else left the meeting: Disabled by default. If true, device will automatically leave the meeting if it's the only participant in the meeting for more than 5 minutes before or after the scheduled meeting time.
- HDMI ingest audio sharing: Disabled by default. When disabled, audio from a connected HDMI ingest isn't shared to Teams Meeting participants.
- Enable room capacity notifications: Enabled by default. Enabled by default to provide warnings to in room participants that the room has reached capacity (this requires the room capacity be set in Exchange and a camera capable of people counting). Set to false if you wish to disable these warnings.
- Show Captions: Disabled by default. When enabled, captions will be displayed.
- Filter Profane words in captions and transcripts: Enabled by default. When captions are on, use of profane words are redacted.
- Enable People Count: Enabled by default. If true, people count will be enabled for Teams Rooms.
- Require passcode for all Teams meetings: Disabled by default. If true, users are required to enter the correct meeting ID and passcode to join all Teams meetings scheduled in the room with a Microsoft Teams Room Pro license.
- Require passcode for all Private Teams meetings: Disabled by default. If true, users are required to enter the correct meeting ID and passcode to join all private Teams meetings scheduled in the room with a Microsoft Teams Room Pro license.
- Join third-party meetings: May require calling plan to enable. For more information, see [Join third-party meetings](/microsoftteams/rooms/third-party-join?tabs=MTRW).
- Join with room info: Uses conference room account info to join third party meetings.
- Join with custom info: Disabled by default. If this value is set to true, you must specify both CustomDisplayNameForThirdPartyMeetings and CustomDisplayEmailForThirdPartyMeetings must be specified.
- Show Room Facilitator QR code: Disabled by default.

### Device

Dual Monitor mode: Disabled by default. Dual screen mode is enabled. Otherwise, the device uses single screen mode.

Allow content duplication: Disabled by default. When checkbox is selected, content is shown on both screens in dual screen mode, when out of meeting.

Enable Resolution and Scaling: Disabled by default. If true, the display resolution and scale setting will be applied. This setting affects both the main front-of-room display and extended front-of-room display once this setting is enabled. For more information, see [Remotely configure layout, scale, and resolution on Teams Rooms displays](/microsoftteams/rooms/remotely-configure-layout-scale-resolution).

Main Front of Room Display Resolution (Width): Enter a value. The width entered could be unsupported. Valid resolutions (width x height) are: 1920x1080, 2560x1080, 3840x2160, 3840x2560, 5120x2160. Note: Any changes are applied to the device. However, in the Settings Job History, it results in a Completed with Errors message.

Main Front of Room Display (Height): Enter a value. The height entered could be unsupported. Valid resolutions (width x height) are: 1920x1080, 2560x1080, 3840x2160, 3840x2560, 5120x2160. Note: Any changes are applied to the device. However, in the Settings Job History, it results in a Completed with Errors message.

Main Front of Room scaling: Input numeric value of scaling. Valid values are 100 (recommended), 125, 150, 175, 200, 225, 250, and 300. If you input greater than 300 and your front-of-room display only supports up to 300, it's set to 300. For more information, see [Remotely configure layout, scale, and resolution on Teams Rooms displays](/microsoftteams/rooms/remotely-configure-layout-scale-resolution).

Extended Front of Room Display Resolution (width): Enter a value. The width entered could be unsupported. Valid resolutions (width x height) are: 1920x1080, 2560x1080, 3840x2160, 3840x2560, 5120x2160. Note: Any changes are applied to the device. However, in the Settings Job History, it results in a Completed with Errors message.

Extended Front of Room Display Resolution (height): Enter a value. The height entered could be unsupported. Valid resolutions (width x height) are: 1920x1080, 2560x1080, 3840x2160, 3840x2560, 5120x2160. Note: Any changes are applied to the device. However, in the Settings Job History, it results in a Completed with Errors message.

Extended Front of Room scaling: Input numeric value of scaling. Valid values are 100 (recommended), 125, 150, 175, 200, 225, 250, and 300. If you input greater than 300 and your front-of-room display only supports up to 300, it's set to 300. For more information, see [Remotely configure layout, scale, and resolution on Teams Rooms displays](/microsoftteams/rooms/remotely-configure-layout-scale-resolution). Note: Any changes are applied to the device. However, in the Settings Job History, it results in a Completed with Errors message.

Disable Split video gallery: Default is false. This setting is only applicable

## Related articles
- 
- 
- 
- 