# stopstart-logicapps

This procedure use Azure Logic Apps to stop/start VMs on Azure using any schedule.

>1. Open **Azure Portal**, click **+ Create a Resource** , type  **Logic App** and press **ENTER**

![img1](/img/img1.png)

![img2](/img/img2.png)

![img3](/img/img3.png)

>2. At this point you can use an existing **Resource Group** or create a new one. I recommend you to create a test environment before use on production. 

![img4](/img/img4.png)

>3. Logic App will be created and you can click to configure. On **Templates** section click on **Blank Logic App** to create your first workflow. 

![img5](/img/img5.png)

>4. Type **Schedule** on **Search** bar

![img6](/img/img6.png)

>5. Click on **Schedule**. The **Trigger** option will appear and then select **Recurrence**. 

![img7](/img/img7.png)

>6. On **Interval** field type **1**. Select **Week** on **Frequency** field. Use the other options for **Parameters** field:

![img8](/img/img8.png)

After selecting all (you don't have to select start time) you can define each one.

- Time zone: based on your location you can define your currently Time Zone. In my case I'm using UTC-03:00 Brasília.
- On these days: Define wich day of week this Logic App will work. 
- - If you want to use everyday just change the Frequency parameter to Day (with interval = 1) instead of Week.
- - If you want to setup a different schedule for weekend then you have to create another Logic App with a different schedule (1 Logic app for week days and other for weekends)
- At these hours: select wich hour you want to execute this Logic App. For this test I'm defining the exactly hour (19:00hr) that this Logic app will Stop/deallocate the VMs. 
- At these minutes: just set here if you want a specific minute. Otherwise you can remove this parameter.

After finishing these parameters click on **NEXT** button to choose an action

>7. On **Search** type **Azure VM** and select **Deallocate virtual machine (preview)**

Note: The option **Deallocate** will stop the VM and them will deallocate. You don't need to select the option **Power off virtual machine**. Deallocate will stop incurring costs to your virtual machine. 

![img9](/img/img9.png)

>8. Select your **Tenant**. Also you have 2 options here and it's very important an short explanation:  

![img10](/img/img10.png)

- Sign in: if you click here this Logic App will be executed based on your credentials. 
- Connect with Service Principal: this option will execute this Logic App using a specific Service Principal and strongly recommended.
- - if you want to create a Service Principal just follow the steps here: https://docs.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal
- - Don't forget to assign permission to allow this Service Principal on the Resource Group to manage virtual machines. You can use the built-in role **Virtual Machine Contributor**

For this lab I'm selecting the option **Sign in** 








