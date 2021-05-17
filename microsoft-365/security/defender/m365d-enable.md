---
title: Aktivieren Microsoft 365 Defender im Microsoft 365 Security Center
description: Erfahren Sie, wie Sie Microsoft 365 Defender aktivieren und mit der Integration Ihres Sicherheitsvorfalls und Ihrer Reaktion beginnen.
keywords: Erste Schritte, Aktivieren Microsoft 365 Defender, Microsoft 365 Defender, M365, Sicherheit, Datenspeicherort, erforderliche Berechtigungen, Lizenzberechtigung, Einstellungsseite
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
ms.openlocfilehash: 2d69ae70b137c9e5378958721f7f9958e57c0306
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935641"
---
# <a name="turn-on-microsoft-365-defender"></a>Microsoft 365 Defender aktivieren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-365-defender.md) vereint Ihren Prozess zur Reaktion auf Vorfälle, indem wichtige Funktionen in Microsoft Defender for Endpoint, Microsoft Defender für Office 365, Microsoft Cloud App Security und Microsoft Defender for Identity integriert werden. Diese vereinheitlichte Lösung bietet zusätzliche leistungsfähige Funktionen, auf die Sie im Microsoft 365 Security Center zugreifen können.

Microsoft 365 Defender wird automatisch aktiviert, wenn berechtigte Kunden mit den erforderlichen Berechtigungen das Microsoft 365 besuchen. In diesem Artikel erfahren Sie mehr über die verschiedenen Voraussetzungen und Microsoft 365 Bereitstellung von Defender.

## <a name="check-license-eligibility-and-required-permissions"></a>Überprüfen der Lizenzberechtigung und der erforderlichen Berechtigungen

Eine Lizenz für Microsoft 365 Sicherheitsprodukt berechtigt Sie im Allgemeinen zur Verwendung von Microsoft 365 Defender in Microsoft 365 Security Center ohne zusätzliche Lizenzierungskosten. Es wird empfohlen, eine Microsoft 365 E5, eine E5 Security-, A5- oder A5-Sicherheitslizenz oder eine gültige Kombination von Lizenzen zu erhalten, die Zugriff auf alle unterstützten Dienste bietet.

Ausführliche Lizenzierungsinformationen finden [Sie in den Lizenzierungsanforderungen](prerequisites.md#licensing-requirements).

### <a name="check-your-role"></a>Überprüfen Ihrer Rolle

Sie müssen ein **globaler Administrator oder** **Sicherheitsadministrator** in Azure Active Directory sein, um defender Microsoft 365 aktivieren. [Anzeigen Ihrer Rollen in Azure AD](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Unterstützte Dienste

Microsoft 365 Defender aggregiert Daten aus den verschiedenen unterstützten Diensten, die Sie bereits bereitgestellt haben. Es wird Daten zentral verarbeiten und speichern, um neue Erkenntnisse zu identifizieren und zentrale Reaktionsworkflows zu ermöglichen. Dies ohne Auswirkungen auf vorhandene Bereitstellungen, Einstellungen oder Daten, die den integrierten Diensten zugeordnet sind.

Um den bestmöglichen Schutz zu erhalten und Microsoft 365 Defender zu optimieren, empfehlen wir die Bereitstellung aller anwendbaren unterstützten Dienste in Ihrem Netzwerk. Weitere Informationen finden Sie [unter Bereitstellen von unterstützten Diensten](deploy-supported-services.md).

## <a name="onboard-to-the-service"></a>Onboarding in den Dienst
Das Onboarding Microsoft 365 Defender ist einfach. Wählen Sie im Navigationsmenü ein beliebiges Element im Abschnitt Endpunkte aus, z. B. Vorfälle, Suche, Aktionscenter oder Bedrohungsanalyse, um den Onboardingprozess zu initiieren. 

### <a name="data-center-location"></a>Rechenzentrumsspeicherort

Microsoft 365 Defender wird Daten am gleichen Speicherort speichern und verarbeiten, [der von Microsoft Defender for Endpoint verwendet wird.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy) Wenn Sie nicht über Microsoft Defender for Endpoint verfügen, wird automatisch ein neuer Rechenzentrumsspeicherort basierend auf dem Speicherort der aktiven Microsoft 365 ausgewählt. Der ausgewählte Rechenzentrumsspeicherort wird auf dem Bildschirm angezeigt.

Wählen **Sie Hilfe benötigen?** im Microsoft 365 Security Center aus, um den Microsoft-Support zur Bereitstellung von Microsoft 365 Defender an einem anderen Rechenzentrumsspeicherort zu kontaktieren.

> [!NOTE]
> Microsoft Defender for Endpoint stellt automatisch In Rechenzentren in der Europäischen Union (EU) bereit, wenn sie über Azure Defender aktiviert sind. Microsoft 365 Defender wird automatisch im gleichen EU-Rechenzentrum für Kunden bereitgestellt, die Defender for Endpoint auf diese Weise bereitgestellt haben.

### <a name="confirm-that-the-service-is-on"></a>Vergewissern Sie sich, dass der Dienst aktiviert ist

Sobald der Dienst bereitgestellt ist, wird Folgendes hinzugefügt:

- [Verwalten von Vorfällen](incidents-overview.md)
- [Benachrichtigungswarteschlange](investigate-alerts.md)
- Ein Info-Center für die Verwaltung [automatisierter Untersuchungen und Reaktionen](m365d-autoir.md)
- [Erweiterte Funktionen für die Suche](advanced-hunting-overview.md)
- Bedrohungsanalyse

![Abbildung des Microsoft 365 Security Center-Navigationsbereichs mit Microsoft 365 Defender-Features Microsoft 365 Security Center mit Vorfallverwaltung und ](../../media/overview-incident.png)
 *anderen funktionen Microsoft 365 Defender*

### <a name="getting-microsoft-defender-for-identity-data"></a>Abrufen von Microsoft Defender for Identity-Daten 
Um die Integration in Microsoft Cloud App Security zu aktivieren, müssen Sie sich mindestens einmal bei Microsoft Cloud App Security anmelden.

## <a name="get-assistance"></a>Unterstützung erhalten

Antworten auf die am häufigsten gestellten Fragen zum Aktivieren von Microsoft 365 Defender finden Sie in den [häufig gestellten Fragen](m365d-enable-faq.md).

Mitarbeiter des Microsoft-Support unterstützen Sie bei der Bereitstellung oder Deprovision des Diensts und der zugehörigen Ressourcen für Ihren Mandanten. Wenn Sie Unterstützung benötigen, wählen Sie **Hilfe?** im Microsoft 365 Sicherheitscenter aus. Wenn Sie sich an den Support wenden, Microsoft 365 Defender.

## <a name="related-topics"></a>Verwandte Themen

- [Häufig gestellte Fragen](m365d-enable-faq.md)
- [Lizenzierungsanforderungen und andere Voraussetzungen](prerequisites.md)
- [Bereitstellen unterstützter Dienste](deploy-supported-services.md)
- [Microsoft 365 Übersicht über Defender](microsoft-365-defender.md)
- [Übersicht über Microsoft Defender for Endpoint](../defender-endpoint/microsoft-defender-endpoint.md)
- [Defender for Office 365 Overview](../office-365-security/defender-for-office-365.md)
- [Übersicht über Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)
- [Übersicht über Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp)
- [Datenspeicherung von Microsoft Defender for Endpoint](../defender-endpoint/data-storage-privacy.md)
