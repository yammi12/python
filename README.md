                    PROGRAM : 1A

test1 = int(input("Enter marks of Test 1: "))
test2 = int(input("Enter marks of Test 2: "))
test3 = int(input("Enter marks of Test 3: "))
Worst_score = min(test1, test2, test3)
best_average = (test1 + test2 + test3 - Worst_score) / 2
print("Best average of two tests: ", best_average) 

                      PROGRAM : 1B
                      
num = int(input("Enter number:"))
temp=num
rev=0
while(num>0):
dig = num % 10
rev = rev*10 + dig
num = num//10
if(temp==rev):
print(f"The number {temp} is a palindrome!")
else:
print(f"The number {temp} isn't a palindrome!")
digit_counts = {}
for digit in str(temp):
if digit in digit_counts:
digit_counts[digit] += 1
else:
digit_counts[digit] = 1
print("Digit counts in", temp, ":")
for digit, count in digit_counts.items():
print(digit, ":", count)


               PROGRAM: 2A
               
def Fibonacci(n):
if n<= 0:
print("Incorrect input, Please enter a positive integer")
# First Fibonacci number is 0
elif n == 1:
return 0
# Second Fibonacci number is 1
elif n == 2:
return 1
else:
return Fibonacci(n-1)+Fibonacci(n-2)
n = int(input("Enter a positive integer: "))
print(Fibonacci(n))


              PROGRAM: 2B (binary to decimal)
              
def binaryToDecimal(binary):
decimal, i = 0, 0
while(binary != 0):
dec_rem = binary % 10
decimal = decimal + dec_rem * pow(2, i)
binary = binary//10
i += 1
print(f"binary number {bin} in decimal is: ",
decimal)
bin = int(input("Enter the binary number for
conversion: "))
binaryToDecimal(bin)


           PROGRAM: 2B (octal to hexadecimal)
           
octal_number = input("Enter octal number")
# convert octal to decimal
decimal_number = 0
power = len(str(octal_number)) - 1
for digit in str(octal_number):
decimal_number += int(digit) * 8 ** power
power -= 1
# convert decimal to hexadecimal
hexadecimal_number=hex(decimal_number)[2:].upper()
print(f"The hexadecimal equivalent of {octal_number} is {hexadecimal_number}"


          PROGRAM: 3A
          
sentence = input("Enter a sentence: ")
num_words = len(sentence.split())
num_digits = 0
num_uppercase = 0
num_lowercase = 0
for char in sentence:
if char.isdigit():
num_digits += 1
elif char.isupper():
num_uppercase += 1
elif char.islower():
num_lowercase += 1
print("Number of words:", num_words)
print("Number of digits:", num_digits)
print("Number of uppercase letters:", num_uppercase)
print("Number of lowercase letters:", num_lowercase) 


            PROGRAM: 3B
            
from difflib import SequenceMatcher
string1 = "Python Exercises"
string2 = "Python Exercise"
similarity = SequenceMatcher(None, string1, string2).ratio()
print("Original string:")
print(string1)
print(string2)
print("Similarity between two said strings:")
print(similarity)


            PROGRAM: 4A (insertion sort)
            
def insertion_sort(alist):
for i in range(1, len(alist)):
temp = alist[i]
j = i - 1
while (j >= 0 and temp < alist[j]):
alist[j + 1] = alist[j]
j = j - 1
alist[j + 1] = temp
alist = input('Enter the list of numbers: ').split()
alist = [int(x) for x in alist]
insertion_sort(alist)
print('Sorted list: ', end='')
print(alist)


           PROGRAM: 4A (merge sort)
           
def merge_sort(arr):
if len(arr) > 1:
mid = len(arr) // 2
left_half = arr[:mid]
right_half = arr[mid:]
merge_sort(left_half)
merge_sort(right_half)
i = j = k = 0
while i < len(left_half) and j < len(right_half):
if left_half[i] < right_half[j]:
arr[k] = left_half[i]
i += 1
else:
arr[k] = right_half[j]
j += 1
k += 1
while i < len(left_half):
arr[k] = left_half[i]
i += 1
k += 1
while j < len(right_half):
arr[k] = right_half[j]
j += 1
k += 1
return arr
num = int(input("how many elements you want in a list: "))
arr = [int(input()) for x in range(num)]
merge_sort(arr)
print("sorted list is: ", arr) 


           PROGRAM: 4B
           
def roman_to_int(roman_numeral):
roman_dict = {'I': 1, 'V': 5, 'X': 10, 'L': 50, 'C': 100, 'D': 500, 'M': 1000}
result = 0
prev_value = 0
for i in range(len(roman_numeral)-1, -1, -1):
current_value = roman_dict[roman_numeral[i]]
if current_value < prev_value:
result -= current_value
else:
result += current_value
prev_value = current_value
return result
print(roman_to_int('XXIV'))
print(roman_to_int('MMMCMLXXXVI')) 


                    PROGRAM: 5A
                    
# How to recognize the pattern without using regular expressions:
def isphonenumber(text):
if len(text) != 12:
return False
for i in range(0, 3):
if not text[i].isdecimal():
return False
if text[3] != '-':
return False
for i in range(4, 7):
if not text[i].isdecimal():
return False
if text[7] != '-':
return False
for i in range(8, 12):
if not text[i].isdecimal():
return False
return True
# call function with a string argument to check if it matches the pattern of a phone number
isphonenumber('415-555-4242')


                   PROGRAM:5B
                   
with open('filename.txt', 'r') as file:
text = file.read()
import re
# Search for phone numbers using regular expressions
phone_numbers = re.findall(r'\+91\d{10}', text)
# Search for email addresses using regular expressions
email_addresses = re.findall(r'\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Z|az]{2,}\b', text)
# Print the results
print("Phone numbers found:", phone_numbers)
print("Email addresses found:", email_addresses)


                       PROGRAM:6A.1
                       
inputFile = "exampletextfile.txt" # input text file
N = int(input("Enter N value: ")) # Enter N value
with open(inputFile, 'r') as filedata: # Opening the given file in read-only mode
linesList= filedata.readlines() # Read the file lines using readlines()
print("The following are the first",N,"lines of a text file:")
for textline in (linesList[:N]): # Traverse in the list of lines to retrieve the first N lines of a file
print(textline, end ='') # Printing the first N lines of the file line by line.
filedata.close() # Closing the input file


                     PROGRAM:6A.2
                     
fname = input("Enter file name: ")
word=input("Enter word to be searched:")
k = 0
with open(fname, 'r') as f:
for line in f:
words = line.split()
for i in words:
if(i==word):
k=k+1
print(f"Occurrences of the word {word} is:" , k ) 


                     PROGRAM:6B
                     
import os
from zipfile import ZipFile
# Create object of ZipFile
with ZipFile('E:/Zipped file.zip', 'w') as zip_object:
# Traverse all files in directory
for folder_name, sub_folders, file_names in os.walk('E:\CIT\DSD lab programs'):
for filename in file_names:
# Create filepath of files in directory
file_path = os.path.join(folder_name, filename)
# Add files to zip file
zip_object.write(file_path, os.path.basename(file_path))
if os.path.exists('E:/Zipped file.zip'):
print("ZIP file created")
else:
print("ZIP file not created") 


                PROGRAM: 7A
                
class Shape:
def area(self):
pass
class Triangle(Shape):
def init (self, base, height):
self.base = base
self.height = height
def area(self):
return 0.5 * self.base * self.height
class Circle(Shape):
def init (self, radius):
self.radius = radius
def area(self):
return 3.14 * self.radius * self.radius
class Rectangle(Shape):
def init (self, length, width):
self.length = length
self.width = width
def area(self):
return self.length * self.width
# Example usage
t = Triangle(10, 5)
print("Area of triangle:", t.area())
c = Circle(7)
print("Area of circle:", c.area())
r = Rectangle(8, 6)
print("Area of rectangle:", r.area())


                 PROGRAM: 7B
                 
class Employee:
def init (self):
self.name = ""
self.employee_Id = ""
self.department = ""
self.salary = 0
def getEmpDetails(self):
self.name = input("Enter Employee name : ")
self.employee_Id = input("Enter Employee ID : ")
self.department = input("Enter Employee Dept : ")
self.salary = int(input("Enter Employee Salary : "))
def showEmpDetails(self):
print("Employee Details")
print("Name : ", self.name)
print("ID : ", self.employee_Id)
print("Dept : ", self.department)
print("Salary : ", self.salary)
def updtSalary(self):
self.salary = int(input("Enter new Salary : "))
print("Updated Salary", self.salary)
e1 = Employee()
e1.getEmpDetails()
e1.showEmpDetails()
e1.updtSalary()


                    PROGRAM: 8
                    
class PaliStr:
def init (self):
self.isPali = False
def chkPalindrome(self, myStr):
if myStr == myStr[::-1]:
self.isPali = True
else:
self.isPali = False
return self.isPali
class PaliInt(PaliStr):
def init (self):
self.isPali = False
def chkPalindrome(self, val):
temp = val
rev = 0
while temp != 0:
dig = temp % 10
rev = (rev*10) + dig
temp = temp //10
if val == rev:
self.isPali = True
else:
self.isPali = False
return self.isPali
st = input("Enter a string : ")
stObj = PaliStr()
Python Programming Lab / 21CSL46
Dept of AD, CIT, GUBBI. Page 33
if stObj.chkPalindrome(st):
print("Given string is a Palindrome")
else:
print("Given string is not a Palindrome")
val = int(input("Enter a integer : "))
intObj = PaliInt()
if intObj.chkPalindrome(val):
print("Given integer is a Palindrome")
else:
print("Given integer is not a Palindrome")


                        PROGRAM: 9.A
                        
import requests
import os
from bs4 import BeautifulSoup
# Set the URL of the first XKCD comic
url = 'https://xkcd.com/1/'
# Create a folder to store the comics
if not os.path.exists('xkcd_comics'):
os.makedirs('xkcd_comics')
# Loop through all the comics
while True:
# Download the page content
res = requests.get(url)
res.raise_for_status()
# Parse the page content using BeautifulSoup
soup = BeautifulSoup(res.text, 'html.parser')
# Find the URL of the comic image
comic_elem = soup.select('#comic img')
if comic_elem == []:
print('Could not find comic image.')
else:
comic_url = 'https:' + comic_elem[0].get('src')
# Download the comic image
print(f'Downloading {comic_url}...')
res = requests.get(comic_url)
res.raise_for_status()
# Save the comic image to the xkcd_comics folder
image_file = open(os.path.join('xkcd_comics',
os.path.basename(comic_url)), 'wb')
Python Programming Lab / 21CSL46
Dept of AD, CIT, GUBBI. Page 35
for chunk in res.iter_content(100000):
image_file.write(chunk)
image_file.close()
# Get the URL of the previous comic
prev_link = soup.select('a[rel="prev"]')[0]
if not prev_link:
break
url = 'https://xkcd.com' + prev_link.get('href')
print('All comics downloaded.')


                PROGRAM: 9.B
                
from openpyxl import Workbook
from openpyxl.styles import Font
wb = Workbook()
sheet = wb.active
sheet.title = "Language"
wb.create_sheet(title = "Capital")
lang = ["Kannada", "Telugu", "Tamil"]
state = ["Karnataka", "Telangana", "Tamil Nadu"]
capital = ["Bengaluru", "Hyderabad", "Chennai"]
code =['KA', 'TS', 'TN']
sheet.cell(row = 1, column = 1).value = "State"
sheet.cell(row = 1, column = 2).value = "Language"
sheet.cell(row = 1, column = 3).value = "Code"
ft = Font(bold=True)
for row in sheet["A1:C1"]:
for cell in row:
cell.font = ft
for i in range(2,5):
sheet.cell(row = i, column = 1).value = state[i-2]
sheet.cell(row = i, column = 2).value = lang[i-2]
sheet.cell(row = i, column = 3).value = code[i-2]
wb.save("demo.xlsx")
sheet = wb["Capital"]
sheet.cell(row = 1, column = 1).value = "State"
sheet.cell(row = 1, column = 2).value = "Capital"
sheet.cell(row = 1, column = 3).value = "Code"
Python Programming Lab / 21CSL46
Dept of AD, CIT, GUBBI. Page 37
ft = Font(bold=True)
for row in sheet["A1:C1"]:
for cell in row:
cell.font = ft
for i in range(2,5):
sheet.cell(row = i, column = 1).value = state[i-2]
sheet.cell(row = i, column = 2).value = capital[i-2]
sheet.cell(row = i, column = 3).value = code[i-2]
wb.save("demo.xlsx")
srchCode = input("Enter state code for finding capital ")
for i in range(2,5):
data = sheet.cell(row = i, column = 3).value
if data == srchCode:
print("Corresponding capital for code", srchCode, "is", sheet.cell(row = i, column =
2).value)
sheet = wb["Language"]
srchCode = input("Enter state code for finding language ")
for i in range(2,5):
data = sheet.cell(row = i, column = 3).value
if data == srchCode:
print("Corresponding language for code", srchCode, "is", sheet.cell(row = i, column =
2).value)
wb.close()


                   PROGRAM: 10.A
                   
from PyPDF2 import PdfWriter, PdfReader
num = int(input("Enter page number you want combine from multiple documents "))
pdf1 = open('10a1.pdf', 'rb')
pdf2 = open('10a2.pdf', 'rb')
pdf_writer = PdfWriter()
pdf1_reader = PdfReader(pdf1)
page = pdf1_reader.pages[num - 1]
pdf_writer.add_page(page)
pdf2_reader = PdfReader(pdf2)
page = pdf2_reader.pages[num - 1]
pdf_writer.add_page(page)
with open('output.pdf', 'wb') as output:
pdf_writer.write(output) 


                  PROGRAM: 10.B 

import json
# Open the JSON file and read its contents
with open('weather.json', 'r') as f:
data = f.read()
# Parse the JSON data into a Python dictionary
weather_dict = json.loads(data)
# Access the weather data from the dictionary
temperature = weather_dict['main']['temp']
humidity = weather_dict['main']['humidity']
description = weather_dict['weather'][0]['description']
# Print the weather data
print(f"Temperature: {temperature}°C")
print(f"Humidity: {humidity}%")
print(f"Description: {description}")                   









