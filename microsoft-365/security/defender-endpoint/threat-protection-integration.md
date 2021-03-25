---
title: Integrieren von Microsoft Defender for Endpoint in andere Microsoft-Lösungen
description: Erfahren Sie, wie Microsoft Defender for Endpoint in andere Microsoft-Lösungen integriert wird, einschließlich Microsoft Defender for Identity und Azure Security Center.
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: microsoft 365 Defender, bedingter Zugriff, Office, erweiterter Bedrohungsschutz, Microsoft Defender for Identity, Microsoft Defender for Office, Azure Security Center, Microsoft Cloud App Security, Azure Sentinel
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
ms.openlocfilehash: 287ad9adeccd527b756bdd5304d3c89fc1b2d789
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068455"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a>Microsoft Defender für Endpoint und andere Microsoft-Lösungen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a>Integration in andere Microsoft-Lösungen

Microsoft Defender for Endpoint kann direkt in verschiedene Microsoft-Lösungen integriert werden.

### <a name="azure-security-center"></a>Azure Security Center
Microsoft Defender for Endpoint bietet eine umfassende Serverschutzlösung, einschließlich der Funktionen für die Erkennung und Reaktion von Endpunkten (Endpoint Detection and Response, EDR) auf Windows-Servern.

### <a name="azure-sentinel"></a>Azure Sentinel
Mit dem Microsoft Defender for Endpoint-Connector können Sie Warnungen von Microsoft Defender for Endpoint in Azure Sentinel streamen. Auf diese Weise können Sie Sicherheitsereignisse in Ihrer Organisation umfassender analysieren und Playbooks für eine effektive und sofortige Reaktion erstellen.

### <a name="azure-information-protection"></a>Azure Information Protection
Schützen Sie vertrauliche Daten, und ermöglichen Sie gleichzeitig die Produktivität am Arbeitsplatz durch Datenermittlung und Datenschutz.

### <a name="conditional-access"></a>Bedingter Zugriff
Die dynamische Geräterisikobewertung von Microsoft Defender for Endpoint ist in die Bewertung für bedingten Zugriff integriert und stellt sicher, dass nur sichere Geräte Zugriff auf Ressourcen haben. 

### <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security
Microsoft Cloud App Security nutzt Microsoft Defender for Endpoint-Endpunktsignale, um eine direkte Sichtbarkeit der Verwendung von Cloudanwendung zu ermöglichen, einschließlich der Verwendung nicht unterstützter Clouddienste (Shadow-IT) von allen überwachten Microsoft Defender for Endpoint-Geräten.

### <a name="microsoft-defender-for-identity"></a>Microsoft Defender for Identity
Verdächtige Aktivitäten sind Prozesse, die in einem Benutzerkontext ausgeführt werden. Die Integration zwischen Microsoft Defender for Endpoint und Azure ATP bietet die Flexibilität der Durchführung von Cybersicherheitsuntersuchungen über Aktivitäten und Identitäten hinweg.

### <a name="microsoft-defender-for-office"></a>Microsoft Defender for Office
[Defender für Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) schützt Ihre Organisation vor Schadsoftware in E-Mail-Nachrichten oder Dateien über ATP Safe Links, ATP Safe Attachments, advanced Anti-Phishing und Spoof Intelligence-Funktionen. Durch die Integration zwischen Office 365 ATP und Microsoft Defender for Endpoint können Sicherheitsanalysten den Einstiegspunkt eines Angriffs untersuchen. Durch die Freigabe von Bedrohungsinformationen können Angriffe verhindert und verhindert werden. 

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
- [Aktivieren von Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/mtp-enable)
- [Schützen von Benutzern, Daten und Geräten mit bedingten Zugriff](conditional-access.md)
