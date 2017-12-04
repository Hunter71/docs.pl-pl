---
title: "Jak pobrać właściwości obiektu systemowego drukowania bez odbicia"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: PrintSystemObject [WPF], getting properties
ms.assetid: 43560f28-183d-41c1-b9d1-de7c2552273e
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2f6015d25ee8868fe9b4c6dcf3bf145d413521e1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-print-system-object-properties-without-reflection"></a>Jak pobrać właściwości obiektu systemowego drukowania bez odbicia
Podziel na pozycje właściwości (i typy tych właściwości) w obiekcie za pomocą odbicia może zmniejszyć wydajność aplikacji. <xref:System.Printing.IndexedProperties> Przestrzeni nazw umożliwia pobranie tych informacji przy użyciu odbicia.  
  
## <a name="example"></a>Przykład  
 Dostępne są następujące kroki, aby to zrobić.  
  
1.  Utwórz wystąpienie typu. W poniższym przykładzie jest typ <xref:System.Printing.PrintQueue> typu, który jest dostarczany z [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)], ale niemal identyczne kodu powinny działać dla typów wyprowadzonych z <xref:System.Printing.PrintSystemObject>.  
  
2.  Utwórz <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> z poziomu typu <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>. <xref:System.Collections.DictionaryEntry.Value%2A> Właściwości każdego wpisu w tym słowniku jest obiektem jednego z jego typów pochodnych <xref:System.Printing.IndexedProperties.PrintProperty>.  
  
3.  Wyliczanie elementów członkowskich w słowniku. Dla każdego z nich wykonaj następujące czynności.  
  
4.  Wartość każdego wpisu do rzutowania w górę <xref:System.Printing.IndexedProperties.PrintProperty> i umożliwia utworzenie <xref:System.Printing.IndexedProperties.PrintProperty> obiektu.  
  
5.  Wybrany typ <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> poszczególnych <xref:System.Printing.IndexedProperties.PrintProperty> obiektu.  
  
 [!code-csharp[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/CSharp/Program.cs#showpropertytypeswithoutreflection)]
 [!code-vb[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/visualbasic/program.vb#showpropertytypeswithoutreflection)]  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Printing.IndexedProperties.PrintProperty>  
 <xref:System.Printing.PrintSystemObject>  
 <xref:System.Printing.IndexedProperties>  
 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Collections.DictionaryEntry>  
 [Dokumentów na platformie WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Omówienie drukowania](../../../../docs/framework/wpf/advanced/printing-overview.md)