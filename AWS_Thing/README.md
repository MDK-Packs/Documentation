# AWS Thing

This tutorial explains how to create an [AWS thing](https://docs.aws.amazon.com/iot/latest/developerguide/iot-thing-management.html) and configure the AWS SDK.

## In the AWS IoT Console

In the [AWS IoT console](https://console.aws.amazon.com/iotv2/), you need to create a thing, download its certificates, create a policy, and attach the policy to the thing. Here’s how to do this:

### Create an IoT thing for your device

1. Browse to the [AWS IoT console](https://console.aws.amazon.com/iotv2/).
2. In the left navigation pane, choose **Manage**, and then choose **Things**.
3. If you do not have any IoT things registered in your account, the **You don’t have any things yet** page is displayed. If you see this page, choose **Register** a thing.
4. On the **Creating AWS IoT things** page, choose **Create a single thing**.
5. On the **Add your device to the thing registry** page, type a name for your thing (for example `MyThing`), and then choose **Next**. You will need to add the name later to your C code.
6. On the **Add a certificate for your thing** page, under **One-click certificate creation**, choose **Create certificate**.
7. Download your private key and certificate by choosing the **Download** links for each. Make note of the certificate ID. You need it later to attach a policy to your certificate.
8. Choose **Activate** to activate your certificate. Certificates must be activated prior to use.

### Create a policy and attach it to your thing

1. In the navigation pane of the AWS IoT console, choose **Secure**, and then choose **Policies**.
2. On the **Policies** page, choose **Create** (top right corner).
3. On the **Create a policy** page, enter a name for the policy. In the **Action** box, enter **iot:Connect**, **iot:Publish**, **iot:Subscribe**, **iot:Receive**. The **Resource ARN** box will be auto-filled with your credentials. Replace the entry with *. Under **Effect**, check the **Allow** box. Click on **Create**.
4. In the left navigation pane of the AWS IoT console, choose **Secure**, and then choose **Certificates**. You should see the certificate that you have created earlier.
5. Click on the three dots in the upper right corner of the certificate and choose **Attach policy**.
6. In the **Attach policies to certificate(s)** window, enable the policy that you have just created and click **Attach**.

### Make a note of your custom endpoint

In the navigation pane of the [AWS IoT console](https://console.aws.amazon.com/iotv2/), choose **Settings**. On the **Settings** page, copy the name of your **Endpoint** (such as `a3xyzzyx.iot.us-east-2.amazonaws.com`) to have it ready for later.

Now you are ready to connect your device to the AWS IoT Cloud.

## In µVision

## Configure AWS IoT Client: IoT Client:iot_config.h

1. `IOT_DEMO_SERVER`: Enter your custom endpoint, as noted down before.
2. `IOT_DEMO_IDENTIFIER`: Enter the thing’s name here (as created in the AWS IoT console).
3. `IOT_DEMO_ROOT_CA`: Copy the following into this section:
    ```
    "-----BEGIN CERTIFICATE-----\n\
    MIIDQTCCAimgAwIBAgITBmyfz5m/jAo54vB4ikPmljZbyjANBgkqhkiG9w0BAQsF\
    ADA5MQswCQYDVQQGEwJVUzEPMA0GA1UEChMGQW1hem9uMRkwFwYDVQQDExBBbWF6\
    b24gUm9vdCBDQSAxMB4XDTE1MDUyNjAwMDAwMFoXDTM4MDExNzAwMDAwMFowOTEL\
    MAkGA1UEBhMCVVMxDzANBgNVBAoTBkFtYXpvbjEZMBcGA1UEAxMQQW1hem9uIFJv\
    b3QgQ0EgMTCCASIwDQYJKoZIhvcNAQEBBQADggEPADCCAQoCggEBALJ4gHHKeNXj\
    ca9HgFB0fW7Y14h29Jlo91ghYPl0hAEvrAIthtOgQ3pOsqTQNroBvo3bSMgHFzZM\
    9O6II8c+6zf1tRn4SWiw3te5djgdYZ6k/oI2peVKVuRF4fn9tBb6dNqcmzU5L/qw\
    IFAGbHrQgLKm+a/sRxmPUDgH3KKHOVj4utWp+UhnMJbulHheb4mjUcAwhmahRWa6\
    VOujw5H5SNz/0egwLX0tdHA114gk957EWW67c4cX8jJGKLhD+rcdqsq08p8kDi1L\
    93FcXmn/6pUCyziKrlA4b9v7LWIbxcceVOF34GfID5yHI9Y/QCB/IIDEgEw+OyQm\
    jgSubJrIqg0CAwEAAaNCMEAwDwYDVR0TAQH/BAUwAwEB/zAOBgNVHQ8BAf8EBAMC\
    AYYwHQYDVR0OBBYEFIQYzIU07LwMlJQuCFmcx7IQTgoIMA0GCSqGSIb3DQEBCwUA\
    A4IBAQCY8jdaQZChGsV2USggNiMOruYou6r4lK5IpDB/G/wkjUu0yKGX9rbxenDI\
    U5PMCCjjmCXPI6T53iHTfIUJrU6adTrCC2qJeHZERxhlbI1Bjjt/msv0tadQ1wUs\
    N+gDS63pYaACbvXy8MWy7Vu33PqUXHeeE6V/Uq2V8viTO96LXFvKWlJbYK8U90vv\
    o/ufQJVtMVT8QtPHRh8jrdkPSHCa2XV4cdFyQzR1bldZwgJcJmApzyMZFo6IQ6XU\
    5MsI+yMRQ+hDKXJioaldXgjUkK642M4UwtBV8ob2xJNDd2ZhwLnoQdeXeGADbkpy\
    rqXRfboQnoZsG4q5WTP468SQvvG5\n\
    -----END CERTIFICATE-----\n"
    ```
4. `IOT_DEMO_CLIENT_CERT`: Open the file `<ID>-certificate.pem.crt` in a text editor. Edit the certificate as shown under item 3. Then, copy the content into the section.
5. `IOT_DEMO_PRIVATE_KEY`: Open the file `<ID>-private.pem.key` in a text editor. Edit the key as shown under item 3. Then, copy the content into the section.