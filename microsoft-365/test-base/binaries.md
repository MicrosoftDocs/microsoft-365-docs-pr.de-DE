---
title: Hochladen Anwendungsbinärdateien
description: Erste Schritte mit der Testbasis für M365
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 1c4ff6ac03989cc9be70e18a1b8634f2da11e721
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322818"
---
# <a name="step-3-upload-your-binaries-dependencies-and-scripts"></a>Schritt 3: Hochladen Ihrer Binärdateien, Abhängigkeiten und Skripts

Auf dieser Registerkarte laden Sie ein einzelnes ZIP-Paket hoch, das Ihre Binärdateien, Abhängigkeiten und Skripts enthält, die zum Ausführen Ihrer Testsuite verwendet werden.

## <a name="upload-package-zip-file"></a>Hochladen Zip-Paketdatei

![Hochladen Ihrer Binärdateien](Media/AddBinaries.png)

  - Hochgeladene Abhängigkeiten können Testframeworks, Skriptmodule oder Daten enthalten, auf die zum Ausführen Ihrer Anwendung oder von Testfällen zugegriffen wird. Sie können z. B. Selenium und ein Webdriver-Installationsprogramm hochladen, um browserbasierte Tests auszuführen.
  - Es empfiehlt sich, sicherzustellen, dass Ihre Skriptaktivitäten modular gehalten werden, d. h. 
    - Das ```Install``` Skript führt nur Installationsvorgänge aus.
    - Das ```Launch``` Skript startet nur die Anwendung.
    - Das ```Close``` Skript schließt nur die Anwendung.
    - Das optionale ```Uninstall``` Skript deinstalliert nur die Anwendung.

**Derzeit unterstützt das Portal nur PowerShell-Skripts.**


## <a name="next-steps"></a>Nächste Schritte 

Fahren Sie mit dem nächsten Artikel fort, um zu Schritt 4: **Legen Sie Ihre Testaufgaben fest.**
> [!div class="nextstepaction"]
> [Zurück](uploadApplication.md)
> [!div class="nextstepaction"]
> [Nächster Schritt](testtask.md)

