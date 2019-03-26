# bot
# Echobot написан на Python 3
<body>
<p>import telebot</p>
<p>token = ' '</p>
<p>bot = telebot.TeleBot(token)</p>
<p> </p>
<p>@bot.message_handler(content_types=["text"])</p>
<p>def repeat_all_messages(message): </p>
   <p> bot.send_message(message.chat.id, message.text)</p>
<p> </p>
<p>if __name__ == '__main__':</p>
    <p> bot.polling(none_stop=True)</p>
</body>   
</html>

# Добавляем Yandex.Translate API.
# Получаем бот-переводчик
</body>
<p>import telebot</p>
<p>from yandex_translate import YandexTranslate </p>
<p>token = '895984736:AAEGJg2l1woST5RseHHv-FUWAYpOjIbUin4'</p>
<p>bot = telebot.TeleBot(token)</p>
<p>@bot.message_handler(content_types=["text"])</p>
<p>def translate_messages(message):</p>
    <p>translate = YandexTranslate('trnsl.1.1.20190325T181920Z.42182bec9d969ec3.0b475a0a36b7573a03dcfd2a3928afe32013fd9f') </p>
    <p>translate_text = translate.translate(message.text, 'ru-en')['text'][0]</p>
    <p>out_text = message.text + " " + translate_text</p>
   <p> bot.send_message(message.chat.id, out_text)</p>
<p>if __name__ == '__main__':</p>
    <p>bot.polling(none_stop=True)  </p>
      <p> </p>
</body>
</html>
