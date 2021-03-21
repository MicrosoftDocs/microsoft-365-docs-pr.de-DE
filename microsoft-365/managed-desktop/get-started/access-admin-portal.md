---
title: Zugriff auf das Verwaltungsportal
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
description: Informationen zum Suchen und Verwenden des Admin-Portals, einschließlich der Steuerung des Zugriffs darauf.
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: 7293c8ced43332f84ced56908ea5203ba867e600
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925904"
---
# <a name="access-the-admin-portal"></a>Zugreifen auf das Administratorportal

Ihr Gateway zum Microsoft Managed Desktop-Dienst ist [Microsoft Endpoint Manager](https://endpoint.microsoft.com/). Wenn Sie mit den Funktionen dieses Portals für die Geräteverwaltung nicht vertraut sind, lesen Sie die [Microsoft Endpoint Manager-Dokumentation](/mem/).

> [!NOTE]
> In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) werden die folgenden Browser unterstützt:
> - Microsoft Edge (neueste Version)
> - Microsoft Internet Explorer 11
> - Safari (neueste Version, nur Mac)
> - Chrome (neueste Version)
> - Firefox (neueste Version)

Ihr Administratorkonto benötigt bestimmte Berechtigungen, um auf die Verwaltungsfeatures von Microsoft Managed Desktop in Microsoft Endpoint Manager zu zugreifen. Sie können den Administratorzugriff auf diese Features in Ihrer Organisation mithilfe der rollenbasierten Zugriffssteuerung verwalten. Mehrere Azure Active Directory (Azure AD)-Administratorrollen und integrierte Microsoft Managed Desktop-Rollen stehen zur Verfügung, um eine differenziertere Steuerung der verschiedenen Features im Microsoft Managed Desktop Admin-Portal zu ermöglichen. Weitere Informationen zu Azure Active Directory-Rollen finden Sie unter [Administratorrollenberechtigungen in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Im Gegensatz zu Azure AD-Administratorrollen, die für verschiedene Microsoft-Produkte und -Dienste gelten, gelten die integrierten Rollen nur für Microsoft Managed Desktop und garantieren nur den Zugriff auf die Administratorfeatures für diesen Dienst. Administratoren können Benutzern integrierte Rollen einzeln oder in Kombination mit Azure AD-Administratorrollen zuweisen, um vorhandenen Administratorkonten Microsoft Managed Desktop-Berechtigungen hinzuzufügen.

## <a name="azure-active-directory-roles-with-microsoft-managed-desktop-access"></a>Azure Active Directory-Rollen mit Microsoft Managed Desktop-Zugriff

|Azure AD-Rolle  |Microsoft Managed Desktop-Berechtigungen  |
|---------|---------|
|Globaler Administrator     | Administratoren mit dieser Rolle verfügen über Lese- und **Schreibberechtigungen** für alle Features im Microsoft Managed Desktop Admin-Portal.         |
|Globaler Leser     | Administratoren mit dieser Rolle verfügen über schreibgeschützte Berechtigungen **für alle Features** im Microsoft Managed Desktop Admin-Portal.         |
|Intune-Dienstadministrator     |  Administratoren mit dieser Rolle verfügen über Lese- und **Schreibberechtigungen** für Features, die sich nicht auf die Sicherheit im Microsoft Managed Desktop Admin-Portal bezogen haben.       |
|Dienstunterstützungsadministrator     | Administratoren mit dieser Rolle verfügen **über** schreibgeschützte Berechtigungen  für Features, die keine Sicherheits- und Schreibberechtigungen zum Verwalten von Supportanforderungen im Microsoft Managed Desktop Admin-Portal haben.         |
|Sicherheitsadministrator | Administratoren mit dieser Rolle verfügen **über** schreibgeschützte Berechtigungen für alle Features und Schreibberechtigungen für sicherheitsrelevante Features **in** Microsoft Managed Desktop im Administratorportal. |
|Sicherheitsleseberechtigter |Administratoren mit dieser Rolle verfügen über schreibgeschützte Berechtigungen **für alle Features** im Microsoft Managed Desktop Admin-Portal.|

Wenn Sie Hilfe beim Zuweisen von Azure Active Directory-Rollen benötigen, lesen Sie [Administratorrollenberechtigungen in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).

> [!IMPORTANT]
> Nur die Rolle "Globaler Administrator" verfügt über die erforderlichen Berechtigungen, um *Ihre* Organisation bei Microsoft Managed Desktop zu registrieren. Beachten Sie, dass Azure Active Directory-Rollen Benutzerkonten über eine Vielzahl von Microsoft-Diensten hinweg Berechtigungen zuweisen. Nach abschluss der Registrierung bei Microsoft Managed Desktop sollten  Sie die Rolle immer mit den geringsten Rechten verwenden, die zum Ausführen Ihrer anderen Aufgaben erforderlich sind.

## <a name="built-in-roles-provided-by-microsoft-managed-desktop"></a>Integrierte Rollen, die von Microsoft Managed Desktop bereitgestellt werden


|Integrierte Rolle  |Microsoft Managed Desktop-Berechtigungen  |
|---------|---------|
|Microsoft Managed Desktop Service Administrator  | Wenn diese Rolle einem Benutzer zugewiesen  wird, erhält der Administrator Lese- und Schreibberechtigungen für Features, die sich nicht auf die Sicherheit im Microsoft Managed Desktop Admin-Portal bezogen haben.  |
|Microsoft Managed Desktop Service Reader | Wenn diese Rolle einem Benutzer zugewiesen  wird, erhält der Administrator schreibgeschützte Berechtigungen für Features, die sich nicht auf die Sicherheit im Microsoft Managed Desktop Admin-Portal bezogen haben. |
|Microsoft Managed Desktop Security Manager |Wenn diese Rolle einem Benutzer zugewiesen  wird, erhält dieser Administrator Lese- und Schreibberechtigungen nur für sicherheitsrelevante Features im Microsoft Managed Desktop Admin-Portal.   |

> [!NOTE]
> Zu den Sicherheitsfeatures gehören die sicherheitsbezogene Kommunikation, die Verwaltung von Sicherheitskontakten, die Verwaltung sicherheitsbezogener Supportanfragen und der Zugriff auf sicherheitsbezogene Berichte. 

### <a name="assigning-built-in-roles-to-user"></a>Zuweisen von integrierten Rollen zum Benutzer

Zur einfachen Verwaltung integrierter Rollen gibt es für jede benutzerdefinierte Rolle eine Sicherheitsgruppe mit dem Namen "Moderne Arbeitsplatzrollen - _Rollenname"_(z. B. "Moderne Arbeitsplatzrollen – Security Manager"). Führen Sie die folgenden Schritte aus, um Benutzern eine dieser Sicherheitsgruppen zuzuordnen:
1.  Wechseln Sie zum Microsoft Endpoint Manager-Portal.
2.  Wählen **Sie auf** der linken Seite Gruppen aus.
3.  Suchen Sie **nach modernen Arbeitsplatzrollen,** und wählen Sie dann die Gruppe aus, die der Rolle zugeordnet ist, die Sie zuweisen möchten. 
4.  Wählen **Sie auf** der linken Seite Mitglieder aus, und wählen Sie dann auf der Befehlsleiste **+** Mitglieder hinzufügen aus.
5.  Geben Sie die E-Mail der person ein, die hinzugefügt wird. Wenn sie ein Gast sind, müssen Sie sie einladen, bevor Sie die Gruppe zuweisen können.
6.  Wählen **Sie unten** auswählen aus.

> [!NOTE]
> Das Schachteln von Sicherheitsgruppen für die Rollenzuweisung wird derzeit nicht unterstützt. 

### <a name="assigning-built-in-roles-to-groups"></a>Zuweisen von integrierten Rollen zu Gruppen

Wenn Sie einer vorhandenen Gruppe eine oder mehrere der integrierten Rollen zuweisen müssen, führen Sie die folgenden Schritte aus:
1. Wechseln Sie zu [portal.azure.com](https://portal.azure.com/).
2. Suchen und öffnen Sie **Enterprise-Anwendungen.**
3. Ändern Sie **den Anwendungstypfilter** in _Microsoft Applications,_ und wählen Sie dann **Anwenden aus.**
4. Suchen Sie nach _Kunden-APIs für modernen Arbeitsplatz, und wählen Sie sie aus._
5. Wählen **Sie im** Bereich auf der linken Seite Benutzer und Gruppen aus, und wählen Sie dann + **Benutzer/Gruppe hinzufügen aus.**
6. Suchen Sie in Benutzern und Gruppen nach **der gruppe, die Sie möchten.**
7. Suchen Sie unter **Rolle** auswählen nach der entsprechenden Rolle, und wählen Sie sie dann aus.
8. Wählen Sie **Zuweisen aus.**
