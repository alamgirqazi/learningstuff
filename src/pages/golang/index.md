---
title: Go lang notes
date: "2018-12-30"
---


Go Lang

https://golang.org/ref/spec#Types
https://gobuffalo.io/en/docs/installation
https://tour.golang.org/welcome/1
https://gobyexample.com/goroutines

Why?

But, most of the modern programming languages(like Java, Python etc.) are from the ’90s single threaded environment.
 Most of those programming languages supports multi-threading. But the real problem comes with concurrent execution,
 threading-locking, race conditions and deadlocks. Those things make it hard to create a multi-threading application on those languages.

For an example, creating new thread in Java is not memory efficient. As every thread consumes approx 1MB of the memory heap size and eventually if you start spinning thousands of threads, they will put tremendous pressure on the heap and will cause shut down due to out of memory. Also, if you want to communicate between two or more threads, it’s very difficult.

On the other hand, Go was released in 2009 when multi-core processors were already available. That’s why Go is built with keeping concurrency in mind. Go has goroutines instead of threads. They consume almost 2KB memory from the heap. So, you can spin millions of goroutines at any time.

Goroutines have growable segmented stacks. That means they will use more memory only when needed.
Goroutines have a faster startup time than threads.
Goroutines come with built-in primitives to communicate safely between themselves (channels).


Go takes good of both the worlds. Easy to write concurrent and efficient to manage concurrency


One most considerable benefit of using C, C++ over other modern higher level languages like Java/Python is their performance. Because C/C++ are compiled and not interpreted.


While on the other side, C/C++ does not execute on VMs and that removes one step from the execution cycle and increases the performance. It directly compiles the human readable code to binaries.


It also uses garbage collection to allocation and removal of the object. So, no more malloc() and free() statements!!! Cool!!!


Go intentionally leaves out many features of modern OOP languages.

No classes. Every thing is divided into packages only. Go has only structs instead of classes.
Does not support inheritance. That will make code easy to modify. In other languages like Java/Python, if the class ABC inherits class XYZ and you make some changes in class XYZ, then that may produce some side effects in other classes that inherit XYZ. By removing inheritance, Go makes it easy to understand the code also (as there is no super class to look at while looking at a piece of code).
No constructors.
No annotations.
No generics.
No exceptions.



Today applications rely on a number of external services: databases, caches, search and message queues.

It is becoming more common to build applications as a collection of microservices.

Go should use asynchronous I/O so that our application can interact with any number of services without blocking web requests.


What happens if we want to support thousands of connections and still take advantage of multicore? We could combine threads and coroutines (Ruby calls them fibers, Python uses generators). Or mix callbacks and processes, using Node.js with the Cluster module.



Go has one straightforward model. It multiplexes goroutines onto OS threads (like Erlang), and stacks grow as needed. Go not only addresses the C10K problem, it blows past it! (C1000K)


If you must have a full stack web application framework, Revel is as close as it gets.


While many shops that have been using Java have moved to Scala for concurrency reasons, we felt that moving to a functional programming language was going to really up the learning curve.

If you’re doing distributed work then you’ll find Go’s expressive concurrency primitives very helpful. We could achieve similar things in Node with generators, but in my opinion generators will only ever get us half way there. 


Go heavily relies on static code analysis. Examples include godoc for documentation, gofmt for code formatting, golint for code style linting, and many others.

Concurrent programming in complex applications is never easy regardless of the specific technique, partly due to the possibility of race conditions.


Stick to static types as much as possible, and use interfaces when you know exactly what sort of types you’re dealing with. Interfaces are very powerful and ubiquitous in Go.


Go has only 25 keywords, and this can give you a clue on how simple it is to learn the language. We'll be looking at the common language patterns, and we'll see how cleaner and easier it is to do some common tasks as compared to other languages.



	names := []string{"Scotch", "IO"}
    var flt float64 = 2.34 // declaring a float 
    var name string = "Scotch" // declaring a string
    a, b := true, false,  // shorthand declaration syntax


Since Go is statically typed, we need to do a little extra to define objects. There are two ways to do this, and it involves using map. A map is a key value data structure, where the keys are a set (does not contain duplicates).


The other way to write obects in Go is by using Structs. A struct is an abstract data structure, with properties and methods. It's a close equivalent to a Class in Javascript.


Go's files must be written within packages, and this usually affects your file structure.

In JavaScript, you'll see a lot of require statements at the beginning of files, while in Golang, the first line is always a package name, which will then be used as an import path in a file where it's required import package_path/package_name

A goroutine is a lightweight thread of execution.

To invoke this function in a goroutine, use go f(s). This new goroutine will execute concurrently with the calling one.

Concurrency in Go is the ability for functions to run independent of each other. 

Automation and Command-line tools - Go is also a great tool to make complex automation tools for developers. It fast, lightweight and follows unix “Do one thing. And do it well.”. Bash scripting serves the purpose as well, but bash scripts can get ugly really fast when you need to do more complex processes. DevOps is beginning to use more and more golang.

Producing maintainable code - Standardized formatting and naming through tooling (gofmt, lint) and minimalistic language makes it easy to read and reason. Through my experience as a Freelancer, go is very popular for companies who hire a large amount of freelancers, because short term contractors can get into the codebase fairly easy and get productive in no time.

Golang is good for almost any and every type of Business Application. It is great for analytics applications, AI, apps on the cloud and more. Some of the reasons why Golang is good for so many different types of application are:

Everything else? It's great for. It's real sweet spot is backend server APIs and ops tooling - it's being adopted in droves for those two use cases.

Sometimes you can tell a lot about a language by the features its creators choose to omit. Go deviates from most OOP languages by choosing composition over inheritance. 


