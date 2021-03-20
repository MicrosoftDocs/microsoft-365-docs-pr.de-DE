---
title: Hinzufügen oder Entfernen eines Geo-Administrators
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection: SPO_Content
localization_priority: Normal
f1.keywords:
- NOCSH
description: Müssen Separate Administratoren für jeden geografischen Standort konfiguriert werden? So fügen Sie eine Geo-Administrator in Microsoft 365 Multi-Geo hinzu oder entfernen ihn.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 32fe5e934e6a3d6f18c802c3c427974e67c1b454
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905608"
---
# <a name="add-or-remove-a-geo-administrator-in-microsoft-365-multi-geo"></a>Hinzufügen oder Entfernen eines Geo-Administrators in Microsoft 365 Multi-Geo.

Sie können für jeden geographischen Standort in Ihrem Mandanten einen eigenen Administrator festlegen. Dieser Administrator hat Zugriff auf SharePoint Online- und OneDrive-Einstellungen, die für seinen geographischen Standort gelten.

Einige Dienste – wie Terminologiespeicher – werden an einem zentralen Standort verwaltet und an Satellitenstandorten repliziert. Der Geo-Administrator des zentralen Standorts hat Zugriff auf diese, was für Administratoren von Satellitenstandorten nicht gilt.

Globale Administratoren und SharePoint-Onlineadministratoren haben weiterhin Zugriff auf Einstellungen am zentralen Standort und allen Satellitenstandorten.

## <a name="configuring-geo-administrators"></a>Konfigurieren von Geo-Administratoren

Für das Konfigurieren von Geo-Administratoren ist das SharePoint Online-PowerShell-Modul erforderlich.

Verwenden Sie [Connect-SPOService](/powershell/module/sharepoint-online/Connect-SPOService), um eine Verbindung zum Administrationscenter des geographischen Standorts herzustellen, an dem Sie den Geo-Administrator hinzufügen möchten (zum Beispiel Connect-SPOService https://ContosoEUR-admin.sharepoint.com.))

Führen Sie `Get-SPOGeoAdministrator` aus, um die vorhandenen Geo-Administratoren eines Standorts anzuzeigen.

### <a name="adding-a-user-as-a-geo-admin"></a>Einen Benutzer als Geo-Administrator hinzufügen

Führen Sie `Add-SPOGeoAdministrator -UserPrincipalName <UPN>` aus, um einen Benutzer als Geo-Administrator hinzuzufügen.

Führen Sie `Remove-SPOGeoAdministrator -UserPrincipalName <UPN>` aus, um einen Benutzer als Geo-Administrator zu entfernen

### <a name="adding-a-group-as-a-geo-admin"></a>Eine Gruppe als Geo-Administrator hinzufügen

Sie können eine Sicherheitsgruppe oder eine E-Mail-aktivierte Sicherheitsgruppe als Geo-Administrator hinzufügen. (Verteilergruppen und Microsoft 365-Gruppen werden nicht unterstützt.)

Führen Sie `Add-SPOGeoAdministrator -GroupAlias <alias>` aus, um eine Gruppe als Geo-Administrator hinzuzufügen.

Führen Sie `Remove-SPOGeoAdministrator -GroupAlias <alias>` aus, um eine Gruppe als Geo-Administrator zu entfernen.

Beachten Sie, dass nicht alle Sicherheitsgruppen einen Gruppenalias besitzen. Wenn Sie eine Sicherheitsgruppe hinzufügen möchten, die keinen Alias besitzt, führen Sie [Get-MsolGroup](/powershell/module/msonline/get-msolgroup) aus, um eine Liste der Gruppen anzurufen. Suchen Sie nach der ObjectID Ihrer Sicherheitsgruppe Sie dann Folgendes aus:

`Add-SPOGeoAdministrator -ObjectID <ObjectID>`

Führen Sie `Remove-SPOGeoAdministrator -ObjectID <ObjectID>` aus, um eine Gruppe anhand der ObjectID zu entfernen.

## <a name="related-topics"></a>Verwandte Themen

[Add-SPOGeoAdministrator](/powershell/module/sharepoint-online/add-spogeoadministrator)

[Get-SPOGeoAdministrator](/powershell/module/sharepoint-online/get-spogeoadministrator)

[Remove-SPOGeoAdministrator](/powershell/module/sharepoint-online/remove-spogeoadministrator)

[Legen Sie einen Alias ("MailNickName") für eine Sicherheitsgruppe fest](/powershell/module/azuread/set-azureadgroup)