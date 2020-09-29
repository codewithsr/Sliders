# Sliders
This GUI represents the correct use of sliders
Code:


from tkinter import *
import tkinter.messagebox as tmsg

root = Tk()
root.geometry("455x420")
root.minsize(200, 300)
root.maxsize(500, 450)

root.title("Customer Satisfaction GUI")

def dollar():
    print("The amount you have is ...", my_slider2.get())

def rate():
    with open("records of tkinter.txt", "a") as f:
        f.write("You rated us as -- ")
        f.write(f"{my_slider.get()}\n")
        if my_slider.get() >= 7:
            f.write("Thank you so much \n\n")

        else:
            f.write("We are happy to serve you \n\n")



Label(root, text="How many dollars you have in your pocket?").pack()
#my_slider = Scale(root, from_=0, to=100)        #Note: "from" k baad "_" lagana jaroori h
#my_slider.pack()

my_slider2 = Scale(root, from_=0, to=100, orient=HORIZONTAL, tickinterval=20)        #Note: "from" k baad "_" lagana jaroori h
my_slider2.pack(side=TOP, anchor="ne", fill="x")
my_slider2.set(12)      #This will start the value from 12
Button(root, text="Submit", command=dollar).pack()




Label(root, text="Please rate us!", bg="lightblue").pack(pady=10)
my_slider = Scale(root, from_=0, to=10, orient=HORIZONTAL, tickinterval=2)
my_slider.set(6)
my_slider.pack(fill="x")
Button(root, text="Submit", command=rate).pack()



root.mainloop()
