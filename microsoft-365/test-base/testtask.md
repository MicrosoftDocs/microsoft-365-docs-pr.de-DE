---
title: Festlegen der Testaufgaben
description: Festlegen der Testaufgaben
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
ms.openlocfilehash: 64abb5b10e3dc1d52b6baf8ceccd5aff2baacefe
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322690"
---
# <a name="step-4-the-tasks-tab"></a>Schritt 4: Registerkarte "Aufgaben"

Auf der Registerkarte "Aufgaben" müssen Sie die Pfade zu Ihren Testskripts angeben, die sich im ZIP-Ordner befinden, den Sie auf der Registerkarte "Binärdateien" hochgeladen haben.

  - **Out-of-Box-Testskripts:** Geben Sie die relativen Pfade zu Ihren Installations-, Start-, Schließ- und Deinstallationsskripts ein. Sie haben auch die Möglichkeit, zusätzliche Einstellungen für das Installationsskript auszuwählen.
  - **Funktionstestskripts:** Geben Sie den relativen Pfad zu jedem hochgeladenen Funktionstestskript ein. Mithilfe der Schaltfläche können zusätzliche funktionale Testskripts hinzugefügt ```Add Script``` werden. Sie benötigen mindestens ein Skript (1) und können bis zu acht (8) funktionale Testskripts hinzufügen. 
  
    Die Skripts werden in der Uploadsequenz ausgeführt, und ein Fehler in einem bestimmten Skript hindert nachfolgende Skripts an der Ausführung.
    Sie haben auch die Möglichkeit, zusätzliche Einstellungen für jedes bereitgestellte Skript auszuwählen.

## <a name="set-script-path"></a>Skriptpfad festlegen

![Abbildung der Testaufgabe](Media/testtask.png)

Nachfolgend finden Sie ein Beispiel für die Bereitstellung des relativen Pfads für eine Ordnerstruktur:

_**Zip_file_uploaded**_
~~~
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - **ScriptX.ps1.** _ScriptX.ps1_ als relativer Pfad.
  - **Script.ps1** würde _ordner1/script.ps1_ als relativen Pfad haben.


## <a name="next-steps"></a>Nächste Schritte

Anzeigen von Details der Registerkarte "Testoptionen" im nächsten Artikel 
> [!div class="nextstepaction"]
> [Nächster Schritt](testoptions.md)
