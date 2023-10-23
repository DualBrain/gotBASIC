[Home](https://gotbasic.com) • [VB 7+](vb.md) • VB 1-6 • [FB](freebasic.md) • [QB64](qb64.md) • [QB45](qb.md) • [GW-BASIC](gw-basic.md) • [Micro](micro.md) • [Retro](retro.md)

## Language Tips and Tricks

### How do I use that new CallByName function?

*The CallByName function looks interesting. How do I use it?*

The CallByName function allows you to call a procedure by the string version of its name. In the example below, the CallByName function will call a routine in "Me", which in this case is a form. The function name is retrieved from the combo box text (Combo1.Text). The type of call is vbMethod. Other choices include Property Let and Property Get statements. The file two parameters are the parameters to the method defined by Combo1.Text.

```vb
Private Sub Combo1_Click()
  txtSolution.Text = CallByName(Me, Combo1.Text, VbMethod, txt1.Text, txt2.Text)
End Sub

Function Add(i1 As Integer, i2 As Integer) As Integer
  Add = i1 + i2
End Function

Function Subtract(i1 As Integer, i2 As Integer) As Integer
  Subtract = i1 - i2
End Function

Function Multiply(i1 As Integer, i2 As Integer) As Integer
  Multiply = i1 * i2
End Function

Function Divide(i1 As Integer, i2 As Integer) As Integer
  Divide = i1 / i2
End Function
```

To download this example, [click here](images/callbyname.zip).

## What is an Enum?

*What is an Enum and why would I use one?*

Enum is new to VB5. It allows you to define a set of long integer constants that are global. If you have ever wanted constants in a class module to be accessible to the client application, you now have the capability with the Enum key word.

```vb
Public Enum taskPriority
  taskTPEmpty = 0
  taskTPUrgent = 1
  taskTPHigh = 2
  taskTPMedium = 3
  taskTPLow = 4
End Enum
```

The taskTPEmpty, taskTPUrgent, and so on are constants that are accessible from anywhere in the application. If this Enum was added to an ActiveX component, the constants are accessible from any application with a reference to the ActiveX component. This is because the constants defined in the Enum statement are added to the type library for the component. When a reference is set to the type library, these constants become part of the global name space of the application.

For example, if the Enum taskPriority was created in an ActiveX component, a reference to the component could be set in a test application. This test application could then include the following code:

```vb
If Val(Text1.Text) <> TaskTPEmpty then
  '...do something
End If
```

You don't need to create an object from the class to access the Enum constants declared in that class.

Note that these constants can only be long integers. For strings and other types of constants, use a [global object](vb6_active.md).

### How do I hide an enumerated constant?

*I want to be able to add enumerated constants to an enum that don't show up in the list of enumerated constants. How do I do that?*

There may be times that you want to identify some constant values that you don't want to have appear in the list of enumerated constants.

```vb
Public Enum taskPriority
  taskTPFirst = 0
  taskTPEmpty = 0
  taskTPUrgent = 1
  taskTPHigh = 2
  taskTPMedium = 3
  taskTPLow = 4
  taskTPLast
End Enum
```

This type of enum allows you have code that checks for values in the range by checking less than taskTPFirst and greater than or equal to taskTPLast. (Note that taskTPLast was not given a specific numeric constant. It allows you to add more constants above it and it will always be one more than the last one.)

The downside of this approach is that the developer using your component will see the values taskTPFirst and taskTPLast in the list of available values. This may not be desirable. You can hide these enumerated constants by prefixing the name with an underscore character. Since the underscore character is not a valid character in a name, the entire name needs to be in square brackets: `[ ]`.

```vb
Public Enum taskPriority
  [_taskTPFirst] = 0
  taskTPEmpty = 0
  taskTPUrgent = 1
  taskTPHigh = 2
  taskTPMedium = 3
  taskTPLow = 4
  [_taskTPLast]
End Enum
```

You now how two hidden enums in the taskPriority enumerated list.

### When should I use an Optional parameter?

*I have been hearing about Optional parameters. What are they and when should I use them?*

Parameters define the data to be passed to a Function or Sub procedure in Visual Basic. For example:

```vb
' Display a data initialized with the data from the defined record number
Public Sub Display(lRecNumber as Long)
  ' <Code here to get the defined record>
End Sub
```

This routine is called as follows:

```vb
Call Display(52)
```

What if you would like this Sub procedure to be able to display a blank form and not initialized with data from a defined record? You could hard-code the procedure to define a special type of record number, such as -1, be passed to your procedure to mean no record number. The code would look as follows:

```vb
' Display a data initialized with the data from the defined record number
Public Sub Display(lRecNumber as Long)
  If lRecNumber = -1 then
    ' <Code to display blank form
  Else
    ' <Code here to get the defined record>
  End If
End Sub
```

And the call would look like:

```vb
Call Display(-1)
```

All developers using your subroutine would then need to know that special meaning of -1.

Starting with VB4, Visual Basic introduced Optional parameters. These are procedure parameters that are just what they say they are, optional. To define an Optional parameter, you use the Optional key word as shown below.

```vb
' Display a data initialized with the data from the defined record number
Public Sub Display(Optional lRecNumber as Variant)
  If IsMissing(lRecNumber) then
    ' <Code to display blank form
  Else
    ' <Code here to get the defined record>
  End If
End Sub
```

The IsMissing function is used to determine whether or not the Optional Variant argument was provided when the function is called. The IsMissing function will return true if no argument was passed for the Optional parameter.

If the user wants to call your Sub procedure without the Optional parameter, the call is as follows:

```vb
Call Display
```

A few tips for working with Optional parameters:

* With VB4, Optional parameters had to be Variants. With VB5, you can use any data type.
* In VB4 Optional parameters could not be used in Property procedures. In VB5 they can.
* All parameters following an Optional parameter must also be Optional.

### How come IsMissing doesn't always work?

*You stated in the prior tip that I could use IsMissing to determine whether or not a value was passed for an Optional parameter. This does not always seem to work. Why?*

IsMissing actually determines if a Variant variable is empty. Therefore, IsMissing will not work if you define an Optional parameter of a specific (non-Variant) data type. When you think about this, it makes sense. How could Microsoft define what integer value was defined to be "empty"? Even if they picked some large negative number, there would be some developer somewhere that needed to pass an Optional parameter with that value.

So, how do you check for missing values with non-Variant data types? One way is to use default values, which basically would define "empty" or "not defined" for your particular application. For example:

```vb
' Display a data initialized with the data from the defined record number
Public Sub Display(Optional lRecNumber as Long = -1)
  If lRecNumber = -1 then
    ' <Code to display blank form
  Else
    ' <Code here to get the defined record>
  End If
End Sub
```

This takes us back to using -1 as in the prior tip. The difference here is that the developer calling your routine does not need to know about this special number. By simply not passing an argument for that parameter, the -1 value will be used.

### Why is my string handling so slow?

*My application is performing poorly. When I evaluated where the problems were, I found it to be in the string handling. Why is my string handling so slow and what can I do about it?*

The following tidbit of information is from the new book: "VB Developer's Guide to ASP and IIS" (Sybex) by Russell Jones. "...VB must allocate memory and create a new string every time you concatenate two strings together. The longer the two strings are, the more memory (and time) it takes to concatenate them. By using shorter strings or byte arrays, you can often dramatically speed up a routine with very little work."

Another tip from Jones, if you need to concatenate many different string elements into a large string you can get better performance by building each string individually and concatenating all of them at the same time.

Another option is to use the MID$ function. This would work as follows:

```vb
' Prepare the length of the string
' This is critical for performance reasons
sLargeString = Space$(rs.RecordCount * 52)
lPos = 1

' Copy each field from the recordset to a UDT
' and append this all to a very long string
Do Until rs.EOF

  udtTeamDetail.TeamID = rs!TeamID
  udtTeamDetail.TeamName = rs!TeamName & ""
  udtTeamDetail.TeamGames = Val(rs!TeamGames & "")
  udtTeamDetail.TeamWins = Val(rs!TeamWins & "")

  LSet udtTeamSummary = udtTeamDetail
  Mid$(sLargeString, lPos, 52) = udtTeamSummary.TeamBuffer
  lPos = lPos + lUDT

  rs.MoveNext

Loop
```
