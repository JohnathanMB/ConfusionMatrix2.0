# confusionmatrix
This repository contains an Eclipse Java project that is useful for generating accuracy, precision, and recall metrics 
for [Watson Conversation Service](http://www.ibm.com/watson/developercloud/conversation.html). The code also generates
the confusion matrix to help better understand the quality of your trained [Watson Conversation Service]
(http://www.ibm.com/watson/developercloud/conversation.html).

For further details on how to leverage this code, please refer to this blog.

# Running Locally
To run the code locally:
-	Start Eclipse
-	Go to **File -> Import**
-	Choose **Git -> Projects from Git** and press **Next**
-	Choose **Clone URI** and press **Next**
-	In the URI field, paste the link to github repo and press **Next**:
  **https://github.com/joekozhaya/confusionmatrix.git**
-	Select **master** and press **Next**
-	Select Directory on your local machine where repository will be cloned and press **Next**
  **Directory: ~/git/confusionmatrix**
  **Initial branch: master**
  **Remote name: origin**
-	Choose **Import existing Eclipse projects** and press **Next**
-	Select **confusionMatrix** project and press **Finish**
 This should clone the project from github repository to your local disk and load the project into Eclipse.
-	In your Package Explorer view in Eclipse, select the **confusionMatrix** project, right click and select 
  **Maven --> Update Project**. Then select the **confusionMatrix** project in the pop-up window and press **OK**.

-	Select **confusionMatrix** project, right click and select **Run As** and select **Run Configurations**. 
- Provide as argument a Java properties file and press **Run**

## Sample Properties file
conv_url=https://gateway.watsonplatform.net/conversation/api/v1/workspaces/$WORKSPACE_ID/message?version=2016-07-11
userid=YOUR_WATSON_CONVERSATION_SERVICE_username
userpass= YOUR_WATSON_CONVERSATION_SERVICE_password
numIntents=NUMBER_OF_INTENTS
test_csv_filename=COMPLETE_PATH_TO_YOUR_CSV_TEST_FILE
confmatrix_filename=COMPLETE_PATH_TO_YOUR_CSV_CONFUSIONMATRIX_RESULTS_FILE

To get conv_url, userid, userpass, and numIntents:
-	Log into your Bluemix account
-	Go to your Dashboard and select the conversation service you’d like to test
-	Select Service Credentials and that gives you username (userid) and password (userpass)
-	Select Manage and press Launch Tool  this opens the Workspace view
-	Select the workspace that includes the conversation intents you’d like to test (hit the menu 3 dots and select “View details”)
-	Go back and click on the workspace to open it and go to Intents tab to get the number of intents defined (if you don’t know those).

conv_url is the url link to your Watson Conversation Service which includes reference to the specific WORKSPACE_ID for your conversation flow.
userid is the username for your Watson Conversation Service.
userpass is the password for your Watson Conversation Service.
numIntents is the number of intents your Conversation service is trained on.
Test_csv_filename is the complete path to the csv file which includes test utterances and their corresponding intents. Here is an example test csv file:
confmatrix_filename is the name of a file (complete path) to write out the results to.

## Sample Test csv file

## Sample Result Confusion Matrix