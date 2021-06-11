---
title: Integrieren von Microsoft Defender für Endpunkt in andere Microsoft-Lösungen
description: Erfahren Sie, wie Microsoft Defender für Endpunkt in andere Microsoft-Lösungen integriert wird, einschließlich Microsoft Defender for Identity und Azure Defender.
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: Microsoft 365 Defender, bedingter Zugriff, Office, Microsoft Defender für Endpunkt, Microsoft Defender für Identität, Microsoft Defender für Office, Azure Defender, Microsoft Cloud App Security, Azure Sentinel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: aeb6d93017f138ce898d25f7d76e05cdcf3e90c5
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878568"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a>Microsoft Defender für Endpunkt und andere Microsoft-Lösungen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a>Integration in andere Microsoft-Lösungen

Microsoft Defender für Endpunkt lässt sich direkt in verschiedene Microsoft-Lösungen integrieren.

### <a name="azure-defender"></a>Azure Defender
Microsoft Defender für Endpunkt bietet eine umfassende Serverschutzlösung, einschließlich EDR (EDR)-Funktionen auf Windows Servern.

### <a name="azure-sentinel"></a>Azure Sentinel
Mit dem Microsoft Defender für Endpunkt-Connector können Sie Warnungen von Microsoft Defender für Endpunkt in Azure Sentinel streamen. Auf diese Weise können Sie Sicherheitsereignisse in Ihrer Organisation umfassender analysieren und Playbooks für eine effektive und sofortige Reaktion erstellen.

### <a name="azure-information-protection"></a>Azure Information Protection
Wir haben kürzlich die Azure Information Protection-Integration als veraltet eingestuft, da unsere Endpunkt-DLP-Funktionen eine verbesserte Ermittlungs- und Schutzlösung für vertrauliche Daten enthalten, die auf Endpunktgeräten gespeichert sind, was eine bessere Sichtbarkeit und Integration zwischen Lösungen ermöglicht. Dies wurde im folgenden [Blog](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555)angekündigt. Es wird empfohlen, dass Kunden zur Verwendung von Endpunkt-DLP wechseln.

### <a name="conditional-access"></a>Bedingter Zugriff
Die dynamische Geräterisikobewertung von Microsoft Defender für Endpunkt ist in die Bewertung des bedingten Zugriffs integriert, um sicherzustellen, dass nur sichere Geräte Zugriff auf Ressourcen haben. 

### <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security
Microsoft Cloud App Security nutzt Endpunktsignale von Microsoft Defender für Endpunkt, um direkte Einblicke in die Nutzung von Cloudanwendungen zu ermöglichen, einschließlich der Verwendung von nicht unterstützten Clouddiensten (Schatten-IT) von allen von Microsoft Defender für Endpunkt überwachten Geräten.

### <a name="microsoft-defender-for-identity"></a>Microsoft Defender for Identity
Verdächtige Aktivitäten sind Prozesse, die unter einem Benutzerkontext ausgeführt werden. Die Integration zwischen Microsoft Defender für Endpunkt und Microsoft Defender for Identity bietet die Flexibilität, Cybersicherheitsuntersuchungen über Aktivitäten und Identitäten hinweg durchzuführen.

### <a name="microsoft-defender-for-office"></a>Microsoft Defender für Office
[Defender für Office 365](/office365/securitycompliance/office-365-atp) schützt Ihre Organisation vor Schadsoftware in E-Mail-Nachrichten oder Dateien über sichere Links, sichere Anlagen, erweiterte Antiphishing- und Spoofing-Intelligence-Funktionen. Die Integration zwischen Microsoft Defender für Office 365 und Microsoft Defender für Endpunkt ermöglicht Es Sicherheitsanalysten, den Einstiegspunkt eines Angriffs zu untersuchen. Durch die Freigabe von Bedrohungserkennungen können Angriffe eingedämmt und blockiert werden. 

>[!NOTE]
> Defender für Office 365 Daten werden für Ereignisse innerhalb der letzten 30 Tage angezeigt. Bei Warnungen werden Defender für Office 365 Daten basierend auf dem Zeitpunkt der ersten Aktivität angezeigt. Danach sind die Daten in Defender nicht mehr für Office 365 verfügbar.

### <a name="skype-for-business"></a>Skype for Business
Die Skype for Business Integration bietet Analysten die Möglichkeit, über eine einfache Schaltfläche aus dem Portal mit einem potenziell gefährdeten Benutzer oder Gerätebesitzer zu kommunizieren.

## <a name="microsoft-365-defender"></a>Microsoft 365 Defender
Mit Microsoft 365 Defender, Microsoft Defender für Endpunkt und verschiedenen Sicherheitslösungen von Microsoft bilden Sie eine einheitliche Unternehmensschutzsuite vor und nach dem Angriff, die systemintern in Endpunkt, Identität, E-Mail und Anwendungen integriert ist, um komplexe Angriffe zu erkennen, zu verhindern, zu untersuchen und automatisch darauf zu reagieren. 
 
[Weitere Informationen zu Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)


## <a name="related-topics"></a>Verwandte Themen
- [Konfigurieren der Integration und anderer erweiterter Features](advanced-features.md)
- [Microsoft 365 Übersicht über Defender](/microsoft-365/security/defender/microsoft-threat-protection)
- [Microsoft 365 Defender aktivieren](/microsoft-365/security/defender/mtp-enable)
- [Schützen von Benutzern, Daten und Geräten mit bedingtem Zugriff](conditional-access.md)
