---
title: Bereitstellen von von Microsoft Threat Protection unterstützten Diensten
description: Erfahren Sie mehr über die Microsoft-Sicherheitsdienste, die von Microsoft Threat Protection, ihren Lizenzierungsanforderungen und Bereitstellungsverfahren integriert werden können.
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: c2798238f0e3cb10edab7f98bf096474a80fa006
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857475"
---
# <a name="deploy-supported-services"></a>Bereitstellen unterstützter Dienste

**Gilt für:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft Threat Protection](microsoft-threat-protection.md) integriert verschiedene Microsoft-Sicherheitsdienste, um zentralisierte Erkennungs-, Präventions-und Ermittlungsfunktionen Gegenanspruchs volle Angriffe bereitzustellen. In diesem Artikel werden die unterstützten Dienste, ihre Lizenzierungsanforderungen, die Vorteile und Einschränkungen im Zusammenhang mit der Bereitstellungeines oder mehrerer Dienste sowie Links dazu beschrieben, wie Sie diese vollständig einzeln bereitstellen können.

## <a name="supported-services"></a>Unterstützte Dienste
Eine Microsoft 365 E5, E5 Security, A5 oder A5-Sicherheitslizenz oder eine gültige Kombination von Lizenzen bietet Zugriff auf die folgenden unterstützten Dienste und berechtigt Sie zur Verwendung von Microsoft Threat Protection im Microsoft 365 Security Center. [Siehe Lizenzierungsanforderungen](prerequisites.md#licensing-requirements)

| Unterstützter Dienst | Beschreibung |
| ------ | ------ |
| Microsoft Defender ATP | Endpoint Protection-Suite um leistungsstarke Verhaltens Sensoren, Cloud Analytics und Threat Intelligence |
| Office 365 ATP | Erweiterter Schutz für Ihre apps und Daten in Office 365, einschließlich e-Mail und anderer Tools für die Zusammenarbeit |
| Azure ATP | Schutz vor fortgeschrittenen Bedrohungen, gefährdeten Identitäten und böswilligen Insidern mithilfe korrelierter Active Directory Signale |
| Microsoft Cloud App Security | Identifiziert und bekämpft Bedrohungen in den Cloud-Diensten von Microsoft und Drittanbietern. |

## <a name="deployed-services-and-functionality"></a>Bereitgestellte Dienste und Funktionen
Bei der Bereitstellung von mehr unterstützten Diensten bietet Microsoft Threat Protection eine bessere Sichtbarkeit, Korrelation und Korrektur.

### <a name="benefits-of-full-deployment"></a>Vorteile der vollständigen Bereitstellung
Um die vollständigen Vorteile von Microsoft Threat Protection zu erhalten, empfehlen wir die Bereitstellung aller unterstützten Dienste. Hier sind einige der wichtigsten Vorteile der vollständigen Bereitstellung:
- Vorfälle werden anhand von Warnungen und Ereignis Signalen aus allen verfügbaren Sensoren und dienstspezifischen Analysefunktionen identifiziert und korreliert.
- Automatische Untersuchung und Behebung (Air) Textbuch gilt für verschiedene Entitätstypen, einschließlich Geräten, Postfächern und Benutzerkonten.
- Eine umfassendere erweiterte Jagd Schema kann für Ereignis-und Entitätsdaten von Geräten, Postfächern und anderen Entitäten abgefragt werden

### <a name="limited-deployment-scenarios"></a>Szenarien mit begrenzten Bereitstellungen
Jeder unterstützte Dienst, den Sie bereitstellen, bietet eine äußerst umfangreiche Reihe von unformatierten Signalen sowie korrelierte Informationen. Während die eingeschränkte Bereitstellung nicht dazu führt, dass Microsoft Threat Protection-Funktionen deaktiviert werden, ist die Möglichkeit, eine umfassende Sichtbarkeit über ihre Endpunkte, apps, Daten und Identitäten hinweg zu gewährleisten, davon betroffen. Gleichzeitig gelten alle Korrekturfunktionen nur für Entitäten, die von den von Ihnen bereitgestellten Diensten verwaltet werden können.

In der folgenden Tabelle ist aufgeführt, wie jeder unterstützte Dienst zusätzliche Daten bereitstellt, Möglichkeiten zum Abrufen zusätzlicher Einblicke durch Korrelation der Daten und bessere Korrektur-und Reaktionsfunktionen.

| Dienst | Daten (Signale & korrelierten Informationen) | Korrektur & Reaktionsbereich |
| ------ | ------ | ------ |
| Microsoft Defender ATP | -Endpunkt Zustände und Rohdaten Ereignisse<br />-Endpunkt Erkennungen und Warnungen, einschließlich Antivirus, EDR, Verringerung der Angriffsfläche<br />-Informationen zu Dateien und anderen Entitäten, die an Endpunkten beobachtet werden | Endpunkte |
| Office 365 ATP | -Mail-und Postfachstatus und RAW-Ereignisse<br />-E-Mail-, Anlagen-und Link Erkennungen | -Postfächer<br />-Office 365 Konten |
| Azure ATP | -Active Directory Signale, einschließlich Authentifizierungsereignissen<br />-Identitätsbezogene Verhaltens Erkennungen | Identitäten |
| Microsoft Cloud App Security | -Erkennung von nicht sanktionierten Cloud-apps & Diensten (Shadow IT)<br />-Belichtung von Daten an Cloud-apps<br />-Bedrohungsaktivität, die Cloud-apps zugeordnet ist | Cloud-Apps |

## <a name="deploy-the-services"></a>Bereitstellen der Dienste
Für die Bereitstellung der einzelnen Dienste ist in der Regel ein Bereitstellungsaufwand für den Mandanten und eine anfängliche Konfiguration erforderlich. In der folgenden Tabelle erfahren Sie, wie diese Dienste bereitgestellt werden.

| Dienst | Anweisungen zur Vorstellung | Erstkonfiguration |
| ------ | ------ | ------ |
| Microsoft Defender ATP | [Microsoft Defender ATP-Bereitstellungshandbuch](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | *Siehe Anweisungen zur Vorstellungs Anweisung* |
| Office 365 ATP | *None, mit Office 365* | [Konfigurieren von ATP-Richtlinien](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| Azure ATP | [Schnellstart: Erstellen Ihrer Azure ATP-Instanz](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | *Siehe Anweisungen zur Vorstellungs Anweisung* |
| Microsoft Cloud App Security | *Keine* | [Schnellstart: Erste Schritte mit der Microsoft Cloud-App-Sicherheit](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

Nachdem Sie die unterstützten Dienste bereitgestellt haben, [Aktivieren Sie Microsoft Threat Protection](mtp-enable.md).

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über Microsoft Threat Protection](microsoft-threat-protection.md)
- [Aktivieren von Microsoft Threat Protection](mtp-enable.md)
- [Übersicht über Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Übersicht über Office 365 ATP](../office-365-security/office-365-atp.md)
- [Übersicht über Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Übersicht über Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
