---
title: Hochladen Ihres Pakets
description: So laden Sie Ihre App-Anwendung, Binärdateien und Abhängigkeiten in die Testbasis hoch
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: e8b4323eda31c55bbf32de0996fc7bd48d54ade2
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322782"
---
# <a name="step-2-uploading-a-package"></a>Schritt 2: Hochladen eines Pakets

Navigieren Sie auf der Seite "Testbasisportal" zur Option "Hochladen neues Paket" auf der linken Navigationsleiste, wie unten dargestellt: ![ Hochladen ein neues Paket](Media/Upload-New-Package.png)

Führen Sie dort die folgenden Schritte aus, um ein neues Paket hochzuladen.

## <a name="enter-details-for-your-package"></a>Geben Sie Details für Ihr Paket ein.

Geben Sie auf der Registerkarte "Testdetails" den Namen, die Version und andere Details des Pakets nach Bedarf ein. 

**Out-of-Box-** und **Funktionstests** können über dieses Dashboard durchgeführt werden.

Die folgenden Schritte enthalten eine Anleitung zum Ausfüllen ihrer Paketdetails:

1.  **Geben Sie den Namen für ihr Paket in das ```“Package name``` Feld ein.**

> [!Note]  
> Der eingegebene Paketname und die eingegebene Versionskombination müssen innerhalb Ihrer Organisation eindeutig sein. Dies wird durch das Häkchen wie unten dargestellt überprüft.
  
  - Wenn Sie den Namen eines Pakets wiederverwenden, muss die Versionsnummer eindeutig sein (d. h. nie mit einem Paket mit diesem bestimmten Namen verwendet).
  - Wenn die Kombination aus Paketname und Version die Eindeutigkeitsprüfung nicht besteht, wird die Fehlermeldung *"Paket mit dieser Paketversion ist bereits vorhanden" angezeigt.* 

![Abbildung für das Hochladen von Paketanweisungen](Media/Instructions.png)

2. **Geben Sie eine Version in das Feld "Paketversion" ein.**

![Paketversion](Media/ApplicationVersion.png)

3.  **Wählen Sie den Testtyp aus, den Sie für dieses Paket ausführen möchten.**

    Bei einem **Out-of-Box (OOB)-Test** wird das Paket *installiert,* *gestartet,* *geschlossen* und *deinstalliert.* Nach der Installation wird die Start-Schließen-Routine 30 Mal wiederholt, bevor eine einzelne Deinstallation ausgeführt wird. 
    
    Dieser OOB-Test bietet Ihnen standardisierte Telemetrie für Ihr Paket, die sie in Windows Builds vergleichen können.

    Ein **Funktionstest** würde Ihre hochgeladenen Testskripts auf Ihrem Paket ausführen. Die Skripts werden in der Uploadsequenz ausgeführt, und ein Fehler in einem bestimmten Skript hindert nachfolgende Skripts an der Ausführung.

> [!Note]
> **Alle** Skripts werden höchstens 80 Minuten lang ausgeführt. 
    
4.  **Auswählen des Betriebssystemupdatetyps**

   - Mit den "Sicherheitsupdates" kann Ihr Paket gegen inkrementelle Änderungen von Windows monatlichen Sicherheitsupdates vor der Veröffentlichung getestet werden. 
   - Die "Featureupdates" ermöglichen das Testen Ihres Pakets mit Windows halbjährlichen Vorabversionen von Featureupdates aus dem Windows-Insider-Programm.
<!---
Change to the correct picture
-->
![Betriebssystemupdatetyp](Media/OSUpdateType.png)

5.  **Wählen Sie die Betriebssystemversionen für Sicherheitsupdates aus.**

Wählen Sie in der Dropdownliste mit mehrfacher Auswahl die Betriebssystemversion(n) von Windows Ihr Paket installiert wird. 

  - Um Ihr Paket nur mit Windows Client-OSes zu testen, wählen Sie in der Menüliste die zutreffenden Betriebssystemversionen Windows 11 aus.
  - Wenn Sie Ihr Paket nur mit Windows Server-OSes testen möchten, wählen Sie in der Menüliste die entsprechenden Windows Serverbetriebssystemversionen aus.
  - Um Ihr Paket mit Windows Client- und Server-OSes zu testen, wählen Sie alle anwendbaren OSes aus der Menüliste aus. 

> [!Note]
> Wenn Sie ihr Paket sowohl mit Server- als auch mit Client-OSes testen möchten, stellen Sie sicher, dass das Paket kompatibel ist und auf beiden OSes ausgeführt werden kann.


![Auswählen einer Betriebssystemversion](Media/OSVersion.png)
<!---
Change to the correct picture
-->
6.  **Wählen Sie Optionen für Featureupdatetests aus:**

  - Wählen Sie auf der Option "Insider-Kanal auswählen" den Build aus, auf ```Windows Insider Program Channel``` den Ihre Pakete getestet werden sollen.
  
    Wir verwenden derzeit Builds mit Test-Flight im Insider Beta-Kanal.

  - Wählen Sie bei der Option "BS-Basisplan für Insight auswählen" die Windows Betriebssystemversion aus, die als Basisplan für den Vergleich Ihrer Testergebnisse verwendet werden soll. 

> [!Note]
> Featureupdatetests für Server-OSes werden derzeit NICHT unterstützt.
<!---
Note to actual note format for markdown
-->
<!---
Change to the correct picture
-->
![Testen von Funktionsupdates](Media/FeatureUpdate.png)

7.  Eine abgeschlossene Seite "Testdetails" sollte wie folgt aussehen: 

![Anzeigen von Testdetails](Media/TestDetails.png)
## <a name="next-steps"></a>Nächste Schritte

Unser nächster Artikel behandelt das Hochladen Ihrer Binärdateien in unsere Serivce.
> [!div class="nextstepaction"]
> [Nächster Schritt](binaries.md)

<!---
Add button for next page
-->

