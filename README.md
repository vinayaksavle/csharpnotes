# csharpnotes
C# revision notes

C# concepts

1. Data Types in C#

Value Data Type	- int, bool, char, double, float, etc.
Reference Data Type - string, class, object, interface, delegate, etc.
Pointer Data Type - Pointers.

2. C# Operators

- Arithmetic Operators
- Relational Operators
- Logical Operators
- Bitwise Operators
- Assignment Operators
- Operators Precedence
- C# Ternary Operator (?:)

3. Jump statements

- Break (Break statement is used to break or terminate the execution of loops)
- Continue (Continue statement is used to pass a control to the next iteration of loops)
- Goto (Goto statement is used to transfer a program control to the defined labeled statement)

4. C# Passing Parameters to Methods
- Pass by Value Parameters	(These are called as “input parameters” and these parameters will pass a copy of original value instead of original parameters. So the changes made to the parameters in called method will not have an effect on the original values when control returns to the caller.)

- Pass by Reference Parameters	(These are called as “input/output parameters” and these will pass a memory reference of original parameters. So the changes made to the parameters in called method will have an effect on the original values when control returns to the caller.)

- Output Parameters	(These are called as “output parameters” and these are more like reference type parameters but only difference is we don’t need to initialize it before passing.)

5. C# Params Keyword (This keyword is used to specify a method parameter that takes a variable number of arguments. The params keyword is useful when we are not sure about number of arguments to send as a parameter.)

6. C# Arrays
- Single-Dimensional Arrays
- Multi-Dimensional Arrays
- Jagged Arrays

7. C# Classes and Objects (The class in c# is nothing but a collection of various data members (fields, properties, etc.) and member functions. The object in c# is an instance of a class to access the defined properties and methods.)

8. C# Constructors (Constructor is a method which will invoke automatically whenever an instance of class or struct is created.  The constructor will have a same name as the class or struct and it useful to initialize and set a default values for the data members of the new object.)

- Default Constructor (If we create a constructor without having any parameters, then we will call it as default constructor and the every instance of class will be initialized without any parameter values.)

- Parameterized Constructor (If we create a constructor with at least one parameter, then we will call it as parameterized constructor and the every instance of class will be initialized with parameter values.)

- Copy Constructor (Copy Constructor is a parameterized constructor which contains a parameter of same class type. The copy constructor in c# is useful whenever we want to initialize a new instance to the values of an existing instance.) 

- Static Constructor (Static Constructor is used to perform a particular action only once throughout the application. If we declare a constructor as static, then it will be invoked only once irrespective of number of class instances and it will be called automatically before the first instance is created.)

- Private Constructor (Private Constructor is a special instance constructor and it is used in a classes that contains only static members. If a class contains one or more private constructors and no public constructors, then the other classes are not allowed to create an instance for that particular class except nested classes.)

Concepts in Constructor :
- C# Destructor ( In c#, Destructor is a special method of a class and it is used in a class to destroy the object or instances of classes. The destructor in c# will invoke automatically whenever the class instances become unreachable.)

- C# Constructor Overloading (In c#, we can overload the constructor by creating another constructor with same method name but with different parameters.)

- C# Constructor Chaining (Constructor Chaining is an approach to invoke one constructor from another constructor. To achieve constructor chaining we need to use this keyword after our constructor definition.)

- C# this Keyword (this keyword is used to refer the current instance of class and by using this keyword we can pass current instance of class as a parameter to the other methods.)

9. C# Static Keyword (static is a keyword or a modifier which is used to make a class or methods or a variable properties as not instantiable that means we cannot instantiate the items which we declared with a static modifier.)

10. Difference between const and readonly (The read only field values needs to be initialized either at the declaration or in a constructor of the same class unlike constant keyword in c#. If we use readonly keyword with fields, then those field values will be evaluated at the runtime.)

11. C# Structures Structs (structures are same as classes but only difference is classes are the reference types and structures are the value types. As a value type, the structures directly contain their value so their object or instance is stored on the stack and structures are faster than classes.)

12. C# Enum Enumerator (In c#, enum is a keyword which is used to declare an enumeration. In c#, enumeration is a type that consists a set of named constants as list.)

13. C# Properties (Property is an extension of class variable and it provides a mechanism to read, write or change the value of class variable without effecting the external way of accessing it in our applications.In object oriented programming languages like c# we need to define a fields as private, and then use properties to access their values in public way with get and set accessors.)

14. C# Partial Class ( Partial class is useful to split the functionality of particular class into multiple class files and all these files will be combined into one single class file when the application is compiled.)

15. C# Partial Method ( Partial method is a special type of method which will contain a declaration part in one partial class and the definition part in another partial class or in same partial class.)

16. C# String (used to represent a sequential collection of characters that is called a text and the string is an object of System.String type.)
Methods:
Split, Replace, Concat, Contains, Substring, Compare, Remove, Format, Equals, Clone, Copy (The main difference between string clone() and copy() method is, the copy method will create a new instance of specified string object with the same content but the clone method will not create a new instance, instead it will refer an existing instance of specified string object.), Trim Method (TrimStart, TrimEnd), Join, IndexOf, 

17. C# StringBuilder (StringBuilder is a class which is used to represent a mutable string of characters and it is an object of System.Text namespace.)
- Difference between string and StringBuilder (Strings are immutable and StringBuilder is mutable. Mutability means once an instance of class is created, then the same instance will be used to perform any operations like inserting, appending, removing or replacing the characters instead of creating a new instance for every time.)

18. C# Access Modifiers
- public	(It is used to specifies that access is not restricted.)
- private	(It is used to specifies that access is limited to the containing type.)
- protected	(It is used to specifies that access is limited to the containing type or types derived from the containing class.)
- internal	(It is used to specifies that access is limited to current assembly.)
- protected internal	(It is used to specifies that access is limited to the current assembly or types derived from the containing class.)
- private protected	(It is used to specifies that access is limited to the containing class or types derived from the containing class within the current assembly.)

19. C# Encapsulation (In c#, Encapsulation is a process of binding the data members and member functions into a single unit. In c#, class is the real time example for encapsulation because it will combine a various type of data members and member functions into a single unit.)

20. C# Abstraction (It is used to hide the implementation details and display only essential features of the object.)
Difference between Abstraction and Encapsulation

21. C# Inheritance (It is used to inherit the properties from one class (base) to another (child) class.the class whose members are inherited is called a base (parent) class and the class that inherits the members of base (parent) class is called a derived (child) class.)

22. C# Method Overloading (In c#, Method Overloading means defining a multiple methods with same name but with different parameters. By using Method Overloading, we can perform a different tasks with same method name by passing different parameters. Method Overloading is also called as compile time polymorphism or early binding.) 

23. C# Method Overriding (In c#, Method Overriding means override a base class method in derived class by creating a method with same name and signatures to perform a different task. The Method Overriding in c# can be achieved by using override & virtual keywords along with inheritance principle.Method Overriding is also called as run time polymorphism or late binding.)
Difference between Overloading and Overriding

- C# Virtual Keyword (Virtual keyword is used to override a base class members such as properties, methods, etc. in derived class to modify it based on our requirements.)

- C# Override Keyword (Override keyword is used to override a base class virtual members such as properties, methods, etc. in derived class to modify it based on our requirements.)

- C# Base Keyword (In c#, base keyword is used to access a base class members such as properties, methods, etc. in derived class.)

24. C# Polymorphism (Polymorphism means providing an ability to take more than one form)

Two different kind of polymorphisms
- Compile Time Polymorphism (Compile Time Polymorphism means defining a multiple methods with same name but with different parameters. By using compile time polymorphism, we can perform a different tasks with same method name by passing different parameters.)

- Run Time Polymorphism (Run Time Polymorphism means overriding a base class method in derived class by creating a similar function and this can be achieved by using override & virtual keywords along with inheritance principle.)

- C# Sealed Keyword (In c#, sealed is a keyword which is used to stop inheriting the particular class from other classes and we can also prevent overriding the particular properties or methods based on our requirements.)

25. C# Abstract (In c#, abstract is a keyword and it is useful to define a classes and class members that are needs to be implemented or overridden in a derived class.The members which we defined as abstract or included in an abstract class those must be implemented by a classes that derive from an abstract class.The abstract class cannot be instantiated and it can contain both abstract and non-abstract members.)

26. C# Interface (In c#, interface is same like class but only difference is class can contain both declarations and implementation of methods, properties and events but interface will contain only the declarations of methods, properties and events that a class or struct can implement. C# will not support multiple inheritance of classes but that can be achieved by using interface)

Difference between Abstract Class and Interface(The members of abstract class can contain different access modifiers. By default, all the members of interface are public and we are not allowed to include any other access modifiers.	)

27. C# Delegates (Delegate is a type that defines a method signature and it is useful to hold the reference of one or more methods which is having same signatures.)

Two different type of delegates
- Single Cast Delegates (A delegate which points to single method is called a single cast delegate and it is used to hold the reference of single method.)

- Multicast Delegates (A delegate that points to a multiple methods is called a multicast delegate and it is used to hold the reference of multiple methods with single delegate.Multicast delegates will work with only the methods which is having a void as return type. In case, if we want to create a multicast delegate with return type, then we will get a return type of last method in the invoking list. By using delegate we can pass a methods as parameter.)

28. C# Events (Event is a message which is sent by an object to indicate that particular action is going to be happen. The action could be caused either by button click, mouse movements or by some other programming logic. The object that raises an event is called event sender. In c#, events will follow the same pattern and it will contain a publisher, subscriber, notification and handler. The events will enable a class or object to notify other classes or objects when something of special happens. The class that sends (or raises) an event is called publisher and the class that receives (or handle) an event is called subscriber.In c#, the publisher will determines when an event is raised and the subscribers will determine what action can be taken in response to the event. An event in c# will have a multiple subscribers and the events that have no subscribers will never be raised. The subscriber can handle a multiple events from multiple publishers.)

29. Collections in C# (Collection is a class which is useful to manage a group of objects in a flexible manner to perform various operations like insert, update, delete, get, etc. on the object items in a dynamic manner based on our requirements.  Arrays in c# but those are useful only when we are working with fixed number of strongly-typed objects. So, to solve this problem Microsoft has introduced collections in c# to work with a group of objects which can grow or shrink dynamically based on our requirements.)

Type of collection classes :
- C# Non-Generic Collections (System.Collections)
Non-generic collection classes are useful to store an elements of different data types.
Different type of non-generic collection classes :
	-ArrayList	(It is useful to represent an array of objects whose size is dynamically increased as required.)
		* C# Arraylist Properties
			*Capacity-	It is used to get or set the number of elements an arraylist can contain.
			*Count-	It is used to get the number of elements in arraylist.
			*IsFixedSize-	It is used to get a value to indicate that the arraylist has fixed size or not.
			*IsReadOnly	-It is used to get a value to indicate that the arraylist is readonly or not.
			*Item-	It is used get or set an element at the specified index.
			*IsSynchronized-	It is used to get a value to inidicate that an access to arraylist is synchronized (thread safe) or not.
			
		* C# Arraylist Methods
			*Add	It is used to add an element at the end of arraylist.
			*AddRange	It is used to add all the elements of specified collection at the end of arraylist.
			*Clear	It will remove all the elements in arraylist.
			*Clone	It will create a shallow copy of arraylist.
			*Contains	It is used determine whether the specified element exists in arraylist or not.
			*CopyTo	It is used to copy all the elements of an arraylist into another compatible array.
			*GetRange	It is used to return a specified range of arraylist elements starting from the specified index.
			*IndexOf	It is used to search for a specified element and return a zero-based index if found otherwise return -1 if no element found.
			*Insert	It is used to insert an element in arraylist at the specified index.
			*InsertRange	It is used to insert all the elements of specified collection into arraylist starting from the specified index.
			*Remove	It is used to remove a first occurence of specified element from the arraylist.
			*RemoveAt	It is used to remove an element from arraylist based on the specified index position.
			*RemoveRange	It is used to remove a range of elements from arraylist.
			*Reverse	It reverse the order of arraylist elements.
			*Sort	It sorts the elements in an arraylist.
			*ToArray	It copies all the elements of an arraylist to new array object.
			
Difference between Array and ArrayList(To use an arraylist items, we need to cast it to appropriate data type but in array we don’t need to cast an elements because it’s a strongly type.)			
		
	-Queue	(It is useful to represent a FIFO (First in, First Out) collection of objects.)
		* C# Queue Properties
			*Count	It will return the total number of elements in queue
			*IsSynchronized	It is used to get a value to inidicate that an access to queue is synchronized (thread safe) or not.
			
		* C# Queue Methods
			*Enqueue	It is used to add an elements at the end of queue.
			*Dequeue	It will remove and returns an item from the starting of queue.
			*Clear	It will remove all the elements from queue.
			*Clone	It will create a shallow copy of queue.
			*Contains	It is used determine whether an element exists in queue or not.
			*Peek	It is used to get a first element from the queue.
			*TrimToSize	It is used set the capacity of queue to actual number of elements in the queue.
		
	-Stack	(It is useful to represent a LIFO (Last in, First Out) collection of objects.)
		* C# Stack Properties
			*Count	It will return the total number of elements in stack
			*IsSynchronized	It is used to get a value to inidicate that an access to stack is synchronized (thread safe) or not.
		
		* C# Stack Methods
			*Push	It is used to insert an object at the top of stack.
			*Pop	It will remove and return an object at the top of the stack.
			*Clear	It will remove all the elements from stack.
			*Clone	It will create a shallow copy of stack.
			*Contains	It is used determine whether an element exists in stack or not.
			*Peek	It is used to return a top element from the stack.
	
	-Hashtable	(It is useful to represent a collection of key/value pairs that are organized based on the hash code of the key. Hashtable is same as dictionary object but only difference is the dictionary object is used to store a key value pair of same data type elements.)
		* C# HashTable Properties
			*Count	It is used to get the number of key/value pair elements in hashtable.
			*IsFixedSize	It is used to get a value to indicate that the hashtable has fixed size or not.
			*IsReadOnly	It is used to get a value to indicate that the hashtable is readonly or not.
			*Item	It is used get or set the value associated with the specified key.
			*IsSynchronized	It is used to get a value to inidicate that an access to hashtable is synchronized (thread safe) or not.
			*Keys	It is used to get the collection of keys in the hashtable.
			*Values	It is used to get the collection of values in the hashtable.
			
		* C# HashTable Methods
			*Add	It is used to add an element with specified key and value in hashtable.
			*Clear	It will remove all the elements from hashtable.
			*Clone	It will create a shallow copy of hashtable.
			*Contains	It is used determine whether the hashtable contains a specific key or not.
			*ContainsKey	It is used determine whether the hashtable contains a specific key or not.
			*ContainsValue	It is used determine whether the hashtable contains a specific value or not.
			*Remove	It is used to remove an element with specified key from the hashtable.
			*GetHash	It is used get the hash code for the specified key.


- C# Generic Collections (System.Collections.Generic)
Generic collections will enforce a type safety so we can store only the elements which is having same data type. In c#, generic collections are the strongly typed objects so it will allow only same data type elements to store  and it doesn’t required any type casting (boxing and unboxing) while storing and retrieving an elements so performance will be improved.

Different type of generic collection classes :

	-List	(It is useful to represent a list of objects that can be accessed by index.List is same as an arraylist but only difference is arraylist is a non-generic type of collection so it will allow store an elements of different data types.)
	
	(List<T>) is an implementation of IList<T> interface so we can also use IList<T> interface to create an object of generic list (List<T>)
	IList<T> lst = new List<T>();

		C# List Properties
			*Capacity	It is used to get or set the number of elements a list can contain.
			*Count	It is used to get the number of elements in list.
			*Item	It is used get or set an element at the specified index.
			
		C# List Methods
			*Add	It is used to add an element at the end of the List.
			*AddRange	It is used to add all the elements of specified collection at the end of the List.
			*Clear	It will remove all the elements from the List.
			*Contains	It is used determine whether the specified element exists in the List or not.
			*CopyTo	It is used to copy entire List to compatiable one-dimensional array.
			*Find	It is used to search for an element that matches the conditions defined by the specified predicate and return the first occurrence of the List.
			*FindAll	It is used to retrieve all the elements that matches the conditions defined by the specified predicate.
			*ForEach	It is used to iterate through the List to access an elements.
			*Insert	It is used to insert an element into the List at the specified index.
			*InsertRange	It is used to insert all the elements of specified collection into List starting from the specified index.
			*Remove	It is used to remove the first occurence of specified element from the List.
			*RemoveAt	It is used to remove an element from the List based on the specified index position.
			*RemoveRange	It is used to remove a range of elements from the List.
			*Reverse	It reverse the order of List elements.
			*Sort	It sorts the elements in the List.
			*ToArray	It will copies the elements of List to new array object.
	
	
	-Queue	(It is useful to represent a FIFO (First in, First Out) collection of objects.)
	-Stack	(It is useful to represent a LIFO (Last in, First Out) collection of objects.)
	
	-SortedList<K,V>	(It is useful to represent a collection of key/value pairs that are sorted by a key.)
		
		C# SortedList Properties
			*Capacity	It is used to get or set the number of elements a sortedlist can contain.
			*Count	It is used to get the number of key/value pair elements in list.
			*Item[TKey]	It is used get or set the value associated with the specified key.
			*Keys	It is used get a collection of keys in sortedlist.
			*Values	It is used get a collection of values in sortedlist.
		
		C# SortedList Methods
			*Add	It is used to add an elements with specified key and value in SortedList<TKey, TValue>.
			*Clear	It will remove all the elements from SortedList<TKey, TValue>.
			*ContainsKey	It is used determine whether the specified key exists in the SortedList<TKey, TValue> or not.
			*ContainsValue	It is used determine whether the specified value exists in SortedList<TKey, TValue> or not.
			*IndexOfKey	It is used to get the index value of specified key stored in the SortedList<TKey, TValue>.
			*IndexOfValue	It is used to get the index value of specified value stored in the SortedList<TKey, TValue>.
			*Remove	It is used to remove an element from SortedList<TKey, TValue> with specified key.
			*RemoveAt	It is used to remove an element at the specified index position from SortedList<TKey, TValue>.
			*TryGetValue	It is used to get the value associated with the specified key.
	
	-Dictionary<K,V>	(It is useful to represent a collection of key/value pairs that are organized based on the key.)
		
		C# Dictionary Properties
			*Count	It is used to get the number of key/value pair elements in dictionary.
			*Item[TKey]	It is used get or set the value associated with the specified key.
			*Keys	It is used get a collection of keys in dictionary.
			*Values	It is used get a collection of values in dictionary.
			
		C# Dictionary Methods
			*Add	It is used to add an elements to dictionary object with specified key and value.
			*Clear	It will remove all the keys and values from the Dictionary<TKey, TValue>.
			*ContainsKey	It is used determine whether the specified key exists in Dictionary<TKey, TValue> or not.
			*ContainsValue	It is used determine whether the specified value exists in Dictionary<TKey, TValue> or not.
			*Remove	It is used to remove an element from Dictionary<TKey, TValue> with specified key.
			*TryGetValue	It is used to get the value associated with the specified key.
			
	-HashSet (HashSet<T>) (The hashset will provide a high performance set operations and the set will return only unique elements and those elements will not be in particular order. Even if we add a duplicate elements in hashset, it will return only the unique elements in result set.)

			
Difference between Dictionary and HashTable in C# (In foreach loop, we need to use DictionaryEntry property to get the key/value pair from hashtable but we need to use KeyValuePair property to access key/value pair elements from dictionary.When compared with dictionary object, the hashtable will provide a lower performance because the hashtable elements are of object type so the boxing and unboxing process will occur when we store or retrieve a values from hashtable.In c#, the hashtable will throw an error if we try to find a key which does not exists but the dictionary object will return null in case the defined key not exists.)

- C# Concurrent Collections (System.Collections.Concurrent)
Concurrent collections are useful to access a collection items from multiple threads and these are available from .NET Framework 4 .
Different type of concurrent collection classes :
	-BlockingCollection	(It is useful to provide a blocking and bounding capabilities for thread-safe collections.)
	-ConcurrentBag	(It is useful to represent a thread-safe, unordered collection of objects.)
	-ConcurrentDictionary<K,V>	(It is useful to represent a thread-safe collection of key/value pairs that can be accessed by multiple threads concurrently.)
	-ConcurrentQueue	(It is useful to represent a thread-safe FIFO (First in, First Out) collection.)
	-ConcurrentStack	(It is useful to represent a thread-safe LIFO (Last in, First Out) collection.)
	-Partitioner	(It is useful to provide a partitioning strategies for arrays, lists, enumerables.)
	-OrderablePartitioner	(It is useful to provide a specific way of splitting an orderable data source into multiple partitions.)
	
30. Generics in C# (generic is a type which is used to define a class, structure, interface or method with a placeholders (type parameters) to indicate that they can store or use one or more of the types. In c#, the compiler will replace a placeholders with the specified type at compile time.)

- We can use generic class as base class, but we need to provide a type instead of type parameter for the base class because there is no way to send a required type argument to instantiate a base class at run time.
- If derived class is generic, then we don’t need to specify a type for generic base class instead we can use type parameter (T).

// No Error
class DClass1 : GenericClass<string> {
// implementation
}

// No Error
class DClass2<T> : GenericClass<T>{
// implementation
}

31. Generic Constraints in C# (If we want to restrict a generic class to accept only the particular type of placeholder, then we need to use Constraints.)
Constraints are specified by using where keyword.
where T : struct	The type argument must be a value type.
where T : unmanaged	The type of argument must not be a reference type.
where T : class	The type argument must be a reference type.
where T : new()	The type argument must have a public parameterless constructor.
where T : <base class name>	The type argument must be or derive from the specified base class.
where T : <interface name>	The type argument must be or implement the specified interface.
where T : U	The type argument supplied for T must be or derive from the argument supplied for U.

32. C# Exception (Exception is an unexpected event or an error which may occur during execution of the program and it will provide necessary information about the error which occurred in our application.) 

Properties of Exception
Data	This property will hold an arbitrary data in key-value pairs.
HelpLink	It will hold a help file URL that provides a detailed information about the cause of exception.
InnerException	This property will provide an information about the series of exceptions that might have occurred.
Message	It will provide the details about the cause of an exception.
Source	It will set or get the name of an application or object that causes the error.
StackTrace	It provide a stack trace to determine where an error occurred.

33. C# Exception Handling (To handle runtime or unexpected errors in applications, c# has provided a built-in exception handling support by using try, catch and finally blocks. finally block is useful to clean up any resources that are allocated in the try block.  In c#, the try block must always be followed by catch or finally or both blocks otherwise we will get a compile-time error.)


34. C# Var Keyword (To declare the implicitly typed local variables without specifying an explicit type and the type of local variables will automatically determine by the compiler based on the right side value of initialization statement.

var x = 50; // Implicitly typed

int y = 50; // Explicitly typed)

35. C# Dynamic Type(The new dynamic type has been introduced to bypass the type checking at compile-time instead, it will resolve the type at runtime. In c#, the dynamic type is same as implicitly typed local variable var but the only difference is the type checking will happen at runtime.  The compiler will compile the variables of dynamic type into the variables of object type but those are not resolved by the compiler during compile-time instead, those will be evaluated at run time. Actual type will be assigned to the dynamic variables at runtime based on the right side value of the initialization statement.)

36. C# Nullable Types (Nullable Types are useful to assign a null value to the value type variables. Generally, in c# if we try to assign a null value to the value type variables, then we will get a compile-time error.)
E.g. Nullable<int> x = 10;	int? y = 20;	bool? z = null;	Nullable<double> a = null;	int?[] arr = new int?[10];

37. C# Anonymous Types (Anonymous types are useful to create an object that contains a set of read-only properties without specifying its type using the new keyword. The name and type for the properties in anonymous type object will be generated by the compiler automatically.)
E.g. var userInfo = new { Id = 1, name = "Suresh", isActive = true };

The access scope of anonymous type is limited to the method where it has defined. In case, if we want to send the anonymous type to another method, then that method must accept the parameter of dynamic type but that is not recommended.

38. Anonymous Methods in C# (Anonymous methods are the methods without a name. Generally, the anonymous methods can be defined by using delegate keyword and can be assigned to the variable of the delegate type.)

39. C# Indexer (Indexer is a special type of property and that allows an instances of a class or structure to be indexed same like an array. Indexer is same as property but the only difference is, the indexer will define with this keyword along with the square bracket and parameters.)
Syntax:
[access_modifier] [return_type] this[parameter_type parameter_name]
{
    get
    {	// return specified index value    }
	set
	{	// set value at specified index	   }
}

40. C# Reflection (Reflection is useful to get the type information that describes assemblies, modules, members, parameters and other entities in the managed code by examining their metadata.)

41. IEnumerable in C# (IEnumerable is an interface and it is useful to enable an iteration over a non-generic collections)
42. C# Yield Keyword ( It is useful to indicate that the method, operator or property in which it appears is an iterator. The yield return statement will return one element at a time and the return type of yield keyword must be always IEnumerable or IEnumerator object of values. The yield break statement is useful to end the iteration.The yield return or yield break statements are not allowed to use in anonymous methods and in the methods that contain unsafe blocks.)

43. C# Regex (Regular Expression) (In c#, regular expression (regex) is a pattern and it is useful to parse and validate whether the given input text is matching the defined pattern (such as an email address) or not.)

44. C# String Interpolation ($)(String Interpolation is a feature which is used to embed any valid expression that returns a value into a string using $ operator. The string which is prepended with $ operator will call it as an interpolated string and this feature is available from c# 6.0.)

C# Multiline String Interpolation (In c#, the String Interpolation will support multiline or verbatim interpolated string which starts with ‘@’ character. To implement verbatim interpolated string, the string must starts with $ character followed by @ character.)

45. C# Extension Methods (Extension methods are useful to extend the behaviour of existing types by adding new methods without modifying, deriving or recompiling the original types such as class, struct or interface.)

46. C# Optional Parameters (The optional parameters have been introduced to specify the parameters as optional while defining the methods, indexers, constructors, and delegates.)

C# Named Parameters (The named parameters have been introduced to pass the method arguments with parameter name rather than with the method parameter’s position in the parameter list.
Generally, while calling the method we need to pass all the method arguments in the same sequence of parameters in the method definition. If we use named parameters, we don’t need to worry about the order or sequence of parameters while calling the method.)
E.g. GetDetails(id: 1, name: "Trishi", location: "Guntur");

47. C# Thread (Threading) (In c#, thread is a basic unit of execution within the process and it is responsible for executing the application logic. Every application or program will carry one thread to execute the application logic and that thread is called a Main thread.)

C# Thread Properties
	*CurrentContext	It will return the current context in which the thread is executing.
	*CurrentThread	It will return the currently running thread.
	*CurrentCulture	It is useful to get or set the culture for current thread.
	*CurrentUICulture	It is useful to get or set the Resource Manager current culture to look up culture-specific resources at run time.
	*IsAlive	It is useful to get the execution status of current thread.
	*IsBackground	It is useful to get or set a value which indicating whether the thread is background thread or not.
	*IsThreadPoolThread	It will return a value which indicate whether the thread belongs to the managed thread pool or not.
	*ManagedThreadId	It will return unique identifier of the current managed thread.
	*Name	It is useful to get or set the name of the thread.
	*Priority	We can get or set a value which indicate the schedule priority of a thread.
	*ThreadState	It is useful to get the state of current thread.
	
C# Thread Methods
	*Abort()	This method is useful to terminate the thread.
	*AllocateDataSlot()	It will allocates an unnamed data slot on all the threads.
	*AllocateNamedDataSlot()	It will allocates a named data slot on all threads.
	*BeginThreadAffinity()	It will notify a host that the managed code is about to execute the instructions that depend on the identity of current physical operating system thread.
	*EndThreadAffinity()	It will notify a host that the managed code has finished executing the instructions that depend on the identity of the current physical operating system thread.
	*Equals()	It will determine whether the specified object is equal to the current object or not.
	*Finalize()	It will ensures that the resources are freed and other cleanup operations are performed when the garbage collector reclaims the Thread object.
	*GetData()	It is useful to retrieve the value from the specified slot on the current thread.
	*GetDomain()	It will return the current domain in which the current thread is running.
	*GetHashCode()	It will return the hash code of current thread.
	*GetType()	It will return the type of current instance.
	*Interrupt()	It will interrupt a thread that is in the WaitSleepJoin thread state.
	*Join()	It will make the thread to finish its work or it will halt other threads until it finishes work.
	*Resume()	It will resumes a thread that has been suspended.
	*Sleep()	It will suspend the current thread for specified amount of time.
	*Start()	It will instruct the operating system to change the state of current instance to Running.
	*Suspend()	It will suspend the thread.
	*VolatileRead()	It will read the value of a field and that value is the latest written by any processor in a computer.
	*VolatileWrite()	It will write a value to the field immediately, so that the value will be visible for all processors in the computer.
	*Yield()	It will yield the execution to another thread that is ready to run on the current processor.
	
C# Thread Life Cycle
	*Unstarted	When we create the thread that will be in unstarted state.
	*Runnable	When we call the Start() method, the thread will be moved to ready to run or runnable state.
	*Running	It indicates that the thread is in running state.
	*Not Runnable	If thread is in not runnable state means there is a chance that the Sleep() or Wait() or Suspend() method is called on the thread or blocked by I/O operations.
	*Dead	If thread is in dead state means the thread completes its task execution or it is aborted.

Two types of threads :

- Foreground Threads (Foreground threads are the threads which will run until it finishes its work even if, the Main thread completes its process. So, the lifespan of foreground threads will not depend on the Main thread.)
- Background Threads (The background threads will quit its process immediately when Main thread quits. Here, the lifespan of background threads will depend on the Main thread.To make the thread as a background thread, we need to set IsBackground property to true for that thread.)

Multithreading in C# (Multithreading means executing the multiple threads simultaneously to perform multiple tasks at a time.)

C# Sleep (Thread Sleep) (Sleep method is useful to suspend or pause the current thread execution for the specified amount of time.)

C# Lock (Thread Lock) ( lock keyword is useful to acquire the mutual-exclusion of lock for the specified block of code to make sure that at a time only one thread can execute it.)

C# Timer (Timer component is useful to raise an event repeatedly in our application based on the specified interval of time.)

48. C# Task (task is useful to perform the operations asynchronously on a thread pool threads and it was introduced in .NET Framework 4.0.)

C# Task Properties 
	*CurrentId	It will provide the ID of currently executing Task.
	*Status	It will return the Task status.
	*IsCanceled	It will return a value that indicates whether the task cancelled or not.
	*IsCompleted	It will return a value that indicates whether the task completed or not.
	*IsFaulted	It will return a value that indicates whether the task stopped due to unhandled exception or not.
	*Factory	It provides an access to factory methods for creating and configuring Task.
	*Exception	It will return the exceptions that caused the Task to end prematurely.

C# Task Methods
	*ConfigureAwait()	We can configure to use await keyword to await the Task.
	*ContinueWith()	It is useful to create continuation of tasks.
	*Start()	It is useful to start the Task.
	*Run()	It will queues the specified work to run on the thread pool.
	*RunSynchronously()	It will the Task synchronously on the current TaskScheduler.
	*Delay()	It will create a task that completes after a specified number of milliseconds.
	*Wait()	It will make to wait for the Task to complete execution.
	*WaitAll()	It will make waits for all of the provided Task objects to complete execution.
	*WaitAny()	It will make waits for any of the provided Task objects to complete execution..
	*Dispose()	It will releae all the resources used by the current instance of the Task class.
	
49. C# Tuple (Tuple is a data structure and it is useful to store the sequence of elements of different data types. By using tuple we can return more than one value from the methods as a single set of data.Tuple class instance will directly support only 1 to 7 elements. But The Create method will directly support the creation of a tuple object from 1 to 8 elements.We can access the tuple object elements with Item<positionNumber> properties. For example, the first element can be accessed like Item1, the second element can be accessed like Item2, and so on based on our requirements.)

C# ValueTuple (In c#, ValueTuple is same as Tuple to store the sequence of elements of different data types but the only difference is ValueTuples are the value types (structures) rather than reference types (classes) like Tuple and it will overcome the limitations of Tuple class.ValueTuple will support more than 8 elements.)


50. LINQ C# (LINQ means Language Integrated Query and it was introduced in .NET Framework 3.5 to query the data from different data sources such as collections, generics, XML documents, SQL databases, etc. in both C# and VB.NET based on our requirements.)

LINQ, we can write the queries in two ways.

- Using Query Syntax 
from <variable> in <collection>
<where, joining, grouping, operators etc.> <lambda expression>
<select or groupBy operator> <format the results>

Using Method Syntax
int[] Num = { 1, 2, 3, 4, 5, 6, 7, 8, 9 };
//LINQ Method Syntax to Print Numbers Greater than 3
IEnumerable<int> result = Num.Where(n => n > 3).ToList();

51. C# Func Delegate (Func is a built-in generic delegate and it is useful to hold the reference of one or more methods which is having same method signature without declaring any custom delegate object.)

52. C# Action Delegate (Action is a built-in generic delegate same like Func delegate to hold the reference of one or more methods but the only difference is the Action delegate will not return any value.)

53. C# Predicate Delegate ( Predicate is a built-in generic delegate and it is useful to validate whether the input parameter meets the specified condition or not and it’s same like Func and Action delegates to hold the reference of one or more methods.)





	
















 

