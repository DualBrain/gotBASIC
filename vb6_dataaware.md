[Home](https://gotbasic.com) • [VB 7+](vb.md) • VB 1-6 • [FB](freebasic.md) • [QB64](qb64.md) • [QB45](qb.md) • [GW-BASIC](gw-basic.md) • [Micro](micro.md) • [Retro](retro.md)

## Understanding Data Aware Classes

### What is a data aware class?

*I've been hearing about data aware classes. What are they?*

A data aware class is a class that manages data. A data aware class can be a data source and provide data to other parts of an application. Or a data aware class can be a data consumer and bind class properties to a data source. Or a data aware class can be both a data source and data consumer.

### How do I change the recordset of a data aware class?

*I created a data aware class as a data source. I want to change the recordset associated with that data source at design time. How do I do that?*

To make sure the problem is clear, let's start with an example. Say that you create a data aware class that knows how to locate a record from the Biblio database for one author, where the author ID is defined as a parameter to the query used by the data aware class. Then the user selects to retrieve a different author. How do you tell the data aware class to reget the recordset using the new ID? Since GetDataMember is an event, you can't just call it.

The answer is to use the DataMemberChanged method. In the data aware class, call the DataMemberChanged method providing the name of the data member that changed. The next time a data consumer requests that data member, the data aware class will regenerate the GetDataMember event which in turn should retrieve the revised recordset.

### How do I get my data aware class to work within an ActiveX EXE?

*I created a data aware class as a data source within my project. Now I want to make that project an ActiveX EXE. As soon as I change the project type to ActiveX EXE, the DataSourceBehavior property of the class disappears and I cannot make it data aware. I can make the project into an ActiveX DLL and it works fine. Why can't I make it into an ActiveX EXE?*

Data sources can only be in process. This is because the IDataSource and some of the OLEDB interfaces cannot be remoted across processes/machines. As a result, you can only have a data source in:

* a standard EXE
* an ActiveX DLL
* a Usercontrol (since its in process)
* a private class in an ActiveX EXE

### What is a complex bound class?

*I plan to do property binding and see that the DataBindingBehavior property gives me the choice to use complex binding. What is that?*

Complex bound means that you work with the whole recordset in your data consumer. For example, a DataGrid is complex bound because it manipulates and displays the whole recordset.

To create a complex bound class:

* Set the `DataBindingBehavior = 2 - vbComplexBound``.
* You will see procedure stubs added to your class. In addition, VB automatically sets a reference to Microsoft Data Source Interfaces.
* Set a reference to ADO.
* Add the following code to the class module:

```vb
  Private rs As New ADODB.Recordset
  Private m_DataMember As DataMember

  Public Property Get DataMember() As DataMember
    DataMember = m_DataMember
  End Property

  Public Property Let DataMember(ByVal DataMember As DataMember)
    m_DataMember = DataMember
  End Property

  Public Property Get DataSource() As DataSource
    Set DataSource = rs.DataSource
  End Property

  Public Property Set DataSource(ByVal DataSource As DataSource)
    rs.DataMember = m_DataMember
    Set rs.DataSource = DataSource
    ' do something with the data now in this recordset
  End Property
```
