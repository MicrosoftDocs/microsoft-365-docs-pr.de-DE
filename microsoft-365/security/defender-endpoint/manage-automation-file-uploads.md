---
title: Verwalten von Automatisierungsdateiuploads
description: Aktivieren der Inhaltsanalyse und Konfigurieren der Dateierweiterung und der E-Mail-Anlagenerweiterungen, die zur Analyse übermittelt werden
keywords: Automatisierung, Datei, Uploads, Inhalt, Analyse, Datei, Erweiterung, E-Mail, Anlage
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
ms.openlocfilehash: c8935368e4439221f2ce21cfa620e540c02165f8
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185849"
---
# <a name="manage-automation-file-uploads"></a>Verwalten von Automatisierungsdateiuploads

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationefileuploads-abovefoldlink)

Aktivieren Sie die Inhaltsanalysefunktion, damit bestimmte Dateien und E-Mail-Anlagen automatisch zur zusätzlichen Überprüfung in die Cloud hochgeladen werden können.

Identifizieren Sie die Dateien und E-Mail-Anlagen, indem Sie die Dateinamenerweiterungsnamen und E-Mail-Anlagenerweiterungsnamen angeben. 

Wenn Sie beispielsweise *exe* und *bat* als Datei- oder Anlagenerweiterungsnamen hinzufügen, werden alle Dateien oder Anlagen mit diesen Erweiterungen automatisch zur weiteren Überprüfung während der automatisierten Untersuchung an die Cloud gesendet. 

## <a name="add-file-extension-names-and-attachment-extension-names"></a>Fügen Sie Dateinamen und Anlagenerweiterungsnamen hinzu.

1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Automatisierungsdateiuploads aus.** 

2. Umschalten der Inhaltsanalyseeinstellung zwischen **Ein** und **Aus**.

3. Konfigurieren Sie die folgenden Erweiterungsnamen und separaten Erweiterungsnamen mit einem Komma:
   - **Dateinamenerweiterungsnamen** – Verdächtige Dateien mit Ausnahme von E-Mail-Anlagen werden zur weiteren Überprüfung übermittelt.
  

## <a name="related-topics"></a>Verwandte Themen
- [Verwalten von Ausschlüssen für Automatisierungsordner](manage-automation-folder-exclusions.md)
