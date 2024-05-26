<b>Configure team site libraries to sync automatically:</b>

This setting is used to specify what SharePoint team to sync automatically the next time users sign in to OneDrive app. May take up to 8 hrs after the user signs in before syncing starts.

I have created a HR SharePoint site and added a “HR_dept” dynamic group as a member.

Go to “Endpoint manager” > Configuration > Create 
Fine “Configure team site libraries to sync automatically” > Enabled

To specify a library to sync:

Open a web browser, sign in to Office 365 as a global or SharePoint admin for your organization, and browse to the library to sync.


Click the "Sync" button on the library you want to sync automatically, and then click "Copy library ID."

![onedrive3](https://github.com/stahir131/SharePoint-Sync-in-Intune/assets/64047385/a10e908a-3806-46c2-978e-2451fe8c3186)

Click "Show", and then enter a friendly name to identify the library in the Value Name field and then enter the library ID in the Value field.

![onedrive4](https://github.com/stahir131/SharePoint-Sync-in-Intune/assets/64047385/2ed0d2ba-49ee-4e28-aa56-492694ff5590)

Assign devices to the policy and create.
