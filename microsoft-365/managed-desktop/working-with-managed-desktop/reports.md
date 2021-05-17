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

Microsoft Managed Desktop bietet mehrere Berichte und Dashboards, die IT-Administratoren in Ihrer Organisation verwenden können, um verschiedene Aspekte der Gerätegesamtheit zu verstehen.Berichte finden Sie an zwei Speicherorten: in [Microsoft Endpoint Manager](https://endpoint.microsoft.com) und im [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop). 

## <a name="reports-in-microsoft-endpoint-manager"></a>Berichte in Microsoft Endpoint Manager

Die Microsoft Endpoint Manager führt Berichte aus mehreren Produkten an einem einzigen Ort zusammen, um Probleme mit ihrer Azure AD-Organisation ("Mandant")-Konfiguration und -Geräten zu überwachen und zu untersuchen. Microsoft Managed desktop has a section under **Reports** in the main menu where you can find reports specific to Microsoft Managed Desktop's management of the devices you've registered.

Zu diesen Berichten gehören:
- **Verwaltete Geräte**  >  **Featureupdates:** Diese Ansicht zeigt den Gesamtstatus von Featureupdates auf Ihren Microsoft Managed Desktop an.
- **Verwaltete Geräte**  >  **Office Updates:** Diese Ansicht zeigt den Gesamtstatus der Office Updates auf Ihren Microsoft Managed Desktop an.

Darüber hinaus können Sie berichte Microsoft Endpoint Manager anderen Produktgruppen filtern, um Ihre Geräte, die von anderen Produktgruppen verwaltet werden, explizit ein- oder auszuschließen, Microsoft Managed Desktop. Diese Berichte haben diese Filterfunktion integriert:

- [Alle Geräte](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [Gerätekompatibilität](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [Nicht kompatible Geräte](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> Benutzerdefinierte Microsoft Managed Desktop garantieren nur zugriff auf die Microsoft Managed Desktop Berichte. Informationen zum Zugriff auf andere Microsoft Endpoint Manager, z. B. **Alle** Geräte, finden Sie unter [Rollenbasierte](/mem/intune/fundamentals/role-based-access-control)Zugriffssteuerung mit Microsoft Intune . 

## <a name="reports-in-microsoft-365-admin-center"></a>Berichte im Microsoft 365 Admin Center

Sie finden Microsoft Managed Desktop Einblickeberichte, indem Sie das [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)öffnen und  dann zu Berichte navigieren und **Microsoft Managed Desktop**. Sie können den direkten Link zu  diesen Berichten auch über die Registerkarte Microsoft Managed Desktop auf der Homepage [Microsoft Endpoint Manager.](https://endpoint.microsoft.com) 

Zu diesen Berichten gehören: 

- [Nutzungseinblicke](usage-insights.md) – Diese Ansicht bietet Verwendungsmetriken für Ihre Microsoft Managed Desktop Geräte.
- [Einblicke in die](reliability-insights.md) Zuverlässigkeit – Diese Ansicht enthält eine Integritätszusammenfassung Ihrer verwalteten Geräte.
- [Einblicke in den](battery-insights.md) Akku: In dieser Ansicht werden Informationen zum Energieverbrauch von Apps und zur projizierten Akkulaufzeit für Geräte in Ihrer Umgebung angezeigt.
- [Windows Einblicke in](security-update-insights.md) Sicherheitsupdates– Diese Ansicht zeigt Informationen zum Status von Sicherheitsupdates für Ihre Microsoft Managed Desktop Geräte.

 ## <a name="inventory-data"></a>Bestandsdaten

Zusätzlich zu den anderen Berichten können Sie Informationen zu den geräten exportieren, die von Microsoft Managed Desktop. Verwenden Sie **in** der Geräteansicht **des** Bereichs Geräte von Microsoft Endpoint Manager die Registerkarte **Alle** exportieren, um [einen detaillierten Inventarbericht herunterzuladen.](device-inventory-report.md)