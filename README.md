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

If you haven't done already, download and install Bruno from the URL [www.usebruno.com](https://www.usebruno.com).

If you already have Bruno installed, make sure you uodate it to the latest version. The collection is tested with Bruno version 3.0.2.

### Install the collection

Download this repository to your local machine. Unzip the file if needed. Once unzipped there is a folder **bruno** in the repository. Copy that folder and all its contents to a location on your machine where you want to keep the collection.

1. Open **Bruno** and click on the + sign next to **Collections** in the left sidebar.
2. Choose **Open collection**.
3. Navigate to the location where you copied the **bruno** folder, open it, click on the **Joomla Web Services API** folder and click the **Open** button.
4. In the left sidebar below Collections you should now see the **Joomla Web Services API** collection. Click on it to expand and see all the folders and requests in the collection.
5. With the collection open, at the top right you see a button **Joomla Web ...** Click on it to expand the dropdown. Click on **Joomla Web Services API**.
6. Click on the button again to reopen the dropdown. Click on **Configure**.
7. You see two variables: **base_url** and **api_key**. Modify the value of the base_url variable to match the URL of your Joomla website.
8. Copy the API token from your Joomla user profile and paste it as the value of the api_key variable, for example ```https://www.myjoomlawebsite.com/api/index.php```. Keep the **/api/index.php** part at the end of the URL, as that is the endpoint for Joomla API requests.
9. Click the **Save** button at the bottom of the **Environments** tab.

You now have set up the collection and you can start using the requests in the collection to make API calls to your Joomla website.

## Using the collection

### Running a GET request

A simple test to see if the API endpoint are working is a ```GET``` on Config Application.

1. In the left sidebar click on **Joomla Web Services API** to expand the collection.
2. Click on **Config Application** to open the requests.
3. Click on **GET Get Global Configuration**. The URL for this request is ```{{base_url}}/v1/config/application```.
4. Click on the right arrow at the top right to send the request. If all is working you should see a response with status 200 and the body of the response should contain the global configuration of your Joomla website in JSON format.

### Using variables in requests

In Bruno you can use variables in the request URLs, headers and body. In this example we will use the ```article_id``` variable in the URL of the request.

First, retrieve a list of articles.

1. In the left sidebar click on **Joomla Web Services API** to expand the collection.
2. Click on **Content Articles** to open the requests.
3. Click on **GET content/articles**. The URL for this request is ```{{base_url}}/v1/content/articles```.
4. Click on the right arrow at the top right to send the request. If your Joomla website has articles, you should see a response with status 200 and the body of the response should contain a list of articles in JSON format.

Retrieve an article with a specific ID.

In the JSON result of the content/articles request, find the ID of an article you want to retrieve. An example ID is shown as ```"id": 11```. To retrieve the article with ID 11 you can do the following.

1. In the left sidebar below **Content Articles** choose the request **GET content/articles {article_id}**.
2. The URL for this request is ```{{base_url}}/v1/content/articles/{{article_id}}```.
3. If the variable {{article_id}} in the URL is shown in red, it means the value is not set. To set the value of the variable, hover with your mousepointer over the variable. A dropdown appears where you can input a value for the variable. Input the ID of the article you want to retrieve, for example **11**, and press the Enter key. The variable should now be shown in green, which means it is set.
4. If you want to change the value of the variable, you can hover over it again and modify the value in the dropdown. Or, on the request tab, click on **Vars**. This will show all variables for this request and you can modify the value there. It also allows you to delete the variable, which will make it unset and show in red again.

