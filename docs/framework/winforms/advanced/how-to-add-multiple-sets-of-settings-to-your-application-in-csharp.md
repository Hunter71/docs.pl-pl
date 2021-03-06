---
title: 'Porady: dodawanie wielu zestawów ustawień do aplikacji w C#'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: 029dffc878c62613e291620a2bd86971f369d15a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a>Porady: dodawanie wielu zestawów ustawień do aplikacji w C# #
W niektórych przypadkach można mieć wielu zestawów ustawień w aplikacji. Na przykład jeśli tworzysz aplikację, których można oczekiwać określonej grupy ustawień można zmienić często, można ją rozsądnego je rozdzielić wszystko w jednym pliku, dzięki czemu plik można zastąpić hurtowym, pozostawiając inne ustawienia nie mają wpływu. Program Visual Studio umożliwia dodawanie wielu zestawów ustawień do projektu. Ustawia dodatkowe ustawienia są dostępne za pośrednictwem obiektu Properties.Settings.  
  
### <a name="to-add-an-additional-set-of-setting-to-your-application"></a>Aby dodać dodatkowy zestaw ustawień aplikacji  
  
1.  Z **projektu** menu, wybierz **Dodaj nowy element**. **Dodaj nowy element** zostanie otwarte okno dialogowe.  
  
2.  W **Dodaj nowy element** okno dialogowe, wybierz opcję **pliku ustawień**, wpisz nazwę pliku i kliknij przycisk **Dodaj** można dodać nowego pliku ustawień do rozwiązania.  
  
3.  W **Eksploratora rozwiązań**, przeciągnij nowy plik ustawień do **właściwości** folderu. Dzięki temu nowe ustawienia mają być dostępne w kodzie.  
  
4.  Dodaj i użyj ustawień w tym pliku, jak w przypadku każdego innego pliku ustawień. Ta grupa ustawień za pomocą obiektu Properties.Settings są dostępne.  
  
## <a name="see-also"></a>Zobacz też  
 [Używanie ustawień aplikacji i ustawień użytkownika](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [Przegląd ustawień aplikacji](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
