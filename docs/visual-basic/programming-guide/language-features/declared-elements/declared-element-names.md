---
title: Zadeklarowane nazwy elementów (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic], case sensitivity
- names [Visual Basic], Visual Basic rules
- naming conventions [Visual Basic]
- element names [Visual Basic]
- declared elements [Visual Basic], identifiers
- declarations [Visual Basic], elements
- declared elements [Visual Basic], valid names
- '[] escape characters [Visual Basic]'
- names [Visual Basic], elements
- declaration statements [Visual Basic], declared elements
- declaring elements [Visual Basic]
- identifiers [Visual Basic], declared elements
- case sensitivity, declared element names
- escape characters [Visual Basic]
- names [Visual Basic], declared elements
- declared elements [Visual Basic], about declared elements
- escaped names [Visual Basic]
- declared elements [Visual Basic], names
- names [Visual Basic], naming conventions
- identifiers [Visual Basic], elements
ms.assetid: 09d8843b-c0dc-4afe-9dab-87c439a69e66
ms.openlocfilehash: 2f48f885b66f99ecc8c6c7e13fea7e75f0e3d24a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="declared-element-names-visual-basic"></a>Zadeklarowane nazwy elementów (Visual Basic)
Każdy element zadeklarowane ma nazwę, nazywany również *identyfikator*, czyli w kodzie użyto odwoływanie się do niego.  
  
## <a name="rules"></a>Reguły  
 Nazwa elementu w języku Visual Basic musi być zgodna z poniższymi regułami:  
  
-   Musi zaczynać się od litery lub znaku podkreślenia (`_`).  
  
-   Musi ona zawierać tylko znaki alfabetyczne, cyfry dziesiętne i podkreślenia.  
  
-   Musi ona zawierać co najmniej jedną literę alfabetu lub cyfrę, jeśli zaczyna się od znaku podkreślenia.  
  
-   Nie może być dłuższa niż 1023 znaków.  
  
 Limit długości 1023 znaków ma również zastosowanie do całego ciągu nazwy FQDN, takich jak `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.  
  
 W poniższym przykładzie przedstawiono niektóre nazwy elementów prawidłową.  
  
 `aB123__45`  
  
 `_567`  
  
 W poniższym przykładzie przedstawiono niektóre nazwy nieprawidłowy element. Pierwszy zawiera tylko znak podkreślenia, drugi rozpoczyna się od cyfry dziesiętne i trzeci zawiera nieprawidłowy znak ($).  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
>  Nazwy elementów, począwszy od znaku podkreślenia (`_`) czy nie jest częścią [niezależność od języka i elementy niezależne od języka](../../../../standard/language-independence-and-language-independent-components.md) (ze specyfikacją CLS), więc kodu zgodne ze specyfikacją CLS nie można użyć składnika, który definiuje takich nazw. Jednak podkreślenia w inne położenie w nazwie elementu jest zgodne ze specyfikacją CLS.  
  
### <a name="name-length-guidelines"></a>Wskazówki dotyczące długość nazwy  
 Jak to w praktyce Twoja nazwa powinna być możliwie krótki podczas nadal jednoznacznie identyfikujący rodzaj elementu. To poprawia czytelność kodu i zmniejsza rozmiar linii długość i pliku źródłowego.  
  
 Z drugiej strony nie należy tak krótki, że nie można ją było właściwie opisano reprezentuje element i jak kod używający nazwę. Jest to ważne w przypadku czytelność kodu. Jeśli ktoś próbuje go zrozumieć lub samodzielnie poszukujesz go przez długi czas, po jego zapisano, nazwy odpowiednich elementów można zapisać znaczną ilość czasu.  
  
## <a name="escaped-names"></a>Nazwy wyjścia  
 Ogólnie rzecz biorąc, nazwa elementu nie może być dopasowana dowolnego słowa zastrzeżone w języku Visual Basic, takie jak `Case` lub `Friend`. Można jednak zdefiniować *zmieniona nazwa*, która jest ujęta w nawiasy klamrowe (`[ ]`). Nazwa zmienionym może dopasować słowa kluczowego języka Visual Basic, ponieważ nawiasy usunąć niejednoznaczność. Można również użyć nawiasów, w przypadku odwoływania się do nazwy w dalszej części kodu.  
  
 Ogólnie rzecz biorąc, należy użyć nazwy wyjścia tylko wtedy, gdy:  
  
-   Kod został zmigrowany z poprzedniej wersji programu Visual Basic, który nie zarezerwować słowa kluczowego jako nazwy; lub  
  
-   Pracujesz kod napisany w innym języku, w którym dane słowo kluczowe nie jest zarezerwowana.  
  
 W przeciwnym razie należy rozważyć, jeśli jego nazwa powoduje konflikt ze słowem kluczowym, zmiana nazwy elementu. Zintegrowane środowisko programistyczne (IDE) zapewnia prosty sposób w tym celu. Aby uzyskać więcej informacji, zobacz [Refactoring](/visualstudio/vb-ide/refactoring-vb).  
  
## <a name="case-sensitivity-in-names"></a>Uwzględniana wielkość liter w nazwach  
 Nazwy elementów w języku Visual Basic jest rozróżniana wielkość liter. Oznacza to, że gdy kompilator porównuje dwie nazwy, które różnią się od litery alfabetu tylko wielkością liter, jego interpretuje je jako takiej samej nazwie. Na przykład traktuje `ABC` i `abc` do odwoływania się do tego samego elementu zadeklarowane.  
  
 Środowisko uruchomieniowe języka wspólnego (CLR) nie korzysta jednak powiązania z uwzględnieniem wielkości liter. W związku z tym podczas tworzenia zestawu lub biblioteki DLL i był dostępny do innych zestawów nazwy nie są już bez uwzględniania wielkości liter. Na przykład można zdefiniować klasę z element o nazwie `ABC`, i innych zestawów użyć klasy przez środowisko uruchomieniowe języka wspólnego, ich musi odwoływać się do elementu jako `ABC`. Jeśli są później ponownie skompilowana, klasy i Zmień nazwę elementu, aby `abc`, innych zestawów przy użyciu klasy nie może uzyskać dostępu do tego elementu. W związku z tym po zwolnieniu zaktualizowanej wersji zestawu, nie należy zmieniać w przypadku alfabetyczne żadnych publicznych elementów.  
  
## <a name="names-and-locales"></a>Nazwy i ustawień regionalnych  
 Porównanie nazw zależy od ustawień regionalnych. Jeśli dwie nazwy są zgodne z ustawieniami regionalnymi jeden, ich dotrą do dopasowania wszystkich ustawień regionalnych.  
  
## <a name="see-also"></a>Zobacz też  
 [Zadeklarowane elementy](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)  
 [Charakterystyka zadeklarowanych elementów](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [Odwołania do elementów zadeklarowanych](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Instrukcje](../../../../visual-basic/language-reference/statements/index.md)
