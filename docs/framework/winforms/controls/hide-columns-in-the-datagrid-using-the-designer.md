---
title: "Porady: ukrywanie kolumn w formancie DataGridView formularzy systemu Windows przy użyciu narzędzia Projektant"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], hiding
- DataGridView control [Windows Forms], column hiding
- data [Windows Forms], displaying
ms.assetid: a81c38e6-2527-426a-bcb1-be691403be04
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6deefcfb4a1fcf0c1a3bd0d521e6a69ea6902dd4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="28e69-102">Porady: ukrywanie kolumn w formancie DataGridView formularzy systemu Windows przy użyciu narzędzia Projektant</span><span class="sxs-lookup"><span data-stu-id="28e69-102">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="28e69-103">Czasami można wyświetlić tylko niektóre kolumny, które są dostępne w formularzach systemu Windows <xref:System.Windows.Forms.DataGridView> formantu.</span><span class="sxs-lookup"><span data-stu-id="28e69-103">Sometimes you will want to display only some of the columns that are available in a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="28e69-104">Na przykład możesz wyświetlić pracownika wynagrodzenie kolumny do użytkowników przy użyciu poświadczeń zarządzania są ukryte go od innych użytkowników.</span><span class="sxs-lookup"><span data-stu-id="28e69-104">For example, you may want to show an employee salary column to users with management credentials while hiding it from other users.</span></span> <span data-ttu-id="28e69-105">Alternatywnie można powiązać ze źródłem danych, który zawiera wiele kolumn, tylko niektóre z nich ma być wyświetlany formant.</span><span class="sxs-lookup"><span data-stu-id="28e69-105">Alternately, you may want to bind the control to a data source that contains many columns, only some of which you want to display.</span></span> <span data-ttu-id="28e69-106">W takim przypadku zwykle spowoduje usunięcie kolumny, które nie są zainteresowane wyświetlania, a nie ich.</span><span class="sxs-lookup"><span data-stu-id="28e69-106">In this case, you will typically remove the columns you are not interested in displaying rather than hiding them.</span></span> <span data-ttu-id="28e69-107">Aby uzyskać więcej informacji, zobacz [porady: Dodawanie i usuwanie kolumn w Windows Forms DataGridView formantu przy użyciu projektanta](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="28e69-107">For more information, see [How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md).</span></span>  
  
 <span data-ttu-id="28e69-108">Poniższa procedura wymaga **aplikacji systemu Windows** projekt zawierający formularz <xref:System.Windows.Forms.DataGridView> formantu.</span><span class="sxs-lookup"><span data-stu-id="28e69-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="28e69-109">Informacje o konfigurowaniu tych projektu, zobacz [jak: utworzyć projekt aplikacji systemu Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) i [porady: dodawanie formantów do formularzy systemu Windows](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="28e69-109">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28e69-110">Okna dialogowe i polecenia menu mogą się różnić od tych opisanych w Pomocy, w zależności od ustawień aktywnych lub wydania.</span><span class="sxs-lookup"><span data-stu-id="28e69-110">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="28e69-111">Aby zmienić ustawienia, wybierz **Import i eksport ustawień** na **narzędzia** menu.</span><span class="sxs-lookup"><span data-stu-id="28e69-111">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="28e69-112">Aby uzyskać więcej informacji, zobacz [Dostosowywanie ustawień środowiska w programie Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="28e69-112">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-hide-a-column-using-the-designer"></a><span data-ttu-id="28e69-113">Aby ukryć kolumnę przy użyciu narzędzia Projektant</span><span class="sxs-lookup"><span data-stu-id="28e69-113">To hide a column using the designer</span></span>  
  
1.  <span data-ttu-id="28e69-114">Kliknij symbol tagu inteligentnego (![symbol tagu inteligentnego](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) w prawym górnym rogu <xref:System.Windows.Forms.DataGridView> kontroli, a następnie wybierz **Edytowanie kolumn**.</span><span class="sxs-lookup"><span data-stu-id="28e69-114">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>  
  
2.  <span data-ttu-id="28e69-115">Wybierz kolumny z **wybrane kolumny** listy.</span><span class="sxs-lookup"><span data-stu-id="28e69-115">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="28e69-116">W **właściwości kolumny** siatki, ustaw <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> właściwości `false`.</span><span class="sxs-lookup"><span data-stu-id="28e69-116">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> property to `false`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="28e69-117">Można również ukryć kolumny podczas dodawania go, usuwając zaznaczenie **Visible** pole wyboru w **Dodaj kolumnę** okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="28e69-117">You can also hide a column when adding it by clearing the **Visible** check box in the **Add Column** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28e69-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="28e69-118">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="28e69-119">Porady: Dodawanie i usuwanie kolumn w oknach formularzy formantu DataGridView, przy użyciu narzędzia Projektant</span><span class="sxs-lookup"><span data-stu-id="28e69-119">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 [<span data-ttu-id="28e69-120">Porady: Tworzenie projektu aplikacji systemu Windows</span><span class="sxs-lookup"><span data-stu-id="28e69-120">How to: Create a Windows Application Project</span></span>](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [<span data-ttu-id="28e69-121">Porady: dodawanie formantów do formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="28e69-121">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)