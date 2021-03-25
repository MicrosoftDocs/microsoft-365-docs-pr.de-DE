---
title: Aktivieren von Microsoft 365 Defender im Microsoft 365 Security Center
description: Erfahren Sie, wie Sie Microsoft 365 Defender aktivieren und mit der Integration Ihres Sicherheitsvorfalls und Ihrer Reaktion beginnen.
keywords: Erste Schritte, Aktivieren von MTP, Microsoft Threat Protection, M365, Sicherheit, Datenspeicherort, erforderlichen Berechtigungen, Lizenzberechtigung, Einstellungsseite
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
ms.openlocfilehash: 4165f13e24e1ecb53413025c59bf6f3195525b17
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068623"
---
# <a name="turn-on-microsoft-365-defender"></a>Aktivieren von Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-365-defender.md) vereint Ihren Prozess zur Reaktion auf Vorfälle, indem wichtige Funktionen in Microsoft Defender for Endpoint, Microsoft Defender für Office 365, Microsoft Cloud App Security und Microsoft Defender for Identity integriert werden. Diese vereinheitlichte Lösung bietet zusätzliche leistungsfähige Funktionen, auf die Sie im Microsoft 365 Security Center zugreifen können.

Microsoft 365 Defender wird automatisch aktiviert, wenn berechtigte Kunden mit den erforderlichen Berechtigungen das Microsoft 365 Security Center besuchen. Lesen Sie diesen Artikel, um die verschiedenen Voraussetzungen und die Bereitstellung von Microsoft 365 Defender zu verstehen.

## <a name="check-license-eligibility-and-required-permissions"></a>Überprüfen der Lizenzberechtigung und der erforderlichen Berechtigungen

Eine Lizenz für ein Microsoft 365-Sicherheitsprodukt berechtigt Sie im Allgemeinen, Microsoft 365 Defender im Microsoft 365 Security Center ohne zusätzliche Lizenzierungskosten zu verwenden. Es wird empfohlen, eine Microsoft 365 E5-, E5 Security-, A5- oder A5-Sicherheitslizenz oder eine gültige Kombination von Lizenzen zu erhalten, die Zugriff auf alle unterstützten Dienste bietet.

Ausführliche Lizenzierungsinformationen finden [Sie in den Lizenzierungsanforderungen](prerequisites.md#licensing-requirements).

### <a name="check-your-role"></a>Überprüfen Ihrer Rolle

Sie müssen ein globaler Administrator **oder** **Sicherheitsadministrator** in Azure Active Directory sein, um Microsoft 365 Defender aktivieren zu können. [Anzeigen Ihrer Rollen in Azure AD](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Unterstützte Dienste

Microsoft 365 Defender aggregiert Daten aus den verschiedenen unterstützten Diensten, die Sie bereits bereitgestellt haben. Es wird Daten zentral verarbeiten und speichern, um neue Erkenntnisse zu identifizieren und zentrale Reaktionsworkflows zu ermöglichen. Dies ohne Auswirkungen auf vorhandene Bereitstellungen, Einstellungen oder Daten, die den integrierten Diensten zugeordnet sind.

Um den bestmöglichen Schutz zu erhalten und Microsoft 365 Defender zu optimieren, empfehlen wir die Bereitstellung aller anwendbaren unterstützten Dienste in Ihrem Netzwerk. Weitere Informationen finden Sie [unter Bereitstellen von unterstützten Diensten](deploy-supported-services.md).

## <a name="onboard-to-the-service"></a>Onboarding in den Dienst
Das Onboarding in Microsoft 365 Defender ist einfach. Wählen Sie im Navigationsmenü ein beliebiges Element im Abschnitt Endpunkte aus, z. B. Vorfälle, Suche, Aktionscenter oder Bedrohungsanalyse, um den Onboardingprozess zu initiieren. 

### <a name="data-center-location"></a>Rechenzentrumsspeicherort

Microsoft 365 Defender wird Daten am gleichen Speicherort speichern und verarbeiten, der von [Microsoft Defender for Endpoint verwendet wird.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy) Wenn Sie nicht über Microsoft Defender for Endpoint verfügen, wird basierend auf dem Speicherort aktiver Microsoft 365-Sicherheitsdienste automatisch ein neuer Rechenzentrumsspeicherort ausgewählt. Der ausgewählte Rechenzentrumsspeicherort wird auf dem Bildschirm angezeigt.

Wählen **Sie Hilfe benötigen?** im Microsoft 365 Security Center aus, um den Microsoft-Support über die Bereitstellung von Microsoft 365 Defender an einem anderen Rechenzentrumsstandort zu kontaktieren.

> [!NOTE]
> Microsoft Defender for Endpoint stellt automatisch In Rechenzentren in der Europäischen Union (EU) bereit, wenn sie über Azure Defender aktiviert sind. Microsoft 365 Defender stellt automatisch im gleichen EU-Rechenzentrum Kunden zur Verfügung, die Defender for Endpoint auf diese Weise bereitgestellt haben.

### <a name="confirm-that-the-service-is-on"></a>Vergewissern Sie sich, dass der Dienst aktiviert ist

Sobald der Dienst bereitgestellt ist, wird Folgendes hinzugefügt:

- [Verwalten von Vorfällen](incidents-overview.md)
- [Benachrichtigungswarteschlange](investigate-alerts.md)
- Ein Info-Center für die Verwaltung [automatisierter Untersuchungen und Reaktionen](m365d-autoir.md)
- [Erweiterte Funktionen für die Suche](advanced-hunting-overview.md)
- Bedrohungsanalyse

![Abbildung des Microsoft 365 Security Center-Navigationsbereichs mit Microsoft 365 Defender bietet Microsoft 365 Security Center mit Vorfallverwaltung und anderen ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365 Defender-Funktionen*

### <a name="getting-microsoft-defender-for-identity-data"></a>Abrufen von Microsoft Defender for Identity-Daten 
Um die Integration in Microsoft Cloud App Security zu ermöglichen, müssen Sie sich mindestens einmal bei der Microsoft Cloud App Security anmelden.

## <a name="get-assistance"></a>Unterstützung erhalten

Antworten auf die am häufigsten gestellten Fragen zum Aktivieren von Microsoft 365 Defender finden Sie [in den häufig gestellten Fragen](m365d-enable-faq.md).

Mitarbeiter des Microsoft-Support unterstützen Sie bei der Bereitstellung oder Deprovision des Diensts und der zugehörigen Ressourcen für Ihren Mandanten. Wenn Sie Unterstützung benötigen, **wählen Sie Hilfe?** im Microsoft 365 Security Center aus. Wenn Sie den Support kontaktieren, erwähnen Sie Microsoft 365 Defender.

## <a name="related-topics"></a>Verwandte Themen

- [Häufig gestellte Fragen](m365d-enable-faq.md)
- [Lizenzierungsanforderungen und andere Voraussetzungen](prerequisites.md)
- [Bereitstellen unterstützter Dienste](deploy-supported-services.md)
- [Übersicht über Microsoft 365 Defender](microsoft-365-defender.md)
- [Übersicht über Microsoft Defender for Endpoint](../defender-endpoint/microsoft-defender-advanced-threat-protection.md)
- [Übersicht über Defender for Office 365](../defender-365-security/defender-for-office-365.md)
- [Übersicht über Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)
- [Übersicht über Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp)
- [Datenspeicherung von Microsoft Defender for Endpoint](../defender-endpoint/data-storage-privacy.md)
