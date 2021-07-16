---
title: Verwalten von automatischen Ordnerausschlüssen
description: Fügen Sie Automatisierungsordnerausschlüsse hinzu, um die Dateien zu steuern, die von einer automatisierten Untersuchung ausgeschlossen sind.
keywords: Verwalten, Automatisierung, Ausschluss, blockieren, sauber, bösartig
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 05c103cba051c7d5e7f45e5dd3feb288013ee367
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454817"
---
# <a name="manage-automation-folder-exclusions"></a>Verwalten von automatischen Ordnerausschlüssen 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender für Endpunkt erfahren? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationexclusionfolder-abovefoldlink)

Mit Automatisierungsordnerausschlüssen können Sie Ordner angeben, die von der automatischen Untersuchung übersprungen werden. 

Sie können die folgenden Attribute zu dem Ordner steuern, der übersprungen werden soll:
- Ordner 
- Erweiterungen der Dateien
- Dateinamen


**Ordner**<br>
Sie können einen Ordner und seine Unterordner angeben, die übersprungen werden sollen. 


>[!NOTE]
>Derzeit wird die Verwendung von Platzhaltern als Möglichkeit zum Ausschließen von Dateien in einem Verzeichnis noch nicht unterstützt. 


**Erweiterungen**<br>
Sie können die auszuschließenden Erweiterungen in einem bestimmten Verzeichnis angeben. Die Erweiterungen sind eine Möglichkeit, um zu verhindern, dass ein Angreifer einen ausgeschlossenen Ordner verwendet, um einen Exploit auszublenden. Die Erweiterungen definieren explizit, welche Dateien ignoriert werden sollen. 

**Dateinamen**<br>
Sie können die Dateinamen angeben, die in einem bestimmten Verzeichnis ausgeschlossen werden sollen. Die Namen sind eine Möglichkeit, um zu verhindern, dass ein Angreifer einen ausgeschlossenen Ordner verwendet, um einen Exploit auszublenden. Die Namen definieren explizit, welche Dateien ignoriert werden sollen. 



## <a name="add-an-automation-folder-exclusion"></a>Hinzufügen eines Automatisierungsordnerausschlusses
1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Ordnerausschlüsse** für die Automatisierung von  >  **Endpunktregeln**  >  **aus.**  

2. Klicken Sie auf **"Neuer Ordnerausschluss".**  

3. Geben Sie die Ordnerdetails ein:

    - Ordner
    - Erweiterungen
    - Dateinamen
    - Beschreibung

4. Klicken Sie auf **Speichern**.

>[!NOTE]
> Live Response-Befehle zum Sammeln oder Untersuchen ausgeschlossener Dateien schlagen mit der Fehlermeldung fehl: "Datei wird ausgeschlossen". Darüber hinaus ignorieren automatisierte Untersuchungen die ausgeschlossenen Elemente.

## <a name="edit-an-automation-folder-exclusion"></a>Bearbeiten eines Automatisierungsordnerausschlusses 
1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Ordnerausschlüsse** für die Automatisierung von  >  **Endpunktregeln**  >  **aus.** 

2. Klicken Sie auf **"Bearbeiten"** für den Ordnerausschluss.  

3. Aktualisieren Sie die Details der Regel, und klicken Sie auf **"Speichern".**

## <a name="remove-an-automation-folder-exclusion"></a>Entfernen eines Automatisierungsordnerausschlusses 
1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Ordnerausschlüsse** für die Automatisierung von  >  **Endpunktregeln**  >  **aus.**  
2. Klicken Sie auf **"Ausschluss entfernen".** 


## <a name="related-topics"></a>Verwandte Themen
- [Verwalten von zugelassenen/blockierten Automatisierungslisten](manage-indicators.md)
- [Verwalten von automatischen Dateiuploads](manage-automation-file-uploads.md)
