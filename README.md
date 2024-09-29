"# songrahi_tele_bot" 
from tele_token import token  # Importing the 'token' from token.py

import telegram.ext
#from queue import Queue

Token=token
#update_queue = Queue()

#updater = telegram.ext.Updater(Token, update_queue)
#updater=telegram.ext._updater("8100590178:AAEc1BQtfUPl5OdCahlQNEI2SP0dR5AdvUs",use_context=True)
updater = telegram.ext.Updater(Token, use_context=True)
dispatcher=updater.dispatcher

def start(update,context):
    update.message.reply_text("hi welcome to songrahi")
def help(update,context):
    update.message.reply_text(
    """
    /start-> welcome to my bot
    /help-> this is help
    /content-> youtube link/ insta mp3
    """
    )
def content(update,context):
    update.message.reply_text("get ready to download")

dispatcher.add_handler(telegram.ext.CommandHandler("start",start))
dispatcher.add_handler(telegram.ext.CommandHandler("help",help))
dispatcher.add_handler(telegram.ext.CommandHandler("content",content))
updater.start_polling()
updater.idle()
