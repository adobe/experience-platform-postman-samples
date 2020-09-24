## Adobe Experience Platform Postman Samples

A repository that collects Postman samples work with Adobe Experience Platform.

Please note this repository is undergoing a migration/normalization to align with Adobe I/O Console's "Export Details to Postman" functionality.
The Postman Collections in the following folders has been aligned with the Adobe I/O generated Platform API Postman Environment file:

* [./apis/experience-platform](./apis/experience-platform)
* [./apis/ims](./apis/ims)

## Goals

The purpose of this repository is to collect Postman samples that show how to interact with Adobe Experience Platform. Each of the samples will use a common Postman Environment file in order to make it easier to switch between separate collections.

### Usage

#### Generate and Import the Postman Environment

1. [Install Postman](https://www.getpostman.com/apps)
1. Start Postman
1. Login to [Adobe I/O Console](https://console.adobe.io/), select _Integrations_, and select the Adobe Experience Platform API Integration you wish to interact with using Postman.
1. Tap the __Export Details to Postman__ button to have a Postman Environment file with the Integration's details pre-populated.
1. Select the downloaded __Platform API.postman_environment.json__ file to import the environment.
1. Now click on the newly imported `Platform API`.
1. All of the values with the exception of `PRIVATE_KEY` should be pre-populated.
1. Copy the contents of your `private.key` and use it as the value for `PRIVATE_KEY` in BOTH the Initial and Current values fields.

   **For MacOS & Linux platform**

   From the same terminal you ran `openssl`, execute the following command:

   ```shell
   pbcopy < private.key
   ```

   **For Windows Platform**

   From the same terminal you ran `openssl`, execute the following command:

   ```shell
   notepad private.key
   ```

   Copy the entire key to the keyboard, including the `-----BEGIN PRIVATE KEY-----` and `-----END PRIVATE KEY-----` lines.

1. Click `Update` and close the `Manage Environments` dialog.
1. Now make sure you select the `Platform API` from the environments drop down at the top right of Postman.

#### Import the Collection

To import a Postman Collection

1. Download the `.postman_collection.json` file(s) from this Github repository
1. In Postman, select __Import__ int he to left
1. Select __Import File__
1. Select the downloaded  `.postman_collection.json` file(s)


### Reference

See also the [Medium post on the Adobe Techblog](https://medium.com/adobetech/using-postman-for-jwt-authentication-on-adobe-i-o-7573428ffe7f) around the usage of Postman with Adobe I/O.

### Contributing

Contributions are welcomed! Read the [Contributing Guide](CONTRIBUTING.md) for more information.

### Licensing

This project is licensed under the MIT. See [LICENSE](LICENSE) for more information.
