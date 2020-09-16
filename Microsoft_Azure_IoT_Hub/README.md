# Microsoft Azure IoT Hub

This tutorial explains how to create certificates for your devices in the [Azure portal](https://portal.azure.com/).

## In the Microsoft Azure Portal

### Create an IoT Hub

1. Sign in to the [Azure portal](https://portal.azure.com/).
2. Select **Create a resource > Internet of Things > IoT Hub**.
3. In the **IoT hub pane**, enter the following information for your IoT hub:
   - **Subscription**: Choose the subscription that you want to use to create this IoT hub.
   - **Resource group**: Create a resource group to host the IoT hub or use an existing one. For more information, see [Use resource groups to manage your Azure resources](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-portal).
   - **Region**: Select the closest location to you.
   - **Name**: Create a name for your IoT hub. If the name you enter is available, a green check mark appears.
     *Important:* The IoT hub will be publicly discoverable as a DNS endpoint, so make sure to avoid any sensitive information while naming it.
4. Select **Next: Size and scale** to continue creating your IoT hub.
5. Choose your **Pricing and scale tier**. For this article, select the **F1 - Free tier** if it’s still available on your subscription. For more information, see the [Pricing and scale tier](https://azure.microsoft.com/pricing/details/iot-hub/).
6. Select **Review + create**.
7 Review your IoT hub information, then click **Create**. Your IoT hub might take a few minutes to create. You can monitor the progress in the **Notifications** pane.

### Register a device in the IoT hub for your device

1. In your IoT hub navigation menu, open **IoT devices**, then click **Add** to register a device in your IoT hub.
2. Enter a **Device ID** for the new device. Device IDs are case sensitive.
   *Important:* The device ID may be visible in the logs collected for customer support and troubleshooting, so make sure to avoid any sensitive information while naming it.
3. Click **Save**.
4. After the device is created, open the device from the list in the **IoT devices** pane.
5. Copy the **Connection string—primary key** for later use.

## In the Project

Update the `connectionString` constant with the **Connection string—primary key** obtained from the Azure portal.
