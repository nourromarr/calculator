import tkinter
from tkinter import*
root = Tk()

root.title("calcalutor")

root.geometry("300x400+100+200")

root.resizable(False , False)

root.configure(bg="#000")

equation = ' '

def show_operator(value):
  
  global equation
  
  equation+=value
  
  label.config(text=equation)     
      
def show_number(value):
  
  global equation
  
  equation+=value
  
  label.config(text=equation)         
  
def clear():
  global equation
  
  equation= ' '
  
  label.config(text=0.0)
def calculate():
       global equation
       result= ''
       if equation != "":
              try:
                     result = eval(equation)
                     
              except:
                     result = "error"
                     equation = ""
       label.config(text=result)
              


label = Label(root , width=20 , height=1 , text='' , font=("arial " , 30))

label.pack()
label.config(text= 0.0)
Button(root , text='C' , width=8 , height=3 , font=("arial" , 10 , "bold") ,bd = 1  , fg="#fff" , bg="#00f" , command= lambda:clear()).place(x=3 , y=55)

Button(root , text='/' , width=8 , height=3 , font=("arial" , 10 , "bold") ,bd = 1  , fg="#000" , bg="#666",command= lambda:show_operator('/')).place(x=79 , y=55)

Button(root , text='%' , width=8 , height=3 , font=("arial" , 10 , "bold") ,bd = 1  , fg="#000" , bg="#666",command= lambda:show_operator('%')).place(x=155 , y=55)

Button(root , text='*' , width=8 , height=3 , font=("arial" , 10 , "bold") ,bd = 1  , fg="#000" , bg="#666",command= lambda:show_operator('*')).place(x=230, y=55)

Button(root , text='7' , width=8 , height=3 , font=("arial" , 10 , "bold") ,bd = 1  , fg="#000" , bg="#666",command= lambda:show_number('7')).place(x=3 , y=120)
Button(root , text='8' , width=8 , height=3 , font=("arial" , 10 , "bold") ,bd = 1  , fg="#000" , bg="#666",command= lambda:show_number('8')).place(x=79 , y=120)

Button(root , text='9' , width=8 , height=3 , font=("arial" , 10 , "bold") ,bd = 1  , fg="#000" , bg="#666",command= lambda:show_number('9')).place(x=155 , y=120)

Button(root , text='-' , width=8 , height=3 , font=("arial" , 10 , "bold") ,bd = 1  , fg="#000" , bg="#666",command= lambda:show_operator('-')).place(x=230 , y=120)


Button(root , text='4' , width=8 , height=3 , font=("arial" , 10 , "bold") ,bd = 1  , fg="#000" , bg="#666",command= lambda:show_number('4')).place(x=3 , y=185)

Button(root , text='5' , width=8 , height=3 , font=("arial" , 10 , "bold") ,bd = 1  , fg="#000" , bg="#666",command= lambda:show_number('5')).place(x=79 , y=185)

Button(root , text='6' , width=8 , height=3 , font=("arial" , 10 , "bold") ,bd = 1  , fg="#000" , bg="#666",command= lambda:show_number('6')).place(x=155 , y=185)

Button(root , text='+' , width=8 , height=3 , font=("arial" , 10 , "bold") ,bd = 1  , fg="#000" , bg="#666",command= lambda:show_operator('+')).place(x=230 , y=185)


Button(root , text='1' , width=8 , height=3 , font=("arial" , 10 , "bold") ,bd = 1  , fg="#000" , bg="#666",command= lambda:show_number('1')).place(x=3 , y=250)

Button(root , text='2' , width=8 , height=3 , font=("arial" , 10 , "bold") ,bd = 1  , fg="#000" , bg="#666",command= lambda:show_number('2')).place(x=79 , y=250)

Button(root , text='3' , width=8 , height=3 , font=("arial" , 10 , "bold") ,bd = 1  , fg="#000" , bg="#666",command= lambda:show_number('3')).place(x=155 , y=250)

Button(root , text='=' , width=8 , height=9 , font=("arial" , 10 , "bold") ,bd = 1  , fg="#fff" , bg="#830",command= lambda:calculate()).place(x=230 , y=250)


Button(root , text='0' , width=17 , height=4 , font=("arial" , 10 , "bold") ,bd = 1  , fg="#000" , bg="#666",command= lambda:show_number('0')).place(x=3 , y=320)

Button(root , text='.' , width=8 , height=4 , font=("arial" , 10, "bold") ,bd = 1  , fg="#000" , bg="#666",command= lambda:show_number('.')).place(x=155 , y=320)

root.mainloop()
