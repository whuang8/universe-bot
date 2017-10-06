# Universe Bot

<!-- MDTOC maxdepth:6 firsth1:2 numbering:0 flatten:0 bullets:1 updateOnSave:1 -->

- [Prerequisites](#prerequisites)   
   - [Tools](#tools)   
- [Part 1: Steps for Getting Started](#part-1-steps-for-getting-started)   
- [Part 2: Pick Your Own Adventure](#part-2-pick-your-own-adventure)   
   - [Add new bot messages](#add-new-bot-messages)   
   - [Get your own bot instead of our default bot](#get-your-own-bot-instead-of-our-default-bot)   
   - [Deploy to Heroku](#deploy-to-heroku)   
   - [Create your own Hubot from scratch with hubot.github.com](#create-your-own-hubot-from-scratch-with-hubotgithubcom)   

<!-- /MDTOC -->

Universe Bot is a chat bot built on the [Hubot][hubot] framework. It was initially generated by [generator-hubot][generator-hubot], and configured to be deployed on [Glitch][glitch] to get you up and running as quickly as possible. Glitch will deploy your hubot and keep it running as long as your web browser has it open. If you want to deploy to something more persistent, see the directions in the Choose Your Own Adventure section below to deploy to Heroku.

This README is intended to help get you started. Definitely update and improve
to talk about your own instance, how to use and deploy, what functionality is
available, etc!

[glitch]: http://glitch.com
[heroku]: http://www.heroku.com
[hubot]: http://hubot.github.com
[generator-hubot]: https://github.com/github/generator-hubot

## Prerequisites

### Tools

Tool | Used for
--- | ---
[GitHub](https://github.com) (Please log in now) | To store and version code
[Glitch](https://glitch.com) (Please login with GitHub now) | A temporary server for your chat bot
[Slack team](https://slack.com/get-started#create) (Please create a new Slack team) | To interact with your chatbot


## Part 1: Get the Code
1. Fork the [universeworkshops/universe-bot repository](https://github.com/universeworkshops/universe-bot)
2. In [Glitch](https://glitch.com), import your fork of the universeworkshops/universe-bot repository
  - Click 'Edit Code'
  - Click the title of the app on the top left
  - Select 'Advanced Options'
  - By 'Import from GitHub', click 'Grant Access' and allow the app the proper permissions
  - Select 'Import from GitHub' and type the name of your fork, `USERNAME/universe-bot`
  - **Note: Any changes made in Glitch will not automatically be made in your fork. The steps are similar to importing, but instead select 'Export to GitHub'.**

> :tada: Congratulations, you've just: 
> - Created a fork
> - Integrated with Glitch

## Part 2: Get the Bot
1. **[Create your own Slack team](https://slack.com/get-started#create)** and follow the instructions above to have your bot listen to your own private team. A free Slack team can have up to five apps.
1. **Create your Hubot App**
  - Log into your new Slack team in your web browser using the credentials you created
  - Find the Hubot App Dashboard by going to `/apps` from your Slack team and searching "Hubot". (ex: `https://build-a-chatbot.slack.com/apps`)
  - Click "Add Configuration"
  - Give your new bot a name (like universe-bot), select `Add Hubot Integration`, and wait a couple of seconds for the page to refresh with the configuration of your new bot!
    - _Note: When you select `Add Hubot Integration`, Slack takes a few seconds to create the new app so be patient. If it seems to take too long, try going back to the [Hubot App Dashboard](https://build-a-chatbot.slack.com/apps/A0F7XDU93-hubot), and your Hubot may be there._
2. **Reconfigure your Hubot Instance**
  - Once your app is created in Slack, copy the `HUBOT_SLACK_TOKEN=` line provided in the "Setup Instructions" section of its configuration
  - In your Glitch app, go to your `.env` file and replace the entire file with this line
3. **Test your bot**
  - Return to Slack (your new team) where you should find your bot's name under `APPS`
  - Enter the `#general` channel, and invite your bot by `@mention`ing them.
  - Use your bot's name and a message it will recognize, like `universe-bot universe` to test its response

> :tada: Congratulations, you've just: 
> - Used Glitch to deploy live code
> - Integrated with Slack
> - Connected an external integration with Slack
> - Created a standalone bot, not dependant on any other repositories
> - Created (or integrated with) another slack team
> - Gotten so much closer to having a bot in your daily workflow - maybe it's done! 


## Part 3: Customize the Bot
Mix and match from the following activities. It doesn't matter if you do none of them or all of them, or what order you do them in. Each activity is independent of the others and is a way to fill out functionality of the bot for your specific use. If you don't have time to get to everything today, don't worry! You still have all of the instructions on your fork.

### Add new bot messages
1. **Find the existing message code**
  - The basic messages are stored in `scripts/messages.coffee`.
  - So far, our bot is best at watching for incoming chat messages, and uses regex to know when to respond.
  - Test out the current messages (and your regex knowledge) to see what our Bot can say:
    - `/universe/gim`
    - `/lunch/gim`
    - `/movie/i`
    - `/fruit/i`
  - It's easy to add simple, static messages here. This is the point of contact for more interactive messages, too.
2. **Add a new message and trigger that will be unique to your bot.**
  - If we all write a message for the same trigger, and try that trigger in the chat room, every bot will respond.
  - Change line 16, replacing `USERNAME` with your own username.
  - Change the response to be whatever you'd like, maybe something like "I heard they're the best tennis player in the country."...or something more true, perhaps.
  > _Note: Remember that bots are interacting with people. Bots should be programmed to adhere to the code of conduct in any given organization, and should be built empathetically._
3. **Test this out in the Slack channel.**
4. **Specialize the bot**.
  - Whether you want to add more commands that are basic call and response or add more advanced functionality, code them in now.
  - If you aren't sure how to complete the feature, add some comments in the code so you can come back to it later. 

> :tada: Congratulations, you've just: 
> - Edited JavaScript to customize bot responses
> - Interacted with a bot through chat
> - Set plans for a bot for future use

## Part 4: Sync from Glitch to GitHub 
When you made changes in Glitch, they are automatically deployed. However, they aren't committed back to GitHub. 
1. Click the title of the app, then select "Advanced Options" in the dropdown menu
1. Click "Export to GitHub"
1. Make sure the repository names matches the repository that you'd like to export to, and click OK
1. Update `master` with the new commit(s)
  - Back in your `universe-bot` fork on GitHub, you will see there is now a branch called `glitch`
  - For now, this could be OK because at least your code is saved
  - To add these changes to the master branch, create a [pull request](https://help.github.com/articles/about-pull-requests/) with `base fork: USERNAME/universe-bot`, `base: master` and `compare: glitch`. It's a good idea to add more cnotext to the body and title of this pull request for future reference. 
  - Merge the pull request and delete the `glitch` branch.

> _Note: The information in the `.env` file is confidential, so it is not pushed back to GitHub. Do not commit tokens._

> :tada: Congratulations, you've just: 
> - Committed your new work in GitHub
> - Set up your work to be shared with colleagues and other developers 
> - Created a record of your workshop day to come back and improve on more later

## Part 5: Deploy to Heroku
Glitch is a fantastic way to test a deployment, but it only runs as long as you have it open in your browser. If you want to have your bot running all the time, you'll need to find another way to deploy. Heroku is a great option if you want to use a hosted service. To deploy on Heroku, follow these directions.

1. If you don't already have a Heroku account, [register for one here](https://signup.heroku.com)
2. After you've signed into your new account, [create a new app](https://dashboard.heroku.com/new-app).
3. Go to the `Deploy` tab and select GitHub as your deployment method
  - If you haven't connected to your Heroku account to GitHub, click `Connect to GitHub` (seen below)
  - Once connected, select your username, enter "universe-bot", and select `Connect`  ![connect-to-github](https://user-images.githubusercontent.com/11798972/28807953-e65a12fe-7635-11e7-9c8b-9892d45f33da.png)

4. In the `Manual Deploy` section, click `Deploy Branch`
5. Add your Hubot Slack Token to your Heroku app's environment variable
  - Get your Slack Token from the `.env` file in your Glitch app or directly from your Hubot configuration on Slack
  - Navigate to the `Settings` tab on your Heroku app
  - Select the `Reveal Config Vars` button
  - Type `HUBOT_SLACK_TOKEN` in the `KEY` field and your token into the `VALUE` field, then click `Add`
6. Open Slack to test your deployment
  - _Note: To test properly, make sure to close the Glitch browser._

> :tada: Congratulations, you've just: 
> - Integrated with Heroku
> - Set up a bot that will always be listening - even when Glitch isn't open!

### Create your own Hubot from scratch with hubot.github.com
The original repository for this project was generated as an npm app using the documentation from GitHub's [open-source version of Hubot](https://hubot.github.com/docs/). To gain a fuller understanding of how Hubot works, consider starting from the beginning by following the [Getting Started with Hubot](https://hubot.github.com/docs/) walkthrough.
