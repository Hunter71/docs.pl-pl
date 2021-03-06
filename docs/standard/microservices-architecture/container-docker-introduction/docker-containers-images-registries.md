---
title: Kontenery docker, obrazy i rejestrów
description: Architektura Mikrousług .NET dla aplikacji .NET konteneryzowanych | Kontenery docker, obrazy i rejestrów
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 02ee40ebab37ae1898dc46e215728cba512a23e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="docker-containers-images-and-registries"></a>Kontenery docker, obrazy i rejestrów

Przy użyciu rozwiązania Docker, deweloper tworzy aplikację lub usługę i pakiety go i jego zależności w obrazie kontenera. Obraz jest statyczny reprezentację aplikacji lub usługi i konfiguracji oraz zależności.

Aby uruchomić aplikację lub usługę, obraz aplikacji zostanie uruchomiony, aby utworzyć kontener, który zostanie uruchomiona na hoście Docker. Kontenery początkowo są testowane w środowisko projektowe lub komputera.

Deweloperzy należy przechowywać obrazów w rejestrze, który działa jako biblioteka obrazów, jest potrzebne podczas wdrażania orchestrators produkcji. Docker przechowuje rejestr publiczny za pomocą [Centrum Docker](https://hub.docker.com/); innych dostawców Podaj rejestrów dla różnych kolekcji obrazów. Alternatywnie przedsiębiorstwa mogą mieć prywatnych rejestru lokalnymi własnych obrazów Docker.

Rysunek 2-4 przedstawiono, jak obrazy i rejestrów w Docker odnoszą się do innych składników. Zawiera także wiele ofert rejestru od dostawców.

![](./media/image5.PNG)

**Rysunek 2-4**. Taksonomii Docker terminy i pojęcia

Umieszczanie obrazów w rejestrze pozwala przechowywać bitów statycznych i modyfikować aplikacji, łącznie z ich zależności na poziomie framework. Tych obrazów można następnie numerów wersji i wdrożone w wielu środowiskach i stanowić jednostki spójne wdrożenia.

Rejestrów prywatnej obrazu hostowanych lokalnie lub w chmurze, jest zalecana, gdy:

-   Obrazów nie może być udostępniany publicznie z powodu poufności.

-   Chcesz, aby minimalna sieci opóźnienia między obrazów i środowiska wdrażania wybrany. Na przykład jeśli chmury Azure znajduje się w środowisku produkcyjnym, prawdopodobnie chcesz przechowywać obrazów w rejestrze kontenera platformy Azure, dzięki czemu jest minimalnego opóźnienia sieci. W podobny sposób w przypadku środowiska produkcyjnego w infrastrukturze lokalnej, możesz mieć lokalnymi Docker zaufane rejestru dostępne w ramach tej samej sieci lokalnej.

>[!div class="step-by-step"]
[Poprzednie] (docker-terminology.md) [dalej] (.. /NET-Core-NET-Framework-containers/index.MD)
