---
permalink: cloud-office-mfa-app-guide.md/
audit_date: '2020-07-27'
title: Multifactor Authentication App Setup
type: article
created_date: '2020-07-27'
created_by: Nicholas Ramirez
last_modified_date: '2020-07-27'
last_modified_by: William Loy
product: Rackspace Email
product_url: rackspace-email
---

### Prerequisites

- **Applies to:** Administrator and User
- **Difficulty:** Easy
- **Time Needed:** About 15 minutes
- **Tools Needed:** Internet Browser access and a mobile device with an active network connection

For more information about prerequisite terminology, see [Cloud Office support terminology](/how-to/cloud-office-support-terminology).

Multi-factor authentication (MFA) requires users to give a second form of authentication when accessing their account. This second form of authentication is an extra layer of security and minimizes the chances of account compromise.

MFA for both the Cloud Office Control Panel and Rackspace Email Webmail can use an authenticator app. When configuring MFA for the first time, users have the option to receive a Short Message Service (SMS) text message or use an authenticator app. You can use any Time-based One Time Password (TOTP) app. This article provides an overview of a few options that you can use and instructions for configuring your account on each.

**Warning:** These are third party apps which Rackspace doesn't own or support. Use of these apps is at your own discretion.

#### Microsoft Authenticator for iOS and Android

Use the following steps to configure the Microsoft Authenticator&reg; mobile app for use with your Cloud Office Control Panel admin login:

1. **Install** the Microsoft Authenticator app from the iOS App Store&reg; or the Android Google Play Store&reg;.

2. Open Microsoft Authenticator app itself, and select **Scan QR Code**. If the Microsoft Authenticator app is previously configured, you can tap the three vertical dots in the top-right corner of the app, select **+ Add Account**, and then choose **Other account** to continue.

    **Note:** When selecting **Scan QR Code**, you must allow the Microsoft Authenticator app to take pictures or video in order to scan the QR code in the following steps.

3.  After selecting **Scan QR Code**, navigate to the [Cloud Office Control Panel](cp.rackspace.com) and enter your administrator credentials in the fields provided, then select **Log In**.

4. Next, within the prompt **Choose Your Multi-Factor Authentication Method**, select the option **Use an Authenticator**, and then press **Continue**.

5. Scan the QR code that appears with the **Microsoft Authenticator** app. This automatically adds your account to the list of available accounts within the authenticator app itself.

6. Tap the account which was just added to the authenticator app. Next, enter the six digit code displayed by the Microsoft Authenticator app within the field provided to you in the Cloud Office Control Panel, and then select **Verify Code**.

7. When the code verifies a message appears stating that the multi-factor authenticator is set up successfully. You can now select **Got It** to begin performing administrative tasks within the Cloud Office Control Panel.

**Note:** You can have a direct link to the app on the app store sent to your device by going to https://www.microsoft.com/en-us/account/authenticator#getapp and entering your phone number.

### Google Authenticator for iOS and Android

Use the following steps to configure the Google Authenticator mobile app for use with your Cloud Office Control Panel administrator login:

1. **Install** the Google Authenticator app from the iOS App Store or the Android Google Play Store.

2. Open the Google Authenticator app itself, and select **Get Started**.

3. Next, when prompted to **Setup Your First Account**, select **Scan QR Code**. If the Google Authenticator app is previously configured, select the **+** icon in the bottom-right corner of the app, and then select **Scan a QR Code** to continue.

    **Note:** When selecting **Scan QR Code**, you must allow the Google Authenticator app to take pictures or video in order to scan the QR code in the following steps.

4. After selecting **Scan QR Code**, navigate to the [Cloud Office Control Panel](cp.rackspace.com) and enter your administrator credentials in the fields provided, then select **Log In**.

5. Next, within the prompt **Choose Your Multi-Factor Authentication Method**, select the option **Use an Authenticator**, and then press **Continue**.

6. Scan the QR code that appears with the Google Authenticator app. This automatically adds your account to the list of available accounts within the authenticator app itself.

7. Tap the account which was just added to the authenticator app. Next, enter the six digit code displayed by the Google Authenticator app within the field provided to you in the Cloud Office Control Panel, and then select **Verify Code**.

8. When the code verifies a message appears stating that the multi-factor authenticator is set up successfully. You can now select **Got It** to begin performing administrative tasks within the Cloud Office Control Panel.

### Authy for iOS and Android

Use the following steps to configure the Authy mobile app for use with your Cloud Office Control Panel administrator login:

1. Download Authy (Twilio Authy 2-Factor Authentication) from the iOS App Store or the Android Google Play Store.

2. Open Authy, then enter a valid phone number within the field provided, and then select **Ok**.

3. After entering your phone number, you must verify your account through by using one of the following options: 

    - Phone call 
    - SMS(text)
    - Use Existing Device 

    Select **SMS**, then enter the code you have receive when prompted by Authy.

4. Tap the three vertical lines in the top-right corner of the app, then select **Add Account**, and then **Scan QR Code**.

    **Note:** When selecting **Scan QR Code**, you must allow the Authy app to take pictures or video in order to scan the QR code in the following steps.

5.  After selecting **Scan QR Code**, navigate to the [Cloud Office Control Panel](cp.rackspace.com) and enter your administrator credentials in the fields provided, then select **Log In**.

6. Next, within the prompt **Choose Your Multi-Factor Authentication Method**, select the option **Use an Authenticator**, and then press **Continue**.

7. Scan the QR code that appears with the Authy app. This automatically adds your account to the list of available accounts within the authenticator app itself.

8. Tap the account which was just added to the authenticator app. Next, enter the six digit code displayed by the Authy app within the field provided to you in the Cloud Office Control Panel, and then select **Verify Code**.

9. When the code verifies a message appears stating that the multi-factor authenticator is set up successfully. You can now select **Got It** to begin performing administrative tasks within the Cloud Office Control Panel.

**Note:** You can have a direct link to the app on the app store sent to your device by going to https://authy.com/download/ and entering your phone number.

### Authy for Mac and PC

If a mobile authenticator app isn't an option, you can choose to use the desktop version of Authy as an alternative by following the steps listed below:

1. Navigate to https://authy.com/download/, select the appropriate operating system under the **Desktop - Direct Download** field, and then select **Download**.

2. After selecting **Download**, you must run the **Authy Desktop Setup** executable file by opening the file and selecting **Run**.

3. After installation  you must enter a phone number in the prompt to continue. Enter a valid phone number, and then select **SMS** from the **Get Verification Via...** prompt.

4. Enter the code sent to your mobile number within the appropriate field in the Authy desktop app.

5. Select the **+** symbol within the Authy desktop app to begin adding a new account.

6.  When the prompt **Code given by the website** appears, navigate to the [Cloud Office Control Panel](cp.rackspace.com) in your web browser. Next, enter your administrator credentials in the fields provided, and then select **Log In**.

7. Next, within the prompt **Choose Your Multi-Factor Authentication Method**, select the option **Use an Authenticator**, and then press **Continue**.

8. Copy the code provided in **Step 3 - Manually enter the secret key below in the app.** in the Cloud Office Control Panel, then paste the code  into the field provided via the Authy desktop app. 

9. Select **Add Account** in the Authy desktop app, assign a name, and select an icon to help identify the account within the app. Now you can enter the six digit Authy code into the appropriate field within the Cloud Office Control Panel.

10. When the code verifies a message appears stating that the multi-factor authenticator is set up successfully. You can now select **Got It** to begin performing administrative tasks within the Cloud Office Control Panel.

### Additional suggestions

- If you are unable to **Log In** to the Cloud Office Control Panel as you no longer have access to your previous authentication method, contact your administrator for assistance with resetting any existing authentication methods via the Cloud Office Control Panel.

- After successfully configuring multi-factor authentication for your Cloud Office Control Panel administrator login, you can opt to add a **Backup Number** within the Cloud Office Control Panel as an alternate verification method. In the event that you are unable to utilize your primary authentication method, having a **Backup Number** can prevent you from having to reset your multi-factor authentication method.

- You can configure more than one  device to use the same authentication method for your Cloud Office Control Panel. Having access to a backup authentication method can mitigate potential inconveniences that might arise from temporarily losing access to your primary device.
