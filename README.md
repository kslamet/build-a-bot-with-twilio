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
7. Create your first task called “help”
8. Put in the task samples (yes, one by one)
| Task Name  | Sample |
| ------------- | ------------- |
| Help | I'm lost  |
|  | I don't know what to do |
|  | How does this work? |
|  | What are you good for? |
|  | How can you help? |
|  | What do I do? |
|  | Help |
|  | What things can you do? |
|  | What should I do? |
|  | What can you do? |
9. We will be using Rates API http://ratesapi.io/ to retrieve the currency exchange data, and have already built out a Twilio Function to fetch the data for us - https://tangerine-toad-5117.twil.io/currency
10. Create the task action (we will do this via console, but Twilio does provide a programmatic way of doing this via Command Line Interface)
11. Add the task samples (yes, one by one) into the samples section
| Task Name  | Sample |
| ------------- | ------------- |
| convert_currencies | Currency conversion |
|  | I'd like a forex rate |
|  | I'd like to check forex rates |
|  | Check some currency rates for me |
|  | Check currencies |
|  | Convert currencies |
|  | What is the forex rate? |
|  | Check forex rates |
|  | I want to check currency rate |
|  | Can I convert currencies? |
|  | Can you help me get a forex rate? |
|  | I'd like to convert some currencies please |
12. Once done, you can finally build your model!
13. When the build is finished, you can now click on the Simulate button on the bottom right and try out your bot!

## Enhance your bot #1 - submit the currencies at once

1. Under Train Task, click on the Fields section, and add ‘source’ under field name, and ‘Twilio.CURRENCY’ under field type, and hit add field
2. Add ‘target’ under field name, and ‘Twilio.CURRENCY’ under field type and hit add field
3. Going back to samples, add samples to include Fields and Prefill to skip some of the questions
| Task Name  | Sample |
| ------------- | ------------- |
| convert_currencies | Convert from {source} |
|  | Convert to {target} |
|  | I want to convert to {target} |
|  | I want to convert from {source} |
|  | I want to convert {source} |
|  | What's the exchange rate for {source}? |
|  | I'd like to convert some {source} |
|  | Get me exchange rate for {source} |
4. Switching back to program task, add prefill fields in each question, and save. Completed code sample below
5. Optionally, you can add more samples that include both source and target. This way when a user passes both field information, we can directly fetch the result.
6. Click Build model.

## Enhance your bot #2 - convert a specific amount

1. Add new *amount* field with type *Twilio.NUMBER*
2. Define new samples which includes the *amount* field
3. (already done) Update our function to cater for the *amount* field
4. Create some samples with the *amount* field

| Task Name  | Sample |
| ------------- | ------------- |
| convert_currencies | Convert {amount} {source} to {target} |
|  | Help me convert {amount} {source} to {target} |
|  | Can you convert {amount} {source} to {target} for me please? |
|  | What's exchange rate for {amount} {source} to {target}? |
|  | Please convert {amount} {source} to {target} |
|  | Convert from {amount} {source} to {target} |
|  | I'd like to convert {amount} {source} to {target} |
|  | What's the conversion for {amount} {source} to {target} |
|  | {amount} {source} to {target} |
|  | From {amount} {source} to {target} |
|  | How much is {amount} {source} in {target}? |
5. Rebuild our model
6. Test it on the simulator

## (Optional) Connect your bot to some channels

1. Under Autopilot → Bot Name → select Channels
2. The easiest ones to setup are Voice, Messaging and WhatsApp
3. Buy a phone number from Twilio
    1. Go to All Products & Services → Phone Numbers
    2. Click Buy a number, and choose one of the US Local phone numbers which are Voice and SMS ready
    3. Click Buy <Number>, and give it a friendly name if required
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
    5. Send a WhatsApp message to +14155238886 with your code: join <word1>-<word2>
    6. You can try sending a one way template, else hit Next: Try Two-Way Messaging
    7. You can try receiving and replying using Two-Way Messaging, else hit Next: Configure your Sandbox
    8. Paste the Autopilot WhatsApp link to the section “When A Message Comes In”
    9. Click Save at the bottom of the page
    10. Try out your bot on WhatsApp! Say Hi to the WhatsApp number after typing join <word1>-<word2>.

