from telegram.ext import Application, CommandHandler, MessageHandler, filters

# 🔴 YAHAN APNA BOTFATHER TOKEN PASTE KARO
TOKEN = 8534348602:AAF2V-Q3fjQergpWmfOqzgvP4uLWBkFOFNI

async def start(update, context):
    await update.message.reply_text(
        "Assalam o Alaikum 👋\n\n"
        "🤖 Crypto Ustad Bot\n"
        "📊 Free crypto signals & market updates\n\n"
        "Commands:\n"
        "btc  → BTC update\n"
        "eth  → ETH update\n"
        "signal → Aaj ka signal\n\n"
        "⚠️ Not financial advice"
    )

async def handle_message(update, context):
    text = update.message.text.lower()

    if text == "btc":
        await update.message.reply_text(
            "📈 BTC Update:\n"
            "Market sideways hai\n"
            "Resistance strong hai\n"
            "Entry apni research se lo\n\n"
            "⚠️ Not financial advice"
        )

    elif text == "eth":
        await update.message.reply_text(
            "📊 ETH Update:\n"
            "Trend stable lag raha hai\n"
            "High risk avoid karo\n\n"
            "⚠️ Not financial advice"
        )

    elif text == "signal":
        await update.message.reply_text(
            "🔥 Aaj ka Signal:\n"
            "Market observe karo\n"
            "Clear setup ka wait karo\n\n"
            "⚠️ Not financial advice"
        )

    else:
        await update.message.reply_text(
            "BTC / ETH / SIGNAL likho"
        )

def main():
    app = Application.builder().token(TOKEN).build()

    app.add_handler(CommandHandler("start", start))
    app.add_handler(MessageHandler(filters.TEXT & ~filters.COMMAND, handle_message))

    print("✅ Bot LIVE ho chuka hai...")
    app.run_polling()

if __name__ == "__main__":
    main()
