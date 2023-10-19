# CHALLENGE1.1

1.1def isLeapYear(year):
    if(year % 4 == 0 and year % 100 != 0) or year % 400 == 0:
        return True
    else:
        return False
year=int(input("Enter a year"))


if isLeapYear(year):
    print('{} is a leap year.'.format(year))
else:
    print('{} is not a leap year.'.format(year))

#CHALLENGE1.2

1.2 def  factorial(n):
  if n==0|n==1:
    return 1
  else:
    return n*factorial(n-1)
number=5
result=factorial(number)

print("the facti=orial of {}is{}.".format(number,result))


#CHALLENGE2.1

# 2.1 Implement a class called BankAccount that represents a bank account. The class should have private attributes for account number, account holder name, and account balance. Include methods to deposit money, withdraw money, and display the account balance. Ensure that the account balance cannot be accessed directly from outside the class. Write a program to create an instance of the BankAccount class and test the deposit and withdrawal functionality. class BankAccount: def __init__(self, account_number, account_holder_name, initial_balance=0.0): self.__account_number = account_number self.__account_holder_name = account_holder_name self.__account_balance = initial_balance def deposit(self, amount): if amount > 0: self.__account_balance += amount print(f"Deposited ${amount:.2f} into account {self.__account_number}") else: print("Invalid deposit amount. Please deposit a positive amount.") def withdraw(self, amount): if amount > 0: if self.__account_balance >= amount: self.__account_balance -= amount print(f"Withdrew ${amount:.2f} from account {self.__account_number}") else: print("Insufficient balance. Cannot withdraw.") else: print("Invalid withdrawal amount. Please withdraw a positive amount.") def display_balance(self): print(f"Account {self.__account_number} balance: ${self.__account_balance:.2f}") # Testing the BankAccount class if _name_ == "__main__": # Create a BankAccount instance account1 = BankAccount("123456", "John Doe", 1000.0) # Deposit money account1.deposit(500.0) # Withdraw money account1.withdraw(200.0) # Display balance account1.display_balance()


#CHALLENGE 2.2

#2.2 Implement a class called Player that represents a cricket player. The Player class should have a method called play() which prints "The player is playing cricket. Derive two classes, Batsman and Bowler, from the Player class. Override the play() method in each derived class to print "The batsman is batting" and "The bowler is bowling", respectively. Write a program to create objects of both the Batsman and Bowler classes and call the play() method for each object. # Define the Player class class Player: def play(self): print("The player is playing cricket.") # Define the Batsman class, derived from Player class Batsman(Player): def play(self): print("The batsman is batting.") # Define the Bowler class, derived from Player class Bowler(Player): def play(self): print("The bowler is bowling.") # Create objects of Batsman and Bowler classes batsman = Batsman() bowler = Bowler() # Call the play() method for each object batsman.play() bowler.play()


#CHALLENGE3.1

#3.1 Write a function called linear_search_product that takes the list of products and a target product name as input. The function should perform a linear search to find the target product in the list and return a list of indices of all occurrences of the product if found, or an empty list if the product is not found.
def linear_search_product(product_list, target_product):
    indices = []
    for i, product in enumerate(product_list):
        if product == target_product:
            indices.append(i)
    return indices

# Example usage:
products = ["apple", "banana", "apple", "orange", "apple"]
target = "apple"
result = linear_search_product(products, target)
if result:
    print(f"The product '{target}' was found at indices: {result}")
else:
    print(f"The product '{target}' was not found in the list.")

#CHALLENGE 3.2

#3.2 Implement a function called sort_students that takes a list of student objects as input and sorts the list based on their CGPA (Cumulative Grade Point Average) in descending order. Each student object has the following attributes: name (string), roll_number (string), and cgpa (float). Test the function with different input lists of students.
class Student:
    def __init__(self, name, roll_number, cgpa):
        self.name = name
        self.roll_number = roll_number
        self.cgpa = cgpa

def sort_students(student_list):
    sorted_students = sorted(student_list, key=lambda student: student.cgpa, reverse=True)
    return sorted_students

# Example usage:
student1 = Student("Alice", "S123", 3.7)
student2 = Student("Bob", "S124", 3.9)
student3 = Student("Charlie", "S125", 3.5)
student4 = Student("David", "S126", 3.8)

students = [student1, student2, student3, student4]

sorted_students = sort_students(students)

# Print the sorted list of students by CGPA in descending order
for student in sorted_students:
    print(f"Name: {student.name}, Roll Number: {student.roll_number}, CGPA: {student.cgpa}")
