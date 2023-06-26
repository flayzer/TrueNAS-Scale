# Installing TrueNAS Scale

**Table of Contents**
- [Download and Install TrueNAS Scale](#download-and-install-truenas-scale)
- [Create Storage Pools](#create-storage-pools)
- [Add TrueCharts Application Database](#add-truecharts-application-database)
- [Configure System Settings](#configure-system-settings)
  - [User Accounts](#user-accounts)
  - [SMB Share](#smb-share)
  - [Network Settings](#network-settings)
  - [Localization](#localization)
- [System Updates](#system-updates)

Before we begin, make sure you have downloaded the TrueNAS Scale installation ISO. If you haven't done so already, you can download it from [here](https://www.truenas.com/download-truenas-scale/).

## Download and Install TrueNAS Scale

1. Create a bootable drive using the downloaded TrueNAS Scale ISO.
2. Insert the bootable drive into your NAS system and boot from it.
3. Follow the on-screen instructions to install TrueNAS Scale on your system.
4. Once the installation is complete, remove the bootable drive and restart your system.
5. Access the TrueNAS Scale web interface by entering the IP address of your NAS system into a web browser.

## Create Storage Pools

1. In the TrueNAS Scale web interface, navigate to the **Storage** section.
2. Click on the **Create** button to create a new pool.
3. Configure the pool settings, such as the name, RAID level, and disk allocation.
4. Check the Force tickbox if there is only one disk in the pool.
5. If desired, repeat the above steps to create additional storage pools for different purposes.

## Add TrueCharts Application Database

1. Go to the **Apps** page from the top-level SCALE menu.
2. Select the **Manage Catalogs** tab on the Apps page.
3. Click on **Add Catalog**.
4. Read the iXsystems notice and click **Continue**.
5. Enter the following information in the required fields:
   - Name: `truecharts`
   - Repository: `https://github.com/truecharts/catalog`
   - Preferred Trains: `enterprise`, `stable`, `operators` (type each one manually)
   - Branch: `main`
6. Click **Save** and allow SCALE to refresh its catalog with TrueCharts. This may take a few minutes.

## Configure System Settings

Once you have completed the initial setup, it is recommended to perform the following additional configuration steps:

### User Accounts & Groups
Here is a list of users and groups I am using:
#### Groups
- download-access
- plex-media-access

#### Users
These are the UID's I'm using for each user. They can all be personalised except for Nextcloud
- twade - UID: 2132 (This can be any unsued number)
- plex - UID: 972
- sabnzbd - UID: 955
- sonarr-radarr - UID: 963
- tdarr - UID: (unknown)
- www-data - UID: 33 (Used by Nextcloud)

#### Create a user
1. Navigate to the **Credentials** section in the TrueNAS Scale web interface.
2. Select **Local Users** from the pop-up menu.
3. Create user accounts with appropriate permissions and access levels for managing and accessing your NAS system.
4. Create and add the user to a group to make it easier to assign future permissions.

### SMB Share

1. Click on **Datasets** from the left-side menu.
2. Select the datasets and select **Edit** under Permissions.
3. Add the appropriate permissions for the User/Group that needs access.

### Network Settings

1. Go to the **Network** section in the TrueNAS Scale web interface.
2. Select **Settings** under Global Configuration.
3. Configure the network settings, including IP addressing, DNS, and gateway, to ensure proper network connectivity for your NAS system.

### Localization

1. Go to the **System Settings** page from the top-level SCALE menu.
2. Select **General** from the pop-up menu.
3. Configure the localization settings according to your preferences.

## System Updates

1. Regularly check for system updates in the **update** section.
2. Apply updates to keep your TrueNAS Scale installation up to date with the latest features, bug fixes, and security patches.

That's it! You have now successfully installed TrueNAS Scale and performed the initial configuration. You can now proceed with the installation of various applications and services to enhance your NAS system.

---

[&larr; Previous: Overview](README.md) | [Home](README.md) | [Next: Installing Plex Media Server &rarr;](Installing%20Plex%20Media%20Server.md)
