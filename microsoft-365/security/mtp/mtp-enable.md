---
title: Aktivieren von Microsoft Threat Protection im Microsoft 365 Security Center
description: Erfahren Sie, wie Sie Microsoft Threat Protection aktivieren und Ihre Reaktionen auf Sicherheitsvorfälle ergänzen können.
keywords: Erste Schritte, Aktivieren von MTP, Microsoft Threat Protection, M365, Sicherheit, Datenspeicherort, erforderliche Berechtigungen, Lizenz Berechtigung, Seite "Einstellungen"
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
ms.openlocfilehash: 0badae0d81b52b89c47f950b889109d4b9d35dda
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844597"
---
# <a name="turn-on-microsoft-threat-protection"></a>Aktivieren von Microsoft Threat Protection

**Gilt für:**
- Microsoft Threat Protection

[Microsoft Threat Protection](microsoft-threat-protection.md) vereinigt ihren Vorfall Antwortprozess durch die Integration wichtiger Funktionen in Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security und Azure ATP. Diese vereinheitlichte Lösung bietet zusätzliche leistungsfähige Funktionen, auf die Sie im Microsoft 365 Security Center zugreifen können.

Microsoft Threat Protection wird automatisch aktiviert, wenn berechtigte Kunden mit den erforderlichen Berechtigungen Microsoft 365 Security Center besuchen. Lesen Sie diesen Artikel, um die verschiedenen Voraussetzungen und den Schutz von Microsoft Threat Protection zu verstehen.

## <a name="check-license-eligibility-and-required-permissions"></a>Überprüfen der Lizenz Berechtigung und der erforderlichen Berechtigungen
Eine Lizenz für ein Microsoft 365-Sicherheitsprodukt berechtigt Sie im Allgemeinen zur Verwendung von Microsoft Threat Protection im Microsoft 365 Security Center ohne zusätzliche Lizenzierungskosten. Es wird empfohlen, eine Sicherheitslizenz für Microsoft 365 E5, E5, A5 oder A5 oder eine gültige Kombination von Lizenzen zu erhalten, die Zugriff auf alle unterstützten Dienste bereitstellt.

Ausführliche Lizenzierungsinformationen finden [Sie in den Lizenzierungsanforderungen](prerequisites.md#licensing-requirements).

### <a name="check-your-role"></a>Überprüfen der Rolle
Sie müssen ein **globaler Administrator** oder ein **Sicherheitsadministrator** in Azure Active Directory sein, um Microsoft Threat Protection zu aktivieren. [Anzeigen ihrer Rollen in Azure AD](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Unterstützte Dienste
Microsoft Threat Protection aggregiert Daten aus den verschiedenen unterstützten Diensten, die Sie bereits bereitgestellt haben. Die Daten werden zentral verarbeitet und gespeichert, um neue Erkenntnisse zu identifizieren und um zentralisierte Antwort Workflows zu ermöglichen. Dies geschieht ohne Beeinträchtigung vorhandener Bereitstellungen, Einstellungen oder Daten, die den integrierten Diensten zugeordnet sind.

Um den optimalen Schutz zu erzielen und Microsoft Threat Protection zu optimieren, wird empfohlen, alle anwendbaren unterstützten Dienste in Ihrem Netzwerk bereitzustellen. Weitere Informationen finden [Sie unter Deploying supported Services](deploy-supported-services.md).

## <a name="before-starting-the-service"></a>Vor dem Starten des Diensts
Bevor Sie den Dienst aktivieren, wird im Microsoft 365-Sicherheitscenter ([Security.Microsoft.com](https://security.microsoft.com)) die Seite Microsoft Threat Protection-Einstellungen angezeigt, wenn Sie im Navigationsbereich **Vorfälle**, das **Aktionscenter**oder die **Suche** auswählen. Diese Navigationselemente werden nicht angezeigt, wenn Sie nicht berechtigt sind, Microsoft Threat Protection zu verwenden.

![Abbildung der Seite Microsoft Threat Protection-Einstellungen, die angezeigt wird, wenn Microsoft Threat Protection nicht auf ](../../media/mtp-enable/mtp-settings.png)
 *Microsoft Threat Protection-Einstellungen im Microsoft 365 Security Center* aktiviert wurde

## <a name="starting-the-service"></a>Starten des Diensts
Wählen Sie zum Aktivieren von Microsoft Threat Protection einfach **Microsoft Threat Protection aktivieren** aus, und wenden Sie die Änderung an. Sie können auf diese Option auch zugreifen, indem Sie im Navigationsbereich **Einstellungen** ([Security.Microsoft.com/Settings](https://security.microsoft.com/settings)) auswählen und dann **Microsoft Threat Protection**auswählen.

>[!NOTE]
>Wenn im Navigationsbereich keine **Einstellungen** angezeigt werden oder Sie nicht auf die Seite zugreifen können, überprüfen Sie Ihre Berechtigungen und Lizenzen.

### <a name="data-center-location"></a>Rechenzentrumsstandort
Microsoft Threat Protection speichert und verarbeitet Daten am [gleichen Speicherort, der von Microsoft Defender ATP verwendet](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)wird. Wenn Sie nicht über Microsoft Defender ATP verfügen, wird automatisch ein neuer rechenzentrumsstandort basierend auf dem Speicherort der aktiven Microsoft 365-Sicherheitsdienste ausgewählt. Der ausgewählte Speicherort des Rechenzentrums wird auf dem Bildschirm angezeigt.

>[!NOTE]
>Wählen Sie **need help?** im Microsoft 365 Security Center aus, um den Microsoft-Support zur Versorgung mit Microsoft Threat Protection an einem anderen rechenzentrumsstandort zu kontaktieren. 

### <a name="confirm-that-the-service-is-on"></a>Vergewissern Sie sich, dass der Dienst aktiviert ist
Sobald der Dienst bereitgestellt ist, wird Folgendes hinzugefügt:

- [Verwalten von Vorfällen](incidents-overview.md)
- Ein Info-Center für die Verwaltung [automatisierter Untersuchungen und Reaktionen](mtp-autoir.md)
- [Erweiterte Jagd](advanced-hunting-overview.md) Funktionen

![Bild des Microsoft 365 Security Center-Navigationsbereichs mit Microsoft Threat Protection ](../../media/mtp-enable/mtp-on.png)
 *-Features Microsoft 365 Security Center mit Incidents Management und anderen Microsoft Threat Protection-* Funktionen

### <a name="getting-azure-atp-data"></a>Abrufen von Azure ATP-Daten
Stellen Sie sicher, dass Microsoft Cloud App Security und die Azure ATP-Integration aktiviert sind, um Azure ATP-Daten für Microsoft Threat Protection freizugeben. Erfahren Sie mehr über [diese Integration](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a>Deaktivieren von Microsoft Threat Protection
Wenn Sie Microsoft Threat Protection nicht länger verwenden möchten, wechseln Sie zu **Einstellungen** > **Microsoft Threat Protection** > **Aktivieren/Deaktivieren** im Microsoft 365 Security Center. Deaktivieren Sie **Microsoft Threat Protection aktivieren** , und wenden Sie die Änderungen an.

Die entsprechenden Features werden aus dem Microsoft 365 Security Center entfernt.

## <a name="get-assistance"></a>Unterstützung erhalten

Wenn Sie Antworten auf die am häufigsten gestellten Fragen zum Aktivieren von Microsoft Threat Protection erhalten möchten, [Lesen Sie die FAQ](mtp-enable-faq.md).

Microsoft-Supportmitarbeiter können Ihnen helfen, den Dienst und die zugehörigen Ressourcen auf Ihrem Mandanten bereitzustellen oder zu entbinden. Um Unterstützung zu erhalten, wählen Sie **need help?** im Microsoft 365 Security Center aus. Wenn Sie sich an den Support wenden, erwähnen Sie Microsoft Threat Protection.

## <a name="related-topics"></a>Verwandte Themen

- [Häufig gestellte Fragen](mtp-enable-faq.md)
- [Lizenzierungsanforderungen und andere Voraussetzungen](prerequisites.md)
- [Bereitstellen unterstützter Dienste](deploy-supported-services.md)
- [Übersicht über Microsoft Threat Protection](microsoft-threat-protection.md)
- [Übersicht über Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Übersicht über Office 365 ATP](../office-365-security/office-365-atp.md)
- [Übersicht über Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Übersicht über Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Übersicht über Microsoft Defender ATP und Datenspeicherung](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)