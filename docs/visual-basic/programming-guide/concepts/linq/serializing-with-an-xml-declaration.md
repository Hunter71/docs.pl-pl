---
title: Serializacja z deklaracją XML (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 8726f79e-2bb0-4ba0-969d-197cca591647
ms.openlocfilehash: 6b7351d85dab997ba6cb0ef023972e9e4e4fca14
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="serializing-with-an-xml-declaration-visual-basic"></a>Serializacja z deklaracją XML (Visual Basic)
W tym temacie opisano sposób kontrolowania, czy serializacji generuje deklaracji XML.  
  
## <a name="xml-declaration-generation"></a>Generowanie deklaracji XML  
 Serializacja do <xref:System.IO.File> lub <xref:System.IO.TextWriter> przy użyciu <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> metody lub <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType> metoda generuje deklaracji XML. Podczas serializacji do <xref:System.Xml.XmlWriter>, ustawień edytora (określony w <xref:System.Xml.XmlWriterSettings> obiektu) ustalić, czy deklaracja XML jest generowany, czy nie.  
  
 Jeśli są serializacji przy użyciu ciągu `ToString` metody, wynikowy kod XML nie zostaną uwzględnione w deklaracji XML.  
  
### <a name="serializing-with-an-xml-declaration"></a>Serializacja z deklaracją XML  
 Poniższy przykład tworzy <xref:System.Xml.Linq.XElement>, dokument jest zapisywany do pliku i następnie drukuje plik do konsoli:  
  
```vb  
Dim root As XElement = <Root>  
                           <Child>child content</Child>  
                       </Root>  
root.Save("Root.xml")  
Dim str As String = File.ReadAllText("Root.xml")  
Console.WriteLine(str)  
```  
  
 Ten przykład generuje następujące wyniki:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a>Serializacja bez deklaracji XML  
 Poniższy przykład przedstawia sposób zapisania <xref:System.Xml.Linq.XElement> do <xref:System.Xml.XmlWriter>.  
  
```vb  
Dim sb As StringBuilder = New StringBuilder()  
Dim xws As XmlWriterSettings = New XmlWriterSettings()  
xws.OmitXmlDeclaration = True  
  
Using xw As XmlWriter = XmlWriter.Create(sb, xws)  
    Dim root = <Root>  
                   <Child>child content</Child>  
               </Root>  
    root.Save(xw)  
End Using  
Console.WriteLine(sb.ToString())  
```  
  
 Ten przykład generuje następujące wyniki:  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Serializacja drzewa XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
