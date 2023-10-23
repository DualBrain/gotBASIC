[Home](https://gotbasic.com) • [VB 7+](vb.md) • VB 1-6 • [FB](freebasic.md) • [QB64](qb64.md) • [QB45](qb.md) • [GW-BASIC](gw-basic.md) • [Micro](micro.md) • [Retro](retro.md)

## Common Database Questions

### What is Universal Data Access?

*I have just barely gotten used to ADO, now Microsoft is talking about UDA? What is that and how is it different from ADO.*

Universal data access is a philosophy whereby a developer should be able to use one tool to access any type of data from any data source. Microsoft is realizing this dream through the new database access technology called OLE-DB. OLE-DB is a set of COM interfaces that provide access to data stored in diverse information sources, both relational and nonrelational.

Most of us did not program directly to ODBC, but instead used data access objects (DAO) or remote data access objects (RDO) to access the data through ODBC. The same is true with OLE-DB. Most developers will use the ActiveX Data Objects (ADO) to access data through OLE-DB.

### What is ADO?

*I have been hearing a lot about ADO. What is it?*

ADO is ActiveX Data Objects. This is a new object model for accessing data from any type of datasource. You can use it in place of data access objects (DAO) or remote data objects (RDO).

The benefits of this technology over DAO and RDO are as follows:

* It provides one standard object model for accessing any type of data source
* The object model is VERY simple, yet powerful
* In many cases, you can get better performance using ADO over the other choices
* You can define and use disconnected recordsets

### Where do I find ADO?

*I cannot find ADO on my VB 4.0 or VB 5.0 CD. Where do I find it?*

ADO 2.0 comes with Visual Basic 6.0 ADO did not come with Visual Basic 5. To download ADO, link to: [www.microsoft.com/data](https://www.microsoft.com/data)

## What is a connection?

*I cannot find any "OpenDatabase" command in ADO. I heard that I am now supposed to use connections. What are connections?*

A Connection object in ADO is a comparable to a Database object in DAO. The Connection object manages the actual connection to the database. It defines the ODBC or OLE DB driver to use, the path to the database, and any login information. Once you establish a connection to a database, you can build recordsets or issue commands using that connection

### Do I need to close the connection manually if I am using MTS?

*I understand that Microsoft Transaction Server (MTS) pools connections. That is, it creates connections and then reuses them for different users, thereby minimizing the scare connection resources and improving efficiency in making connections. To use this feature from my Visual Basic code, do I have to close the connection or does MTS do that for me?*

When building objects for MTS, you want each method call that requests data to open the connection, retrieve the desired data, and close the connection. When you issue the open, MTS will give you a connection from the pool. When you close the connection, MTS returns the connection to the pool. If you don't close the connection, your application will not release the connection for MTS to reuse.

### What is a disconnected recordset?

*I have heard about disconnected recordsets. What are they and when should I use them?*

A disconnected recordset is a recordset that has been disconnected from its original connection. The recordset can then be efficiently marshaled between components without maintaining a connection. These are useful when passing data between components in a three-tiered architecture.

To build a disconnected recordset, you need to define the CursorLocation as adUseClient before opening the recordset, then open and build the recordset, and then disconnect using Set rs.ActiveConnection = Nothing.

NOTE: If you are using MaxRows, a disconnected recordset will not know how to get the next set of rows.

### How do I create a recordset which contains concatenated fields?

*I want to bind my list box to a recordset. However, I want to display two fields concatenated together, like "Jones, Barbara". How can I do this?*

You can use a calculated expression in the SQL statement of the query.

```sql
SELECT PersonID, LastName, FirstName, LastName + ', ' + FirstName AS FullName FROM Person ORDER BY LastName, FirstName
```

### How do I build a "Like" SQL statement?

*I am building an SQL string to access a Microsoft Access database. I would like to find all names that are like a particular pattern. For example, all names that begin with "M". I cannot seem to get the correct syntax.*

Two important things to remember when working with the SQL Like clause: 1) be sure to use single and not double quotes 2) For Microsoft Access, the wild card character is "%" and not "*".

For example, to select all publishers from the Biblio database that begin with an "M", us the following SQL statement:

```sql
SELECT Name FROM Publishers WHERE name LIKE 'M%'
```

### Why doesn't RecordCount provide the correct number of records in a recordset?

*When accessing the RecordCount from a recordset, the RecordCount does not always provide the correct number of records in the recordset. Why is that?*

The RecordCount returns the number of records that Visual Basic currently knows about. To ensure the count is correct, you need to move through all of the records.

```vb
rs.MoveLast
iCount = rs.RecordCount
```

### What is a Cursor?

*Someone told me I should be using client-side cursors. I don't even know what a cursor is. Can you describe them?*

A cursor exposes the set of data resulting from a query as a set of rows in a sequential file. This makes it easier to track your current position within that data and navigate through the data. With most cursors you can handle data access requirements like reading, inserting, updating, and deleting selected data. Normally what you think of as your recordset is really a cursor exposing the logical set of data returned from your query.

There are several types of cursors:

* Forward-only cursor. Can only move forward through the result set. Forward-only cursors don't support scrolling. In most implementations (such as SQL Server) changes made to records are visible when the record is fetched. Forward-only cursors provide the best way for retrieving data quickly and efficiently.
* Static cursor: Always displays the result set as it was when the cursor was first opened. Static cursors normally detect their own updates, deletes, and inserts. However, they don't detect other updates, deletes, and inserts. Static cursors are recommended if your application needs to scroll both forward and backward and does not need to detect changes make by other applications or other users.
* Keyset cursor: Can detect changes to row values, but cannot detect additions and deletions made by other applications.. A keyset is the set of unique key values from all of the rows returned by a query. With keyset-driven cursors, a key is built for each row in the cursor and stored on the client or on the server. When you access a row, the key is used to retrieve the row values from the database. Keyset cursors are useful if your application is not concerned with concurrent updates, can programmatically handle bad keys, and must directly access certain keyed rows.
* Dynamic cursors: Detect all changes made to all rows in the result set. Dynamic cursors don't support bookmarks because they do absolute fetching, ie. fetching specific row numbers. Dynamic cursors are not normally recommended due to their large overhead.

You can define the location where the cursor will hold its data::

* Client-side cursor: The resources for the cursor are located on the client machine. With a non-keyset client-side cursor, the server sends the entire result set across the network to the client machine. The client machine provides and manages the temporary resources needed by the cursor and result set. The client-side application can browse through the entire result set to determine which rows it requires. There may be a performance hit in fetching large result sets. After the result set has been downloaded to the client machine, browsing through the rows is very fast.
* Server-side cursor: The resources for the cursor are located on the client machine. Server-side cursors only return requested data over the network. This can perform well in situations where there is heavy network traffic. However, server-side cursors can be slow because they only work on one row at a time, no batch updates.

### What is a Data Link?

*The Data View window allows me to create data links. What are they and when do I use them?*

A data link with OLE DB is similar in concept to a DSN for ODBC. It provides a mechanism for defining a connection to a specific database using a specific OLE DB driver.

You can create a data link several ways:

* Within the Data View window. Data links created here are stored in your registry and are available to all projects that you open.
* With Explorer (File | New | Microsoft Data Link). Files you create the Explorer cannot be used within the Data View window. They can be used when creating a connection by using the following syntax for your ConnectionSource property: "File Name = C:\Path\MyLnk.UDL". Data link files created in this fashion can be distributed with your application using the Package and Deployment wizard.
* By right-clicking in any directory and selecting New | Microsoft Data Link. This is a short-cut to the previous technique.
