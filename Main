from tkinter import *
from tkinter import messagebox


def clear():
    STO_entry.delete(0, END)
    DEPAE_entry.delete(0, END)
    ARRA_entry.delete(0, END)
    TRTS_entry.delete(0, END)


def count_load(event = None):
    if (len(STO_entry.get().strip()) == 0 or len(DEPAE_entry.get().strip()) == 0 or len(ARRA_entry.get().strip()) == 0 or len(TRTS_entry.get().strip()) == 0):
        messagebox.showerror("Неверные данные", "Введите все данные")

    elif (STO_entry.get().isdecimal() == 0 or DEPAE_entry.get().isdecimal() == 0 or ARRA_entry.get().isdecimal() == 0 or TRTS_entry.get().isdecimal() == 0):
        messagebox.showerror("Неверные данные", "Введите корректные данные")
        
    elif (int(STO_entry.get()) >= 0 and int(DEPAE_entry.get()) >= 0 and int(ARRA_entry.get()) >= 0 and int(TRTS_entry.get()) > 0):
        load = (int(STO_entry.get()) + int(DEPAE_entry.get()) + int(ARRA_entry.get())) * 100 / int(TRTS_entry.get())
        load = str(int(load))
        messagebox.showinfo("Загрузка", load + " %")
        
    else:
        messagebox.showerror("Неверные данные", "Введите корректные данные")


root = Tk()
root.title("Расчёт загрузки")
root.eval('tk::PlaceWindow . center')


#Data entry
STO_label = Label(text = "Stayovers:")
DEPAE_label = Label(text = "Departures Expected:")
ARRA_label = Label(text = "Arrivals Actual:")
TRTS_label = Label(text = "Total rooms to sell:")

STO_label.grid(row = 0, column = 0, sticky = "e")
DEPAE_label.grid(row = 1, column = 0, sticky = "e")
ARRA_label.grid(row = 2, column = 0, sticky = "e")
TRTS_label.grid(row = 3, column = 0, sticky = "e")

STO_entry = Entry()
DEPAE_entry = Entry()
ARRA_entry = Entry()
TRTS_entry = Entry()
 
STO_entry.grid(row = 0,column = 1, padx = 5, pady = 5)
DEPAE_entry.grid(row = 1,column = 1, padx = 5, pady = 5)
ARRA_entry.grid(row = 2,column = 1, padx = 5, pady = 5)
TRTS_entry.grid(row = 3,column = 1, padx = 5, pady = 5)


#Count, clear and quit buttons.
count_button = Button(text = "Расчитать загрузку", bg = "#FFF", fg = "#800080", font = "16", command = count_load)
clear_button = Button(text = "Очистить", command = clear)
quit_button = Button(root, text = "Выйти",command = root.destroy)

count_button.grid(row = 4,column = 1, padx=5, pady=5, sticky="e")
clear_button.grid(row = 5, column = 1, padx=5, pady=5, sticky="e")
quit_button.grid(row = 6, column = 1, padx=5, pady=5, sticky="e")

root.bind('<Return>', count_load)
root.mainloop()
