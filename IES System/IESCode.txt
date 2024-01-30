#IES Code System
# import required modules
import PCF8591 as ADC#Raspberry pi 3 sheild (all compotents connected to this shield )
import RPi.GPIO as GPIO#define the raspberry pins
import time#for sleep function 
import LCD1602#for lcd scren 
from time import sleep
from playsound import playsound
import telepot
from telepot.loop import MessageLoop
from pydub import AudioSegment
from pydub.playback import play
##################################################################
bot = telepot.Bot('5267763826:AAEM4WYGrs-wJmYoM7VTfNs7DtruziGnIug')#IES Telegram Bot(TELEBOT)
GPIO.setmode(GPIO.BCM)
#Initial Vlaue for sensors
gasSensor = 0
mq9 = 0
channel = 21
GPIO.setup(channel, GPIO.IN)
flame = 0
# Here the output pin to which the LEDs are connected.
LED_Rot = 25
LED_Gruen = 24
LED_Blau = 23
# To Set pins to output mode
GPIO.setup(LED_Rot, GPIO.OUT)
GPIO.setup(LED_Gruen, GPIO.OUT)
GPIO.setup(LED_Blau, GPIO.OUT)
Freq = 100  # Hz
# The respective colors are initialized.
ROT = GPIO.PWM(LED_Rot, Freq)
GRUEN = GPIO.PWM(LED_Gruen, Freq)
BLAU = GPIO.PWM(LED_Blau, Freq)
ROT.start(0)
GRUEN.start(0)
BLAU.start(0)
chat_id2 = '1334909526'
chat_id3 = '1337613901'
def LED_Farbe(Rot, Gruen, Blau, pause):
    ROT.ChangeDutyCycle(Rot)
    GRUEN.ChangeDutyCycle(Gruen)
    BLAU.ChangeDutyCycle(Blau)
    time.sleep(pause)
    ROT.ChangeDutyCycle(0)
    GRUEN.ChangeDutyCycle(0)
def setup():
    ADC.setup(0x48)
    LCD1602.init(0x27, 1)  # init(slave address, background light)
    time.sleep(0.5)
def loop():
    while True:
        gasSensor = ADC.read(0)
        mq9 = ADC.read(1)
        print(str(gasSensor) + "--" + str(mq9))
        time.sleep(0.1)
        channel_is_on = GPIO.input(channel)  # Returns 0 if OFF or 1 if ON
        if channel_is_on or gasSensor >= 120 or mq9 >= 120:
            flame = 1


            # Send Message to IES Telebot
            bot.sendMessage(chat_id3, "Attention ...Attention ...IES Activated")
            bot.sendMessage(chat_id3, "إنتباه ... إنتباه ...تم تفعيل نظام الإخلاء الذكي")

            LED_Farbe(0, 100, 0, 0.20)
            # LCD1602.clear()
            # sleep(2)
            #    print("fire system detected")
            LCD1602.write(0, 0, " IES Activated ")
            LED_Farbe(0, 100, 0, 0.20)
            sleep(0.5)
            LED_Farbe(0, 100, 0, 0.20)
            sleep(0.5)
            LED_Farbe(0, 100, 0, 0.20)
            LED_Farbe(0, 100, 0, 0.20)
            sleep(0.5)
            LED_Farbe(0, 100, 0, 0.20)
            sleep(0.5)
            LED_Farbe(0, 100, 0, 0.20)
            LCD1602.write(0, 1, "   System On ")
            LED_Farbe(0, 100, 0, 0.20)
            # for playing wav file
            song = AudioSegment.from_wav("audio.wav")
            #   Sound Alarm Detiction
            play(song)
            # playsound ('audio.wav')
            LED_Farbe(0, 100, 0, 0.40)
            sleep(0.5)
            LCD1602.clear()
            LED_Farbe(100, 0, 0, 0.20)
            sleep(0.5)
            LED_Farbe(100, 0, 0, 0.20)
            LCD1602.write(0, 0, "Telegram Active")
            LED_Farbe(100, 0, 0, 0.20)
            sleep(0.5)
            LED_Farbe(100, 0, 0, 0.20)
            sleep(0.5)
            sleep(0.5)
            # send Message to IES Telebort
            bot.sendMessage(chat_id3, "IES Detect 3 Person Inside Room # 201")
            bot.sendMessage(chat_id3, "تم رصد ٣ أشخاص داخل غرفة رقم :٢٠١")
            LCD1602.write(0, 1, " Telegram Sent")
            LED_Farbe(100, 0, 0, 0.20)
            sleep(1)
            LED_Farbe(100, 0, 0, 0.20)
            sleep(1)

            LED_Farbe(100, 0, 0, 0.20)
            sleep(1)
            LCD1602.clear()
            sleep(1)
        else:

            LED_Farbe(0, 0, 100, 0.20)
            flame = 0
            sleep(0.5)
            LCD1602.write(0, 0, "   IES Stable")
            sleep(0.5)
            LCD1602.write(0, 1, "   System OFF")
            sleep(0.5)
            LCD1602.clear()

def destroy():
    ADC.write(0)
if __name__ == "__main__":
    try:
        setup()
        loop()
    except KeyboardInterrupt:
        destroy()