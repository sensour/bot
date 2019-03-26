# bot
# Echobot написан на Python 3
<body>
import telebot
token = ' '
bot = telebot.TeleBot(token)

@bot.message_handler(content_types=["text"])
def repeat_all_messages(message): 
    bot.send_message(message.chat.id, message.text)

if __name__ == '__main__':
     bot.polling(none_stop=True)>
# Добавляем Yandex.Translate API.
# Получаем бот-переводчик
import telebot
from yandex_translate import YandexTranslate 
token = '895984736:AAEGJg2l1woST5RseHHv-FUWAYpOjIbUin4'
bot = telebot.TeleBot(token)
@bot.message_handler(content_types=["text"])
def translate_messages(message):
    translate = YandexTranslate('trnsl.1.1.20190325T181920Z.42182bec9d969ec3.0b475a0a36b7573a03dcfd2a3928afe32013fd9f') #api yandex
    translate_text = translate.translate(message.text, 'ru-en')['text'][0]
    out_text = message.text + " " + translate_text
    bot.send_message(message.chat.id, out_text)
if __name__ == '__main__':
     bot.polling(none_stop=True)    
</body>
</html>
