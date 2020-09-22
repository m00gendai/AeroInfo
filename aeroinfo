import csv
import tkinter as tk
import urllib
import urllib.request
import os.path, time

def navaidgetter():
    getter = entry_1.get()  
    capgetter = getter.upper()
    with open('navaids.csv') as csv_file:
        csv_reader = csv.reader(csv_file, delimiter=',')
        line_count = 0
        for row in csv_reader:
            if capgetter == row[2] or capgetter == row[19] and row[19] != "":
                box1.insert(0, row[3])
                box2.insert(0, row[2])
                if row[4] == "VOR-DME":
                    box3.insert(0, row[4][0:3] + "/" + row[4][4:7])
                else:
                    box3.insert(0, row[4])
                if len(row[5]) < 4:
                    box4.insert(0, row[5])
                else:
                    box4.insert(0, row[5][0:3] + "." + row[5][3:6])
                box5.insert(0, row[9])
                if row[19] == "":
                    box6.insert(0, "none")
                else:
                    box6.insert(0, row[19])
        if box2.size() == 0:
            label_notfound = tk.Label(text="no records found", bg='#f7f7f7', fg="red")
            label_notfound.grid(row=0, column=2, padx=10, pady=5, sticky="w")


def airportgetter():
    getter = entry_2.get()  
    capgetter = getter.upper()
    with open('runways.csv') as csv_file:
        csv_reader = csv.reader(csv_file, delimiter=',')
        line_count = 0
        for row in csv_reader:
            if capgetter == row[2]:
                box7.insert(0, row[2])
                box8.insert(0, row[8] + "/" + row[14])
                
        if box7.size() == 0:
            label_notfound = tk.Label(text="no records found", bg='#f7f7f7', fg="red")
            label_notfound.grid(row=4, column=2, padx=10, pady=5, sticky="w")
        else:
            label_notfound = tk.Label(text="                                ", bg='#f7f7f7')
            label_notfound.grid(row=4, column=2, padx=10, pady=5, sticky="w")
    with open('airport-frequencies.csv', encoding="utf8") as csv_file:
        csv_reader = csv.reader(csv_file, delimiter=',')
        line_count = 0
        for row in csv_reader:
            if capgetter == row[2]:
                box9.insert(0, row[3])
                box10.insert(0, row[4])
                box11.insert(0, row[5])
    


def handle_keypress_navaid(event):
    label_notfound = tk.Label(text="                                ", bg='#f7f7f7')
    label_notfound.grid(row=0, column=2, padx=10, pady=5, sticky="w")
    box1.delete(0, "end")
    box2.delete(0, "end")
    box3.delete(0, "end")
    box4.delete(0, "end")
    box5.delete(0, "end")
    box6.delete(0, "end")
    navaidgetter()
    

def handle_button_navaid():                 # checks for specific pressed keys (tkinter)

    box1.delete(0, "end")
    box2.delete(0, "end")
    box3.delete(0, "end")
    box4.delete(0, "end")
    box5.delete(0, "end")
    box6.delete(0, "end")
    navaidgetter()


def handle_keypress_ap(event):
    label_notfound = tk.Label(text="                                ", bg='#f7f7f7')
    label_notfound.grid(row=4, column=2, padx=10, pady=5, sticky="w")
    box7.delete(0, "end")
    box8.delete(0, "end")
    box9.delete(0, "end")
    box10.delete(0, "end")
    box11.delete(0, "end")
    airportgetter()
    

def handle_button_ap():                 # checks for specific pressed keys (tkinter)
    box7.delete(0, "end")
    box8.delete(0, "end")
    box9.delete(0, "end")
    box10.delete(0, "end")
    box11.delete(0, "end")
    airportgetter()

# urllib.request.urlretrieve ("https://ourairports.com/data/navaids.csv", "navaids.csv")

window = tk.Tk()
window.title("AeroInfo by @weberml")
window.configure(bg='#f7f7f7')
window.minsize(810, 755)
entry = tk.Entry()

box1 = tk.Listbox(height=15)
box2 = tk.Listbox()
box3 = tk.Listbox()
box4 = tk.Listbox()
box5 = tk.Listbox()
box6 = tk.Listbox()
box7 = tk.Listbox(height=15)
box8 = tk.Listbox()
box9 = tk.Listbox()
box10 = tk.Listbox()
box11 = tk.Listbox()

label_notfound = tk.Label(text="no records found")

label_l = tk.Label(text="Enter Navaid: ")
label_l.grid(row=0, column=0, padx=5, pady=5, sticky="w")
label_l.configure(bg="#f7f7f7")
entry_1 = tk.Entry()
entry_1.grid(row=0, column=1, padx=5, pady=5, sticky="e")
entry_1.configure(bg="white")
entry_1.focus()
label_2 = tk.Label(text="Enter Airport: ")
label_2.grid(row=4, column=0, padx=5, pady=5, sticky="w")
label_2.configure(bg="#f7f7f7")
entry_2 = tk.Entry()
entry_2.grid(row=4, column=1, padx=5, pady=5, sticky="e")
entry_2.configure(bg="white")

button1 = tk.Button(text="Get", bg="#fcfcfc", fg="black", command=handle_button_navaid, borderwidth = 1, relief="raised")
button1.grid(row=1, column=0, columnspan=6, padx=5, pady=5, sticky="nesw",)
button2 = tk.Button(text="Get", bg="#fcfcfc", fg="black", command=handle_button_ap, borderwidth = 1, relief="raised")
button2.grid(row=5, column=0, columnspan=6, padx=5, pady=5, sticky="nesw",)

label_2a = tk.Label(text="Name")
label_2a.grid(row=2, column=0, padx=5, pady=3, sticky="w")
label_2a.configure(bg="#f7f7f7")
label_2b = tk.Label(text="ID")
label_2b.grid(row=2, column=1, padx=1, pady=3, sticky="w")
label_2b.configure(bg="#f7f7f7")
label_2c = tk.Label(text="TYP")
label_2c.grid(row=2, column=2, padx=1, pady=3, sticky="w")
label_2c.configure(bg="#f7f7f7")
label_2d = tk.Label(text="FREQ")
label_2d.grid(row=2, column=3, padx=1, pady=3, sticky="w")
label_2d.configure(bg="#f7f7f7")
label_2e = tk.Label(text="Country")
label_2e.grid(row=2, column=4, padx=1, pady=3, sticky="w")
label_2e.configure(bg="#f7f7f7")
label_2f = tk.Label(text="AD")
label_2f.grid(row=2, column=5, padx=1, pady=3, sticky="w")
label_2f.configure(bg="#f7f7f7")

label_3a = tk.Label(text="Airport")
label_3a.grid(row=6, column=0, padx=5, pady=3, sticky="w")
label_3a.configure(bg="#f7f7f7")
label_3b = tk.Label(text="RWY")
label_3b.grid(row=6, column=1, padx=1, pady=3, sticky="w")
label_3b.configure(bg="#f7f7f7")
label_3c = tk.Label(text="FREQ Type")
label_3c.grid(row=6, column=2, padx=1, pady=3, sticky="w")
label_3c.configure(bg="#f7f7f7")
label_3d = tk.Label(text="FREQ Description")
label_3d.grid(row=6, column=3, padx=1, pady=3, sticky="w")
label_3d.configure(bg="#f7f7f7")
label_3e = tk.Label(text="FREQ")
label_3e.grid(row=6, column=4, padx=1, pady=3, sticky="w")
label_3e.configure(bg="#f7f7f7")

box1.grid(row=3, column=0, padx=(5, 1), sticky="nesw")
box2.grid(row=3, column=1, padx=1, sticky="nesw")
box3.grid(row=3, column=2, padx=1, sticky="nesw")
box4.grid(row=3, column=3, padx=1, sticky="nesw")
box5.grid(row=3, column=4, padx=1, sticky="nesw")
box6.grid(row=3, column=5, padx=(1, 5), sticky="nesw")
box7.grid(row=7, column=0, padx=(5, 1), sticky="nesw")
box8.grid(row=7, column=1, padx=1, sticky="nesw")
box9.grid(row=7, column=2, padx=1, sticky="nesw")
box10.grid(row=7, column=3, padx=1, sticky="nesw")
box11.grid(row=7, column=4, padx=(1,5), sticky="nesw")
box1.grid_rowconfigure(0, weight=1)

label_src1 = tk.Label(text="Source Navaids: ourairports.com/data > navaids.csv")
label_src1.grid(row=8, column=0, columnspan=2, pady=(10, 0), padx=5, sticky="nw")
label_src1.configure(bg="#f7f7f7", font=("TkDefaultFont", 7))
label_dat1 = tk.Label(text="Latest update: %s" % time.ctime(os.path.getmtime("navaids.csv")))
label_dat1.grid(row=8, column=4, columnspan=2, pady=(10,0), padx=5, sticky="ne")
label_dat1.configure(bg="#f7f7f7", font=("TkDefaultFont", 7))
label_src2 = tk.Label(text="Source Runways: ourairports.com/data > runways.csv")
label_src2.grid(row=9, column=0, columnspan=2, pady=(10, 0), padx=5, sticky="nw")
label_src2.configure(bg="#f7f7f7", font=("TkDefaultFont", 7))
label_dat2 = tk.Label(text="Latest update: %s" % time.ctime(os.path.getmtime("runways.csv")))
label_dat2.grid(row=9, column=4, columnspan=2, pady=(10,0), padx=5, sticky="ne")
label_dat2.configure(bg="#f7f7f7", font=("TkDefaultFont", 7))
label_src3 = tk.Label(text="Source Frequencies: ourairports.com/data > airport-frequencies.csv")
label_src3.grid(row=10, column=0, columnspan=2, pady=(10, 0), padx=5, sticky="nw")
label_src3.configure(bg="#f7f7f7", font=("TkDefaultFont", 7))
label_dat3 = tk.Label(text="Latest update: %s" % time.ctime(os.path.getmtime("airport-frequencies.csv")))
label_dat3.grid(row=10, column=4, columnspan=2, pady=(10,0), padx=5, sticky="ne")
label_dat3.configure(bg="#f7f7f7", font=("TkDefaultFont", 7))

# print("%s" % time.ctime(os.path.getmtime("navaids.csv")))

# Bind keypress event to handle_keypress()
entry_1.bind("<Return>", handle_keypress_navaid)
navaidgetter()
entry_2.bind("<Return>", handle_keypress_ap)
airportgetter()


window.mainloop()


