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





