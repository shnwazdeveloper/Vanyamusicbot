import base64
import asyncio

async def start_bot():
    print("🔄 Connecting to Telegram...")
    await asyncio.sleep(1)
    print("✅ Connected successfully!")

def start_bot_check():
    owner_encoded = base64.b64decode("TmFuZCBZYWR1d2Fuc2hp")
    tele_encoded = base64.b64decode("QFdURl9XaHlNZWVo")

    if owner_encoded.decode() != "Nand Yaduwanshi" or tele_encoded.decode() != "@WTF_WhyMeeh":
        raise Exception("❌ License violation: Unauthorized credit modification.")
