# Lab-assignment-bs-AI-A-0007
CODE
def Total_Cal(S1,S2,S3):
Total=S1+S2+S3
return Total
def average(Total):
average=Total/3
return average
def Grade_Cal(Aver):
a=Aver
if a>90:
retu="Your Grade is A "
elif 80 <= a <=89:
retu="Your Grade is B "
elif 70 <= a <=79:
retu="Your Grade is C "
elif 60 <= a <=69:
retu="Your Grade is D "
elif 50 <= a <=59:
retu="Your Grade is E "
else:
retu="You ara a fail "
return retu
Total_Class_Marks=0
Class_Average=0.0
Total_Average_Python=0
Total_Average_AI=0
Total_Average_Math=0
Student=[]
for i in range(5):
print("\n",i+1,"Student")
Student_Name=input("Enter Student Name ")
Python = int(input("Enter Number For Python"))
Artificial_Intelligence =int(input("Enter Number For Artificial Intelligence"))
Mathematics = int(input("Enter Number For Mathematics"))
Total=Total_Cal(Python,Artificial_Intelligence,Mathematics )
Average=average(Total)
Grade=Grade_Cal(Average)
Student.append({"Student Name":Student_Name,"Marks For Python":Python,
"Marks for Ai":Artificial_Intelligence ,"Marks for Math":Mathematics,
"Total_Marks":Total,"Average":Average,"Grade":Grade})
Total_Class_Marks=Total_Class_Marks+Total
Total_Average_Python=Total_Average_Python+Python
Total_Average_AI=Total_Average_AI+Artificial_Intelligence
Total_Average_Math=Total_Average_Math+Mathematics
#print(Grade_Cal(average(Total_Cal(Python,Artificial_Intelligence,Mathematics ))))
Class_Average=(Total_Class_Marks/1500)*100
print("\n>>>>> ALl Student Data <<<<<")
for i in Student:
print("\nStudent |", i['Student Name'], "|", i['Marks For Python'], "|", i['Marks for Ai'], "|
", i['Marks for Math'], "|", i['Total_Marks'], "|", i['Average'], "|", i['Grade'])
print("\nTotal Class Marks:", Total_Class_Marks)
print("Class Average:", Class_Average)
print("Class Average Of Python:", (Total_Average_Python/500)*100)
print("Class Average of AI :", (Total_Average_AI/500)*100)
print("Class Average:", (Total_Average_Math/500)*100)
with open("student_records.txt", "w") as file:
file.write(">>>>> ALL Student Data <<<<<\n\n")
Page 2
# Sabhi students ki details file me store karna
for i in Student:
file.write(f"Student | {i['Student Name']} | Python: {i['Marks For Python']} | AI: {i['Mar
ks for Ai']} | Math: {i['Marks for Math']} | Total: {i['Total_Marks']} | Avg: {i['Aver
age']:.2f} | Grade: {i['Grade']}\n")
# Class averages aur total marks save karna
file.write(f"\nTotal Class Marks: {Total_Class_Marks}\n")
file.write(f"Class Average: {Class_Average:.2f}%\n")
file.write(f"Python Avg %: {(Total_Average_Python / 500) * 100:.2f}%\n")
file.write(f"AI Avg %: {(Total_Average_AI / 500) * 100:.2f}%\n")
file.write(f"Math Avg %: {(Total_Average_Math / 500) * 100:.2f}%\n")
print("\nStudent records successfully saved to 'student_records.txt'!")
OUTPUT
1 Student
Cell 2
CODE
# Functions for specific tasks
def get_longest_word(words):
return max(words, key=len)
def get_shortest_word(words):
return min(words, key=len)
def count_vowels(text):
vowels = "aeiouAEIOU"
count = 0
for char in text:
if char in vowels:
count += 1
return count
# User Input
text = input("Enter a sentence: ")
# Words processing
words = text.split()
clean_words = [word.strip(".,!?;:\"'") for word in words if word.strip(".,!?;:\"'")]
# Calculations
total_words = len(words)
total_chars = len(text)
longest = get_longest_word(clean_words) if clean_words else ""
shortest = get_shortest_word(clean_words) if clean_words else ""
vowel_count = count_vowels(text)
unique_words = set(word.lower() for word in clean_words)
sorted_words = sorted(list(unique_words))
# Output display
print("\nTotal Words:", total_words)
print("Total Characters:", total_chars)
print("Longest Word:", longest)
print("Shortest Word:", shortest)
print("Number of Vowels:", vowel_count)
print("Unique Words Set:", unique_words)
print("Words in Alphabetical Order:", sorted_words)
# --- file handling ---
with open("word_analysis.txt", "w") as file:
file.write(f"Total Words: {total_words}\n")
file.write(f"Total Characters: {total_chars}\n")
file.write(f"Longest Word: {longest}\n")
file.write(f"Shortest Word: {shortest}\n")
file.write(f"Number of Vowels: {vowel_count}\n")
file.write(f"Unique Words Set: {unique_words}\n")
file.write(f"Words in Alphabetical Order: {sorted_words}\n")
print("\nAnalysis successfully saved to 'word_analysis.txt'!")
OUTPUT
Enter a sentence: My Name is Faizan Ali. And I am Student of Ai.
Page 3
Total Words: 11
Total Characters: 47
Longest Word: Student
Shortest Word: I
Number of Vowels: 16
Unique Words Set: {'i', 'am', 'ai', 'ali', 'student', 'faizan', 'my', 'is', 'name', 'of', 'and'}
Words in Alphabetical Order: ['ai', 'ali', 'am', 'and', 'faizan', 'i', 'is', 'my', 'name', 'of', '
student']
Analysis successfully saved to 'word_analysis.txt'!
Cell 3
CODE
Total_Bill=0
Discount_Bill=0
Expensive_Product_Price=0
Expensive_Product_Name=""
def Total_Price_Cal(Price,Quantity):
Total_Price= Price*Quantity
return Total_Price
for i in range(5):
Product_Name=input("Enter Product name")
Price=int(input("Enter Product Price"))
Quantity=int(input("Enter Product Quantity"))
print("Total Price for This Product is:",Total_Price_Cal(Price,Quantity))
Total_Bill+=Total_Price_Cal(Price,Quantity)
print("\n")
if Total_Price_Cal(Price,Quantity)>Expensive_Product_Price:
Expensive_Product_Price=Total_Price_Cal(Price,Quantity)
Expensive_Product_Name=Product_Name
print("Your Total bill is :",Total_Bill)
if Total_Bill>500:
Discount_Bill = Total_Bill-((Total_Bill*10)/100)
print("Your Bill After the Discount is:",Discount_Bill)
else:
print("Your Total Bill is Less Than to 500 ,So No discount !")
print("More Expensive Product Is ",Expensive_Product_Name,"And Price is :",Expensive_Product_Price
)
#>>>_>_>_ File handling apply<__Lo-
with open("bill.txt", "w") as file:
file.write(f"Your Total bill is : {Total_Bill}\n")
if Total_Bill > 500:
file.write(f"Your Bill After the Discount is: {Discount_Bill}\n")
else:
file.write("Your Total Bill is Less Than to 500 ,So No discount !\n")
file.write(f"More Expensive Product Is {Expensive_Product_Name} And Price is : {Expensive_Prod
uct_Price}\n")
print("\nOutput successfully saved to 'bill.txt'!")
file.close()
OUTPUT
Enter Product name Drink
Enter Product Price 50
Enter Product Quantity 5
Total Price for This Product is: 250
Enter Product name Snacks
Enter Product Price 60
Enter Product Quantity 6
Total Price for This Product is: 360
Your Total bill is : 610
Page 4
Your Bill After the Discount is: 549.0
More Expensive Product Is Snacks And Price is : 360
Cell 4
CODE
class student:
def input_Two_Number(self):
Number_1=int(input("Enter Number 01:"))
Number_02=int(input("Enter Number 02:"))
return Number_1,Number_02
def Operator_input(self):
Number_1,Number_02= self.input_Two_Number()
while True:
operator=input("\nEnter Operator(+,-,*,/,%) that apply Between Two Operators and type
-1 if you exit:")
if operator=="+":
Sum=Number_1 + Number_02
print("Sum of Two nuber is :",Sum)
elif operator=="-":
Sub=Number_1 - Number_02
print("Subtraction of Two nuber is :",Sub)
elif operator=="*":
Mul=Number_1 * Number_02
print("Multiplication of Two nuber is :",Mul)
elif operator=="/":
if Number_02 != 0:
Div=Number_1 / Number_02
print("Division of Two number is :",Div)
else:
print("Cannot Divide by Zero a/b , (b != 0) ")
elif operator=="%":
Mod=Number_1 % Number_02
print("Modoules of Two nuber is :",Mod)
elif operator== "-1":
print("Thank you For Using This Calculater !")
break
s = student()
s.Operator_input()
OUTPUT
Enter Number 01: 12
Enter Number 02: 13
Enter Operator(+,-,*,/,%) that apply Between Two Operators and type -1 if you exit: /
Rong Input a/b , (a>b)
Enter Operator(+,-,*,/,%) that apply Between Two Operators and type -1 if you exit: -1
Thank you For Using This Calculater !
Cell 5
CODE
Total_Bill=0
def Bill_Cal(select,Quantity):
if select == 1:
bill=Quantity*500
print("your bill is :",bill)
elif select == 2:
bill=Quantity*800
print("your bill is :",bill)
elif select == 3:
bill=Quantity*150
print("your bill is :",bill)
else:
return 0
return bill
while True:
print("------- Menu -------")
print("1. Burger : 500 ","\n2. Pizza : 800","\n3. Fries : 150 ","\nType -1 For exit!")
Page 5
#Menu={"1. Burger ": 500 ,"2. Pizza ": 800,"3. Fries ": 150 }
Select=int(input("Select Menu :"))
if Select == -1:
break
elif 1 <= Select <=3:
Quantity=int(input("Enter Quantity :"))
Total_Bill+=Bill_Cal(Select,Quantity)
else:
print("Rong Input")
print("\nTotal Bill is :",Total_Bill)
OUTPUT
------- Menu -------
1. Burger : 500
2. Pizza : 800
3. Fries : 150
Type -1 For exit!
Select Menu : 1
Enter Quantity : 4
your bill is : 2000
------- Menu -------
1. Burger : 500
2. Pizza : 800
3. Fries : 150
Type -1 For exit!
Select Menu : 6
Rong Input
------- Menu -------
1. Burger : 500
2. Pizza : 800
3. Fries : 150
Type -1 For exit!
Select Menu : 3
Enter Quantity : 6
your bill is : 900
------- Menu -------
1. Burger : 500
2. Pizza : 800
3. Fries : 150
Type -1 For exit!
Select Menu : -1
Total Bill is : 2900