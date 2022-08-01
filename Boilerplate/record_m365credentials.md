# Record your Microsoft 365 credentials

>[!ALERT] This challenge lab is part of a series. To complete this challenge lab, you will need the domain name and credentials of the Microsoft 365 trial account that you created in the **Provision an Office 365 E5 Trial Subscription** lab.

- Record the unique onmicrosoft.com domain of the Microsoft 365 tenant in the following text box: 

    **Domain name**     
    @lab.TextBox(TenantName)

    >[!Note] For example, if your unique domain name is *Hexelo123456*.onmicrosoft.com, enter **Hexelo123456.onmicrosoft.com**.

- Record the password for the Microsoft 365 tenant administrator, Microsoft365Admin@@lab.Variable(TenantName), in the following text box:

    **Password**       
    @lab.TextBox(Password)
