
# Sign up for a new Microsoft account

In this task, you will create a new Microsoft account that you will use to sign up for an Office 365 E5 trial subscription.

When you sign up for an Office 365 E5 trial subscription, you need a Microsoft account that has never been used to sign up for a trial subscription. Creating a new Microsoft account ensures that you can create the Office 365 E5 trial subscription successfully. 

1. [] Sign in to the @lab.VirtualMachine(Win10-CL1).SelectLink virtual machine as +++Admin+++ by using +++Passw0rd!+++ as the password.

    >[!TIP]Select the +++Type Text+++ icon to enter the associated values into the virtual machine.


1. [] Open @[Microsoft Edge][Open URL0]{Shell}, and then go to +++https://outlook.com+++.

    >[!TIP]Select the lightning bolt icon to open Microsoft Edge automatically in the virtual machine and go directly to the specified URL.

1. [] Select **Create free account**.

1. [] Complete the wizard to create a new Microsoft account that uses either **outlook.com** or **hotmail.com** as the suffix.

    >[!NOTE] If you are prompted to stay signed in, select **Yes**.

1. [] Record the email address and password in the following text boxes:

    **Microsoft Account Email Address**     
    @lab.TextBox(MicrosoftAccountEmailAddress)

    **Microsoft Account Password**      
    @lab.TextBox(MicrosoftAccountPassword)

1. [] Record the new Microsoft account email address and password on your local computer, and then store them in a location to which you will have access for the remaining challenge labs in this series. 

    >[!KNOWLEDGE] A Microsoft account provides a single sign-on for Microsoft online services—for example, Outlook, OneDrive, and Microsoft Teams—as well as for devices running Microsoft operating systems, and for Microsoft applications—for example, Visual Studio.

===
# Deploy a Microsoft 365 tenant

In this task, you will deploy a Microsoft 365 tenant. First, you will review the Microsoft 365 subscription options. Next, you will sign up for an Office 365 E5 trial subscription. Finally, you will deploy a tenant in the Office 365 E5 trial subscription.

1. [] In Microsoft Edge, open a new tab, and then go to +++https://products.office.com/en-us/business/compare-more-office-365-for-business-plans+++.

    >[!KNOWLEDGE] This page includes descriptions of the plans available to enterprises. You can also review the plans available for [homes and small businesses](https://products.office.com/en-us/compare-all-microsoft-office-products?&activetab=tab%3aprimaryr2).

1. [] Review the Office apps and services included with each Office 365 plan.

1. [] On the Microsoft 365 Enterprise page, on the Office 365 E5 tile, select @[Learn more][Open URL2]{Shell}.

1. [] On the Office 365 E5 page, select **Free trial**.

1. [] In Let's get you started, in Email, enter +++@lab.Variable(MicrosoftAccountEmailAddress)+++, and then select **Next**.

    >[!NOTE] You will use the new Microsoft account you created to set up the free trial.

1. [] Select **Set up account**.

1. [] In Company name, enter +++Hexelo@lab.LabInstance.Id+++, in Company size, select **50-249 people**, and then complete the remainder of the form by using your own information.

1. [] Select **Next**.

1. [] In Tell us about yourself, select **Text me**, enter a phone number that you can use to receive text messages, and then select **Send verification code**.

1. [] Enter your verification code, and then select **Verify**.

1. [] In How you'll sign in, in Username, enter +++Microsoft365Admin+++. 

1. [] In Domain name, ensure that the value is set to +++Hexelo@lab.LabInstance.Id+++**.onmicrosoft.com**, and then select **Save**.  

    > [!KNOWLEDGE] The company name Hexelo@lab.LabInstance.Id becomes your tenant name. This name must be unique.

1. [] In Password and Confirm password, enter a secure password that you will remember for use in future challenge labs, and then record the password in the following text box:

    **Microsoft 365 Password**  
    @lab.TextBox(Password)

    >[!NOTE] This password is **NOT** saved after you complete this prerequisite lab.

1. [] Select **Next** to create the tenant.

    >[!NOTE] It will take approximately 1—2 minutes to create the tenant.

1. [] In confirmation details, review the username of the new tenant. 

    >[!ALERT] Make sure that you **save your username and your password**. You will need them for the challenge labs in this series. 
    >
    >Your user ID is ++Microsoft365Admin@Hexelo@lab.LabInstance.Id.onmicrosoft.com++. 
    >
    >Your password is ++@lab.Variable(Password)++.
    >
    >Please record this information in a separate location. It will not be saved after you finish this prerequisite lab.

    >[!TIP] Select the ++Copy to clipboard++ icon to copy the text string to the clipboard.

1. [] Select **Get Started**.

1. [] If prompted to install Office and add a domain, in the lower-right corner, select **Exit setup**.

1. [] If prompted to select a reason, select **I'm not ready to complete setup**, and then select **Send and exit**.


    >[!NOTE] Your Office 365 E5 trial subscription is valid for 30 days from the date on which you created it. As of this writing, you can extend your trial subscription for a 30-day period.
    
<!--- As of the time of writing, when you exit setup, you will be prompted for a reason. Select **I'm not ready to complete setup**, and then select **Send and exit**. This kind of prompt changes frequently enough that we don't need to include it. Users should be able to figure this out. If we get a lot of Help desk questions, we can always add this as a part of the final step. 
    1. [] If propmted to install Office and add a domain, select **Exit setup**, if prompted to select a reason, select **I'm not ready to complete setup**, and then select **Send and exit**.
--->


===
# Create users and groups by using a PowerShell script

In this task, you will run a Windows PowerShell&trade; script that will populate your Microsoft 365 tenant with users and groups for use in subsequent challenge labs.

1. [] On the taskbar, right-click **Windows PowerShell**, select **Run as Administrator**, and then in the User Account Control dialog box, select **Yes**.

1. [] Run the following command to change to the LabFiles folder:

    ```
    cd D:\LabFiles
    ```

1. [] Run the following command to create users and groups:

    ```
    .\CreateOnlineUsers.ps1
    ```

1. [] In User name, enter +++Microsoft365Admin@Hexelo@lab.LabInstance.Id.onmicrosoft.com+++, in Password, enter +++@lab.Variable(Password)+++, and then select **OK**.

    >[!NOTE] This script creates 20 Microsoft 365 users. The script also creates three Azure Active Directory (Azure AD) security groups, and then it populates the groups with the 20 users based on properties of their accounts. It will take approximately 2—3 minutes for the script to run.

1. [] In Microsoft Edge, in the Microsoft 365 admin center, in the upper-left corner, select the **Navigation menu** icon, expand **Users**, and then select **Active users**.

1. [] Verify that there are a total of 21 users.


===
# Summary

Congratulations, you have completed the **Provision an Office 365 E5 Trial Subscription** challenge lab.

You have accomplished the following:

- Created a new Microsoft account.
- Signed up for a Office 365 E5 trial subscription.
- Deployed a Microsoft 365 tenant in the trial subscription.
- Created 20 users and 3 Azure AD security groups in a Microsoft 365 tenant by using a Windows PowerShell script.

    >[!ALERT] Did you record your Microsoft 365 username and password and store it in a safe place? When you end this challenge lab, you will not be able to see this unique username in subsequent challenge labs unless you enter it manually. This is your last chance to view the username and password.
    >
    >Your Microsoft 365 username is ++Microsoft365Admin@Hexelo@lab.LabInstance.Id.onmicrosoft.com++.
    >
    >Your Microsoft 365 password is ++@lab.Variable(Password)++.
    >
    >Your Microsoft account is ++@lab.Variable(MicrosoftAccountEmailAddress)++.
    >
    >Your Microsoft account password is ++@lab.Variable(MicrosoftAccountPassword)++.


!instructions[](https://raw.githubusercontent.com/LODSContent/ChallengeTemplates/master/Boilerplate/Feedback.md)





[Open URL0]:
```Shell
Start microsoft-edge:https://outlook.com
```


[Open URL1]:
```Shell
Start microsoft-edge:https://products.office.com/en-us/business/compare-more-office-365-for-business-plans
```   


[Open URL2]:
```Shell
Start microsoft-edge:https://products.office.com/en-us/business/office-365-enterprise-e5-business-software
``` 
