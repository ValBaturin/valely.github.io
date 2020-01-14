---
title: "What is RPC for real"
date: 2020-01-14T18:43:24+03:00
draft: false
---

### Before you get started
I assume that a fellow reader has some understanding of APIs and experience with REST, in particular, might help as well.
The goal of this post is to provide a clear understanding of RPC. You might've already worked
with gRPC or Apache Thrift but still can't elaborate on the differences between REST API and the mentioned tech.
This post is exactly for you.

### How to deal with new knowledge
Math teaches us before we're working with some kind abstraction we'd better have a formal definition of that thing. Having a format definition is essential for a deep understanding of any domain. Knowing what an abstraction exactly is, eliminates the possibility of misunderstanding. Human languages are always a consensus-based tool. Let's have a consensus then!

### Letter by letter
Let's all of us agree on what do we mean when we say an RPC acronym. Acronyms are easy, huh? Basically, knowing what each letter of a word stands for gives you a grasp on what the word means for free. RPC stands for "Remote Procedure Call". So it's a call of a remote procedure. It might be calls of remote procedures as well. Say honestly can you explain what RPC is after knowing what are call, remote, and procedure. I bet you can't. What if you knew what remote procedure is? It must be slightly better I guess, however, what's RPC?

### Easy way
For computer science terms it's often quite easy to just search for a term and actually find something.
What I found on wikipedia from my point of view is bad. Let me remind you that words’ meaning is also context-based. For example, the word call as a noun in American English has 4 different possible contexts and 5 different meanings according to the cambridge dictionary. So it's necessary to understand the exact meaning for terms you use depending on a context. You might argue that in computer science all terms are independent on a context. The first example which pops up in my head is a pointer. So what is a pointer in C++ programming language?
> In C++ pointers are variables that store addresses and can be null.

Then what is smart pointer?

> Smart pointer is an abstract data type that simulates a pointer while providing added features.

Can abstract data type simulate a variable? No, of course, it can not. So it must mean there's another definition of C++ pointer which fits here. And here it is!

> In C++ pointer is a class of types (eg int*, void*) which represents a position of an object in memory while also being able to represent no position (nullptr).

### Bad definition
I'm just quoting wikipedia's one.
> In distributed computing, a remote procedure call (RPC) is
> **when** a computer program causes a procedure (subroutine) to execute
> in a different address space (commonly on another computer on a shared network),
> which is coded as if it was a normal (local) procedure call,
> without the programmer explicitly coding the details for the remote interaction.

So why is it bad? The main problem with the definition above is that you can't say what RPC is after reading the definition of it.
I mean you can repeat what you've just heard but it makes no sense. Why do I say that and how's it different from good definitions.

The 2 definitions of the C++ pointers are good and let me show you the difference.
> In C++ pointers are variables that store addresses and can be null.

##### What is a pointer?

First of all, a pointer is a variable.
##### Is it just any variable?
No, it must store addresses or be null.
So we have an object and constraints on an object

The same goes for the second definition.
> In C++ pointer is a class of types (int*, void*) which represents a position of an object in memory
   while also being able to represent no position (nullptr).
       
##### What is a pointer?
First of all, a pointer is a class of types
##### Which class of types?
You can think of classes as some restrictions, so you might wonder which class is that and it's easy to answer
that pointer must represent a position of an object in memory.
This is clear.

I'm quoting again RPC definition.
> In distributed computing, a remote procedure call (RPC) is
> **when** a computer program causes a procedure (subroutine) to execute
> in a different address space (commonly on another computer on a shared network),
> which is coded as if it was a normal (local) procedure call,
> without the programmer explicitly coding the details for the remote interaction.

##### What's RPC?
I don't know. If you don't have prior knowledge you can't answer the question just using that definition.
Definitions which start with the word **when** are destructive and considered to be harmful to the deep understanding of a subject.

### Starting over
Here is a historical remark for you just in case. Originally the word RPC stood for an extension of procedure call.
The difference is that an actual execution must happen on a remote machine or at least in a different address space.
So the original definition of RPC would be
> A remote procedure call is a procedure call that's executed in a different address space.

Thus we can answer the question "what's RPC".
##### What's rpc?
Firstly it's a procedure call.
##### Is in any procedure call?
No, it must be executed in a different address space.

Awesome! Now we all know what RPC is. Well, not really.
In reality, nobody still uses RPC as a word that was used almost 50 years ago.
So let me explain what RPC means nowadays.
> RPC is a software architectural style that defines a set of constraints to be used for creating APIs.

### Getting real
It's important to notice that people often omit the word `implementation` when they mean it.
For example, even though REST is an approach, style and just a list of constraints for implementing web application APIs
we can say that service has REST or REST API and what we actually mean is that service has an implementation of REST API.
It has an implementation of API according to the specific style and which abides the rules.

Even though being a human means we would probably omit the implementation word
partially because the use of it is redundant and can be
deducted from a context now we have a clear understanding of what RPC implementation means.

### Getting even more real
You might think that the definition is too vague and you still don't really get what's the
difference between REST and RPC. RPC and REST are essentially the same at least because they
solve the same problem in software engineering. If we dive into details we'd see the difference.
That's what're we going to do right now.
As you can see the origin of RPC is an attempt to isolate processes and create virtual memory
abstraction to achieve different kinds of goals. Once computers evolved enough we don't see a problem of
processes isolation that vivid anymore and basically take for granted that procedures can be executed in different
address spaces.

The legacy that RPC brings to us is that RPC means to be as simple as possible
and creating abstraction on top of the application is not required. Therefore the guideline of RPC
is to be tightly coupled with an internal app.
On the other hand, RESTful web services have loosely coupled API implementations.

### A bit of history of REST.
> The term representational state transfer was introduced and defined in 2000 by Roy Fielding in his doctoral dissertation.
> Fielding's dissertation explained the REST principles that were known as the "HTTP object model" beginning in 1994,
> and were used in designing the HTTP 1.1 and Uniform Resource Identifiers (URI) standards.
> The term is intended to evoke an image of how a well-designed Web application behaves:
> it is a network of Web resources (a virtual state-machine) where the user progresses
> through the application by selecting resource identifiers such as `http://www.example.com/articles/21`
> and resource operations such as GET or POST (application state transitions),
> resulting in the next resource's representation (the next application state) being transferred to the end user for their use.

The concept is aiming to indeed create a loosely coupled architecture and what else is that such a design style makes
sense when you want to create a lot of reusable components so that it's possible and quite easy to create another application on top 
of the API by combining those components. There's a bunch of other architectural constraints which REST introduces, however, I hope
that you got the main idea.

### Now you know
Congratulations! By this point, you know what RPC is and can explain what the difference between REST and RPC is.
