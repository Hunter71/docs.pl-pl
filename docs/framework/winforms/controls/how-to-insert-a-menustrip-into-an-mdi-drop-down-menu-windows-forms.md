---
title: 'Porady: wstawianie elementu MenuStrip do menu rozwijanego MDI (Formularze systemu Windows)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip control [Windows Forms], inserting
- MenuStrip control [Windows Forms], merging
- MDI [Windows Forms], merging menu items
ms.assetid: 0fad444e-26d9-49af-8860-044d9c10d608
ms.openlocfilehash: 9f7534720f9be185a176247ce00b0be5e2649bff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms"></a>Porady: wstawianie elementu MenuStrip do menu rozwijanego MDI (Formularze systemu Windows)
W niektórych aplikacjach rodzaj okno podrzędne interfejsu wielu dokumentów (MDI) może się różnić od nadrzędnego okna MDI. Na przykład element nadrzędny MDI może być arkusza kalkulacyjnego i podrzędnych MDI może być wykresu. W takim przypadku chcesz zaktualizować zawartość element nadrzędny MDI menu z zawartością menu podrzędnego MDI jako okien podrzędnych MDI różnego rodzaju są uaktywnione.  
  
 W poniższej procedurze użyto <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>, i <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> właściwości, aby wstawić grupy elementów menu z menu podrzędnego MDI do listy rozwijanej części menu nadrzędnego MDI. Zamknięcie okna podrzędnego MDI usuwa elementy menu wstawiony element nadrzędny MDI.  
  
### <a name="to-insert-a-menustrip-into-an-mdi-drop-down-menu"></a>Aby wstawić elementu MenuStrip do menu rozwijanego MDI  
  
1.  Tworzenie formularza i ustawić jej <xref:System.Windows.Forms.Form.IsMdiContainer%2A> właściwości `true`.  
  
2.  Dodaj <xref:System.Windows.Forms.MenuStrip> do `Form1` i ustaw <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> właściwość <xref:System.Windows.Forms.MenuStrip> do `true`.  
  
3.  Dodaj element menu najwyższego poziomu do `Form1` <xref:System.Windows.Forms.MenuStrip> i ustawić jej <xref:System.Windows.Forms.Control.Text%2A> właściwości `&File`.  
  
4.  Dodaj trzy elementy podmenu do `&File` element menu i zestaw ich <xref:System.Windows.Forms.ToolStripItem.Text%2A> właściwości `&Open`, `&Import from`, i `E&xit`.  
  
5.  Dodaj dwa elementy podmenu do `&Import from` elementu podmenu i zestaw ich <xref:System.Windows.Forms.ToolStripItem.Text%2A> właściwości `&Word` i `&Excel`.  
  
6.  Dodawanie formularza do projektu, należy dodać <xref:System.Windows.Forms.MenuStrip> formularza i zestawu <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> właściwość `Form2` <xref:System.Windows.Forms.MenuStrip> do `true`.  
  
7.  Dodaj element menu najwyższego poziomu do `Form2` <xref:System.Windows.Forms.MenuStrip> i ustawić jej <xref:System.Windows.Forms.ToolStripItem.Text%2A> właściwości `&File`.  
  
8.  Dodawanie elementów podmenu w celu `&File` menu `Form2` w następującej kolejności: <xref:System.Windows.Forms.ToolStripSeparator>, `&Save`, `&Close``and Save`, a inny <xref:System.Windows.Forms.ToolStripSeparator>.  
  
9. Ustaw <xref:System.Windows.Forms.MergeAction> i <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> właściwości `Form2` elementów menu, jak pokazano w poniższej tabeli.  
  
    |Element menu formularz2|Wartość MergeAction|Wartość MergeIndex|  
    |---------------------|-----------------------|----------------------|  
    |Plik|MatchOnly|-1|  
    |Separator|Insert|2|  
    |Zapisanie|Insert|3|  
    |Zapisz i zamknij|Insert|4|  
    |Separator|Insert|5|  
  
10. Tworzenie procedury obsługi zdarzeń dla <xref:System.Windows.Forms.Control.Click> zdarzenie `&Open` <xref:System.Windows.Forms.ToolStripMenuItem>.  
  
11. W ramach programu obsługi zdarzeń, Wstaw kod podobny do poniższego przykładu kodu można tworzyć i wyświetlać nowych wystąpień `Form2` jako elementy podrzędne MDI `Form1`.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    private void openToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
    ```  
  
12. Umieść kod podobny do poniższego przykładu kodu w `&Open` <xref:System.Windows.Forms.ToolStripMenuItem> można zarejestrować obsługi zdarzeń.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new System.EventHandler(this.openToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
 Ten przykład wymaga:  
  
-   Dwa <xref:System.Windows.Forms.Form> formantów `Form1` i `Form2`.  
  
-   A <xref:System.Windows.Forms.MenuStrip> kontrolować na `Form1` o nazwie `menuStrip1`, a <xref:System.Windows.Forms.MenuStrip> kontrolować na `Form2` o nazwie `menuStrip2`.  
  
-   Odwołuje się do <xref:System?displayProperty=nameWithType> i <xref:System.Windows.Forms?displayProperty=nameWithType> zestawów.  
  
## <a name="see-also"></a>Zobacz też  
 [Instrukcje: tworzenie formularzy nadrzędnych MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [Instrukcje: tworzenie formularzy podrzędnych MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [MenuStrip, kontrolka — omówienie](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
