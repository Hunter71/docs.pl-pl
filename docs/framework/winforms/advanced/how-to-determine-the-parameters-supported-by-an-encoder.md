---
title: "Porady: określanie parametrów obsługiwanych przez koder"
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
helpviewer_keywords: encoder parameters [Windows Forms], determining supported
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3e041434e9ace24618dbdc45341a0e8468721c3c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-the-parameters-supported-by-an-encoder"></a><span data-ttu-id="59239-102">Porady: określanie parametrów obsługiwanych przez koder</span><span class="sxs-lookup"><span data-stu-id="59239-102">How to: Determine the Parameters Supported by an Encoder</span></span>
<span data-ttu-id="59239-103">Można dostosować parametry obrazu, takie jak poziomu jakości i ich kompresji, ale musi wiedzieć, które parametry są obsługiwane przez koder danego obrazu.</span><span class="sxs-lookup"><span data-stu-id="59239-103">You can adjust image parameters, such as quality and compression level, but you must know which parameters are supported by a given image encoder.</span></span> <span data-ttu-id="59239-104"><xref:System.Drawing.Image> Klasa udostępnia <xref:System.Drawing.Image.GetEncoderParameterList%2A> metody, dzięki czemu można określić, które parametry obrazu są obsługiwane dla konkretnego kodera.</span><span class="sxs-lookup"><span data-stu-id="59239-104">The <xref:System.Drawing.Image> class provides the <xref:System.Drawing.Image.GetEncoderParameterList%2A> method so that you can determine which image parameters are supported for a particular encoder.</span></span> <span data-ttu-id="59239-105">Koder można określić za pomocą identyfikatora GUID.</span><span class="sxs-lookup"><span data-stu-id="59239-105">You specify the encoder with a GUID.</span></span> <span data-ttu-id="59239-106"><xref:System.Drawing.Image.GetEncoderParameterList%2A> Metoda zwraca tablicę <xref:System.Drawing.Imaging.EncoderParameter> obiektów.</span><span class="sxs-lookup"><span data-stu-id="59239-106">The <xref:System.Drawing.Image.GetEncoderParameterList%2A> method returns an array of <xref:System.Drawing.Imaging.EncoderParameter> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59239-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="59239-107">Example</span></span>  
 <span data-ttu-id="59239-108">Poniższy przykładowy kod generuje obsługiwane parametry dla kodera JPEG.</span><span class="sxs-lookup"><span data-stu-id="59239-108">The following example code outputs the supported parameters for the JPEG encoder.</span></span> <span data-ttu-id="59239-109">Zapoznaj się z listą parametrów kategorii i skojarzonych identyfikatorów GUID w <xref:System.Drawing.Imaging.Encoder> Przegląd klasy, aby określić kategorię dla każdego parametru.</span><span class="sxs-lookup"><span data-stu-id="59239-109">Use the list of parameter categories and associated GUIDs in the <xref:System.Drawing.Imaging.Encoder> class overview to determine the category for each parameter.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="59239-110">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="59239-110">Compiling the Code</span></span>  
 <span data-ttu-id="59239-111">Ten przykład wymaga:</span><span class="sxs-lookup"><span data-stu-id="59239-111">This example requires:</span></span>  
  
-   <span data-ttu-id="59239-112">Aplikacji formularzy systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="59239-112">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="59239-113">A <xref:System.Windows.Forms.PaintEventArgs>, który jest parametrem <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="59239-113">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59239-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="59239-114">See Also</span></span>  
 [<span data-ttu-id="59239-115">Porady: lista zainstalowanych koderów</span><span class="sxs-lookup"><span data-stu-id="59239-115">How to: List Installed Encoders</span></span>](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 [<span data-ttu-id="59239-116">Typy map bitowych</span><span class="sxs-lookup"><span data-stu-id="59239-116">Types of Bitmaps</span></span>](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)  
 [<span data-ttu-id="59239-117">Używanie kodeków obrazu w zarządzanym GDI +</span><span class="sxs-lookup"><span data-stu-id="59239-117">Using Image Encoders and Decoders in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)