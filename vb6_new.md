[Home](https://gotbasic.com) • [VB 7+](vb.md) • VB 1-6 • [FB](freebasic.md) • [QB64](qb64.md) • [QB45](qb.md) • [GW-BASIC](gw-basic.md) • [Micro](micro.md) • [Retro](retro.md)

## Want to see what is new in VB6?

Most of the information below is from the book *Doing Objects in Visual Basic 6* by Deborah Kurata (SAMS).

## Known Bugs/Issues

There have been some reported bugs and issues with VB6. [Click here for a list of them](http://web.archive.org/web/20080212122832/http://www.insteptech.com/techLibrary/vbClassic/vb6_bugs.htm).

Microsoft has also announced VB6/SP6. For information on that release, see: http://msdn.microsoft.com/vstudio/sp/default.asp

## New Database Features: Tools and Binding

Visual Basic 6 provides some very nice new database tools and technologies:

* ADO. Visual Basic now fully supports ActiveX Data Objects ([ADO](http://web.archive.org/web/20080212122832/http://www.insteptech.com/techLibrary/vbClassic/vb6_db.htm#DB_ADO)) 2.0. See Chapter 14, "Do Database Objects," for information on ADO.
* Hierarchical cursors/Data shaping. Writing code to handle database parent/child relationships was always a challenge. With ADO 2.0, you can now use data shaping to develop [hierarchical recordsets](http://web.archive.org/web/20080212122832/http://www.insteptech.com/techLibrary/vbClassic/vb6_hierarchical.htm). These cursors define parent/child relationships and provide a single recordset with the parent data and child data. See Chapter 14, "Do Database Objects," for a more detailed description of data shaping and examples for using it.
* Data View Window. This new window in the Visual Basic IDE provides a visual mechanism for establishing connections to your data and then viewing or modifying the data. When using SQL Server or Oracle, you can also access the Database Designer, Query Designer, and SQL Editor to view and change the structure of your database. This is project independent, so once you define your connections they appear in all of your projects. See Chapter 14, "Do Database Objects," for the details.
* Data Environment Designer. A Data Environment designer is a visual tool for defining ADO connections and commands for a project. It provides an easy way to define hierarchical cursors. You can drag and drop from the Data View window to add connections to your DE. You can drag commands from the DE to a form to automatically build a form that is bound to the DE. You can also access the Data Environment objects programmatically. The DE is defined on a per-project basis and is added to the Project window just like other project files. See Chapter 14, "Do Database Objects," for an example.
* Data binding. With VB6, you can now bind any ADO/OLE DB data source to any ADO/OLE DB data consumer with a technique called [data binding](http://web.archive.org/web/20080212122832/http://www.insteptech.com/techLibrary/vbClassic/vb6_databinding.htm#DB_DataBinding). With older versions of VB, you could only bind controls (data consumers) to a data control (data source). Now you can bind any control directly to recordset, to a Data Environment, to a data-aware class or to an ADO data control. See Chapter 7, "Implementation-Centered Design," and Chapter 14, "Doing Database Objects," for more information.
* Data-Aware Classes. Using a [data aware class](http://web.archive.org/web/20080212122832/http://www.insteptech.com/techLibrary/vbClassic/vb6_dataaware.htm), you can define a class to be a data source and bind controls directly to an instance of a class. Or, you can define a class as a data consumer and bind data fields directly to the properties of the class. See Chapter 14, "Doing Database Objects," for examples.
* Data Form Wizard. This wizard now provides three different techniques for binding data to a form. You can use the original technique of binding controls to a data control and then bind the fields to the data control. Or you can use the Wizard to bind the controls on a form directly to a recordset. This technique generates ADO code instead of linking to a data control. The third option generates a data-aware class and binds controls to the data-aware class. See Chapter 14, "Do Database Objects," for examples using the Data Form wizard.
* Data Report Designer. Microsoft provides its own report designer. This tool allows you to drag and drop information from the Data View window directly onto a report. Crystal Reports is still provided, but it is not automatically installed.
* Create recordsets on the fly. With ADO 2.0 you can now create recordsets in your code with any data. You can create the data in your application and dynamically create a recordset with that data. This allows you to provide recordsets to other parts of your application, even when you aren't accessing a database.
* Save recordsets to a file. With the new ADO 2.0 Save method, you can save a recordset to a flat file and later read the file back into a recordset using the Open method.
New Find method that uses internal indexes. If you have missed the Find method of DAO, ADO 2.0 now provides that feature.
* Improved error handling. If you were disappointed in some of the error messages you received from ADO 1.5, these have been enhanced to give you more information and more options for handling situations such as concurrency errors.

## New Web Features: Building Web Applications with VB

Visual Basic 6 provides the tools for developing client-side or server-side Web applications:

* DHTML Applications. Visual Basic provides a new type of application called a [DHTML application](http://web.archive.org/web/20080212122832/http://www.insteptech.com/techLibrary/vbClassic/vb6_dhtmlapp.htm). This allows you to create a client-side ActiveX component that provides dynamic Web applications. See Chapter 13, "Building ActiveX Components," for more information.
* IIS Applications. Visual Basic provides another new type of application called an IIS application. These are most commonly called WebClasses. This allows you to create a server-side ActiveX component that provides ASP-like Web applications. See Chapter 13, "Building ActiveX Components," for more information.

## New Object-Oriented Features: More Reasons to Go OO

Several new Visual Basic 6 features are specifically for the design and development of object-oriented applications:

* Array Properties. You can now define a property procedure that can return an array. You can also assign a dynamic array to any other dynamic array. [Click here for an example.](http://web.archive.org/web/20080212122832/http://www.insteptech.com/techLibrary/vbClassic/vb6_dataaware.htm)
* UDTs. You can now define a user-defined type (UDT) within a class and return a variable of the user-defined type from the class. Note, however, that this technique is restricted to Public classes. Chapter 10, "Building Your First Class," demonstrates how to create and use UDTs in a class.
* Data Aware classes. You can now define a class to be a data source and/or a data consumer. Examples of [data aware classes](http://web.archive.org/web/20080212122832/http://www.insteptech.com/techLibrary/vbClassic/vb6_dataaware.htm) will be posted soon.
* Class persistence. Using [class persistence](http://web.archive.org/web/20080212122832/http://www.insteptech.com/techLibrary/vbClassic/vb6_classpersistence.htm), you can now save the values of the properties of your class to a file and retrieve them the next time the user requests the object. This uses the PropertyBag to store and retrieve the properties. Chapter 11 " Building Classes: Additional Techniques," demonstrates this technique.
* CreateObject enhanced. CreateObject now has a parameter that allows definition of a remote machine on which to execute the component.

## New IDE Features

The Visual Basic 6 integrated development environment (IDE) is very similar to the VB 5 IDE. There are just a few more tools:

* **Revised VB Application Wizard**. The VB Application wizard can complete the entire framework for your application. It was enhanced and polished. This wizard is shown in Chapter 6, "User-Interface Design."
* **Revised Add-In Manager**. The new Add-In Manager allows you to load an add-in only for a session or load it whenever VB is started.. The Add-In Manager is shown in Chapter 11, "Building Classes: Additional Techniques."
* **Revised Class Builder Utility**. The VB Class Builder utility builds the classes of your application. It was enhanced to support Enums and additional types of Property procedures. However, it cannot handle Enums that contain equations such as vbObjectError+512+100. The Class Builder utility is demonstrated in Chapter 11, "Building Classes: Additional Techniques."
* **New Package and Deployment Wizard**. The old SetupWizard was replaced with the new Package and Deployment wizard, discussed in Chapter 15, "Putting the Pieces Together".
* **API Viewer Add-In**. The API Viewer provides the list of Windows API function names and required constants. This supporting application has been around for a while. With Visual Basic 6, it has been added to the Add-Ins. See Chapter 15, "Putting the Pieces Together," for more information.
* **Resource Editor Add-In**. In prior versions of Visual Basic, you had to create a resource file using a text editor tool, compile it with a resource editor compiling tool, and then include the compiled file in your project. Visual Basic 6 provides an add-In that allows you to create the resource file directly in your Visual Basic project. See Chapter 15, "Putting the Pieces Together," for more information.
* Toolbar Wizard. The new Toolbar wizard simplifies creating of a toolbar by giving you more standard icons and by generating the code to respond to the toolbar selection. This wizard is discussed in Chapter 15, "Putting the Pieces Together".
* Help. The help is now HTML.

## Other New Features: An Assortment of Enhancements

Here are some other new features that are important to mention:

* New Controls. There are several new controls and enhancements to existing controls. Of most interest is the Date/Time Picker, Hierarchical FlexGrid, and the Coolbar control, which gives you the IE toolbars. There is also an ADO Data Control.
* Validate event. No more attempts to validate field entry in the LostFocus event. There is now a [Validate event](http://web.archive.org/web/20080212122832/http://www.insteptech.com/techLibrary/vbClassic/vb6_forms.htm#Win_Validate) for your data validation.
* Dynamic control creation. If you tried to create the controls for a form in the past, you had to add at least one of each type of control, and then use the Load function to load them. Now you can dynamically build a form from formlessness. A cool example using a database to build a form is provided with the sample code.
* String handling. There many new string handling functions added to the language.
CallByName. CallByName is a very useful function that allows you to call a procedure by its name. [An example is available.](http://web.archive.org/web/20080212122832/http://www.insteptech.com/techLibrary/vbClassic/vb6_lang.htm#Lang_CallByName)
* FileSystem objects. These provide access to the directory and file system.
* Dictionary object. The dictionary is an improved collection. [Here is more information.](http://web.archive.org/web/20080212122832/http://www.insteptech.com/techLibrary/vbClassic/vb6_oo.htm#Obj_Dictionary)
* Format object. Allows formatting of the data between the time it is retrieved and the time it is displayed in a bound control.

## Compatibility issues

There are some issues with running VB6 with VB5. Specifically with the following components:

* APE.
* Visual Data Manager.
* T-SQL Debugger.
* Remote Data Control.
* API Text Viewer.

## What's Not There?

And last but not least, what isn't there is often of importance:

* No inheritance. There is no inheritance in VB6.
* No WithEvents for a control array. We keep hoping for this one.
* No ability to ask a class for its interface. Especially with the CallByName, it would be nice to be able to ask a class for its list of properties and methods without resorting to API calls.
* No new error handling tools. There was hope for some type of global error handling, but there were no improvements in this area. The only thing news about error handling are techniques for dealing with the new technologies, such as debugging the IIS applications and debugging components under MTS.
* No new debugging features. Not even a button to clear the Immediate window.
* No new Menu Editor. That is one piece of code that does not seem to have been touched since VB 1.0.
