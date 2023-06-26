# Installing SABnzbd & VPN

## Table of Contents
- [Configure Datasets](#configure-datasets)
- [Prepare VPN](#prepare-vpn)
- [Create Directories](#create-directories)
- [Install App from TrueCharts](#install-app-from-truecharts)
- [Configure SABnzbd](#configure-sabnzbd)
- [Backups](#backups)

## Configure Datasets
Before installing SABnzbd and VPN, we need to set up the necessary storage configurations.

1. Create a dataset for your Download Cache. This dataset will be used to store downloaded data before moving it to PlexMedia.
2. Ensure that you have an SMB share set up for the next section. This will allow easy file transfer between systems. If you don't have an SMB share set up, click [here](1.%20Installing%20TrueNAS%20Scale.md/#smb-share).

## Prepare VPN
To set up the VPN for your TrueNAS SCALE system, follow these steps:

1. Visit [this page](https://my.surfshark.com/vpn/manual-setup/main/openvpn).
2. Click on the **Credentials** tab and save the provided credentials for later use.
6. Copy the downloaded file to your TrueNAS system using the SMB share.

## Create Directories
6. Under **System Settings**, select **Shell**.
7. Navigate to the download cache dataset you created earlier using `cd /mnt/path/to/folder/` and create the following directories:
   - `sudo mkdir downloads`
   - `sudo mkdir downloads/complete`
   - `sudo mkdir downloads/incomplete`

## Install App from TrueCharts
To install SABnzbd using TrueCharts, follow these steps:

1. Go to the **Apps** page from the top-level SCALE menu.
2. Select the **Available Applications** tab.
3. Search for SABnzbd in the search bar.
4. Click **Install** and wait for the sidebar to open.

### Storage
1. Locate **Storage and Persistance**.
2. Click the **Add** button next to the **Additional App Storage** label.
3. Leave Type of Storage as **Host Path**.
4. Enable Automatic Permissions.
6. Mount the Download Dataset to a local path in the application, such as `/mnt/data`.

### VPN
1. Scroll down to the **VPN** section in the right-side menu.
2. Select **Gluetun** as the type.
3. Optionally, enable the killswitch to disconnect the internet if the VPN fails or disconnects. You can exclude specific networks from the killswitch if needed.
4. Under **VPN Environment Variables**, add the following values:
   - `VPN_SERVICE_PROVIDER` `=` `surfshark`
   - `OPENVPN_USER` `=` *user credentials from earlier*
   - `OPENVPN_PASSWORD` `=` *password credentials from earlier*
5. Click **Save** and wait for the application to install.
6. Once the application has installed, head over to the **Installed Applications** tab.

That's it! You have now installed SABnzbd and set up the necessary VPN configurations. You can proceed to further configuration and customization based on your requirements.

## Configure SABnzbd

### Quick-Start Wizard
1. Locate the SABnzbd instance and wait for it to deploy.
2. Click on **Open**. This will take you to the setup wizard.
3. Click **Next** and enter your usenet provider details. For example, if using euro.fastusenet.org, use the following:
   - Usenet server: euro.fastusenet.org
   - Username: frogoful
   - Password: *usual password*
4. Click the **Test Server** button, and if the connection is successful, click **Next**.
5. Click on **Go to SABnzbd**.

### Settings
1. Click on the **Settings Cog** located in the top right-hand corner.
2. Change the settings under General according to your preference.
3. Enable **Advanced settings** in the top right hand corner.

### Folders
1. In the **Folders** tab, select **Browse** to select the **Temporary Download Folder**.
2. Locate the `/mnt/data/downloads/incomplete` folder and click **Accept**.
3. Select **Browse** to select the **Completed Download Folder**.
4. Locate the `/mnt/data/downloads/complete` folder and click **Accept**.
5. Set the **Minimum Free Space for Temporary Download Folder**. Downloads will pause when there is less free space than this value.
6. Enable **Auto Resume**. This will resume downloads once the minimum free space is available again.
7. Set **Permissions for completed downloads** to `777` (Everyone All access). Alternatively, leave it blank to inherit permissions from the dataset. Make sure to set up permissions for Plex, Sonarr, and Radarr to have read/write access.

### Servers
1. Click **Show details** on the fastusenet server we added.
2. Increase the **Connections** to `25`.

### Categories
You can set up individual folders in `downloads/complete` for each Sonarr or Radarr instance and add them as a category if you have multiple installs grabbing different qualities. (Optional)

### Switches
Enable the following switches:
1. **Direct Unpack**: This allows unpacking of files while downloading the next file, reducing post-processing time.
2. **On failure, try alternative NZB**.
3. **Ignore Samples**.

That's it! You have now installed SABnzbd and set up the necessary VPN configurations. You can now proceed to further adjust the configuration based on your requirements.

## Backups
1. Go to **Settings** and select the **General** tab.
2. Scroll to the bottom of the page.
3. Click **Create backup**. This will save a backup in the `downloads/complete` directory.

---
[&larr; Previous: Installing Plex Media Server](Installing%20Plex%20Media%20Server.md) | [Home](README.md) | [Next: Installing Sonarr &rarr;](Installing%20Sonarr.md)
