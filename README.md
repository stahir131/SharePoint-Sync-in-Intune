## Configure team site libraries to sync automatically<br />
This setting lets you specify SharePoint team site libraries to sync automatically the next time users sign in to the OneDrive sync app. The OneDrive sync app will automatically download specified libraries as online-only files at the user's next sign-in, and users will not be able to stop the syncing of these libraries. Microsoft states that syncing may take up to 8 hours after the user signs in, though in my experience, it only took about 2 hours.<br />

**Requirements**
1. The setting requires that OneDrive Files On-Demand be enabled.<br />
2. Computer must be running Windows 10 (1709) Fall Creators Update or later<br />
3. Computer must be Intune-joined
 
To automatically sync a SharePoint site library to Intune-managed Windows devices, you can use the OneDrive settings available in the **Configuration** blade in Microsoft Endpoint Manager (Intune).  Here’s a step-by-step approach:

**Step 1: Configure OneDrive Settings in SharePoint**<br />
Login to **SharePoint** admin portal as global or SharePoint administrator and locate the library to be synced.<br />
Go to the "**Documents**" and select "**Sync**" at the top<br />
Cancel out the "**Open Microsoft OneDrive**" window and select **Copy library ID** <br />
The special characters in this copied string are in Unicode and must be converted to ASCII.<br />

To convert the Unicode to ASCII, open up a **PowerShell** and run this command below.
#### [uri]::UnescapeDataString("**Copied String**") <br />
replacing "Copied String" with the library ID you copied above and press Enter:<br /> 
Save the resulting ID for later use in Step 2.

  ![image](https://github.com/user-attachments/assets/9a3ca6ac-0c20-4b02-a869-53f5fa4d80cf)

**Step 2: Set up Intune Configuration**<br />
Go to “**Endpoint manager**” admin portal> **Devices** > **Configuration**<br />
Select **Create New policy**<br />
Platform: **Windows 10 and later**<br />
Profile type: **Template**<br />
Template name: **Administrative templates**<br /> and **Create**<br />

![image](https://github.com/user-attachments/assets/925a876c-684d-4cc3-8b29-5a103e1289dd)

Name: Give it a descriptive name and click **Next** to **Configuration settings**<br >
Click on **All Settings**> search for OneDrive > Select **Configure team site libraries to sync automatically(User)**<br />
Select **Enabled** > Enter a name for the library, copy and paste the ID saved in Step 1 above.<br />
Click **OK**<br >

![image](https://github.com/user-attachments/assets/31f48a66-c257-48ad-85c7-9f3aa2059820)

Again on search bar, type "Use OneDrive File On-Demand" and enable that as part of this configuration. You can enable as many settings as needed here.<br />

![image](https://github.com/user-attachments/assets/c7bafc33-3a19-4bf9-a938-0de15168db2b)
<br />
Click Next and leave **Scope** as Default and Next to the **Assignment**<br />
**Assignment**: Assign devices or users groups as required and **Create**<br />

The SharePoint library was synced to down to the user device after couple of hours as seen below.<br />

![image](https://github.com/user-attachments/assets/6e3952e6-1e53-445a-ab60-46a7b04bee7b)

Further reading at Microsoft [here](https://docs.microsoft.com/en-us/onedrive/use-group-policy#AutoMountTeamSites/)

