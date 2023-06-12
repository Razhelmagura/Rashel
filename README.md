
import telegram

# Set API token and chat ID
API_TOKEN = '6285771452:AAFP5509OtxUf3s4-n5xGoX0xWw7ahi5aiI'
CHAT_ID = 'your_chat_id_here'

# Create bot object
bot = telegram.Bot(token=6285771452:AAFP5509OtxUf3s4-n5xGoX0xWw7ahi5aiI)

# Send welcome message on /start command
def start(update, context):
    context.bot.send_message(chat_id=update.effective_chat.id, text="Welcome to MyTestBot!")

# Register handler for /start command
from telegram.ext import CommandHandler
start_handler = CommandHandler('start', start)
dispatcher.add_handler(start_handler)

# Forward any message to chat ID
def forward_message(update, context):
    message = update.message
    bot.forward_message(chat_id=1579419568, from_chat_id=message.chat_id, message_id=message.message_id)

# Register handler for any message
from telegram.ext import MessageHandler, Filters
message_handler = MessageHandler(Filters.all, forward_message)
dispatcher.add_handler(message_handler)

# Start polling for updates
updater.start_polling()
