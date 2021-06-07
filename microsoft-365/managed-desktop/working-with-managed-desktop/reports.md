---
title: Mit Berichten arbeiten
description: Die verschiedenen in Microsoft Managed Desktop verfügbaren Berichte
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: b37ce09a0781aa83970502224ddbb3658ed07d69
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771885"
---
# <a name="work-with-reports"></a>Mit Berichten arbeiten

Microsoft Managed Desktop bietet mehrere Berichte und Dashboards, die IT-Administratoren in Ihrer Organisation verwenden können, um verschiedene Aspekte der Geräteanzahl zu verstehen. 

## <a name="reports-in-microsoft-endpoint-manager"></a>Berichte in Microsoft Endpoint Manager

Die Microsoft Endpoint Manager-Konsole vereint Berichte aus mehreren Produkten an einem zentralen Ort, um Probleme mit der Konfiguration und den Geräten Ihrer Azure AD-Organisation ("Mandant") zu überwachen und zu untersuchen. Microsoft Managed Desktop verfügt über einen Abschnitt unter **"Berichte"** im Hauptmenü, in dem Sie Berichte finden können, die Microsoft Managed Desktop die Verwaltung der geräte, die Sie registriert haben, spezifisch sind.

Diese Berichte umfassen:
- **Verwaltete Geräte**  >  **Featureupdates:** In dieser Ansicht wird der Gesamtstatus von Featureupdates auf Ihren Microsoft Managed Desktop Geräten angezeigt.
- **Verwaltete Geräte**  >  **Office Updates:** In dieser Ansicht wird der Gesamtstatus von Office Updates auf Ihren Microsoft Managed Desktop Geräten angezeigt.

Darüber hinaus können Sie an mehreren Stellen in Microsoft Endpoint Manager Berichte aus anderen Produktgruppen filtern, um Speziell Ihre Geräte einzuschließen oder auszuschließen, die von Microsoft Managed Desktop verwaltet werden. Diese Berichte haben diese Filterfunktion integriert:

- [Alle Geräte](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [Gerätekompatibilität](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [Nicht konforme Geräte](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> Benutzerdefinierte Microsoft Managed Desktop Rollen gewährleisten den Zugriff nur auf die Microsoft Managed Desktop Berichte. Informationen zum Zugriff auf andere Teile von Microsoft Endpoint Manager, z. B. **alle Geräte,** finden Sie unter [Rollenbasierte Zugriffssteuerung mit Microsoft Intune](/mem/intune/fundamentals/role-based-access-control). 

## <a name="endpoint-analytics"></a>Endpunktanalysen
Microsoft Managed Desktop ist jetzt in [Endpunktanalysen](/mem/analytics/overview)integriert. Diese Berichte geben Ihnen Einblicke, um zu messen, wie Ihre Organisation funktioniert und wie die Qualität der Benutzererfahrung ihren Benutzern bereitgestellt wird. Die Endpunktanalyse befindet sich im Menü **"Berichte"** von [Microsoft Endpoint Manager](https://endpoint.microsoft.com/). Um eine Bewertung so zu pivotieren, dass nur Geräte einbezogen werden, die von Microsoft Managed Desktop zu einem beliebigen Bericht wechseln, wählen Sie **die** Filter-Dropdownliste und dann **Microsoft Managed Desktop Geräte** aus.

Wenn Endpunktanalysen während der Registrierung nicht automatisch für Ihre Azure AD-Organisation ("Mandant") konfiguriert wurden, können Sie dies selbst tun. Weitere Informationen finden Sie unter [Onboarding im Endpunktanalyseportal.](/mem/analytics/enroll-intune#bkmk_onboard) Sie können alle Ihre Geräte registrieren oder, wenn Sie nur Microsoft Managed Desktop Geräte einschließen möchten, die gerätegruppen für den **modernen Arbeitsplatz** für "Test", "First", "Fast" und "Allgemein" auswählen. Für diese Berichte sind möglicherweise unterschiedliche Berechtigungen erforderlich. Weitere Informationen finden Sie unter ["Berechtigungen",](/mem/analytics/overview#permissions) um sicherzustellen, dass Ihnen Rollen entsprechend zugewiesen sind.

> [!NOTE]
> Um den Datenschutz der Benutzer besser zu respektieren, müssen mehr als 10 Microsoft Managed Desktop Geräte bei Endpunktanalysen registriert sein, um diesen Filter verwenden zu können.

 ## <a name="inventory-data"></a>Bestandsdaten

Zusätzlich zu den anderen Berichten können Sie Informationen zu den von Microsoft Managed Desktop verwalteten Geräten exportieren. In the **Devices** view of the **Devices** area of Microsoft Endpoint Manager, use the **Export all** tab to download a detailed [inventory report](device-inventory-report.md).
