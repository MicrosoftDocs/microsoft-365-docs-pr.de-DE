---
title: Zugriff auf das Verwaltungsportal
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.prod: microsoft-365-enterprise
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: 420cdaabb607eacf0d7a7109827fe5437e2f999c
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530223"
---
# <a name="access-the-admin-portal"></a>Zugreifen auf das Verwaltungsportal

Ihr Gateway zum Microsoft Managed Desktop-Dienst ist das Microsoft [Azure-Portal](https://portal.azure.com). Weitere Informationen zum verwenden und Anpassen Ihrer Azure-Portal-Erfahrung im Allgemeinen finden Sie in der [Azure-Portal Dokumentation](https://docs.microsoft.com/azure/azure-portal/). Verfügbar in Vorschau jetzt können Sie auch Microsoft Managed Desktop im [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)finden. Wenn Sie mit den Funktionen dieses Portals für die Geräteverwaltung nicht vertraut sind, lesen Sie die [Microsoft Endpoint Manager-Dokumentation](https://docs.microsoft.com/mem/).

Ihr Administratorkonto benötigt bestimmte Berechtigungen, um auf das Verwaltungsportal von Microsoft Managed Desktop zugreifen zu können. Sie können den Administratorzugriff auf diese Features in Ihrer Organisation mithilfe der rollenbasierten Zugriffssteuerung (Role-Based Access Control, RBAC) verwalten. Weitere Informationen zu Azure Active Directory Rollen finden Sie unter [Administrator Role Permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).

Weisen Sie Ihren Administrator-Benutzerkonten eine der folgenden Rollen zu, um den Zugriff sicherzustellen:

|Azure AD Rolle  |Berechtigungen für Microsoft Managed Desktops  |
|---------|---------|
|Globaler Administrator     | Administratoren mit dieser Rolle verfügen über **Lese-und Schreibberechtigungen** für alle Features im Verwaltungsportal von Microsoft Managed Desktop.         |
|Globaler Leser     | Administratoren mit dieser Rolle verfügen über **schreibgeschützte Berechtigungen** für alle Features im Verwaltungsportal von Microsoft Managed Desktop.         |
|InTune-Dienst Administrator     |  Administratoren mit dieser Rolle verfügen über **Lese-und Schreibberechtigungen** für alle Features im Verwaltungsportal von Microsoft Managed Desktop.       |
|Dienst Support Administrator     | Administratoren mit dieser Rolle verfügen über **Lese-und Schreibberechtigungen** für alle Features im Verwaltungsportal von Microsoft Managed Desktop.         |

> [!IMPORTANT]
> Nur die globale Administrator Rolle verfügt über die erforderlichen Berechtigungen zum *registrieren* Ihrer Organisation in Microsoft Managed Desktop. Achten Sie darauf, dass Azure Active Directory-Rollen Benutzerkontenberechtigungen für eine Vielzahl von Microsoft-Diensten erhalten. Nachdem Sie die Registrierung bei Microsoft Managed Desktop abgeschlossen haben, sollten Sie die Rolle immer mit den am *wenigsten* erforderlichen Rechten verwenden, um Ihre anderen Aufgaben auszuführen.

## <a name="assigning-roles-to-administrators"></a>Zuweisen von Rollen zu Administratoren

Wenn Sie Hilfe beim Zuweisen von Azure Active Directory Rollen benötigen, finden Sie weitere Informationen unter [Administrator Rollen Berechtigungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).
