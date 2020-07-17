---
title: Vorschau der Features in Microsoft Threat Protection
description: Informationen zu neuen Features in der Microsoft 365-Sicherheit
keywords: Vorschau, neu, m365 Sicherheit, Sicherheit, 365, Funktionen
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 45bc42e825c55ca228b13e8d308f9a1384301d07
ms.sourcegitcommit: 11218af1d792af297b4280ca5975d139d2bbe350
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2020
ms.locfileid: "45048267"
---
# <a name="microsoft-threat-protection-preview-features"></a>Vorschaufunktionen für Microsoft Threat Protection

**Gilt für:**
- Microsoft Threat Protection


Der Microsoft Threat Protection-Dienst wird ständig aktualisiert und enthält neue Funktionsverbesserungen und Funktionen.

In diesem Artikel erfahren Sie mehr über die neuen Features in der Preview-Version von Microsoft Threat Protection und sind unter den ersten, die die bevorstehenden Features testen, indem Sie die Vorschau-Funktionalität aktivieren.

Weitere Informationen zu neuen Funktionen, die allgemein verfügbar sind, finden Sie unter [Neuigkeiten in Microsoft Threat Protection](whats-new.md).

## <a name="turn-on-preview-features"></a>Vorschaufunktionen aktivieren
Sie haben Zugriff auf kommende Features, über die Sie Feedback geben können, um die allgemeine Erfahrung zu verbessern, bevor Features allgemein verfügbar sind.

Aktivieren Sie die Einstellung Vorschau der Benutzeroberfläche, um zu den ersten zu gehören, die bevorstehende Features ausprobieren.

1. Wählen Sie im Navigationsbereich die Option **Einstellungen**aus.

2. Wählen Sie **Microsoft Threat Protection**aus.


3. **Vorschau-Features**aktivieren aktivieren Sie die  >  **Vorschaufunktionen**. 

3. Wählen Sie **Speichern** aus.

Sie wissen, dass Sie die Vorschaufunktionen aktiviert haben, wenn Sie sehen, dass das Kontrollkästchen **Vorschau-Features aktivieren** aktiviert ist. 

## <a name="preview-features"></a>Vorschaufeatures
Die folgenden Features und Verbesserungen sind derzeit in der Vorschau verfügbar:

- **[In-Portal-Schemareferenz](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** : Informationen zu Schema Tabellen, die direkt im Sicherheitscenter verfügbar sind. Neben Tabellen-und Spaltenbeschreibungen enthält dieser Verweisinformationen zu unterstützten Ereignistypen ( `ActionType` Werten) und Beispielabfragen.  

- **[Identitäts-und App-Tabellen](advanced-hunting-schema-tables.md)** – erhalten Sie Einblick in Authentifizierungsereignisse, Active Directory Abfragen und App-bezogene Aktivitäten mit den Tabellen [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)und [AppFileEvents](advanced-hunting-appfileevents-table.md) im erweiterten Jagd Schema.

- **[Go Hunt](advanced-hunting-go-hunt.md)** – schnell von der Untersuchung eines Vorfalls zur Überprüfung eines bestimmten Ereignisses, eines Benutzers, eines Geräts oder anderer Entitätstypen mithilfe abfragebasierter [Erweiterter Jagd](advanced-hunting-overview.md) Funktionen pivotieren.

- **[Fileprofile ()-Funktion](advanced-hunting-fileprofile-function.md)** – verwenden Sie in Ihren [erweiterten Jagd](advanced-hunting-overview.md) Abfragen, um umfassende Dateiinformationen zu integrieren.
