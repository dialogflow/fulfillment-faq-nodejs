# Dialogflow FAQ Sample
This sample uses [Knowledge Connectors](https://dialogflow.com/docs/knowledge-connectors) to create an agent surfaced on the Google Assistant and phone calls through [Actions on Google](https://developers.google.com/actions/) and Dialogflow's [Phone Gateway](https://dialogflow.com/docs/integrations/telephony). Knowledge connectors allow you to connect FAQ and knowledge-base-style articles to Dialogflow without creating any intents or manual configuration.  Dialogflow parses the documents and determines if a user's query would be satisfied by information in the document, and if it is, the information from the document is surfaced to the user.

This sample is meant to be a starting point for developers looking to create an action that is also accessible by phone as well as developers looking to connect FAQ or knowledge base data to a Dialogflow agent.

## Setup Instructions
Click on the **Add to Dialogflow** button below and follow the prompts to create a new agent:

[![Firestore Sample](https://storage.googleapis.com/dialogflow-oneclick/deploy.svg "FAQ Sample")](https://console.dialogflow.com/api-client/oneclick?templateUrl=https://storage.googleapis.com/dialogflow-oneclick/dialogflow-agent-knowlege-base-phone-gateway.zip&agentName=FAQSample)

1. Click on the button above and click `Create agent`
1. After the creation is complete (this may take a few minutes) click `Open agent`

### Knowledge Connector
1. Click on the "Knowledge" tab in the left column and then "Create Knowledge base" in the top right.  Name the knowledge base `Conference` and click "Save"
1. Next, click `Create the first one.` in the center of the screen to create your first knowledge document.  Enter in `Conference FAQ` for the document name, `text/csv` for the "Mime Type" and `FAQ` for the "Knowledge type".
1.  Under "Data source" select `URL` and enter `https://raw.githubusercontent.com/dialogflow/fulfillment-faq-nodejs/master/next-faq.csv` and then click "Create".
1. After the knowledge document has been created in the response section click "Add response". In text response you should see `$Knowledge.Answer[1]`. Add `. Do you have any more questions about Cloud Next?` to the response and Click "Save".
1. Select the "Google Assistant" tab for responses and add a "Simple Response" with the value `$Knowledge.Answer[1]` and then add a second "Simple Response" with the value `Do you have any more questions about Cloud Next?` and click "Save"
1. Try it out! In the simulator on the right enter `What time does the conference start and end?`.  You should see the response from the CSV you just uploaded: "The first keynote starts at 9 AM on Tuesday and programming ends at 2:30 PM on Thursday. We highly recommend picking up your badge on Monday (anytime between 7 AM and 8 PM) or early on Tuesday to avoid lines."

### Phone Gateway
1. Click on the "Integrations" tab in the left column and then click the "Dialogflow Phone Gateway".  In the pop-up, enter you preffered area code (optional) and click "Next"
1. Select your preferred phone number from the list and click "Create"
1. Call the phone number displayed and talk to your agent! Note: Calling the gateway from a device using Project Fi, Google Voice, or Google Hangouts is not currently supported.

### Google Assistant
1. Click on the "Integrations" tab in the left column and then click on "Google Assistant".  In the pop-up, click on the "Test" button, then the "Continue" button (if present) which will open the Actions on Google console in a new tab
1.  In the new tab that was open to the Actions on Google console, click on the text at the bottom of the page that says "Talk to my test app" and press enter.
1. Continue the conversation with your Dialogflow agent through the Google Assistant!  You can also speak with you agent on any Google Assistant enabled device logged into the same Google account like Google Home speakers & smart displays as well as phones.

## How to make contributions?
Please read and follow the steps in the CONTRIBUTING.md.

## License
See [LICENSE](LICENSE).

## Terms
Your use of this sample is subject to, and by using or downloading the sample files you agree to comply with, the [Google APIs Terms of Service](https://developers.google.com/terms/).
