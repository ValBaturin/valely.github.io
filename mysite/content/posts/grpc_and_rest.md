# What is RPC for real?

### Prelude
Math teaches us before we're working with some kind abstraction we'd better have a formal
definition of that thing. Having a format definition is essential for deep understanding of any domain.
Knowing what an abstraction exactly is eliminates possibily of misunderstanding.
Human languages are always a concensus based tool. Let's have a concensus then!

Let's all of us agree on what do we mean when we say an RPC acronym. Acronyms are easy, huh? Basically knowing what each letter of a word stands for
give you an insignt on what the word means for free. 
RPC stands for remote procedure call. So it's a call of a remote procedure. It might be calls of remote procedures as well. Say honestly can you explain what
RPC is after knowing what are call, remote and procedure. I bet you can't. What if you knew what remote procedure is? It must be slightly better I guess.

For computer science terms it's often possible to search for a term and actually find something.

What I found on wikipedia from my point of view is bad.
Let me remind you that words' meaning is also context based. For example the word `call` as a noun in American English has 4 different possible contexts and
5 different meanings according to the cambridge dictionary.
So it's necessary to understand the exact meaning for terms you use depending on a context.
You might argue that in computer science all terms are independent on a context.
The first example which pops up in my head is a pointer. So what is a pointer in C and C++ programming languages?

> In C and C++ pointers are variables that store addresses and can be null.

Then what is smart pointer?

> Smart pointer is an abstract data type that simulates a pointer while providing added features.

Can abstract data type simulate a variable?
No, of course it can not. Even though a type word has a bunch of meaning from mathematics to computer science to fashion
I bet that there's no meaning of that word which can be used in a context of being simulated by an abstract data type.

> In C and C++ pointer is a class of types (eg int*, void*) which represents a position of an object in memory
   while also being able to represent no position (nullptr).

I'm quoting it
> In distributed computing, a remote procedure call (RPC) is
> **when** a computer program causes a procedure (subroutine) to execute
> in a different address space (commonly on another computer on a shared network),
> which is coded as if it was a normal (local) procedure call,
> without the programmer explicitly coding the details for the remote interaction.

##### Why is it bad?
The main problem with the definition above is that you can't say what rpc is after reading the definition of it.
I mean you can repeat what you've just heard but it makes no sence. Why do I say that and how's it different for compared to good definitions.

The 2 definitions of the C/C++ pointers are good enough and let me show you the difference and why do I think they're better than rpc wiki definition.
> In C and C++ pointers are variables that store addresses and can be null.

##### What is a pointer?

First of all a pointer is a variable.
##### Is it just any variable?
No, it must store addresses or be null.
So we have an object and constraints on an object

The same goes for the second definition.
> In C and C++ pointer is a class of types (int*, void*) which represents a position of an object in memory
   while also being able to represent no position (nullptr).
       
##### What is a pointer?
First of all a pointer is a class of types
##### Which class of types?
Class means some restrictions so you might wonder which class is that and it's easy to answer
that pointer must represents a position of an object in memory.
This is clear.

I'm quoting again rpc definition.
> In distributed computing, a remote procedure call (RPC) is
> **when** a computer program causes a procedure (subroutine) to execute
> in a different address space (commonly on another computer on a shared network),
> which is coded as if it was a normal (local) procedure call,
> without the programmer explicitly coding the details for the remote interaction.

##### What's rpc?
I don't know. If you don't have a prior knowleadge you can't answer the question just using that definition.
Definitions which start with the word **when** are destructive and considered to be harmful for the deep understanding of a subject.

### Historical remark
Originaly the word RPC stood for an extension of procedure call.
The difference is that an actual execution must happen on a remote machine or at least in a different address space.
So the original definition of RPC would be
> A remote procedure call is a procedure call that's executed in a different address space.

Thus we can answer the question what's rpc.
##### What's rpc?
Firstly it's a procedure call.
##### Is in any procedure call?
No, it must be executed in a different address space.

Awesome! Now we all know what rpc is. Well, not really.
In reallity nobody still uses rpc as a word which was used almost 50 years ago.
So let me explain what RPC means nowadays.
> RPC is a software architectural style that defines a set of constraints to be used for creating APIs.

It's important to notice that people often omit the word `implementation` when they actually mean it.
For example even though REST is an approach, style and just a list of constraints for implementing web applications
we can say that a service has REST or REST API and what we actually mean is that a service has an implementation of REST API.
It has an implementation of API according to the specific style and which abides the rules.

Even though being a human means we would probably omit the impelementation word
partialy because the use of it is redundant and can be
deducted from a context now we have a clear understaing what rpc implementation means.

You might think that the definition is too vague and you still don't really get what's the
difference between REST and RPC. RPC and REST are essentially the same at least because they
solve the same problem in software engineering. If we dived into details we'd see the difference.
That's what're we going to do right now.
As you can see the origin of rpc is an attempt to isolate processes and create virtual memory
abstraction to achive different kinds of goals. Once computers evolved enough we don't see a problem of
processes isolation that vivid anymore and basically take for granted that procedures can be executed in different
address spaces.

The legacy that rpc brings to us is that rpc means to be as simple as possible
and creating abstraction on top of application is not requered. Therefore the guildline of RPC
is to be tightly coupled with an internal app.
On the other hand RESTful web services have loosly coupled API implementations.

### A bit of history of ReST.
> The term representational state transfer was introduced and defined in 2000 by Roy Fielding in his doctoral dissertation.
> Fielding's dissertation explained the REST principles that were known as the "HTTP object model" beginning in 1994,
> and were used in designing the HTTP 1.1 and Uniform Resource Identifiers (URI) standards.
> The term is intended to evoke an image of how a well-designed Web application behaves:
> it is a network of Web resources (a virtual state-machine) where the user progresses
> through the application by selecting resource identifiers such as `http://www.example.com/articles/21`
> and resource operations such as GET or POST (application state transitions),
> resulting in the next resource's representation (the next application state) being transferred to the end user for their use.

The concept is aiming to indeed create a loosly coupled architecture and what else is that such a design style makes
sense when you want to create a lot of reuseble components so that it's possible and quite easy to create another application on top 
of the api by combining those components. There's a bunch of other architectural constraints which REST introduces however I hope
that you got the main idea.

Congratulations! By this point you know what RPC is, some basics of REST and how they are different.
