---
title: Aktivieren von Microsoft Threat Protection im Microsoft 365 Security Center
description: Erfahren Sie, wie Sie Microsoft Threat Protection aktivieren und Ihre Reaktionen auf Sicherheitsvorfälle ergänzen können.
keywords: Erste Schritte, MTP, Microsoft Threat Protection, M365, Sicherheit, Datenspeicherorte
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
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
ms.openlocfilehash: 7790e079d4b39b5d41961a26bb17009adb1bec1d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808450"
---
# <a name="turn-on-microsoft-threat-protection"></a>Aktivieren von Microsoft Threat Protection

**Gilt für:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Microsoft Threat Protection vereinheitlicht Ihren Reaktionsprozess auf Sicherheitsvorfälle durch die Integration der wichtigsten Funktionen von Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security und Azure ATP. Diese vereinheitlichte Lösung bietet zusätzliche leistungsfähige Funktionen, auf die Sie im Microsoft 365 Security Center zugreifen können.

## <a name="check-your-eligibility"></a>Überprüfen Sie Ihre Berechtigung
Kunden, die über eine Microsoft 365 E5- oder eine entsprechende Lizenz verfügen, können Microsoft Threat Protection verwenden. Weitere Informationen finden Sie unter [Lizenzierungsanforderungen](prerequisites.md#licensing-requirements).

## <a name="start-using-the-service"></a>Verwenden des Diensts – erste Schritte
Durch die Aktivierung des Microsoft Threat Protection-Diensts werden Daten aus den verschiedenen integrierten Diensten zusammengeführt. Diese Daten werden zentral verarbeitet und gespeichert, um neue Erkenntnisse zu gewinnen und um zentralisierte Reaktionsabläufe zu ermöglichen.

Vor der Aktivierung des Dienstes werden im Microsoft 365 Security Center ([Security.Microsoft.com](https://security.microsoft.com)) die Optionen **Vorfälle** und **Info-Center** nicht im Menü angezeigt.

![Abbildung des Microsoft 365 Security Center-Menüs ohne Microsoft Threat Protection-Funktionen](../images/mtp-off.png)
*Microsoft 365 Security Center mit deaktiviertem Microsoft Threat Protection*

Wenn Sie den Microsoft Threat Protection-Dienst aktivieren möchten, wechseln Sie zu **Einstellungen** > **Microsoft Threat Protection** > **Aktivieren/Deaktivieren** im Microsoft 365 Security Center. Sie müssen ein globaler Administrator oder ein Sicherheitsadministrator in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) sein, um diese Aktion ausführen zu können.

Wenn Microsoft Defender ATP für Ihre Organisation bereitgestellt wurde, werden die Daten im selben Rechenzentrumsspeicherort gespeichert und verarbeitet, den Sie für [Ihre Microsoft Defender ATP-Daten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy) ausgewählt haben. Wenn Sie nicht über Microsoft Defender ATP verfügen, werden Sie aufgefordert, einen neuen Rechenzentrumsspeicherort speziell für Microsoft Threat Protection zu wählen. Sie müssen die entsprechende Zustimmung geben, bevor Daten zwischen den Diensten geteilt und zusammengeführt werden.

### <a name="confirm-that-the-service-is-on"></a>Vergewissern Sie sich, dass der Dienst aktiviert ist
Sobald der Dienst bereitgestellt ist, wird Folgendes hinzugefügt:

- [Verwalten von Vorfällen](incidents-overview.md)
- Ein Info-Center für die Verwaltung [automatisierter Untersuchungen und Reaktionen](mtp-autoir.md)
- [Erweiterte Suchfunktionen](advanced-hunting-overview.md) für die bestehende **Such**-Seite

![Abbildung des Microsoft 365 Security Center-Menüs mit Microsoft Threat Protection-Funktionen](../images/mtp-on.png)
*Microsoft 365 Security Center mit Funktionen für die Verwaltung von Vorfällen und anderen Microsoft Threat Protection-Funktionen*

### <a name="getting-azure-atp-data"></a>Abrufen von Azure ATP-Daten
Stellen Sie sicher, dass Microsoft Cloud App Security und die Azure ATP-Integration aktiviert sind, um Azure ATP-Daten für Microsoft Threat Protection freizugeben. Erfahren Sie mehr über [diese Integration](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a>Deaktivieren von Microsoft Threat Protection
Wenn Sie Microsoft Threat Protection nicht länger verwenden möchten, wechseln Sie zu **Einstellungen** > **Microsoft Threat Protection** > **Aktivieren/Deaktivieren** im Microsoft 365 Security Center. Heben Sie die Auswahl **Microsoft Threat Protection aktivieren** auf, und speichern Sie die Änderung.

Die Daten werden dauerhaft gelöscht, und die entsprechenden Funktionen werden aus dem Microsoft 365 Security Center entfernt.

## <a name="get-assistance"></a>Unterstützung erhalten

Microsoft-Mitarbeiter können Sie dabei unterstützen, den Dienst und die zugehörigen Ressourcen in Ihrem Mandanten bereitzustellen oder die Bereitstellung aufzuheben. Wenn Sie Hilfe benötigen, wenden Sie sich an den [Premier Support](https://go.microsoft.com/fwlink/?LinkID=733758).

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über Microsoft Threat Protection](microsoft-threat-protection.md)
- [Lizenzierungsanforderungen und andere Voraussetzungen](prerequisites.md)
- [Übersicht über Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Übersicht über Office 365 ATP](../office-365-security/office-365-atp.md)
- [Übersicht über Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Übersicht über Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Übersicht über Microsoft Defender ATP und Datenspeicherung](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
