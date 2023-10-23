[Home](https://gotbasic.com) • [VB 7+](vb.md) • VB 1-6 • [FB](freebasic.md) • [QB64](qb64.md) • [QB45](qb.md) • [GW-BASIC](gw-basic.md) • [Micro](micro.md) • [Retro](retro.md)

## Understanding Class Persistence

### What is a class persistence?

*I have been hearing about persisting classes. What does that mean?*

Persisting a class simply refers to saving the properties of that class. In VB, this means to write the properties into the PropertyBag and then store the PropertyBag in a file or in a database.

### I cannot seem to make my object persist itself

*I have been using the techniques for object persistence in the object's class. But it does not seem to work.*

That's right. An object cannot persist or depersist itself. Just like an object cannot create itself.

When an object's properties are stored in the PropertyBag, VB also writes the class ID of the object into the PropertyBag. When the object is depersisted, VB retrieves the class ID from the PropertyBag, creates the object, and then allows you to assign the properties of the object to values from the PropertyBag.

So the follow-on question here is what should cause the object to persist itself. When doing simple applications, you can have the form do this - but that is not very encapsulated. Another way to do this is to create an Application class that is responsible for persisting all of the objects in the application.

### I cannot seem to persist my array properties

*The persistence seems to work, but it generates an error any time I add an array property.*

That's right. Array properties cannot be persisted.
