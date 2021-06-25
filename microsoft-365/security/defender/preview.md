---
title: Vorschaufeatures in Microsoft 365 Defender
description: Informationen zu den neuen Features in Microsoft 365 Security.
keywords: Vorschau, neu, m365 security, Sicherheit, 365, Funktionen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: b852071c3fbfe12aac62e1d309fa130a4cd81e9c
ms.sourcegitcommit: b42dd3e706ebf9638cd893b35f75eaa56dd8fd7e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2021
ms.locfileid: "53125398"
---
# <a name="microsoft-365-defender-preview-features"></a>Microsoft 365 Defender Vorschaufeatures

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> [!IMPORTANT]
> Die Vorschauversionen werden ohne Vereinbarung zum Servicelevel bereitgestellt und für Produktionsworkloads nicht empfohlen. Bestimmte Features werden möglicherweise nicht unterstützt oder verfügen über eingeschränkte Funktionen.

**Gilt für:**
- Microsoft 365 Defender

Der Microsoft 365 Defender-Dienst wird ständig aktualisiert, um neue Featureverbesserungen und -funktionen einzuschließen.

Erfahren Sie mehr über die neuen Features in der Microsoft 365 Defender Vorschauversion und gehören Sie zu den ersten, die anstehende Features ausprobieren, indem Sie die Vorschau aktivieren.

Weitere Informationen zu neuen Funktionen, die allgemein verfügbar sind, finden Sie unter [Neuigkeiten in Microsoft 365 Defender](whats-new.md).

## <a name="required-permissions"></a>Erforderliche Berechtigungen

Konten, die den folgenden Azure Active Directory (Azure AD)-Rollen zugewiesen sind, können Microsoft 365 Defender Vorschaufeatures aktivieren:

- Globaler Administrator
- Sicherheitsadministrator
- Sicherheitsoperator

## <a name="turn-on-preview-features"></a>Vorschaufeatures aktivieren

Sie haben Zugriff auf bevorstehende Features, zu denen Sie Feedback geben können, um die Gesamterfahrung zu verbessern, bevor Features allgemein verfügbar sind.

Aktivieren Sie die Einstellung für die Vorschauerfahrung, um zu den ersten zu gehören, die kommende Features ausprobieren.

1. Wählen Sie im Navigationsbereich **Einstellungen** aus.
2. Wählen Sie **Microsoft 365 Defender** aus.
3. Wählen Sie **Vorschaufeatures** > **Aktivieren Sie Vorschaufeatures**. 
4. Klicken Sie auf **Speichern**.

Sie wissen, dass Sie Vorschaufeatures aktiviert haben, wenn Sie sehen, dass das Kontrollkästchen **Vorschaufeatures aktivieren** aktiviert ist. 

## <a name="preview-features"></a>Vorschaufeatures

Die folgenden Features und Verbesserungen sind derzeit in der Vorschau verfügbar:

- **[Anzeigen von Berichten pro Bedrohungstags](threat-analytics.md#view-reports-per-threat-tags)** – Bedrohungstags helfen Ihnen, sich auf bestimmte Bedrohungskategorien zu konzentrieren und die relevantesten Berichte zu überprüfen.
- **[Streaming-API](../defender-endpoint/raw-data-export.md)** – Microsoft 365 Defender unterstützt das Streamen aller über die erweiterte Suche verfügbaren Ereignisse auf ein Event Hubs- und/oder Azure-Speicherkonto.
- **[Microsoft 365 Defender APIs:](api-overview.md)** Mit den APIs auf oberster Ebene Microsoft 365 Defender können Sie Workflows basierend auf den freigegebenen Vorfalltabellen und erweiterten Suchtabellen automatisieren. 
- **[Ergreifen Sie Maßnahmen bei der erweiterten Suche](advanced-hunting-take-action.md)** – Schließen Sie schnell Bedrohungen ein, oder beheben Sie kompromittierte Ressourcen, die Sie bei der [erweiterten Suche](advanced-hunting-overview.md)finden.
- **[In-Portal-Schemareferenz](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** – Abrufen von Informationen zu Schematabellen für die erweiterte Suche direkt im Security Center. Zusätzlich zu Tabellen- und Spaltenbeschreibungen enthält diese Referenz unterstützte Ereignistypen ( `ActionType` Werte) und Beispielabfragen.
- **[DeviceFromIP()-Funktion](advanced-hunting-devicefromip-function.md)** – Abrufen von Informationen darüber, welchen Geräten zu einem bestimmten Zeitraum eine bestimmte IP-Adresse oder Adressen zugewiesen wurden.
