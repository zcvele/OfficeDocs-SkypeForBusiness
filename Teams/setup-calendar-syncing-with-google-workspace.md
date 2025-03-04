---
title:  Set up calendar syncing between Google Workspace and Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: jtremper
ms.topic: article
ms.date: 03/03/2025
ms.service: msteams
audience: admin
ms.collection: 
ms.reviewer: 
search.appverid: MET150
f1.keywords:
- NOCSH
description: Learn how to enable bidirectional calendar syncing between Google Workspace and Microsoft Teams.
appliesto: 
- Microsoft Teams
ms.localizationpriority: medium
---

# Set up calendar syncing between Google Workspace and Microsoft Teams for your small or medium business

If your small or medium business relies on Google Workspace for email and calendaring, you can enable bidirectional syncing with Microsoft Teams. Enabling sync reduces missed meetings and simplifies meeting management by ensuring events created in either platform are seamlessly reflected in both.

> [!NOTE]
> Currently, this set up is only available to small and medium business administrators with a Teams Essentials license.

## Prerequisites

- Be assigned Microsoft Global Admin role with a Teams Essentials license.
- Be sure all of your users added in Microsoft directory for whom you want to enable calendar sync for have licenses assigned.  
- Be sure that all users in the Microsoft directory for whom you want to enable calendar synchronization have a Microsoft subscription license assigned.
- Have the login credentials for your Google Workspace admin account (admin.google.com).
- Have the login credentials for your custom business domain host website (for example, GoDaddy).

## Choose the appropriate Setup Wizard

1. Sign into [Teams](https://teams.microsoft.com) using your Global Admin account.
1. Go to the [Admin app in Teams](https://teams.microsoft.com/dl/launcher/launcher.html).
1. If you've not already connected your custom business domain with Microsoft 365, select the **Use your existing email and custom domain with Teams** option on the Admin app home page.
1. If you've already connected your domain, select the **Set up calendar synchronization** option on the Admin app home page (and proceed to "Set up calendar synchronization").

## Use your existing email and custom domain with Teams

1. Choose **Google Workspace** on the email selection screen.
1. Review the overview page and select **Continue**.  
1. Enter your business domain and select **Verify**.

Teams attempts to detect your domain host provider and prompt you to sign into your account. This authorization is solely for verifying domain ownership and doesn't involve any DNS changes. There are two methods to verify ownership.

**If your domain is hosted at a common registrar, such as GoDaddy, WordPress, or 1&1 IONOS, you have the option to sign in to that registrar and give Microsoft permission to set up your domain for you.**
1. Select **Verify**.
1. Sign in to your registrar if prompted, and then select **Authorize Microsoft to conduct verification**.
1. Return to Microsoft Teams and the custom domain setup task.

**To manually verify ownership and configure DNS records, follow the instructions in Add DNS records to connect your domain.**

1. Sign out of Teams and sign back in with your updated email.

    Your work remains intact and your Microsoft 365 password stays the same. If you encounter issues, allow time for the process to complete and try again.

1. After you sign back into Teams using your business email, return to the Admin app in Teams, and to the custom domain setup task, to update email addresses for other users.
1. Next, you'll move to the calendar synchronization process. Follow the steps outlined in "Set up calendar synchronization."

## Set up calendar synchronization

1. Review the Calendar sync **Overview** page and select **Get Started**.
1. Before moving forward in the Setup Wizard in Microsoft Teams, you must install an application in Google Marketplace that will authorize Microsoft to access your Google user directory and manage their calendars. To do this, select the **Go to Google Workspace Marketplace** button to go to the Google Workspace Marketplace, choose **Install**, and follow the steps to authorize access. These permissions are used solely for calendar synchronization.
1. After the installation, return to the Setup Wizard in Teams. Select the **I have installed the Microsoft 365 Mail Migration app** checkbox in Google Workspace and select **Next**.
1. When prompted, sign in to your Google Workspace administrator account. Select the **Sign in to Google Workspace** button, enter your credentials in the pop-up diaslog box, and follow the instructions to sign in and provide consent.

    Once you've successfully signed in, you may get a loading screen as the system pulls the Google user-account details and performs matching with the corresponding Microsoft user accounts.  

1. Next, you'll see two tables. The first table shows you all the Google user accounts that could be auto-matched with existing Microsoft user accounts based on user’s first name, last name, and email address. The second table contains a list of Google user accounts that could not be auto-matched. For unmatched users, select the existing Microsoft user account you would like to sync the Google account with from the provided drop-down.
1. Once you're satisfied with all user account matching, be sure you've selected the checkboxes for the users for whom you want you to enable bi-directional calendar synchronization, and select **Next**.  
1. Review all Google user accounts matched with their corresponding Microsoft user accounts. Carefully check each match. An incorrect pairing could result in users gaining access to each other’s calendar events. Also, mismatches can lead to data privacy issues and unintended calendar access. Once you've thoroughly reviewed and confirmed the matches, to initiate calendar synchronization, select **Start Sync**.
1. The calendar-synchronization process might take up to 30 minutes to begin. After reviewing the information on the final page, select **Finish & View Users page** to navigate to the **Users** page. Form there, you can monitor and manage the sync status for each user.
