# Introduction to XML
- XML stands for eXtensible Markup Language.
- It is a markup language that defines a set of rules for encoding documents in a format that is both human-readable and machine-readable.
- Unlike HTML, XML is used to store and transport data, not to display it.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<note>
  <to>Harini</to>
  <from>XYZ</from>
  <heading>Reminder</heading>
  <body>Don't forget to practice JavaScript!</body>
</note>
```
The XML data is structured and easy to understand. Tags like <to>, <from>, <heading>, and <body> are custom-defined.

##  XML Document Structure
An XML document is composed of:
- Prolog: Contains XML declaration and optional comments.
- Root Element: Every XML document must have exactly one root element.
- Child Elements: Nested elements that represent data.
- Attributes: Additional information about elements.
```xml
<?xml version="1.0" encoding="UTF-8"?>
<library>
  <book category="Programming">
    <title>JavaScript Basics</title>
    <author>John Doe</author>
    <year>2025</year>
  </book>
  <book category="Web Development">
    <title>HTML & CSS Guide</title>
    <author>Jane Smith</author>
    <year>2024</year>
  </book>
</library>
```
- <library> is the root element.
- <book> is a child element with an attribute category.
- <title>, <author>, and <year> are child elements inside <book>.

## Document Type Definition (DTD)
DTD defines the structure and the legal elements and attributes of an XML document.

It can be internal or external.

Internal DTD Example:
```xml
<!DOCTYPE note [
  <!ELEMENT note (to, from, heading, body)>
  <!ELEMENT to (#PCDATA)>
  <!ELEMENT from (#PCDATA)>
  <!ELEMENT heading (#PCDATA)>
  <!ELEMENT body (#PCDATA)>
]>
<note>
  <to>Harini</to>
  <from>XYZ</from>
  <heading>Reminder</heading>
  <body>Practice JavaScript daily!</body>
</note>
```

## Namespaces
Namespaces are used to avoid naming conflicts by grouping elements and attributes under a unique name.

They are defined using the xmlns attribute.
```xml
<bookstore xmlns:tech="https://example.com/tech" xmlns:fiction="https://example.com/fiction">
  <tech:book>
    <tech:title>Learning JavaScript</tech:title>
  </tech:book>
  <fiction:book>
    <fiction:title>The Hobbit</fiction:title>
  </fiction:book>
</bookstore>
```
Here, tech and fiction are namespaces for different categories.

## XML Schemas
XML Schemas define the structure, content, and data types of XML documents.

It is more powerful than DTD as it supports data types.

Example of XML Schema (XSD):
```xml
<?xml version="1.0"?>
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="note">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="to" type="xs:string"/>
        <xs:element name="from" type="xs:string"/>
        <xs:element name="heading" type="xs:string"/>
        <xs:element name="body" type="xs:string"/>
      </xs:sequence>
    </xs:complexType>
  </xs:element>
</xs:schema>
```
## Displaying XML Documents with CSS
XML data can be styled with CSS.

CSS selectors can be used to display XML tags.
```xml
<?xml version="1.0"?>
<?xml-stylesheet type="text/css" href="style.css"?>
<note>
  <to>Harini</to>
  <from>XYZ</from>
  <heading>Reminder</heading>
  <body>Learn about XML today!</body>
</note>
```
style.css
```css
note {
  font-family: Arial, sans-serif;
}

to, from {
  color: blue;
}

heading {
  font-weight: bold;
  font-size: 18px;
}

body {
  margin-top: 10px;
}
```
##  XPath Basics
XPath (XML Path Language) is used to navigate through elements and attributes in XML documents.

It uses path expressions to select nodes or node sets.
```xml
<library>
  <book>
    <title>JavaScript Basics</title>
    <author>John Doe</author>
  </book>
  <book>
    <title>HTML Guide</title>
    <author>Jane Smith</author>
  </book>
</library>
```
XPath Expressions:

- /library/book/title → Selects all <title> elements under <book>.
- //title → Selects all <title> elements in the document.
- /library/book[1]/title → Selects the <title> of the first <book>.

## XSLT (eXtensible Stylesheet Language Transformations)
XSLT is used to transform XML documents into other formats like HTML, plain text, or other XML formats.

It uses XPath to navigate and manipulate the XML tree.
```xml
<?xml version="1.0"?>
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
  <xsl:template match="/">
    <html>
      <body>
        <h2>Book List</h2>
        <ul>
          <xsl:for-each select="library/book">
            <li><xsl:value-of select="title"/></li>
          </xsl:for-each>
        </ul>
      </body>
    </html>
  </xsl:template>
</xsl:stylesheet>
```
##  XML Processors
- An XML processor is responsible for parsing XML documents.
- It checks for:

  Well-Formed XML: Ensures tags are properly nested and closed.

  Validity: Ensures it follows the structure defined by DTD or XML Schema.

- Two types:
  
  Validating Processor: Ensures XML follows DTD or Schema.

  Non-Validating Processor: Only checks if XML is well-formed.
