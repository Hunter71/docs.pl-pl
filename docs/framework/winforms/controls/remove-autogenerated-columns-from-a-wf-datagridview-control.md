---
title: 'Porady: usuwanie utworzonych automatycznie kolumn z formantu DataGridView formularzy systemu Windows'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], removing columns
- columns [Windows Forms], removing
ms.assetid: 92e28d98-95a3-446c-9150-41b7c7e5be15
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 04375c89e80acb079f4862c159583adb4b0e4ca1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-remove-autogenerated-columns-from-a-windows-forms-datagridview-control"></a>Porady: usuwanie utworzonych automatycznie kolumn z formantu DataGridView formularzy systemu Windows
Jeśli Twoje <xref:System.Windows.Forms.DataGridView> formantu jest ustawiona na automatyczne generowanie kolumn na podstawie danych z źródła danych, można selektywnie pominąć niektóre kolumny. Można to zrobić przez wywołanie metody <xref:System.Windows.Forms.DataGridViewColumnCollection.Remove%2A> metoda <xref:System.Windows.Forms.DataGridView.Columns%2A> kolekcji. Alternatywnie można ukryć kolumny w widoku, ustawiając <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> właściwości `false`. Ta technika jest przydatne, jeśli chcesz wyświetlić ukryte kolumny w niektórych warunkach lub gdy chcesz uzyskać dostęp do danych w kolumnach bez ich wyświetlania.  
  
### <a name="to-remove-autogenerated-columns"></a>Aby usunąć utworzonych automatycznie kolumn  
  
-   Wywołanie <xref:System.Windows.Forms.DataGridViewColumnCollection.Remove%2A> metoda <xref:System.Windows.Forms.DataGridView.Columns%2A> kolekcji.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#111](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#111)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#111](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#111)]  
  
### <a name="to-hide-autogenerated-columns"></a>Aby ukryć utworzonych automatycznie kolumn  
  
-   Wartość w kolumnie <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> właściwości `false`.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#112](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#112)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#112](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#112)]  
  
## <a name="example"></a>Przykład  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#110)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#110)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
 Ten przykład wymaga:  
  
-   A <xref:System.Windows.Forms.DataGridView> formantu o nazwie `dataGridView1` powiązana z tabelą, który zawiera `Fax` i `CustomerID` kolumn, takich jak `Customers` tabeli w bazie danych Northwind.  
  
-   Odwołuje się do <xref:System?displayProperty=nameWithType> i <xref:System.Windows.Forms?displayProperty=nameWithType> zestawów.  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumnCollection.Remove%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>  
 [Wyświetlanie danych w formancie DataGridView formularzy systemu Windows](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)