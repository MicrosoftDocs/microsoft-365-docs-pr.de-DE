---
title: Berechtigungen im Microsoft 365 Compliance Center und Security Center
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
ms.audience: Admin
ms.topic: article
audience: Admin
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Mithilfe des Microsoft 365 Security Centers oder des Microsoft 365 Compliance Centers können Sie Berechtigungen zentral für alle Aufgaben im Zusammenhang mit Sicherheit und Compliance verwalten.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cc2808ffe5d0acd3a5c3c3a6252503ee5e2cf94e
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52530826"
---
# <a name="permissions-in-the-microsoft-365-compliance-center-and-microsoft-365-security-center"></a>Berechtigungen im neuen Microsoft 365 Compliance Center und Microsoft 365 Security Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Ihre Organisation muss Compliance- und Sicherheitsszenarien verwalten, die alle Microsoft 365-Dienste umfassen. Und Sie benötigen die Flexibilität, die richtigen Administratorberechtigungen für die richtigen Personen in der IT-Gruppe Ihrer Organisation bereitzustellen. Mithilfe des Microsoft 365 Security Centers oder des Microsoft 365 Compliance Centers können Sie Berechtigungen zentral für alle Aufgaben im Zusammenhang mit Sicherheit und Compliance verwalten.

Nachdem ein globaler Administrator Benutzer zu diesen Administratorrollen hinzugefügt hat, haben diese Administratoren Zugriff auf Features und Daten, die alle Dienste in Microsoft 365 umfassen, z. B. das Microsoft 365 Security Center, das Microsoft 365 Compliance Center, Azure, Office 365 und Enterprise Mobility + Security.

## <a name="what-the-microsoft-365-roles-are"></a>Was die Microsoft 365-Rollen sind

Die Rollen, die im Microsoft 365 Compliance Center und im Microsoft 365 Security Center angezeigt werden, sind Azure Active Directory-Rollen. Diese Rollen sind so konzipiert, dass Sie den Aufgaben in der IT-Gruppe Ihrer Organisation entsprechen, sodass einer Person ganz einfach alle Berechtigungen gewährt werden können, die sie für ihre Arbeit benötigt.

****

|Rolle|Beschreibung|
|---|---|
|**Globaler Administrator**|Zugriff auf alle Verwaltungsfunktionen in allen Microsoft 365-Diensten. Nur globale Administratoren können weitere Administratorrollen zuweisen. Weitere Informationen finden Sie unter [Globaler Administrator/Unternehmensadministrator](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator).|
|**Compliancedatenadministrator**|Verfolgen Sie die Daten Ihrer Organisation in Microsoft 365 nach, stellen Sie sicher, dass sie geschützt sind, und erhalten Sie Einblicke in alle Probleme, um Risiken zu minimieren. Weitere Informationen finden Sie unter [Compliancedatenadministrator](/azure/active-directory/roles/permissions-reference#compliance-data-administrator).|
|**Complianceadministrator**|Tragen Sie dazu bei, dass Ihre Organisation alle behördlichen Bestimmungen einhält und eDiscovery-Fälle verwalten sowie Richtlinien zur Datengovernance über Microsoft 365-Standorte, -Identitäten und -Apps hinweg aufrechterhalten kann. Weitere Informationen finden Sie unter [Complianceadministrator](/azure/active-directory/roles/permissions-reference#compliance-administrator).|
|**Sicherheitsoperator**|Zeigen Sie aktive Bedrohungen für Ihre Microsoft 365-Benutzer, -Geräte und -Inhalte an und untersuchen und reagieren Sie auf sie. Weitere Informationen finden Sie unter [Sicherheitsoperator](/azure/active-directory/roles/permissions-reference#security-operator).|
|**Benutzer mit Leseberechtigung für Sicherheitsfunktionen**|Zeigen Sie aktive Bedrohungen für Ihre Microsoft 365-Benutzer, -Geräte und -Inhalte an und untersuchen Sie diese; Sie besitzen jedoch (im Gegensatz zum Sicherheitsoperator) keine Berechtigung dazu, dagegen Maßnahmen zu ergreifen. Weitere Informationen finden Sie unter [Benutzer mit Leseberechtigung für Sicherheitsfunktionen](/azure/active-directory/roles/permissions-reference#security-reader).|
|**Sicherheitsadministrator**|Steuern Sie die Gesamtsicherheit Ihres Unternehmens, indem Sie Sicherheitsrichtlinien verwalten, Sicherheitsanalysen und Berichte zu Microsoft 365-Produkten überprüfen und im Hinblick auf Bedrohungen immer auf dem neuesten Stand bleiben. Weitere Informationen finden Sie unter [Sicherheitsadministrator](/azure/active-directory/roles/permissions-reference#security-administrator).|
|**Globaler Leser**|Die Version mit reiner Leseberechtigung der Rolle **globaler Administrator**. Zeigen Sie alle Einstellungen und Verwaltungsinformationen in Microsoft 365 an. Weitere Informationen finden Sie unter [Globaler Leser](/azure/active-directory/roles/permissions-reference#global-reader).|
|

## <a name="global-administrators-can-manage-roles-in-azure-active-directory"></a>Globale Administratoren können Rollen in Azure Active Directory verwalten

Wenn Sie im Microsoft 365 Compliance Center und im Microsoft 365 Security Center eine auswählen, können Sie deren Zuweisungen anzeigen. Um diese Zuweisungen verwalten zu können, müssen Sie aber zum Azure Active Directory wechseln.

Weitere Informationen finden Sie unter [Anzeigen und Zuweisen von Administratorrollen in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

![Verknüpfung zum Verwalten von Standardbenutzerberechtigungen in Azure Active Directory](../../media/permissions-manage-in-azure-ad-link.png)

## <a name="managing-roles-in-a-service-instead-of-azure-active-directory"></a>Verwalten von Rollen in einem Dienst anstelle von Azure Active Directory

Die Rollen, die im Microsoft 365 Compliance Center und im Microsoft 365 Security Center angezeigt werden, werden auch in den Diensten angezeigt, in denen sie über Berechtigungen verfügen. Sie können diese Rollen beispielsweise im Security & Compliance Center anzeigen.

![Rollen im Security & Compliance Center](../../media/m365-roles-in-o365-scc.png)

Informationen zur Verwendung dieser Rollen im Security & Compliance Center finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

### <a name="breaking-inheritance"></a>Unterbrechen der Vererbung

Es ist wichtig, dass Sie verstehen die Verwaltung dieser Rollen in Azure Active Directory zentral für **alle** Microsoft 365-Dienste erfolgt. Wenn Sie jedoch eine Rolle in einem bestimmten Dienst verwalten, wie z. B. dem Security & Compliance Center, so verwalten Sie die Rolle **nur** für diesen spezifischen Dienst. Die Zuweisungen und Berechtigungen für eine Rolle in einem Dienst setzen alle Berechtigungen außer Kraft, die der Azure Active Directory-Rolle erteilt wurden.

Dies kann äußerst nützlich sein. Wenn eine Person beispielsweise der Rolle „Sicherheitsadministrator“ zugewiesen ist, verfügt sie nicht über die Berechtigung zum Verwalten von Vorfällen. Sie können die Berechtigungen in Microsoft Defender für Endpunkt jedoch verwenden, um ihr die spezifische Berechtigung für die Vorfallsverwaltung in diesem Dienst zu erteilen.

## <a name="where-to-find-role-information-for-each-microsoft-365-service"></a>Wo Sie Rolleninformationen zu den einzelnen Microsoft 365-Diensten finden

Indem Sie einen Benutzer einer der Microsoft 365 Compliance- oder Sicherheitsrollen zuweisen, erteilen Sie diesem Benutzer die Berechtigung für eine Vielzahl von Microsoft 365-Diensten. Verwenden Sie die nachstehenden Links, um weitere Informationen zu den spezifischen Berechtigungen für eine Rolle in den einzelnen Diensten zu erhalten.

****

|Microsoft 365-Dienst|Rolleninformation|
|---|---|
|Administratorrollen in Office 365 und Microsoft 365 Business-Plänen|[Microsoft 365-Administratorrollen](../../admin/add-users/about-admin-roles.md)|
|Azure Active Directory (Azure AD) und Azure AD Identity Protection|[Azure AD-Administratorrollen](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Microsoft Defender for Identity|[Microsoft Defender for Identity-Rollengruppen](/azure-advanced-threat-protection/atp-role-groups)|
|Azure Information Protection|[Azure AD-Administratorrollen](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Compliance-Manager|[Compliance-Manager](../../compliance/compliance-manager-setup.md#set-user-permissions-and-assign-roles)|
|Exchange Online|[Rollenbasierte Zugriffssteuerung in Exchange](/exchange/permissions-exo/permissions-exo)|
|Intune|[Rollenbasierte Zugriffssteuerung von Intune](/intune/role-based-access-control)|
|Managed Desktop|[Azure AD-Administratorrollen](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Microsoft Cloud App Security|[Rollenbasierte Zugriffssteuerung](/cloud-app-security/manage-admins)|
|Security & Compliance Center|[Microsoft 365-Administratorrollen](permissions-in-the-security-and-compliance-center.md)|
|Privileged Identity Management|[Azure AD-Administratorrollen](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Sicherheitsbewertung|[Azure AD-Administratorrollen](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|SharePoint Online|[Azure AD-Administratorrollen](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) <p> [Informationen zur SharePoint-Administratorrolle in Office 365](/sharepoint/sharepoint-admin-role)|
|Teams/Skype for Business|[Azure AD-Administratorrollen](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Microsoft Defender für Endpunkt|[Microsoft Defender für Endpunkt – rollenbasierte Zugriffssteuerung](/windows/security/threat-protection/windows-defender-atp/rbac-windows-defender-advanced-threat-protection)|
|

## <a name="coming-soon"></a>In Kürze verfügbar

Wir arbeiten noch an den Berechtigungen im neuen Microsoft 365 Compliance Center und Microsoft 365 Security Center Wir arbeiten derzeit beispielsweise an der Unterstützung für Folgendes:

- Verwalten der Rollen im Microsoft 365 Compliance Center und im Microsoft 365 Security Center und nicht in Azure Active Directory.
- Anpassen von Rollen durch Hinzufügen oder Entfernen bestimmter Berechtigungen.
- Erstellen benutzerdefinierter Rollen mit von Ihnen ausgewählten Berechtigungen.