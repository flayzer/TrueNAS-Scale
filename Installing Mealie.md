# Installing Mealie (Work in Progress)

### Table of Contents
- [Prepare TrueCharts](#prepare-truecharts)
- [Install Mealie via TrueCharts](#install-mealie-via-truecharts)

## Prepare TrueCharts
To install Mealie, we need to make sure the "incubator" category is enabled in TrueCharts.

1. Go to the **Apps** page and click on the **Manage Catalogs** tab.
2. Find the `truecharts` catalog and click on the ellipsis next to it.
3. Select **Edit** and add `incubator` to the **Preferred Trains**.
4. Click **Save** to apply the changes.

## Install Mealie via TrueCharts
Follow these steps to install Mealie using TrueCharts:

1. Navigate to the **Available Applications** tab.
2. Search for `mealie` and click on the **Install** button.
3. In the **Extra Environment Variables** section, click the **Add** button three times and set the following variables:
   - `PUID` with the value `911`
   - `PGID` with the value `911`
   - `DB_ENGINE` with the value `sqlite`
4. Scroll down to the **Service Port(s) Configuration** and configure the following:
   - Set the **Main Service Port Configuration** to `9925`
   - Choose **ClusterIP (Do Not Expose Ports)** as the **Service Type**
   - Set the **API Service Port Configuration** to `9000`
5. Scroll down to the **Security and Permissions** section and configure the following:
   - Set **runAsUser** to `911`
   - Set **runAsGroup** to `911`
6. Scroll to the bottom of the page and click **Save** to start the installation process.
7. Wait for the application to be deployed. The process may take some time as it sets up the database.
8. Once the installation is complete, you can access the Mealie web portal at `youripaddress:9925`.

---
[&larr; Previous: Installing NextCloud](7.%20Installing%20NextCloud.md) | [Home](README.md) | [Next: Installing Tdarr &rarr;](9.%20Installing%20Tdarr.md)
