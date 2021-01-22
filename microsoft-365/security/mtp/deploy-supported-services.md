---
title: Bereitstellen von Diensten, die von Microsoft 365 Defender unterstützt werden
description: Erfahren Sie mehr über die Microsoft-Sicherheitsdienste, die von Microsoft 365 Defender integriert werden können, deren Lizenzierungsanforderungen und Bereitstellungsverfahren.
keywords: bereitstellen, Lizenzen, unterstützte Dienste, Bereitstellung, Konfiguration Microsoft Threat Protection, M365, Lizenzberechtigung, Microsoft Defender ATP, MDATP, Office 365 ATP, Azure ATP, Microsoft Cloud App Security, MCAS, erweiterter Bedrohungsschutz, E5, A5, EMS
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 5af58a1c6850619ca08960997a30fe4a81158446
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928962"
---
# <a name="deploy-supported-services"></a>Bereitstellen unterstützter Dienste

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft 365 Defender](microsoft-threat-protection.md) integriert verschiedene Microsoft-Sicherheitsdienste, um zentrale Erkennungs-, Verhinderungs- und Untersuchungsfunktionen gegen komplexe Angriffe zu bieten. In diesem Artikel werden die unterstützten Dienste, deren Lizenzierungsanforderungen, die Vorteile und Einschränkungen im Zusammenhang mit der Bereitstellung eines oder mehrerer Dienste sowie Links dazu beschrieben, wie Sie sie einzeln vollständig bereitstellen können.

## <a name="supported-services"></a>Unterstützte Dienste
Eine Microsoft 365 E5-, E5 Security-, A5- oder A5 -Sicherheitslizenz oder eine gültige Kombination von Lizenzen bietet Zugriff auf die folgenden unterstützten Dienste und berechtigt Sie zur Verwendung von Microsoft 365 Defender in Microsoft 365 Security Center. [Siehe Lizenzierungsanforderungen](prerequisites.md#licensing-requirements)

| Unterstützter Dienst | Beschreibung |
| ------ | ------ |
| Microsoft Defender für Endpunkt | Endpoint Protection Suite, die auf leistungsstarken Verhaltenssensoren, Cloudanalysen und Bedrohungsintelligenz aufgebaut ist |
|Microsoft Defender für Office 365 | Erweiterter Schutz für Ihre Apps und Daten in Office 365, einschließlich E-Mail und anderer Tools für die Zusammenarbeit |
| Microsoft Defender for Identity | Schutz vor erweiterten Bedrohungen, gefährdeten Identitäten und böswilligen Insidern mit korrelierten Active Directory-Signalen |
| Microsoft Cloud App-Sicherheit | Identifizieren und Bekämpfen von Cyberbedrohungen in Ihren Microsoft- und Drittanbieter-Clouddiensten |

## <a name="deployed-services-and-functionality"></a>Bereitgestellte Dienste und Funktionen
Microsoft 365 Defender bietet eine bessere Sichtbarkeit, Korrelation und Korrektur, wenn Sie mehr unterstützte Dienste bereitstellen.

### <a name="benefits-of-full-deployment"></a>Vorteile der vollständigen Bereitstellung
Um die vollständigen Vorteile von Microsoft 365 Defender zu nutzen, empfehlen wir die Bereitstellung aller unterstützten Dienste. Hier sind einige der wichtigsten Vorteile einer vollständigen Bereitstellung:
- Vorfälle werden basierend auf Warnungen und Ereignissignalen aller verfügbaren Sensoren und dienstspezifischen Analysefunktionen identifiziert und korreliert.
- Playbooks für automatisierte Untersuchung und Wartung (AIR) gelten für verschiedene Entitätstypen, einschließlich Geräten, Postfächern und Benutzerkonten.
- Ein umfassenderes Erweitertes Suchschema kann nach Ereignis- und Entitätsdaten von Geräten, Postfächern und anderen Entitäten abgefragt werden.

### <a name="limited-deployment-scenarios"></a>Eingeschränkte Bereitstellungsszenarien
Jeder unterstützte Dienst, den Sie bereitstellen, bietet eine äußerst umfangreiche Gruppe von Rohsignalen sowie korrelierte Informationen. Während die eingeschränkte Bereitstellung nicht dazu führen kann, dass die Microsoft 365 -Defender-Funktionalität deaktiviert wird, ist die Möglichkeit, umfassende Transparenz für Ihre Endpunkte, Apps, Daten und Identitäten bereitzustellen, davon betroffen. Gleichzeitig gelten alle Korrekturfunktionen nur für Entitäten, die von den bereitgestellten Diensten verwaltet werden können.

In der folgenden Tabelle ist aufgeführt, wie jeder unterstützte Dienst zusätzliche Daten liefert, Möglichkeiten zum Abrufen zusätzlicher Einblicke durch Korrelieren der Daten sowie bessere Wartungs- und Reaktionsfunktionen.

| Dienst | Daten (Signale & korrelierten Informationen) | Problembehebung & Antwortbereichs |
| ------ | ------ | ------ |
| Microsoft Defender für Endpunkt | – Endpunktzustände und unformatierte Ereignisse<br />– Erkennungen und Warnungen von Endpunkten, einschließlich Antivirus, EDR, Reduzierung der Angriffsfläche<br />- Informationen zu Dateien und anderen Entitäten, die auf Endpunkten beobachtet werden | Endpunkte |
|Microsoft Defender für Office 365 | - E-Mail- und Postfachzustände und unformatierte Ereignisse<br />– E-Mail-, Anlagen- und Linkerkennungen | - Postfächer<br />- Microsoft 365-Konten |
| Microsoft Defender for Identity | – Active Directory-Signale, einschließlich Authentifizierungsereignissen<br />– Identitätsbezogene Verhaltenserkennungen | Identitäten |
| Microsoft Cloud App-Sicherheit | – Erkennung nicht verwendeter Cloud-Apps und -Dienste (Schatten-IT)<br />– Belichtung von Daten für Cloud-Apps<br />– Bedrohungsaktivität im Zusammenhang mit Cloud-Apps | Cloud-Apps |

## <a name="deploy-the-services"></a>Bereitstellen der Dienste
Für die Bereitstellung der einzelnen Dienste ist in der Regel eine Bereitstellung für Ihren Mandanten und einige Erstkonfigurationen erforderlich. In der folgenden Tabelle erfahren Sie, wie diese Dienste bereitgestellt werden.

| Dienst | Bereitstellungsanweisungen | Erstkonfiguration |
| ------ | ------ | ------ |
| Microsoft Defender für Endpunkt | [Bereitstellungshandbuch für Microsoft Defender für Endpunkte](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | *Siehe Bereitstellungsanweisungen* |
|Microsoft Defender für Office 365 | *Keine, bereitgestellt mit Office 365* | [Konfigurieren von Microsoft Defender für Office 365-Richtlinien](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| Microsoft Defender for Identity | [Schnellstart: Erstellen Der Instanz von Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | *Siehe Bereitstellungsanweisungen* |
| Microsoft Cloud App-Sicherheit | *Keine* | [Schnellstart: Erste Schritte mit Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

Nachdem Sie die unterstützten Dienste bereitgestellt haben, aktivieren Sie [Microsoft 365 Defender.](mtp-enable.md)

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über Microsoft 365 Defender](microsoft-threat-protection.md)
- [Aktivieren von Microsoft 365 Defender](mtp-enable.md)
- [Übersicht über Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Übersicht über Microsoft Defender für Office 365](../office-365-security/office-365-atp.md)
- [Übersicht über Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Übersicht über Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
