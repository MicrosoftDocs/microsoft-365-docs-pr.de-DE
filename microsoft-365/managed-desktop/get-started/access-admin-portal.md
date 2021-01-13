---
title: Zugriff auf das Verwaltungsportal
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
description: Informationen zum Suchen und Verwenden des Verwaltungsportals, einschließlich der Steuerung des Zugriffs darauf.
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: 09427d163b8b5e47911b6df26e5acf0fcd1f3524
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841351"
---
# <a name="access-the-admin-portal"></a>Zugreifen auf das Verwaltungsportal

Ihr Gateway zum Microsoft Managed Desktop Service ist das Microsoft [Azure-Portal.](https://portal.azure.com) Weitere Informationen zur Allgemeinen Verwendung und Anpassung Ihrer Azure-Portal-Erfahrung finden Sie in der [Dokumentation zum Azure-Portal.](https://docs.microsoft.com/azure/azure-portal/) In der Vorschau jetzt verfügbar, finden Sie auch Microsoft Managed Desktop im [Microsoft Endpoint Manager](https://endpoint.microsoft.com/). Wenn Sie mit den Funktionen dieses Portals für die Geräteverwaltung nicht vertraut sind, lesen Sie die [Microsoft Endpoint Manager-Dokumentation.](https://docs.microsoft.com/mem/)

> [!NOTE]
> Sie greifen jedoch auf Microsoft Managed Desktop zu, in [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) oder im [Azure-Portal,](https://portal.azure.com)und die folgenden Browser werden unterstützt:
> - Microsoft Edge (neueste Version)
> - Microsoft Internet Explorer 11
> - Safari (neueste Version, nur Mac)
> - Chrome (neueste Version)
> - Firefox (neueste Version)

Ihr Administratorkonto benötigt bestimmte Berechtigungen, um auf die Verwaltungsfeatures von Microsoft Managed Desktop im Azure-Portal oder microsoft Endpoint Manager zugreifen zu können. Sie können den Administratorzugriff auf diese Features innerhalb Ihrer Organisation mithilfe der rollenbasierten Zugriffssteuerung (Role-based Access Control, RBAC) verwalten. Mehrere Azure Active Directory (Azure AD)-Administratorrollen und integrierte benutzerdefinierte Rollen stehen zur Verfügung, um eine genauere Kontrolle über verschiedene Features im Microsoft Managed Desktop Admin Portal zu ermöglichen. Weitere Informationen zu Azure Active Directory-Rollen finden Sie unter [Administratorrollenberechtigungen in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Im Gegensatz zu Azure AD-Administratorrollen, die für verschiedene Produkte und Dienste von Microsoft gelten, gelten benutzerdefinierte Rollen speziell für Microsoft Managed Desktop und garantieren nur den Zugriff auf die Administratorfeatures für diesen Dienst. Administratoren können Benutzern benutzerdefinierte Rollen einzeln oder in Kombination mit Azure AD-Administratorrollen zuweisen, um vorhandenen Administratorkonten Microsoft Managed Desktop-Berechtigungen hinzuzufügen.

Jede der folgenden Rollen kann zugewiesen werden, um unterschiedliche Zugriffsebenen zu ermöglichen:

|Azure AD-Rolle  |Microsoft Managed Desktop-Berechtigungen  |
|---------|---------|
|Globaler Administrator     | Administratoren mit dieser Rolle verfügen über Lese- und **Schreibberechtigungen** für alle Features im Microsoft Managed Desktop Admin-Portal.         |
|Globaler Leser     | Administratoren mit dieser Rolle verfügen über schreibgeschützte Berechtigungen für **alle Features** im Microsoft Managed Desktop Admin-Portal.         |
|Intune-Dienstadministrator     |  Administratoren mit dieser Rolle verfügen über Lese- und **Schreibberechtigungen** für Features, die sich nicht auf die Sicherheit im Microsoft Managed Desktop Admin Portal bezogen haben.       |
|Dienstsupportadministrator     | Administratoren mit dieser Rolle  verfügen über schreibgeschützte Berechtigungen  für Features, die sich nicht auf Die Sicherheit und Schreibberechtigungen zum Verwalten von Supportanfragen im Microsoft Managed Desktop Admin Portal bezogen haben.         |
|Sicherheitsadministrator | Administratoren mit dieser Rolle  verfügen über schreibgeschützte Berechtigungen für alle Features und Schreibberechtigungen für sicherheitsbezogene Features **in** Microsoft Managed Desktop im Verwaltungsportal. |
|Sicherheitsleseberechtigter |Administratoren mit dieser Rolle verfügen über schreibgeschützte Berechtigungen für **alle Features** im Microsoft Managed Desktop Admin-Portal.|

> [!IMPORTANT]
> Nur die Rolle "Globaler Administrator" verfügt über die erforderlichen Berechtigungen, um *Ihre* Organisation bei Microsoft Managed Desktop zu registrieren. Beachten Sie, dass Azure Active Directory-Rollen Benutzerkonten berechtigungen für eine Vielzahl von Microsoft-Diensten zuweisen. Nach Abschluss der Registrierung bei Microsoft Managed Desktop sollten  Sie die Rolle immer mit den geringsten Berechtigungen verwenden, die zum Ausführen anderer Aufgaben erforderlich sind.

 
|Benutzerdefinierte Rolle  |Microsoft Managed Desktop-Berechtigungen  |
|---------|---------|
|Microsoft Managed Desktop Service Administrator  | Wenn diese Rolle einem Benutzer zugewiesen  wird, erhält der Administrator Lese- und Schreibberechtigungen für Features, die nicht mit der Sicherheit im Microsoft Managed Desktop Admin Portal in Zusammenhang stehen.  |
|Microsoft Managed Desktop Service Reader | Wenn diese Rolle einem Benutzer zugewiesen  wird, erhält der Administrator schreibgeschützte Berechtigungen für Features, die sich nicht auf die Sicherheit im Microsoft Managed Desktop Admin Portal bezogen haben. |
|Microsoft Managed Desktop Security Manager |Wenn diese Rolle einem Benutzer zugewiesen  wird, erhält dieser Administrator Lese- und Schreibberechtigungen nur für sicherheitsbezogene Features im Microsoft Managed Desktop Admin-Portal.   |

> [!NOTE]
> Zu den Sicherheitsfeatures gehören die sicherheitsbezogene Kommunikation, die Verwaltung von Sicherheitskontakten, die Verwaltung sicherheitsbezogener Supportanfragen und der Zugriff auf sicherheitsbezogene Berichte. 

## <a name="assigning-roles-to-administrators"></a>Zuweisen von Rollen zu Administratoren

Wenn Sie Hilfe beim Zuweisen von Azure Active Directory-Rollen benötigen, lesen Sie [die Administratorrollenberechtigungen in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

Damit integrierte Rollen einfach verwaltet werden können, gibt es eine Sicherheitsgruppe für jede benutzerdefinierte Rolle (z. B. "Moderne Arbeitsplatzrollen – Sicherheits-Manager"). Führen Sie die folgenden Schritte aus, um Benutzer einer der Sicherheitsgruppen zuzuordnen:
1.  Wechseln Sie zum Microsoft Endpoint Manager-Portal.
2.  Wählen **Sie Gruppen** auf der linken Seite aus.
3.  Suchen Sie **nach modernen Arbeitsplatzrollen,** und wählen Sie dann die Gruppe aus, die der Rolle zugeordnet ist, die Sie zuweisen möchten. 
4.  Wählen **Sie auf** der linken Seite Mitglieder aus, und wählen Sie dann auf der Befehlsleiste **"Mitglieder** hinzufügen" aus.
5.  Geben Sie die E-Mail der Person ein, die hinzugefügt wird. Wenn es sich um einen Gast handelt, müssen Sie ihn einladen, bevor Sie die Gruppe zuweisen können.
6.  Wählen **Sie unten** "Auswählen" aus.

> [!NOTE]
> Das Schachteln von Sicherheitsgruppen für die Rollenzuweisung wird derzeit nicht unterstützt. 
