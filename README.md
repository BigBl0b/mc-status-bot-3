# Minecraft Server Status Bot

Discord Bot that checks status for a specified server and displays it in the Discord sidebar.

**If you have any issues, join my [support server](https://www.discord.gg/wfCGTrp).**

## Installation

1. Clone the repository
   - Press the green `Clone or download` button, and click on Download ZIP
   - Extract the ZIP file
2. Install requirements (listed in the Requirements section)
   - Python is required to run the bot. [Download Python here](https://www.python.org/downloads/)
   - Once you have python installed, you can use `py -m pip install -U REQUIREMENT_HERE` (replace `py` with `python` on Linux and Mac)
   - Use the command above in cmd (or terminal on Linux and Mac).
      You can add all the requirements to the end of the command, seperated by spaces.
   - You could also use the command separately for each requirement
3. Create a config.json file (with notepad or your prefered text editor), and paste this in (make sure to fill in the values):

   ```json
   {
    "bot-token" : "BOT_TOKEN_HERE",
    "prefix" : "PREFIX_HERE",
    "server-ip" : "SERVER_IP_HERE",
   }
   ```

   - If you're unsure on how to create a bot application, [visit this website](https://discordpy.readthedocs.io/en/latest/discord.html).
4. Run bot.py
   - It's recommended you run bot.py in cmd.
   - On Windows, you navigate to the folder where you have the bot, open CMD (shift right click, click `Open Powershell window here`)
   - Type `py bot.py` to start the bot.

## Deploy to Heroku

You may have noticed that you have to keep CMD open if you want your bot to stay online.
With Heroku, you don't have worry about any of this.

Assuming you have installed the bot with the section above, follow these steps:

1. Download and install [Git](https://git-scm.com/downloads)
2. Download and install the [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli#download-and-install)
3. Create a Heroku account
4. Create a git repo in the bot folder
   - Open CMD in the bot's folder (see step 4 in Installation for more info)
   - Use the following commands in CMD:
     - `git init` - This creates the repo
     - `git add .`
     - `git commit -m "Initial commit"` - You can put anything you want inside the quotes
5. Create a Heroku App
   - Use the command `heroku create` to create a Heroku App
6. Deploy to Heroku
   - Use the command `git push heroku master` to upload the files to Heroku
   - To actually turn on the bot, you have to navigate to the [Heroku Dashboard](https://dashboard.heroku.com/apps/)
   - Click `Configure Dynos`
   - Click the pencil icon next to `worker python bot.py`
   - Toggle the switch
   - Your will now start and should appear online shortly
   - You can turn the bot off by toggling off the switch

## Setup Updates (after installation)

Make sure you have installed the bot correctly and are running `bot.py`.
The bot should appear online and should be showing the server's status.

After you have confirmed the bot is installed correctly, follow these steps to set up updates:

1. Create a channel. Call it whatever you like.
2. Set the channel permissions so the status bot has send messages and embed links.
3. Use the `;enable CHANNEL_HERE` command, replacing `CHANNEL_HERE` with the channel you just created.
4. You can use the updates feature with the `;update STATUS_HERE MESSAGE_HERE` command.
   - `STATUS_HERE` can be online, offline, maintenance, buggy, or difficulties.
   - `MESSAGE_HERE` can be left blank. This will set the message to the default.

## Commands

- `;help` - View all commands
- `;server` - View current server's IP
  - `;server set` - Set the server to get status from
- `;players` - Get a list of the players on the server (APPEARS TO BE BROKEN)
- `;updates` - View updates channel
  - `;updates enable` - Enable updates (see Setup Updates section above)
  - `;updates disable` - Disable updates
  - `;updates set` - Update the updates message with a new one (see Setup Updates section above)

## Requirements

- discord.py==1.3.2
- mcstatus
- OPTIONAL: jishaku
