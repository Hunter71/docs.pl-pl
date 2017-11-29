---
title: "ToolBar — Style i szablony"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- states [WPF], ToolBar
- styles [WPF], ToolBar
- ControlTemplate [WPF], ToolBar
- parts [WPF], ToolBar
- ToolBar [WPF], styles and templates
- templates [WPF], ToolBar
ms.assetid: bd875f46-4690-46f5-81e0-f11a9822484f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3e153ff0fd89259dafedf6f8abb669090a944e91
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="toolbar-styles-and-templates"></a><span data-ttu-id="03247-102">ToolBar — Style i szablony</span><span class="sxs-lookup"><span data-stu-id="03247-102">ToolBar Styles and Templates</span></span>
<span data-ttu-id="03247-103">W tym temacie opisano, style i szablonów dla <xref:System.Windows.Controls.ToolBar> formantu.</span><span class="sxs-lookup"><span data-stu-id="03247-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolBar> control.</span></span> <span data-ttu-id="03247-104">Można zmodyfikować domyślne <xref:System.Windows.Controls.ControlTemplate> umożliwiają unikatowego wyglądu formantu.</span><span class="sxs-lookup"><span data-stu-id="03247-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="03247-105">Aby uzyskać więcej informacji, zobacz [Dostosowywanie wyglądu formant tworząc ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="03247-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="toolbar-parts"></a><span data-ttu-id="03247-106">Części paska narzędzi</span><span class="sxs-lookup"><span data-stu-id="03247-106">ToolBar Parts</span></span>  
 <span data-ttu-id="03247-107">W poniższej tabeli wymieniono nazwanego części dla <xref:System.Windows.Controls.ToolBar> formantu.</span><span class="sxs-lookup"><span data-stu-id="03247-107">The following table lists the named parts for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="03247-108">Część</span><span class="sxs-lookup"><span data-stu-id="03247-108">Part</span></span>|<span data-ttu-id="03247-109">Typ</span><span class="sxs-lookup"><span data-stu-id="03247-109">Type</span></span>|<span data-ttu-id="03247-110">Opis</span><span class="sxs-lookup"><span data-stu-id="03247-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="03247-111">PART_ToolBarPanel</span><span class="sxs-lookup"><span data-stu-id="03247-111">PART_ToolBarPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarPanel>|<span data-ttu-id="03247-112">Obiekt, który zawiera formanty na <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="03247-112">The object that contains the controls on the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
|<span data-ttu-id="03247-113">PART_ToolBarOverflowPanel</span><span class="sxs-lookup"><span data-stu-id="03247-113">PART_ToolBarOverflowPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|<span data-ttu-id="03247-114">Obiekt, który zawiera formanty, które znajdują się w obszarze przepełnienia <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="03247-114">The object that contains the controls that are in the overflow area of the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
  
 <span data-ttu-id="03247-115">Po utworzeniu <xref:System.Windows.Controls.ControlTemplate> dla <xref:System.Windows.Controls.ToolBar>, szablon może zawierać <xref:System.Windows.Controls.ItemsPresenter> w <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="03247-115">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ToolBar>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="03247-116">( <xref:System.Windows.Controls.ItemsPresenter> Wyświetla każdy element <xref:System.Windows.Controls.ToolBar>; <xref:System.Windows.Controls.ScrollViewer> włącza przewijanie w kontrolce).</span><span class="sxs-lookup"><span data-stu-id="03247-116">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ToolBar>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="03247-117">Jeśli <xref:System.Windows.Controls.ItemsPresenter> nie jest bezpośrednim elementem podrzędnym elementu <xref:System.Windows.Controls.ScrollViewer>, musisz podać <xref:System.Windows.Controls.ItemsPresenter> nazwę, `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="03247-117">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="toolbar-states"></a><span data-ttu-id="03247-118">Stany paska narzędzi</span><span class="sxs-lookup"><span data-stu-id="03247-118">ToolBar States</span></span>  
 <span data-ttu-id="03247-119">W poniższej tabeli wymieniono stany wizualne dla <xref:System.Windows.Controls.ToolBar> formantu.</span><span class="sxs-lookup"><span data-stu-id="03247-119">The following table lists the visual states for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="03247-120">Nazwa stanu wizualnego</span><span class="sxs-lookup"><span data-stu-id="03247-120">VisualState Name</span></span>|<span data-ttu-id="03247-121">Nazwa VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="03247-121">VisualStateGroup Name</span></span>|<span data-ttu-id="03247-122">Opis</span><span class="sxs-lookup"><span data-stu-id="03247-122">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="03247-123">Prawidłowe</span><span class="sxs-lookup"><span data-stu-id="03247-123">Valid</span></span>|<span data-ttu-id="03247-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="03247-124">ValidationStates</span></span>|<span data-ttu-id="03247-125">Używa kontrolki <xref:System.Windows.Controls.Validation> klasy i <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> jest dołączona właściwość `false`.</span><span class="sxs-lookup"><span data-stu-id="03247-125">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="03247-126">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="03247-126">InvalidFocused</span></span>|<span data-ttu-id="03247-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="03247-127">ValidationStates</span></span>|<span data-ttu-id="03247-128"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Jest dołączona właściwość `true` ma formant ma fokus.</span><span class="sxs-lookup"><span data-stu-id="03247-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="03247-129">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="03247-129">InvalidUnfocused</span></span>|<span data-ttu-id="03247-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="03247-130">ValidationStates</span></span>|<span data-ttu-id="03247-131"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Jest dołączona właściwość `true` ma formant nie ma fokusa.</span><span class="sxs-lookup"><span data-stu-id="03247-131">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="toolbar-controltemplate-example"></a><span data-ttu-id="03247-132">Przykład ControlTemplate paska narzędzi</span><span class="sxs-lookup"><span data-stu-id="03247-132">ToolBar ControlTemplate Example</span></span>  
 <span data-ttu-id="03247-133">Poniższy przykład przedstawia sposób definiowania <xref:System.Windows.Controls.ControlTemplate> dla <xref:System.Windows.Controls.ToolBar> formantu.</span><span class="sxs-lookup"><span data-stu-id="03247-133">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/toolbar.xaml#toolbar)]  
  
 <span data-ttu-id="03247-134">Powyższy przykład korzysta z co najmniej jeden z następujących zasobów.</span><span class="sxs-lookup"><span data-stu-id="03247-134">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="03247-135">Pełny przykład, zobacz [style próbki ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="03247-135">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03247-136">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="03247-136">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="03247-137">Style formantu i szablony</span><span class="sxs-lookup"><span data-stu-id="03247-137">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="03247-138">Dostosowywanie formantu</span><span class="sxs-lookup"><span data-stu-id="03247-138">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="03247-139">Style i tworzenia szablonów</span><span class="sxs-lookup"><span data-stu-id="03247-139">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="03247-140">Dostosowywanie wyglądu formant tworząc ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="03247-140">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)