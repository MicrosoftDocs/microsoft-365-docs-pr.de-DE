---
title: Multi-Geo-Funktionen in OneDrive und SharePoint Online
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
localization_priority: Normal
ms.assetid: 094e86f2-9ff0-40ac-af31-28fcaba00c1d
description: Erweitern Sie Ihre Microsoft 365-Präsenz auf mehrere geografische Regionen mit Multi-Geo-Funktionen in OneDrive Online.
ms.openlocfilehash: 8f42b071abef0602304f1a468190c33700fe3e82
ms.sourcegitcommit: 321610fd312e5c54ae8a757a71ab0c9fd2f1ac03
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "48995909"
---
# <a name="multi-geo-capabilities-in-onedrive-and-sharepoint-online"></a>Multi-Geo-Funktionen in OneDrive und SharePoint Online

Multi-Geo-Funktionen in OneDrive und SharePoint Online ermöglichen die Steuerung freigegebener Ressourcen wie SharePoint-Teamwebsites und Microsoft 365-Gruppen Postfächer, die im Rest in einem Land oder einer Region gespeichert sind.

Benutzer, Gruppenpostfächer und SharePoint-Sites haben Preferred Data Locations (PDLs), die den geografischen Ort für die verknüpften Daten angeben. Die personenbezogenen Daten von Benutzern (Exchange-Posteingang und OneDrive) können zusammen mit beliebigen Microsoft 365-Gruppen oder SharePoint-Sites, die sie erstellen, am angegebenen geografischen Ort gespeichert werden, um Datenaufbewahrungsanforderungen zu erfüllen. Sie können [verschiedene Administratoren für jeden geografischen Ort angeben](add-a-sharepoint-geo-admin.md).

Benutzer erhalten die vertraute Oberfläche bei Verwendung von Microsoft 365-Diensten, einschließlich Office-Anwendungen, OneDrive und Suche. Details finden Sie unter [Benutzererfahrung in einer Multi-Geo-Umgebung](multi-geo-user-experience.md).

## <a name="onedrive"></a>OneDrive

Das OneDrive jedes Benutzers kann in Einklang mit der PDL an einem Satellitenort bereitgestellt oder [von einem Administrator dorthin verschoben werden](move-onedrive-between-geo-locations.md). Persönliche Dateien verbleiben an diesem geografischen Ort, obwohl sie mit Benutzern an anderen geografischen Orten geteilt werden können.

## <a name="sharepoint-sites-and-groups"></a>SharePoint-Websites und -Gruppen

Die Verwaltung des Features "Multi-Geo" steht über das SharePoint Admin Center zur Verfügung. Ausführliche Informationen finden Sie im [entsprechenden Blogbeitrag](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302).

Wenn ein Benutzer eine mit einer SharePoint-Gruppe verbundene Site in einer Multi-Geo-Umgebung erstellt, wird ihre PDL verwendet, um den geografischen Ort zu bestimmen, an dem die Site und ihr zugehöriges Gruppenpostfach erstellt werden. (Wenn der PDL-Wert des Benutzers nicht festgelegt oder auf den geografischen Ort festgelegt wurde, der nicht als Satellitenort konfiguriert wurde, werden Site und Postfach am zentralen Ort erstellt.)

Andere Microsoft 365-Dienste als Exchange, OneDrive und SharePoint sind nicht Multi-Geo. Microsoft 365-Gruppen, die jedoch von diesen Diensten erstellt werden, erhalten die PDL des Erstellers. Exchange-Gruppenpostfach und SharePoint O365-Gruppenwebsite werden am entsprechenden geografischen Ort bereitgestellt. 

## <a name="managing-the-multi-geo-environment"></a>Verwalten der Multi-Geo-Umgebung

Das Einrichten und Verwalten Ihrer Multi-Geo-Umgebung erfolgt über das SharePoint-Admin Center. 

![Screenshot der Seite mit geografischen Orten im SharePoint-Admin Center](../media/sharepoint-multi-geo-admin-center.png)

(Für einige Aktionen wie das Verschieben einer SharePoint- oder OneDrive-Site ist Microsoft PowerShell erforderlich.)

## <a name="see-also"></a>Siehe auch

[Multi-Geo in SharePoint- und Microsoft 365-Gruppen](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)

[Verwalten einer Multi-Geo-Umgebung](administering-a-multi-geo-environment.md)

[SharePoint-Speicherkontingente in Multi-Geo-Umgebungen](sharepoint-multi-geo-storage-quota.md)

[Verwalten von Exchange Online-Postfächern in einer Multi-Geo-Umgebung](administering-exchange-online-multi-geo.md)
