# bruno-joomla-api
Bruno collection for Joomla 6 API endpoints.

## Installation instructions

### Prepare your Joomla 6 website

1. Install Joomla 6 on your server or local development environment or use an existing Joomla 6 website.
2. Login into the Joomla 6 administrator panel and go to the Global Configuration.
3. On the **Site** tab make sure that the **Search Engine Friendly URLs** option is enabled. It it isn't, enable it and click the **Save&Close** button at the top.
4. Click on the **User Menu** button at the top right and select **Edit Account**.
5. On the **User Profile** page go to the **Joomla API Token** tab.
6. Check if the token is present, if it isn't, click the **Save** button at the top and the token will be generated.
7. Close the Edit profile page.
8. Go to **System** > **Plugins**.
9. Click on the **Filter Options** button. In the **Select Type** dropdown choose **webservices**.
10. Make sure all Web Services plugins are enabled. If any of them is disabled, enable it and click the **Save&Close** button at the top.

Your Joomla website is now ready to be used with webservices API and the Bruno collection.

### Install Bruno

If you haven't done already, download and install Bruno from the URL <a href="https://www.usebruno.com/" target="_blank">https://www.usebruno.com</a>.

### Install the collection

Download this repository to your local machine. Unzip the file if needed.