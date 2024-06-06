# Raponchi
Raponchi is a Python script which daily looks at Bing for a random frog photo, composes a name based on a predefined list,
and post them together in a Twitter account. And that's all. No context, no motivation, no philosophy, no reason. Just frogs.
I really love frogs. But it can be easily modified to make the same with any other thing.

Built with:
- [Tweepy](https://docs.tweepy.org/en/stable/index.html)
- Lots of frogs

#### How to run
You need the following envvars as specified:

#### Environment
- TIMEZONE: Timezone. Defaults to system timezone
- LOGLEVEL: Log level. Defaults to INFO

#### Frog generation parameters
- FROGWORD: Keyword to be used. Defaults to "rana"
- PATH_TO_FROGS: Temporary path where frog images will be stored. Defaults to "dataset"
- FROG_NUMBER: Number of frog images downloaded in each batch. Defaults to 5
- FROG_SCHEDULER_INTERVAL: How frequently the scheduler will poll for pending jobs. Defaults to 30 seconds
- FROG_NAMES_URL: Online source for frog names. Should be a URL to a plain text file with names, one per line.

#### Twitter Publication parameters
- TW_CONSUMER_KEY: Twitter Consumer Key
- TW_CONSUMER_SECRET: Twitter Consumer Secret
- TW_ACCESS_TOKEN: Twitter Access Token
- TW_ACCESS_TOKEN_SECRET: Twitter Access Token Secret

#### ElasticSerch Logging Integration

You can send logs to ElasticSearch. Assumed TLS and Credentials is active, but TLS verification can be disabled.

- ELK_URL: URL of ElasticSearch cluster used to send logs. TLS assumed. If ELK_URL and ELK_PORT are defined, ELK logger will be configured.
- ELK_PORT: Port of the ElasticSearch cluster used to send logs. If ELK_URL and ELK_PORT are defined, ELK logger will be configured.
- ELK_USER: ELK User
- ELK_PASS: ELK Password
- ELK_TLS_VERIFY: Allows disabling TLS verification for ELK. Default to True
- ELK_INDEX: Name of the index used to store logs. Defaults to raponchi-log

#### Prometheus Exporter

By default, Raponchi exposes port 10090 for prometheus metrics.
The follwing metrics are implemented:

- raponchi_total_frogs: Counter. Total frogs launched
- raponchi_success_frogs: Counter. Successfully published frogs
- raponchi_error_frogs: Counter. Unpublished frogs due to error
- raponchi_latency: Histogram. Total time spent from invocation of scheduler until frog publishing
- raponchi_bing_latency: Histogram. Time spent searching and downloading from Bing
- raponchi_twitter_latency: Histogram. Time spent publishing frog on Twitter

[You can install it using Helm from my repo](https://sergiofernandezcordero.github.io/ygdrassil/)

Looking for the source code? Look [here](https://github.com/SergioFernandezCordero/raponchi).