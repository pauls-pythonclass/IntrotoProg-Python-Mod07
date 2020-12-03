Paul Shaw

Dec 1st, 2020

IT FDN 110A

Assignment #7

# Assignment #7 - Pickling, Try & Except

# Introduction
Week 7 modules and chapter 7 added more complexity to programs  by working with pickling and.

# Assignment Task
The assignment task was to revise previously written code that would perform the same end task of saving data to a file as a pickled format, and reloading it from the pickled format.  Additionally a short example was created on how to execute a try & except operation.

# Proof of Work
Script was developed with the knowledge learned in module 7.  The script was started from the Assignment07_starter file and built within the Pycharm program and additionally ran with the Windows command prompt.  I was able to find solutions for most code to transfer them to a function setup with the aid of the course material. The code was ran in both the command prompt and PyCharm and worked well.  The try and except function also displayed error codes appropriately, as the case when the user inputs a string when it is expecting an interger.  
![Clip of Pycharm execution](https://github.com/pauls-pythonclass/IntrotoProg-Python-Mod07/blob/main/os%20run.PNG"Figure 1: Pycharm Execution")
Figure 1: Pycharm Execution(pickling, try & except)
```
# ------------------------------------------------- #
# Title: Assignment 07
# Description: A simple example of storing data in a binary file
# ChangeLog: (Who, When, What)
# <Paul Shaw>,<12.1.2020>,Created Script
# ------------------------------------------------- #
###
#  References - Pickling, try & except
#  https://www.geeksforgeeks.org/understanding-python-pickling-example/
#  https://www.tutorialspoint.com/python-pickling
#  https://realpython.com/python-exceptions/
###
import pickle  # This imports code from another code file!

# Data -------------------------------------------- #
strFileName = 'AppData.dat'
lstCustomer = []

class nochoice(Exception):
    def __str__(self):
        return('please enter 1,2, or 3') +"\n"
# Processing -------------------------------------- #
def save_data(file_name, list_of_data):
    file = open(file_name, 'wb')
    pickle.dump(list_of_data, file)
    file.close()

def read_data_from_file(file_name):
    file = open(file_name, 'rb')
    list_of_data = pickle.load(file)
    file.close()
    return list_of_data


# Presentation ------------------------------------ #
print("Pickling Database")
id = input(str("Please enter ID: "))
name = input (str("Please enter your name: "))
lstCustomer = [id, name]

save_data(strFileName, lstCustomer) #execute pickling save

print(read_data_from_file(strFileName)) #printing pickle data from file

#Error Handling Example
while True:
    try:
        choice = int(input("Enter 1 to input a number \nEnter 2 to input a word\n Enter 3 to exit: ")) #number must be selected or error will generate
        if choice == 1:

            numinput = int(input("Enter a whole number: ")) #choice must be # or error will result
            print("your number was:",(numinput))
            print(e)

        elif choice == 2:
            strinput = str(input("Enter a word: ")) # no error will be generated
            print("your word is: ",(strinput))
        elif choice == 3:
            break
        else:
            raise nochoice()
    except ValueError as e:
        print("Input was not a number, please try again")
        print(e)
    except Exception as e:
        print('the python message is: +"\n')
        print(e)
```


Figure 2: Clips from pycharm code

Figure 3: Updated pickled txt file from input 


Figure 4: Executing properly within command prompt.

	


Summary
As shown the code completed the task, albeit in a simplified manner.

