# Raponchi
Raponchi is a Python script which daily looks at Bing for a random frog photo, composes a name based on a predefined list,
and post them together in a Twitter account. And that's all. No context, no motivation, no philosophy, no reason. Just frogs.
I really love frogs. But it can be easily modified to make the same with any other thing.

Built with:
- [Tweepy](https://docs.tweepy.org/en/stable/index.html)
- Lots of frogs

#### How to run
You need the following envvars as specified:

- TIMEZONE: Timezone. Defaults to system timezone
- LOGLEVEL: Log level. Defaults to INFO
- PATH_TO_FROGS: Temporary path where frog images will be stored. Defaults to "dataset"
- FROG_NUMBER: Number of frog images downloaded in each batch. Defaults to 5
- FROG_SCHEDULER_INTERVAL: How frequently the scheduler will poll for pending jobs. Defaults to 30 seconds
- FROG_NAMES_URL: Online source for frog names. Should be a URL to a plain text file with names, one per line.
- FROG_SCHEDULER_RUN_NOW: Run all scheduled jobs at startup without waiting to its schedule. Useful for development
- TW_CONSUMER_KEY: Twitter Consumer Key
- TW_CONSUMER_SECRET: Twitter Consumer Secret
- TW_ACCESS_TOKEN: Twitter Access Token
- TW_ACCESS_TOKEN_SECRET: Twitter Access Token Secret

[You can install it using Helm from my repo](https://sergiofernandezcordero.github.io/ygdrassil/)

Looking for the source code? Look [here](https://github.com/SergioFernandezCordero/raponchi).