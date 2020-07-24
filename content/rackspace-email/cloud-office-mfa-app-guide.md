---
permalink: cloud-office-mfa-app-guide.md/
audit_date:
title: Multifactor Authentication App Setup
type: article
created_date: '2020-07-24'
created_by: Nicholas Ramirez
last_modified_date: '2020-07-24'
last_modified_by: Nicholas Ramirez
product: Rackspace Email
product_url: rackspace-email
---

### Prerequisites

- **Applies to:** Administrator and User
- **Difficulty:** Easy
- **Time Needed:** Approximately 15 minutes
- **Tools Needed:** Internet Browser (Google Chrome, Microsoft Edge, Mozilla Firefox, Safari) to sign into the Cloud Office Control Panel, and a mobile device with an active network connection (Cellular or Wi-Fi).

For more information about prerequisite terminology, see [Cloud Office support terminology](/how-to/cloud-office-support-terminology).

Multi-factor authentication (MFA) requires users to provide a second form of authentication when accessing their account. This second form of authentication is an additional layer of security and minimizes the chances of account compromise.

MFA for both the Cloud Office Control Panel and Rackspace Email Webmail can be configured to use an authenticator app. When configuring MFA for the first time, users are presented with an option to receive an SMS text message or use an Authenticator App. You can use any Time-based One Time Password (TOTP) app, and there are many options available for both desktop and mobile devices. This article provides an overview of a few options that you can use and instructions for configuring your account on each.

**Warning:** These applications are third party and Rackspace does not own or provide support for these apps. Use of these applications is at your own discretion.

#### Microsoft Authenticator for iOS and Android

Use the following steps to configure the Microsoft Authenticator mobile app for use with your Cloud Office Control Panel admin login:

1.	**Install** the Microsoft Authenticator application from the iOS App Store or the Android Google Play Store.

2.  Once the Microsoft Authenticator application has been successfully installed, **Open** the application itself, and select **Scan QR Code** when prompted. If the Microsoft Authenticator application has been set up previously, you can tap the three vertical dots in the top-right corner of the application, select **+ Add Account**, and then choose **Other account** to continue.

**Note:** When selecting 'Scan QR Code', your device may prompt you to allow the Microsoft Authenticator app to take pictures or video - this is necessary to scan the QR code in the following steps.

3.  After selecting **Scan QR Code**, navigate to the [Cloud Office Control Panel](cp.rackspace.com) and enter your admin credentials in the fields provided, then select **Log In**.

4.  Once logged in, you will be prompted to **Choose Your Multi-Factor Authentication Method** - in order to proceed, select the option **Use an Authenticator**, and then press **Continue**.

5.  Next, you will be provided with a QR code to scan, as well as a field for a six digit code - **Scan** the QR code with the **Microsoft Authenticator** application, and the account will be automatically added to the list of available accounts within the authenticator app itself.

6.  After successfully scanning the QR code, tap the account which was just added to the authenticator app - from here, you will be presented with the six digit code mentioned in the previous step. Enter the six digit code displayed by the Microsoft Authenticator app within the field provided to you in the Cloud Office Control Panel, and then select **Verify Code** to continue.

7.  Once you have verified the six digit code, you will be prompted with a message stating that multi-factor authenticator has been set up successfully, and you can now select **Got It** to begin performing administrative tasks within the Cloud Office Control Panel.

**Note:** You can have a direct link to the application on the app store sent to your device by going to https://www.microsoft.com/en-us/account/authenticator#getapp and entering your phone number.

### Google Authenticator for iOS and Android

Use the following steps to configure the Google Authenticator mobile app for use with your Cloud Office Control Panel admin login:

1.  **Install** the Google Authenticator application from the iOS App Store or the Android Google Play Store.

2.  After successfully installing the Google Authenticator mobile application, **Open** the application itself, and select **Get Started** when prompted.

3.  Next, when prompted to **Setup Your First Account**, select **Scan QR Code** - if you have previously configured the Google Authenticator application for use with another account, select the **+** icon in the bottom-right corner of the app, and then select **Scan a QR Code** to continue.

**Note:** When selecting 'Scan QR Code', your device may prompt you to allow the Google Authenticator app to take pictures or video - this is necessary to scan the QR code in the following steps.

4.  After selecting **Scan QR Code**, navigate to the [Cloud Office Control Panel](cp.rackspace.com) and enter your admin credentials in the fields provided, then select **Log In**. Once logged in, you will be prompted to **Choose Your Multi-Factor Authentication Method** - in order to proceed, select the option **Use an Authenticator**, and then press **Continue**.

5.  You will now be prompted with a QR code to scan, as well as a field to enter a six digit code - to proceed, **scan** the QR code provided by the Cloud Office Control Panel with the Google Authenticator mobile application.

6.  After scanning the QR code, you will then be prompted with a six digit number displayed by the Google Authenticator application - enter this number into the field provided via the Cloud Office Control Panel, then select **Verify Code** to continue.

7.  Once the code has been verified, the setup has been successfully completed - simply hit **Got It** when prompted to be taken into the Cloud Office Control Panel.

### Authy for iOS and Android

Use the following steps to configure the Authy mobile app for use with your Cloud Office Control Panel admin login:

1.	Download Authy (Twilio Authy 2-Factor Authentication) from the iOS App Store or the Android Google Play Store.

2.  Once Authy has been installed successfully, **Open** the application - you will then be prompted to enter a phone number to continue. Enter a valid phone number within the field provided, and then select **Ok**.

3.  After entering your phone number, you will then be prompted to verify your account through one of the following options: Phone call, SMS, or 'Use Existing Device' - for first time setup, select **SMS**, then enter the code you have received when prompted by Authy.

4.  Now that Authy has been successfully configured for first time use, tap the three vertical lines within the top-right corner of the application, select **Add Account**, and then **Scan QR Code** when prompted.

**Note:** When selecting 'Scan QR Code', your device may prompt you to allow the Authy mobile app to take pictures or video - this is necessary to scan the QR code in the following steps.

5.  After selecting **Scan QR Code**, navigate to the [Cloud Office Control Panel](cp.rackspace.com) and enter your admin credentials in the fields provided, then select **Log In**.

6.  Once logged in, you will be prompted to **Choose Your Multi-Factor Authentication Method** - in order to proceed, select the option **Use an Authenticator**, and then press **Continue**.

7.  Next, you will be provided with a QR code to scan, as well as a field to enter a six digit code - **Scan** the QR code displayed in the Cloud Office Control Panel with the Authy mobile authenticator app, assign a name to the account when prompted by Authy, and then tap **Save**.

8.  Once the account has been successfully added to Authy, enter the six digit code displayed by the authenticator application into the field provided via the Cloud Office Control Panel - after entering the code, select **Verify Code** to continue.

9.  After successfully verifying the code, select **Got It** to be taken into the Cloud Office Control Panel.

**Note:** You can have a direct link to the application on the app store sent to your device by going to https://authy.com/download/ and entering your phone number.

### Authy for Mac and PC

If a mobile authenticator application is not a viable option, you can choose to use the desktop version of Authy as an alternative by following the steps listed below:

1.  To begin, navigate to https://authy.com/download/ and scroll towards the bottom half of the page - select the appropriate operating system (macOS, Windows 32/64bit, or Linux) under the **Desktop - Direct Download** field, then select **Download**.

2.  After selecting **Download**, you will be prompted to run the **Authy Desktop Setup** executable file - open the file, and select **Run**.

3.  Once Authy has been successfully installed and opened, you will be prompted to enter a phone number to continue - enter a valid phone number, and then select **SMS** when prompted with **Get Verification Via...**.

4.  Once the verification code arrives to your mobile device via SMS, enter the code within the field provided via the Authy desktop application.

5.  After successfully entering the code, you can then select the **+** symbol within the Authy desktop application to begin adding a new account.

6.  When prompted for a **Code given by the website**, navigate to the [Cloud Office Control Panel](cp.rackspace.com) within your web browser, enter your admin credentials in the fields provided, and then select **Log In**.

7.  Once logged in, you will be prompted to **Choose Your Multi-Factor Authentication Method** - to proceed, select the option **Use an Authenticator**, and then press **Continue**.

8.  Next, **Copy** the code provided under **Step 3 - Manually enter the secret key below in the app.** in the Cloud Office Control Panel, then **Paste** the code itself into the field provided via the Authy desktop application - finally, select **Add Account**.

9.  After selecting **Add Account** in the Authy desktop application, you will be prompted to assign a name, as well as select an icon to help identify the account within the app - after this, you can enter the six digit code provided by Authy into the appropriate field within the Cloud Office Control Panel.

10.  Once you have successfully verified the code within the Cloud Office Control Panel, select **Got It** on the following confirmation window to be taken directly into the Cloud Office Control Panel.

### Additional Suggestions

1.  If you are unable to **Log In** to the Cloud Office Control Panel as you no longer have access to your previous authentication method, contact your administrator for assistance with resetting any existing authentication methods via the Cloud Office Control Panel.

2.  After successfully configuring multi-factor authentication for your Cloud Office Control Panel admin login, you can opt to add a **Backup Number** within the Cloud Office Control Panel as an alternate verification method. In the event that you are unable to utilize your primary authentication method, having a **Backup Number** can prevent you from having to reset your multi-factor authentication methods entirely.

3.  Once you have completed setting up a mobile authenticator application for your primary device, you can then configure other devices to use the same authentication method for your Cloud Office Control Panel admin login. Having access to a backup authentication method can mitigate potential inconveniences that may arise from temporarily losing access to your primary device.
