Q1. Explain Class and Object with respect to Object-Oriented Programming. Give a suitable example. 
Ans) Class is a group of similar objects and it is a blueprint from which objects are created. It is declared using class keyword.It is declared once. Eg) class Student{}
Object is an instance of a class. It is a real world entity. It is created through new keyword mainly and we can create objects many times. Eg) student s1 = new Student();


Q2. Name the four pillars of OOPs. 
Ans) Four pillars of OOPS are : Inheritance , Polymorphism, Encapsulation and Abstraction.

Q3. Explain why the __init__() function is used. Give a suitable example.
Ans)All classes have a function called __init__(), which is always executed when the class is being initiated. We use the __init__() function to assign values to object properties, or other operations that are necessary to do when the object is being created. Example:


```python
class Person:
  def __init__(self, name, age):
    self.name = name
    self.age = age

p1 = Person("Soumya", 23)

print(p1.name)
print(p1.age)
```

    Soumya
    23


Q4) Why self is used in OOPs? 
Ans) Self is used in OOPs because it refers to current object. By using self we can access attributes and methods of class.

Q5) What is inheritance? Give an example for each type of inheritance. 
Ans) Inheritance is defined as a mechanism where the sub or child class inherits the properties and characteristics of the other derived classes. It also supports additional features of extracting properties from the child class and using it into other derived classes.

Types of inheritance:
 - Single Inheritance : In this type, the child class(sub class) inherits the properties from the superclass(Parent class).
 Eg:
class Parent:
    def func1(self):
        print("This function is in parent class.")

class Child(Parent):
    def func2(self):
        print("This function is in child class.") 

object = Child()
object.func1()
object.func2()

 - Multiple Inheritance : The child class inherits the properties and features from two or more parent classes with this type.
Eg)
class Mother:
    mothername = ""
    
    def mother(self):
        print(self.mothername)
class Father:
    fathername = ""
 
    def father(self):
        print(self.fathername)
        
class Son(Mother, Father):
    def parents(self):
        print("Father :", self.fathername)
        print("Mother :", self.mothername)
s1 = Son()
s1.fathername = "RAM"
s1.mothername = "SITA"
s1.parents()

 - Multilevel Inheritance : In this type, one child class inherits the properties and behavior from two or more parent classes.
Eg)
class Grandfather:

	def __init__(self, grandfathername):
		self.grandfathername = grandfathername


class Father(Grandfather):
	def __init__(self, fathername, grandfathername):
		self.fathername = fathername

		# invoking constructor of Grandfather class
		Grandfather.__init__(self, grandfathername)

class Son(Father):
	def __init__(self, sonname, fathername, grandfathername):
		self.sonname = sonname
        
		Father.__init__(self, fathername, grandfathername)

	def print_name(self):
		print('Grandfather name :', self.grandfathername)
		print("Father name :", self.fathername)
		print("Son name :", self.sonname)

s1 = Son('Prince', 'Rampal', 'Lal mani')
print(s1.grandfathername)
s1.print_name()

 - Hierarchical Inheritance : In this two or more child classes inherit the properties and behaviors from one parent class.
 Eg)
class Parent:
	def func1(self):
		print("This function is in parent class.")

class Child1(Parent):
	def func2(self):
		print("This function is in child 1.")

class Child2(Parent):
	def func3(self):
		print("This function is in child 2.")

object1 = Child1()
object2 = Child2()
object1.func1()
object1.func2()
object2.func1()
object2.func3()

 - Hybrid Inheritance : In this two or more type of inheritances are used.

class School:
	def func1(self):
		print("This function is in school.")


class Student1(School):
	def func2(self):
		print("This function is in student 1. ")


class Student2(School):
	def func3(self):
		print("This function is in student 2.")


class Student3(Student1, School):
	def func4(self):
		print("This function is in student 3.")

object = Student3()
object.func1()
object.func2()


