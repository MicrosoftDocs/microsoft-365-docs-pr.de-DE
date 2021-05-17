---
title: Verwalten von automatischen Ordnerausschlüssen
description: Fügen Sie Automatisierungsordnerausschlüsse hinzu, um die Dateien zu steuern, die von einer automatisierten Untersuchung ausgeschlossen sind.
keywords: verwalten, automatisieren, ausschließen, blockieren, sauber, bösartig
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
ms.openlocfilehash: 37a251acd3b7631cffffaf2eb76bf0f2b4954ee6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185837"
---
# <a name="manage-automation-folder-exclusions"></a>Verwalten von automatischen Ordnerausschlüssen 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationexclusionfolder-abovefoldlink)

Mit Ausschlüssen für Automatisierungsordner können Sie Ordner angeben, die von der automatisierten Untersuchung übersprungen werden. 

Sie können die folgenden Attribute für den Ordner steuern, den Sie überspringen möchten:
- Ordner 
- Erweiterungen der Dateien
- Dateinamen


**Ordner**<br>
Sie können einen Ordner und dessen Unterordner angeben, die übersprungen werden sollen. 


>[!NOTE]
>Derzeit wird die Verwendung von Platzhaltern zum Ausschließen von Dateien unter einem Verzeichnis noch nicht unterstützt. 


**Erweiterungen**<br>
Sie können die erweiterungen angeben, die in einem bestimmten Verzeichnis ausgeschlossen werden. Die Erweiterungen verhindern, dass ein Angreifer einen ausgeschlossenen Ordner verwendet, um einen Exploit auszublenden. Die Erweiterungen definieren explizit, welche Dateien ignoriert werden. 

**Dateinamen**<br>
Sie können die Dateinamen angeben, die in einem bestimmten Verzeichnis ausgeschlossen werden sollen. Die Namen sind eine Möglichkeit, einen Angreifer daran zu hindern, einen ausgeschlossenen Ordner zum Ausblenden eines Exploits zu verwenden. Die Namen definieren explizit, welche Dateien ignoriert werden. 



## <a name="add-an-automation-folder-exclusion"></a>Hinzufügen eines Automatisierungsordnerausschlusses
1. Wählen Sie im Navigationsbereich die **Option Einstellungen**  >  **Automatisierungsordnerausschlüsse aus.**  

2. Klicken Sie **auf Neuer Ordnerausschluss**.  

3. Geben Sie die Ordnerdetails ein:

    - Ordner
    - Erweiterungen
    - Dateinamen
    - Beschreibung
    

4. Klicken Sie auf **Speichern**.

>[!NOTE]
> Live Response-Befehle zum Sammeln oder Untersuchen ausgeschlossener Dateien führen zu einem Fehler: "Datei ist ausgeschlossen". Darüber hinaus ignorieren automatisierte Untersuchungen die ausgeschlossenen Elemente.

## <a name="edit-an-automation-folder-exclusion"></a>Bearbeiten eines Automatisierungsordnerausschlusses 
1. Wählen Sie im Navigationsbereich die **Option Einstellungen**  >  **Automatisierungsordnerausschlüsse aus.** 

2. Klicken **Sie auf Bearbeiten** für den Ordnerausschluss.  

3. Aktualisieren Sie die Details der Regel, und klicken Sie auf **Speichern**.

## <a name="remove-an-automation-folder-exclusion"></a>Entfernen eines Automatisierungsordnerausschlusses 
1. Wählen Sie im Navigationsbereich die **Option Einstellungen**  >  **Automatisierungsordnerausschlüsse aus.**  
2. Klicken **Sie auf Ausschluss entfernen**. 


## <a name="related-topics"></a>Verwandte Themen
- [Verwalten von zulässigen/blockierten Automatisierungslisten](manage-indicators.md)
- [Verwalten von automatischen Dateiuploads](manage-automation-file-uploads.md)
