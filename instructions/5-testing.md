# Alexa Skill Sample - Sales Assistant

[![Salesforce Setup](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/tutorial-page-marker-1-done._TTH_.png)](./1-salesforce-setup.md)[![Deploy](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/tutorial-page-marker-2-done._TTH_.png)](./2-heroku.md)[![Account Linking](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/tutorial-page-marker-3-done._TTH_.png)](./3-deploy.md)[![Testing](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/tutorial-page-marker-4-done._TTH_.png)](./4-account-linking.md)[![Distribute Private Skills](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/tutorial-page-marker-5-on._TTH_.png)](./5-testing.md)[![Distribute Private Skills](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/tutorial-page-marker-6-off._TTH_.png)](./6-distribute-private-skills.md)

## Part 5: Testing

Now that you completed most of the setup, let's make sure everything is working. We'll show you first how to test using the command line, then validate the account linking flow, finally interact with the skill to access Salesforce data.

### Simulate

1. Run the following command to execute a command against your skill:

```
$ ask dialog -l en-US
========================================== Welcome to ASK Dialog 
========================================== In interactive mode, type your utterance text onto the console and hit enter 
========================================== Alexa will then evaluate your input and give a response! 
========================================== Use ".record <fileName>" or ".record <fileName> --append-quit" to save list of utterances to a file. 
========================================== You can exit the interactive mode by entering ".quit" or "ctrl + c". 

User  > Open Sales Assistant
...
```

2. Check for the output message to also see what Alexa would have said. In this case, the message just indicates you need to link a Salesforce account since the skill requires authentication against Salesforce to get started. 

```
Alexa > You need to link a Salesforce account before you can use this skill. I've sent a card to your Alexa app to help.
```

### Test the Linking Flow

1. Go to your Alexa app on your device (or go to https://alexa.amazon.com).
2. Click **Skills**. 
3. Click **Your Skills**.
4. Click the **Dev Skills** header.
5. Find the **Sales Assistant** skill and click it.
6. Click **Settings**.
7. Click **Link Account**.

Your browser or device will then open a window to the Salesforce login screen. 
Enter your Salesforce user credentials, and you should see a page letting you know your skill was successfully linked.

### Use the Skill

Now it's time to use the skill out on an Alexa-enabled device.

1. Try out the following request: **“Alexa, open Sales Assistant”**.
2. Alexa will welcome you and prompt you with some functions you can use.
3. Try **"Tell me my revenue report"**.
4. Alexa will tell you any opportunities that are closing or closed in this current fiscal quarter.
5. Try **"Get my United Oil opportunity"**.
6. Alexa will ask you to help provide some terms to limit the results. Try saying **"Installations"**.
7. Alexa will now read you specific opportunity details. You can then change the opportunity size, stage, amount, or next steps. Try changing each one of these options.
8. Check in your Alexa application or Echo Show and you should receive a card that shows the updated opportunity details.

### Debugging

1. If for any reason you aren't seeing the expected response, debugging via the [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli) can help provide visibility that the skill backend is being invoked. 
2. Once you install the CLI, you can use the the following command to see the logs for your specific application:

```bash
$ heroku logs -a <Your Application Name> --tail
```

[![Next](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/button-next._TTH_.png)](./6-distribute-private-skills.md)
