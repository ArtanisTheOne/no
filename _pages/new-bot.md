---
title: "How to install and setup Rita for the First Time."
permalink: /new-bot/
excerpt: "How to install and setup Rita for the First Time."
last_modified_at: 2019-09-10T14:00:00+01:00   #Please Update, The +00:00 is the Time Zone difference
redirect_from:
  - /theme-setup/
toc: true

# Date formatting & Date Parsing - Let formatting and parsing date expressed in ISO8601 format.
# Can be obtained from https://dencode.com/en/date
# ---- Defined ----
# YYYY-MM-DD'T'hh:mm:ssTZD (e.g. 2015-12-11T20:28:30+01:00)
# YYYY = four-digit year
# MM = two-digit month (01=January, etc.)
# DD = two-digit day of month (01 through 31)
# hh = two digits of hour (00 through 23) (am/pm NOT allowed)
# mm = two digits of minute (00 through 59)
# ss = two digits of second (00 through 59)
# TZD = time zone designator (Z or +hh:mm or -hh:mm)
---

Rita is a an automatic translation bot built using `discord.js` and `Google Translate API`.

## Setting up a New Bot (RECOMMENDED)

**To deploy a free translation bot that you can add to your discord server, follow these easy steps.**

### Step 1 - Fork this repo.

If you don't yet have a github account, [create one](https://github.com/join)! It's free and easy.

The repo to fork is located here: [repo](https://github.com/ZyC0R3/RitaBot)

Use the button in the upper righthand side of this page to fork the repo so that it will be associated with your github account.

### Step 2 - Create a new Discord App

Create a new [Discord App](https://discordapp.com/developers/applications/me/create)

Give app a friendly name and click the **Create App** button

 *I like the name **Rita**, but feel free to pick something different if you want.*

Take note of the app **CLIENT ID**, you will need it later

Scroll down to the **Bot** section

Click the **Create a Bot User** button

Click the **Yes, do it!** button

Copy the bot's **TOKEN**, you will need it later


### Step 3 - Create a Heroku account

Create a new [Heroku](https://id.heroku.com/signup/login ) account. *(It's free!)*

Create a new app. It's name must be unique and composed of all lowercase letters and dashes.
Something like `yourname-discordbot` is fine

Under **Deployment Method** select Github. Connect to your Github account and search for this repo by name.

Scroll down to the manual deploy section, and select the **master** branch. Click deploy branch, and wait for the successfully deployed message.

Go to the **Resources** tab and look for the addons section. Search 'Postgres', and add a 'Hobby Dev - Free' version of Heroku Postgres. This will be automatically attached as your bot's database.

Go to the **Settings** tab. Click to reveal Config Variables, then add a new one. The key will be **DISCORD_TOKEN**, and the value will be your discord bot's token that you copied earlier.

Go to the **Overview** tab and click configure dynos. Turn off the default `web npm start` dyno and turn on the `worker node src/bot.js` dyno. Your bot will now be up and running!

### Step 4 - Invite your bot to your server and configure it!

Replace the "CLIENTID" in the following url with the client ID of your bot:

```
https://discordapp.com/oauth2/authorize?&client_id=CLIENTID&scope=bot&permissions=8
```

Visit the resulting url and add your bot to any server where you have admin privileges.

Once added, your bot should show up more or less instantaneously. Type `!t help` within the discord chat for more details on how to use it. Happy translating!
