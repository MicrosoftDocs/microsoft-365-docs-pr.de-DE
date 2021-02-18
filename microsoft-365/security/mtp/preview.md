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
ms.openlocfilehash: 1636b1deb5f35d8286b33238a8f4bbfff0b33521
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288125"
---
# <a name="microsoft-365-defender-preview-features"></a>Microsoft 365 Defender –Vorschaufeatures

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> [!IMPORTANT]
> Die Vorschauversionen werden ohne Vereinbarung zum Servicelevel bereitgestellt und werden für Produktionsarbeitslasten nicht empfohlen. Bestimmte Features werden möglicherweise nicht unterstützt oder verfügen über eingeschränkte Funktionen.

**Gilt für:**
- Microsoft 365 Defender

Der Microsoft 365 Defender-Dienst wird ständig aktualisiert, um neue Featureverbesserungen und -funktionen zu bieten.

Erfahren Sie mehr über die neuen Features in der Microsoft 365 Defender Preview-Version, und gehören Sie zu den ersten, die bevorstehende Features testen, indem Sie die Vorschau aktivieren.

Weitere Informationen zu neuen Funktionen, die allgemein verfügbar sind, finden Sie [unter What's new in Microsoft 365 Defender](whats-new.md).

## <a name="required-permissions"></a>Erforderliche Berechtigungen

Konten, denen die folgenden Azure Active Directory (Azure AD)-Rollen zugewiesen sind, können Microsoft 365 Defender Preview-Features aktivieren:

- Globaler Administrator
- Sicherheitsadministrator
- Sicherheitsoperator

## <a name="turn-on-preview-features"></a>Vorschaufeatures aktivieren

Sie haben Zugriff auf anstehende Features, zu der Sie Feedback geben können, um die Gesamterfahrung zu verbessern, bevor Features allgemein verfügbar sind.

Aktivieren Sie die Einstellung für die Vorschauerfahrung, um zu den ersten zu gehören, die kommende Features ausprobieren.

1. Wählen Sie im Navigationsbereich **Einstellungen** aus.
2. Wählen **Sie Microsoft 365 Defender aus.**
3. Wählen Sie **Vorschaufeatures** > **Aktivieren Sie Vorschaufeatures**. 
4. Klicken Sie auf **Speichern**.

Sie wissen, dass Sie Vorschaufeatures aktiviert haben, wenn Sie sehen, dass das Kontrollkästchen **Vorschaufeatures aktivieren** aktiviert ist. 

## <a name="preview-features"></a>Vorschaufeatures

Die folgenden Features und Verbesserungen sind derzeit in der Vorschau verfügbar:

### <a name="improved-microsoft-365-security-center"></a>Verbessertes Microsoft 365 Security Center
Das verbesserte [Microsoft 365 Security Center](https://security.microsoft.com) ist jetzt in der öffentlichen Vorschau verfügbar. Diese neue Erfahrung bringt Defender für Endpoint, Defender für Office 365, Microsoft 365 Defender und vieles mehr in das Microsoft 365 Security Center. Dies ist die neue Startseite für die Verwaltung Ihrer Sicherheitskontrollen. [Erfahren Sie, was es Neues gibt](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center).

- **[Microsoft 365 Defender Threat Analytics-Bericht](threat-analytics.md)** – Bedrohungsanalyse hilft Ihnen, auf aktive Angriffe zu reagieren und die Auswirkungen zu minimieren. Sie können auch mehr über Angriffsversuche erfahren, die von Microsoft 365 -Defender-Lösungen blockiert werden, und vorbeugende Maßnahmen ergreifen, um das Risiko einer weiteren Gefährdung zu verringern und die Resilienz zu erhöhen. Im Rahmen der einheitlichen Sicherheitserfahrung ist die Bedrohungsanalyse jetzt für Microsoft Defender für Endpoint und Microsoft Defender für Office E5-Lizenzinhaber verfügbar.
- **[Microsoft 365 Defender-APIs](api-overview.md)** – Mit den Microsoft 365 Defender-APIs der obersten Ebene können Sie Workflows basierend auf den freigegebenen Vorfällen und erweiterten Tabellen für die Suche automatisieren. 
- **[Ergreifen Sie Maßnahmen bei der erweiterten Suche](advanced-hunting-take-action.md)**– sie können schnell Bedrohungen enthalten oder gefährdete Objekte, die Sie bei der erweiterten [Suche finden, adressieren.](advanced-hunting-overview.md)
- **[Schemareferenz im Portal –](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** Informationen zu Schematabellen für die erweiterte Suche direkt im Security Center erhalten. Zusätzlich zu Tabellen- und Spaltenbeschreibungen enthält diese Referenz unterstützte Ereignistypen `ActionType` (Werte) und Beispielabfragen.
- **[DeviceFromIP() function](advanced-hunting-devicefromip-function.md)**— Get information about which devices have been assigned a specific IP address or addresses at a given time range.
