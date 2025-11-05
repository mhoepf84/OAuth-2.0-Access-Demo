# Video Demonstration
Will be posted soon (posting this note on Nov 5th)
# Overview
In this portfolio piece, I'll be demonstrating an API interaction utilizing OAuth 2.0 within Postman. This will be using a Dropbox API which can be set up quickly.

# Installation & Setup
This is demonstrated in the video linked above. Since there is some setup on the user end, I'm going to detail the setup here, step-by-step. I'll elaborate further on these steps/actions within the video demonstration.

1. First, we need to create a Dropbox account (specifically, a free one). This can be performed from the main [Dropbox website](https://www.dropbox.com/).
   
2. Next, we need to create our API which Postman will communicate through. This can be performed from the [Dropbox App Creation](https://www.dropbox.com/developers/apps) page. For item 2, I specified "App folder" just for security's sake. Provide a unique name and proceed.
   
![API Creation Page](https://github.com/user-attachments/assets/8e877713-c95f-4342-abe8-da4deabd0d31)

3. From the following screen, choose to modify the API we just created. From there, copy the App key and App secret for Postman. As for Redirect URIs, add the following:
```
https://oauth.pstmn.io/v1/callback
```

![API Settings](https://github.com/user-attachments/assets/61f4dcc7-aba9-478b-af7b-ce0706bf834d)

4. Finally, click the Permissions tab at the top, and toggle the "files.metadata.read" checkbox.

![API Permissions](https://github.com/user-attachments/assets/6679da3b-5550-49cd-b09b-42b4b2ce3546)

5. Import the JSON files provided here. From within Postman, navigate to the OAuth Dropbox Environment. Using the "App key" and "App secret" from step 3, enter these to the Value column. Leave "token" empty for now.

![Environment Settings](https://github.com/user-attachments/assets/c5561d77-daf0-4de9-8929-a1783e62d7ad)

6. Click on the "Query Contents" POST request and navigate to the Authorization tab. Ensure that the environment is set in the top-right drag-down option.

![Environment Check](https://github.com/user-attachments/assets/0f4526d1-57fb-4484-a7e3-066b201535ba)
   
7. I've already populated it with information specified within [Dropbox's API Documentation](https://www.dropbox.com/developers/documentation/http/documentation). From Authorization, scroll to the bottom of the page and click "Get New Access Token". This will open a new browser window for confirmations (allow pop-ups if you receive a warning). Upon approving these, Postman will show a new window with your token information. Copy this and place it into the "token" environment (mentioned in the previous step).

![Query Contents POST Request](https://github.com/user-attachments/assets/330bd753-8bb9-4ee8-af61-ca8b26defa0f)

9. The OAuth Dropbox POST request can now run. When run, it will access the Apps directory in your Dropbox, then a subdirectory within that, named after your API created in Step 2. If you deposite a file within that path, it will appear in the POST request. In my case, I placed an image inside in here.

![My Dropbox Example Structure](https://github.com/user-attachments/assets/37c81b17-303b-4ab6-bd65-14dfcfa9d5b0)

11. Send the POST request. The default Body is configured as recommended within the API documentation.

![POST Response](https://github.com/user-attachments/assets/b8493f57-97db-4118-ba07-57b0a89c9f7d)
