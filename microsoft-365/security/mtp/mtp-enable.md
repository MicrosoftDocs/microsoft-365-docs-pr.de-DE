---
title: Aktivieren von Microsoft 365 Defender im Microsoft 365 Security Center
description: Erfahren Sie, wie Sie Microsoft 365 Defender aktivieren und mit der Integration Ihres Sicherheitsvorfalls und ihrer Reaktion beginnen.
keywords: Erste Schritte, MTP aktivieren, Microsoft Threat Protection, M365, Sicherheit, Datenspeicherort, erforderliche Berechtigungen, Lizenzberechtigung, Einstellungsseite
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 19f035a271626077911b05082a4aba6d67355cdb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930222"
---
# <a name="turn-on-microsoft-365-defender"></a>Aktivieren von Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-threat-protection.md) vereint Ihren Prozess zur Reaktion auf Vorfälle, indem wichtige Funktionen in Microsoft Defender für Endpoint, Microsoft Defender für Office 365, Microsoft Cloud App Security und Microsoft Defender for Identity integriert werden. Diese vereinheitlichte Lösung bietet zusätzliche leistungsfähige Funktionen, auf die Sie im Microsoft 365 Security Center zugreifen können.

Microsoft 365 Defender wird automatisch aktiviert, wenn berechtigte Kunden mit den erforderlichen Berechtigungen das Microsoft 365 Security Center besuchen. Lesen Sie diesen Artikel, um die verschiedenen Voraussetzungen und die Bereitstellung von Microsoft 365 Defender zu verstehen.

## <a name="check-license-eligibility-and-required-permissions"></a>Überprüfen der Lizenzberechtigung und der erforderlichen Berechtigungen

Eine Lizenz für ein Microsoft 365-Sicherheitsprodukt berechtigt Sie im Allgemeinen, Microsoft 365 Defender im Microsoft 365 Security Center ohne zusätzliche Lizenzierungskosten zu verwenden. Es wird empfohlen, eine Microsoft 365 E5-, E5 Security-, A5- oder A5 -Sicherheitslizenz oder eine gültige Kombination von Lizenzen zu erhalten, die Zugriff auf alle unterstützten Dienste bietet.

Ausführliche Lizenzierungsinformationen finden [Sie in den Lizenzierungsanforderungen.](prerequisites.md#licensing-requirements)

### <a name="check-your-role"></a>Überprüfen Ihrer Rolle

Sie müssen ein globaler **Administrator oder** ein **Sicherheitsadministrator** in Azure Active Directory sein, um Microsoft 365 Defender zu aktivieren. [Anzeigen Ihrer Rollen in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Unterstützte Dienste

Microsoft 365 Defender aggregiert Daten aus den verschiedenen unterstützten Diensten, die Sie bereits bereitgestellt haben. Es wird Daten zentral verarbeiten und speichern, um neue Einblicke zu identifizieren und zentrale Reaktionsworkflows zu ermöglichen. Dies wird ohne Auswirkungen auf vorhandene Bereitstellungen, Einstellungen oder Daten, die den integrierten Diensten zugeordnet sind, verwendet.

Um den besten Schutz zu erhalten und Microsoft 365 Defender zu optimieren, empfehlen wir die Bereitstellung aller anwendbaren unterstützten Dienste in Ihrem Netzwerk. Weitere Informationen finden Sie [unter Bereitstellung unterstützter Dienste.](deploy-supported-services.md)

## <a name="before-starting-the-service"></a>Vor dem Starten des Diensts

Bevor Sie den Dienst aktivieren, zeigt das Microsoft 365 Security Center ([security.microsoft.com](https://security.microsoft.com)) die Seite mit den Microsoft  365 Defender-Einstellungen an, wenn Sie im **Navigationsbereich**"Vorfälle", **"Action** Center" oder "Suche" auswählen. Diese Navigationselemente werden nicht angezeigt, wenn Sie nicht berechtigt sind, Microsoft 365 Defender zu verwenden.

![Abbildung der Microsoft 365 Defender-Einstellungsseite, die angezeigt wird, wenn Microsoft 365 Defender nicht auf ](../../media/mtp-enable/mtp-settings.png)
 *Microsoft 365 Defender-Einstellungen im Microsoft 365 Security Center aktiviert wurde*

## <a name="starting-the-service"></a>Starten des Diensts

Um Microsoft 365 Defender zu aktivieren, wählen Sie einfach **"Microsoft 365 Defender** aktivieren" aus, und wenden Sie die Änderung an. Sie können auch auf diese Option zugreifen, indem Sie einstellungen **(** [security.microsoft.com/settings](https://security.microsoft.com/settings)) im Navigationsbereich und dann **Microsoft 365 Defender auswählen.**

> [!NOTE]
> Wenn die Einstellungen  im Navigationsbereich nicht angezeigt werden oder nicht auf die Seite zugreifen konnten, überprüfen Sie Ihre Berechtigungen und Lizenzen.

### <a name="data-center-location"></a>Rechenzentrumsstandort

Microsoft 365 Defender wird Daten am gleichen Speicherort speichern und verarbeiten, der von [Microsoft Defender für Endpunkt verwendet wird.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy) Wenn Sie nicht über Microsoft Defender for Endpoint verfügen, wird basierend auf dem Speicherort der aktiven Microsoft 365-Sicherheitsdienste automatisch ein neuer Rechenzentrumsstandort ausgewählt. Der ausgewählte Standort des Rechenzentrums wird auf dem Bildschirm angezeigt.

Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.

> [!NOTE]
> Microsoft Defender for Endpoint wird automatisch in Rechenzentren der Europäischen Union (EU) bereitgestellt, wenn sie über Azure Defender aktiviert sind. Microsoft 365 Defender wird automatisch im selben EU-Rechenzentrum für Kunden bereitgestellt, die Defender for Endpoint auf diese Weise bereitgestellt haben.

### <a name="confirm-that-the-service-is-on"></a>Vergewissern Sie sich, dass der Dienst aktiviert ist

Sobald der Dienst bereitgestellt ist, wird Folgendes hinzugefügt:

- [Verwalten von Vorfällen](incidents-overview.md)
- Ein Info-Center für die Verwaltung [automatisierter Untersuchungen und Reaktionen](mtp-autoir.md)
- [Erweiterte Funktionen für die Suche](advanced-hunting-overview.md)

![Abbildung des Navigationsbereichs im Microsoft 365 Security Center mit Microsoft 365 Defender features Microsoft 365 Security Center mit Vorfallverwaltung und anderen ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365 Defender-Funktionen*

### <a name="getting-microsoft-defender-for-identity-data"></a>Abrufen von Microsoft Defender for Identity-Daten

Um Microsoft Defender for Identity-Daten mit Microsoft 365 Defender zu teilen, stellen Sie sicher, dass die Integration von Microsoft Cloud App Security und Microsoft Defender for Identity aktiviert ist. [Erfahren Sie mehr über diese Integration.](https://docs.microsoft.com/cloud-app-security/mdi-integration)

## <a name="get-assistance"></a>Unterstützung erhalten

Antworten auf die am häufigsten gestellten Fragen zum Aktivieren von Microsoft 365 Defender finden Sie [in den häufig gestellten Fragen.](mtp-enable-faq.md)

Supportmitarbeiter von Microsoft können ihnen bei der Bereitstellung oder Debereitstellung des Diensts und der zugehörigen Ressourcen auf Ihrem Mandanten helfen. Wenn Sie Hilfe benötigen, wählen Sie **im** Microsoft 365 Security Center Hilfe aus. Wenn Sie den Support kontaktieren, erwähnen Sie Microsoft 365 Defender.

## <a name="related-topics"></a>Verwandte Themen

- [Häufig gestellte Fragen](mtp-enable-faq.md)
- [Lizenzierungsanforderungen und andere Voraussetzungen](prerequisites.md)
- [Bereitstellen unterstützter Dienste](deploy-supported-services.md)
- [Übersicht über Microsoft 365 Defender](microsoft-threat-protection.md)
- [Übersicht über Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Übersicht über Defender für Office 365](../office-365-security/office-365-atp.md)
- [Übersicht über Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Übersicht über Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender für Endpunktdatenspeicherung](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
