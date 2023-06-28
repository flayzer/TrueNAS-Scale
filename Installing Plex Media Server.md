# Installing Plex Media Server

#### Table of Contents
- [Prepare the Storage](#prepare-the-storage)
- [Installing Plex Media Server](#installing-plex-media-server)
- [Plex Configuration](#plex-configuration)
- [Updating](#updating)

Follow these steps to install and configure Plex Media Server on TrueNAS:

Plex UID 972

## Prepare the Storage
We are going to need three different datasets. Create these datasets in whichever pool you like.
- Transcode Volume
- Data Volume
- Config Volume

## Installing Plex Media Server
1. Log in to TrueNAS. From the dashboard screen, select "Apps" in the left-side menu.
2. Select the **Available Applications** tab and search for *Plex*.
3. Click **Install**.
4. Visit [plex.tv/claim](https://www.plex.tv/claim/) to get your claim token.
5. Copy and paste this token into the **Plex Claim Token** field.
7. Check the **Configure Host Network** option under Networking.
8. Configure the storage section. Set the host path for the `Transcode Volume`, `Data Volume`, and `Config Volume`.
9. Finally, click **Save**.

Once the TrueNAS setup is complete, your Plex Media Server application will be ready for use.

Note: With TrueNAS Scale, you don't have to add an automatic start. As long as your host is up and running, your app will also be running. If you restart your host for any reason, you must go back to Installed Applications and manually start Plex.

## Plex Configuration

1. Navigate to your TrueNAS Dashboard and select **Apps** in the left-side menu.
2. Click on **Installed Applications**.
3. Find `Plex` and click on the **Web Portal** button.
4. Go through the wizard using the Web Interface.
5. Add a name for your TrueNAS Server.
6. In the Media Library tab, select the content type you want and the location of the media. (The host path maps to the local `data` folder).
7. Add as many libraries as you need and click **Next**.
8. Finally, click **Done** to complete the server setup.

## Updating
1. On the **Installed Applications** tab, locate the Plex widget.
2. Click on the ellipsis (...) and select **Upgrade**.

---

[&larr; Previous: Installing TrueNAS SCALE](Installing%20TrueNAS%20SCALE.md) | [Home](README.md) | [Next: Installing SABnzbd and OpenVPN &rarr;](Installing%20SABnzbd%20%26%20VPN.md)
