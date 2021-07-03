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
ms.openlocfilehash: 345ae56a1c328dad7b777468dd03bcab40f9b4e1
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286873"
---
# <a name="access-the-admin-portal"></a>Zugreifen auf das Verwaltungsportal

Ihr Gateway zum Microsoft Managed Desktop-Dienst ist [Microsoft Endpoint Manager.](https://endpoint.microsoft.com/) Wenn Sie mit den Funktionen dieses Portals für die Geräteverwaltung nicht vertraut sind, lesen Sie die [Microsoft Endpoint Manager Dokumentation.](/mem/)

> [!NOTE]
> In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) werden die folgenden Browser unterstützt:
> - Microsoft Edge (neueste Version)
> - Safari (neueste Version, nur Mac)
> - Chrome (neueste Version)
> - Firefox (neueste Version)

Ihr Administratorkonto benötigt bestimmte Berechtigungen, um auf die Microsoft Managed Desktop administrativen Features in Microsoft Endpoint Manager zugreifen zu können. Sie können den Administratorzugriff auf diese Features innerhalb Ihrer Organisation mithilfe der rollenbasierten Zugriffssteuerung verwalten. Mehrere Azure Active Directory (Azure AD)-Administratorrollen und integrierte Microsoft Managed Desktop Rollen stehen zur Verfügung, um die verschiedenen Features im Microsoft Managed Desktop Admin-Portal präziser zu steuern. Weitere Informationen zu Azure Active Directory Rollen finden Sie unter [Administratorrollenberechtigungen in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Im Gegensatz zu Azure AD-Administratorrollen, die für verschiedene Microsoft-Produkte und -Dienste gelten, sind die integrierten Rollen spezifisch für Microsoft Managed Desktop und gewährleisten nur den Zugriff auf die Administratorfeatures für diesen Dienst. Administratoren können benutzern integrierte Rollen einzeln oder in Kombination mit Azure AD-Administratorrollen zuweisen, um vorhandenen Administratorkonten Microsoft Managed Desktop Berechtigungen hinzuzufügen.

## <a name="azure-active-directory-roles-with-microsoft-managed-desktop-access"></a>Azure Active Directory von Rollen mit Microsoft Managed Desktop Zugriff

|Azure AD-Rolle  |Microsoft Managed Desktop Berechtigungen  |
|---------|---------|
|Globaler Administrator     | Administratoren mit dieser Rolle verfügen über **Lese- und Schreibberechtigungen für alle Features** im Microsoft Managed Desktop Verwaltungsportal.         |
|Globaler Leser     | Administratoren mit dieser Rolle verfügen **über schreibgeschützte Berechtigungen für alle Features** im Microsoft Managed Desktop Verwaltungsportal.         |
|Intune-Dienstadministrator     |  Administratoren mit dieser Rolle verfügen über **Lese- und Schreibberechtigungen für Features,** die sich nicht auf die Sicherheit im Microsoft Managed Desktop Verwaltungsportal beziehen.       |
|Dienstsupportadministrator     | Administratoren mit dieser Rolle verfügen **über schreibgeschützte Berechtigungen für Features,** die sich nicht auf Die Sicherheit beziehen, und **Schreibberechtigungen zum Verwalten von Supportanfragen** im Microsoft Managed Desktop Admin-Portal.         |
|Sicherheitsadministrator | Administratoren mit dieser Rolle verfügen **über schreibgeschützte Berechtigungen für alle Features** und **Schreibberechtigungen für sicherheitsbezogene Features** in Microsoft Managed Desktop im Verwaltungsportal. |
|Sicherheitsleseberechtigter |Administratoren mit dieser Rolle verfügen **über schreibgeschützte Berechtigungen für alle Features** im Microsoft Managed Desktop Verwaltungsportal.|

Wenn Sie Hilfe beim Zuweisen Azure Active Directory Rollen benötigen, lesen Sie [administratorrollenberechtigungen in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).

> [!IMPORTANT]
> Nur die Rolle "Globaler Administrator" verfügt über die erforderlichen Berechtigungen, um Ihre Organisation in Microsoft Managed Desktop *zu registrieren.* Beachten Sie, dass Azure Active Directory Rollen Benutzerkonten berechtigungen für eine Vielzahl von Microsoft-Dienste gewähren. Nach Abschluss der Registrierung mit Microsoft Managed Desktop sollten Sie immer die Rolle mit den *geringsten* Berechtigungen verwenden, die zum Ausführen Ihrer anderen Aufgaben erforderlich sind.

## <a name="built-in-roles-provided-by-microsoft-managed-desktop"></a>Integrierte Rollen, die von Microsoft Managed Desktop bereitgestellt werden


|Integrierte Rolle  |Microsoft Managed Desktop Berechtigungen  |
|---------|---------|
|Microsoft Managed Desktop Dienstadministrator  | Wenn sie einem Benutzer zugewiesen ist, gewährt diese Rolle dem Administrator **Lese- und Schreibberechtigungen für Features,** die sich nicht auf die Sicherheit im Microsoft Managed Desktop Admin-Portal beziehen.  |
|Microsoft Managed Desktop Dienstleseberechtigter | Wenn sie einem Benutzer zugewiesen ist, gewährt diese Rolle dem Administrator **schreibgeschützte Berechtigungen für Features,** die sich nicht auf die Sicherheit im Microsoft Managed Desktop Admin-Portal beziehen. |
|Microsoft Managed Desktop Sicherheits-Manager |Wenn sie einem Benutzer zugewiesen ist, gibt diese Rolle dem Administrator **nur Lese- und Schreibberechtigungen für sicherheitsbezogene Features** im Microsoft Managed Desktop Admin-Portal.   |

> [!NOTE]
> Zu den Sicherheitsfeatures gehören die sicherheitsbezogene Kommunikation, die Verwaltung von Sicherheitskontakten, die Verwaltung sicherheitsbezogener Supportanfragen und der Zugriff auf sicherheitsbezogene Berichte. 

### <a name="assigning-built-in-roles-to-user"></a>Zuweisen integrierter Rollen zu Benutzern

Für die einfache Verwaltung integrierter Rollen gibt es für jede benutzerdefinierte Rolle eine Sicherheitsgruppe mit dem Namen "Moderne Arbeitsplatzrollen – _Rollenname"_(z. B. "Moderne Arbeitsplatzrollen – Sicherheits-Manager"). Führen Sie die folgenden Schritte aus, um einer dieser Sicherheitsgruppen Benutzer zuzuweisen:
1. Wechseln Sie zum Microsoft Endpoint Manager Portal.
2. Wählen Sie auf der linken Seite **Gruppen** aus.
3. Suchen Sie nach **modernen Arbeitsplatzrollen,** und wählen Sie dann die Gruppe aus, die der Rolle zugeordnet ist, die Sie zuweisen möchten. 
4. Wählen Sie auf der linken Seite **Member** aus, und wählen Sie dann in der Befehlsleiste **"Mitglieder hinzufügen"** aus.
5. Geben Sie die E-Mail-Adresse der Person ein, die hinzugefügt wird. Wenn sie Gast sind, müssen Sie sie einladen, bevor Sie die Gruppe zuweisen können.
6. Wählen Sie unten **"Auswählen"** aus.

> [!NOTE]
> Das Schachteln von Sicherheitsgruppen für die Rollenzuweisung wird derzeit nicht unterstützt. 

### <a name="assigning-built-in-roles-to-groups"></a>Zuweisen integrierter Rollen zu Gruppen

Wenn Sie einer vorhandenen Gruppe eine oder mehrere der integrierten Rollen zuweisen müssen, führen Sie die folgenden Schritte aus:

1. Wechseln Sie zu [portal.azure.com](https://portal.azure.com/).
2. Suchen und öffnen **Sie Enterprise Anwendungen.**
3. Ändern Sie den **Anwendungstypfilter** in _Microsoft Applications,_ und wählen Sie dann **"Übernehmen"** aus.
4. Suchen Sie nach _modernen Workplace-Kunden-APIs,_ und wählen Sie diese aus.
5. Wählen Sie **Benutzer und Gruppen** im Bereich auf der linken Seite aus, und wählen Sie dann + **Benutzer/Gruppe hinzufügen** aus.
6. Suchen Sie aus **Benutzern und Gruppen** nach der gewünschten Gruppe.
7. Suchen Sie unter **"Rolle auswählen"** nach der entsprechenden Rolle, und wählen Sie sie aus.
8. Wählen Sie **"Zuweisen" aus.**
