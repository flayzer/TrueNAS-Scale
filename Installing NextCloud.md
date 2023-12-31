# Installing Nextcloud (wip)

### Table of Contents
- [Configure Datasets](#configure-datasets)
- [Prepare VPN](#prepare-vpn)
- [Create Directories](#create-directories)

## Prepare Storage
1. Create a nextcloud storage dataset if you haven't already.
2. Navigate to **Datasets**, select the nextcloud storage dataset, and click **edit** next to permissions.
3. Nextcloud by default runs as user: `www-data`. We need to give it permission to read/write/execute that dataset.
4. Change the Owner user to `www-data`
5. Enable **Apply Group** and **Apply permissions recursively**.
6. Click **Save**

## Install Nextcloud via TrueCharts
1. Navigate to **Apps** &rarr; **Available Applications** and search for **Nextcloud**
2. Install the **Truenas Charts** version. Even though this is updated ledd often, it is more stable.
3. Under **Nextcloud Configuration**, set the administrator username and password.
4. Click **Add** to add a local host path.
5. Scroll down to **Storage** and enable **Enable Host Path for Nextcloud Data Volume**.
6. Browse and select the host path, and then copy and paste it into the **Nextcloud data directory** field. (Under Nextcloud Configuration. Scroll up a bit).
7. Scroll to the bottom and hit **Save**.
8. Wait for the application to be installed. This may take some time.

## Setup Nextcloud
1. Navigate to `youripaddress:9001` to access the Web GUI.
2. Log in using your admin username and password.
3. Create users and set additional settings.


---
[&larr; Previous: Installing Overseer](Installing%20Overseer.md) | [Home](README.md) | [Next: Installing Mealie &rarr;](Installing%20Mealie.md)
