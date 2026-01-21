# AeneaBot

Your personal Telegram bot with several functions.

AeneaBot is a Telegram Chat Bot which includes its own conversational AI base in Ollama. It is developed in python3.

Apart from several commands, all messages will be forwarded to an Ollama API server of your election so you can go full IA!

Built with:
- [Python-Telegram-Bot](https://github.com/python-telegram-bot/python-telegram-bot)
- Lots of love :)

#### Commands

- /health - Run an active healthcheck. Returns a list of components check and its status
- /dice - Rolls a 6 sides dice.
- /man - Search a Linux/Unix command in the man pages. Defaults to Debian distro.(More info [aquí](http://www.polarhome.com/service/man/))
- /park - Park an object in the Parking (if database is configured SQLite database)
- /list_parking - List all object currentl in the Parking. Includes its UID and the date they were parked.
- /clear_object - Removes an object from the Parking. Must specify an object UID
- /clear_parking - Removes all objects from the Parking.

#### How to run
Use the included file config.yml.sample to create a config.yml file and fill the following variables:

  * token: Telegram bot Token
  * botname: Your Telegram bot name. Be creative!
  * authuser: Telegram username allowed to use the bot (yours)
  * ollama_url: URL of the Ollama server whith will be used to provide AI.
  * ollama_model: Name of the model configured in Ollama.
  * sqlitepath: Path for the SQLite3 persistent database. Required for Parking functionality.
  * loglevel: Log level output. See [python docs](https://docs.python.org/3/howto/logging.html#when-to-use-logging)

[You can install it using Helm from my repo](https://sergiofernandezcordero.github.io/ygdrassil/) including the AeneaAI sidecar which provides your own AI using Ollama.

And that's all! Your bot is up and running. You can add the modifications you want.

Looking for the source code? Look [here](https://github.com/SergioFernandezCordero/AeneaBot).