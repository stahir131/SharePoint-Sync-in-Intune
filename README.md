<p align="center">
<b>Configure team site libraries to sync automatically:</b>
</p>
This setup allows devices to automatically start syncing specified SharePoint libraries as soon as the OneDrive client connects, providing seamless access to shared document libraries. This may take up to 8 hrs after the user signs in before syncing starts.<br />

To automatically sync a SharePoint site library to Intune-managed Windows devices, you can use the OneDrive settings available in Configuration blade in Microsoft Endpoint Manager (Intune).  Here’s a step-by-step approach:

**Step 1: Configure OneDrive Settings in SharePoint**<br />
Login to **SharePoint** admin portal and locate the site to be synced.<br />
Go to the "**Documents**" and select "**Sync**" at the top<br />
Cancel out the "**Open Microsoft OneDrive**" window and select **Copy library ID** <br />
Save the ID for later use in Step 2.

![image](https://github.com/user-attachments/assets/9a3ca6ac-0c20-4b02-a869-53f5fa4d80cf)

**Step 2: Set up Intune Configuration**<br />
Go to “**Endpoint manager**” admin portal> **Devices** > **Configuration**<br />
Select **Create New policy**<br />
Platform: **Windows 10 and later**<br />
Profile type: **Template**<br />
Template name: **Administrative templates**<br /> and **Create**<br />

![image](https://github.com/user-attachments/assets/925a876c-684d-4cc3-8b29-5a103e1289dd)

Name: Give it a descriptive name and click **Next** to **Configuration settings**<br >
Click on **All Settings**> search for OneDrive > Select **Configure team site libraries to sync automatically**<br />
Select **Enabled** > Enter a a name for the library copy and paste the ID saved in Step 1 above.<br />
Click **OK**<br >
![image](https://github.com/user-attachments/assets/925b653a-9e55-4b2d-9fd9-fc0d0f463d56) 
<br />
Click Next and leave **Scope** as Default and Next **Assignment**<br />
**Assignment**: Assign a groups as required and **Create**

