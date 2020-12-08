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
ms.openlocfilehash: bfd8305d23e0e6d761c629ee3048c6204f702d37
ms.sourcegitcommit: 98146c67a1d99db5510fa130340d3b7be8d81b21
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/07/2020
ms.locfileid: "49585328"
---
# <a name="work-with-reports"></a>Mit Berichten arbeiten

Microsoft Managed Desktop bietet mehrere Berichte und Dashboards, die IT-Administratoren in Ihrer Organisation verwenden können, um verschiedene Aspekte der Geräte Auffüllung zu verstehen.Sie finden Berichte an zwei Standorten: in [Microsoft Endpoint Manager](https://endpoint.microsoft.com) und im [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop). 

## <a name="reports-in-microsoft-endpoint-manager"></a>Berichte in Microsoft Endpoint Manager

In der Microsoft Endpoint Manager-Konsole werden Berichte aus mehreren Produkten an einem zentralen Ort zusammengefasst, damit Sie Probleme mit der Konfiguration und den Geräten ihrer Azure AD Organisation ("Mandanten") überwachen und untersuchen können. Microsoft Managed Desktop verfügt über einen Abschnitt unter **Berichte** im Hauptmenü, in dem Sie Berichte finden, die spezifisch für die Verwaltung von Microsoft Managed Desktops der Geräte sind, die Sie registriert haben.

Darüber hinaus können Sie an mehreren Standorten in Microsoft Endpoint Manager Berichte aus anderen Produktgruppen filtern, um Ihre Geräte, die von Microsoft Managed Desktop verwaltet werden, explizit einzubeziehen oder auszuschließen. Diese Filterfunktionen wurden in diesen Berichten integriert:

- **Alle Geräte**
- **Gerätekompatibilität**
- **Nicht konforme Geräte**

> [!NOTE]
> Benutzerdefinierte Microsoft Managed Desktop-Rollen garantieren den Zugriff nur auf die Microsoft Managed Desktop-Berichte. Informationen zum Zugriff auf andere Teile von Microsoft Endpoint Manager, beispielsweise auf **alle Geräte**, finden Sie unter [rollenbasierte Zugriffssteuerung mit Microsoft InTune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control). 

## <a name="reports-in-microsoft-365-admin-center"></a>Berichte im Microsoft 365 Admin Center

Sie können Microsoft Managed Desktop Insights-Berichte finden, indem Sie das [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)öffnen und dann zu **Berichten** navigieren und **Microsoft Managed Desktop** auswählen. Sie können auch den direkten Link zu diesen Berichten auf der Registerkarte **Microsoft Managed Desktop** auf der Startseite von [Microsoft Endpoint Manager](https://endpoint.microsoft.com)folgen. 

Diese Berichte umfassen Folgendes: 

- [Einblicke](usage-insights.md) in die Nutzung-diese Ansicht stellt Verwendungs Metriken für Ihre von Microsoft verwalteten Desktop Geräte bereit.
- [Zuverlässigkeits Einblicke](reliability-insights.md) – in dieser Ansicht erhalten Sie eine Integritäts Übersicht über Ihre verwalteten Geräte.
- [Battery Insights](battery-insights.md) -diese Ansicht zeigt Ihnen Informationen über den Energieverbrauch von apps und die voraussichtliche Lebensdauer der Batterie für Geräte in Ihrer Umgebung.
- [Windows Security Update Insights](security-update-insights.md) -diese Ansicht enthält Informationen zum Status von Sicherheitsupdates für Ihre von Microsoft verwalteten Desktop Geräte.

 ## <a name="inventory-data"></a>Inventurdaten

Zusätzlich zu den anderen Berichten können Sie Informationen zu den von Microsoft Managed Desktop verwalteten Geräten exportieren. Verwenden Sie in der Ansicht **Geräte** des Bereichs **Geräte** von Microsoft Endpoint Manager die Registerkarte **Alle exportieren** , um [einen detaillierten Inventurbericht herunterzuladen](device-inventory-report.md).