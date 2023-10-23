[Home](https://gotbasic.com) • [VB 7+](vb.md) • VB 1-6 • [FB](freebasic.md) • [QB64](qb64.md) • [QB45](qb.md) • [GW-BASIC](gw-basic.md) • [Micro](micro.md) • [Retro](retro.md)

## Understanding DHTML Applications

#### What is DHTML?
*I've been hearing about DHTML. What is it?*

DHTML stands for dynamic hypertext markup language. The standard hypertext markup language, HTML, is basically a tag-based formatting language used frequently on Web pages. It allows you to specify the style and content of a Web page using simple tags. For example:

```html
<p><font size="3">We have also found some DHTML features that don't seem to work correctly: </font></p>
```

The `<p>` at the beginning defines the start of a paragraph. The `</p>` defines the end of the paragraph.

Dynamic HTML allows for changing of the Web page style and/or content on the client side without going to the Web server. This is possible because of the DHTML object model, which exposes the different styles and page contents.

### What is a DHTML Application?

*Is DHTML and a DHTML application the same thing?*

This one depends on your point of view. From the Visual Basic point of view, a DHTML application is a specific type of application you can build with Visual Basic. It combines the dynamic content of a Web page with Visual Basic style coding. So you can build HTML pages with a HTML page tool (such as FrontPage or the VB DHTML designer) and then write Visual Basic code to respond to browser events, such as a mouse move over a text string or the user selecting a button.

### Common HTML Tags and Their Meanings

*The VB documentation implies that I can use the DHTML application feature to build Web pages by using my VB knowledge? Does that mean I don't need to learn HTML?*

In order to do anything really dynamic with DHTML applications you need to be able to add, modify, and delete HTML tags from the HTML pages. Some of the more common HTML tags that you will need to know are defined below.

| ------------------------ | --------------- |
| `<font size="1"></font>` | Font attributes |
| `<p></p>`                | Paragraph       |

### Funky things with DHTML Applications

*Some of these DHTML Application features don't seem to work quite right. Am I doing something wrong?*

We have also found some DHTML features that don't seem to work correctly:

* Save HTML as part of the VB project. This save feature was to allow you to easily send your DHTML project to another developer without worrying about the paths that VB hard-codes everywhere. We were not able to get this to work. We saved all of the files as part of the VB project, e-mailed it to a friend, and the developer receiving it could not see the pages. The developer had to resave all of the files as HTML first before the pages could be seen or edited.
* Changing the Save setting for a DHTML application. If you simply change the "Save HTML..." setting and nothing else in a DHTML designer, sometimes the change is not saved. We can normally work around this by changing something else on the page and then saving.
* Graphics in the IDE. Graphics added to a Web page will not appear in the IDE. You have to run the application to see them.

If you know of a workaround to these things, please let us know.
