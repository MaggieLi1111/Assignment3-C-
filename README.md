# Assignment3-C#

1. What are the six combinations of access modifier keywords and what do they do? 

C# provides four types of access modifiers: private, public, protected, internal, and two combinations: protected-internal and private-protected.
Objects that implement private access modifiers are accessible only inside a class or a structure. As a result, we can’t access them outside the class they are created:
Objects that implement public access modifiers are accessible from everywhere in our project. Therefore, there are no accessibility restrictions:
The protected keyword implies that the object is accessible inside the class and in all classes that derive from that class. 
The internal keyword specifies that the object is accessible only inside its own assembly but not in other assemblies.
The protected internal access modifier is a combination of protected and internal. As a result, we can access the protected internal member only in the same assembly or in a derived class in other assemblies (projects).
The private protected access modifier is a combination of private and protected keywords. We can access members inside the containing class or in a class that derives from a containing class, but only in the same assembly(project). Therefore, if we try to access it from another assembly, we will get an error.


2. What is the difference between the static, const, and readonly keywords when applied to
a type member?

Constant and ReadOnly keyword is used to make a field constant which value cannot be modified.
The static keyword is used to make members static that can be shared by all the class objects.
Only the class level fields or variables can be constant.
Readonly fields can be initialized at declaration or in the constructor.
ReadOnly is a runtime constant. Const is a compile time constant. The value of readonly field can be changed. The value of the const field can not be changed.
Static members can only be accessed within the static methods. The non-static methods cannot access static members.

3. What does a constructor do?

A constructor is a special method of a class or structure in object-oriented programming that initializes a newly created object of that type. Whenever an object is created, the constructor is called automatically.

A constructor is like an instance method that usually has the same name as the class, and can be used to set the values of the members of an object, either to default or to user-defined values. 
However, although it resembles it, a constructor is not a proper method since it doesn’t have a return type. 
Instead of performing a task by executing code, the constructor initializes the object, and it cannot be static, final, abstract, and synchronized.

Constructors are not called explicitly and are invoked only once during their lifetime. In the case of a hierarchy of classes where a derived class inherits from a parent class, the execution sequence of the constructor is a call to the constructor of the parent class first and then that of the derived class. Constructors cannot be inherited.

Users do not need to write constructors for every class. A constructor can be declared using any of the access modifiers. It is mandatory to have a constructor with the right access modifier.

However, the compiler supplies a default if an access modifier is not defined in the class and a constructor is not declared. This default constructor cannot be found inside the source code since it’s found in the .class file. Its behavior depends on the language.

If a constructor is declared as private, the class cannot be created or derived and hence cannot be instantiated. Such a constructor, however, can be overloaded with different sets of parameters.

// 1. is a special method which shares the same name of the class and doesn't have any return type
// 2. constructor is used to create an object of the class and initialize class members
// 3. if there is no constructor in the class, the compiler will provide us a default constructor, and it's parameter-less
// 4. if we create any constructor ourselves, the default constructor will be replaced
// 5. constructor can be overloaded
// 6. constructor cannot be inherited, so a constructor cannot be overriden
// 7. by default derived class constructor will make a call to a base class constructor



4. Why is the partial keyword useful?

A partial class is a special feature of C#. It provides a special ability to implement the functionality of a single class into multiple files and all these files are combined into a single class file when the application is compiled. A partial class is created by using a partial keyword.
With partial classes, we can spread the definition of a class over multiple files. 
With the help of partial classes, multiple developers can work simultaneously in the same class in different files.
With the help of a partial class concept, you can split the UI of the design code and the business logic code to read and understand the code.
When you were working with automatically generated code, the code can be added to the class without having to recreate the source file like in Visual studio.
You can also maintain your application in an efficient manner by compressing large classes into small ones.

5. What is a tuple?

A tuple is a data structure that contains a sequence of elements of different data types. It can be used where you want to have a data structure to hold an object with properties, but you don't want to create a separate type for it.


(double, int) t1 = (4.5, 3);
Console.WriteLine($"Tuple with elements {t1.Item1} and {t1.Item2}.");
// Output:
// Tuple with elements 4.5 and 3.

(double Sum, int Count) t2 = (4.5, 3);
Console.WriteLine($"Sum of {t2.Count} elements is {t2.Sum}.");
// Output:
// Sum of 3 elements is 4.5.


6. What does the C# record keyword do?

C# 9 introduces records, a new reference type that you can create instead of classes or structs. C# 10 adds record structs so that you can define records as value types. Records are distinct from classes in that record types use value-based equality. 


7. What does overloading and overriding mean?
 
Overloading occurs when two or more methods in one class have the same method name but different parameters. 
Overriding occurs when two methods have the same method name and parameters.
overloading is compile time polymorphism
overriding is rum-time polymorphism
polymorphism: many forms
// 1. method overriding: happens between base class and derived class, same method signature(accesss modifier, method name, same input parameters), derived classes can have different implementations for the same methods
// 2. method overloading: we have multiple methods in the same class, same method name, but different parameter lists


8. What is the difference between a field and a property?

A field is a variable of any type that is declared directly in a class.	
A property is a member that provides a flexible mechanism to read, write or compute the value of a private field.
 Usage
A field can be used to explain the characteristics of an object or a class.	
A property can be used to set and receive values of a field.

9. How do you make a method parameter optional?


Use Parameter arrays
Default parameter
Use OptionalAttribute
Method Overloading


10. What is an interface and how is it different from abstract class?

abstract class: we cannot create any objects, cannot be instantiated, but we can contain both abstract and concrete methods. 
As long as one abstract method, the class should be abstract class.

interface is a collection of methods which are by default abstract and public, and will be implemented by the derived class.
one class can implements multiple interfaces
interface can not be instantiated
interface is helpful in writing loosely coupled code

Abstract class vs. Interface:
1. Abstract class provides a base class to its subclasses -- clear class hierachy 
   Interface define common behaviors or functionalities that can be implemented by a class -- contract
2. One class can only inherit from one (abstract) class, but one class can implement multiple interfaces
3. Methods in abstract class can be abstract methods or non-abstract methods, but methods in interfaces are by default abstract

11. What accessibility level are members of an interface?

 internal access



12. True/False. Polymorphism allows derived classes to provide different implementations of the same method.

True

13. True/False. The override keyword is used to indicate that a method in a derived class is providing its own implementation of a method.

False

14. True/False. The new keyword is used to indicate that a method in a derived class is providing its own implementation of a method.

False

15. True/False. Abstract methods can be used in a normal (non-abstract) class. 

False

16. True/False. Normal (non-abstract) methods can be used in an abstract class. 

True

17. True/False. Derived classes can override methods that were virtual in the base class. 

True

virtual methods: can have an implementation and provide the derived classes with the OPTION of overriding it

18. True/False. Derived classes can override methods that were abstract in the base class.

True

19. True/False. In a derived class, you can override a method that was neither virtual non abstract in the base class.

True

20. True/False. A class that implements an interface does not have to provide an implementation for all of the members of the interface.

False.


21. True/False. A class that implements an interface is allowed to have other members that
aren’t defined in the interface.

True

22. True/False. A class can have more than one base class.

24. True/False. A class can implement more than one interface.
Working with methods



1. Let’s make a program that uses methods to accomplish a task. Let’s take an array and
reverse the contents of it. For example, if you have 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, it would
become 10, 9, 8, 7, 6, 5, 4, 3, 2, 1.
To accomplish this, you’ll create three methods: one to create the array, one to reverse the
array, and one to print the array at the end.
Your Mainmethod will look something like this:
static void Main(string[] args) {
int[] numbers = GenerateNumbers();
Reverse(numbers);
PrintNumbers(numbers);
}
The GenerateNumbersmethod should return an array of 10 numbers. (For bonus points,
change the method to allow the desired length to be passed in, instead of just always
being 10.)
The PrintNumbersmethod should use a foror foreachloop to print out each item in the
array. The Reversemethod will be the hardest. Give it a try and see what you can make
happen. If you get
stuck, here’s a couple of hints:
Hint #1:To swap two values, you will need to place the value of one variable in a temporary
location to make the swap:
// Swapping a and b.
int a = 3;
int b = 5;
int temp = a;
a = b;
b = temp;
Hint #2:Getting the right indices to swap can be a challenge. Use a forloop, starting at 0
and going up to the length of the array / 2. The number you use in the forloop will be the
index of the first number to swap, and the other one will be the length of the array minus
the index minus 1. This is to account for the fact that the array is 0-based. So basically,
you’ll be swapping array[index]with array[arrayLength – index – 1].



2. The Fibonacci sequence is a sequence of numbers where the first two numbers are 1 and 1,
and every other number in the sequence after it is the sum of the two numbers before it. So
the third number is 1 + 1, which is 2. The fourth number is the 2nd number plus the 3rd,
which is 1 + 2. So the fourth number is 3. The 5th number is the 3rd number plus the 4th number: 2 + 3 = 5. This keeps going forever.
The first few numbers of the Fibonacci sequence are: 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, ...
Because one number is defined by the numbers before it, this sets up a perfect
opportunity for using recursion.
Your mission, should you choose to accept it, is to create a method called Fibonacci, which
takes in a number and returns that number of the Fibonacci sequence. So if someone calls
Fibonacci(3), it would return the 3rd number in the Fibonacci sequence, which is 2. If
someone calls Fibonacci(8), it would return 21.
In your Mainmethod, write code to loop through the first 10 numbers of the Fibonacci
sequence and print them out.
Hint #1:Start with your base case. We know that if it is the 1st or 2nd number, the value will
be 1.
Hint #2:For every other item, how is it defined in terms of the numbers before it? Can you
come up with an equation or formula that calls the Fibonaccimethod again?






Designing and Building Classes using object-oriented principles
1. Write a program that that demonstrates use of four basic principles of
object-oriented programming /Abstraction/, /Encapsulation/, /Inheritance/ and
/Polymorphism/.
2. Use /Abstraction/ to define different classes for each person type such as Student
and Instructor. These classes should have behavior for that type of person.
3. Use /Encapsulation/ to keep many details private in each class.
4. Use /Inheritance/ by leveraging the implementation already created in the Person
class to save code in Student and Instructor classes.
5. Use /Polymorphism/ to create virtual methods that derived classes could override to
create specific behavior such as salary calculations.
6. Make sure to create appropriate /interfaces/ such as ICourseService, IStudentService,
IInstructorService, IDepartmentService, IPersonService, IPersonService (should have
person specific methods). IStudentService, IInstructorService should inherit from
IPersonService.
Person
Calculate Age of the Person
Calculate the Salary of the person, Use decimal for salary
Salary cannot be negative number
Can have multiple Addresses, should have method to get addresses
Instructor


