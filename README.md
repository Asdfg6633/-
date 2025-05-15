import tkinter as tk
from tkinter import filedialog, Listbox
import pygame
import os

# شروع pygame
pygame.init()
pygame.mixer.init()

class MusicPlayer:
    def __init__(self, root):
        self.root = root
        self.root.title("پخش‌کننده موسیقی")
        self.root.geometry("400x400")

        self.playlist = []
        self.current_index = -1
        self.is_paused = False

        # لیست آهنگ‌ها
        self.listbox = Listbox(self.root, width=50)
        self.listbox.pack(pady=20)

        # دکمه‌ها
        tk.Button(self.root, text="افزودن آهنگ", command=self.add_song).pack()
        tk.Button(self.root, text="پخش", command=self.play_song).pack(pady=5)
        tk.Button(self.root, text="مکث", command=self.pause_song).pack()
        tk.Button(self.root, text="ادامه", command=self.resume_song).pack()
        tk.Button(self.root, text="توقف", command=self.stop_song).pack(pady=5)

        # برچسب نمایش نام آهنگ
        self.song_label = tk.Label(self.root, text="", fg="blue")
        self.song_label.pack()

    def add_song(self):
        files = filedialog.askopenfilenames(filetypes=[("MP3 Files", "*.mp3")])
        for file in files:
            self.playlist.append(file)
            self.listbox.insert(tk.END, os.path.basename(file))

    def play_song(self):
        try:
            selected = self.listbox.curselection()
            if not selected:
                return
            self.current_index = selected[0]
            pygame.mixer.music.load(self.playlist[self.current_index])
            pygame.mixer.music.play()
            self.song_label.config(text="در حال پخش: " + os.path.basename(self.playlist[self.current_index]))
        except:
            pass

    def pause_song(self):
        if pygame.mixer.music.get_busy():
            pygame.mixer.music.pause()
            self.is_paused = True

    def resume_song(self):
        if self.is_paused:
            pygame.mixer.music.unpause()
            self.is_paused = False

    def stop_song(self):
        pygame.mixer.music.stop()
        self.song_label.config(text="")

# اجرای برنامه
root = tk.Tk()
app = MusicPlayer(root)
root.mainloop()import tkinter as tk
from tkinter import filedialog, Listbox
import pygame
import os

# شروع pygame
pygame.init()
pygame.mixer.init()

class MusicPlayer:
    def __init__(self, root):
        self.root = root
        self.root.title("پخش‌کننده موسیقی")
        self.root.geometry("400x400")

        self.playlist = []
        self.current_index = -1
        self.is_paused = False

        # لیست آهنگ‌ها
        self.listbox = Listbox(self.root, width=50)
        self.listbox.pack(pady=20)

        # دکمه‌ها
        tk.Button(self.root, text="افزودن آهنگ", command=self.add_song).pack()
        tk.Button(self.root, text="پخش", command=self.play_song).pack(pady=5)
        tk.Button(self.root, text="مکث", command=self.pause_song).pack()
        tk.Button(self.root, text="ادامه", command=self.resume_song).pack()
        tk.Button(self.root, text="توقف", command=self.stop_song).pack(pady=5)

        # برچسب نمایش نام آهنگ
        self.song_label = tk.Label(self.root, text="", fg="blue")
        self.song_label.pack()

    def add_song(self):
        files = filedialog.askopenfilenames(filetypes=[("MP3 Files", "*.mp3")])
        for file in files:
            self.playlist.append(file)
            self.listbox.insert(tk.END, os.path.basename(file))

    def play_song(self):
        try:
            selected = self.listbox.curselection()
            if not selected:
                return
            self.current_index = selected[0]
            pygame.mixer.music.load(self.playlist[self.current_index])
            pygame.mixer.music.play()
            self.song_label.config(text="در حال پخش: " + os.path.basename(self.playlist[self.current_index]))
        except:
            pass

    def pause_song(self):
        if pygame.mixer.music.get_busy():
            pygame.mixer.music.pause()
            self.is_paused = True

    def resume_song(self):
        if self.is_paused:
            pygame.mixer.music.unpause()
            self.is_paused = False

    def stop_song(self):
        pygame.mixer.music.stop()
        self.song_label.config(text="")

# اجرای برنامه
root = tk.Tk()
app = MusicPlayer(root)
root.mainloop()import tkinter as tk
from tkinter import filedialog, Listbox
import pygame
import os

# شروع pygame
pygame.init()
pygame.mixer.init()

class MusicPlayer:
    def __init__(self, root):
        self.root = root
        self.root.title("پخش‌کننده موسیقی")
        self.root.geometry("400x400")

        self.playlist = []
        self.current_index = -1
        self.is_paused = False

        # لیست آهنگ‌ها
        self.listbox = Listbox(self.root, width=50)
        self.listbox.pack(pady=20)

        # دکمه‌ها
        tk.Button(self.root, text="افزودن آهنگ", command=self.add_song).pack()
        tk.Button(self.root, text="پخش", command=self.play_song).pack(pady=5)
        tk.Button(self.root, text="مکث", command=self.pause_song).pack()
        tk.Button(self.root, text="ادامه", command=self.resume_song).pack()
        tk.Button(self.root, text="توقف", command=self.stop_song).pack(pady=5)

        # برچسب نمایش نام آهنگ
        self.song_label = tk.Label(self.root, text="", fg="blue")
        self.song_label.pack()

    def add_song(self):
        files = filedialog.askopenfilenames(filetypes=[("MP3 Files", "*.mp3")])
        for file in files:
            self.playlist.append(file)
            self.listbox.insert(tk.END, os.path.basename(file))

    def play_song(self):
        try:
            selected = self.listbox.curselection()
            if not selected:
                return
            self.current_index = selected[0]
            pygame.mixer.music.load(self.playlist[self.current_index])
            pygame.mixer.music.play()
            self.song_label.config(text="در حال پخش: " + os.path.basename(self.playlist[self.current_index]))
        except:
            pass

    def pause_song(self):
        if pygame.mixer.music.get_busy():
            pygame.mixer.music.pause()
            self.is_paused = True

    def resume_song(self):
        if self.is_paused:
            pygame.mixer.music.unpause()
            self.is_paused = False

    def stop_song(self):
        pygame.mixer.music.stop()
        self.song_label.config(text="")

# اجرای برنامه
root = tk.Tk()
app = MusicPlayer(root)
root.mainloop()import tkinter as tk
from tkinter import filedialog, Listbox
import pygame
import os

# شروع pygame
pygame.init()
pygame.mixer.init()

class MusicPlayer:
    def __init__(self, root):
        self.root = root
        self.root.title("پخش‌کننده موسیقی")
        self.root.geometry("400x400")

        self.playlist = []
        self.current_index = -1
        self.is_paused = False

        # لیست آهنگ‌ها
        self.listbox = Listbox(self.root, width=50)
        self.listbox.pack(pady=20)

        # دکمه‌ها
        tk.Button(self.root, text="افزودن آهنگ", command=self.add_song).pack()
        tk.Button(self.root, text="پخش", command=self.play_song).pack(pady=5)
        tk.Button(self.root, text="مکث", command=self.pause_song).pack()
        tk.Button(self.root, text="ادامه", command=self.resume_song).pack()
        tk.Button(self.root, text="توقف", command=self.stop_song).pack(pady=5)

        # برچسب نمایش نام آهنگ
        self.song_label = tk.Label(self.root, text="", fg="blue")
        self.song_label.pack()

    def add_song(self):
        files = filedialog.askopenfilenames(filetypes=[("MP3 Files", "*.mp3")])
        for file in files:
            self.playlist.append(file)
            self.listbox.insert(tk.END, os.path.basename(file))

    def play_song(self):
        try:
            selected = self.listbox.curselection()
            if not selected:
                return
            self.current_index = selected[0]
            pygame.mixer.music.load(self.playlist[self.current_index])
            pygame.mixer.music.play()
            self.song_label.config(text="در حال پخش: " + os.path.basename(self.playlist[self.current_index]))
        except:
            pass

    def pause_song(self):
        if pygame.mixer.music.get_busy():
            pygame.mixer.music.pause()
            self.is_paused = True

    def resume_song(self):
        if self.is_paused:
            pygame.mixer.music.unpause()
            self.is_paused = False

    def stop_song(self):
        pygame.mixer.music.stop()
        self.song_label.config(text="")

# اجرای برنامه
root = tk.Tk()
app = MusicPlayer(root)
root.mainloop()import tkinter as tk
from tkinter import filedialog, Listbox
import pygame
import os

# شروع pygame
pygame.init()
pygame.mixer.init()

class MusicPlayer:
    def __init__(self, root):
        self.root = root
        self.root.title("پخش‌کننده موسیقی")
        self.root.geometry("400x400")

        self.playlist = []
        self.current_index = -1
        self.is_paused = False

        # لیست آهنگ‌ها
        self.listbox = Listbox(self.root, width=50)
        self.listbox.pack(pady=20)

        # دکمه‌ها
        tk.Button(self.root, text="افزودن آهنگ", command=self.add_song).pack()
        tk.Button(self.root, text="پخش", command=self.play_song).pack(pady=5)
        tk.Button(self.root, text="مکث", command=self.pause_song).pack()
        tk.Button(self.root, text="ادامه", command=self.resume_song).pack()
        tk.Button(self.root, text="توقف", command=self.stop_song).pack(pady=5)

        # برچسب نمایش نام آهنگ
        self.song_label = tk.Label(self.root, text="", fg="blue")
        self.song_label.pack()

    def add_song(self):
        files = filedialog.askopenfilenames(filetypes=[("MP3 Files", "*.mp3")])
        for file in files:
            self.playlist.append(file)
            self.listbox.insert(tk.END, os.path.basename(file))

    def play_song(self):
        try:
            selected = self.listbox.curselection()
            if not selected:
                return
            self.current_index = selected[0]
            pygame.mixer.music.load(self.playlist[self.current_index])
            pygame.mixer.music.play()
            self.song_label.config(text="در حال پخش: " + os.path.basename(self.playlist[self.current_index]))
        except:
            pass

    def pause_song(self):
        if pygame.mixer.music.get_busy():
            pygame.mixer.music.pause()
            self.is_paused = True

    def resume_song(self):
        if self.is_paused:
            pygame.mixer.music.unpause()
            self.is_paused = False

    def stop_song(self):
        pygame.mixer.music.stop()
        self.song_label.config(text="")

# اجرای برنامه
root = tk.Tk()
app = MusicPlayer(root)
root.mainloop()
