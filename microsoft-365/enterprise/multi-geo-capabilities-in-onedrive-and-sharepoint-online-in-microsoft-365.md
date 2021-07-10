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
ms.openlocfilehash: 405f876317a6cec6defdf3f1a49b0dc32ac0add2
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362282"
---
# <a name="multi-geo-capabilities-in-onedrive-and-sharepoint-online"></a>Multi-Geo-Funktionen in OneDrive und SharePoint Online

Multi-Geo-Funktionen in OneDrive und SharePoint Online ermöglichen die Kontrolle über freigegebene Ressourcen wie SharePoint Teamwebsites und Microsoft 365 Gruppenpostfächer, die an einem angegebenen geografischen Standort gespeichert sind.

Benutzer, Gruppenpostfächer und SharePoint-Sites haben Preferred Data Locations (PDLs), die den geografischen Ort für die verknüpften Daten angeben. Die personenbezogenen Daten von Benutzern (Exchange-Posteingang und OneDrive) können zusammen mit beliebigen Microsoft 365-Gruppen oder SharePoint-Sites, die sie erstellen, am angegebenen geografischen Ort gespeichert werden, um Datenaufbewahrungsanforderungen zu erfüllen. Sie können [verschiedene Administratoren für jeden geografischen Ort angeben](add-a-sharepoint-geo-admin.md).

Benutzer erhalten die vertraute Oberfläche bei Verwendung von Microsoft 365-Diensten, einschließlich Office-Anwendungen, OneDrive und Suche. Details finden Sie unter [Benutzererfahrung in einer Multi-Geo-Umgebung](multi-geo-user-experience.md).

## <a name="onedrive"></a>OneDrive

Das OneDrive jedes Benutzers kann in Einklang mit der PDL an einem Satellitenort bereitgestellt oder [von einem Administrator dorthin verschoben werden](move-onedrive-between-geo-locations.md). Persönliche Dateien verbleiben an diesem geografischen Ort, obwohl sie mit Benutzern an anderen geografischen Orten geteilt werden können.

## <a name="sharepoint-sites-and-groups"></a>SharePoint-Websites und -Gruppen

Die Verwaltung des Features "Multi-Geo" steht über das SharePoint Admin Center zur Verfügung. Ausführliche Informationen finden Sie im [entsprechenden Blogbeitrag](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302).

Wenn ein Benutzer eine mit einer SharePoint-Gruppe verbundene Site in einer Multi-Geo-Umgebung erstellt, wird ihre PDL verwendet, um den geografischen Ort zu bestimmen, an dem die Site und ihr zugehöriges Gruppenpostfach erstellt werden. (Wenn der PDL-Wert des Benutzers nicht festgelegt oder auf den geografischen Ort festgelegt wurde, der nicht als Satellitenort konfiguriert wurde, werden Site und Postfach am zentralen Ort erstellt.)

Microsoft 365 anderen Dienste als Exchange, OneDrive, SharePoint und Teams sind keine Multi-Geo-Dienste. Microsoft 365 Gruppen, die von diesen Diensten erstellt werden, werden jedoch mit dem PDL des Erstellers und dem Exchange Gruppenpostfach konfiguriert, SharePoint Website im entsprechenden geografischen Raum bereitgestellt wird. 

## <a name="managing-the-multi-geo-environment"></a>Verwalten der Multi-Geo-Umgebung

Das Einrichten und Verwalten Ihrer Multi-Geo-Umgebung erfolgt über das SharePoint-Admin Center. 

![Screenshot der Seite mit geografischen Orten im SharePoint-Admin Center](../media/sharepoint-multi-geo-admin-center.png)

(Für einige Aktionen wie das Verschieben einer SharePoint- oder OneDrive-Site ist Microsoft PowerShell erforderlich.)

## <a name="see-also"></a>Siehe auch

[Multi-Geo in SharePoint- und Microsoft 365-Gruppen](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)

[Verwalten einer Multi-Geo-Umgebung](administering-a-multi-geo-environment.md)

[SharePoint-Speicherkontingente in Multi-Geo-Umgebungen](sharepoint-multi-geo-storage-quota.md)

[Verwalten von Exchange Online-Postfächern in einer Multi-Geo-Umgebung](administering-exchange-online-multi-geo.md)
