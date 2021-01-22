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
ms.openlocfilehash: a80616b58298ba544b9eab1d19ffb77f0e6825d4
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921350"
---
# <a name="work-with-reports"></a>Mit Berichten arbeiten

Microsoft Managed Desktop stellt mehrere Berichte und Dashboards zur Verfügung, die von DEN ADMINISTRATOREN in Ihrer Organisation verwendet werden können, um verschiedene Aspekte der Gerätegesamtheit zu verstehen.Berichte finden Sie an zwei Orten: im [Microsoft Endpoint Manager](https://endpoint.microsoft.com) und im Microsoft [365 Admin Center.](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop) 

## <a name="reports-in-microsoft-endpoint-manager"></a>Berichte in Microsoft Endpoint Manager

Die Microsoft Endpoint Manager-Konsole vereint Berichte aus mehreren Produkten an einem zentralen Ort, um Sie bei der Überwachung und Untersuchung von Problemen mit der Konfiguration Ihrer Azure AD-Organisation ("Mandant") und ihren Geräten zu unterstützen. Microsoft Managed Desktop verfügt  über einen Abschnitt unter Berichte im Hauptmenü, in dem Sie Berichte finden können, die speziell auf die Verwaltung der von Microsoft Managed Desktop registrierten Geräte spezifisch sind.

Zu diesen Berichten gehören:
- **Verwaltete Geräte**  >  **Featureupdates:** Diese Ansicht zeigt den Gesamtstatus von Featureupdates auf Ihren Microsoft Managed Desktop-Geräten.
- **Verwaltete Geräte**  >  **Office-Updates:** Diese Ansicht zeigt den Gesamtstatus von Office-Updates auf Ihren Microsoft Managed Desktop-Geräten.

Darüber hinaus können Sie an mehreren Standorten im gesamten Microsoft Endpoint Manager Berichte aus anderen Produktgruppen filtern, um Ihre Geräte, die von Microsoft Managed Desktop verwaltet werden, speziell ein- oder auszuschließen. Diese Filterfunktion wurde in diese Berichte integriert:

- [Alle Geräte](https://docs.microsoft.com/mem/intune/remote-actions/device-management#get-to-your-devices)
- [Gerätekompatibilität](https://docs.microsoft.com/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [Nicht kompatible Geräte](https://docs.microsoft.com/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> Benutzerdefinierte Microsoft Managed Desktop-Rollen garantieren nur den Zugriff auf die Microsoft Managed Desktop-Berichte. Informationen zum Zugriff auf andere Teile von Microsoft Endpoint Manager, z. B. alle **Geräte,** finden Sie unter rollenbasierte Zugriffssteuerung [mit Microsoft Intune.](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control) 

## <a name="reports-in-microsoft-365-admin-center"></a>Berichte im Microsoft 365 Admin Center

Sie finden Microsoft Managed Desktop Insights-Berichte, indem Sie das [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)öffnen und dann zu Berichten navigieren und Microsoft Managed Desktop **auswählen.**  Sie können dem direkten Link zu diesen Berichten auch auf der **Microsoft Managed Desktop-Registerkarte** auf der Startseite [von Microsoft Endpoint Manager folgen.](https://endpoint.microsoft.com) 

Zu diesen Berichten gehören: 

- [Einblicke in die](usage-insights.md) Nutzung: Diese Ansicht enthält Nutzungsmetriken für Ihre Microsoft Managed Desktop-Geräte.
- [Zuverlässigkeitseinblicke–](reliability-insights.md) Diese Ansicht bietet Ihnen eine Integritätszusammenfassung Ihrer verwalteten Geräte.
- [Akkueinblicke–](battery-insights.md) In dieser Ansicht werden Informationen zum Energieverbrauch von Apps und zur projizierten Akkulaufzeit für Geräte in Ihrer Umgebung angezeigt.
- [Einblicke in Windows-Sicherheitsupdates:](security-update-insights.md) In dieser Ansicht werden Informationen zum Status von Sicherheitsupdates für Ihre Microsoft Managed Desktop-Geräte angezeigt.

 ## <a name="inventory-data"></a>Bestandsdaten

Zusätzlich zu den anderen Berichten können Sie Informationen zu den von Microsoft Managed Desktop verwalteten Geräten exportieren. In the **Devices** view of the **Devices** area of Microsoft Endpoint Manager, use the **Export all** tab to download a detailed [inventory report](device-inventory-report.md).
