<p align="center">
<b>Configure team site libraries to sync automatically:</b>
</p>
This setup allows devices to automatically start syncing specified SharePoint libraries as soon as the OneDrive client connects, providing seamless access to shared document libraries. This may take up to 8 hrs after the user signs in before syncing starts.<br />

To automatically sync a SharePoint site library to Intune-managed Windows devices, you can use the OneDrive settings available in Configuration blade in Microsoft Endpoint Manager (Intune).  Here’s a step-by-step approach:

**Step 1: Configure OneDrive Settings in SharePoint**
Login to SharePoint admin portal and locate the site to be synced.<br />
Go to the "**Documents**" and select "**Sync**" at the top<br />
Cancel out the "Open Microsoft OneDrive" window and select **Copy library ID** <br />
Save the ID for later use.

![image](https://github.com/user-attachments/assets/9a3ca6ac-0c20-4b02-a869-53f5fa4d80cf)

Go to “Endpoint manager” > Configuration > Create 

Find <b>“Configure team site libraries to sync automatically”</b>  -> Enabled

To specify a library to sync:

Open a web browser, sign in to Office 365 as a global or SharePoint admin for your organization, and browse to the library to sync.


Click the "Sync" button on the library you want to sync automatically, and then click "Copy library ID."

![onedrive3](https://github.com/stahir131/SharePoint-Sync-in-Intune/assets/64047385/a10e908a-3806-46c2-978e-2451fe8c3186)

Click "Show", and then enter a friendly name to identify the library in the Value Name field and then enter the library ID in the Value field.

![onedrive4](https://github.com/stahir131/SharePoint-Sync-in-Intune/assets/64047385/2ed0d2ba-49ee-4e28-aa56-492694ff5590)

Assign devices to the policy and create.
