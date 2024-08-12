# MDK-Toolbox

The MDK-Toolbox consists of the following utilities:

- **FCARM**, a file converter that reformats web files into a single C source file which is then included and compiled into a project.
- **ElfDwT**, a command-line utility that computes and writes a signature into the application image file.
- **Mbed TLS/cert_write**, an application that signs a certificate signing request, or self-signs a certificate.
- **Mbed TLS/gen_key**, an application that generates a key for any of the supported public-key algorithms (RSA or ECC).

## Using the toolbox

The tools are to be used using vcpkg for simplicity and portability. There is no need for the user to manually install any tools inside of the toolbox.

For using the tools by the means of a vcpkg integration, the following steps need to be taken:

1. In the vcpkg_configuration.json file, the Arm artifactory registry should be added to the list of registries.
   ```
   {
       "name": "arm",
       "kind": "artifact",
       "location": "https://artifacts.tools.arm.com/vcpkg-ce-registry/registry.zip"
   }
   ```
2. In the vcpkg_configuration.json file, the mdk-toolbox should be added under the requirement list
   ```
   "arm:mdk-toolbox": "^1.0.0"
   ```
3. Update the vcpkg registry using the command:
   ```
   vcpkg x-update-registry --all
   ```
4. Reactivate your vcpkg environment
   ```
   vcpkg activate
   ```

## Documentation

The documentation for the MDK-Toolbox utilities can found here:

- [FCARM](https://developer.arm.com/documentation/101407/latest/Appendix/H--File-Converter-FCARM)
- [ElfDwT](https://developer.arm.com/documentation/101407/latest/Utilities/Signature-Creator-for-NXP-Cortex-M-Devices)
- [Mbed TLS/cert_write](https://mbed-tls.readthedocs.io/en/latest/kb/how-to/generate-a-self-signed-certificate/#command-to-generate-a-self-signed-certificate)
- Mbed TLS/gen_key:
  - [RSA key pair generator](https://mbed-tls.readthedocs.io/en/latest/kb/cryptography/rsa-key-pair-generator/)
  - [How to generate a Certificate Request (CSR)](https://mbed-tls.readthedocs.io/en/latest/kb/how-to/generate-a-certificate-request-csr/)
  - [How to generate a self-signed certificate](https://mbed-tls.readthedocs.io/en/latest/kb/how-to/generate-a-self-signed-certificate/)

## Licenses

The MDK-Toolbox utilities are provided under the following license terms:

- The FCARM and ElfDwT tools are provided under the [MDK v6 license agreement](https://www.keil.arm.com/license-agreement/).
- The Mbed TLS tools are provided under the [mbed TLS license argreement](https://github.com/Mbed-TLS/mbedtls/blob/development/LICENSE).
