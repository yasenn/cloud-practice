# Yandex.Cloud practice

Simple tg bot that summarizes longread articles.


## Acknowledgements

 - [galinaalperovich (Galina Alperovich)](https://github.com/galinaalperovich) 
 - [Awesome Readme Templates](https://awesomeopensource.com/project/elangosundar/awesome-README-templates)
 - [readme.so](https://readme.so/editor)


## Environment Variables

To run this project, you will need to add the following environment variables to your .env file

1. `BOT_TOKEN` - Telegram bot token. Get it by creating in [@BotFather](https://t.me/BotFather)
2. `MODEL_NAME` - Summarization model name (options: "sshleifer/distilbart-cnn-12-6", "facebook/bart-large-cnn", "
   facebook/bart-large-xsum"). By default "sshleifer/distilbart-cnn-12-6"
3. `LOG_LEVEL` - Logging level (options: "DEBUG", "INFO", "WARNING", "ERROR", "CRITICAL"). By default "INFO"
4. `FROM_DOCKER` - If the app is running in Docker (options: 1, 0). By default 0


## Installation

1. Clone this repo
2. Install/check [pre-requisites](Prerequisites.md)
    
## Running Tests

Run tests (at first, it will download the model, and it will take a few minutes)

```shell
pytest
```

## Run Locally

Run the bot

```shell
python summary_bot/bot.py
```

Send to your Telegram bot a link to the article and get the summary!


## Deployment

See [Deployment](Deployment.md)


## Features

This Telegram bot will extract the content of an article from a given URL and summarize it for you with the help of AI


## Optimizations ... and beyond!

### There are 24+ Model architectures for (text) transformations (e.g.  summarization)

[ Model architectures  ](https://github.com/huggingface/transformers#model-architectures)

## Train summarization model

[transformers/examples/tensorflow/summarization at main · huggingface/transformers](https://github.com/huggingface/transformers/tree/main/examples/tensorflow/summarization) 

## Add Russian summarization

[sn4kebyt3/ru-bart-large at main](https://huggingface.co/sn4kebyt3/ru-bart-large/tree/main)

> This is a smaller version of the facebook/mbart-large-50 with only Russian and English embeddings left. 



## Related

* [Запускаем контейнерные приложения в Yandex Serverless Containers | Yandex Cloud - Мероприятия и вебинары](https://cloud.yandex.ru/events/760)
* [Потоковый анализ данных с использованием serverless-технологий | Yandex Cloud - Мероприятия и вебинары](https://cloud.yandex.ru/events/686)
* [Практикум. Создание интерактивного serverless-приложения с использованием WebSocket | Yandex Cloud - Мероприятия и вебинары](https://cloud.yandex.ru/events/776)
* [Практикум. Создание Telegram-бота с использованием serverless | Yandex Cloud - Мероприятия и вебинары](https://cloud.yandex.ru/events/831)


# What is Under the hood

## Telegram bot with `aiogram`
[Long-polling - aiogram 3.2.0 documentation](https://docs.aiogram.dev/en/dev-3.x/dispatcher/long_polling.html)

Long-pollingLong-polling is a technology that allows a Telegram server to send updates in case when you don’t have dedicated IP address or port to receive webhooks for example on a developer machine.

## Scraping with `Playwright Python`

[Fast and reliable end-to-end testing for modern web apps | Playwright Python](https://playwright.dev/python/)

## Summarization with a `🤗 Transformers` model (`BartForConditionalGeneration`)

[transformers/examples/pytorch/summarization/run_summarization_no_trainer.py at main · huggingface/transformers](https://github.com/huggingface/transformers/blob/main/examples/pytorch/summarization/run_summarization_no_trainer.py)
Fine-tuning a 🤗 Transformers model on summarization

## License

[MIT](https://choosealicense.com/licenses/mit/)
