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

select count(1) from tbl_ToDosUsageTracking where activityid in (6,13) and activitydate  > ()
from thenmozhi (privately):
select count(1) from tbl_ToDosUsageTracking where activityid in (9,10,11,12) and activitydate  > ()


Cloudmoyo
Design patterns used
Exp on .Net Core
where do we register DI and how to add
Actions performed in Controller  
How you manage connectionstring for dev, sit, uat, prod
.Net core where can we host kestrel, iis
Describe Abstract , Interface where can we use
Abstraction and Encapsulation
Practical example of Abstraction

What is component
What contains in Component
Directive and its type , how will you crate custom directive, have you created custom directive in your project
Pipe
Role of model in your project
To display list of employees, create, update, implementation of that


Gateway
.Net Core different from other framework
Authorization in .NetCore
What is json
constant vs static 
sealed class
extension methods
string interpolation
interface vs abstraction
method overriding

Difference between first and firstordefault
left join in linq query
can I have the method in derived class of same but different parameters can we override that method

Component
Services in Angular
Parent to Child
Child to Parent
Authorization in Angular
How to restrict the user from authenticating/ access
inner join vs left join
where we use char and nchar
primary key in SQL can it be null
foreign key can it be null
how to check whether value isnull in where condition

UST Global
Angular Lifecycle, which one will call at the end of lifecycle,  why to use ngOnDestroy
parent to child, child to parent, cross component
Custom library, or packages
Custom Pipes, What is Pipe
Directive, Example of Attribute Directive
Component vs Directive
What is Observable, normal method and observable method difference.
Observable vs Promises
What is AOT
How will you pas data from one component to other component
What is AuthGuards
What is Resolver in AuthGuards, resolver in routing
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
