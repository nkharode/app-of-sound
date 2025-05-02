# app-of-sound
media player
from tkinter import *
from pygame import mixer
from tkinter import filedialog
a   = Tk()
a.config(bg = 'white')
l = Label(a, text = 'Media player').pack()
mixer.init()
def sound_chosing_funtion():
         c = filedialog.askopenfilename()
         mixer.init()
         mixer.music.load(f'{c}')
         mixer.music.play()
         Button(a,text = c , command = play).pack()
def pause():
         mixer.music.pause()
def play():
         mixer.music.play()
def volume(x):
         i = int (x) / 100
         mixer.music.set_volume(i)

Button(a,text = 'select and play ',command = sound_chosing_funtion,width = 20,bg = 'gold').pack()
Button(a,text = ' | | ',command = pause, width = 20,bg = 'blue',fg = 'black').pack()
Button(a,text = ' > ',command = play,width = 20).pack()
t = Scale(a ,  from_ =0 , to = 100,width = 10,orient = 'horizontal', command = volume,bg = 'white',fg = 'blue')
t.set(50)
t.pack()
