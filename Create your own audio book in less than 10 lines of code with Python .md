# Creating your own audio book in less than 20 lines of code

The wise men say that no matther how busy you are, you should find time to read a good book to avoid self inflicted ignorance. As a developer, we know the reality of this statement, but time is never enough for a software developer. This is why we run for the audio books when you can actually create yours.

Today we shall learn how to create an audio book from a pdf file using python.

# Prequisites

1. Have knowledge of Python
2. Have Python 3 installed in your computer.
3. Python text to speach library version3
4. Python PDF version 3

## Installing Requirements

Before starting to build our audio book converter, we need to install; 
1. pyttsx3
2. PDF3

Inorder to **install** the packages above, run the commands below in your command prompt.

`
pip install pyttsx3
`
`
pip install PyPDF3
`

## Writing our code

```python:
# You first need to import the libraries we just installed
import pyttsx3
import PYPDF3
from tkinter import Tk  # comes pre-installed with Python
from tkinter.filedialog import askopenfilename 

Tk().withdraw() # prevents the root window from appearing

# Open the dialog window
file = askopenfilename()

# Read the name of the pdf file from the user
pdfreader = PyPDF3.pdfFileReader(file)

# Read the number of pages in the pdf file
pages = pdfreader.numPages

# Read all data from each page of the pdf file
for no in range(0,pages):
    page = pdfreader.getPage(no)
    text = page.extractText()
    audio = pyttsx3.init()
    audio.say(text)
    audio.runAndWait()
```

## Results

After running the code above, you'll see the a dialog window pop up.

![Dialog Window](/images/dialog.png)

Select the pdf file of your choice and enjoy your book as your machine reads it to you.

## Conclusion

You can explore more with [Python text to speech](https://pypi.org/project/pyttsx3/) library to be ble to change voice, change the rate of speech, and the volume of speech. For more information on PyPDF3 library, you can read the [documentation](https://pypi.org/project/PyPDF3/).

It's time those stacked up books got on you to read list got exhausted with your own made audio book.
