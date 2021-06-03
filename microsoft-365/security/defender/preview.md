---
title: Vorschaufunktionen in Microsoft 365 Defender
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
ms.openlocfilehash: 8ad5ffe2b175a8f7a42b2fad353fcde13a60cfec
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730522"
---
# <a name="microsoft-365-defender-preview-features"></a>Microsoft 365 Defender-Vorschaufeatures

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> [!IMPORTANT]
> Die Vorschauversionen werden ohne Vereinbarung zum Servicelevel bereitgestellt und werden für Produktionsworkloads nicht empfohlen. Bestimmte Features werden möglicherweise nicht unterstützt oder verfügen möglicherweise über eingeschränkte Funktionen.

**Gilt für:**
- Microsoft 365 Defender

Der Microsoft 365 Defender-Dienst wird ständig aktualisiert, um neue Funktionserweiterungen und -funktionen zu enthalten.

Erfahren Sie mehr über neue Features in der Microsoft 365 Defender Preview Release und gehören zu den ersten, die bevorstehende Features ausprobieren, indem Sie die Vorschaufunktion aktivieren.

Weitere Informationen zu neuen Funktionen, die allgemein verfügbar sind, finden Sie unter [What's new in Microsoft 365 Defender](whats-new.md).

## <a name="required-permissions"></a>Erforderliche Berechtigungen

Konten, denen die folgenden Azure Active Directory (Azure AD)-Rollen zugewiesen sind, können Microsoft 365 Defender Preview-Features aktivieren:

- Globaler Administrator
- Sicherheitsadministrator
- Sicherheitsoperator

## <a name="turn-on-preview-features"></a>Vorschaufeatures aktivieren

Sie haben Zugriff auf anstehende Features, zu der Sie Feedback geben können, um die Allgemeine Erfahrung zu verbessern, bevor Features allgemein verfügbar sind.

Aktivieren Sie die Einstellung für die Vorschauerfahrung, um zu den ersten zu gehören, die kommende Features ausprobieren.

1. Wählen Sie im Navigationsbereich **Einstellungen** aus.
2. Wählen **Microsoft 365 Defender aus.**
3. Wählen Sie **Vorschaufeatures** > **Aktivieren Sie Vorschaufeatures**. 
4. Klicken Sie auf **Speichern**.

Sie wissen, dass Sie Vorschaufeatures aktiviert haben, wenn Sie sehen, dass das Kontrollkästchen **Vorschaufeatures aktivieren** aktiviert ist. 

## <a name="preview-features"></a>Vorschaufeatures

Die folgenden Features und Verbesserungen sind derzeit in der Vorschau verfügbar:

- **[Streaming-API](../defender-endpoint/raw-data-export.md)** – Microsoft 365 Defender unterstützt das Streaming aller ereignisse, die über die erweiterte Suche verfügbar sind, an event hubs und/oder azure storage account.
- **[Microsoft 365 Defender-APIs](api-overview.md)** – Die top-level-Microsoft 365 Defender-APIs ermöglichen es Ihnen, Workflows basierend auf den freigegebenen Vorfällen und erweiterten Nachschlagetabellen zu automatisieren. 
- **[Ergreifen Sie Maßnahmen bei der erweiterten Suche](advanced-hunting-take-action.md)** – Enthalten Sie schnell Bedrohungen oder adressieren sie gefährdete Objekte, die Sie bei der [erweiterten Suche finden.](advanced-hunting-overview.md)
- **[In-Portal-Schemareferenz](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** : Informationen zu Schematabellen für die erweiterte Suche direkt im Security Center erhalten. Zusätzlich zu Tabellen- und Spaltenbeschreibungen enthält dieser Verweis unterstützte Ereignistypen ( `ActionType` Werte) und Beispielabfragen.
- **[DeviceFromIP()-Funktion](advanced-hunting-devicefromip-function.md)** : Hier erhalten Sie Informationen darüber, welchen Geräten zu einem bestimmten Zeitraum eine bestimmte IP-Adresse oder -Adresse zugewiesen wurde.
