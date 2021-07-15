# Module 0 - Lab environment setup with a pre-installed virtual machine

The following instructions enables learners to prepare their lab environments for the modules that follow. Please run through these instructions prior to starting Module 1.

**Time to complete**: It takes around 5 minutes to perform the steps below and initiate the automated setup scripts. The scripts may take an hour or more to complete.

> **Note**: These instructions are designed to be used in the pre-installed virtual machine provided for the course. If you aren't using the pre-installed virtual machine, you can follow the [full setup instructions](00FullSetupREADME.md).

## Requirements

Before starting setup, you will need an Azure Account with the ability to create an Azure Synapse Workspace.

## Setup steps

Perform the following tasks to prepare your environment for the labs.

1. Use the Windows **Search** box to search for **Windows PowerShell**, and then run it as an administrator.

2. In Windows PowerShell, run the following commands to download the required course files. This may take a few minutes. <!-- Change path when labs are moved to production repo -->

    ```powershell
    mkdir c:\labfiles

    cd c:\labfiles

    git clone https://github.com/ctesta-oneillmsft/xyz.git data-engineering-ilt-deployment
    ```

3. In Windows PowerShell, run the following command set the execution policy so you can run a local PowerShell script file:

    ```powershell
    Set-ExecutionPolicy Unrestricted
    ```

    > [!Note]: If you receive a prompt that you are installing the module from an untrusted repository, select **Yes to All** to proceed with the setup.

4. In Windows PowerShell, use the following command to change directories to the folder containing the automation scripts. <!-- Change path when labs are moved to production repo -->

    ```powershell
    cd C:\labfiles\data-engineering-ilt-deployment\Allfiles\00\artifacts\environment-setup\automation\
    ```

5. In Windows PowerShell, run the following command to sign into Azure.

    ```powershell
    az login
    ```

    When your browser opens, sign into your Azure account. After signing in, you can close the browser and return to Windows PowerShell, which should display the Azure subscriptions to which you have access. If you have multiple subscriptions with the same name, use the unique IDs to identify the subscription that you want to use in the labs.

6. In Windows PowerShell, enter the following command to run the setup script:

    ```powershell
    .\dp-203-setup.ps1
    ```

7. When prompted, sign into your Azure account again (this is required so that the script can manage resources in your Azure subscription).

8. If you have more than one Azure subscription, when prompted, select the one you want to use in the labs.

9. When prompted, enter a suitably complex password for the SQL Database (make a note of this password in case you need it later).

While the script runs, your instructor will present the first module of the course. Your environment should be ready for you when it's time to start the first lab.

> **NOTE** The script will take about 30-45 minutes to complete. The script will create the Azure resources with randomly generated names. In some very rare cases, a resource name may already be in use or there may be capacity constraints for specific resources in the randomly-selected region, causing an error. If this happens, delete the **data-engineering-synapse-*xxxxxx*** resource group created by the script and re-run the script.
