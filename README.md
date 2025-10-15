import telebot
import os

TOKEN = os.environ.get("BOT_TOKEN")
bot = telebot.TeleBot(TOKEN)

@bot.message_handler(commands=['start'])
def start_message(message):
    bot.reply_to(message, "👋 Hello! I'm your AI video assistant bot.")

@bot.message_handler(content_types=['video'])
def handle_video(message):
    bot.reply_to(message, "🎥 Thanks! I'll analyze this video soon.")

print("Bot is running...")
bot.infinity_polling()
