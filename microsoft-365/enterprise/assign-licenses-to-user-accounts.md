---
title: Zuweisen von Microsoft 365-Lizenzen zu Benutzerkonten
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/03/2019
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Beschreibt, wie Sie Benutzerkonten Microsoft 365-Lizenzen einzeln oder basierend auf einer Gruppenmitgliedschaft zuweisen.
ms.openlocfilehash: 60936e52bffa58d50419f771e670848ee76271fd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690331"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a>Zuweisen von Microsoft 365-Lizenzen zu Benutzerkonten

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Für das nur-Cloud-Identitätsmodell können Sie Microsoft 365-Lizenzen den Benutzerkonten zuweisen, je nachdem, wie Sie erstellt wurden.

Wenn Active Directory-Domänendienste (AD DS) Benutzerkonten zum ersten Mal synchronisiert werden, wird für das hybride Identitätsmodell nicht automatisch eine Microsoft 365-Lizenz zugewiesen. Sie müssen zunächst jedes Benutzerkonto mit einem Benutzer Speicherort konfigurieren.

In beiden Fällen müssen Sie Benutzerkonten eine Lizenz zuweisen, damit Ihre Benutzer auf Microsoft 365-Dienste wie e-Mail und Microsoft Teams zugreifen können.

Sie können Benutzerkonten entweder einzeln oder automatisch über die Gruppenmitgliedschaft Lizenzen zuweisen.

Wenn Sie Microsoft 365-Lizenzen einzelnen Benutzerkonten zuweisen möchten, können Sie Folgendes verwenden:

- [Das Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
- [PowerShell für Microsoft 365](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)

Informationen zur automatischen Zuweisung von Lizenzen finden Sie unter [Group-based licensing in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).

## <a name="next-steps"></a>Nächste Schritte

Mit dem vollständigen Benutzer kontensatz, dem Lizenzen zugewiesen wurden, können Sie nun folgende Aufgaben durchsetzen:

- [Implementieren der Sicherheit](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)
- [Bereitstellen von Client Software wie Microsoft 365-apps](https://docs.microsoft.com/DeployOffice/deployment-guide-microsoft-365-apps)
- [Einrichten der Verwaltung mobiler Geräte in Microsoft 365](https://support.office.com/article/set-up-mobile-device-management-mdm-in-office-365-dd892318-bc44-4eb1-af00-9db5430be3cd)
- [Konfigurieren von Diensten und Anwendungen](configure-services-and-applications.md)
