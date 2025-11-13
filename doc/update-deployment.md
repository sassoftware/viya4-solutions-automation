[← Back to README](../README.md)

## Update A Deployment

We support updating from one cadence to the next cadence.

#### 0. Prerequisites

1. You have taken a good backup before any migration work begins.
2. The cadence you are upgrading to is supported by your current AKS level.

#### 1. Upgrading a Manually Created Deployment

To upgrade a manual deployment, you will follow all of the steps you did for the initial creation. You can reuse the managed application definition name and it will update the current managed application.

#### 2. Upgrading an Automated Deployment Creation via GitHub Actions

To upgrade an automated deployment, you will run the same github action as you did for the initial deployment, however you will need to pass in the required Additional parameters for an upgrade found in the Notes on Additional parameters section in the [Deploy SAS Solution Automated via GitHub Actions](deploy-automated.md) page.

#### 3. Post Upgrade Migration

If your solution supports customization, after the upgrade process has been completed your solution instance will not automatically upgrade to the newest cadence. You will need to go into the Cirrus Builder page to make the new version active.


---
[← Back to README](../README.md)