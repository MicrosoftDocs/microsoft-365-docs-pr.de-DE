---
title: Details zum Azure Active Directory-Mandanten
description: In diesem Thema werden Änderungen beschrieben, die beim Registrieren von Microsoft Managed Desktop an Ihrem Aad-Konto vorgenommen wurden.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: 6b2b30d8dedba1086bfa9268fb0fdbce20367c20
ms.sourcegitcommit: dd426c686b52cf79325f11022b2d99bc45285577
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2019
ms.locfileid: "35643946"
---
# <a name="azure-active-directory-tenant-details"></a>Details zum Azure Active Directory-Mandanten
{blutige Details zu Konten, API-aufrufen, perms usw., etc.}


## <a name="data-transmitted-to-and-from-your-aad-account"></a>An das und von Ihrem Aad-Konto übermittelte Daten


Daten, die von Microsoft an Ihr Konto gesendet wurden:

- Gruppennamen
- Konfiguration der Sicherheitsrichtlinie
- Geräte Bestellungen
- Benutzerkonten (msadmin, MSTest, mwaas_soc_ro, mwaas_wdgsoc)
- E5-Lizenzzuweisung zu den Benutzerkonten
- Windows Update-Richtlinien für Update Ringe

Von Ihrem Konto an Microsoft gesendete Daten:

- Geräteupdate-, Nutzungs-und Zuverlässigkeitsdaten
- App-Bereitstellungs-und Zuverlässigkeitsdaten
- Update-und Sicherheitsrichtlinien Bereitstellungsdaten
- Benutzern zugewiesenen Geräten  

Daten, die von Ihrem Konto übermittelt werden, werden in Azure SQL-Datenbanken im Microsoft-Mandanten gespeichert, der in den USA gehostet wird. Die Daten werden gemäß den unter {Microsoft Azure Security} beschriebenen Richtlinien gespeichert und verarbeitet. 

## <a name="api-permissions-and-calls"></a>API-Berechtigungen und-Aufrufe

**Während der Registrierung:**

API-Berechtigungen:
- DeviceManagementServiceConfig.ReadWrite.All
- Directory.AccessAsUser.All
- User.ReadWrite.All
- DeviceManagementConfiguration.ReadWrite.All
- DeviceManagementManagedDevices.ReadWrite.All
- Group.ReadWrite.All

API-Aufrufe:
- Post/Organization/{organizationId}/setMobileDeviceManagementAuthority
- Get/Post-/directoryRoles/{ID}/Members
- Get/Post-/users
- Get/Post-/Groups
- Patch-/Groups/{ID}
- Get/Post-/deviceManagement/deviceConfigurations
- /DeviceManagement/detectedApps abrufen

**Nach der Registrierung während der ordentlichen Verwaltung:**

API-Berechtigungen:
- DeviceManagementManagedDevices.ReadWrite.All
- DeviceManagementApps.ReadWrite.All
- DeviceManagementConfiguration.ReadWrite.All
- Reports.Read.All
- User.ReadWrite.All
- Group.ReadWrite.All
- Directory.AccessAsUser.All

API-Aufrufe:
- Get/Post-/directoryRoles/{ID}/Members
- Get/Patch/Post/users
- Get/Post-/Groups
- Patch-/Groups/{ID}
- Get/Post-/deviceManagement/deviceConfigurations
- Get/Post-/deviceAppManagement/mobileApps
- /DeviceManagement/detectedApps abrufen
- /Devices abrufen
- Post/users/{ID | userPrincipalName}/assignLicense
- /SubscribedSkus abrufen

## <a name="accounts-used-by-microsoft-managed-desktop"></a>Von Microsoft Managed Desktop verwendete Konten





| Konto | Beschreibung  | Bedingter Zugriff  | Mehrstufige Authentifizierung  | Gründe für die ordnungsgemäße |
|---------|---------|---------|---------|--------------|
| msadmin @ * onmmicrosoft. com | Das beschränkte Dienstkonto mit Administratorrechten, das als Microsoft InTune und Benutzer Administrator verwendet wird {What es this?} So definieren und konfigurieren Sie den Mandanten für moderne Desktop Geräte von Microsoft.Verfügt nicht über interaktive Anmeldeberechtigungen; führt Vorgänge nur über den Dienst aus.  | Ausgeschlossen, da Sie nicht in Ihrem Netzwerk stammt        | Ausgeschlossen, da keine interaktive Anmeldung vorhanden ist        | Im Azure Key Vault gespeichertes Kennwort |
| MSTest @ * onmmicrosoft. com     |         |         |         |
| mssupport @ * onmmicrosoft. com     |         |         |         |
| msadminint @ * onmmicrosoft. com     |         |         |         |
