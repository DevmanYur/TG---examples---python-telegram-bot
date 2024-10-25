# Examples

In this folder are small examples to show what a bot written with `python-telegram-bot` looks like. Some bots focus on one specific aspect of the Telegram Bot API while others focus on one of the mechanics of this library. Except for the [`rawapibot.py`](#pure-api) example, they all use the high-level framework this library provides with the [`telegram.ext`](https://python-telegram-bot.readthedocs.io/en/latest/telegram.ext.html) submodule.

All examples are licensed under the [CC0 License](https://github.com/python-telegram-bot/python-telegram-bot/blob/v13.x/examples/LICENSE.txt) and are therefore fully dedicated to the public domain. You can use them as the base for your own bots without worrying about copyrights.

Do note that we ignore one pythonic convention. Best practice would dictate, in many handler callbacks function signatures, to replace the argument `context` with an underscore, since `context` is an unused local variable in those callbacks. However, since these are examples and not having a name for that argument confuses beginners, we decided to have it present.

```
В этой папке представлены небольшие примеры, показывающие, как выглядит бот, написанный 
 помощью "python-telegram-bot". Некоторые боты фокусируются на одном конкретном аспекте 
 Telegram Bot API, в то время как другие - на одной из механик этой библиотеки. 
 За исключением примера [`rawapibot.py`](#pure-api), все они используют фреймворк 
 высокого уровня, предоставляемый этой библиотекой с подмодулем .

Все примеры лицензированы по лицензии  и, следовательно, 
являются общественным достоянием. Вы можете использовать 
их в качестве основы для своих собственных ботов, 
не беспокоясь об авторских правах.

Обратите внимание, что мы игнорируем одно соглашение python. 
Во многих сигнатурах функций обратного вызова обработчика 
рекомендуется заменять аргумент "context" символом подчеркивания, 
поскольку "context" является неиспользуемой локальной переменной 
в этих обратных вызовах. Однако, поскольку это примеры и отсутствие 
названия для этого аргумента сбивает с толку новичков, мы решили привести его в соответствие.
```


### [`echobot.py`](https://github.com/python-telegram-bot/python-telegram-bot/blob/v13.x/examples/echobot.py) 
This is probably the base for most of the bots made with `python-telegram-bot`. It simply replies to each text message with a message that contains the same text.
```
Вероятно, это основа для большинства ботов, созданных с помощью "python-telegram-bot". Он просто отвечает 
на каждое текстовое сообщение сообщением, содержащим тот же текст.
```

### [`timerbot.py`](https://github.com/python-telegram-bot/python-telegram-bot/blob/v13.x/examples/timerbot.py) 
This bot uses the [`JobQueue`](https://python-telegram-bot.readthedocs.io/en/latest/telegram.ext.jobqueue.html) class to send timed messages. The user sets a timer by using `/set` command with a specific time, for example `/set 30`. The bot then sets up a job to send a message to that user after 30 seconds. The user can also cancel the timer by sending `/unset`. To learn more about the `JobQueue`, read [this wiki article](https://github.com/python-telegram-bot/python-telegram-bot/wiki/Extensions-%E2%80%93-JobQueue).
```
Этот бот использует класс для отправки сообщений по расписанию. Пользователь устанавливает 
таймер с помощью команды "/set" на определенное время, например "/set 30`. Затем бот настраивает 
задание на отправку сообщения этому пользователю через 30 секунд. 
Пользователь также может отменить таймер, отправив сообщение "/unset". 
Чтобы узнать больше о `очереди заданий`, прочитайте.
```

### [`conversationbot.py`](https://github.com/python-telegram-bot/python-telegram-bot/blob/v13.x/examples/conversationbot.py)
A common task for a bot is to ask information from the user. In v5.0 of this library, we introduced the [`ConversationHandler`](https://python-telegram-bot.readthedocs.io/en/latest/telegram.ext.conversationhandler.html) for that exact purpose. This example uses it to retrieve user-information in a conversation-like style. To get a better understanding, take a look at the [state diagram](https://github.com/python-telegram-bot/python-telegram-bot/blob/v13.x/examples/conversationbot.png).
```
Обычной задачей бота является запрос информации у пользователя. 
В версии 5.0 этой библиотеки мы ввели функцию для этой цели. 
В этом примере она используется для получения информации 
о пользователе в стиле диалога. Чтобы лучше понять, взгляните на [диаграмму состояний]
```

### [`conversationbot2.py`](https://github.com/python-telegram-bot/python-telegram-bot/blob/v13.x/examples/conversationbot2.py)
A more complex example of a bot that uses the `ConversationHandler`. It is also more confusing. Good thing there is a [fancy state diagram](https://github.com/python-telegram-bot/python-telegram-bot/blob/v13.x/examples/conversationbot2.png) for this one, too!
```
Более сложный пример бота, использующего "обработчик разговоров". 
Он также более запутанный. 
Хорошо, что для этого тоже есть [причудливая диаграмма состояний]!
```

### [`nestedconversationbot.py`](https://github.com/python-telegram-bot/python-telegram-bot/blob/v13.x/examples/nestedconversationbot.py)
A even more complex example of a bot that uses the nested `ConversationHandler`s. While it's certainly not that complex that you couldn't built it without nested `ConversationHanldler`s, it gives a good impression on how to work with them. Of course, there is a [fancy state diagram](https://github.com/python-telegram-bot/python-telegram-bot/blob/v13.x/examples/nestedconversationbot.png) for this example, too!
```
Еще более сложный пример бота, использующего вложенный обработчик разговоров. 
Хотя он, конечно, не настолько сложен, чтобы его нельзя 
было создать без вложенного обработчика разговоров, 
он дает хорошее представление о том, как с ним работать. 
Конечно, для этого примера тоже есть 
[необычное состояние diagram]!
```

### [`persistentconversationbot.py`](https://github.com/python-telegram-bot/python-telegram-bot/blob/v13.x/examples/persistentconversationbot.py)
A basic example of a bot store conversation state and user_data over multiple restarts.
```
Простой пример того, 
как бот сохраняет состояние диалога и пользовательские данные в течение нескольких перезапусков.
```

### [`inlinekeyboard.py`](https://github.com/python-telegram-bot/python-telegram-bot/blob/v13.x/examples/inlinekeyboard.py)
This example sheds some light on inline keyboards, callback queries and message editing. A wikipedia site explaining this examples lives at https://github.com/python-telegram-bot/python-telegram-bot/wiki/InlineKeyboard-Example.
```
Этот пример проливает некоторый свет на встроенные клавиатуры, запросы 
обратного вызова и редактирование сообщений. Сайт Википедии, 
объясняющий эти примеры, находится по адресу
```

### [`inlinekeyboard2.py`](https://github.com/python-telegram-bot/python-telegram-bot/blob/v13.x/examples/inlinekeyboard2.py)
A more complex example about inline keyboards, callback queries and message editing. This example showcases how an interactive menu could be build using inline keyboards.
```
Более сложный пример, посвященный встроенным клавиатурам, 
запросам обратного вызова и редактированию сообщений. 
В этом примере показано, как можно создать интерактивное меню с использованием встроенных клавиатур.
```

### [`deeplinking.py`](https://github.com/python-telegram-bot/python-telegram-bot/blob/v13.x/examples/deeplinking.py)
A basic example on how to use deeplinking with inline keyboards.
```
Простой пример того, как использовать глубокую компоновку со встроенными клавиатурами.
```

### [`inlinebot.py`](https://github.com/python-telegram-bot/python-telegram-bot/blob/v13.x/examples/inlinebot.py)
A basic example of an [inline bot](https://core.telegram.org/bots/inline). Don't forget to enable inline mode with [@BotFather](https://telegram.me/BotFather).
```
Простой пример работы [онлайн-бота]. Не забудьте включить встроенный режим с помощью [@BotFather]
```

### [`pollbot.py`](https://github.com/python-telegram-bot/python-telegram-bot/blob/v13.x/examples/pollbot.py)
This example sheds some light on polls, poll answers and the corresponding handlers.
```
Этот пример проливает некоторый свет на опросы, ответы на них и соответствующие обработчики.
```

### [`passportbot.py`](https://github.com/python-telegram-bot/python-telegram-bot/blob/v13.x/examples/passportbot.py)
A basic example of a bot that can accept passports. Use in combination with [`passportbot.html`](https://github.com/python-telegram-bot/python-telegram-bot/blob/v13.x/examples/passportbot.html). Don't forget to enable and configure payments with [@BotFather](https://telegram.me/BotFather). Check out this [guide](https://github.com/python-telegram-bot/python-telegram-bot/wiki/Telegram-Passport) on Telegram passports in PTB.
```
Простой пример бота, который может принимать паспорта. 
Используйте в сочетании с [`passport bot.html`]
Не забудьте включить и настроить платежи с помощью [@BotFather]. 
Ознакомьтесь с этим [руководством] по Telegram passports в PTB.
```

### [`paymentbot.py`](https://github.com/python-telegram-bot/python-telegram-bot/blob/v13.x/examples/paymentbot.py)
A basic example of a bot that can accept payments. Don't forget to enable and configure payments with [@BotFather](https://telegram.me/BotFather).
```
Простой пример бота, который может принимать платежи. 
Не забудьте включить и настроить платежи с помощью [@BotFather]
```

### [`errorhandlerbot.py`](https://github.com/python-telegram-bot/python-telegram-bot/blob/v13.x/examples/errorhandlerbot.py)
A basic example on how to set up a custom error handler.
```
Простой пример того, как настроить пользовательский обработчик ошибок.
```

### [`chatmemberbot.py`](https://github.com/python-telegram-bot/python-telegram-bot/blob/v13.x/examples/chatmemberbot.py)
A basic example on how `(my_)chat_member` updates can be used.
```
Простой пример того, как можно использовать обновления `(my_)chat_member`.
```

### [`contexttypesbot.py`](https://github.com/python-telegram-bot/python-telegram-bot/blob/v13.x/examples/contexttypesbot.py)
This example showcases how `telegram.ext.ContextTypes` can be used to customize the `context` argument of handler and job callbacks.
```
В этом примере показано, как "типы telegram.text.Context" 
можно использовать для настройки аргумента "context" 
в обработчике и обратных вызовах заданий.
```

### [`arbitrarycallbackdatabot.py`](https://github.com/python-telegram-bot/python-telegram-bot/blob/v13.x/examples/arbitrarycallbackdatabot.py)
This example showcases how PTBs "arbitrary callback data" feature can be used.
```
В этом примере показано, как можно использовать функцию PTBs "произвольные данные обратного вызова".
```

## Pure API
The [`rawapibot.py`](https://github.com/python-telegram-bot/python-telegram-bot/blob/v13.x/examples/rawapibot.py) example uses only the pure, "bare-metal" API wrapper.
```
В примере [`rawapibot.py`] используется только чистая, "голая" оболочка API.
```
