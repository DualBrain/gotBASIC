[Home](https://gotbasic.com) • [VB 7+](vb.md) • VB 1-6 • [FB](freebasic.md) • [QB64](qb64.md) • [QB45](qb.md) • [GW-BASIC](gw-basic.md) • [Micro](micro.md) • [Retro](retro.md)

## Working with Forms and Controls

### What is the normal order of form events?

*There are several new form events in VB 4.0. In what order are these events normally generated?*

This is a good question, and depends on your code. In most cases, the event will fire in the following order:

`Form_Initialize` - This event will occur as soon as the form is referenced in any way. Normally, any related objects are initialized in this event.

`Form_Load` - This event will occur as soon as you Load or Show the form of if you reference any controls or visual properties of the form. (The form will load automatically when it is shown, so a separate load is not required.) This event will not occur if you simply reference properties on the form that you created.

`Form_Resize` - This event resizes the form appropriately.

`Form_Activate` - Any code that must be run after the form has been loaded (such as a SetFocus call) can be put into the Activate event. The form will get additional Activate events whenever it becomes the active form in the application.

`Form_GotFocus` - This event will only occur if no other control on the form can get focus. Otherwise, the specific control (the first enabled control in the TabOrder) will get the focus.

`Form_Paint` - This event will occur whenever the form needs to be repainted.

`Form_Unload` - This event will occur whenever you close the form using the Close box or with an unload statement. Closing and unloading the form removes the form from memory, but not the code associated with the form. So you can still reference properties and methods you have created in the form code after the form itself has been unloaded.

`Form_Terminate` - This event will occur when all references to the form are terminated by going out of scope or with the Set frmXXX = Nothing syntax. To ensure you are cleaning up memory after you unload the form, you should set the form reference to Nothing. If you don't need access to any methods or properties, you can add this line to the Unload event:

```vb
Set frmPerson = Nothing
```

Note: You cannot use the Me key word here. You have to set the form reference to Nothing.

### What is the best way to validate user-entered data?

*I would like to perform field-by-field validation. However, using the LostFocus event for this causes many problems in my application. Is there an easier way to perform field-by-field validation?*

Visual Basic 6.0 added a new Validate event and CausesValidation property to aid in field-by-field validation. To use the new Validate event, set the CausesValidation property to True for each field that could receive focus, which luckily is the default value for that property. As you leave a field, the Validate event is then generated before any of the focus events (such as LostFocus) are generated. This allows you to validate the data before actually losing focus from the field.

If you want to have a field on the form that the user can select without going through any validation, you can set the CausesValidation property to False for that field. For example, if you have a Help or Cancel button, you want to allow the user to select the button without having the current field validated. So set the CausesValidation property for the Help or Cancel button to False. When the user leaves a field and clicks the Help button, the user will be able to view the help without first validating the field.

The Validate event has a Cancel parameter. You can set this parameter to True if you want to keep focus on the field that is in error. Alternatively, you can set the Cancel parameter to False (the default) if you want to allow the end-user to continue entering data without immediately correcting the problem.

You may want to use the Validate event without using the Cancel parameter. If an error occurs during validation, you can set the field’s Forecolor property to red and modify the ToolTipText property to display the specific error message for that field. That tells the user something is wrong without interrupting the data entry flow.

Here is a simple example:

```vb
Private Sub txtBook_Validate(Index As Integer, Cancel As Boolean)

  Dim sErr as String
  Select Case Index
    Case idxYear
      If Len(txtBook(idxYear).Text) <> 4 then
        txtBook(Index).ForeColor = vbRed
        txtBook(Index).ToolTipText = "For Y2K compliance, the year must be four characters"
      End If
  End Select
End Sub
```

Issues/comments:

* It appears that the Validate event is not fired if you have a default button set. This is not actually true. If you make a button the default button and put code in the Validate event, the code will execute. This appears not to work because normally, the default button is the OK button. The code in the OK button Click event normally contains the statement Unload Me. This unloads the form and prevents the Validate event from executing. To ensure the last field is validated, use the Me.ValidateControls in the OK Click event before the Unload Me statement.
* You can use your business object to provide the validation by calling the Property Let procedure from the Validate event. A shortcut to doing this is to use the new CallByName feature of VB. For details, see the Programming with Class column in the July 1999 edition of the Visual Basic Programmers Journal or click here for an example.

### How can I prevent partially painted windows?

*Sometimes when you display a form only some of the controls appear. After a pause the remaining controls appear. This does not have a professional look.*

This has become much less apparent in VB 5.0 because of dramatic improvements in screen painting.

When showing a non-modal form, use the following code:

```vb
frmPerson.Show vbModeless
frmPerson.Refresh
```

The Refresh method will ensure that the form repainting is complete before executing any other code in the routine.

### How do I make a form top most so it appears over all other windows?

It will also work with 32-bit if the setWindowPos function is changed to the 32-bit version.

*Some windows should appear on the top, over the other windows in an application. A splash screen is an example of this type of form. Normally, you would want the splash screen to appear on top and your main form to build behind it. But how do you do that in VB?*

Code:

```vb
'Declares for formSetTopMost
Declare Sub setWindowPos Lib "User" (ByVal hWnd%, ByVal hWndInsertAfter%, ByVal X%, ByVal Y%, ByVal cx%, ByVal cy%, ByVal wFlags%)

' SetWindowPos() hwndInsertAfter values
Global Const HWND_TOPMOST = -1
Global Const HWND_NOTOPMOST = -2
' SetWindowPos Flags
Global Const SWP_NOSIZE = &H1
Global Const SWP_NOMOVE = &H2
Global Const SWP_NOACTIVATE = &H10

' Sets a window to topmost or non-topmost
' Parameters:
' frmtop form to be made topmost/ non-topmost
' isTopMost true if the form is to be made topmost
' false to reset the form to normal
Sub SetTopMostForm (frmTop As Form, isTopMost As Integer)
   ' Turn on topmost
   If isTopMost Then
     ' Set the toolbox to topmost window
     Call setWindowPos(frmTop.hWnd, HWND_TOPMOST, 0, 0, 0, 0, SWP_NOSIZE Or SWP_NOMOVE Or SWP_NOACTIVATE)
   Else
     ' Set the toolbox to topmost window
     Call setWindowPos(frmTop.hWnd, HWND_NOTOPMOST, 0, 0, 0, 0, SWP_NOSIZE Or SWP_NOMOVE Or SWP_NOACTIVATE)
   End If
End Sub
```

### How do I lock a form in place so the user can't size or move it?

NOTE: This requires a tool such as MessageBlaster or SpyWorks to subclass the window to be locked. This example used the SpyWorks control..

*There are situations in which you want to allow a user to size a form vertically but not horizontally. Or you may want to prevent the user from moving it.*

The code in this example demonstrates how to snag the size and move messages. You could modify it to only trap those messages that you want to ignore.

Code:

```vb
'Locks a window in place by snagging all of the move messages. NOTE: requires subclassing of the window to be locked.
Global Const WM_SYSCOMMAND = &H112
Global Const SC_SIZE = &HF000&
Global Const SC_MOVE = &HF010&

Global g_bLock As Integer

Sub SubClass1_WndMessage (wnd As Integer, msg As Integer, wp As Integer, lp As Long, retval As Long, nodef As Integer)

  Select Case msg
    Case WM_SYSCOMMAND
      If g_bLock = true Then
        If (wp And &HFFF0) = SC_MOVE Or (wp And &HFFF0) = SC_SIZE Then
          nodef = True
        End If
      End If
  End Select

End Sub
```

NOTE: With VB 5.0 forms have a Moveable property. You can set this to false to prevent the user from moving the form. You can set the BorderStyle to a nonsizeable style to prevent the user from sizing the form.

### How can I load my MDI child forms without showing them?

*My MDI child form contains many controls that I want to preload with data. So I want to load these when the application is started, but I don't want to show them until the user requests them. How can I do that?*

Starting with VB 4.0, MDI forms have a new property: AutoShowChildren. If this property is set to True, MDI works has it has before ie. MDI child forms are shown as soon as they are loaded. If this property is set to False, the MDI child forms can be loaded without being shown.

```vb
Private Sub MDIForm_Load()
  MDIForm1.AutoShowChildren = False
  Load Form1
End Sub
```

NOTE: With VB 5.0, the speed of form display is significantly improved. So you no longer need to use this technique just to display child forms more quickly. This technique is still useful for preloading data into MDI child forms.

### How can I change the default font used for controls?

*If you don't like the default font used for your controls, you can add them all to your form and then change each one. Is there an easier way?*

Yes! You can change the default font of the form first, then put the controls on it. That way the controls will use the form's font as its initial value.

### How can I preselect an entry in a combo box?

*When filling a form with pre-existing data, it would be nice to also preselect entries in any combo boxes on the form. When the user drops down the combo box, the currently selected entry will then appear.*

In VB 3.0, you had to either search through the entries in the combo box using a loop or use the Windows API to find and preselect an entry. If you then selected the entry using the .listIndex property, the Click event on the combo box would get fired and you had to have special code to determine when you caused the click event versus the user selecting an entry from the combo box. With VB 4.0 it is easier.

Simply set the Text property of the combo box. Watch out, however, because if the entry is not in the combo box VB will generate a "Text property is read-only" type of error message. By the way, this also works with list boxes.

```vb
cboState.Text = "CA"
```

### Why can't I pass a control to a subroutine?

*I want to be able to pass a Visual Basic control to a subroutine to perform standard processing. The code is as follows:*

```vb
  doFormat (txtPerson)
```

Why doesn't this work?

In VB, expressions in parenthesis are evaluated before they are processed. So by putting parenthesis around the control name, you are telling it to evaluate it. Since a control cannot be evaluated, it gives you the value of the default property. The above code is actually passing the Text value (since Text is the default property) to the subroutine instead of passing the control.

There are two ways to make this work appropriately.

```vb
  Call doFormat(txtPerson)
```

or

```vb
  doFormat txtPerson
```

### How do I pass a control array to a subroutine?

*I want to be able to pass a Visual Basic control array to a subroutine to perform standard processing.*

The code in this example passing a control array txtPerson( ) to a subroutine.

```vb
Private Sub Form_Load()
  Test txtPerson()
End Sub

Sub Test(ctrlArr As Object)
  Dim txt As TextBox
  For Each txt In ctrlArr
    Debug.Print txt.Index
  Next
End Sub
```

The trick here is to pass the control array As Object.

### Is there a suggested way to set the mouse pointer?

*I know that I should set the mouse pointer to an hour glass when I am executing long operations. What is the suggested way to do this?*

> This tip was a joint effort by the VBPJFO CompuServe forum section leaders.

The code in this example uses a mouse pointer class to set the mouse pointer.

```vb
Private m_nPointer As MousePointerConstants

Public Sub SetCursor(Optional nPointer As MousePointerConstants = vbHourglass)
  Screen.MousePointer = nPointer
End Sub

Private Sub Class_Initialize()
  m_nPointer = Screen.MousePointer
End Sub

Private Sub Class_Terminate()
    Screen.MousePointer = m_nPointer
End Sub
```

This class can then be used by creating an instance of this class and then setting SetCursor to the desired value (vbHourglass is the default).
