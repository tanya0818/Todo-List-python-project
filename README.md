# Todo-List-python-project
import tkinter
from tkinter import *
from tkinter import messagebox
def addTask():
    task=entry.get()
    if task!="":
        lb.insert(END,task)
        entry.delete(0,"end")
    else:
        messagebox.showwarning("warning","Please enter some task.")
def deleteTask():
    lb.delete(ANCHOR)

root=Tk()
root.title("To-Do List")
root.geometry("500x450+500+200")
root.config(bg='#223441')
root.resizable(False,False)

frame=Frame(root)
frame.pack(pady=10)

lb=Listbox(frame,width=25,height=8,font=('Times',18),bd=0,fg='#464646',highlightthickness=0,selectbackground='#a6a6a6',activestyle="none")
lb.pack(side=LEFT,fill=BOTH)
lst=[]
for item in lst:
    lb.insert(END,item)

sb=Scrollbar(frame)
sb.pack(side=RIGHT,fill=BOTH)
lb.config(yscrollcommand=sb.set)
sb.config(command=lb.yview)
entry=Entry(root,font=('times',24))
entry.pack(pady=20)

button=Frame(root)
button.pack(pady=20)
add_button=Button(button,text='Add Task',font=('times14'),bg='#c5f776',padx=20,pady=10,command=addTask)
add_button.pack(fill=BOTH,expand=True,side=LEFT)
del_button=Button(button,text='Remove task',font=('times14'),bg='#ff8b61',padx=20,pady=10,command=deleteTask)
del_button.pack(fill=BOTH,expand=True,side=LEFT)
root.mainloop()
