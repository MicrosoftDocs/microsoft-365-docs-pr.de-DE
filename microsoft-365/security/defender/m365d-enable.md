---
title: Aktivieren Microsoft 365 Defender im Microsoft 365 Security Center
description: Erfahren Sie, wie Sie Microsoft 365 Defender aktivieren und mit der Integration Ihres Sicherheitsvorfalls und Ihrer Reaktion beginnen.
keywords: erste Schritte, aktivieren sie Microsoft 365 Defender, Microsoft 365 Defender, M365, Sicherheit, Datenspeicherort, erforderliche Berechtigungen, Lizenzberechtigung, Einstellungsseite
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 3f05cc8c9b2509f8c95b802f56905e2859221cd2
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861599"
---
# <a name="turn-on-microsoft-365-defender"></a>Microsoft 365 Defender aktivieren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-365-defender.md) vereinheitlicht Ihren Vorfallreaktionsprozess, indem wichtige Funktionen in Microsoft Defender für Endpunkt, Microsoft Defender für Office 365, Microsoft Cloud App Security und Microsoft Defender for Identity integriert werden. Diese vereinheitlichte Lösung bietet zusätzliche leistungsfähige Funktionen, auf die Sie im Microsoft 365 Security Center zugreifen können.

Microsoft 365 Defender wird automatisch aktiviert, wenn berechtigte Kunden mit den erforderlichen Berechtigungen Microsoft 365 Security Center besuchen. Lesen Sie diesen Artikel, um verschiedene Voraussetzungen zu verstehen und zu erfahren, wie Microsoft 365 Defender bereitgestellt wird.

## <a name="check-license-eligibility-and-required-permissions"></a>Überprüfen der Lizenzberechtigung und der erforderlichen Berechtigungen

Eine Lizenz für ein Microsoft 365-Sicherheitsprodukt berechtigt Sie in der Regel dazu, Microsoft 365 Defender im Microsoft 365 Security Center ohne zusätzliche Lizenzierungskosten zu verwenden. Es wird empfohlen, eine Microsoft 365 E5-, E5 Security-, A5- oder A5 Security-Lizenz oder eine gültige Kombination von Lizenzen zu erhalten, die Zugriff auf alle unterstützten Dienste bietet.

Ausführliche Informationen zur Lizenzierung [finden Sie in den Lizenzierungsanforderungen.](prerequisites.md#licensing-requirements)

### <a name="check-your-role"></a>Überprüfen Ihrer Rolle

Sie müssen ein **globaler Administrator** oder **Sicherheitsadministrator** in Azure Active Directory sein, um Microsoft 365 Defender zu aktivieren. [Anzeigen Ihrer Rollen in Azure AD](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Unterstützte Dienste

Microsoft 365 Defender aggregiert Daten aus den verschiedenen unterstützten Diensten, die Sie bereits bereitgestellt haben. Sie verarbeitet und speichert Daten zentral, um neue Erkenntnisse zu identifizieren und zentrale Reaktionsworkflows zu ermöglichen. Dies geschieht ohne Auswirkungen auf vorhandene Bereitstellungen, Einstellungen oder Daten, die den integrierten Diensten zugeordnet sind.

Um den besten Schutz zu erhalten und Microsoft 365 Defender zu optimieren, empfehlen wir die Bereitstellung aller anwendbaren unterstützten Dienste in Ihrem Netzwerk. Weitere Informationen [finden Sie unter "Bereitstellen unterstützter Dienste".](deploy-supported-services.md)

## <a name="onboard-to-the-service"></a>Onboarding in den Dienst
Das Onboarding in Microsoft 365 Defender ist einfach. Wählen Sie im Navigationsmenü alle Microsoft 365 Defender-Elemente aus, z. B. Vorfälle, Suche, Info-Center oder Bedrohungsanalyse, um den Integrationsprozess zu initiieren. 

### <a name="data-center-location"></a>Rechenzentrumsstandort

Microsoft 365 Defender speichert und verarbeitet Daten am gleichen Speicherort, der [von Microsoft Defender für Endpunkt verwendet wird.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy) Wenn Sie nicht über Microsoft Defender für Endpunkt verfügen, wird basierend auf dem Standort der aktiven Microsoft 365 Sicherheitsdienste automatisch ein neuer Rechenzentrumsstandort ausgewählt. Der ausgewählte Rechenzentrumsstandort wird auf dem Bildschirm angezeigt.

Wählen Sie **"Benötigen Sie Hilfe?"** im Microsoft 365 Security Center aus, um sich an den Microsoft-Support zu wenden, um Microsoft 365 Defender an einem anderen Rechenzentrumsstandort bereitzustellen.

> [!NOTE]
> In der Vergangenheit wurde Microsoft Defender für Endpunkt automatisch in Rechenzentren der Europäischen Union (EU) bereitgestellt, wenn es über Azure Defender aktiviert wurde. Microsoft 365 Defender stellt automatisch im selben EU-Rechenzentrum für Kunden bereit, die Defender für Endpunkt in der Vergangenheit auf diese Weise bereitgestellt haben.

### <a name="confirm-that-the-service-is-on"></a>Vergewissern Sie sich, dass der Dienst aktiviert ist

Sobald der Dienst bereitgestellt ist, wird Folgendes hinzugefügt:

- [Verwalten von Vorfällen](incidents-overview.md)
- [Benachrichtigungswarteschlange](investigate-alerts.md)
- Ein Info-Center für die Verwaltung [automatisierter Untersuchungen und Reaktionen](m365d-autoir.md)
- [Erweiterte Suchfunktionen](advanced-hunting-overview.md)
- Bedrohungsanalyse

![Abbildung des Navigationsbereichs Microsoft 365 Sicherheitscenters mit Microsoft 365 Defender-Features ](../../media/overview-incident.png)
 *Microsoft 365 Security Center mit Vorfallverwaltung und anderen Microsoft 365 Defender-Funktionen*

### <a name="getting-microsoft-defender-for-identity-data"></a>Abrufen von Microsoft Defender for Identity-Daten 
Um die Integration in Microsoft Cloud App Security zu aktivieren, müssen Sie sich mindestens einmal beim Microsoft Cloud App Security anmelden.

## <a name="get-assistance"></a>Unterstützung erhalten

Um Antworten auf die am häufigsten gestellten Fragen zum Aktivieren von Microsoft 365 Defender zu erhalten, [lesen Sie die häufig gestellten Fragen.](m365d-enable-faq.md)

Microsoft-Supportmitarbeiter können ihnen dabei helfen, den Dienst und die zugehörigen Ressourcen auf Ihrem Mandanten bereitzustellen oder aufzuheben. Um Hilfe zu erhalten, wählen **Sie "Benötigen Sie Hilfe?"** im Microsoft 365 Security Center aus. Wenn Sie sich an den Support wenden, erwähnen Sie Microsoft 365 Defender.

## <a name="related-topics"></a>Verwandte Themen

- [Häufig gestellte Fragen](m365d-enable-faq.md)
- [Lizenzierungsanforderungen und andere Voraussetzungen](prerequisites.md)
- [Bereitstellen unterstützter Dienste](deploy-supported-services.md)
- [Microsoft 365 Übersicht über Defender](microsoft-365-defender.md)
- [Übersicht über Microsoft Defender für Endpunkt](../defender-endpoint/microsoft-defender-endpoint.md)
- [Übersicht über Defender für Office 365](../office-365-security/defender-for-office-365.md)
- [Übersicht über Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)
- [Übersicht über Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender für Endpunkt-Datenspeicherung](../defender-endpoint/data-storage-privacy.md)
