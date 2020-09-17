# IBM Watson IoT

This tutorial explains how to create the required certificates for your device.

## In the IBM Watson IoT Platform Dashboard

Refer to [Getting started tutorial - Step 1: Register your device](https://console.bluemix.net/docs/services/IoT/getting-started.html#getting-started-with-iotp).

1.  [Sign in](https://console.bluemix.net/login) to your [IBM Cloud account](https://console.bluemix.net/registration/).
2.  In the IBM Cloud console, click **Launch** on the Watson IoT Platform service details page.
3.  In the Overview dashboard, from the menu pane, select **Devices** and then click **Add Device**.
4.  Create a device type for the device that you are adding.
5.  Click **Next** to begin the process of adding your device with the selected device type.
6.  Enter a device ID, for example `my_first_device`.
7.  Click **Next** to complete the process.
8.  Provide an authentication token, or accept an automatically generated token.
9.  Verify the summary information is correct, and then click **Add** to add the connection. 
10. In the device information page, copy and save the following details:
    - Organization ID
    - Device Type
    - Device ID
    - Authentication Method
    - Authentication Token

You'll need the Organization ID, Device Type, Device ID, and Authentication Token to configure your device to be able to connect to the Watson IoT Platform.

## In the Project

### Provide Server Certificate

The **Server Certificate** should be stored on the **File System Drive** using the name `IoTFoundation.pem`.