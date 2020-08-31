---
title: Berechtigungen im Microsoft 365 Security- und Compliance Center
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Mithilfe des Microsoft 365 Security Centers oder des Microsoft 365 Compliance Centers können Sie Berechtigungen zentral für alle Aufgaben im Zusammenhang mit Sicherheit und Compliance verwalten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c18f50fcad7b934e02c2110fa05196874ab0169a
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307773"
---
# <a name="permissions-in-the-microsoft-365-compliance-center-and-microsoft-365-security-center"></a>Berechtigungen im neuen Microsoft 365 Compliance Center und Microsoft 365 Security Center

Ihre Organisation muss Sicherheits- und Complianceszenarios verwalten, die alle Microsoft 365-Dienste umfassen. Und Sie benötigen die Flexibilität, die richtigen Administratorberechtigungen für die richtigen Personen in der IT-Gruppe Ihrer Organisation bereitzustellen. Mithilfe des Microsoft 365 Security Centers oder des Microsoft 365 Compliance Centers können Sie Berechtigungen zentral für alle Aufgaben im Zusammenhang mit Sicherheit und Compliance verwalten.

Nachdem der globale Administrator diese Administratorrollen zugewiesen hat, haben die Administratoren Zugriff auf Features und Daten, die alle Dienste in Microsoft 365 umfassen, z. B. das Microsoft 365 Security Center, das Microsoft 365 Compliance Center, Azure, Office 365 und Enterprise Mobility +.Security.

## <a name="what-the-microsoft-365-roles-are"></a>Was die Microsoft 365-Rollen sind

Die Rollen, die im Microsoft 365 Compliance Center und im Microsoft 365 Security Center angezeigt werden, sind Azure Active Directory-Rollen. Diese Rollen sind so konzipiert, dass Sie den Aufgaben in der IT-Gruppe Ihrer Organisation entsprechen, sodass einer Person ganz einfach alle Berechtigungen gewährt werden können, die sie für ihre Arbeit benötigt.

****

|Rolle|Beschreibung|
|---|---|
|**Globaler Administrator**|Benutzer mit dieser Rolle haben Zugriff auf alle Verwaltungsfunktionen in allen Microsoft 365-Diensten. Nur globale Administratoren können weitere Administratorrollen zuweisen.|
|**Compliancedatenadministrator**|Benutzer mit dieser Rolle können die Daten Ihrer Organisation in Microsoft 365 nachverfolgen, sicherstellen, dass sie geschützt sind, und Einblicke in alle Probleme erhalten, um Risiken zu minimieren.|
|**Complianceadministrator**|Benutzer mit dieser Rolle können dazu beitragen, dass Ihre Organisation alle behördlichen Bestimmungen einhält und eDiscovery-Fälle verwalten und Richtlinien zur Datengovernance über Microsoft 365-Standorte, -Identitäten und -Apps hinweg aufrechterhalten kann.|
|**Sicherheitsoperator**|Benutzer mit dieser Rolle können aktive Bedrohungen für Ihre Microsoft 365-Benutzer, -Geräte und -Inhalte anzeigen, untersuchen und auf Sie reagieren.|
|**Benutzer mit Leseberechtigung für Sicherheitsfunktionen**|Benutzer mit dieser Rolle können aktive Bedrohungen für Ihre Microsoft 365-Benutzer, -Geräte und -Inhalte anzeigen und untersuchen, besitzen aber (im Gegensatz zum Sicherheitsoperator) keine Berechtigungen zum Reagieren, indem sie Maßnahmen ergreifen.|
|**Sicherheitsadministrator**|Benutzer mit dieser Rolle können die Gesamtsicherheit Ihres Unternehmens steuern, indem sie Sicherheitsrichtlinien verwalten, Sicherheitsanalysen und Berichte in Microsoft 365-Produkten überprüfen und im Zusammenhang mit Bedrohungen immer auf dem neuesten Stand bleiben.|
|

## <a name="what-the-microsoft-365-roles-have-access-to"></a>Worauf die Microsoft 365-Rollen Zugriff haben

Nachfolgend sind die verfügbaren Rollen und die Aufgaben aufgelistet, die von den Benutzern ausgeführt werden können, denen diese zugewiesen sind.

### <a name="global-administrator"></a>Globaler Administrator

Benutzer mit dieser Rolle besitzen Zugriff auf alle administrativen Features in Azure Active Directory sowie Dienste, die Azure Active Directory-Identitäten nutzen, z.B. Microsoft 365 Security Center, Microsoft 365 Compliance Center, Exchange Online, SharePoint Online oder Skype for Business Online. Die Person, die die Anmeldung für den Azure Active Directory-Mandanten vornimmt, wird ein globaler Administrator. Nur globale Administratoren können weitere Administratorrollen zuweisen. In Ihrem Unternehmen können mehrere globale Administratoren vorhanden sein. Globale Administratoren können das Kennwort für alle Benutzer und alle anderen Administratoren zurücksetzen.

### <a name="compliance-administrator"></a>Complianceadministrator

Benutzer mit dieser Rolle verfügen über Berechtigungen zum Verwalten von Compliancefeatures im Microsoft 365 Compliance Center, Microsoft 365 Admin Center, Azure und Security & Compliance Center. Die Benutzer können auch alle Features im Exchange Admin Center sowie im Teams und Skype for Business Admin Center verwalten und Supporttickets für Azure und Microsoft 365 erstellen.

****

|In diesem Dienst...|Der Complianceadministrator kann...|
|---|---|
|[**Microsoft 365 Compliance Center**](https://compliance.microsoft.com/)|Schützen und Verwalten Ihrer Organisationsdaten für Microsoft 365-Dienste <br/><br/> Verwalten von Konformitätwarnungen|
|[**Compliancebewertung**](https://docs.microsoft.com/microsoft-365/compliance/meet-data-protection-and-regulatory-reqs-using-microsoft-cloud)|Nachverfolgen, Zuweisen und Überprüfen der Einhaltung gesetzlicher Vorschriften durch Ihre Organisation|
|[**Security & Compliance Center**](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|Verwalten der Datengovernance <br/><br/> Durchführen von Untersuchungen zu rechtlichen Aspekten und Daten <br/><br/> Verwalten von DRS-Anforderungen.|
|[**Intune**](https://docs.microsoft.com/intune/role-based-access-control)|Anzeigen aller Intune-Überwachungsdaten|
|[**Cloud-App-Sicherheit**](https://docs.microsoft.com/cloud-app-security/manage-admins)|Verfügt über schreibgeschützten Zugriff und kann Warnungen verwalten <br/><br/> Kann Dateirichtlinien erstellen und ändern und Dateigovernanceaktionen zulassen <br/><br/> Kann alle unter „Datenverwaltung“ integrierten Berichte anzeigen|
|

### <a name="compliance-data-administrator"></a>Compliancedatenadministrator

Benutzer mit dieser Rolle verfügen über Berechtigungen zum Schützen und Nachverfolgen von Daten im Microsoft 365 Compliance Center, Microsoft 365 Admin Center und in Azure. Die Benutzer können auch alle Features im Exchange Admin Center, in Compliancebewertung sowie im Teams und Skype for Business Admin Center verwalten und Supporttickets für Azure und Microsoft 365 erstellen.

****

|In diesem Dienst...|Der Compliancedatenadministrator kann...|
|---|---|
|[**Microsoft 365 Compliance Center**](https://compliance.microsoft.com/)|Schützen und Verwalten Ihrer Organisationsdaten für Microsoft 365-Dienste <br/><br/> Verwalten von Konformitätwarnungen <br/><br/> Verwalten von Vertraulichkeitsbezeichnungen|
|[**Compliancebewertung**](https://docs.microsoft.com/microsoft-365/compliance/meet-data-protection-and-regulatory-reqs-using-microsoft-cloud)|Nachverfolgen, Zuweisen und Überprüfen der Einhaltung gesetzlicher Vorschriften durch Ihre Organisation|
|[**Security & Compliance Center**](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|Verwalten der Datengovernance <br/><br/> Durchführen von Untersuchungen zu rechtlichen Aspekten und Daten <br/><br/> Verwalten von DRS-Anforderungen. <br/><br/> Verwalten von Vertraulichkeitsbezeichnungen|
|[**Intune**](https://docs.microsoft.com/intune/role-based-access-control) (in Kürze verfügbar)|Anzeigen aller Intune-Überwachungsdaten|
|[**Cloud-App-Sicherheit**](https://docs.microsoft.com/cloud-app-security/manage-admins)|Verwenden von schreibgeschützten Berechtigungen zum Anzeigen von Informationen <br/>Verwalten von Benachrichtigungen <br/><br/> Erstellen und Ändern von Dateirichtlinien und Zulassen von Dateigovernanceaktionen <br/><br/> Anzeigen aller unter „Datenverwaltung“ integrierten Berichte|
|

### <a name="security-administrator"></a>Sicherheitsadministrator

Benutzer mit dieser Rolle haben Berechtigungen zur Verwaltung sicherheitsrelevanter Funktionen im Microsoft 365 Security Center, Azure Active Directory Identity Protection, Azure Information Protection und Security & Compliance Center.

****

|In diesem Dienst...|Der Sicherheitsadministrator kann...|
|---|---|
|[**Microsoft 365 Security Center**](https://security.microsoft.com/)|Überwachen von sicherheitsrelevanten Richtlinien in Microsoft 365-Diensten <br/><br/>  Verwalten von Sicherheitsbedrohungen und Warnungen <br/><br/> Anzeigen von Berichten <br/><br/> Verwalten von Vertraulichkeitsbezeichnungen|
|**Identity Protection Center**|Alle Berechtigungen des Benutzers mit Leseberechtigung für Sicherheitsfunktionen plus Durchführung aller  Identity Protection Center-Vorgänge, mit Ausnahme des Zurücksetzens von Kennwörtern.|
|[**Privileged Identity Management**](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-configure)|Alle Berechtigungen des Benutzers mit Leseberechtigung für Sicherheitsfunktionen <br/><br/> **Kann keine** Azure AD-Rollenzuweisungen oder -einstellungen verwalten.|
|[**Security & Compliance Center**](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|Verwalten von Sicherheitsrichtlinien <br/><br/> Anzeigen, Untersuchen und Reagieren auf Sicherheitsbedrohungen <br/><br/> Anzeigen von Berichten <br/><br/> Verwalten von Vertraulichkeitsbezeichnungen|
|**Azure Advanced Threat Protection**|Überwachen und Reagieren auf verdächtige Sicherheitsaktivitäten|
|**Windows Defender ATP und EDR**|Zuweisen von Rollen <br/><br/> Verwalten von Computergruppen <br/><br/> Konfigurieren der Endpunkt-Bedrohungserkennung und der automatisierten Korrektur <br/><br/> Anzeigen, Untersuchen und Reagieren auf Warnungen|
|[**Intune**](https://docs.microsoft.com/intune/role-based-access-control)|Anzeigen von Benutzern, Geräten, Registrierung, Konfiguration und Anwendungsinformationen <br/><br/> Kann **keine** Änderungen an Intune vornehmen|
|[**Cloud-App-Sicherheit**](https://docs.microsoft.com/cloud-app-security/manage-admins)|Hinzufügen von Administratoren, Richtlinien und Einstellungen, Hochladen von Protokollen und Ausführen von Governanceaktionen|
|[**Azure Security Center**](https://docs.microsoft.com/azure/role-based-access-control/built-in-roles) (in Kürze verfügbar)|Anzeigen von Sicherheitsrichtlinien und -zuständen, Bearbeiten von Sicherheitsrichtlinien sowie Anzeigen und Verwerfen von Warnungen und Empfehlungen.|
|[**Office 365-Dienstintegrität**](https://docs.microsoft.com/microsoft-365/enterprise/view-service-health)|Anzeigen der Integrität von Office 365-Diensten|
|

### <a name="security-operator"></a>Sicherheitsoperator

Benutzer mit dieser Rolle können Warnungen verwalten und besitzen globalen schreibgeschützten Zugriff auf sicherheitsbezogene Features, einschließlich alle Informationen in Microsoft 365 Security Center, Azure Active Directory, Identity Protection, und Privileged Identity Management, sowie die Möglichkeit zum Lesen von Azure Active Directory-Anmeldeberichten und Überwachungsprotokollen und für das Security & Compliance Center.

****

|In diesem Dienst...|Der Sicherheitsoperator kann...|
|---|---|
|[**Microsoft 365 Security Center**](https://security.microsoft.com/)|Alle Berechtigungen des Benutzers mit Leseberechtigung für Sicherheitsfunktionen <br/><br/> Anzeigen, Untersuchen und Reagieren auf Sicherheitswarnungen|
|**Identity Protection Center** (in Kürze verfügbar)|Alle Berechtigungen des Benutzers mit Leseberechtigung für Sicherheitsfunktionen|
|[**Privileged Identity Management**](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-configure)|Alle Berechtigungen des Benutzers mit Leseberechtigung für Sicherheitsfunktionen|
|[**Security & Compliance Center**](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|Alle Berechtigungen des Benutzers mit Leseberechtigung für Sicherheitsfunktionen <br/><br/> Anzeigen, Untersuchen und Reagieren auf Sicherheitsbedrohungen|
|**Windows Defender ATP und EDR**|Alle Berechtigungen des Benutzers mit Leseberechtigung für Sicherheitsfunktionen <br/><br/> Anzeigen, Untersuchen und Reagieren auf Warnungen|
|[**Intune**](https://docs.microsoft.com/intune/role-based-access-control)|Anzeigen von Benutzern, Geräten, Registrierung, Konfiguration und Anwendungsinformationen <br/><br/> Kann **keine** Änderungen an Intune vornehmen|
|[**Cloud-App-Sicherheit**](https://docs.microsoft.com/cloud-app-security/manage-admins)|Alle Berechtigungen des Benutzers mit Leseberechtigung für Sicherheitsfunktionen plus Anzeigen und Schließen von Warnungen|
|[**Office 365-Dienstintegrität**](https://docs.microsoft.com/microsoft-365/enterprise/view-service-health)|Anzeigen der Integrität von Office 365-Diensten|
|

### <a name="security-reader"></a>Benutzer mit Leseberechtigung für Sicherheitsfunktionen

Benutzer mit dieser Rolle besitzen globalen schreibgeschützten Zugriff auf sicherheitsbezogene Features, einschließlich alle Informationen in Microsoft 365 Security Center, Azure Active Directory, Identity Protection, und Privileged Identity Management, sowie die Möglichkeit zum Lesen von Azure Active Directory-Anmeldeberichten und Überwachungsprotokollen und für das Security & Compliance Center.

****

|In diesem Dienst...|Ein Sicherheitsleseberechtigte kann...|
|---|---|
|[**Microsoft 365 Security Center**](https://security.microsoft.com/)|Anzeigen von sicherheitsrelevanten Richtlinien in Microsoft 365-Diensten <br/><br/> Anzeigen von Sicherheitsbedrohungen und Warnungen <br/><br/> Anzeigen von Berichten|
|**Identity Protection Center**|Lesen Sie alle Sicherheitsberichte und Einstellungsinformationen für Sicherheitsfeatures: Antispam, Verschlüsselung, Verhinderung von Datenverlust (DLP), Antimalware, Advanced Threat Protection (ATP), Anti-Phishing-und Nachrichtenflussregeln (auch als Transportregeln bezeichnet).|
|[**Privileged Identity Management**](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-configure)|Verwenden Sie schreibgeschützten Zugriff, um alle eingeblendeten Informationen in Azure AD PIM anzuzeigen: Richtlinien und Berichte für Azure AD-Rollenzuweisungen, Sicherheitsüberprüfungen und ( in Zukunft) Richtliniendaten und Berichte für andere Szenarien als die Azure AD-Rollenzuweisung. <br/><br/> **Kann sich nicht** für Azure AD PIM registrieren oder Änderungen durchführen. Im PIM-Portal oder über PowerShell können Personen mit dieser Rolle zusätzliche Rollen (z.B. globaler Administrator oder Administrator für privilegierte Rollen) aktivieren, wenn der Benutzer für sie geeignet ist.|
|[**Security & Compliance Center**](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|Anzeigen von Sicherheitsrichtlinien <br/><br/> Anzeigen und Untersuchen von Sicherheitsbedrohungen <br/><br/> Anzeigen von Berichten|
|**Windows Defender ATP und EDR**|Anzeigen und Untersuchen von Warnungen|
|[**Intune**](https://docs.microsoft.com/intune/role-based-access-control)|Anzeigen von Benutzern, Geräten, Registrierung, Konfiguration und Anwendungsinformationen <br/><br/> Kann **keine** Änderungen an Intune vornehmen|
|[**Cloud-App-Sicherheit**](https://docs.microsoft.com/cloud-app-security/manage-admins)|Verwenden von schreibgeschützten Berechtigungen zum Anzeigen von Informationen <br/><br/> Verwalten von Benachrichtigungen|
|[**Azure Security Center**](https://docs.microsoft.com/azure/role-based-access-control/built-in-roles)|Anzeigen von Empfehlungen und Benachrichtigungen <br/><br/> Anzeigen von Sicherheitsrichtlinien <br/><br/> Kann Sicherheitsstatus anzeigen, aber keine Änderungen vornehmen.|
|[**Office 365-Dienstintegrität**](https://docs.microsoft.com/microsoft-365/enterprise/view-service-health)|Anzeigen der Integrität von Office 365-Diensten|
|

## <a name="global-administrators-can-manage-roles-in-azure-active-directory"></a>Globale Administratoren können Rollen in Azure Active Directory verwalten

Wenn Sie im Microsoft 365 Compliance Center und im Microsoft 365 Security Center eine auswählen, können Sie deren Zuweisungen anzeigen. Um diese Zuweisungen verwalten zu können, müssen Sie aber zum Azure Active Directory wechseln.

Weitere Informationen finden Sie unter [Anzeigen und Zuweisen von Administratorrollen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

![Verknüpfung zum Verwalten von Standardbenutzerberechtigungen in Azure Active Directory](../../media/permissions-manage-in-azure-ad-link.png)

## <a name="managing-roles-in-a-service-instead-of-azure-active-directory"></a>Verwalten von Rollen in einem Dienst anstelle von Azure Active Directory

Die Rollen, die im Microsoft 365 Compliance Center und im Microsoft 365 Security Center angezeigt werden, werden auch in den Diensten angezeigt, in denen sie über Berechtigungen verfügen. Sie können diese Rollen beispielsweise im Security & Compliance Center anzeigen.

![Rollen im Security & Compliance Center](../../media/m365-roles-in-o365-scc.png)

### <a name="breaking-inheritance"></a>Unterbrechen der Vererbung

Es ist wichtig, dass Sie verstehen die Verwaltung dieser Rollen in Azure Active Directory zentral für **alle** Microsoft 365-Dienste erfolgt. Wenn Sie jedoch eine Rolle in einem bestimmten Dienst verwalten, wie z. B. dem Security & Compliance Center, so verwalten Sie die Rolle **nur** für diesen spezifischen Dienst. Die Zuweisungen und Berechtigungen für eine Rolle in einem Dienst setzen alle Berechtigungen außer Kraft, die der Azure Active Directory-Rolle erteilt wurden.

Dies kann hilfreich sein – wenn eine Person beispielsweise der Rolle „Sicherheitsadministrator“ zugewiesen ist, verfügt sie nicht über die Berechtigung zum Verwalten von Vorfällen. Sie können die Berechtigungen in Windows Defender Advanced Threat Protection jedoch verwenden, um ihnen die spezifische Berechtigung für die Vorfallsverwaltung in diesem Dienst zu erteilen.

## <a name="where-to-find-role-information-for-each-microsoft-365-service"></a>Wo Sie Rolleninformationen zu den einzelnen Microsoft 365-Diensten finden

Indem Sie einen Benutzer einer der Microsoft 365 Compliance- oder Sicherheitsrollen zuweisen, erteilen Sie diesem Benutzer die Berechtigung für eine Vielzahl von Microsoft 365-Diensten. Verwenden Sie die nachstehenden Links, um weitere Informationen zu den spezifischen Berechtigungen für eine Rolle in den einzelnen Diensten zu erhalten.

****

|Microsoft 365-Dienst|Rolleninformation|
|---|---|
|Administratorrollen in Office 365 und Microsoft 365 Business-Plänen|[Microsoft 365-Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide)|
|Azure Active Directory (Azure AD) und Azure AD Identity Protection|[Azure AD-Administratorrollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Azure Advanced Threat Protection|[Azure ATP-Rollengruppen](https://docs.microsoft.com/azure-advanced-threat-protection/atp-role-groups)|
|Azure Information Protection|[Azure AD-Administratorrollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Compliancebewertung|[Rollen er Compliancebewertung](https://docs.microsoft.com/microsoft-365/compliance/compliance-score-setup#set-user-permissions-and-assign-roles)|
|Exchange Online|[Rollenbasierte Zugriffssteuerung in Exchange](https://docs.microsoft.com/exchange/understanding-role-based-access-control-exchange-2013-help)|
|Intune|[Rollenbasierte Zugriffssteuerung von Intune](https://docs.microsoft.com/intune/role-based-access-control)|
|Managed Desktop|[Azure AD-Administratorrollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Microsoft Cloud App Security|[Rollenbasierte Zugriffssteuerung](https://docs.microsoft.com/cloud-app-security/manage-admins)|
|Security & Compliance Center|[Microsoft 365-Administratorrollen](permissions-in-the-security-and-compliance-center.md)|
|Privileged Identity Management|[Azure AD-Administratorrollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Sicherheitsbewertung|[Azure AD-Administratorrollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|SharePoint Online|[Azure AD-Administratorrollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) <br/><br/> [Informationen zur SharePoint-Administratorrolle in Office 365](https://docs.microsoft.com/sharepoint/sharepoint-admin-role)|
|Teams/Skype for Business|[Azure AD-Administratorrollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Windows Defender Advanced Threat Protection|[Rollenbasierte Zugriffssteuerung von Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/rbac-windows-defender-advanced-threat-protection)|
|

## <a name="what-is-coming-soon"></a>Was in Kürze verfügbar sein wird

Wir arbeiten noch an den Berechtigungen im neuen Microsoft 365 Compliance Center und Microsoft 365 Security Center Wir arbeiten derzeit beispielsweise an der Unterstützung für Folgendes:

- Verwalten der Rollen im Microsoft 365 Compliance Center und im Microsoft 365 Security Center und nicht in Azure Active Directory.

- Anpassen von Rollen durch Hinzufügen oder Entfernen bestimmter Berechtigungen.

- Erstellen benutzerdefinierter Rollen mit von Ihnen ausgewählten Berechtigungen.
