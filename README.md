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


5. Why is the partial keyword useful?
6. What is a tuple?
7. What does the C# record keyword do?
8. What does overloading and overriding mean?
9. What is the difference between a field and a property?
10. How do you make a method parameter optional?
11. What is an interface and how is it different from abstract class?
12. What accessibility level are members of an interface?
13. True/False. Polymorphism allows derived classes to provide different implementations
of the same method.
13. True/False. The override keyword is used to indicate that a method in a derived class is
providing its own implementation of a method.
14. True/False. The new keyword is used to indicate that a method in a derived class is
providing its own implementation of a method.
15. True/False. Abstract methods can be used in a normal (non-abstract) class. 16.
True/False. Normal (non-abstract) methods can be used in an abstract class. 17. True/False.
Derived classes can override methods that were virtual in the base class. 18. True/False.
Derived classes can override methods that were abstract in the base class. 19. True/False.
In a derived class, you can override a method that was neither virtual non abstract in the
base class.
20. True/False. A class that implements an interface does not have to provide an
implementation for all of the members of the interface.
21. True/False. A class that implements an interface is allowed to have other members that
aren’t defined in the interface.
22. True/False. A class can have more than one base class.
23. True/False. A class can implement more than one interface.
Working with methods
1. Let’s make a program that uses methods to accomplish a task. Let’s take an array and
reverse the contents of it. For example, if you have 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, it would
become
