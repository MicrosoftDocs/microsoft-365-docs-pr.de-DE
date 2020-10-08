---
title: Zugriff auf das Verwaltungsportal
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: 5adf57c2397c4de3c5ea8622a2a9be7207ebf152
ms.sourcegitcommit: 5e40c760c1af2a4cc6d85cb782b17f5c979677c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48379302"
---
# <a name="access-the-admin-portal"></a>Zugreifen auf das Verwaltungsportal

Ihr Gateway zum Microsoft Managed Desktop-Dienst ist das Microsoft [Azure-Portal](https://portal.azure.com). Weitere Informationen zum verwenden und Anpassen Ihrer Azure-Portal-Erfahrung im Allgemeinen finden Sie in der [Azure-Portal Dokumentation](https://docs.microsoft.com/azure/azure-portal/). Verfügbar in Vorschau jetzt können Sie auch Microsoft Managed Desktop im [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)finden. Wenn Sie mit den Funktionen dieses Portals für die Geräteverwaltung nicht vertraut sind, lesen Sie die [Microsoft Endpoint Manager-Dokumentation](https://docs.microsoft.com/mem/).

> [!NOTE]
> Wie auch immer Sie sich für den Zugriff auf Microsoft Managed Desktop entscheiden, in [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) oder im [Azure-Portal](https://portal.azure.com)werden die folgenden Browser unterstützt:
> - Microsoft Edge (neueste Version)
> - Microsoft Internet Explorer 11
> - Safari (neueste Version, nur Mac)
> - Chrome (neueste Version)
> - Firefox (neueste Version)

Ihr Administratorkonto benötigt spezifische Berechtigungen, um auf die administrativen Funktionen von Microsoft Managed Desktop im Azure-Portal oder Microsoft Endpoint Manager zugreifen zu können. Sie können den Administratorzugriff auf diese Features in Ihrer Organisation mithilfe der rollenbasierten Zugriffssteuerung (Role-Based Access Control, RBAC) verwalten. Mehrere Azure Active Directory (Azure AD)-Administratorrollen und integrierte benutzerdefinierte Rollen stehen zur Verfügung, um eine präzisere Steuerung verschiedener Features im Verwaltungsportal von Microsoft Managed Desktop bereitzustellen. Weitere Informationen zu Azure Active Directory Rollen finden Sie unter [Administrator Role Permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Im Gegensatz zu Azure AD Administratorrollen, die für eine Vielzahl von Microsoft-Produkten und-Diensten gelten, sind benutzerdefinierte rollenspezifisch für Microsoft Managed Desktop und garantieren nur den Zugriff auf die Administratorfunktionen für diesen Dienst. Administratoren können Benutzer benutzerdefinierte Rollen einzeln oder in Kombination mit Azure AD Administratorrollen zuweisen, um Microsoft Managed Desktop-Berechtigungen zu vorhandenen Administratorkonten hinzuzufügen.

Jede der folgenden Rollen kann zugewiesen werden, um unterschiedliche Zugriffsebenen bereitzustellen:

|Azure AD Rolle  |Berechtigungen für Microsoft Managed Desktops  |
|---------|---------|
|Globaler Administrator     | Administratoren mit dieser Rolle verfügen über **Lese-und Schreibberechtigungen für alle Features** im Verwaltungsportal von Microsoft Managed Desktop.         |
|Globaler Leser     | Administratoren mit dieser Rolle verfügen über **schreibgeschützte Berechtigungen für alle Features** im Verwaltungsportal von Microsoft Managed Desktop.         |
|InTune-Dienst Administrator     |  Administratoren mit dieser Rolle verfügen über **Lese-und Schreibberechtigungen für Features, die nicht im Zusammenhang** mit der Sicherheit im Verwaltungsportal von Microsoft Managed Desktop stehen.       |
|Dienst Support Administrator     | Administratoren mit dieser Rolle verfügen über **Lese-und Schreibberechtigungen für Features, die nicht im Zusammenhang** mit der Sicherheit im Verwaltungsportal von Microsoft Managed Desktop stehen.         |
|Sicherheitsadministrator | Administratoren mit dieser Rolle verfügen über **schreibgeschützte Berechtigungen für alle Features** und **Schreibberechtigungen für sicherheitsbezogene Features** in Microsoft Managed Desktop im Verwaltungsportal. |
|Sicherheitsleseberechtigter |Administratoren mit dieser Rolle verfügen über **schreibgeschützte Berechtigungen für alle Features** im Verwaltungsportal von Microsoft Managed Desktop.|

> [!IMPORTANT]
> Nur die globale Administrator Rolle verfügt über die erforderlichen Berechtigungen zum *registrieren* Ihrer Organisation in Microsoft Managed Desktop. Achten Sie darauf, dass Azure Active Directory-Rollen Benutzerkontenberechtigungen für eine Vielzahl von Microsoft-Diensten erhalten. Nachdem Sie die Registrierung bei Microsoft Managed Desktop abgeschlossen haben, sollten Sie die Rolle immer mit den am *wenigsten* erforderlichen Rechten verwenden, um Ihre anderen Aufgaben auszuführen.

 
|Benutzerdefinierte Rolle  |Berechtigungen für Microsoft Managed Desktops  |
|---------|---------|
|Administrator des Microsoft Managed Desktop-Diensts  | Wenn Sie einem Benutzer zugewiesen ist, erteilt diese Rolle dem Administrator **Lese-und Schreibberechtigungen für Features, die sich nicht auf die Sicherheit** im Microsoft Managed Desktop-Verwaltungsportal beziehen.  |
|Microsoft Managed Desktop-Dienst Leser | Wenn Sie einem Benutzer zugewiesen ist, gibt diese Rolle dem Administrator **schreibgeschützte Berechtigungen für Features, die sich nicht auf die Sicherheit** im Microsoft Managed Desktop-Verwaltungsportal beziehen. |
|Microsoft Managed Desktop Security Manager |Wenn Sie einem Benutzer zugewiesen ist, erteilt diese Rolle dem Administrator **Lese-und Schreibberechtigungen nur für sicherheitsbezogene Funktionen** im Verwaltungsportal von Microsoft Managed Desktop.   |

> [!NOTE]
> Zu den Sicherheitsfeatures zählen sicherheitsbezogene Kommunikation, Verwaltung von sicherheitskontakten, Verwaltung sicherheitsbezogener Supportanforderungen und Zugriff auf sicherheitsbezogene Berichte. 

## <a name="assigning-roles-to-administrators"></a>Zuweisen von Rollen zu Administratoren

Wenn Sie Hilfe beim Zuweisen von Azure Active Directory Rollen benötigen, finden Sie weitere Informationen unter [Administrator Rollen Berechtigungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).

Für eine einfache Verwaltung der integrierten Rollen wurde eine Sicherheitsgruppe für jede benutzerdefinierte Rolle erstellt (beispielsweise "moderne Arbeitsplatz Rollen – Sicherheits-Manager"). Führen Sie die folgenden Schritte aus, um Benutzer einer der Sicherheitsgruppen zuzuweisen:
1.  Wechseln Sie zum Azure-Portal, und navigieren Sie zum Azure Active Directory Blade.
2.  Wählen Sie auf der linken Seite Gruppen aus.
3.  Suchen Sie nach modernen Arbeitsplatz Rollen, und wählen Sie dann die Gruppe aus, die der Rolle zugeordnet ist, die Sie zuweisen möchten. 
4.  Wählen Sie auf der linken Seite Elemente aus, und klicken Sie dann auf der Befehlsleiste auf + Mitglieder hinzufügen.
5.  Geben Sie die e-Mail-Adresse der hinzugefügten Person ein. Wenn es sich um einen externen Benutzer handelt, müssen Sie ihn einladen, bevor Sie die Gruppe zuweisen können.
6.  Wählen Sie unten auswählen aus.

> [!NOTE]
> Das Verschachteln von Sicherheitsgruppen für die Rollenzuweisung wird derzeit nicht unterstützt. 
