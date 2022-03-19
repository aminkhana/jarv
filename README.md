# jarv
import os
from bs4 import BeautifulSoup

import pyttsx3
import speech_recognition as sr
import webbrowser
import pywhatkit
import wikipedia
import os
import pyautogui
import flask
import keyboard
import datetime
from playsound import playsound
import pyjokes
from PyDictionary import PyDictionary as Diction
import requests
from bs4 import BeautifulSoup
import whatsapp
import ctypes
from pynput.keyboard import Key, Controller




Assistant = pyttsx3.init('sapi5')
voices = Assistant.getProperty('voices')
Assistant.getProperty('voices')
Assistant.setProperty('rate',195)


def speak(audio):
    print("   ")
    Assistant.say(audio)
    print(f": {audio}")
    print("   ")
    Assistant.runAndWait()


def getcommand():
    command = sr.Recognizer()
    with sr.Microphone() as source:
        print("Listening...")
        command.pause_threshold = 0.5
        audio = command.listen(source)

        try:
            print("Recognizing...")
            query = command.recognize_google(audio)
            print(f"You Said : {query}")

        except Exception as Error:
            return  "none"

        return query.lower()

query = getcommand()

if 'hello' in query:
    speak("hello sir")

else:
    speak("can you say that again, sir")

def Taskexec():

    speak("hello, i am jarvis")
    speak("here to help you")





    def Music():
        speak("tell me the song")
        musicName = getcommand()

        if 'Buster boy' in musicName:
            os.startfile('F:\\Bast boi.mp3')

        elif 'Jumme Ki Raat' in musicName:
            os.startfile('E:\\Songs\\Jumme Ki Raat.mp3')

        else:
            pywhatkit.playonyt(musicName)

        speak("your song is now playing,Enjoy")

    def OpenApps():
        speak("ok sir,wait a sec")

        if 'counter strike' in query:
            os.startfile("C:\\Program Files (x86)\\C:\Program Files (x86)\\Steam\\steam.exe")

        elif 'pubg' in query:
            os.startfile("C:\\Program Files (x86)\\C:\Program Files (x86)\\Steam\\steam.exe")

        elif 'adobe' in query:
            os.startfile("C:\\Program Files\\Adobe\\Adobe Premiere Pro 2022\\Adobe Premiere Pro.exe")

        elif 'edge' in query:
            os.startfile("C:\\rogram Files (x86)\\Microsoft\\Edge\\Application\\msedge.exe")

        elif 'facebook' in query:
            webbrowser.open('https://www.facebook.com')

        elif 'instagram' in query:
            webbrowser.open('https://www.instagram.com')

        elif 'youtube' in query:
            webbrowser.open('https://www.youtube.com')

        elif 'opera' in query:
            webbrowser.open('C:\\Users\\amin\\AppData\\Local\\Programs\\Opera GX\\launcher.exe')

    def CloseApps():
        speak("ok sir,wait a moment")

        if 'youtube' in query:
            os.system("TASKKILL /f /im msedge.exe")

        elif 'pubg' in query:
            os.system("TASKKILL /f/ im TslGame.exe")

        elif 'counter strike' in query:
            os.system("TASKKILL /f /im csgo.exe")

        elif 'adobe' in query:
            os.system("TASKKILL /f /im Adobe Premiere Pro.exe")

        elif 'edge' in query:
            os.system("TASKKILL /f /im msedge.exe")

        elif 'instagram' in query:
            os.system("TASKKILL /f /im msedge.exe")

        elif 'facebook' in query:
            os.system("TASKKILL /f /im msedge.exe")

        elif 'h' in query:
            os.system("TASKKILL /f /im msedge.exe")

        elif 'opera' in query:
            os.system("TASKKILL /f /im launcher.exe")

    def Dict():
        speak("activated dictionary")
        speak("tell me the problem")
        probl = getcommand()

        if 'meaning' in probl:
            probl = probl.replace("what is","")
            probl = probl.replace("jarvis","")
            probl = probl.replace("of","")
            result = Diction.meaning(probl)
            speak(f"the meaning of {probl} is {result}")

        elif 'synonym' in probl:
            probl = probl.replace("what is")
            probl = probl.replace("jarvis")
            probl = probl.replace("of")
            result = Diction.synonym(probl)
            speak(f"the synonym of {probl} is {result}")


        elif 'antonym' in probl:
            probl = probl.replace("what is")
            probl = probl.replace("jarvis")
            probl = probl.replace("of")
            result = Diction.antonym(probl)
            speak(f"the antonym of {probl} is {result}")

        speak("dictionary closed")

    def screenshot():
        speak("ok boss,what should i name that file")
        path = getcommand()
        path1name = path + ".png"
        path1 = 'G:\\bd' + path1name
        kk = pyautogui.screenshot()
        kk.save(path1)
        os.startfile("G:\\bd")
        speak("here is your screenshot")



    def windowstls():
        speak("what do you want done sir")
        comm = getcommand()

        if 'task' in comm:
            pyautogui.hotkey('winleft', 'r')



        elif 'desktop' in comm:
            pyautogui.hotkey('winleft', 'd')


        elif 'change tab' in comm:
            pyautogui.hotkey('alt', 'tab')


        elif 'close window' in comm:
            pyautogui.hotkey('alt', 'f4')


        elif 'copy' in comm:
            pyautogui.hotkey('ctrl', 'c')

        elif 'paste' in comm:
            pyautogui.hotkey('ctrl', 'v')

        elif 'cut' in comm:
            pyautogui.hotkey('ctrl', 'x')

        elif 'delete' in comm:
            pyautogui.press('delete')

        elif 'go back' in comm:
            kb = Controller()
            kb.press(Key.backspace)
            kb.release(Key.backspace)





    def Temp():
        search = "temperature in peshawar"
        url = f"https://www.google.com/search?q={search}"
        r = requests.get(url)
        data = BeautifulSoup(r.text,"html.parser")
        temperature = node = data.find('div',class_ = "BNeawe")
        if node is not None:
            temperature = node.text
        else:
            temperature = None
        speak(f"the temperature outside is {temperature}")

    def YoutubeAuto():
        speak("whats your command")
        comm = getcommand()

        if 'pause' in comm:
            keyboard.press('space bar')

        elif 'restart' in comm:
            keyboard.press('0')

        elif 'mute' in comm:
            keyboard.press('m')

        elif 'skip' in comm:
            keyboard.press('1')

        elif 'back' in comm:
            keyboard.press('j')

        elif 'full screen' in comm:
            keyboard.press('f')

        elif 'film mode' in comm:
            keyboard.press('t')

        elif 'leave full screen' in comm:
            keyboard.press('esc')

        speak("done sir")


    while True:

        query = getcommand()

        if 'hello' in query:
            speak("I am Jarvis")
            speak("your personal A I!")
            speak("how can i help")

        elif 'whats up ' in query:
            speak("nothing much sir")
            speak("how may i help")

        elif 'how is the day' in query:
            speak("its splendid out today sir")

        elif 'where do you live' in query:
            speak("i am a program sir i don't have a form")

        elif 'good night' in query:
            speak("good night to you too")
            break


        elif 'see you soon' in query:
            speak("so long")
            break




        elif 'thank you' in query:
            speak("most welcome")

        elif 'how are you' in query:
            speak("i am at my best today")
            speak("what about you")

        elif 'i am doing fine' in query:
            speak('lovely to hear it sir')

        elif 'you need a break' in query:
            speak("fine sir, i will be right here")
            break

        elif 'night night' in query:
            speak("goodbye sir")
            break

        elif 'bye' in query:
            speak("bye bye sir")
            break

        elif 'search youtube' in query:
            speak("searching sir")
            query = query.replace("youtube search","")
            web = 'https://www.youtube.com/results?search_query=' + query
            webbrowser.open(web)
            speak("done sir")

        elif 'search' in query:
            speak("i found this on the web")
            query = query.replace("google search","")
            pywhatkit.search(query)
            speak("done sir")

        elif 'website' in query:
            speak("ok sir, Launching...")
            query = query.replace("jarvis","")
            query = query.replace("website","")
            query = query.replace(" ","")
            web1 = query.replace("open","")
            web2 = 'https://www.' +web1 + '.com'
            webbrowser.open(web2)
            speak("launched")

        elif 'launch' in query:
            speak("tell me the name of website")
            name = getcommand()
            web = 'https://www.' + name + '.com'
            webbrowser.open(web)
            speak("done sir")

        elif 'music' in query:
            Music()








        elif 'wikipedia' in query:
            speak("searching on wiki...")
            query = query.replace("jarvis","")
            query = query.replace("wikipedia","")
            wiki = wikipedia.summary(query,2)
            speak(f"According to wikipedia : {wiki}")

        elif 'whatsapp' in query:
           whatsapp()

        elif 'screenshot' in query:
            screenshot()

        elif 'open opera' in query:
            OpenApps()

        elif 'open counter strike' in query:
            OpenApps()

        elif 'open pubg' in query:
            OpenApps()

        elif 'open facebook' in query:
            OpenApps()

        elif 'open youtube' in query:
            OpenApps()

        elif 'open instagram' in query:
            OpenApps()

        elif 'open opera' in query:
            OpenApps()

        elif 'open adobe' in query:
            OpenApps()

        elif 'close h' in query:
            CloseApps()

        elif 'close opera' in query:
            CloseApps()

        elif 'close instagram' in query:
            CloseApps()

        elif 'close pubg' in query:
            CloseApps()

        elif 'close facebook' in query:
            CloseApps()

        elif 'close adobe' in query:
            CloseApps()

        elif 'close youtube' in query:
            CloseApps()

        elif 'close counter strike' in query:
            CloseApps()

        elif 'close' in query:
            CloseApps()

        if 'task' in query:
            pyautogui.hotkey('winleft', 'r')
            pyautogui.release('winleft', 'r')

        elif 'copy' in query:
            pyautogui.hotkey('ctrl', 'c')
            speak("file copied")

        elif 'paste' in query:
            pyautogui.hotkey('ctrl', 'v')
            speak("file pasted")

        elif 'cut' in query:
            pyautogui.hotkey('ctrl', 'x')
            speak("file cut")

        elif 'delete' in query:
            pyautogui.press('delete')
            speak("file deleted")

        elif 'go back' in query:
            kb = Controller()
            kb.press(Key.backspace)
            kb.keyUp(Key.backspace)


        elif 'desktop' in query:
            pyautogui.hotkey('winleft', 'd')


        elif 'change tab' in query:
            pyautogui.hotkey('alt', 'tab')


        elif 'close window' in query:
            pyautogui.hotkey('alt', 'f4')
            

        elif 'pause' in query:
            keyboard.press('space bar')

        elif 'restart' in query:
            keyboard.press('0')

        elif 'mute' in query:
            keyboard.press('m')

        elif 'skip' in query:
            keyboard.press('1')

        elif 'back' in query:
            keyboard.press('j')

        elif 'full screen' in query:
            keyboard.press('f')

        elif 'film mode' in query:
            keyboard.press('t')

        elif 'leave full screen' in query:
            keyboard.press('esc')

        elif 'youtube tools' in query:
            YoutubeAuto()

        elif 'joke' in query:
            get = pyjokes.get_jokes()
            speak(get)

        elif 'my location' in query:
            speak("")
            webbrowser.open('https://www.google.com/maps/place/Street+1,+J-4+Phase+2+Hayatabad,+Peshawar,+Khyber+Pakhtunkhwa,+Pakistan/@33.9745933,71.4477556,17z/data=!3m1!4b1!4m5!3m4!1s0x38d91096c2566d2f:0xdbef63f9942cd6bd!8m2!3d33.9745907!4d71.4490602')

        elif 'dictionary' in query:
            Dict()

        elif 'alarm' in query:
            speak("enter the time")
            time = input(": Enter the time :")

            while True:
                Time_Ac = datetime.datetime.now()
                now = Time_Ac.strftime("%H:%M:%S")

                if now == time:
                    speak("time to wake up sir")
                    speak("alarm ended")

                elif now>time:
                    break

        elif 'whatsapp' in query:
            whatsapp()

        elif 'temperature' in query:
            Temp()

        elif 'windows tools' in query:
            windowstls()

Taskexec()
