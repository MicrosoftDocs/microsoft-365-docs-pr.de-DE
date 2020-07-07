---
title: Rollen in Azure Active Directory im Microsoft 365 Admin Center
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
description: Verwalten Sie diese Azure-Administratorrollen im Microsoft 365 Admin Center.
ms.openlocfilehash: d35daab57446fd2a6a052f7e0fca29af7910c5f9
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432467"
---
# <a name="azure-active-directory-roles-in-the-microsoft-365-admin-center"></a>Rollen in Azure Active Directory im Microsoft 365 Admin Center

Im Microsoft 365 Admin Center können Sie mehr als 30 Azure AD-Rollen verwalten. Bei diesen Rollen handelt es sich jedoch um eine Teilmenge der Rollen, die im Azure-Portal verfügbar sind. Wenn es sich bei Ihrer Organisation um ein großes Unternehmen handelt, gibt es im Azure-Portal möglicherweise Rollen, die Ihren organisatorischen Anforderungen entsprechen. Sind Sie an detaillierten Rollenbeschreibungen für AZURE AD interessiert? Diese finden Sie unter [Administratorrollenberechtigungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).

Ein Benutzer, dem eine Administratorrolle zugewiesen wurde, verfügt über die gleichen Zugriffsrechte für Clouddienste, die Ihre Organisation abonniert hat, unabhängig davon, ob Sie die Rolle im Microsoft 365 Admin Center, im Azure-Portal oder mithilfe des Azure AD-Moduls für Windows PowerShell zuweisen.

::: moniker range="o365-worldwide"

Im Microsoft 365 Admin Center können Sie zu **Rollen**wechseln und dann eine beliebige Rolle auswählen, um den entsprechenden Detailbereich zu öffnen. Wählen Sie die Registerkarte **Berechtigungen** aus, um eine detaillierte Liste der Berechtigungen anzuzeigen, über die Administratoren mit dieser Rolle verfügen. Wählen Sie die Registerkarte **Zugewiesene** oder **Zugewiesene Administratoren** aus, um Benutzer zu Rollen hinzuzufügen. Weitere Informationen zum Zuweisen von Rollen im Microsoft 365 Admin Center finden Sie unter [Zuweisen von Administratorrollen](assign-admin-roles.md).

::: moniker-end

## <a name="all-azure-ad-roles"></a>Alle Azure AD-Rollen

Hier ist eine Liste aller im Microsoft 365 Admin Center verfügbaren Administratorrollen. Suchen Sie nach den detaillierten Rollenbeschreibungen der Microsoft 365-Administratorrollen? Siehe [Info zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).

|Administratorrolle     |Beschreibung  |
|---------|---------|
|Anwendungsadministrator     |    Hat vollständigen Zugriff auf Unternehmensanwendungen, Anwendungsregistrierungen und Anwendungsproxy-Einstellungen.     |
|Anwendungsentwickler     |    Kann Anwendungsregistrierungen erstellen und den App-Zugriff in seinem eigenen Namen erlauben.     |
|Authentifizierungsadministrator     |    Kann von Benutzern die erneute Registrierung der Authentifizierung für Nicht-Kennwort-Anmeldeinformationen (z. B. mehrstufige Authentifizierung) anfordern.     |
|Azure Information Protection-Administrator     |   Verwaltet Bezeichnungen für die Azure Information Protection-Richtlinie, verwaltet Schutzvorlagen und aktiviert Schutzmaßnahmen.       |
|Rechnungsadministrator     |    Tätigt Einkäufe, verwaltet Abonnements, verwaltet Serviceanfragen und überwacht die Dienstgüte.     |
|Cloudanwendungsadministrator     | Hat vollständigen Zugriff auf Unternehmensanwendungen und Anwendungsregistrierungen. Keine Anwendungsproxys.     |
|Cloudgeräteadministrator     |    Kann Geräte aktivieren, deaktivieren und löschen sowie Windows 10 BitLocker-Schlüssel auslesen.     |
|Compliance-Administrator     |    Verwaltet behördliche Anforderungen und eDiscovery-Fälle, verwaltet die Datengovernance für Speicherorte, Identitäten und Apps.     |
|Compliancedaten-Administrator     |    Verfolgt Daten nach, stellt sicher, dass diese geschützt sind, hat Einblick in Probleme und hilft, Risiken zu minimieren.     |
|Administrator für bedingten Zugriff     |   Verwaltet Azure Active Directory-Einstellungen für den bedingten Zugriff, nicht jedoch die Exchange ActiveSync-Richtlinie für den bedingten Zugriff.      |
|Genehmiger für Kunden-Lockboxzugriff     |      Verwaltet Kunden-Lockbox-Anforderungen, kann die Kunden-Lockbox aktivieren oder deaktivieren.   |
|Desktop Analytics-Administrator     |   Kann auf Desktop-Verwaltungstools und -dienste zugreifen und diese verwalten.      |
|Dynamics 365-Administrator     |  Hat Vollzugriff auf Microsoft Dynamics 365 Online, verwaltet Serviceanfragen, überwacht den Dienststatus.       |
|Exchange-Administrator     |  Hat Vollzugriff auf Exchange Online, erstellt und verwaltet Gruppen, verwaltet Serviceanfragen und überwacht den Dienststatus.    |
|Administrator für externe Identitätsanbieter    |     Konfiguriert Identitätsanbieter für die Verwendung im direkten Verbund.    |
|Globaler Administrator     |    Hat uneingeschränkten Zugriff auf alle Verwaltungsfunktionen und auf die meisten Daten in allen Admin Centern.     |
|Globaler Leser     |    Hat Lesezugriff auf alle Verwaltungsfunktionen und auf die meisten Daten in Admin Centern. Eine detaillierte Beschreibung der Zugriffsrechte und Einschränkungen dieser Rolle finden Sie unter [Administratorrollenberechtigungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader).    |
|Gruppenadministrator   |Erstellt Gruppen und verwaltet alle Gruppeneinstellungen in allen Admin Centern.|
|Gasteniladender     |    Verwaltet Azure Active Directory B2B-Gastbenutzereinladungen.     |
|Helpdesk-Administrator     | Setzt Kennwörter zurück und authentifiziert erneut für Nicht-Administratoren und einige Administratorrollen, verwaltet Serviceanfragen und überwacht den Dienststatus.      |
|Intune-Administrator     | Hat Vollzugriff auf Intune, verwaltet Benutzer und Geräte, um Richtlinien zuzuordnen, Gruppen zu erstellen und zu verwalten.      |
|Kaizala-Administrator     |    Vollzugriff auf alle Kaizala-Verwaltungsfunktionen und -Daten; verwaltet Serviceanfragen.     |
|Lizenzadministrator     |     Kann Benutzern Lizenzen zuweisen, diese entfernen und deren Verwendungsstandort bearbeiten.    |
|Nachrichtencenter-Datenschutzleser     |    Hat Zugriff auf Datenschutznachrichten im Nachrichtencenter, erhält E-Mail-Benachrichtigungen.     |
|Nachrichtencenter-Leseberechtigter     | Kann normale Nachrichten im Nachrichtencenter lesen und teilen, erhält wöchentliche E-Mail-Digests, hat Lesezugriff auf Benutzer, Gruppen, Domänen und Abonnements.     |
|Office-Apps-Administrator    |   Verwaltet cloudbasierte Richtlinien für Office und Inhalte im Dialogfenster "Neuigkeiten", das den Benutzern in ihren Office-Apps angezeigt wird.   |
|Power BI-Administrator    |   Hat Vollzugriff auf Power BI-Verwaltungsaufgaben, verwaltet Serviceanfragen und überwacht den Dienststatus.   |
|Power Plattform-Administrator     |    Hat Vollzugriff auf Microsoft Dynamics 365, PowerApps, Richtlinien zur Verhinderung von Datenverlust und auf Microsoft Flow.     |
|Administrator für privilegierte Rollen     |    Verwaltet Rollenzuweisungen und alle Zugriffssteuerungsfunktionen von Privileged Identity Management.     |
|Privilegierter Authentifizierungsadministrator     |    Setzt Kennwörter zurück, aktualisiert Anmeldeinformationen ohne Kennwörter, erzwingt das Abmelden, überwacht den Dienststatus und verwaltet Serviceanfragen.     |
|Berichtleseberechtigter     |   Hat Einblick in Verwendungsberichtsdaten aus dem Berichtedashboard, dem Inhaltspaket für die Power BI-Einführung, aus Anmeldeberichten und der Microsoft Graph-Berichterstellungs-API.      |
|Suchadministrator     |    Hat Vollzugriff auf Microsoft Search, weist die Rollen "Suchadministrator" und "Such-Editor" zu, verwaltet Inhalte, überwacht den Dienststatus und erstellt Serviceanfragen.     |
|Such-Editor     |    Kann nur Inhalte für Microsoft Search erstellen, bearbeiten und löschen, wie Lesezeichen, F&A und Speicherorte.     |
|Sicherheitsadministrator     |    Überwacht die Sicherheit in der Organisation, verwaltet Sicherheitsrichtlinien, überprüft Sicherheitsanalysen und -berichte und überwacht die Bedrohungslage.     |
|Sicherheitsoperator     |    Untersucht und reagiert auf Sicherheitswarnungen, verwaltet Funktionen im Identity Protection Center, überwacht den Dienststatus.     |
|Benutzer mit Leseberechtigung für Sicherheitsfunktionen     |    Hat reinen Lesezugriff auf Sicherheitsfeatures, Anmeldeberichte und Überwachungsprotokolle.     |
|Dienstsupportadministrator     |    Erstellt Dienstanforderungen für Azure-, Microsoft 365- und Office 365-Dienste und überwacht den Dienststatus.     |
|SharePoint-Administrator     |    Hat Vollzugriff auf SharePoint Online, verwaltet Microsoft 365-Gruppen, verwaltet Serviceanfragen und überwacht den Dienststatus.     |
|Skype for Business-Administrator     | Hat Vollzugriff auf alle Microsoft Teams- und Skype-Funktionen sowie Skype-Benutzerattribute, verwaltet Serviceanfragen und überwacht den Dienststatus.      |
|Microsoft Teams-Administrator     |    Hat Vollzugriff auf die Microsoft Teams- und Skype-Admin Center, verwaltet Microsoft 365-Gruppen und Serviceanfragen und überwacht den Dienststatus.     |
|Microsoft Teams-Kommunikationsmanager     |    Weist Telefonnummern zu, erstellt und verwaltet VoIP- und Besprechungsrichtlinien und liest Anrufanalysen.     |
|Supporttechniker für die Microsoft Teams-Kommunikation     |    Liest Anrufaufzeichnungsdetails für alle Anrufteilnehmer, um Kommunikationsprobleme zu behandeln.     |
|Supportexperte für die Microsoft Teams-Kommunikation     |    Liest Benutzeranrufdetails nur für einen bestimmten Benutzer, um Kommunikationsprobleme zu behandeln.|
|Benutzeradministrator     |   Setzt Benutzerkennwörter zurück, erstellt und verwaltet Benutzer und Gruppen, einschließlich Filtern, verwaltet Serviceanfragen und überwacht den Dienststatus.|

## <a name="delegated-administration-for-microsoft-partners"></a>Delegierte Administration für Microsoft-Partner

Wenn Sie mit einem Microsoft-Partner arbeiten, können Sie den entsprechenden Personen Administratorrollen zuweisen. Diese können wiederum Benutzern in Ihrem (oder deren) Unternehmen Administratorrollen zuweisen. Dies kann beispielsweise sinnvoll sein, wenn diese Personen Ihre Online-Organisation für Sie einrichten und verwalten.
  
Ein Partner kann die folgenden Rollen zuweisen: 

- Vollständige Verwaltung mit Berechtigungen, die jenen eines globalen Administrators entsprechen, mit der Ausnahme, dass die mehrstufige Authentifizierung über das Partner Center verwaltet wird.

- Eingeschränkte Verwaltung mit Berechtigungen, die jenen eines Helpdesk-Administrators entsprechen.

Bevor der Partner diese Rollen Benutzern zuweisen kann, müssen Sie ihn als delegierten Administrator zu Ihrem Konto hinzufügen. Dieser Vorgang wird von einem autorisierten Partner initiiert. Der Partner fragt Sie in einer E-Mail-Nachricht, ob Sie ihm die Berechtigung erteilen möchten, als delegierter Administrator zu fungieren. Weitere Informationen hierzu finden Sie unter [Autorisieren oder Entfernen von Partnerbeziehungen](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner).
  
## <a name="related-articles"></a>Verwandte Artikel

[Informationen zu Microsoft 365-Administratorrollen](about-admin-roles.md)

[Zuweisen von Administratorrollen](assign-admin-roles.md)
  
[Teams-Aktivitätsberichte im Microsoft 365 Admin Center](../activity-reports/activity-reports.md)