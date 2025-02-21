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
ms.subservice: itpro-devices + itpro-rooms
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

In the Teams Rooms Pro management portal, you can configure application settings for individual Teams Rooms on Windows devices, provided you have the necessary role-based access control permissions for Rooms Management. For more information, see [role-based access control in the Microsoft Teams Rooms Pro Management portal](/microsoftteams/rooms/rooms-pro-management-portal-role-based-access-control).

## How It Works

Teams Rooms devices have application settings that can either be applied on the device and synchronized with the Teams Rooms Pro management portal or configured from the Teams Rooms Pro management portal to the device.

In the Teams Rooms Pro management portal, certain Teams Rooms application settings can be changed from the **Rooms detail settings** pane. These changes will require restarting the Teams Rooms application on the device to apply the setting change. The Microsoft Teams Rooms on Windows application uses a SkypeSettings.XML configuration file to manage application settings on the device.

The Teams Rooms Pro management users can make changes to settings through the Teams Rooms Pro management portal. The system will create a SkypeSettings.XML configuration file with the desired changes, transmit them to the device, orchestrate the restart of the Teams Rooms application on the device which consumes the SkypeSettings.XML, and verify that the changes were applied.

When settings are changed on the device, there is a synchronization task that updates the Teams Rooms Pro management portal settings for that device. Note that the synchronization may take up to 15 minutes to reflect the changes.

## Changing Settings

After changing a setting and pressing the **Apply** button, a dialog box will be presented with two options:

- **Apply Now:** This queues a job to apply the setting and will restart the device as soon as possible to apply the setting changes. This process can take several minutes. A banner will be displayed to indicate that a settings change has been initiated. It will also indicate the number of settings change jobs that are queued.
- **Schedule Later:** The settings change will be scheduled to be applied during the nightly maintenance window to avoid disrupting scheduled meetings during business hours.

Note: For devices that are actively in use when settings changes are being applied, the **Apply Now** option will not be available.

## Settings Job History

Since the setting changes from the Teams Rooms Pro management portal to the Teams Rooms device are not in real-time, there will be a delay. An indicator will be visible next to any setting that is pending a change as a visual cue that a job has started to make the change to the device.

To provide visibility to the Teams Rooms Pro management technician, there is a **Settings Job History** activity under the **Activity** tab on the Rooms detail panel to indicate the stage of settings change. An entry will be made for every settings change initiated by a user or by the Teams Rooms Pro management service.

| Field Name   | Description                                                                                                       |
|--------------|-------------------------------------------------------------------------------------------------------------------|
| Status       | Indicates the state of the settings job.                                                                          |
| Submitted on | Indicates the timestamp of the status.                                                                            |
| Submitted by | Indicates the individual who initiated the settings change or the Teams Rooms Pro systems' Managed Rooms Service. |
| Completed on | Indicates the timestamp when the job completed.                                                                   |

## Device Settings Job History Detail

By clicking on a Settings Job history row, a Device settings job panel will be displayed with details about the device settings changes.

| Field Name   | Description                                                                                                       |
|--------------|-------------------------------------------------------------------------------------------------------------------|
| Job Id       | A unique ID assigned to the settings job.                                                                         |
| Status       | Contains one of the following values: Submitted, Running, Completed, Completed with errors, Cancelled, or Failed. |
| Submitted On | Date and Time when the job was submitted.                                                                         |
| Submitted by | Indicates the individual who initiated the settings change or the Teams Rooms Pro systems' Managed Rooms Service. |
| Settings     | Displays the name of the settings that were changed.                                                              |
| Reason       | See the table below for details.                                                                                  |

### Settings Job Reasons

| Status                | Reason                | Reason Description                                                                                                                                                  | Action                                                                                                                                                                |
|-----------------------|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Submitted             | Pending Connection    | Device is disconnected, will execute the job after the device reconnects.                                                                                           | Ensure that the device is connected.                                                                                                                                  |
| Submitted             | Scheduled             | Job was successfully created.                                                                                                                                       | None. The job is scheduled and will run when the device is available or in the nightly maintenance window.                                                            |
| Running               | In Progress           | Job was sent down to the agent, and is pending a response back.                                                                                                     |                                                                                                                                                                       |
| Completed             | Success               | Job successfully completed on the agent, and verification of settings application was done.                                                                         | Settings validation can take up to 10 minutes to reflect in the Teams Rooms Pro management portal.                                                                    |
| Cancelled             | Cancelled             | User cancelled the Job.                                                                                                                                             | Coming soon.                                                                                                                                                          |
| Completed with Errors | App Restart Failed    | XML with new settings has been written to the correct location, but an issue occurred in the app restart process. To complete the process, the device was rebooted. | Re-apply the settings.                                                                                                                                                |
| Completed with Errors | Verification Failed   | XML with new settings has been written, and the app was successfully restarted, but the settings were not applied correctly.                                        | The settings change could not be verified. Check that the settings changed. A retry will be scheduled by the Managed room service for the nightly maintenance window. |
| Failed                | Existing XML Found    | An existing XML was found on the device and the agent was unable to create a new XML due to conflicts.                                                              | Restart the device to apply the existing SkypeSettings.XML on the device or remove it.                                                                                |
| Failed                | Failed to Write XML   | The agent failed to write an XML to the correct location.                                                                                                           | Re-apply the settings change.                                                                                                                                         |
| Failed                | Failed                | General failures outside of the specified error codes.                                                                                                              | Re-apply the settings change.                                                                                                                                         |
| Failed                | Settings Fetch Failed | Unable to fetch the new settings from the service.                                                                                                                  | Re-apply the settings change.                                                                                                                                         |
| Failed                | Device in Meeting     | Device is currently in a meeting.                                                                                                                                   | Try again later.                                                                                                                                                      |
| Failed                | Device Disconnected   | Device was disconnected when we attempted to execute the settings change, so no changes occurred.                                                                   | Re-apply the settings change.                                                                                                                                         |

## Settings Available

Teams Rooms devices have settings that can either be applied on the device and synchronized with the Teams Rooms Pro management portal or configured from the Teams Rooms Pro management portal to the device. The following settings are visible in the portal:

### About

| Field Name          | Description                                                                                    |
|---------------------|------------------------------------------------------------------------------------------------|
| Device ID           | Unique device identifier (Information Only).                                                   |
| Agent version       | Current Pro Management Agent version (Information Only).                                       |
| Last agent activity | Last known time Pro Management agent connected with the Service (Information Only).            |
| OS Version          | Current Windows operating system build (Information Only).                                     |
| IP Address          | Device IP address detected (Information Only).                                                 |
| BIOS Manufacturer   | Name of BIOS manufacturer (Information Only).                                                  |
| BIOS Name           | BIOS Update name (Information Only).                                                           |
| SMBIOSBIOSVersion   | Information Only.                                                                              |
| Latitude            | Coordinates of the device derived by Windows location settings on device (Information Only).   |
| Longitude           | Coordinates of the device derived by Windows location settings on device (Information Only).   |
| Time Zone           | Provided by Microsoft for use with Windows and the .Net TimeZoneInfo class (Information Only). |
| Time Zone (IANA)    | Time zones provided by IANA (Information Only).                                                |

### Account

| Field Name               | Description                                                                                                                                                                                                           |
|--------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Exchange Sign-In address | Device's resource account sign-in address (Information Only).                                                                                                                                                         |
| Supported Meeting Mode   | Teams Only will be displayed (Information Only).                                                                                                                                                                      |
| Public Preview           | Enrolls device into Teams Ring3.6. Enabling this setting will enable Public Preview features on your Teams Rooms device. Please use caution as devices in early preview rings are not supported by Microsoft Support. |

### Meetings

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Field Name</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Default content layout in single display mode</td>
<td><ul>
<li>Focus on Content and People</li>
<li>Focus on Content Only</li>
</ul>
Set the default content layout for single display mode. Meeting participants can change the default content layout during meetings.</td>
</tr>
<tr class="even">
<td>Show Meeting Chat</td>
<td>Enabled by default. If disabled, meeting chat functionality (including chat bubbles and chat selection) isn't available in any meeting layout on the Teams Rooms device.</td>
</tr>
<tr class="odd">
<td>Open Chat by Default</td>
<td>Enabled by default. Checkbox will not be visible if Show Meeting Chat is disabled. If disabled, chat panel will not show by default in meetings using Gallery view.</td>
</tr>
<tr class="even">
<td>Front Row Experience</td>
<td>Enabled by default. If false, Front row is disabled. For more information, see <a href="/microsoftteams/rooms/manage-front-row">Set front row as the default layout</a>.</td>
</tr>
<tr class="odd">
<td>Default Layout Experience</td>
<td>Front row default. Select the default meeting join layout as Gallery or Front Row.</td>
</tr>
<tr class="even">
<td>Front Row Video Size</td>
<td>Medium (default), Small, Large. Sets the size of Front row to provide more or less space for remote participant video and shared content.</td>
</tr>
<tr class="odd">
<td>Right front row panel</td>
<td>Show raised hand list, Show meeting chat, Hide the panel. Configure the position of the raise hand and chat components in the meeting panels to the left and right of meeting content on front-of-room displays.</td>
</tr>
<tr class="even">
<td>Left front row panel</td>
<td>Show raised hand list, Show meeting chat, Hide the panel.</td>
</tr>
<tr class="odd">
<td>Automatic Screen sharing</td>
<td>Disabled by default. If true, a connected HDMI ingest will be automatically shared on the Front of Room display and when in a Teams Meeting it will be automatically shared to remote participants. If false, a connected HDMI ingest will be automatically shared on the Front of Room display in and out of a Teams meeting but it will not be shared to remote participants in the meeting automatically. Users will need to select the share icon to share content to remote participants.</td>
</tr>
<tr class="even">
<td>Show meeting name</td>
<td>Enabled by default. If disabled, the meeting name is hidden from the console and Front of Room calendar displays.</td>
</tr>
<tr class="odd">
<td>Auto-leave if everyone else left the meeting</td>
<td>Disabled by default. If true, the device will automatically leave the meeting if it is the only participant in the meeting for more than 5 minutes before or after the scheduled meeting time.</td>
</tr>
<tr class="even">
<td>HDMI ingest audio sharing</td>
<td>Disabled by default. When disabled, audio from a connected HDMI ingest is not shared to Teams Meeting participants.</td>
</tr>
<tr class="odd">
<td>Enable room capacity notifications</td>
<td>Enabled by default. Enabled by default to provide warnings to in-room participants that the room has reached capacity (this requires the room capacity to be set in Exchange and a camera capable of people counting). Set to false if you wish to disable these warnings.</td>
</tr>
<tr class="even">
<td>Show Captions</td>
<td>Disabled by default. When enabled, captions will be displayed.</td>
</tr>
<tr class="odd">
<td>Filter Profane words in captions and transcripts</td>
<td>Enabled by default. When captions are on, use of profane words is redacted.</td>
</tr>
<tr class="even">
<td>Enable People Count</td>
<td>Enabled by default. If true, people count will be enabled for Teams Rooms.</td>
</tr>
<tr class="odd">
<td>Require passcode for all Teams meetings</td>
<td>Disabled by default. If true, users are required to enter the correct meeting id and passcode to join all Teams meetings scheduled in the room with a Microsoft Teams Room Pro license.</td>
</tr>
<tr class="even">
<td>Require passcode for all Private Teams meetings</td>
<td>Disabled by default. If true, users are required to enter the correct meeting id and passcode to join all private Teams meetings scheduled in the room with a Microsoft Teams Room Pro license.</td>
</tr>
<tr class="odd">
<td>Join third-party meetings</td>
<td><ul>
<li>Cisco Webex</li>
<li>Zoom</li>
<li>GoToMeetings</li>
<li>RingCentral Meetings</li>
<li>Amazon Chime</li>
</ul>
May require calling plan to enable. For more information, see <a href="/microsoftteams/rooms/third-party-join?tabs=MTRW">Third-party join</a>.</td>
</tr>
<tr class="even">
<td>Join with room info</td>
<td>Uses conference room account info to join third-party meetings.</td>
</tr>
<tr class="odd">
<td>Join with custom info</td>
<td>Disabled by default. If this value is set to true, you must specify both , .</td>
</tr>
<tr class="even">
<td>Show Room Facilitator QR code</td>
<td>Disabled by default.</td>
</tr>
</tbody>
</table>

### Device

Field Name

Description

## Related articles
- 
- 
- 
- 