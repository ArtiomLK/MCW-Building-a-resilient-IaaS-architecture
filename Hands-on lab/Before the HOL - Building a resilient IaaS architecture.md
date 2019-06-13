![Microsoft Cloud Workshops](https://github.com/Microsoft/MCW-Template-Cloud-Workshop/raw/master/Media/ms-cloud-workshop.png "Microsoft Cloud Workshops")

<div class="MCWHeader1">
Building a resilient IaaS architecture
</div>

<div class="MCWHeader2">
Before the hands-on lab setup guide
</div>

<div class="MCWHeader3">
June 2019
</div>


Information in this document, including URL and other Internet Web site references, is subject to change without notice. Unless otherwise noted, the example companies, organizations, products, domain names, e-mail addresses, logos, people, places, and events depicted herein are fictitious, and no association with any real company, organization, product, domain name, e-mail address, logo, person, place or event is intended or should be inferred. Complying with all applicable copyright laws is the responsibility of the user. Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.

Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document. Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.

The names of manufacturers, products, or URLs are provided for informational purposes only and Microsoft makes no representations and warranties, either expressed, implied, or statutory, regarding these manufacturers or the use of the products with any Microsoft technologies. The inclusion of a manufacturer or product does not imply endorsement of Microsoft of the manufacturer or product. Links may be provided to third party sites. Such sites are not under the control of Microsoft and Microsoft is not responsible for the contents of any linked site or any link contained in a linked site, or any changes or updates to such sites. Microsoft is not responsible for webcasting or any other form of transmission received from any linked site. Microsoft is providing these links to you only as a convenience, and the inclusion of any link does not imply endorsement of Microsoft of the site or the products contained therein.

© 2019 Microsoft Corporation. All rights reserved.

Microsoft and the trademarks listed at <https://www.microsoft.com/en-us/legal/intellectualproperty/Trademarks/Usage/General.aspx> are trademarks of the Microsoft group of companies. All other trademarks are property of their respective owners.

**Contents**

- [Building a resilient IaaS architecture before the hands-on lab setup guide](#building-a-resilient-iaas-architecture-before-the-hands-on-lab-setup-guide)
  - [Requirements](#requirements)
  - [Before the hands-on lab](#before-the-hands-on-lab)
    - [Task 1: Create a Virtual Machine using the Azure portal](#task-1-create-a-virtual-machine-using-the-azure-portal)
    - [Task 2: Connect to the VM and download the student files](#task-2-connect-to-the-vm-and-download-the-student-files)
    - [Task 3: Install Azure PowerShell](#task-3-install-azure-powershell)
  - [Summary](#summary)

# Building a resilient IaaS architecture before the hands-on lab setup guide 

## Requirements

1.  Microsoft Azure Subscription

2.  Virtual Machine Built during this hands-on lab or local machine with the following:

    - Latest Azure PowerShell cmdlets:
        - <https://azure.microsoft.com/en-us/downloads/>
        - <https://docs.microsoft.com/en-us/powershell/azure/install-azurerm-ps>
        - Ensure you reboot after installing the SDK or Azure PowerShell may not work correctly.

## Before the hands-on lab

Duration: 30 minutes

In this exercise, you deploy a Lab VM and configure the tools needed to complete the rest of your lab.

### Task 1: Create a Virtual Machine using the Azure portal 

1.  Launch a browser and navigate to <https://portal.azure.com>. Once prompted, login with your Microsoft Azure credentials. If prompted, choose whether your account is an organization account or just a Microsoft Account.

    >**Note**: You may need to launch an \"in-private\" session in your browser if you have multiple Microsoft Accounts.

2.  Click on **+ Create a resource**, and in the search box, type in **Visual Studio 2019** and press Enter. Click the Visual Studio Community 2019 image on Windows Server 2019 and with the latest release.

3.  In the returned search results, click the image name.
   
    ![In the Azure Portal, in the Everything blade, the Search field is set to Visual Studio Community 2019 on Windows Server 2019 (x64). In the Results section, Visual Studio Community 2019 on Windows Server 2019 (x64) is selected.](images/Setup/2019-06-13-17-38-41.png "Azure Portal Everything blade")

4.  At the top of the page in the Marketplace solution blade, click **Create**.

    ![In the Marketplace Solution blade click Create.](images/Setup/2019-06-13-17-40-12.png "Marketplace Solution blade")

5.  Set the following configuration on the Basics tab:

    -   Subscription: **If you have multiple subscriptions choose the subscription to execute your labs in**.
    -   Resource Group (create new): **OPSLABRG**
    -   Virtual machine name: **LABVM**
    -   Location: **Choose the closest Azure region to you**.
    -   Size: **D2S\_V3 Standard**
    -   Username: **demouser**
    -   Password: **demo\@pass123**
    -   Public inbound ports: **Allow selected ports**
    -   Select inbound ports: **RDP**

    ![Fields in the Basics tab display the previously defined settings.](images/Setup/2019-06-13-17-45-08.png "Basics tab")

    >**Note**: If you are using a trial subscription or one that you know has a restriction on the number of cores, you may use a smaller virtual machine size such as DS1\_V2.

6.  Select the **Management** tab. Choose your local timezone and select an auto-shutdown time that will not impact your work on the lab. Click **Review + create**.

    ![The management tab with default options shown for shutdown time and time zone.](images/Setup/2019-06-13-17-53-20.png "Management tab")

7.  On the **Review + create** tab, click **Create**.

    ![Azure portal screenshot showing the Review + create tab of the VM create experience.](images/Setup/2019-06-13-17-56-02.png "Review + create")

8.  The deployment should begin provisioning. It may take more than 10 minutes for the virtual machine to complete provisioning.

    ![The Deploying Visual Studio Community 2019 notice displays.](images/Setup/2019-06-13-17-58-11.png "Deploying Visual Studio Community 2019")

    >**Note**: Once the deployment is complete, move on to the next exercise.

### Task 2: Connect to the VM and download the student files

1.  In the Azure portal, browse to **LABVM** and wait for it to show the Status of **Running**. Click **Connect** to establish a new remote desktop session.

    ![On the Azure Portal menu bar, Connect is selected.](images/Setup/2019-06-13-18-03-42.png "Azure Portal")

2.  Depending on your remote desktop protocol client and browser configuration, you will either be prompted to open an RDP file, or you will need to download it followed by opening it up separately to connect. You may also be required to click, **Use a different account**.

    ![In the Windows Security dialog box, Use a different account is selected.](images/Setup/image15.png "Windows Security dialog box")

3.  Login with the credentials specified during creation:

    -   User: **demouser**
    -   Password: **demo\@pass123**

4.  You will be presented with a remote desktop connection warning because of a certificate trust issue. Click, **Don't ask me again for connections to this computer** followed by **Yes** to continue with the connection.

    ![The Remote Desktop Connection warning window displays with the message that the identity of the remote computer cannot be verified, and asking if you want to continue anyway. the Don't ask me again for connections to the computer checkbox is selected.](images/Setup/image16.png "Remote Desktop Connection warning window")

5.  When logging on for the first time, you will see a prompt on the right asking about network discovery. Click **No**.

    ![On the Networks page, the No button is selected.](images/Setup/image17.png "Networks page")

6.  Notice that Server Manager opens by default. On the left, click **Local Server**.

    ![Local Server is selected in the Server Manager menu.](images/Setup/image18.png "Server Manager menu")

7.  On the right side of the pane, click **On** by **IE Enhanced Security Configuration**.

    ![In the Essentials section, IE Enhanced Security Configuration is set to On, and is selected.](images/Setup/image19.png "Essentials section")

8.  Change to **Off** for Administrators and click **OK**.

    ![Administrators is set to Off in the IE Enhanced Security Configuration dialog box.](images/Setup/image20.png "IE Enhanced Security Configuration dialog box")

9.  In the lower left corner, click Internet Explorer to open it. On first use, you will be prompted about security settings. Accept the defaults by clicking **OK**.

    ![In the Internet Explorer 11 dialog box, the option to Use recommended security, privacy, and compatibility settings is selected.](images/Setup/image21.png "Internet Explorer 11 dialog box")

10. If prompted, click **Don't show this again** regarding protected mode.

11. To download the exercise files for the hands-on lab, paste this URL into the browser:

    https://cloudworkshop.blob.core.windows.net/resilient-iaas-hackathon/Building_Resilient_Iaas_Hackathon_Student_Files.zip  

12. You will be prompted about what you want to do with the file. Select **Save**.

    ![In the Internet Explorer dialog box, the Save button is selected.](images/Setup/image22.png "Internet Explorer dialog box")

    >**Note**: If you are blocked from downloading the file with a "Your security settings do not allow this file to be downloaded" alert, you will need to adjust the security settings for IE to allow downloads. Click **Settings > Internet Options**, and then select the **Security** tab. Click the **Custom level...** button and enable both **File download** and **Font download**. Click **OK**, and then **OK** again. Re-paste the URL into the browser and download. 

13. Download progress is shown at the bottom of the browser window. When the download is complete, click **Open folder**.

    ![On the Download Complete bar, the Open folder button is selected.](images/Setup/image23.png "Download Complete bar")

14. The **Downloads** folder will open, ***Right-click*** the zip file, and click **Extract All**. In the **Extract Compressed (Zipped) Folders** window, enter **C:\\HOL** in the **Files will be extracted to this folder** dialog. Click the **Extract** button.

### Task 3: Install Azure PowerShell

1. Open a PowerShell prompt as an administrator (Right click > More > Run as administrator).

2. Execute the following command:

    ```powershell
    Install-Module -Name AzureRM -AllowClobber
    ```

    ![The first time you use the PSGallery you will see a message related to an untrusted repository. Answer Yes or Yes to all to complete the installation..](images/Setup/image28.png "PSGallery untrusted repository")

    >**Note**: By default, the PowerShell gallery isn't configured as a trusted repository for PowerShellGet. The first time you use the PSGallery you will see a message related to an untrusted repository. Answer *Yes* or *Yes to all* to complete the installation.

## Summary

In this exercise, you setup a lab virtual machine, downloaded the required setup files, and installed Azure PowerShell. 

You should follow all steps provided *before* attending the Hands-on lab.
