[← Back to README](../README.md)

# Prerequisites

Before deploying SAS Solutions to Azure, ensure you meet the following requirements:

## At the Azure Subscription level

- **Azure Subscription Access:**  
  You must have an Azure subscription with permissions to create resources and managed applications.

- **Resource Provider Registration:**  
  In the Azure Portal, select your subscription and navigate to **Settings → Resource Providers**. Ensure the the following providers are registered:
  - Microsoft.Storage
  - Microsoft.Solutions
  - Microsoft.ManagedIdentity
  - Microsoft.Network
  - Microsoft.DBforPostgreSQL
  - Microsoft.ContainerService
  - Microsoft.Compute
  - Microsoft.Quota (optional, but recommended if you encounter quota issues)

- **Resource Availability:**  
  Ensure your subscription has sufficient quotas limits (VMs, IP addresses, storage, etc.) for your chosen environment size. 
  Refer to the [Environment Sizing](#environment-sizing) section for details.

## Azure Client

  To enable automated deployments and secure access to Azure resources, you must configure an Azure client (app registration) with the following steps:

- **Create Client (App Registration):**  
  Register a new application in Azure Active Directory.

- **Assign Client as 'Owner' to Subscription:**  
  Add the client as an 'Owner' to your Azure subscription. (Note: Assigning the 'Contributor' role is insufficient for required permissions.)

- **Configure Federated Credentials:**  
  Set up federated credentials for the client to enable secure authentication from GitHub workflows.

- **Add API Permissions:**  
  Grant the following API permissions to the client:
  - `Directory.Read.All`
  - `Group.Read.All`
  - Grant admin consent for these permissions in the Default Directory.

This configuration ensures the GitHub workflow can authenticate and interact with Azure resources securely and with the necessary privileges.

## SAS Solution Assets

  Download SAS solution assets, license, and certificates for your SAS Software Order ID and cadence from [my.sas.com](https://my.sas.com). 
  For automated deployments, these artifacts must be accessible to the GitHub workflow. The recommended approach is to upload them to an Azure Storage Account and provide access via a Shared Access Signature (SAS) token. This ensures the workflow can securely retrieve the necessary files during deployment.
  Make sure the SAS token grants appropriate permissions (read access at minimum) and is scoped to only the required files or containers.

## Miscellaneous

- **Recommended Skills:**  
  Familiarity with Azure Resource Manager (ARM templates), Azure Kubernetes Service (AKS), and managed applications is beneficial.

- **GitHub Workflow Requirements:**  
  If deploying via GitHub workflows, upload SAS solution assets, license, and certificates to an Azure Storage Account accessible by the workflow.

---

[← Back to README](../README.md)