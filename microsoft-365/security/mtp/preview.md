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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 2f5b1a289f55b7237606782afb8e8f5acf6788a2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918858"
---
# <a name="microsoft-365-defender-preview-features"></a>Microsoft 365 Defender -Vorschaufeatures

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> [!IMPORTANT]
> Die Vorschauversionen werden ohne Vereinbarung zum Servicelevel bereitgestellt und werden für Produktionsworkloads nicht empfohlen. Bestimmte Features werden möglicherweise nicht unterstützt oder verfügen möglicherweise über eingeschränkte Funktionen.

**Gilt für:**
- Microsoft 365 Defender

Der Microsoft 365 Defender-Dienst wird ständig aktualisiert, um neue Funktionserweiterungen und -funktionen zu enthalten.

Erfahren Sie mehr über neue Features in der Microsoft 365 Defender-Vorschauversion und gehören zu den ersten, die bevorstehende Features ausprobieren, indem Sie die Vorschaufunktion aktivieren.

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
2. Wählen **Sie Microsoft 365 Defender aus.**
3. Wählen Sie **Vorschaufeatures** > **Aktivieren Sie Vorschaufeatures**. 
4. Klicken Sie auf **Speichern**.

Sie wissen, dass Sie Vorschaufeatures aktiviert haben, wenn Sie sehen, dass das Kontrollkästchen **Vorschaufeatures aktivieren** aktiviert ist. 

## <a name="preview-features"></a>Vorschaufeatures

Die folgenden Features und Verbesserungen sind derzeit in der Vorschau verfügbar:

### <a name="improved-microsoft-365-security-center"></a>Verbessertes Microsoft 365 Security Center
Das verbesserte [Microsoft 365 Security Center](https://security.microsoft.com) ist jetzt in der öffentlichen Vorschau verfügbar. Diese neue Umgebung integriert Microsoft Defender für Endpunkt, Microsoft Defender für Office, 365 Microsoft 365 Defender und mehr in das Microsoft 365 Security Center. Dies ist das neue Zuhause für die Verwaltung Ihrer Sicherheitssteuerelemente. [Erfahren Sie, was es Neues gibt](./overview-security-center.md).

- **[Microsoft 365 Defender Threat Analytics Report](threat-analytics.md)** – Bedrohungsanalyse hilft Ihnen, auf aktive Angriffe zu reagieren und die Auswirkungen zu minimieren. Sie können auch mehr über Angriffsversuche erfahren, die von Microsoft 365 Defender-Lösungen blockiert werden, und präventive Maßnahmen ergreifen, um das Risiko einer weiteren Gefährdung zu mindern und die Ausfallsicherheit zu erhöhen. Als Teil der einheitlichen Sicherheitserfahrung ist die Bedrohungsanalyse jetzt für Microsoft Defender for Endpoint und Microsoft Defender für Office E5-Lizenzinhaber verfügbar.
- **[Microsoft 365 Defender-APIs](api-overview.md)** – Mit den Microsoft 365 Defender-APIs auf oberster Ebene können Sie Workflows basierend auf dem freigegebenen Vorfall und erweiterten Tabellen für die Suche automatisieren. 
- **[Ergreifen Sie Maßnahmen bei der erweiterten Suche](advanced-hunting-take-action.md)**– Enthalten Sie schnell Bedrohungen oder adressieren sie gefährdete Objekte, die Sie bei der [erweiterten Suche finden.](advanced-hunting-overview.md)
- **[In-Portal-Schemareferenz](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**– Informationen zu Schematabellen für die erweiterte Suche direkt im Security Center erhalten. Zusätzlich zu Tabellen- und Spaltenbeschreibungen enthält dieser Verweis unterstützte Ereignistypen ( `ActionType` Werte) und Beispielabfragen.
- **[DeviceFromIP() -Funktion](advanced-hunting-devicefromip-function.md)**– Erhalten Sie Informationen darüber, welchen Geräten zu einem bestimmten Zeitraum eine bestimmte IP-Adresse zugewiesen wurde.