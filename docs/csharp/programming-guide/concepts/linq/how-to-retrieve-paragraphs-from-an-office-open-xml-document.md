---
title: "Porady: pobieranie akapitów z dokumentu pakietu Office Open XML (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: cc2687cf-d648-451e-88ac-3847c6c967c8
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e6014b7cf4dc02c2818dd4b9bf5fadfcbd82e3d4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-retrieve-paragraphs-from-an-office-open-xml-document-c"></a><span data-ttu-id="21e81-102">Porady: pobieranie akapitów z dokumentu pakietu Office Open XML (C#)</span><span class="sxs-lookup"><span data-stu-id="21e81-102">How to: Retrieve Paragraphs from an Office Open XML Document (C#)</span></span>
<span data-ttu-id="21e81-103">W tym temacie przedstawiono przykład otwiera dokumentu pakietu Office Open XML, która pobiera zbiór wszystkich akapitów w dokumencie.</span><span class="sxs-lookup"><span data-stu-id="21e81-103">This topic presents an example that opens an Office Open XML document, and retrieves a collection of all of the paragraphs in the document.</span></span>  
  
 <span data-ttu-id="21e81-104">Aby uzyskać więcej informacji dotyczących Office Open XML, zobacz [www.openxmldeveloper.org](http://go.microsoft.com/fwlink/?LinkID=95573).</span><span class="sxs-lookup"><span data-stu-id="21e81-104">For more information on Office Open XML, see [www.openxmldeveloper.org](http://go.microsoft.com/fwlink/?LinkID=95573).</span></span>  
  
## <a name="example"></a><span data-ttu-id="21e81-105">Przykład</span><span class="sxs-lookup"><span data-stu-id="21e81-105">Example</span></span>  
 <span data-ttu-id="21e81-106">W tym przykładzie zostanie otwarty pakiet Office Open XML, relacje w pakiecie Open XML są używane do wyszukiwania dokumentu i części stylu.</span><span class="sxs-lookup"><span data-stu-id="21e81-106">This example opens an Office Open XML package, uses the relationships within the Open XML package to find the document and the style parts.</span></span> <span data-ttu-id="21e81-107">Następnie wykonuje zapytanie dokumentu projekcji, Kolekcja typu anonimowego, który zawiera akapitu <xref:System.Xml.Linq.XElement> węzła, nazwa stylu każdego akapitu i tekst każdego akapitu.</span><span class="sxs-lookup"><span data-stu-id="21e81-107">It then queries the document, projecting a collection of an anonymous type that contains the paragraph <xref:System.Xml.Linq.XElement> node, the style name of each paragraph, and the text of each paragraph.</span></span>  
  
 <span data-ttu-id="21e81-108">W przykładzie użyto metody rozszerzenia o nazwie `StringConcatenate`, który także podano w przykładzie.</span><span class="sxs-lookup"><span data-stu-id="21e81-108">The example uses an extension method named `StringConcatenate`, which is also supplied in the example.</span></span>  
  
 <span data-ttu-id="21e81-109">Szczegółowy samouczek wyjaśnia, jak działa w tym przykładzie, zobacz [czysty funkcjonalności transformacji XML (C#)](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md).</span><span class="sxs-lookup"><span data-stu-id="21e81-109">For a detailed tutorial that explains how this example works, see [Pure Functional Transformations of XML (C#)](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md).</span></span>  
  
 <span data-ttu-id="21e81-110">W tym przykładzie użyto znaleziony w zestawie WindowsBase klasy.</span><span class="sxs-lookup"><span data-stu-id="21e81-110">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="21e81-111">Używa typów w <xref:System.IO.Packaging?displayProperty=nameWithType> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="21e81-111">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```csharp  
public static class LocalExtensions  
{  
    public static string StringConcatenate(this IEnumerable<string> source)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (string s in source)  
            sb.Append(s);  
        return sb.ToString();  
    }  
  
    public static string StringConcatenate<T>(this IEnumerable<T> source,  
        Func<T, string> func)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (T item in source)  
            sb.Append(func(item));  
        return sb.ToString();  
    }  
  
    public static string StringConcatenate(this IEnumerable<string> source, string separator)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (string s in source)  
            sb.Append(s).Append(separator);  
        return sb.ToString();  
    }  
  
    public static string StringConcatenate<T>(this IEnumerable<T> source,  
        Func<T, string> func, string separator)  
    {  
        StringBuilder sb = new StringBuilder();  
        foreach (T item in source)  
            sb.Append(func(item)).Append(separator);  
        return sb.ToString();  
    }  
}  
  
class Program  
{  
    public static string ParagraphText(XElement e)  
    {  
        XNamespace w = e.Name.Namespace;  
        return e  
               .Elements(w + "r")  
               .Elements(w + "t")  
               .StringConcatenate(element => (string)element);  
    }  
  
    static void Main(string[] args)  
    {  
        const string fileName = "SampleDoc.docx";  
  
        const string documentRelationshipType =  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument";  
        const string stylesRelationshipType =  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles";  
        const string wordmlNamespace =  
          "http://schemas.openxmlformats.org/wordprocessingml/2006/main";  
        XNamespace w = wordmlNamespace;  
  
        XDocument xDoc = null;  
        XDocument styleDoc = null;  
  
        using (Package wdPackage = Package.Open(fileName, FileMode.Open, FileAccess.Read))  
        {  
            PackageRelationship docPackageRelationship =  
              wdPackage  
              .GetRelationshipsByType(documentRelationshipType)  
              .FirstOrDefault();  
            if (docPackageRelationship != null)  
            {  
                Uri documentUri =  
                    PackUriHelper  
                    .ResolvePartUri(  
                       new Uri("/", UriKind.Relative),  
                             docPackageRelationship.TargetUri);  
                PackagePart documentPart =  
                    wdPackage.GetPart(documentUri);  
  
                //  Load the document XML in the part into an XDocument instance.  
                xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()));  
  
                //  Find the styles part. There will only be one.  
                PackageRelationship styleRelation =  
                  documentPart.GetRelationshipsByType(stylesRelationshipType)  
                  .FirstOrDefault();  
                if (styleRelation != null)  
                {  
                    Uri styleUri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri);  
                    PackagePart stylePart = wdPackage.GetPart(styleUri);  
  
                    //  Load the style XML in the part into an XDocument instance.  
                    styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()));  
                }  
            }  
        }  
  
        string defaultStyle =  
            (string)(  
                from style in styleDoc.Root.Elements(w + "style")  
                where (string)style.Attribute(w + "type") == "paragraph" &&  
                      (string)style.Attribute(w + "default") == "1"  
                select style  
            ).First().Attribute(w + "styleId");  
  
        // Find all paragraphs in the document.  
        var paragraphs =  
            from para in xDoc  
                         .Root  
                         .Element(w + "body")  
                         .Descendants(w + "p")  
            let styleNode = para  
                            .Elements(w + "pPr")  
                            .Elements(w + "pStyle")  
                            .FirstOrDefault()  
            select new  
            {  
                ParagraphNode = para,  
                StyleName = styleNode != null ?  
                    (string)styleNode.Attribute(w + "val") :  
                    defaultStyle  
            };  
  
        // Retrieve the text of each paragraph.  
        var paraWithText =  
            from para in paragraphs  
            select new  
            {  
                ParagraphNode = para.ParagraphNode,  
                StyleName = para.StyleName,  
                Text = ParagraphText(para.ParagraphNode)  
            };  
  
        foreach (var p in paraWithText)  
            Console.WriteLine("StyleName:{0} >{1}<", p.StyleName, p.Text);  
    }  
}  
```  
  
 <span data-ttu-id="21e81-112">Uruchomienia z przykładowy dokument Open XML opisanego w [tworzenie źródło dokumentu pakietu Office Open XML (C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md), w tym przykładzie tworzy następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="21e81-112">When run with the sample Open XML document described in [Creating the Source Office Open XML Document (C#)](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md), this example produces the following output:</span></span>  
  
```  
StyleName:Heading1 >Parsing WordprocessingML with LINQ to XML<  
StyleName:Normal ><  
StyleName:Normal >The following example prints to the console.<  
StyleName:Normal ><  
StyleName:Code >using System;<  
StyleName:Code ><  
StyleName:Code >class Program {<  
StyleName:Code >    public static void (string[] args) {<  
StyleName:Code >        Console.WriteLine("Hello World");<  
StyleName:Code >    }<  
StyleName:Code >}<  
StyleName:Normal ><  
StyleName:Normal >This example produces the following output:<  
StyleName:Normal ><  
StyleName:Code >Hello World<  
```  
  
## <a name="see-also"></a><span data-ttu-id="21e81-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="21e81-113">See Also</span></span>  
 [<span data-ttu-id="21e81-114">Zaawansowane techniki zapytania (LINQ do XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="21e81-114">Advanced Query Techniques (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)