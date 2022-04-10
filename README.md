# DailyPlanner
'''PACKAGES'''
from tkinter import *
#-----------------------END IMPORTING PACKAGES

'''WINDOW ATTRIBUTES'''
window_layout=Tk()#Declare var as Tkinter GUI
window_layout.title('Daily Planner')#Window Title
window_layout.geometry('1010x650+0+0')#Layout Size and Location
window_layout.resizable(False,False)#Disable program resize function
window_layout.iconbitmap(r'daily_planner_icon_j6c_icon.ico')#Icon
window_layout.configure(bg='#141414')
#-----------------------END WINDOW ATTRIBUTES

'''FRAMES, CANVAS, BACKGROUND'''
bkg1=PhotoImage(file='cami_bkg.png')
#-----------------------END FRAME DECLARATION
left_canvas = Canvas(window_layout,width=800,height=800)
left_canvas.pack(fill='both', expand=True)
left_canvas.create_image(0,0,image=bkg1,anchor='nw')
#-----------------------END CANVAS DECLARATION
#right_frame = Frame(window_layout, width=240, height=455, bg='ORANGE',relief=RIDGE,borderwidth=3)
#right_frame.place(x=1040, y=65, relx=0.01, rely=0.01)

#-----------------------END BACKGROUND DECLARATION

'''EFFECTS'''
def bttn(x,y,text,bcolor,fcolor,msg):
    #home_btn=PhotoImage(file='home.png')
    def hover(v):
        btn['bg']='#3f3b3d'
    def on_leave(v):
        btn['bg']='#747173'
    btn = Button(window_layout,width=42,height=2,text=text,
                 fg=bcolor,
                 bg=fcolor,
                 border=0,
                 activeforeground=fcolor,
                 activebackground=bcolor,
                 command=msg,)#image=home_btn
    btn.bind("<Enter>", hover)
    btn.bind("<Leave>", on_leave)
    btn.place(x=x,y=y)
def msg():
    print('Done!')
bttn(25,50, 'Sample','#adadad','#8b8b8b',msg)

#Varciables for hover effect
count=0
size=26

def hover():
    home_img= PhotoImage(file='home.png')
    home_btn['image']=home_img
    home_btn.image = home_img
def expand():
    home_img= PhotoImage(file='home_highlight.png.png')
    home_btn['image']=home_img
    home_btn.image = home_img
home_img= PhotoImage(file='home.png')
home_btn = Button(window_layout,image=home_img)
home_btn.image = home_img
home_btn.place(x=0,y=0)

home_btn.bind("<Enter>", hover)
home_btn.bind("<Leave>", expand)
'''WIDGETS'''


'''RUN PROGRAM'''
window_layout.mainloop()#Loop the GUI to run
#-----------------------END PROGRAM CODING || LOOP
