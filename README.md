## Adobe Experience Platform Postman Samples

A repository that collects Postman samples work with the Adobe Experience Platform.

## Goals

The purpose of this repository is to collect Postman samples that show how to interact with the Adobe Experience Platform. Each of the samples will use a common Postman Environment file in order to make it easier to switch between separate collections.

### Usage

#### Import the Environment

1. [Install Postman](https://www.getpostman.com/apps)
1. Start POSTMan

   ![](/images/postman.png)

1. Import the [Adobe Experience Platform Environment](postman/Adobe Experience Platform.postman_environment.json) file into Postman.

1. Select the [Adobe Experience Platform Environment](postman/Adobe%20Experience%20Platform.postman_environment.json) file to import the environment.

   ![](/images/postman_after_env_import.png)

1. Now click on the newly imported `Adobe Experience Platform`.

   ![](/images/postman_set_env.png)

1. Fill out the values for:

   - clientID
   - clientSecret
   - OrgID
   - TechAcctID

   that you generated when you created your **new integration**.

   Also fill out the `ldap` field with your user id so you'll be able to uniquely identify and data you create.

1. Copy the contents of your `private.key` and use it as the value for `secret`.

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

1. Now make sure you select the `Adobe Experience Platform` from the environments drop down at the top right of POSTMan.

   ![](/images/postman_experience_platform_env.png)

#### Import the Collection

@ToDo

### Contributing

Contributions are welcomed! Read the [Contributing Guide](CONTRIBUTING.md) for more information.

### Licensing

This project is licensed under the MIT. See [LICENSE](LICENSE) for more information.
