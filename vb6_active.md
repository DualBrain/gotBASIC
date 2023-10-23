[Home](https://gotbasic.com) • [VB 7+](vb.md) • VB 1-6 • [FB](freebasic.md) • [QB64](qb64.md) • [QB45](qb.md) • [GW-BASIC](gw-basic.md) • [Micro](micro.md) • [Retro](retro.md)

## Working with ActiveX

### What is ActiveX?

*I have been hearing a lot about ActiveX. What is it?*

ActiveX is the set of technologies that allow separately compiled components to communicate with one another. It allows you to develop components in many different languages such as VC++, Java, Excel, and Visual Basic and have all of the components work together.

You may have built ActiveX components with VB4, but way back then (`<G>`) they were called OLE servers. The ActiveX technology in VB5 provides some additional features beyond those provided by the OLE servers in VB4. You can develop threaded components, add non-modal forms to ActiveX DLL components, raise events, have Friends, implement multiple interfaces, define global objects and create ActiveX controls and ActiveX documents.

### Is ActiveX OOP?

*What does ActiveX have to do with object-oriented programming?*

You can use object-oriented programming techniques, such as encapsulation, to build components. ActiveX then provides the technology for the components to interact with each other.

### What is an ActiveX Code Component?

An ActiveX code component is a compiled set of code that is normally comprised of one or more class modules. These components can be ActiveX DLLs or ActiveX EXEs.

A single ActiveX code component normally contains all of the business rules for a particular business object or a set of standard routines. This is very similar to creating libraries of functionality where each set of functionality is compiled into a single component.

### What is an ActiveX DLL?

An ActiveX DLL is a code component that runs in the same process as the client application. So it runs in the same address space as the client application that is using the component.

Any components you create to work with Microsoft Transaction Server must be ActiveX DLL components. Any other components you develop for use on the same machine as the client application can also be ActiveX DLL components. This is normally the preferred choice because it is easier to test (by adding another project using the new VB5 project group feature) and has better performance.

### What is an ActiveX EXE?

An ActiveX EXE is a code component that runs in a separate process from the client application. So it runs in its own address space.

If you plan to place the component on a computer different from the computer running the client application and you don't plan to use Microsoft Transaction Server, the component must be an ActiveX EXE. ActiveX EXEs are also useful for creating components that can also be run stand-alone, that is they can be run by clicking on the icon. This is similar to Excel: you can click on the Excel icon and launch Excel or you can create an Excel object from VB.

Since ActiveX DLLs are easier to test, you can test your ActiveX EXE first as an ActiveX DLL and then convert it to an ActiveX EXE using the Project Properties dialog box.

### What is an ActiveX control?

*I can now create an ActiveX control in VB5. What is an ActiveX control and how is it different from other ActiveX components?*

An ActiveX control is a standard user interface element that you can create. These elements can be used in any container that supports ActiveX controls, such as Visual Basic forms, Excel forms, and VC++. They are different from other ActiveX components in that they normally have a visual component like a combo box or set of text boxes.

Normally, if you are going to define business rules you do that in ActiveX EXE or ActiveX DLL components and not in ActiveX controls.

### How do I define global objects?

*I have heard that I can now create global objects with VB5. What are global objects and why would I want to create one?*

Global objects are not what you may first think they are. Global objects are basically objects that can be used by any client application without the client application having to declare them.

To create a global object, you define a class module in an ActiveX code component and set the Instancing property to be GlobalMultiUse or GlobalSingleUse. To use the global object, any client application can set a reference to the ActiveX code component using the Project Properties option. The properties and methods of the class are then added to the global name space of the client application.

Let's look at an example. Let's create a math ActiveX component that does specialized math processing. The code for a simple CMyMath class can be added to this component:

```vb
Private m_iFirstVal As Integer
Private m_iSecondVal As Integer

Public Property Let FirstVal(RHS As Integer)
  m_iFirstVal = RHS
End Property

Public Property Let SecondVal(RHS As Integer)
  m_iSecondVal = RHS
End Property

' Special type of addition
Public Function Add() As Integer
  Add = (m_iFirstVal * 100) + (m_iSecondVal * 100)
End Function
```

The Instancing property for this class must be set to GlobalMultiUse or GlobalSingleUse.

You can then write a test application to use this class. Create a standard project and set the reference to the project with the CMyMath class. The normal way to use an object from a standard class would be code such as the following:

```vb
Private m_Math As CMyMath

Function AddVal(x, y) As Integer
  Set m_Math = New CMyMath
  m_Math.FirstVal = x
  m_Math.SecondVal = y
  AddVal = m_Math.Add
End Function
```

But since the CMyMath class is defined to be GlobalMultiUse or GlobalSingleUse, the m_Math object variable is not needed. You could therefore write the code like this:

```vb
Function AddVal2(x, y) As Integer
  FirstVal = x
  SecondVal = y
  AddVal2 = Add
End Function
```

There is no declaration and no mention of an object variable. But is this "good" code? Here is the "good" code test: if you look at this code 6 months from now will you have *any* idea what is going on? In this case, will you know where FirstVal, SecondVal, and Add are coming from? Probably not.

What you would want to do instead is provide an object property in the CMyMath class that can be used to more clearly identify the global object. This property would be added to the CMyMath class and would look like this:

```vb
Public Property Get MyMath() As CMyMath
  Set MyMath = Me
End Property
```

You can then rewrite the AddVal routine in the client application as follows:

```vb
Function AddVal3(x, y) As Integer
  myMath.FirstVal = x
  myMath.SecondVal = y
  AddVal3 = myMath.Add
End Function
```

The myMath property then acts and works like other standard Visual Basic objects such as Debug, App, and Err. Since you are using the object property, you also get the AutoList Members that you didn't have in AddVal2 example above.

So, global objects are like the App and Debug objects where you don't need to create an instance before you can use them. They are most beneficial for generic components like specialized math processing or generalized database processing.

NOTE: You can also use this technique to define global string constants since the Public Enum only works for Long Integers.

### Do I need a Sub Main?

*With VB4, I have to have a Sub Main in my OLE servers. Do I have to have a Sub Main in my ActiveX code components in VB 5?*

No, you don't need to have a Sub Main. In the General tab of the Project Properties, you can now select "None" as the Startup Object. You can select Sub Main if you wish to initialize the component, but it is no longer required.
