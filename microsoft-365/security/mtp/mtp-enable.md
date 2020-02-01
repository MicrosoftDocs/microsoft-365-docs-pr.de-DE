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
ms.openlocfilehash: a85680e323c7a8fba6f2d74d5cc00c58c2013d23
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2020
ms.locfileid: "41662051"
---
# <a name="turn-on-microsoft-threat-protection"></a>Aktivieren von Microsoft Threat Protection

**Gilt für:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Microsoft Threat Protection vereinheitlicht Ihren Reaktionsprozess auf Sicherheitsvorfälle durch die Integration der wichtigsten Funktionen von Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security und Azure ATP. Diese vereinheitlichte Lösung bietet zusätzliche leistungsfähige Funktionen, auf die Sie im Microsoft 365 Security Center zugreifen können.

## <a name="check-license-eligibility-and-required-permissions"></a>Überprüfen der Lizenz Berechtigung und der erforderlichen Berechtigungen
Kunden mit Microsoft 365 E5, Microsoft 365 E5 Security oder einer äquivalenten Kombination von Lizenzen können Microsoft Threat Protection verwenden. Weitere Informationen finden Sie unter [Lizenzierungsanforderungen](prerequisites.md#licensing-requirements).

Sie müssen ein **globaler Administrator** oder ein **Sicherheitsadministrator** in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) sein, um Microsoft Threat Protection zu aktivieren.

## <a name="start-using-the-service"></a>Verwenden des Diensts – erste Schritte
Microsoft Threat Protection aggregiert Daten aus den verschiedenen integrierten Diensten. Die Daten werden zentral verarbeitet und gespeichert, um neue Erkenntnisse zu identifizieren und um zentralisierte Antwort Workflows zu ermöglichen.

Bevor Sie den Dienst aktivieren, zeigt das Microsoft 365 Security Center ([Security.Microsoft.com](https://security.microsoft.com)) keine **Vorfälle** und **Aktionscenter** Optionen im Navigationsbereich an.

![Bild des Microsoft 365 Security Center-Navigationsbereichs ohne Microsoft Threat Protection](../images/mtp-off.png)
-Features*Microsoft 365 Security Center mit Microsoft Threat Protection deaktiviert*

Um Microsoft Threat Protection zu aktivieren, wählen Sie im Navigationsbereich die Option **Einstellungen** aus. Wechseln Sie auf der **[Seite Einstellungen](https://security.microsoft.com/settings)** zu **Microsoft Threat Protection** > **Opt-in/Opt-out**.

>[!NOTE]
>Wenn im Navigationsbereich keine **Einstellungen** angezeigt werden oder Sie nicht auf die Seite zugreifen können, überprüfen Sie Ihre Berechtigungen und Lizenzen.

### <a name="select-data-center-location"></a>Auswählen des Datencenter Standorts
Wenn Microsoft Defender ATP für Ihre Organisation bereitgestellt wurde, werden die Daten im selben Rechenzentrumsspeicherort gespeichert und verarbeitet, den Sie für [Ihre Microsoft Defender ATP-Daten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy) ausgewählt haben. Wenn Sie nicht über Microsoft Defender ATP verfügen, werden Sie aufgefordert, einen neuen Rechenzentrumsspeicherort speziell für Microsoft Threat Protection zu wählen. 

Sie müssen die Zustimmung erteilen, bevor Daten zwischen Diensten freigegeben und aggregiert werden.

### <a name="confirm-that-the-service-is-on"></a>Vergewissern Sie sich, dass der Dienst aktiviert ist
Sobald der Dienst bereitgestellt ist, wird Folgendes hinzugefügt:

- [Verwalten von Vorfällen](incidents-overview.md)
- Ein Info-Center für die Verwaltung [automatisierter Untersuchungen und Reaktionen](mtp-autoir.md)
- [Erweiterte Suchfunktionen](advanced-hunting-overview.md) für die bestehende **Such**-Seite

![Bild des Microsoft 365 Security Center-Navigationsbereichs mit Microsoft Threat Protection](../images/mtp-on.png)
 *-Features Microsoft 365 Security Center mit Incidents Management und anderen Microsoft Threat Protection-* Funktionen

### <a name="getting-azure-atp-data"></a>Abrufen von Azure ATP-Daten
Stellen Sie sicher, dass Microsoft Cloud App Security und die Azure ATP-Integration aktiviert sind, um Azure ATP-Daten für Microsoft Threat Protection freizugeben. Erfahren Sie mehr über [diese Integration](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a>Deaktivieren von Microsoft Threat Protection
Wenn Sie Microsoft Threat Protection nicht länger verwenden möchten, wechseln Sie zu **Einstellungen** > **Microsoft Threat Protection** > **Aktivieren/Deaktivieren** im Microsoft 365 Security Center. Heben Sie die Auswahl **Microsoft Threat Protection aktivieren** auf, und speichern Sie die Änderung.

Daten werden endgültig gelöscht, und die entsprechenden Features werden aus dem Microsoft 365 Security Center entfernt.

## <a name="get-assistance"></a>Unterstützung erhalten

Microsoft-Supportmitarbeiter können Ihnen helfen, den Dienst und die zugehörigen Ressourcen auf Ihrem Mandanten bereitzustellen oder zu entbinden. Um Unterstützung zu erhalten, wählen Sie **need help?** im Microsoft 365 Security Center aus. Wenn Sie sich an den Support wenden, erwähnen Sie Microsoft Threat Protection.

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über Microsoft Threat Protection](microsoft-threat-protection.md)
- [Lizenzierungsanforderungen und andere Voraussetzungen](prerequisites.md)
- [Übersicht über Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Übersicht über Office 365 ATP](../office-365-security/office-365-atp.md)
- [Übersicht über Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Übersicht über Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Übersicht über Microsoft Defender ATP und Datenspeicherung](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
