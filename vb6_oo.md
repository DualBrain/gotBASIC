[Home](https://gotbasic.com) • [VB 7+](vb.md) • VB 1-6 • [FB](freebasic.md) • [QB64](qb64.md) • [QB45](qb.md) • [GW-BASIC](gw-basic.md) • [Micro](micro.md) • [Retro](retro.md)

## Working with Objects and Classes

### What is an object?

*You may have heard a thing or two about how Visual Basic is an object-oriented programming tool. But what is an object anyway? And more importantly, why should you care?*

An object is basically a thing that has properties (also called attributes or data elements) and methods (also called behaviors). So you are basically an object. You have properties such as hair color and shoe size. You also have methods that you know how to perform such as brushing your teeth or tying your shoe. Your time sheet is also an object. It has properties such as date, time period, and hours worked. It could also have methods such as Total, if the time sheet is automated.

Ever since the first release of Visual Basic, it provided objects with properties and methods. The text box in the toolbox is an object. It has properties such as Text, Height, Width, and TabIndex. It also has methods such as SetFocus and Move. The syntax for using the properties and methods are similar, yet slightly different.

When referencing a property, you use the "=" sign. For example: Text1.Text = "CA". You can also use the property on the right side of the equal sign: sTemp = Text1.Text.

When calling a method, you don't use an equal sign. If you need to provide information to the method, you pass it as parameters. For example: Text1.Move 200, 200.

With the release of Visual Basic 4.0, you can create your own objects and give them your own properties and methods. These cannot be objects that appear in the toolbox, but they can be business type objects. Take the time sheet example we mentioned earlier. You can create your own time sheet object with Visual Basic. You can define its properties and methods, and you can use those properties and methods as needed. More on how to do this in the next several topics.

### How do I define my own object?

*An object is defined within a class. The class defines the properties and methods appropriate for all objects of a given type. For example, my time sheet is an object and your time sheet is an object. We could develop a general definition of a time sheet to include employee number, date, and hours worked properties and a total method. These are defined in the time sheet class. My specific time sheet and your specific time sheet are individual objects and are instances of that time sheet class.*

Another way to think about the difference between an object and a class is to use the cookie-cutter metaphor presented in the Visual Basic documentation. The cookie-cutter defines the size and shape of the cookies. It is the class. Each cookie is an instance of that class and will have the properties given to it by the class.

To define a class in Visual Basic, you can insert a class module into a Visual Basic project. Only one class can be defined in a single class module, so you need to insert a class module for each class you want to define. You can then define properties and methods in the class as described in the topics which follow.

### How do I define my own properties?

*OK, you've decided to create your own class. So how do you define the properties of that class with Visual Basic?*

You do it by first declaring a variable for the property. Using a time sheet example you could declare an employee number property for the employee that owns the time sheet. This variable would be declared similar to the following:

```vb
Private m_lEmployeeNumber as Long
```

Notice the naming convention for this declaration. The "m_" denotes that it is a member variable in the class. The "l" defines its data type and the rest is the logical name.

Using the Private key word ensures that this member variable is private to the class in which it is defined. This encapsulates the value. But what good is an employee number property if it is private only to this class? The property needs to be available to other parts of the application, such as the time sheet form that wants to display the employee number on the screen.

To make the property useful to other parts of this application, it can be exposed by using Property procedures Property procedures are a special type of procedure that allows the class to provide access to a property for read-only, read and write, or write-only.

```vb
Public Property Get EmployeeNumber( ) as Long
  EmployeeNumber = m_lEmployeeNumber
End Property
Public Property Let EmployeeNumber(lNumber as Long)
  If lNumber < 1000 Then
    Err.Raise lInvalid_Emp_Number, "CEmployee:EmployeeNumber", "Invalid Employee Number"
  Else
    m_lEmployeeNumber = lNumber
  End If
End Property
```

Note that you can also use these same techniques to add your own properties to forms and standard modules.

### How do I define an array property in a class?

*So now you know how to define a property. But what if you want a property that is an array? Is it possible?*

The answer is "yes"! If you are using VB 6.0, see the next topic. If you are using VB 4 or 5, the trick to this one is to remember that a variant can hold any type of data, including an array. Just define the property as a variant and use it as an array.

The following code is in a class called CArray::

```vb
Private m_MyArray As Variant

Public Property Get MyArray() As Variant
  MyArray = m_MyArray
End Property

Public Property Let MyArray(a As Variant)
  m_MyArray = a
End Property
```

You can then use these properties of the class in several different ways, as illustrated by the following code from a form:

```vb
Private m_Array As CArray
Private mArr(3) As String

Private Sub Form_Load()
  Set m_Array = New CArray
  mArr(1) = "One"
  mArr(2) = "Two"
  mArr(3) = "Three"
  m_Array.MyArray = mArr()
  'OR
  '  m_Array.MyArray = Array("One", "Two", "Three")
End Sub

Private Sub Form_Unload(Cancel As Integer)
  Dim i As Integer
  For i = 1 To UBound(m_Array.MyArray)
    MsgBox m_Array.MyArray(i)
  Next
End Sub
```

### How do I define an array property in a class? (1)

*So now you know how to define a property. But what if you want a property that is an array? Is it possible?*

Starting with VB 6.0, you no longer need to use a Variant to store your array.

The following code is in a class called CArray::

```vb
Private m_MyArray() As String

Public Property Get MyArray() As String()
  MyArray = m_MyArray
End Property

Public Property Let MyArray(arr() As String)
  m_MyArray = arr
End Property
```

You can then use this property of the class, as illustrated by the following code from a form:

```vb
Private m_Array As CArray

Private Sub Form_Load()
Dim arr() As String
  Set m_Array = New CArray
  ReDim arr(3)
  arr(0) = "One"
  arr(1) = "Two"
  arr(2) = "Three"
  m_Array.MyArray = arr
End Sub
```

### When do I use the New keyword?

*If you have "Require Variable Declarations" set (which you should`<G>`), you will need to declare any object variable prior to using it. The Dim/Public/Private declaration statement simply defines the data type of the variable you are defining. If you know it is an object, but don't know it's type you can declare it "As Object". Your variable is then late bound and has the associated performance penalties. If you declare it with the specific type "As CPerson" where CPerson is the name of your class, it is early bound and you must have a reference defined for it in the References dialog box.*

If you add the New key word to the declaration statement, VB will automatically create an instance of the object for you when it is first accessed. As far as I know you can only use the New key word on OLE servers created with VB. It does not work with other objects such as DAO or Excel objects.

If you don't use the New key word, then you have to create the object explicitly using the CreateObject or "Set m_oPerson = New CPerson" syntax. From MS's numbers, the New syntax is 6X faster than the CreateObject syntax. Again, the New key word is not available with DAO, Excel, or other predefined objects so you have to use the CreateObject syntax in those cases.

```vb
Private m_oPerson as CPerson
Sub Form_Load( )
  Set m_oPerson = New CPerson
End Sub
```

### How do I use the Implements keyword?

*The Implements keyword allows me to define a common interface (set of properties and methods) on a set of my classes. But how do I use the Implements correctly?*

The first step is to define the common interface (set of properties and methods). You do this by creating a class module with only the property and method declarations (no code). This would look something like:

```vb
' This is the Interface: IPerson
Option Explicit
Public Name As String
Public Address As String
```

Notice that we used Public declarations for the properties instead of Property procedures. Since we are not creating any code, we don't need the property procedures.

The second step is to implement this interface in another class. This is done by first inserting Implements keyword in the class module for the class that will implement the interface. Then add the property and method declarations for each property and method in the implemented interface to the class module. As soon as you type in the Implements statement, the interface name will appear in the Object combo box at the top and left of the Code window. If you select the interface name, the list of all properties and methods appear in the Procedure combo box at the top and right of the Code window. Select each property and method from the combo box and the template for the procedure will be automatically inserted into the class module.

The result will look something like this:

```vb
' This is the class: CCustomer
' that implements IPerson
Option Explicit

Implements IPerson

Private Property Let IPerson_Address(ByVal RHS As String)
  ' Code here
End Property
Private Property Get IPerson_Address() As String
  ' Code here
End Property

Private Property Let IPerson_Name(ByVal RHS As String)
  ' Code here
  MsgBox "New value is: " & RHS
End Property
Private Property Get IPerson_Name() As String
  ' Code here
  MsgBox "Got the value"
End Property
```

I added some test code in this example above so you can try this at home. Notice that even though we declared Name and Address to be Public variables in the interface, they correctly generate pairs of Property procedures in the class that implements the interface.

Finally, we want to be able to use the interface. It would seem that you should be able to do the following:

```vb
' This code is in a form
Private m_Customer As CCustomer
Private Sub Form_Load()
  Set m_Customer = New CCustomer
  m_Customer.Name = "John Smith"
End Sub
```

However, this does not work. If you look at the Property procedures in the CCustomer class, you can see why. First, the Name Property procedures are Private. Second, they are prefaced with the name of the interface. So how do you access the IPerson interface for the CCustomer class?

One way is to do this:

```vb
' This code is in a form
Private m_Customer As CCustomer
Private m_IPerson as IPerson
Private Sub Form_Load()
  Set m_Customer = New CCustomer
  Set m_IPerson = m_Customer
  m_IPerson.Name = "John Smith"
End Sub
```

But this is not very intuitive. If you think too hard about it, it doesn't even seem to make sense. You are basically casting the m_Customer object variable to the m_IPerson interface.

A better approach is to do this:

```vb
' This code is in a form
Private m_Customer As CCustomer
Private Sub Form_Load()
  Set m_Customer = New CCustomer
  Test m_Customer
End Sub

Sub Test(obj As IPerson)
  obj.Name = "John Smith"
  obj.Address = "101 Main Street"
End Sub
```

This passes the object to the Test procedure defined with the interface type (IPerson) thereby casting the object to the correct interface. The additional benefit of this approach is that is supports polymorphism. That means that any class that implements the IPerson interface can be passed to this routine and this routine will call the properties and methods in the appropriate class.

### What is the Dictionary object?

*What is the difference between the Dictionary object and a Collection?*

A dictionary can contain items, which can be any form of data. Each item is associated with a unique key. The key is used to retrieve an individual item and is usually an integer or a string, but can be anything except an array.

Differences between the dictionary and a collection:

* Allows retrieval of the key using the keys(index) syntax
* Has an Exists property to determine if a particular key exists
* Allows changing of a key
* Allows changing a value associated with a key
* 0-based
* Does not provide an enumerator

NOTE: To use the Dictionary object, you must set a reference to the Microsoft Scripting Runtime.

### How do I know where to put my business rules?

*When implementing a three-tiered architecture (which separates user interface, business rules, and the database into three tiers), you have to decide which code belongs in which tier. The most commonly asked question in this regard is "where should the business rules go?" Well the answer is a convincing "it depends".*

For many of my projects I have divided the business rules into all three tiers as follows:

* User-Interface tier: The only type of business rules handled in the user-interface tier is data type validation. This validation is done at the form level, many with specialized controls (such as a masked-edit, date, list box, or combo box control) or with code on the form that prevents entry of certain invalid characters.
* Business object tier: Most of the other business rules are handled in the business object tier. This is where the range checking, required field verification, and other validation is performed.
* Database tier: Some of the business rules make sense as part of the stored procedures in the back-end. For example, validating unique entries are most efficiently handled in the back-end.

Allowing business rules in all three layers provides flexibility and considers factors such as performance and ease of maintenance.

### How should I validate the user-entered values?

*I want to validate the end-user's entry. How do I do this?*

There are two basic approaches to data entry validation:

* Field-by-field. Each field is validated as the user leaves the field.
* All at once. All fields are validated at once. This normally occurs when the user clicks to OK or Save button.

When using the field-by-field approach, the most common method we use to validate the values is to do the following:

* Use the [Validate Event (new in VB6)](vb6_forms.md) to perform the validation.
* In the Validate Event, call the associated Property procedure for the field. This ensures that all of the basic field validation information is defined in the associated class instead of storing the validation information in the forms.
* Leverage the CallByName feature (new in VB6) to use one set of code for all controls on the form that are in one control array. Example:

```vb
Private Sub txtTeam_Validate(Index As Integer, Cancel As Boolean)
  If txtTeam(Index).Tag <> "" Then
    CallByName m_Team, txtTeam(Index).Tag, VbLet, txtTeam(Index).Text
  End If
End Sub
```

* The Property procedure in the class can then raise an error to this routine. Code in the Validate event can then trap this error and notify the user of the error by turning the text red or the text box label another color. WARNING: Click here for info on a related bug.
* Alternatively, the code in the class can keep track of the list of errors. It can manage a collection of these errors. These can be tracked by an Error object that contains detailed information. Alternatively, it can be tracked by a simple collection of strings where each string is the human-readable error description. This collection can then be displayed in a list box, if desired.
* Note: This type of validation will only validate the fields as the user leaves them. It won't validate any fields the user has not entered. So you will also need a Validate method of some type to validate all of the fields before the data is saved. This Validate method can also perform inter-field validation.

When using the all at once approach, we use a Validate method as described above. This Validate method can make use of the errors collection described above to track all of the found errors instead of returning only one error at a time.
