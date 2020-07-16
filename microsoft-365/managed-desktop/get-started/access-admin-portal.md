---
title: Zugreifen auf das Verwaltungsportal
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.prod: microsoft-365-enterprise
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b6310849f27200adbbcbcb1584903011fbdf6145
ms.sourcegitcommit: 9af890ef1b1c95bfc7cc52f7f4e395b62dc5263f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2020
ms.locfileid: "45146267"
---
# <a name="access-the-admin-portal"></a>Zugreifen auf das Verwaltungsportal

Ihr Gateway zum Microsoft Managed Desktop-Dienst ist das Microsoft [Azure-Portal](https://portal.azure.com). Weitere Informationen zum verwenden und Anpassen Ihrer Azure-Portal-Erfahrung im Allgemeinen finden Sie in der [Azure-Portal Dokumentation](https://docs.microsoft.com/azure/azure-portal/). 

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
