---
title: Testen des Basis-SDK für Python
description: Details zum Verständnis des SDK der Testbasis für Python
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: article
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: c7f2d4b7b600e84b2ed35cce320dcb7d7191ecfc
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322795"
---
# <a name="test-base-sdk-for-python"></a>Testen des Basis-SDK für Python

## <a name="overview"></a>Übersicht
Das Test Base SDK kann für die Interaktion mit der Azure-Testbasisressource verwendet werden. (d. h. Ihr Anwendungspaket verwalten, Paket erstellen, Paket bearbeiten und Paket löschen)

Mit dem SDK enthalten die Testzusammenfassung und das Analyseergebnis Folgendes: scriptExecution, Zuverlässigkeit, MemoryUtilization, cpuUtilization, memoryRegression, cpuRegression.

Mit dem Test Base SDK können Sie die Testbasis in Ihre CI/CD-Pipeline integrieren.

## <a name="client-library"></a>Clientbibliothek

Installieren Sie das Testbasispaket mit "pip".

~~~
pip install  Microsoft.Testbase
~~~
 
## <a name="example"></a>Beispiel
