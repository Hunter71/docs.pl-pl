---
title: 'Porady: pobieranie i ustawianie bieżącej komórki w formancie DataGridView formularzy systemu Windows'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], getting current cell
- DataGridView control [Windows Forms], setting current cell
- cells [Windows Forms], getting and setting current
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
ms.openlocfilehash: 0a3c8a891bf3f8424158a7266c3752edc33e8805
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a>Porady: pobieranie i ustawianie bieżącej komórki w formancie DataGridView formularzy systemu Windows
Interakcja z <xref:System.Windows.Forms.DataGridView> często wymaga się, że programowo odkrywasz komórki, która jest obecnie aktywny. Ponadto może być konieczna zmiana bieżącej komórki. Można wykonać te zadania z <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> właściwości.  
  
> [!NOTE]
>  Nie można ustawić bieżącej komórki w wiersz lub kolumnę, która ma jego <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> ustawioną właściwość `false`.  
  
 W zależności od <xref:System.Windows.Forms.DataGridView> tryb zaznaczania formantu, zmiana bieżącej komórki można zmienić zaznaczenia. Aby uzyskać więcej informacji, zobacz [tryby wyboru w formancie DataGridView formularzy systemu Windows](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md).  
  
### <a name="to-get-the-current-cell-programmatically"></a>Aby programowo pobieranie bieżącej komórki  
  
-   Użyj <xref:System.Windows.Forms.DataGridView> formantu <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> właściwości.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a>Aby programowo Ustawianie bieżącej komórki  
  
-   Ustaw <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> właściwość <xref:System.Windows.Forms.DataGridView> formantu. W poniższym przykładzie kodu bieżącej komórki jest równa 0, kolumna 1 wiersz.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
 Ten przykład wymaga:  
  
-   <xref:System.Windows.Forms.Button> formanty o nazwie `getCurrentCellButton` i `setCurrentCellButton`. W środowisku Visual C#, należy dołączyć <xref:System.Windows.Forms.Control.Click> zdarzeń dla każdego przycisku do skojarzonego programu obsługi zdarzeń w przykładowym kodzie.  
  
-   A <xref:System.Windows.Forms.DataGridView> formantu o nazwie `dataGridView1`.  
  
-   Odwołuje się do <xref:System?displayProperty=nameWithType> i <xref:System.Windows.Forms?displayProperty=nameWithType> zestawów.  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>  
 [Podstawowe funkcje komórek, wierszy i kolumn w kontrolce DataGridView formularzy Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 [Tryby wyboru w kontrolce DataGridView formularzy Windows Forms](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)
