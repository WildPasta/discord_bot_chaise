# Discord chaise bot

## The project

A simple discord bot that is designed to roast people arriving late (or not arriving at all) in class.

## Installing requirements

Get a discord API token from the documentation [here](https://discordpy.readthedocs.io/en/stable/discord.html).
While retrieving the token API, also copy your **Application ID**.

### Running on docker  
```
docker build -t wildpasta/discord_bot_chaise:1.8.2 .
docker run --env DISCORD_TOKEN="xxx" --env DISCORD_APP_ID="xxx" wildpasta/discord_bot_chaise:1.8.2
```


### Running on host
- Run the bot
```
export DISCORD_TOKEN="xxx"
export DISCORD_APP_ID="xxx"


python -m pip install -r requirements.txt
python bot_chaise.py &
```

### Process
- Fill database with input catchphrases using `!add`



## Features

### Chaise 🪑

Increment the number of the *chaised* person.

```
!chaise @someone
```
### Chaise 🪑🪑

Increment the number of the *chaised* person.

```
!chaise "@someone @someone_else"
```

### Remove a chaise ❌

Decrement the number of the *unchaised* person.

```
!unchaise @someone
```

### Add sentences ➕

Adding new sentence in the database.

**The `<>` are explicitely needed for this command**

```
!add "foo <pseudo> bar"
```

### Leaderboard 🥇

Displaying the leaderboard, order by higher chaise value.
The higher you are, the more often you arrive late !

```
!top
```

### Reset leaderboard ☢️

Set all number of chaise for all member to 0.

```
!reset
```

### Version 🎲

Displaying the version of the bot.

```
!version
```

### History 🔍

Displaying the history since bot's creation !

```
!history
```

### Listing 📖

Displaying all sentences in database !

```
!list
```

### Delete sentences 🗑️

Delete a sentence in database with a given sentence ID.
Appropriate <id> can be founded in `!list` command.

```
!delete <id>
```

### Player management 💁

Add a user in the SQL database to enter the game:

```
!adduser @someone
```

You can also remove an user with:

```
!deluser @someone
```

## TO-DO

 - [X] Bot tagging the users
 - [X] Scoreboard of users
 - [X] Adding new sentence in database
 - [X] Resetting the database
 - [X] Remove/cancel a chaise
 - [X] History of late arrivals 
 - [X] Adding history with specific NickNames
 - [X] Adding custom sentences
 - [X] Prevent unchaise to go below 0
 - [X] Unchaise should remove the last entry in history
 - [X] A user cannot unchaise himself
 - [X] Show all sentences
 - [X] Delete custom sentence
 - [X] Add a user in the database
 - [X] Setting moderator permission 
 - [X] Malus (+2 chaises) if you rejoin the game after rage-quitting
 - [X] Using logging module instead of print (DEBUG : message)
 - [X] Create !help command
 - [X] Chaise multiple person
 - [ ] Stock hardcoded sentences (responses from the bot) in database AND in FR/EN langage