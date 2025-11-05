# Video Demonstration
Will be posted soon (posting this note on Nov 5th)
# Overview
In this portfolio piece, I'll be demonstrating an API interaction utilizing OAuth 2.0 within Postman. This will be using a Dropbox API which can be set up quickly.

# Installation & Setup

1. First, we need to create a Dropbox account (specifically, a free one). This can be performed from the main [Dropbox website](https://www.dropbox.com/).
   
2. Next, we need to create our API which Postman will communicate through. This can be performed from the [Dropbox App Creation](https://www.dropbox.com/developers/apps) page. For item 2, I specified "App folder" just for security's sake. Provide a unique name and proceed.
  
3. From the following screen, choose to modify the API we just created. From there, copy the App key and App secret for Postman. As for Redirect URIs, add the following:
```
https://oauth.pstmn.io/v1/callback
```
4. Finally, click the Permissions tab at the top, and toggle the "files.metadata.read" checkbox.

5. Import the JSON files provided here. From within Postman, navigate to the OAuth Dropbox Environment. Using the "App key" and "App secret" from step 3, enter these to the Value column. Leave "token" empty for now.
   
6. Click on the "Query Contents" POST request. I've already populated it with information specified within [Dropbox's API Documentation](https://www.dropbox.com/developers/documentation/http/documentation). From Authorization, scroll to the bottom of the page and click "Get New Access Token". This will open a new browser window for confirmations. Upon approving these, Postman will pop up a new window with your token information. Copy this and place it into the "token" environment (mentioned in the previous step).

7. The OAuth Dropbox POST request can now run. When run, it will access the Apps directory in your Dropbox, then a subdirectory within that, named after your API created in Step 2. In my case, I placed an image inside in here.

8. Send the POST request. The default Body is configured as recommended within the API documentation.
