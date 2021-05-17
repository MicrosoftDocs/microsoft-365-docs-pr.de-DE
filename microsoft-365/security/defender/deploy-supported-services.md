---
title: Bereitstellen von Diensten, die von Microsoft 365 Defender unterstützt werden
description: Erfahren Sie mehr über die Microsoft-Sicherheitsdienste, die von Microsoft 365 Defender integriert werden können, deren Lizenzierungsanforderungen und Bereitstellungsverfahren
keywords: deploy, licenses, supported services, provisioning, configuration Microsoft 365 Defender, M365, license eligibility, Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, Microsoft Cloud App Security, MCAS, E5, A5, EMS
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
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
ms.openlocfilehash: 4e1b36423974e46a485727f7e1f158dc6163d834
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935677"
---
# <a name="deploy-supported-services"></a>Bereitstellen unterstützter Dienste

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft 365 Defender](microsoft-365-defender.md) integriert verschiedene Microsoft-Sicherheitsdienste, um zentrale Erkennungs-, Verhinderungs- und Untersuchungsfunktionen gegen anspruchsvolle Angriffe zu bieten. In diesem Artikel werden die unterstützten Dienste, deren Lizenzierungsanforderungen, die Vorteile und Einschränkungen im Zusammenhang mit der Bereitstellung eines oder mehrerer Dienste sowie Links dazu beschrieben, wie Sie sie vollständig einzeln bereitstellen können.

## <a name="supported-services"></a>Unterstützte Dienste
Eine Microsoft 365 E5, E5 Security, A5 oder A5 Security-Lizenz oder eine gültige Kombination von Lizenzen bietet Zugriff auf die folgenden unterstützten Dienste und berechtigt Sie zur Verwendung von Microsoft 365 Defender in Microsoft 365 Security Center. [Siehe Lizenzierungsanforderungen](prerequisites.md#licensing-requirements)

| Unterstützter Dienst | Beschreibung |
| ------ | ------ |
| Microsoft Defender für Endpunkt | Endpoint Protection Suite, die auf leistungsstarken Verhaltenssensoren, Cloudanalysen und Bedrohungsintelligenz aufgebaut ist |
|Microsoft Defender für Office 365 | Erweiterter Schutz für Ihre Apps und Daten in Office 365, einschließlich E-Mail und anderen Tools für die Zusammenarbeit |
| Microsoft Defender for Identity | Schützen vor erweiterten Bedrohungen, gefährdeten Identitäten und böswilligen Insidern mithilfe korrelierter Active Directory-Signale |
| Microsoft Cloud App Security | Identifizieren und Bekämpfen von Cyberangriffen in Ihren Microsoft- und Drittanbieter-Clouddiensten |

## <a name="deployed-services-and-functionality"></a>Bereitgestellte Dienste und Funktionen
Microsoft 365 Defender bietet eine bessere Sichtbarkeit, Korrelation und Korrektur, wenn Sie mehr unterstützte Dienste bereitstellen.

### <a name="benefits-of-full-deployment"></a>Vorteile der vollständigen Bereitstellung
Um die vorteile von defender Microsoft 365 zu nutzen, empfehlen wir die Bereitstellung aller unterstützten Dienste. Hier sind einige der wichtigsten Vorteile der vollständigen Bereitstellung:
- Vorfälle werden anhand von Warnungen und Ereignissignalen aller verfügbaren Sensoren und dienstspezifischen Analysefunktionen identifiziert und korreliert.
- Air-Playbooks (Automated Investigation and Remediation) gelten für verschiedene Entitätstypen, einschließlich Geräten, Postfächern und Benutzerkonten
- Ein umfassenderes erweitertes Suchschema kann nach Ereignis- und Entitätsdaten von Geräten, Postfächern und anderen Entitäten abgefragt werden.

### <a name="limited-deployment-scenarios"></a>Eingeschränkte Bereitstellungsszenarien
Jeder unterstützte Dienst, den Sie bereitstellen, bietet eine äußerst umfangreiche Reihe von Unformatsignalen sowie korrelierte Informationen. Während die eingeschränkte Bereitstellung nicht dazu Microsoft 365, dass die Funktionen von Defender deaktiviert werden, ist die Möglichkeit, eine umfassende Sichtbarkeit für Ihre Endpunkte, Apps, Daten und Identitäten zu bieten, davon betroffen. Gleichzeitig gelten alle Korrekturfunktionen nur für Entitäten, die von den bereitgestellten Diensten verwaltet werden können.

In der folgenden Tabelle wird aufgelistet, wie jeder unterstützte Dienst zusätzliche Daten, Möglichkeiten zum Abrufen zusätzlicher Einblicke durch Korrelieren der Daten sowie bessere Korrektur- und Reaktionsfunktionen bietet.

| Dienst | Daten (Signale & korrelierten Informationen) | Behebung & Antwortbereichs |
| ------ | ------ | ------ |
| Microsoft Defender für Endpunkt | - Endpunktzustände und unformatierte Ereignisse<br />- Endpunkterkennungen und -warnungen, einschließlich Antivirus, EDR, Reduzierung der Angriffsfläche<br />- Informationen zu Dateien und anderen Entitäten, die auf Endpunkten beobachtet werden | Endpunkte |
|Microsoft Defender für Office 365 | - E-Mail- und Postfachzustände und Unformatierte Ereignisse<br />- E-Mail-, Anlagen- und Linkerkennungen | - Postfächer<br />- Microsoft 365 Konten |
| Microsoft Defender for Identity | – Active Directory-Signale, einschließlich Authentifizierungsereignissen<br />- Identitätsbezogene Verhaltenserkennungen | Identitäten |
| Microsoft Cloud App Security | - Erkennung von nicht installierten Cloud-Apps und -Diensten (Schatten-IT)<br />– Belichtung von Daten für Cloud-Apps<br />– Bedrohungsaktivität im Zusammenhang mit Cloud-Apps | Cloud-Apps |

## <a name="deploy-the-services"></a>Bereitstellen der Dienste
Für die Bereitstellung jedes Diensts ist in der Regel eine Bereitstellung für Ihren Mandanten und eine anfängliche Konfiguration erforderlich. In der folgenden Tabelle erfahren Sie, wie jeder dieser Dienste bereitgestellt wird.

| Dienst | Bereitstellungsanweisungen | Erstkonfiguration |
| ------ | ------ | ------ |
| Microsoft Defender für Endpunkt | [Bereitstellungshandbuch für Microsoft Defender for Endpoint](../defender-endpoint/deployment-phases.md) | *Siehe Bereitstellungsanweisungen* |
|Microsoft Defender für Office 365 | *Keine, bereitgestellt mit Office 365* | [Konfigurieren von Microsoft Defender für Office 365-Richtlinien](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies) |
| Microsoft Defender for Identity | [Schnellstart: Erstellen Ihrer Microsoft Defender for Identity-Instanz](/azure-advanced-threat-protection/install-atp-step1) | *Siehe Bereitstellungsanweisungen* |
| Microsoft Cloud App Security | *Keine* | [Schnellstart: Erste Schritte mit Microsoft Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security) |

Nachdem Sie die unterstützten Dienste bereitgestellt haben, [aktivieren Sie Microsoft 365 Defender](m365d-enable.md).

## <a name="related-topics"></a>Verwandte Themen

- [Microsoft 365 Übersicht über Defender](microsoft-365-defender.md)
- [Microsoft 365 Defender aktivieren](m365d-enable.md)
- [Übersicht über Microsoft Defender for Endpoint](../defender-endpoint/microsoft-defender-endpoint.md)
- [Microsoft Defender for Office 365 Overview](../office-365-security/defender-for-office-365.md)
- [Übersicht über Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)
- [Übersicht über Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp)
