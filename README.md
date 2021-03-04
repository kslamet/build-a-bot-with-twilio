# Build your First Bot Workshop with Twilio

## Get your first bot up and running

1. Sign up for a Twilio Account (It’s free!) - https://www.twilio.com/try-twilio
2. To access the contents of this course (also free!), you can go to https://www.twiliotraining.com/users/sign_up
3. Open the confirmation email, and login to your new Twilio Account
    1. Twilio provides you with $15 credits for new signup, to use our channel APIs
    2. The entire process of building and testing your bot is free of charge
4. Under all products and services (... on the left), click on Autopilot
5. Hit Start from scratch, and give your currency converter bot a name
6. Check out the greetings 
7. Create your first task called “help” [here](https://github.com/kslamet/build-a-bot-with-twilio/blob/master/help.json)
8. Put in the task samples (yes, one by one)

| help  | Sample |
| ------------- | ------------- |
| 1 | I'm lost  |
| 2 | I don't know what to do |
| 3 | How does this work? |
| 4 | What are you good for? |
| 5 | How can you help? |
| 6 | What do I do? |
| 7 | Help |
| 8 | What things can you do? |
| 9 | What should I do? |
| 10 | What can you do? |
9. We will be using Rates API http://ratesapi.io/ to retrieve the currency exchange data, and have already built out a Twilio Function to fetch the data for us - https://tangerine-toad-5117.twil.io/currency
10. Create the convert_currencies task (we will do this via console, but Twilio does provide a programmatic way of doing this via Command Line Interface) [here](https://github.com/kslamet/build-a-bot-with-twilio/blob/master/convert_currencies_v1.json)
11. Add the task samples (yes, one by one) into the samples section

| convert_currencies  | Sample |
| ------------- | ------------- |
| 1 | Currency conversion |
| 2 | I'd like a forex rate |
| 3 | I'd like to check forex rates |
| 4 | Check some currency rates for me |
| 5 | Check currencies |
| 6 | Convert currencies |
| 7 | What is the forex rate? |
| 8 | Check forex rates |
| 9 | I want to check currency rate |
| 10 | Can I convert currencies? |
| 11 | Can you help me get a forex rate? |
| 12 | I'd like to convert some currencies please |
12. Once done, you can finally build your model!
13. When the build is finished, you can now click on the Simulate button on the bottom right and try out your bot!

## Enhance your bot #1 - submit the currencies at once

1. Under Train Task, click on the Fields section, and add ‘source’ under field name, and ‘Twilio.CURRENCY’ under field type, and hit add field
2. Add ‘target’ under field name, and ‘Twilio.CURRENCY’ under field type and hit add field
3. Going back to samples, add samples to include Fields and Prefill to skip some of the questions

| convert_currencies  | Sample |
| ------------- | ------------- |
| 1 | Convert from {source} |
| 2 | Convert to {target} |
| 3 | I want to convert to {target} |
| 4 | I want to convert from {source} |
| 5 | I want to convert {source} |
| 6 | What's the exchange rate for {source}? |
| 7 | I'd like to convert some {source} |
| 8 | Get me exchange rate for {source} |

4. Switching back to program task, add prefill fields in each question, and save. Completed code sample [here](https://github.com/kslamet/build-a-bot-with-twilio/blob/master/convert_currencies_v2.json)
5. Optionally, you can add more samples that include both source and target. This way when a user passes both field information, we can directly fetch the result.
6. Click Build model.

## Enhance your bot #2 - convert a specific amount

1. Add new *amount* field with type *Twilio.NUMBER*
2. Define new samples which includes the *amount* field
3. (already done) Update our function to cater for the *amount* field
4. Create some samples with the *amount* field

| convert_currencies  | Sample |
| ------------- | ------------- |
| 1 | Convert {amount} {source} to {target} |
| 2 | Help me convert {amount} {source} to {target} |
| 3 | Can you convert {amount} {source} to {target} for me please? |
| 4 | What's exchange rate for {amount} {source} to {target}? |
| 5 | Please convert {amount} {source} to {target} |
| 6 | Convert from {amount} {source} to {target} |
| 7 | I'd like to convert {amount} {source} to {target} |
| 8 | What's the conversion for {amount} {source} to {target} |
| 9 | {amount} {source} to {target} |
| 10 | From {amount} {source} to {target} |
| 11 | How much is {amount} {source} in {target}? |

5. Rebuild our model
6. Test it on the simulator

## (Optional) Connect your bot to some channels

1. Under Autopilot → Bot Name → select Channels
2. The easiest ones to setup are Voice, Messaging and WhatsApp
3. Buy a phone number from Twilio
    1. Go to All Products & Services → Phone Numbers
    2. Click Buy a number, and choose one of the US Local phone numbers which are Voice and SMS ready
    3. Click Buy Number, and give it a friendly name if required
4. Voice setup
    1. In Autopilot → Channels, click into Programmable Voice and copy the link
    2. Go to All Products & Services → Phone Numbers
    3. Go to the phone number that you just purchased
    4. Paste the link in the section “A Call Comes In”
    5. Click Save at the bottom of the page
    6. Try out your bot on Voice! Call the phone number you just bought.
5. Messaging setup
    1. In Autopilot → Channels, click into Programmable Messaging and copy the link
    2. Go to All Products & Services → Phone Numbers
    3. Go to the phone number that you just purchased
    4. Paste the link in the section “A Message Comes In”
    5. Click Save at the bottom of the page
    6. Try out your bot on SMS! Send an SMS to the phone number you just bought.
6. WhatsApp setup
    1. We will be using Twilio’s WhatsApp Sandbox
    2. In Autopilot → Channels, click into WhatsApp and copy the link
    3. Go to All Products & Services → Programmable Messaging
    4. Click Try it out → Try WhatsApp
    5. Send a WhatsApp message to +14155238886 with your code: join word1-word2
    6. You can try sending a one way template, else hit Next: Try Two-Way Messaging
    7. You can try receiving and replying using Two-Way Messaging, else hit Next: Configure your Sandbox
    8. Paste the Autopilot WhatsApp link to the section “When A Message Comes In”
    9. Click Save at the bottom of the page
    10. Try out your bot on WhatsApp! Say Hi to the WhatsApp number after typing join word1-word2

