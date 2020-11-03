---
title: Bereitstellen von von Microsoft 365 Defender unterstützten Diensten
description: Informationen zu den Microsoft-Sicherheitsdiensten, die von Microsoft 365 Defender, ihren Lizenzierungsanforderungen und Bereitstellungsverfahren integriert werden können
keywords: bereitstellen, Lizenzen, unterstützte Dienste, Bereitstellung, Konfiguration von Microsoft Threat Protection, M365, Lizenz Berechtigung, Microsoft Defender ATP, MDATP, Office 365 ATP, Azure ATP, Microsoft Cloud App Security, MCAS, Advanced Threat Protection, E5, A5, EMS
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 4a1bed4d6c6688c266b9df8ce36e4b25a0632d68
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843924"
---
# <a name="deploy-supported-services"></a>Bereitstellen unterstützter Dienste

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft 365 Defender](microsoft-threat-protection.md) integriert verschiedene Microsoft-Sicherheitsdienste, um zentralisierte Erkennungs-, Präventions-und Ermittlungsfunktionen Gegenanspruchs volle Angriffe bereitzustellen. In diesem Artikel werden die unterstützten Dienste, ihre Lizenzierungsanforderungen, die Vorteile und Einschränkungen im Zusammenhang mit der Bereitstellungeines oder mehrerer Dienste sowie Links dazu beschrieben, wie Sie diese vollständig einzeln bereitstellen können.

## <a name="supported-services"></a>Unterstützte Dienste
Eine Microsoft 365 E5, E5 Security, A5 oder A5-Sicherheitslizenz oder eine gültige Kombination von Lizenzen bietet Zugriff auf die folgenden unterstützten Dienste und berechtigt Sie zur Verwendung von Microsoft 365 Defender im Microsoft 365 Security Center. [Siehe Lizenzierungsanforderungen](prerequisites.md#licensing-requirements)

| Unterstützter Dienst | Beschreibung |
| ------ | ------ |
| Microsoft Defender für Endpunkt | Endpoint Protection-Suite um leistungsstarke Verhaltens Sensoren, Cloud Analytics und Threat Intelligence |
|Microsoft Defender für Office 365 | Erweiterter Schutz für Ihre apps und Daten in Office 365, einschließlich e-Mail und anderer Tools für die Zusammenarbeit |
| Microsoft Defender für Identity | Schutz vor fortgeschrittenen Bedrohungen, gefährdeten Identitäten und böswilligen Insidern mithilfe korrelierter Active Directory Signale |
| Microsoft Cloud App-Sicherheit | Identifizieren und bekämpfen von Bedrohungen in den Cloud-Diensten von Microsoft und Drittanbietern |

## <a name="deployed-services-and-functionality"></a>Bereitgestellte Dienste und Funktionen
Microsoft 365 Defender bietet bei der Bereitstellung von mehr unterstützten Diensten eine bessere Sichtbarkeit, Korrelation und Korrektur.

### <a name="benefits-of-full-deployment"></a>Vorteile der vollständigen Bereitstellung
Um die vollständigen Vorteile von Microsoft 365 Defender zu erhalten, empfehlen wir die Bereitstellung aller unterstützten Dienste. Hier sind einige der wichtigsten Vorteile der vollständigen Bereitstellung:
- Vorfälle werden anhand von Warnungen und Ereignis Signalen aus allen verfügbaren Sensoren und dienstspezifischen Analysefunktionen identifiziert und korreliert.
- Automatische Untersuchung und Behebung (Air) Textbuch gilt für verschiedene Entitätstypen, einschließlich Geräten, Postfächern und Benutzerkonten.
- Eine umfassendere erweiterte Jagd Schema kann für Ereignis-und Entitätsdaten von Geräten, Postfächern und anderen Entitäten abgefragt werden

### <a name="limited-deployment-scenarios"></a>Szenarien mit begrenzten Bereitstellungen
Jeder unterstützte Dienst, den Sie bereitstellen, bietet eine äußerst umfangreiche Reihe von unformatierten Signalen sowie korrelierte Informationen. Während die eingeschränkte Bereitstellung nicht dazu führt, dass die Funktionalität von Microsoft 365 Defender deaktiviert wird, ist die Möglichkeit, eine umfassende Sichtbarkeit über ihre Endpunkte, apps, Daten und Identitäten hinweg zu gewährleisten, davon betroffen. Gleichzeitig gelten alle Korrekturfunktionen nur für Entitäten, die von den von Ihnen bereitgestellten Diensten verwaltet werden können.

In der folgenden Tabelle ist aufgeführt, wie jeder unterstützte Dienst zusätzliche Daten bereitstellt, Möglichkeiten zum Abrufen zusätzlicher Einblicke durch Korrelation der Daten und bessere Korrektur-und Reaktionsfunktionen.

| Dienst | Daten (Signale & korrelierten Informationen) | Korrektur & Reaktionsbereich |
| ------ | ------ | ------ |
| Microsoft Defender für Endpunkt | -Endpunkt Zustände und Rohdaten Ereignisse<br />-Endpunkt Erkennungen und Warnungen, einschließlich Antivirus, EDR, Verringerung der Angriffsfläche<br />-Informationen zu Dateien und anderen Entitäten, die an Endpunkten beobachtet werden | Endpunkte |
|Microsoft Defender für Office 365 | -Mail-und Postfachstatus und RAW-Ereignisse<br />-E-Mail-, Anlagen-und Link Erkennungen | -Postfächer<br />-Microsoft 365-Konten |
| Microsoft Defender für Identity | -Active Directory Signale, einschließlich Authentifizierungsereignissen<br />-Identitätsbezogene Verhaltens Erkennungen | Identitäten |
| Microsoft Cloud App-Sicherheit | -Erkennung unsanktionierter Cloud-apps und-Dienste (Shadow IT)<br />-Belichtung von Daten an Cloud-apps<br />-Bedrohungsaktivität im Zusammenhang mit Cloud-apps | Cloud-Apps |

## <a name="deploy-the-services"></a>Bereitstellen der Dienste
Für die Bereitstellung der einzelnen Dienste ist in der Regel ein Bereitstellungsaufwand für den Mandanten und eine anfängliche Konfiguration erforderlich. In der folgenden Tabelle erfahren Sie, wie diese Dienste bereitgestellt werden.

| Dienst | Anweisungen zur Vorstellung | Erstkonfiguration |
| ------ | ------ | ------ |
| Microsoft Defender für Endpunkt | [Microsoft Defender für Endpoint-Bereitstellungshandbuch](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | *Siehe Anweisungen zur Vorstellungs Anweisung* |
|Microsoft Defender für Office 365 | *None, mit Office 365* | [Konfigurieren von Microsoft Defender für Office 365-Richtlinien](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| Microsoft Defender für Identity | [Schnellstart: Erstellen Sie Ihren Microsoft Defender für die Identitäts Instanz](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | *Siehe Anweisungen zur Vorstellungs Anweisung* |
| Microsoft Cloud App-Sicherheit | *Keine* | [Schnellstart: Erste Schritte mit der Microsoft Cloud-App-Sicherheit](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

Nachdem Sie die unterstützten Dienste bereitgestellt haben, [Aktivieren Sie Microsoft 365 Defender](mtp-enable.md).

## <a name="related-topics"></a>Verwandte Themen

- [Microsoft 365 Defender (Übersicht)](microsoft-threat-protection.md)
- [Aktivieren von Microsoft 365 Defender](mtp-enable.md)
- [Microsoft Defender für Endpoint (Übersicht)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Microsoft Defender für Office 365 Übersicht](../office-365-security/office-365-atp.md)
- [Übersicht über Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Übersicht über Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
