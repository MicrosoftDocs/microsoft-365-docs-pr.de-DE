---
title: Mit Berichten arbeiten
description: Die verschiedenen Berichte, die in Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 28035a9f0a669c1daa7526d0b1fefac52a77c81a
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52729968"
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


 ## <a name="inventory-data"></a>Bestandsdaten

Zusätzlich zu den anderen Berichten können Sie Informationen zu den geräten exportieren, die von Microsoft Managed Desktop. Verwenden Sie **in** der Geräteansicht **des** Bereichs Geräte von Microsoft Endpoint Manager die Registerkarte **Alle** exportieren, um [einen detaillierten Inventarbericht herunterzuladen.](device-inventory-report.md)