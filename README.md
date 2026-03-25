# bot-guerra
Bot VIP Premium: control total para tus grupos con administración, seguridad avanzada, juegos, descargas y diversión. Estable, rápido y moderno, con funciones premium y soporte directo. Ideal para mantener tus comunidades seguras y entretenidas.
import random
import time

# =========================
# CONFIGURACIÓN BOT
# =========================

BOT_NAME = "BOT VIP"
OWNER = "Kevin"

estado_bot = True
modo_admin = False

# =========================
# FUNCIONES PRINCIPALES
# =========================

def generar_sala(modo):
    codigo = random.randint(100000, 999999)
    passwords = ["1234", "vip66", "pro99", "free26"]
    clave = random.choice(passwords)

    return f"""
⚔️ Sala {modo} creada
🆔 ID: {codigo}
🔑 Pass: {clave}
"""

def menu():
    return f"""
🪙 MULTI MENU - {BOT_NAME}

🎮 FREE FIRE
.4vs4
.6vs6
.12vs12
.16vs16
.20vs20
.24vs24

🏘️ GRUPO
.link
.kick
.mute
.unmute
.todos
.ping

⬇️ DESCARGAS
.play
.spotify

⚙️ BOT
.on
.off
.modoadmin

🎭 DIVERSIÓN
.chistes
.consejo
.love
.meme

🎨 STICKERS
.s
.qc
.hd
"""

def chiste():
    lista = [
        "😂 ¿Por qué el programador confunde Halloween y Navidad? Porque OCT 31 = DEC 25",
        "😂 Un bug al día mantiene al programador sin dormir",
        "😂 Python no muerde, pero sí exige indentación"
    ]
    return random.choice(lista)

def consejo():
    lista = [
        "💡 Nunca dejes de aprender.",
        "💡 Si algo falla, revisa la lógica primero.",
        "💡 Automatizar te ahorra tiempo."
    ]
    return random.choice(lista)

def love():
    porcentaje = random.randint(1, 100)
    return f"❤️ Compatibilidad: {porcentaje}%"

def meme():
    memes = [
        "🎭 Cuando compila a la primera: milagro.",
        "🎭 Yo arreglando un bug y dañando tres cosas más."
    ]
    return random.choice(memes)

# =========================
# MOTOR BOT
# =========================

def responder(cmd):
    global estado_bot
    global modo_admin

    if not estado_bot and cmd != ".on":
        return "🔴 Bot apagado"

    if cmd == ".menu":
        return menu()

    elif cmd == ".ping":
        return "🏓 Pong!"

    elif cmd == ".4vs4":
        return generar_sala("4vs4")

    elif cmd == ".6vs6":
        return generar_sala("6vs6")

    elif cmd == ".12vs12":
        return generar_sala("12vs12")

    elif cmd == ".16vs16":
        return generar_sala("16vs16")

    elif cmd == ".20vs20":
        return generar_sala("20vs20")

    elif cmd == ".24vs24":
        return generar_sala("24vs24")

    elif cmd == ".link":
        return "🔗 Link grupo: https://chat.whatsapp.com/ejemplo"

    elif cmd == ".kick":
        return "👢 Usuario expulsado"

    elif cmd == ".mute":
        return "🔇 Grupo silenciado"

    elif cmd == ".unmute":
        return "🔊 Grupo activado"

    elif cmd == ".todos":
        return "📢 Mencionando a todos"

    elif cmd == ".play":
        return "🎶 Buscando canción..."

    elif cmd == ".spotify":
        return "🎵 Descargando desde Spotify..."

    elif cmd == ".on":
        estado_bot = True
        return "🟢 Bot encendido"

    elif cmd == ".off":
        estado_bot = False
        return "🔴 Bot apagado"

    elif cmd == ".modoadmin":
        modo_admin = not modo_admin
        return f"⚙️ modo admin: {modo_admin}"

    elif cmd == ".chistes":
        return chiste()

    elif cmd == ".consejo":
        return consejo()

    elif cmd == ".love":
        return love()

    elif cmd == ".meme":
        return meme()

    elif cmd == ".s":
        return "🎨 Sticker creado"

    elif cmd == ".qc":
        return "💬 Sticker texto generado"

    elif cmd == ".hd":
        return "🖼️ Imagen mejorada"

    else:
        return "❌ comando no existe"

# =========================
# SIMULADOR BOT
# =========================

print(f"{BOT_NAME} iniciado 🚀")

while True:
    entrada = input("Comando: ")
    print(responder(entrada))