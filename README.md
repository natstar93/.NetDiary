# .NET Diary

A timeline of topics covered in mentoring sessions and homework tasks

// TODO Add notes from old laptop for 1st half of the year

## 13/7/21

**Tasks:**
* Create an empty API with .NET Core 
* Come up with idea about what to do with it
* Learn about IOC Containers

**Progress:**

Created basic [PizzaShop API](https://github.com/natstar93/PizzaShop/commit/376853406344bb1e06064fea280e8b721b4a26d5) with GET endpoint that creates new PizzaOrders and displays them

Listed MVP ideas and future requirements on README

Read about IOC containers and dependency injection. It would be good to get started on a concrete example since it's all a bit abstract to me at the moment :) 

## 22/7/21

#### What are AddTransient, AddScoped, AddSingleton?

AddSingleton creates an instance of the service the first time it is requested then reuses this for each request thereafter.

AddScoped creates a new instance for each individual HTTP request, but requests to the service within the same HTTP request will use the same service instance. Use this if you want to maintain state within a request.

AddTransient is the safest if you are worried about multithreading and concurrency but it may be overkill. It creates a new service instance for every request, even if it is within the same HTTP request.

The suggestion last week was to configure services using AddTransient:
```
services.AddTransient<IPizzaRepo,PizzaRepo>();
```

Next week we can discuss why this was used and not AddScoped()


#### Read up on Generics, generic methods that take types

A generic method is declared with type parameters. A type parameter is a placeholder for a specific type; this type is declared by the client when the method is called. 

For example, [`IEnumerable<T>`](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.ienumerable-1?view=net-5.0) is declared with a Type Parameter T, and [in this example](https://github.com/natstar93/Generics/blob/master/IEnumerable.cs) I have specified the types int and string like this ` IEnumerable<int>` ` IEnumerable<string>`.

In the [PizzaShop](https://github.com/natstar93/PizzaShop/blob/master/Startup.cs#L39) I am using the AddTransient method and declaring the custom types IPizzaRepo and PizzaRepo. 


## 3/8/21

**Tasks:**
* Practical: Implement POST endpoint for Pizza shop. Discussion on best appraoch to organising endpoints in next session
* Theory: Read about iDisposable (and finalisers if time)

## 11/8/21
https://github.com/natstar93/TodoApi
