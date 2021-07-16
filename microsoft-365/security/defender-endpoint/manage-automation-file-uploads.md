---
title: Verwalten von automatischen Dateiuploads
description: Aktivieren der Inhaltsanalyse und Konfigurieren der Dateierweiterung und E-Mail-Anlagenerweiterungen, die zur Analyse übermittelt werden
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
ms.openlocfilehash: b7d330388dd698cb524c1f4a8edaf9039ba4d16e
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454829"
---
# <a name="manage-automation-file-uploads"></a>Verwalten von automatischen Dateiuploads

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender für Endpunkt erfahren? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationefileuploads-abovefoldlink)

Aktivieren Sie die Funktion für die Inhaltsanalyse, damit bestimmte Dateien und E-Mail-Anlagen automatisch zur zusätzlichen Untersuchung in die Cloud hochgeladen werden können.

Identifizieren Sie die Dateien und E-Mail-Anlagen, indem Sie die Dateierweiterungsnamen und die Namen der E-Mail-Anlagenerweiterung angeben. 

Wenn Sie beispielsweise *exe* und *bat* als Datei- oder Anlagenerweiterungsnamen hinzufügen, werden alle Dateien oder Anlagen mit diesen Erweiterungen automatisch zur zusätzlichen Überprüfung während der automatisierten Untersuchung an die Cloud gesendet. 

## <a name="add-file-extension-names-and-attachment-extension-names"></a>Fügen Sie Dateierweiterungsnamen und Namen von Anlagenerweiterungen hinzu.

1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Endpoints**  >  **Rules**  >  **Automation uploads** aus.

2. Umschalten der Inhaltsanalyseeinstellung zwischen **"Ein"** und **"Aus".**

3. Konfigurieren Sie die folgenden Erweiterungsnamen und separaten Erweiterungsnamen mit einem Komma:
   - **Dateierweiterungsnamen** – Verdächtige Dateien mit Ausnahme von E-Mail-Anlagen werden zur zusätzlichen Überprüfung übermittelt.
  

## <a name="related-topics"></a>Verwandte Themen
- [Verwalten von automatischen Ordnerausschlüssen](manage-automation-folder-exclusions.md)
