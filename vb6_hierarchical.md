[Home](https://gotbasic.com) • [VB 7+](vb.md) • VB 1-6 • [FB](freebasic.md) • [QB64](qb64.md) • [QB45](qb.md) • [GW-BASIC](gw-basic.md) • [Micro](micro.md) • [Retro](retro.md)

## Understanding Hierarchical Recordsets

### What is a hierarchical recordset?

*I've been hearing about hierarchical recordsets. What are they?*

A hierarchical recordset is a recordset that is comprised of a hierarchy of records. For example, any recordset with a parent/child relationship can be defined as a hierarchical recordset. Unlike a join which basically duplicates all of the parent data for each child, each record in a hierarchical recordset contains the set of parent fields and one field which is the child recordset.

A typical example is an order for goods or services with several line items in the order.  In the past, in order to display order information and detail information from each line, we either had to fetch two recordsets (one for order information, one for detail information) or a single, joined recordset in which the order header information was unnecessarily repeated in each row.

With hierarchical recordsets, you fetch all this information in a single query.   Furthermore, if you happen to fetch multiple orders, the child records will already be organized and attached to their specific parent record, without repeating data.

When you fetch a hierarchical recordset, the parent recordset will contain an extra field, which is the recordset of the detail records associated with that row in the parent recordset. Furthermore, hierarchical recordsets can be nested--companies can have divisions, divisions can have groups, groups can have individuals, etc.

As another example, think of the Biblio database that is provided with Visual Basic. In that database, a publisher has a set of titles. You could define a hierarchical recordset that contained one record for each publisher. Each record contains the set of publisher data fields plus one field containing the recordset of all titles for that publisher.

### What is the difference between building a hierarchical recordset and data shaping?

*I have also been hearing about data shaping. How is that different from a hierarchical recordset?*

Visual Basic builds hierarchical recordsets via the MSDataShape provider, which is new with ADO 2.0. Data shaping involves writing the correct SQL statement to shape the data into a hierarchical recordset.

### How do I create a hierarchical recordset?

*I think I basically understand what a hierarchical recordset is. Are they hard to build?*

First, a note. Hierarchical recordsets are only supported by ADO 2.0 or higher.  So you must reference ADO 2.0 (or higher) in your project and use an ADO connection to open a hierarchical recordset

The easiest way to build a hierarchical recordset is to use the Data Environment designer. Simply add a command to the Data Environment designer for the parent recordset and a second command for the child recordset. Then modify the child recordset relation properties to relate it to the parent recordset. Be sure to add a relation definition defining the key relationship between the parent and the child.

The hierarchical recordset will then appear as a tree view in the Data Environment designer. Right click on the parent recordset and select Hierarchy Info to view the associated data shape command.

For the Biblio example of publisher and titles, the data shape command is:

```txt
SHAPE {SELECT * FROM `Publishers`} AS cmmPublishers _
APPEND ({SELECT * FROM `Titles`} AS cmmTitles RELATE 'PubID' TO 'PubID') AS cmmTitles
```

If you want to build them yourself, when opening an ADO connection to create a hierarchical recordset, you must specify MSDataShape as the Provider. Since MSDataShape is the provider, you must separately specify a Data Provider, such as Microsoft.Jet.OLEDB.3.51. A typical connect string (for a database with no security attached to it) would be:

```vb
  sConnect = "Data Source = " & sFileName & "; " & _
    "Provider = MSDataShape; " & _
    "Data Provider = Microsoft.Jet.OLEDB.3.51; "
```

The SQL command to create a hierarchical recordset takes the following generic form:

```txt
  SHAPE {[Parent Query]} APPEND ({[Child Query]} AS [Alias] RELATE [Parent Field] to [Child Field])
```    

Note that the required delimiters surrounding the two queries are curly brackets, not parentheses.

A typical query might be:

```txt
  SHAPE {SELECT * FROM Orders} APPEND ({SELECT * FROM Details} AS Details RELATE OrderID to OrderID)
```

For more information on creating hierarchical queries, see Knowledge Base Article ID: [Q189657, HOWTO: Use the ADO SHAPE Command](http://web.archive.org/web/20080212123129/http://support.microsoft.com/support/kb/articles/Q189/6/57.asp)

You can also download a sample application demonstrating hierarchical queries from the section on Hierarchical Recordset Performance Issues.

### How do I create a form that uses a hierarchical recordset?

*OK, now I have this hierarchical recordset in the Data Environment designer. How do I use it on a form?*

Simply drag and drop the parent recordset from the Data Environment designer to a form. Visual Basic automatically creates text boxes for each field in the parent recordset and a FlexGrid for the child recordset.

NOTE: The FlexGrid is not updateable.

You can then run the application and the form will appear with the data for the first record.

### How do I move to another record?

*Cool! I now have a form that displays a record. How do I move to another record?*

You need to write a little code to move to another record in the hierarchical recordset. First, add a Next button to the form. Then add the following line of code in the Click event procedure for the button:

```vb
deBiblio.rscmmPublishers.MoveNext
```

The deBiblio object variable is the name of the Data Environment designer. cmmPublishers is the name of the command. Visual Basic automatically creates an object variable for the recordset resulting from a command defined by the Data Environment designer. This recordset object variable is has a prefix of "rs" attached to the name of the command. To move to the next record in that recordset, execute the MoveNext.

### How do I access the child recordset?

*So I can access the parent recordset simply by referencing the recordset object variable provided by the Data Environment designer. How do I reference the child recordset with code?*

Since the child recordset is just a field in the parent recordset, you can access it as follows:

```vb
Dim rsChild As Recordset
Set rsChild = deBiblio.rscmmPublishers.Fields("cmmTitles").Value
```

The deBiblio object variable is the name of the Data Environment designer. rscmmPublishers is the name of the recordset associated with the cmmPublishers command. cmmTitles in the command for the titles. It is also the name given to the field containing the Titles recordset.

NOTE: You cannot use the bang ("!") syntax here. The following will give you a syntax error:

```vb
Dim rsChild As Recordset
Set rsChild = deBiblio.rscmmPublishers!cmmTitles
```

NOTE: You cannot access the child recordset without first assigning it to a recordset object variable. The following will give you a syntax error:

```vb
Text1.Text = deBiblio.rscmmPublishers.Fields("cmmTitles").Value.Fields("title").Value
```

### How do I create an updateable form?

*OK, now I can move through my table and reference my child recordset in code. However, I cannot seem to update. How do I create an updateable form?*

There are several things that you need to do to make your form updateable:

* On the Advanced tab of the Properties dialog box for the parent command, change the Lock Type to optimistic.
* As stated previously, the FlexGrid that is automatically added to your form for child recordsets is not updateable. To build a form that is updateable, you can use the right mouse button to drag and drop the recordsets from the Data Environment to the form. You will then have the option of which type of controls to use on the form. Using the Data Grid provides an updateable grid.

### What if I use the BatchOptimistic Lock Type instead?

*I want to use BatchOptimistic locking to send all of the changes at one time. However, as soon as I set this my changes are no longer saved. How do I create an updateable form that uses BatchOptimistic locking?*

When you set the Lock Type to BatchOptimistic, you then have to manage the code for the update yourself. To do this, add the following code to the Unload event in the form:

```vb
Private Sub Form_Unload(Cancel As Integer)
  Dim rsChild As Recordset
  ' save the updates
  deBiblio.rscmmPublishers.UpdateBatch
  Set rsChild = deBiblio.rscmmPublishers.Fields("cmmTitles").Value
  rsChild.UpdateBatch adAffectAllChapters
End Sub
```

Notice that this code requires two UpdateBatch commands. The first UpdateBatch updates the parent recordset. The second UpdateBatch updates the child recordsets. The adAffectAllChapters parameter ensures that all child recordsets associated with all recordset in the parent recordset are updated. Without it, only the child recordset associated with the current parent will be updated.

NOTE: You must also move from the record for the record to be updated. Changes made to the current record are ignored. (I am hoping this is a "bug" that will be fixed and is not "by design"!)

### Hierarchical Recordset Performance Issues

*I tried a hierarchical query using SHAPE and it takes a long, long time!*

You have to be careful when designing SHAPE queries, particularly with how you specify the child query.  Absent a parameter passed to the child query (more on that later), the child query neither knows nor cares what the parent query returns.  A SHAPE query is more or less two independent queries.  The SHAPE command just takes the results of those queries and organizes them into an object hierarchy that is easy to use and manipulate.

For instance, take a query like:

```txt
  SHAPE {SELECT * FROM Orders WHERE PO_Number = 123} APPEND ({SELECT * FROM Details} AS Details RELATE OrderID to OrderID)
```

The child query will return all the rows in the Details table, even though it only needs the few rows associated with Purchase Order 123. The SHAPE command will filter out the unneeded records, so the resulting recordset will look absolutely correct.  In fact, if you have small tables (up to several thousand on a fast machine with a local database), you won't notice any problems whatsoever. But with large tables and recordsets, the difference is dramatic.

The solution is to constrain the child query in a manner similar to the constraint in the parent query.  Instead of the above query, try the following:

```txt
  SHAPE {SELECT * FROM Orders WHERE PO_Number = 123} APPEND ({SELECT * FROM Details WHERE OrderID IN (SELECT OrderID FROM Orders WHERE PO_Number = 123} AS Details RELATE OrderID to OrderID)
```

  or

```txt
  SHAPE {SELECT * FROM Orders WHERE PO_Number = 123} APPEND ({SELECT Details.* FROM Details INNER JOIN Orders ON Details.OrderID = Orders.OrderID WHERE PO_Number = 123} AS Details RELATE OrderID to OrderID)
```

If you are displaying a single or very small amount of parent records, the best choice may be a parameterized child query:

```txt
  SHAPE {SELECT * FROM Orders WHERE PO_Number = 123} APPEND ({SELECT * FROM Details WHERE PubID = ?} AS Details RELATE OrderID to PARAMETER 0)
```

Be careful with parameterized child queries! The queries themselves execute very fast.  This is because, unlike the other queries, with a parameterized child query the child query is never executed unless and until the child recordset is accessed. This also means that the child query is separately executed each time a child recordset is accessed (repeated visits to the same child recordset are cached, however).  If you are accessing more than a few child recordsets, the other JOIN and IN-Clause queries are just as efficient; if you are accessing many child recordsets, the JOIN and IN-Clause queries are much more efficient.

Please download the [Shape Demonstration project](images/ShapeDemo.zip), which illustrates the issues raised in these Tips and Tricks.

See also Knowledge Base Article ID: [Q196968, PRB: SHAPE Provider Pulls Down All Records in Child Table](http://web.archive.org/web/20080212123129/http://support.microsoft.com/support/kb/articles/q196/9/68.asp)
