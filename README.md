mport telebot
import datetime
bot = telebot.TeleBot("7706266117:AAEBzQ2LTVn-gNbLOMKV6S0TWGr9ZoVAeqE")

# قاموس لتخزين بيانات المستخدم
user_data = {}

# أمر البداية
@bot.message_handler(commands=['start', 'beginwar'])
def send_welcome(message):
    user_id = message.chat.id
    user_data[user_id] = {"started": str(datetime.date.today())}
    bot.send_message(user_id, "أين تريد أن تصل؟ وهل تملك الشجاعة لتدفع الثمن؟\n\nابدأ يومك الآن بـ /daily")

# أمر يومي
@bot.message_handler(commands=['daily'])
def daily_routine(message):
    user_id = message.chat.id

    response = (
        "𝐈𝐍𝐍𝐄𝐑_𝐖𝐀𝐑 - تقرير اليوم:\n\n"
        "⚔ تمرين جسدي: 30 ضغطة + 30 سكوات\n"
        "🧠 مهمة عقل: شاهد فيديو عن الفلسفة الحديثة أو اقرأ 5 صفحات من كتاب\n"
        "☠️ قصف اليوم: لا أحد سينقذك إن لم تقم.\n"
        "✅ تقييم: بعد التنفيذ، أرسل /confess للاعتراف أو التحليل."
    )
    bot.send_message(user_id, response)

# أمر اعتراف
@bot.message_handler(commands=['confess'])
def confess(message):
    bot.send_message(message.chat.id, "اعترف... هل نفذت كل شيء؟")

# تشغيل البوت
print("✅ البوت يعمل الآن... استعد للجلد.")
bot.infinity_polling()
import telebot
import random

# ضع التوكن الخاص بك هنا
bot = telebot.TeleBot("7706266117:AAEBzQ2LTVn-gNbLOMKV6S0TWGr9ZoVAeqE")

# /start
@bot.message_handler(commands=['start'])
def start_message(message):
    bot.reply_to(message, "أين تريد أن تصل؟ وهل تملك الشجاعة لتدفع الثمن؟\n\nابدأ يومك الآن بـ /daily")

# /daily
@bot.message_handler(commands=['daily'])
def daily_message(message):
    quotes = [
        "لا أحد سيُنقذك... احفر طريقك بنفسك.",
        "العالم لا يرحم الضعفاء، لا تكن واحدًا منهم.",
        "توقف عن الأعذار... وابدأ التنفيذ.",
        "كل ثانية ضعف = فرصة لعدوك.",
        "الراحة؟ للجبناء فقط.",
    ]
    bot.reply_to(message, random.choice(quotes))

# /discipline
@bot.message_handler(commands=['discipline'])
def send_discipline(message):
    lines = [
        "أنت تعرف ما يجب أن تفعله، لكنك تفضل الراحة. عار.",
        "توقف عن الشكوى وابدأ العمل.",
        "الانضباط ليس شعورًا، إنه سلاحك.",
    ]
    bot.reply_to(message, random.choice(lines))

# /slap
@bot.message_handler(commands=['slap'])
def slap_user(message):
    bot.reply_to(message, "صفعة من الواقع: لا أحد يهتم إن كنت متعبًا. استمر.")

# /warrior
@bot.message_handler(commands=['warrior'])
def warrior_mode(message):
    bot.reply_to(message, "كل يوم تأخر فيه، عدوك يتقدم خطوة. استعد. تحرك. قاتل.")

# تشغيل البوت
print("البوت يعمل الآن... استعد للجلد.")
bot.infinity_polling()

pyTelegramBotAPI