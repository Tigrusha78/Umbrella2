import logging 
from telegram import Update 
from telegram.ext import Updater, MessageHandler, Filters, CallbackContext 

class TelegramBot: 
    def init(self, token: 7683094231:AAFlnoCepog9JRnfX2Kw_KqGDZbJTBbjifc str, group_chat_id:https://t.me/+ZSdN6ueB8MA3ZmUy int): 
        self.token = token 
        self.group_chat_id = group_chat_id 
        self.updater = Updater(token=self.token, use_context=True) 
        self.dispatcher = self.updater.dispatcher 

        logging.basicConfig( 
            format='%(asctime)s - %(name)s - %(levelname)s - %(message)s', 
            level=logging.INFO 
        ) 

        self.dispatcher.add_handler( 
            MessageHandler(Filters.text & ~Filters.command, self.handle_message) 
        ) 

    def handle_message(self, update: Update, context: CallbackContext) -> None: 
        context.bot.send_message( 
            chat_id=self.group_chat_id, 
            text=update.message.text 
        ) 

    def run(self) -> None: 
        self.updater.start_polling() 
        self.updater.idle() 

if name == 'Bot For Post': 
    TOKEN = '7683094231:AAFlnoCepog9JRnfX2Kw_KqGDZbJTBbjifc' 
    GROUP_CHAT_ID = -https://t.me/+ZSdN6ueB8MA3ZmUy  # 
    bot = TelegramBot(7683094231:AAFlnoCepog9JRnfX2Kw_KqGDZbJTBbjifc) 
    bot.run()
