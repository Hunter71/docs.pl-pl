---
title: Sprawdzanie poprawności schematu (XSD) XML z kolekcji XmlSchemaCollection
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: ad0b5717-3d32-41ad-a4d7-072c3e492b82
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6505229d96c6f27452776403a6e1f997dc5a8b10
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="xml-schema-xsd-validation-with-xmlschemacollection"></a>Sprawdzanie poprawności schematu (XSD) XML z kolekcji XmlSchemaCollection
Można użyć <xref:System.Xml.Schema.XmlSchemaCollection> do sprawdzania poprawności względem schematu XML definition language (XSD) schematów dokumentu XML. <xref:System.Xml.Schema.XmlSchemaCollection> Zwiększa wydajność dzięki przechowywaniu w kolekcji schematów, aby nie były załadowane do pamięci występuje każdego sprawdzania poprawności czasu. Jeśli schemat istnieje w kolekcji schematów `schemaLocation` atrybut służy do wyszukiwania schematu w kolekcji.  
  
> [!IMPORTANT]
>  <xref:System.Xml.Schema.XmlSchemaCollection> Klasy jest teraz przestarzałe i zostało zastąpione <xref:System.Xml.Schema.XmlSchemaSet> klasy. Aby uzyskać więcej informacji na temat <xref:System.Xml.Schema.XmlSchemaSet> , zobacz klasy [XmlSchemaSet kompilowania schematu](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md).  
  
 W poniższym przykładzie pokazano element główny pliku danych.  
  
```xml  
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema"  
    xmlns="urn:bookstore-schema"  
    elementFormDefault="qualified"  
    targetNamespace="urn:bookstore-schema">  
```  
  
 W tym przykładzie wartość `targetNamespace` atrybutu `urn:bookstore-schema`, która jest w tej samej przestrzeni nazw, która jest używana podczas dodawania schematu do <xref:System.Xml.Schema.XmlSchemaCollection>.  
  
 Poniższy przykładowy kod dodaje schematu XML do <xref:System.Xml.Schema.XmlSchemaCollection>.  
  
```vb  
Dim xsc As New XmlSchemaCollection()  
' XML Schema.  
xsc.Add("urn:bookstore-schema", schema)   
reader = New XmlTextReader(filename)  
vreader = New XmlValidatingReader(reader)  
vreader.Schemas.Add(xsc)  
```  
  
```csharp  
XmlSchemaCollection xsc = new XmlSchemaCollection();  
// XML Schema.  
xsc.Add("urn:bookstore-schema", schema);  
reader = new XmlTextReader (filename);  
vreader = new XmlValidatingReader (reader);  
vreader.Schemas.Add(xsc);  
```  
  
 `targetNamespace` Atrybut jest zwykle używany podczas dodawania `namespaceURI` właściwości w <xref:System.Xml.Schema.XmlSchemaCollection.Add%2A> metodę <xref:System.Xml.Schema.XmlSchemaCollection>. Odwołanie o wartości null można określić przed dodaniem schemat <xref:System.Xml.Schema.XmlSchemaCollection>. Ciąg pusty ("") powinny być używane do schematów bez przestrzeni nazw. <xref:System.Xml.Schema.XmlSchemaCollection> Może mieć tylko jeden schemat bez przestrzeni nazw.  
  
 Poniższy przykładowy kod dodaje do schematu XML HeadCount.xsd, <xref:System.Xml.Schema.XmlSchemaCollection> i sprawdza poprawność HeadCount.xml.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.Schema  
  
Namespace ValidationSample  
  
   Class Sample  
  
      Public Shared Sub Main()  
         Dim tr As New XmlTextReader("HeadCount.xml")  
         Dim vr As New XmlValidatingReader(tr)  
  
         vr.Schemas.Add("xsdHeadCount", "HeadCount.xsd")  
         vr.ValidationType = ValidationType.Schema  
         AddHandler vr.ValidationEventHandler, AddressOf ValidationHandler  
  
         While vr.Read()  
         End While  
         Console.WriteLine("Validation finished")  
      End Sub  
      ' Main  
  
      Public Shared Sub ValidationHandler(sender As Object, args As ValidationEventArgs)  
         Console.WriteLine("***Validation error")  
         Console.WriteLine("Severity:{0}", args.Severity)  
         Console.WriteLine("Message:{0}", args.Message)  
      End Sub  
      ' ValidationHandler  
   End Class  
   ' Sample  
End Namespace  
' ValidationSample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.Schema;  
  
namespace ValidationSample  
{  
   class Sample  
   {  
      public static void Main()  
      {  
         XmlTextReader tr = new XmlTextReader("HeadCount.xml");  
         XmlValidatingReader vr = new XmlValidatingReader(tr);  
  
         vr.Schemas.Add("xsdHeadCount", "HeadCount.xsd");  
         vr.ValidationType = ValidationType.Schema;  
         vr.ValidationEventHandler += new ValidationEventHandler (ValidationHandler);  
  
         while(vr.Read());  
         Console.WriteLine("Validation finished");  
      }  
  
      public static void ValidationHandler(object sender, ValidationEventArgs args)  
      {  
         Console.WriteLine("***Validation error");  
         Console.WriteLine("\tSeverity:{0}", args.Severity);  
         Console.WriteLine("\tMessage  :{0}", args.Message);  
      }  
   }  
}  
```  
  
 Poniżej opisano zawartość pliku wejściowego HeadCount.xml do sprawdzenia poprawności.  
  
```xml  
<!--Load HeadCount.xsd in SchemaCollection for Validation-->  
<hc:HeadCount xmlns:hc='xsdHeadCount'>  
   <Name>Waldo Pepper</Name>  
   <Name>Red Pepper</Name>  
</hc:HeadCount>  
```  
  
 Poniżej opisano zawartość pliku schematu XML, HeadCount.xsd, aby być weryfikowany pod kątem.  
  
```xml  
<xs:schema xmlns="xsdHeadCount" targetNamespace="xsdHeadCount" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
   <xs:element name='HeadCount' type="HEADCOUNT"/>  
   <xs:complexType name="HEADCOUNT">  
      <xs:sequence>  
         <xs:element name='Name' type='xs:string' maxOccurs='unbounded'/>  
      </xs:sequence>  
      <xs:attribute name='division' type='xs:int' use='optional' default='8'/>  
   </xs:complexType>  
</xs:schema>  
```  
  
 Poniższy przykład kodu tworzy <xref:System.Xml.XmlValidatingReader> pobierającej <xref:System.Xml.XmlTextReader>. Plik wejściowy, sample4.xml, sprawdzania poprawności względem schematu XML sample4.xsd.  
  
```vb  
Dim tr As New XmlTextReader("sample4.xml")  
Dim vr As New XmlValidatingReader(tr)  
vr.ValidationType = ValidationType.Schema  
vr.Schemas.Add("datatypesTest", "sample4.xsd")  
AddHandler vr.ValidationEventHandler, AddressOf ValidationCallBack  
While vr.Read()  
   Console.WriteLine("NodeType: {0} NodeName: {1}", vr.NodeType, vr.Name)  
End While  
```  
  
```csharp  
XmlTextReader tr = new XmlTextReader("sample4.xml");  
XmlValidatingReader vr = new XmlValidatingReader(tr);  
vr.ValidationType = ValidationType.Schema;  
        vr.Schemas.Add("datatypesTest", "sample4.xsd");  
vr.ValidationEventHandler += new ValidationEventHandler(ValidationCallBack);  
while(vr.Read()) {  
    Console.WriteLine("NodeType: {0} NodeName: {1}", vr.NodeType, vr.Name);  
    }  
```  
  
 Poniżej opisano zawartość pliku wejściowego sample4.xml do sprawdzenia poprawności.  
  
```xml  
<datatypes xmlns="datatypesTest">  
    <number>  
        <number_1>123</number_1>  
    </number>  
</datatypes>  
```  
  
 Poniżej opisano zawartość pliku schematu XML, sample4.xsd, aby być weryfikowany pod kątem.  
  
```xml  
<xs:schema   
    xmlns:xs="http://www.w3.org/2001/XMLSchema"   
    xmlns:tns="datatypesTest"   
    targetNamespace="datatypesTest"  
    elementFormDefault="qualified">  
  
<xs:element name = "datatypes">  
  <xs:complexType>  
    <xs:all>  
        <xs:element name="number">  
            <xs:complexType>  
                <xs:sequence>  
                    <xs:element name="number_1" type="xs:decimal" maxOccurs="unbounded"/>  
                </xs:sequence>  
            </xs:complexType>  
        </xs:element>  
    </xs:all>  
  </xs:complexType>  
</xs:element>  
</xs:schema>  
```  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Xml.XmlParserContext>  
 <xref:System.Xml.XmlValidatingReader.ValidationEventHandler?displayProperty=nameWithType>  
 <xref:System.Xml.XmlValidatingReader.Schemas%2A?displayProperty=nameWithType>  
 [Kompilacja schematu a klasa XmlSchemaCollection](../../../../docs/standard/data/xml/xmlschemacollection-schema-compilation.md)
