---
title: Integrieren von Microsoft Defender for Endpoint in andere Microsoft-Lösungen
description: Erfahren Sie, wie Microsoft Defender for Endpoint in andere Microsoft-Lösungen integriert wird, einschließlich Microsoft Defender for Identity und Azure Defender.
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: microsoft 365 Defender, bedingter Zugriff, Office, Microsoft Defender for Endpoint, microsoft defender for identity, microsoft defender for office, Azure Defender, Microsoft Cloud App Security, azure sentinel
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
ms.openlocfilehash: ce8dbef2f4fb7c3503f04f15148d2071b449b2dc
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935533"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a>Microsoft Defender für Endpoint und andere Microsoft-Lösungen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a>Integration in andere Microsoft-Lösungen

Microsoft Defender for Endpoint kann direkt in verschiedene Microsoft-Lösungen integriert werden.

### <a name="azure-defender"></a>Azure Defender
Microsoft Defender for Endpoint bietet eine umfassende Serverschutzlösung, einschließlich der Funktionen für die Erkennung und Reaktion von Endpunkten (Endpoint Detection and Response, EDR) auf Windows-Servern.

### <a name="azure-sentinel"></a>Azure Sentinel
Mit dem Microsoft Defender for Endpoint-Connector können Sie Warnungen von Microsoft Defender for Endpoint in Azure Sentinel streamen. Auf diese Weise können Sie Sicherheitsereignisse in Ihrer Organisation umfassender analysieren und Playbooks für eine effektive und sofortige Reaktion erstellen.

### <a name="azure-information-protection"></a>Azure Information Protection
Wir haben die Azure Information Protection-Integration kürzlich veraltet, da unsere Endpoint DLP-Funktionen eine verbesserte Ermittlungs- und Schutzlösung für vertrauliche Daten enthalten, die auf Endpunktgeräten gespeichert sind und eine bessere Sichtbarkeit und Integration zwischen Lösungen ermöglichen. Dies wurde im folgenden Blog [angekündigt.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555) Es wird empfohlen, dass Kunden zu Endpoint DLP wechseln.

### <a name="conditional-access"></a>Bedingter Zugriff
Die dynamische Geräterisikobewertung von Microsoft Defender for Endpoint ist in die Bewertung für bedingten Zugriff integriert und stellt sicher, dass nur sichere Geräte Zugriff auf Ressourcen haben. 

### <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security
Microsoft Cloud App Security nutzt Microsoft Defender for Endpoint-Endpunktsignale, um eine direkte Sichtbarkeit der Verwendung von Cloudanwendung zu ermöglichen, einschließlich der Verwendung nicht unterstützter Clouddienste (Shadow-IT) von allen überwachten Microsoft Defender for Endpoint-Geräten.

### <a name="microsoft-defender-for-identity"></a>Microsoft Defender for Identity
Verdächtige Aktivitäten sind Prozesse, die in einem Benutzerkontext ausgeführt werden. Die Integration zwischen Microsoft Defender for Endpoint und Microsoft Defender for Identity bietet die Flexibilität der Durchführung von Cybersicherheitsuntersuchungen über Aktivitäten und Identitäten hinweg.

### <a name="microsoft-defender-for-office"></a>Microsoft Defender for Office
[Defender für Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) schützt Ihre Organisation durch sichere Links, sichere Anlagen, erweiterte Antiphishing- und Spoof intelligence-Funktionen vor Schadsoftware in E-Mail-Nachrichten oder Dateien. Die Integration zwischen Microsoft Defender für Office 365 und Microsoft Defender for Endpoint ermöglicht Es Sicherheitsanalysten, den Einstiegspunkt eines Angriffs zu untersuchen. Durch die Freigabe von Bedrohungsinformationen können Angriffe verhindert und verhindert werden. 

>[!NOTE]
> Defender for Office 365-Daten werden für Ereignisse innerhalb der letzten 30 Tage angezeigt. Bei Warnungen werden Defender for Office 365-Daten basierend auf der ersten Aktivitätszeit angezeigt. Danach sind die Daten in Defender for Office 365 nicht mehr verfügbar.

### <a name="skype-for-business"></a>Skype for Business
Die Skype for Business-Integration bietet Analysten die Möglichkeit, über eine einfache Schaltfläche über das Portal mit einem potenziell gefährdeten Benutzer oder Gerätebesitzer zu kommunizieren.

## <a name="microsoft-365-defender"></a>Microsoft 365 Defender
Mit Microsoft 365 Defender bilden Microsoft Defender für Endpoint und verschiedene Microsoft-Sicherheitslösungen eine einheitliche Vor- und Nachverletzungssuite für die Unternehmensverteidigung, die nativ in Endpunkte, Identitäten, E-Mails und Anwendungen integriert wird, um anspruchsvolle Angriffe zu erkennen, zu verhindern, zu untersuchen und automatisch auf komplexe Angriffe zu reagieren. 
 
[Weitere Informationen zu Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)


## <a name="related-topics"></a>Verwandte Themen
- [Konfigurieren der Integration und anderer erweiterter Features](advanced-features.md)
- [Übersicht über Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)
- [Microsoft 365 Defender aktivieren](https://docs.microsoft.com/microsoft-365/security/defender/mtp-enable)
- [Schützen von Benutzern, Daten und Geräten mit bedingten Zugriff](conditional-access.md)
