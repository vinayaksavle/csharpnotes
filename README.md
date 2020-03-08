Interview questions to be revised:

1. Promise vs Observable
Promises are eager, Observables are lazy.Function passed to Observable constructor gets called only when someone actually subscribes to an Observable.
With a Promise you can only handle one event.
With an Observable you can handle multiple events.
.subscribe() is similar to .then(). 
An Observable can do everything that a Promise can do, plus more.
Use Angular’s HttpClient to handle API calls.
The Angular framework uses a lot of RxJS.


E.g.
* Promise
Promise is always resolved with the first value passed to the resolve function and ignores further calls to it.
const numberPromise = new Promise((resolve) => {
    resolve(5);
    resolve(10);
});

numberPromise.then(value => console.log(value));
// still prints only 5

*Observables
On the contrary, Observables allow you to resolve (or, as we say, “emit”) multiple values. Here is how it would look.
const numberObservable = new Observable((observer) => {
    observer.next(5);
    observer.next(10);
});

numberObservable.subscribe(value => console.log(value));
// prints 5 and 10


2. State Management in Angular v2+
https://medium.com/olricdigital/introduction-to-state-management-in-angular-v2-ef6f5144bade

- “State” term includes both the state of UI and the state of variables in your code. So any change in your application changes the state.
In Angular or other modern JS frameworks, each component has its own state and a component has no idea about the other components’ states unless we make enable the data flow between components. We use @Input and @Output decorators to pass information between parent and child components in Angular v2+.

- It is easy to pass information between components in simple apps. But it gets complicated and painful when you have complex app architecture. Let’s think about how to pass data between Component 2 and Component 6. If you use @Input/@Output it takes 4 hops to get Component 6 from Component 2 and the you should involve the other 3 components in this process.

- We should mention about Redux at this point. Redux is an elegant solution architecture which simplifies the state management.
There are three core principles in Redux architecture:

	*Single Store: state of the application should be stored in a single “store”. Store is the only responsible in providing data to components. Data flows between component and Store instead of component-to-component.

	*Read-only state: state should be read-only or immutable. To change the state, new action should be emitted.

	*Pure function reducers: Reducers take the current state and an action and return next state. Reducers should not take any other parameters outside the function.
	
- Another important point of Redux is that all data in the application flows only one-way, in other words data flow is unidirectional.
	*Component dispatches an action
	*Reducer in the store takes the action and produces a new state
	*New state pass to the component from Store.
	
- @ngrx/store
@ngrx/store is a state management extension for Angular applications inspired by Redux. It imports all core concepts from Redux. From now on, we will use @ngrx/store terms instead of Redux.

- Store
Store is the core structure where actions, reducers and state are located. The store receives actions as inputs, and transmit actions to reducers. Reducers produce a new state depending on the action and emit the new state. The store holds the new state until it changes via another action.

- Action
An action consists of two parts, type and payload. Type is required to make reducer enable to distinguish the actions. Therefore type must be unique for each action.

-Selector: Selector is a function used for obtaining a part of the state from the store.

- Reducer
The reducer is the core element in the tore and it is the responsible for changing the state. A reducer takes action and current state as input parameters and returns a new state according to the function inside it.
(The state is immutable in Redux architecture, so the reducer does not mutate the state but produces a new one.)
It gets more meaningful to implement @ngrx/store in your Angular app when the application goes complex.

3. Stored Procedure vs Select queries.
In SQL Profiler if you observe In select queries, it will first insert the cache (CacheInsert) and when you change parameter in where condition it will again and again creating CacheInsert. But stored procedure at first will create CacheInsert but later on it will use that cache data using CacheHit Event class. So thats why SP is faster than normal SQL query.


3. C# Abstract class constructor with Real Time Example
An abstract class can have a constructor, even though abstract class cannot be instantiated. 
when we create an object of a derived class then constructor of abstract base class is implicitly called, even though we cannot instantiate an abstract class. For example in program, if we create object of derived class then abstract base class constructor will also be called.

abstract class A
{
    protected A() {Console.WriteLine("Abstract class constructor"); }
}
//Derived class
class B : A
{
   public B() {Console.WriteLine("Derived class constructor"); }
}

class Program
{
    static void Main(string[] args)
    {
        B obj = new B();
    }
}

Output:
Abstract class constructor
Derived class constructor

4. Columnstore Indexes?
 Row store does exactly as the name suggests – stores rows of data on a page – and column store stores all the data in a column on the same page. Rowstores are better at random reads and random writes. Columnstores are better at sequential reads and sequential writes.
 
When to use NoLocks?
When update or insert operation happening on table but you want to select records from that table, use nolock to fetch records which are not commited
Issues with NOLOCK
We mentioned above how you can get dirty reads using the NOLOCK hint. These are also other terms you may encounter for this hint.

Dirty Reads - this occurs when updates are done, so the data you select could be different.
Nonrepeatable Reads - this occurs when you need to read the data more than once and the data changes during that process
Phantom Reads - occurs where data is inserted or deleted and the transaction is rolled back. So for the insert you will get more records and for the delete you will get less records.

Index Scan:
Since a scan touches every row in the table, whether or not it qualifies, the cost is proportional to the total number of rows in the table. Thus, a scan is an efficient strategy if the table is small or if most of the rows qualify for the predicate.

Index Seek:
Since a seek only touches rows that qualify and pages that contain these qualifying rows, the cost is proportional to the number of qualifying rows and pages rather than to the total number of rows in the table.
If there is no index, then you might see a Table Scan (Index Scan) in the execution plan.
Index seeks are generally preferred for the highly selective queries. What that means is that the query is just requesting a fewer number of rows or just retrieving the other 10 (some documents says 15 percent) of the rows of the table.
In general query optimizer tries to use an Index Seek which means that the optimizer has found a useful index to retrieve recordset. But if it is not able to do so either because there is no index or no useful indexes on the table, then SQL Server has to scan all the records that satisfy the query condition.

5. IEnumerable Vs IQueryable
IEnumerable
System.Collections Namespace
No base interface	
Lazy Loading Not Supported
While querying data from database, IEnumerable executes select query on server side, load data in-memory on client side and then filter data. Hence does more work and becomes slow.
Suitable for LINQ to Object and LINQ to XML queries
IEnumerable is suitable for querying data from in-memory collections like List, Array and so on.
 	

IQueryable
System.Linq Namespace
Derives from IEnumerable
Lazy Loading Supported
While querying data from database, IQueryable executes select query on server side with all filters. Hence does less work and becomes fast.
Suitable for LINQ to SQL queries
IQueryable is suitable for querying data from out-memory (like remote database, service) collections.


6. Where do we register DI and how to add Dependency Injection
Dependency injection is the design pattern that allow us to inject the dependency to the class from outer world rather than creating with in class. This will help us to create loosely coupled application so that it has provided greater maintainability, testability and also reusability. There is a built-in support of dependency injection in ASP.net Core. This supports is not limited to middleware, but also support in Controllers, views, and model as well. There are three easy step to use Dependency injection into ASP.net core MVC application.

-Create the service
-Register the service into ConfigureService method of the startup class, so that it available to use
-Inject the service where you want to use
-ASP.net core allow us to specify the lifetime for registered services based on our requirement to use the service. The service can either register as Singleton, Transient or Scoped.

7. Model vs ViewModel
Model: Strictly looks and feels like your data model. For all intents and purposes it is only a class representation of your data model. It has no knowledge of your View or any elements within your View. That said, it should not contain any attribute decorators (ie; Required, Length, etc.) that you would use for your View.

View Model: Serves as a data-binder between your View and your Model and in many cases, is also a wrapper for your Model. It would be rendered useless without the View, so it typically isn't reusable across multiple Views and Controllers like a standard Model is.

8. When to use HTTPGET, POST, PUT, DELETE
You can practically use a POST to do all the CRUD operations but you shouldn't. Because Each HTTP verb has its own responsibility. A GET is supposed to be idempotent and safe. A GET can be cached and in a browser, refreshed again and again. Ideally, firing a GET request shouldn't change the data. If HttpGet method can delete, can insert, can update and also can return value then why we use HttpPort, HttpPut and HttpDelete?

Imagine a scenario.
You have a Web API method which adds a new entry to the database using GET. If your GET request becomes a link and it gets crawled by a search engine. You will have your database full of duplicate data. So it makes sense to use POST in this case.

Selecting The Appropriate Method

GET - requests data from the resource and should not produce any side effect.
POST - method requests the server to create a resource in the database, mostly when a web form is submitted. Post is non-idempotent which means multiple requests will have different effects.
PUT - method requests the server to update a resource or create the resource, if it doesn’t exist. Put is idempotent which means multiple requests will have the same effects.
DELETE - method requests that the resources, or its instance, should be removed from the database.

POST vs PUT

POST and PUT are very similar in that they both send data to the server that the server will need to store somewhere. if you make the same request twice using PUT, with the same parameters both times, the second request will have no effect. This is why PUT is generally used for the Update scenario.

There are some more limitations for different Http verbs as well.

GET parameters are passed as part of the URL, which is of small and limited length of 256 chars by default, with some servers supporting 4000+ chars. If you want to insert a long record,you'll have to use POST. Post is considered limitless but there are limitations which vary according to browsers.
GET is re-executed if a user presses a Back button in a browser. Post doesn't.
GET is cached by browsers, nodes in the network, Internet Service Providers.
Unless the content changes, GET to the same URL must return same results to all the users or else you won't have any trust what so ever in the returned result. etc

9. How you manage connectionstring for dev, sit, uat, prod
In Startup file by using IHostingEnvironment we can set IsDevelopment, IsProduction, IsStaging

10. Why to use WebApi if we can return through MVC also
Web API Controllers can be created and hosted in any ASP.NET Application, not just MVC applications. Thus, an obvious reason to create a Web API is if you do not have an MVC front-end (e.g. classic, RESTful web-services hosted by your company/organization.)Almost all MVC Controllers are implemented with the View in mind.

11. What is component, What contains in Component
Components are like the basic building block in an Angular application. Components are defined using the @component decorator. A component has a selector, template, style and other properties, using which it specifies the metadata required to process the component. Compnent is custom tag like how html contains input, form tag. The specific type of directive that allows us to utilize web component functionality - encapsulated, reusable elements available throughout our application. Component is a directive with a view or template.

12. Directive and its type , how will you crate custom directive, have you created custom directive in your project 
Directives is used to add behavior to an existing DOM element. Directive is use to design re-usable components. Directives don’t have View. You can’t define Pipes in directive.

Component vs Directive
For register component we use @Component meta-data annotation.For register directives we use @Directive meta-data annotation.
Component is a directive which use shadow DOM to create encapsulate visual behavior called components.  Components are typically used to create UI widgets.Directives is used to add behavior to an existing DOM element.
Component is used to break up the application into smaller components.Directive is use to design re-usable components.
Only one component can be present per DOM element.Many directive can be used in a per DOM element
@View decorator or templateurl template are mandatory in the component.Directives don’t have View.
Component is used to define pipes. You can’t define Pipes in directive.

13. 
Single() - There is exactly 1 result, an exception is thrown if no result is returned or more than one result. 
SingleOrDefault() – Same as Single(), but it can handle the null value.

First() - There is at least one result, an exception is thrown if no result is returned.
FirstOrDefault() - Same as First(), but not thrown any exception or return null when there is no result.

Single() asserts that one and only one element exists in the sequence.
First() simply gives you the first one.

Use Single / SingleOrDefault() when you sure there is only one record present in database or you can say if you querying on database with help of primary key of table.
Developer may use First () / FirstOrDefault() anywhere,  when they required single value from collection or database.

Single() or SingleOrDefault() will generate a regular TSQL like "SELECT ...".
The First() or FirstOrDefault() method will generate the TSQL statment like "SELECT TOP 1..."

14. map, set 
Map is a new data structure introduced in ES6 which lets you map keys to values without the drawbacks of using Objects.
let map = new Map();
map.set("A",1);
map.set("B",2);
map.set("C",3);

Sets are a bit like maps but they only store keys not key–value pairs.
let set = new Set();
set.add('APPLE');
set.add('ORANGE');
set.add('MANGO');

15. 
Delegates - Delegate is a type that defines a method signature and it is useful to hold the reference of one or more methods which are having the same signatures.
By using delegates, you can invoke the methods and send methods as an argument to other methods.
E.g. <access_modifier> delegate <return_type> <delegate_name>(<parameters>)
    public delegate void SampleDelegate(int a, int b);
	SampleDelegate dlgt = m.Add;

Func - Func is a built-in generic delegate and it is useful to hold the reference of one or more methods which is having the same method signature without declaring any custom delegate object.
E.g. public delegate TResult Func<in T,out TResult>(T arg);
            Func<int, int, int> dlgt = Add;

Action - Action is a built-in generic delegate same as Func delegate to hold the reference of one or more methods but the only difference is the Action delegate will not return any value. 
E.g. public delegate void Action<in T1, in T2>(T1 arg1, T2 arg2);

Predicate - Predicate is a built-in generic delegate and it is useful to validate whether the input parameter meets the specified condition or not and it’s same as Func and Action delegates to hold the reference of one or more methods.
E.g. public delegate bool Predicate<in T>(T arg);

16. 
What is an Observable
Observable converts the ordinary stream of data into an observable stream of data. It observes the stream of data and emits the value, complete or error signals to the consumers of the stream. You can think of Observable it as a wrapper around the stream of data. Observables are declarative. You define an observable function just like any other variable. The observable function executes only when someone subscribes to it.

Who are observers (subscribers)
The Observable on its own is useless unless someone consumes the value delivered by the observable. We call them observers or subscribers. The observable communicates with the observers using callbacks. The observer must subscribe with the observable to receive the value from the observer. While subscribing it optionally passes the three callbacks. next(), error() & complete().

The observable invokes the next() callback whenever the value arrives in the stream. It passes the value as the argument to the next callback. If the error occurs, then the error() callback is invoked. It invokes the complete() callback when the stream completes.

Observable creation functions
1. Create - The Create method is one of the easiest. The create method calls the observable constructor behind the scene. Create is a method of the observable object, Hence you do not have to import it. The Create method calls the constructor behind the scene.

2. Of Operator - The Of creates the observable from the arguments that you pass into it. You can pass any number of arguments to the Of. Each argument emitted separately and one after the other. It sends the Complete signal in the end. Accepts variable no of arguments. emits each argument as it is without changing anything		
E.g. ngOnInit() {
  const array=[1,2,3,4,5,6,7]
  const obsof1=of(array);
  obsof1.subscribe(val => console.log(val),
           error=> console.log("error"),
          () => console.log("complete"))
 
}
 
**** Output ***
[1, 2, 3, 4, 5, 6, 7]
complete

3. From Operator - From Operator takes only one argument that can be iterated and converts it into an observable.Accepts only one argument. iterates over the argument and emits each value.

17. Observable vs Promises
Promise emits a single value while Observable emits multiple values. So, while handling a HTTP request, Promise can manage a single response for the same request, but what if there are multiple responses to the same request, then we have to use Observable. Yes, Observable can handle multiple responses for the same request. But, promise returns the very first value and ignore the remaining values whereas Observable return all the value. Promise is not lazy while Observable is lazy. Observable is lazy in nature and do not return any value until we subscribe. Observable is cancellable in nature by invoking unsubscribe() method, but Promise is not cancellable in nature.

18. What is AOT vs JIT
JIT generates JavaScript however, AoT usually generates TypeScript.
* JIT - Compile TypeScript just in time for executing it.
Compiled in the browser.
Each file compiled separately.
No need to build after changing your code and before reloading the browser page.
Suitable for local development.

* AOT - Compile TypeScript during build phase.
Compiled by the machine itself, via the command line (Faster).
All code compiled together, inlining HTML/CSS in the scripts.
No need to deploy the compiler (Half of Angular size).
More secure, original source not disclosed.
Suitable for production builds.

19. constant vs static vs readonly
* Constant

Constant fields are defined at the time of declaration in the code snippet, because once they are defined they can't be modified. By default a constant is static, so you can't define them static from your side. It is also mandatory to assign a value to them at the time of declaration otherwise it will give an error during compilation of the program snippet. That's why it is also called a compile-time constant.
E.g.
void Sum(int j)  
{  
const int i = 9, k = 2;  
const int A = i + k;  
} 
Output: 11

Explanation
The preceding code snippet will produce a result of 11, without showing any error since we already declared it at the initial point of declaration.
What if, we make some changes in the code above, such as:

void Sum(int j)  
{  
   const int i = 9, k = 2;  
// const int A = i + k;  
   Const int B = i + j;  
} 
Explanation
This code snippet will take you toward a compile-time error, because there is no initialization, since it's evaluated at run time.

Points to Remember

Compile-time constant
Can't be declared static
Can't be modified or changed
Can be of any type of Access Modifier
Local scope
Needs to get initialized
Declared at the time of declaration

* Readonly
A Readonly field can be initialized either at the time of declaration or within the constructor of the same class. We can also change the value of a Readonly at runtime or assign a value to it at runtime (but in a non-static constructor only). For that reason a Readonly field is also called a run-time constant.

E.g.
class ReadOnly  
{  
   readonly int i;  
   public ReadOnly( )  
   {  
       i = 11;  
       Console.WriteLine(i);  
   }  
} 
Explanation
We can assign the value to an integer later in the snippet; this is possible when using the Readonly keyword. We can modify it too depending on the use.

Points to Remember

Run-time constant
It can be static
Global scope
Can be declared in the constructer class
Generally public

* Static

The static keyword is used to declare a static member. If we are declare a class as a static class then in this case all the class members must be static too. The static keyword can be used effectively with classes, fields, operators, events, methods and so on effectively.

Snippet

class ReadOnly  
{  
    static int i = 11;  
    public static void disp()  
    {  
        Console.WriteLine(i);  
    }  
} 
Output: 11

Explanation

This code will show no error and produce a result (11), since we declared its value to be static at the time of declaration. So we can access it depending on our use in the program.

Let's make some changes in the snippet and see what happens then.

class ReadOnly  
{  
    int i = 9;  
    public static void disp()  
    {  
        Console.WriteLine(i);  
    }  
} 
Explanation
This snippet will show an error, because we didn't declare a value for the static and we are trying to access it within a method. We can't do that.

Points to Remember

Can't be used with indexers
Works with constructors too
By default it is private
Can be parameterized or public too
If its applied to a class then all the class members need to be static


20. What is json
JSON stands for JavaScript Object Notation. JSON is a lightweight format for storing and transporting data. JSON is often used when data is sent from a server to a web page
JSON is "self-describing" and easy to understand.

21. Why static
Each object has its own set of member variables and all the member variables have a scope. If we want a variable to have the same value throughout all instances of the object then we can declare it as a static variable in our program. To manipulate and use the values of static variables we can also define a function as static. The keyword "static" means that only one instance of a given variable exists for a class. Static variables are used to define constants because their values can be retrieved by invoking the class without creating an instance of it. Static variables can be initialized outside the member function or class definition. Unlike other member variables, only one copy of the static variable exists in memory for all the objects of that class. Therefore, all objects share one copy of the static variable in memory.

22. What is AuthGuards
Auth-guard makes use of CanActivate interface and it checks for if the user is logged in or not. If it returns true, then the execution for the requested route will continue, and if it returns false, that the requested route will be kicked off and the default route will be shown.
https://www.c-sharpcorner.com/article/protecting-routes-with-auth-guard-in-angular-7/

23. 















Directive, Example of Attribute Directive
https://www.tektutorialshub.com/angular/angular-directives/
https://www.tektutorialshub.com/angular/angular-ngclass-directive/

What is Observable, normal method and observable method difference.



What is Resolver in AuthGuards, resolver in routing
Routing Flow with Resolver
User clicks the link.
Angular executes certain code and returns a value or observable.
You can collect the returned value or observable in constructor or in ngOnInit, in class of your component which is about to load.
Use the collected the data for your purpose.
Now you can load your component.
Steps 2,3 and 4 are done with a code called Resolver.
So basically resolver is that intermediate code, which can be executed when a link has been clicked and before a component is loaded.


Lazy Loading
what is Map
what is Filter
MergeMap and 
let vs const
uploading bulk data can we navigate to other component
Custom directive
ngModel we have used I have to check whether the value is entered or not, Reactive forms, How to validate model value, user clicks submit method you have to validate whether value is entered or not
How will you declare reactive forms
can we create multiple form form inside other form
what type of validation you are using
if I type something then what kind of validation you will use,  keypress event, how will you declare output

Why we use API
WebAPI is stateful or stateless
Attribute Routing
Verbs in WebAPI
What if we not declared HTTPVERBS can we access get, post
how will you restrict action method GET, POST
where do we register routes, RouteConfig
What are types response types from WebAPI, what webapi will return return types
exception occur in WebAPI what is status code of exception and exception
Entityframework version, mvc version


How to disable lazy loading
Check version difference in angular, C#
Queries of SQL, Top highest salaries
Web Security
Design patterns 
Stack Heap
Dependency Injection
Delegate func predicate action
CTE
Entityframework Queries join
How can you see plan seek and scan
OAuth
Debug vs release
covariance and contravarince
Why abstract and not concreate
WebAPI Middleware
Rownumber, PartitionBy, Rank, DenseRank
webAPI code using serializer
Question on finally block
Dispose
SQLDataAdapter
callback
class vs structure
Why value types in stack and reference types in heap














Role of model in your project
To display list of employees, create, update, implementation of that


Gateway

Authorization in .NetCore, Authorization in Angular
https://jasonwatmore.com/post/2019/10/16/aspnet-core-3-role-based-authorization-tutorial-with-example-api
https://jasonwatmore.com/post/2019/08/06/angular-8-role-based-authorization-tutorial-with-example








sealed class
extension methods
string interpolation
interface vs abstraction
method overriding

Difference between first and firstordefault
left join in linq query
can I have the method in derived class of same but different parameters can we override that method


Services in Angular
https://dzone.com/articles/what-is-a-service-in-angular-js-why-to-use-it


inner join vs left join
where we use char and nchar
primary key in SQL can it be null
foreign key can it be null
how to check whether value isnull in where condition

UST Global
Angular Lifecycle, which one will call at the end of lifecycle,  why to use ngOnDestroy
https://www.tektutorialshub.com/angular-tutorial/#component-life-cycle-hook
https://www.tektutorialshub.com/angular/angular-ngoninit-and-ngondestroy/

parent to child, child to parent, cross component
https://www.tektutorialshub.com/angular/angular-passing-data-child-component/

Custom library, or packages

Custom Pipes, What is Pipe
https://www.tektutorialshub.com/angular/angular-custom-pipes/




Http GET, POST
https://www.djamware.com/post/5b87894280aca74669894414/angular-6-httpclient-consume-restful-api-example
 



Cloudmoyo

-Abstraction and Encapsulation, Practical example of Abstraction
https://www.tutlane.com/tutorial/csharp/csharp-abstraction


-Pipe
https://www.tektutorialshub.com/angular/angular-custom-pipes/












