[Home](https://gotbasic.com) • [VB 7+](vb.md) • VB 1-6 • [FB](freebasic.md) • [QB64](qb64.md) • [QB45](qb.md) • [GW-BASIC](gw-basic.md) • [Micro](micro.md) • [Retro](retro.md)

## Understanding Data Binding

### What is Data Binding?

*I have heard a lot about data binding with VB6. What is it and when do I use it?*

Data binding is the process of connecting any ADO/OLE-DB data source to any ADO/OLE-DB data consumer. With prior versions of VB, the only data source was a data control. Now there are other ways to create a data source:

* You can use the new ADO Data Control.
* You can add a Data Environment designer to your project and specify the connections and commands that define a recordset.
* You can build a data-aware class that acts as a data source by specifying the DataSourceBehavior property of the class to be vbDataSource.
* You can use a pre-built recordset as a data source.

With VB6, you can bind the data source directly to controls on form by setting the DataSource property of the control to the name of the ADO data control, name of the Data Environment designer, name of the object variable defined for the data-aware class, or the recordset itself.

In addition to binding to controls, you can also bind to properties of a class. A class with bound properties is also called a data-aware class, but this type of data-aware class is a data consumer. To create a data consumer, you set the DataBindingBehavior property of the class to be vbSimpleBound (for normal properties) or vbComplexBound (for grids and such). Class properties can only be bound to a data-aware class. You can create one class that is both a data consumer and a data provider.

### How do I bind text boxes to a FlexGrid?

*I want to put a FlexGrid on my form to display a set of records. When the user selects a record, I would like the data to appear in a set of text boxes. I assumed that if I bound the FlexGrid and text boxes to the same recordset, that this would work. However, it does not. What am I doing wrong?*

The FlexGrid is not truly bound to the recordset. Rather, the FlexGrid simply reads the data from the recordset and populates the grid. It is then no longer really associated (or bound) to the recordset. The FlexGrid does not respond to navigation or update events fired by the recordset.

Why is the DataSource property there then, you ask? It is there to simplify your coding so you don't have to manually deal with setting the correct number of rows and columns and using GetString on the recordset to set the Clip property of the FlexGrid.
