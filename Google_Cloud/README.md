# Google Cloud 

This tutorial explains how to create a certificates for your device in the Google Cloud. In the Google Cloud IoT console, you need to:
1. [Select or create a project.](#select-or-create-a-project)
2. [Create a device registry.](#create-a-device-registry)
3. [Add a device to the registry.](#add-a-device-to-the-registry)
4. [Create key pairs.](#create-key-pairs)
5. [Add a public key to the device.](#add-a-public-key-to-the-device)

## In the Google Cloud IoT Console

### Select or create a project

Refer to [Quickstart - Before you begin](https://cloud.google.com/iot/docs/quickstart).

1. Sign in to your Google account.
2. In the Cloud Platform Console, go to the Manage resources page and select or create a new project.
3. Enable billing for your project.
4. Enable the Cloud IoT Core and Cloud Pub/Sub APIs.

### Create a device registry

Refer to [Quickstart - Create a device registry](https://cloud.google.com/iot/docs/quickstart).

1.  Go to the Google Cloud IoT Core page in GCP Console. 
2.  Click **Create device registry**.
3.  Enter `my-registry` for the **Registry ID**.
4.  Select **us-central1** for the **Cloud region**.
5.  Select **MQTT** for the **Protocol**.
6.  In the **Telemetry topic** dropdown list, select Create a topic.
7.  In the **Create a topic** dialog, enter `my-device-events` in the **Name** field.
8.  Click **Create** in the **Create a topic** dialog.
9.  The **Device state topic** and **Certificate value** fields are optional, so leave them blank.
10. Click **Create** on the Cloud IoT Core page.

You've just created a device registry with a Cloud Pub/Sub topic for publishing device telemetry events.

### Add a device to the registry

Refer to [Quickstart - Add a device to the registry](https://cloud.google.com/iot/docs/quickstart).

1. On the Registry Details page, click **Add device**.
2. Enter `my-device` for the **Device ID**.
3. Select **Allow** for **Device communication**.
4. The **Authentication** section is optional, so leave its fields blank or use the default values. The **Device metadata** field is also optional; leave it blank.
5. Click **Add**.

You've just added a device to your registry.

### Create key pairs

Google IoT Cloud supports the RSA and Elliptic Curve algorithms. Following sections explain how to generate public/private key pairs using [OpenSSL](https://www.openssl.org/) command-line tools (can be executed within [Google Cloud Shell](https://cloud.google.com/shell)). Public keys can be also wrapped in a self-signed X.509 certificate.

Refer to [Creating public/private key pairs](https://cloud.google.com/iot/docs/how-tos/credentials/keys).

A. Section **Generating an RS256 key**

This section explains how to generate an RSA256 key pair (optional with X.509 certificate).

B. Section **Generating an ES256 key**

This section explains how to generate an EC256 key pair (optional with X.509 certificate).

### Add a public key to the device

Refer to [Quickstart - Add a public key to the device](https://cloud.google.com/iot/docs/quickstart).

1. Open previously generated public key `ec_public.pem` or `rsa_cert.pem`.
2. Copy the contents to the clipboard. Make sure to include the lines that say:

   `-----BEGIN PUBLIC KEY-----` and `-----END PUBLIC KEY-----`

   or

   `-----BEGIN CERTIFICATE-----` and `-----END CERTIFICATE-----`
3. On the **Device details** page for the device you created before, click **Add public key**.
4. Select the **Public key format** based on the key generated.
5. Paste your public key in the **Public key value** box.
6. Click **Add**.

Added key appears on the Device details page for your device.


## In the Project

Device Private Key:
- Add **IoT Client:Google:Device Private Key**. This adds the file `pkey.h` to the project.
- Update ``PrivateKey`` with previously generated **Device Private Key**. Make sure to include the lines that say:

  `-----BEGIN EC PRIVATE KEY-----` and `-----END EC PRIVATE KEY-----` for EC256 key

  or

  `-----BEGIN RSA PRIVATE KEY-----` and `-----END RSA PRIVATE KEY-----` for RSA256 key.

### Adding your certificates
Previously, you have created a template with certificates and keys for your thing. You need to provide the root CA certificate for the server (client certificate and key are not used for Google IoT Cloud).

1. Use the following `CA_Cert` (GlobalSign Root CA - R2):
    ```
    "-----BEGIN CERTIFICATE-----\n"
    "MIIDujCCAqKgAwIBAgILBAAAAAABD4Ym5g0wDQYJKoZIhvcNAQEFBQAwTDEgMB4G"
    "A1UECxMXR2xvYmFsU2lnbiBSb290IENBIC0gUjIxEzARBgNVBAoTCkdsb2JhbFNp"
    "Z24xEzARBgNVBAMTCkdsb2JhbFNpZ24wHhcNMDYxMjE1MDgwMDAwWhcNMjExMjE1"
    "MDgwMDAwWjBMMSAwHgYDVQQLExdHbG9iYWxTaWduIFJvb3QgQ0EgLSBSMjETMBEG"
    "A1UEChMKR2xvYmFsU2lnbjETMBEGA1UEAxMKR2xvYmFsU2lnbjCCASIwDQYJKoZI"
    "hvcNAQEBBQADggEPADCCAQoCggEBAKbPJA6+Lm8omUVCxKs+IVSbC9N/hHD6ErPL"
    "v4dfxn+G07IwXNb9rfF73OX4YJYJkhD10FPe+3t+c4isUoh7SqbKSaZeqKeMWhG8"
    "eoLrvozps6yWJQeXSpkqBy+0Hne/ig+1AnwblrjFuTosvNYSuetZfeLQBoZfXklq"
    "tTleiDTsvHgMCJiEbKjNS7SgfQx5TfC4LcshytVsW33hoCmEofnTlEnLJGKRILzd"
    "C9XZzPnqJworc5HGnRusyMvo4KD0L5CLTfuwNhv2GXqF4G3yYROIXJ/gkwpRl4pa"
    "zq+r1feqCapgvdzZX99yqWATXgAByUr6P6TqBwMhAo6CygPCm48CAwEAAaOBnDCB"
    "mTAOBgNVHQ8BAf8EBAMCAQYwDwYDVR0TAQH/BAUwAwEB/zAdBgNVHQ4EFgQUm+IH"
    "V2ccHsBqBt5ZtJot39wZhi4wNgYDVR0fBC8wLTAroCmgJ4YlaHR0cDovL2NybC5n"
    "bG9iYWxzaWduLm5ldC9yb290LXIyLmNybDAfBgNVHSMEGDAWgBSb4gdXZxwewGoG"
    "3lm0mi3f3BmGLjANBgkqhkiG9w0BAQUFAAOCAQEAmYFThxxol4aR7OBKuEQLq4Gs"
    "J0/WwbgcQ3izDJr86iw8bmEbTUsp9Z8FHSbBuOmDAGJFtqkIk7mpM0sYmsL4h4hO"
    "291xNBrBVNpGP+DTKqttVCL1OmLNIG+6KYnX3ZHu01yiPqFbQfXf5WRDLenVOavS"
    "ot+3i9DAgBkcRcAtjOj4LaR0VknFBbVPFd5uRHg5h6h+u/N5GJG79G+dwfCMNYxd"
    "AfvDbbnvRG15RjF+Cv6pgsH/76tuIMRQyV+dTZsXjAzlAcmgQWpzU/qlULRuJQ/7"
    "TBj0/VLZjmmx6BEP3ojY+x1J96relc8geMJgEtslQIxq/H5COEBkEveegeGTLg=="
    "\n"
    "-----END CERTIFICATE-----\n";
    ```
2. Leave `ClientCert` unchanged (not used).
3. Leave `ClientKey` unchanged (not used).
