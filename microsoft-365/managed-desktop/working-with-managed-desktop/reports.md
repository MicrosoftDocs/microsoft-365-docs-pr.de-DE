---
title: Mit Berichten arbeiten
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e509ae63225362613962cd0c366c51239f3d4493
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917682"
---
# <a name="work-with-reports"></a>Mit Berichten arbeiten

Microsoft Managed Desktop stellt mehrere Berichte und Dashboards zur Verfügung, die IT-Administratoren in Ihrer Organisation verwenden können, um verschiedene Aspekte der Gerätegesamtheit zu verstehen.Berichte finden Sie an zwei Speicherorten: im [Microsoft Endpoint Manager](https://endpoint.microsoft.com) und im Microsoft [365 Admin Center](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop). 

## <a name="reports-in-microsoft-endpoint-manager"></a>Berichte im Microsoft Endpoint Manager

Die Microsoft Endpoint Manager-Konsole führt Berichte aus mehreren Produkten an einem einzigen Speicherort zusammen, um Ihnen bei der Überwachung und Untersuchung von Problemen mit ihrer Azure AD-Organisation ("Mandant")-Konfiguration und -Geräten zu helfen. Microsoft Managed Desktop enthält einen Abschnitt unter **Berichte** im Hauptmenü, in dem Sie Berichte finden, die speziell auf die Verwaltung der von Ihnen registrierten Geräte von Microsoft Managed Desktop spezifisch sind.

Zu diesen Berichten gehören:
- **Verwaltete Geräte**  >  **Featureupdates:** Diese Ansicht zeigt den Gesamtstatus von Featureupdates auf Ihren Microsoft Managed Desktop-Geräten.
- **Verwaltete Geräte**  >  **Office-Updates:** Diese Ansicht zeigt den Gesamtstatus von Office-Updates auf Ihren Microsoft Managed Desktop-Geräten.

Darüber hinaus können Sie berichte aus anderen Produktgruppen filtern, um Ihre geräte, die von Microsoft Managed Desktop verwaltet werden, an mehreren Standorten im Microsoft Endpoint Manager zu filtern. Diese Berichte haben diese Filterfunktion integriert:

- [Alle Geräte](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [Gerätekompatibilität](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [Nicht kompatible Geräte](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> Benutzerdefinierte Microsoft Managed Desktop-Rollen garantieren nur den Zugriff auf die Microsoft Managed Desktop-Berichte. Informationen zum Zugriff auf andere Teile von Microsoft Endpoint Manager, z. B. **Alle** Geräte, finden Sie unter [Rollenbasierte Zugriffssteuerung mit Microsoft Intune](/mem/intune/fundamentals/role-based-access-control). 

## <a name="reports-in-microsoft-365-admin-center"></a>Berichte im Microsoft 365 Admin Center

Sie finden Microsoft Managed Desktop Insights-Berichte, indem Sie das [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)öffnen und dann zu Berichte navigieren und Microsoft Managed Desktop **auswählen.**  Sie können den direkten Link zu diesen Berichten auch über die **Registerkarte Microsoft Managed Desktop** auf der Microsoft Endpoint Manager-Homepage [folgen.](https://endpoint.microsoft.com) 

Zu diesen Berichten gehören: 

- [Einblicke in die](usage-insights.md) Verwendung: Diese Ansicht enthält Verwendungsmetriken für Ihre Microsoft Managed Desktop-Geräte.
- [Einblicke in die](reliability-insights.md) Zuverlässigkeit – Diese Ansicht enthält eine Integritätszusammenfassung Ihrer verwalteten Geräte.
- [Einblicke in den](battery-insights.md) Akku: In dieser Ansicht werden Informationen zum Energieverbrauch von Apps und zur projizierten Akkulaufzeit für Geräte in Ihrer Umgebung angezeigt.
- [Einblicke in Windows-Sicherheitsupdates](security-update-insights.md) – Diese Ansicht zeigt Informationen zum Status von Sicherheitsupdates für Ihre Microsoft Managed Desktop-Geräte.

 ## <a name="inventory-data"></a>Bestandsdaten

Zusätzlich zu den anderen Berichten können Sie Informationen zu den von Microsoft Managed Desktop verwalteten Geräten exportieren. Verwenden Sie **in der Geräteansicht** des **Bereichs Geräte** von Microsoft Endpoint Manager die Registerkarte **Alle** exportieren, um [einen detaillierten Inventarbericht herunterzuladen.](device-inventory-report.md)