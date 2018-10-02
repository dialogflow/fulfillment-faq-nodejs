# Dialogflow FAQ Sample
The following sample uses [Knowledge Connectors](https://dialogflow.com/docs/knowledge-connectors) to create an agent surfaced on the Google Assistant and phone calls through [Actions on Google](https://developers.google.com/actions/) and Dialogflow's [Phone Gateway](https://dialogflow.com/docs/integrations/telephony).
+ Knowledge connectors allow you to connect FAQ and knowledge-base-style articles to Dialogflow without creating any intents or manual configuration.  Dialogflow parses the documents and determines if a user's query would be satisfied by information in the document, and if it is, the information from the document is relayed back to the user.

+ This sample is meant to be a starting point for developers looking to create an action that is also accessible by phone as well as developers looking to connect FAQ or knowledge base data to a Dialogflow agent.

## Setup
To create this agent from our template:

<a href="https://console.dialogflow.com/api-client/oneclick?templateUrl=https://oneclickgithub.appspot.com/dialogflow/fulfillment-faq-nodejs&agentName=FAQsample" target="blank">
  <img src="https://dialogflow.com/images/deploy.png">
</a>

### Knowledge Connector
1. From the left column, go to the **Knowledge** tab > **Create Knowledge base**.  
      + Name the knowledge base `Conference` >  **Save**.
2. To create a knowledge document: **Create the first one** and add:
      + `Conference FAQ` for the Document Name,
      + `text/csv` for the Mime Type,
      + `FAQ` for the Knowledge type
3.  Under **Data source** select `File on Cloud Storage` and enter `gs://cloud-next-csv/next-faq.csv` > **Create**.
4. On the same page, go to the Responses section > **Add response** > Set the default response to `$Knowledge.Answer[1]. Have any other questions?` > **Save**.
5. Under Responses, next to the **Default** tab > add **Google Assistant** and **Simple Response** with the value `$Knowledge.Answer[1]. Do you have any more questions about Cloud Next?` > **Save**.
6. Try it out! In the Dialogflow simulator, enter `What time does the conference start and end?`.  
      + You will see a response directly from the CSV: "The first keynote starts at 9 AM on Tuesday and programming ends at 2:30 PM on Thursday. We highly recommend picking up your badge on Monday (anytime between 7 AM and 8 PM) or early on Tuesday to avoid lines."

### Phone Gateway
1. Go to the **Integrations** tab > **Dialogflow Phone Gateway** > **Next** > **Create**
2. Call the phone number displayed and talk to your agent!
      + Note: Calling the gateway from a device using Project Fi, Google Voice, or Google Hangouts is not currently supported.

### Google Assistant
1. Go to the **Integrations** tab in the left column > **Google Assistant** > **Test** > **Continue** in order to open the Actions on Google console.
2.  In the Actions on Google simulator > `Talk to my test app` and press enter.
3. Continue the conversation with your Dialogflow agent through the Google Assistant!  
      + You can also speak with you agent on any Google Assistant enabled device logged into the same Google account like Google Home speakers, smart displays, and mobile phones.

## Make Contributions
Please read and follow the steps in the CONTRIBUTING.md.

## License
See [LICENSE](LICENSE).

## Terms
Your use of this sample is subject to, and by using or downloading the sample files you agree to comply with, the [Google APIs Terms of Service](https://developers.google.com/terms/).
