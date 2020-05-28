---
title: Informationen zu Administratorrollen im Microsoft 365 Admin Center
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: da585eea-f576-4f55-a1e0-87090b6aaa9d
description: Administratorrollen sind Geschäftsfunktionen zugeordnet. Über sie werden Berechtigungen für bestimmte Aufgaben im Admin Center erteilt. Der Dienstadministrator öffnet beispielsweise Supporttickets bei Microsoft.
ms.openlocfilehash: d67f80ef00f6decb7172d4ea484a3c4161fcbf31
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387422"
---
# <a name="about-admin-roles"></a>Info zu Administratorrollen

Ihr Microsoft 365- oder Office 365-Abonnement bietet eine Reihe von Administratorrollen, die Sie Benutzern in Ihrer Organisation mithilfe von Microsoft 365 Admin Center zuweisen können. Jede Administratorrolle ist häufig genutzten Geschäftsfunktionen zugeordnet. Über diese Rollen erhalten Personen in Ihrer Organisation die Berechtigung zum Ausführen bestimmter Aufgaben in den Admin Centern.

Im Microsoft 365 Admin Center können Sie Azure AD-Rollen und Microsoft Intune-Rollen verwalten. Bei diesen Rollen handelt es sich jedoch um eine Teilmenge der Rollen, die im Azure AD-Portal und im Intune Admin Center verfügbar sind.

Sind Sie an detaillierten Rollenbeschreibungen für AZURE AD interessiert? Diese finden Sie unter [Administratorrollenberechtigungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).

Sind Sie an detaillierten Rollenbeschreibungen für Microsoft Intune interessiert? Siehe [Rollenbasierte Zugriffssteuerung (RBAC) mit Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control).

Weitere Informationen zum Zuweisen von Rollen im Microsoft 365 Admin Center finden Sie unter [Zuweisen von Administratorrollen](assign-admin-roles.md).

## <a name="things-to-consider"></a>Zu berücksichtigende Aspekte...

Da Administratoren Zugriff auf vertrauliche Daten und Dateien haben, empfiehlt es sich, diese Richtlinien zu befolgen, um die Daten Ihrer Organisation besser zu schützen.

| Empfehlung                  | Warum ist das wichtig?                 |
| :------------------- | :------------------- |
| 2 bis 4 globale Administratoren vorsehen  | Da nur ein anderer globaler Administrator das Kennwort eines globalen Administrators zurücksetzen kann, empfiehlt es sich, in Ihrer Organisation mindestens zwei globale Administratoren vorzusehen für den Fall, dass es zu einer Kontosperre kommt. Ein globaler Administrator hat jedoch fast unbegrenzten Zugriff auf die Einstellungen Ihrer Organisation und die meisten Daten. Daher wird empfohlen, nicht mehr als vier globale Administratoren einzurichten, da dies ein Sicherheitsrisiko darstellt. |
| Die Rolle *mit den wenigsten Berechtigungen* zuweisen    | Die Rolle *mit den wenigsten Berechtigungen* zuweisen bedeutet, Administratoren nur den Zugriff zu gewähren, den sie zum Erledigen einer Aufgabe benötigen. Wenn Sie beispielsweise möchten, dass jemand Mitarbeiterkennwörter zurücksetzen kann, sollten Sie ihm nicht die unbegrenzte Rolle des globalen Administrators zuweisen, sondern eine Rolle mit eingeschränkten Befugnissen wie jene des Kennwortadministrators oder des Helpdesk-Administrators. Dies trägt dazu bei, Ihre Daten zu schützen.                 |
| Mehrstufige Authentifizierung vorschreiben                  |    Es ist zwar sinnvoll, die mehrstufige Authentifizierung für alle Benutzer vorzuschreiben, für Administratoren sollte sie jedoch unbedingt zur Anmeldung vorgesehen sein. Bei der mehrstufigen Authentifizierung müssen Benutzer eine zweite Identifikationsmethode eingeben, um sicherzustellen, dass sie tatsächlich die Person sind, die sie behaupten zu sein. Administratoren können auf eine Vielzahl von Kunden- und Mitarbeiterdaten zugreifen. Wenn Sie die mehrstufige Authentifizierung vorschreiben, ist ein kompromittiertes Administratorkennwort ohne die zweite Art der Identifizierung nutzlos.  <br><br>Wenn Sie die mehrstufige Authentifizierung aktivieren, müssen die Benutzer bei der nächsten Anmeldung eine alternative E-Mail-Adresse und Telefonnummer für die Kontowiederherstellung angeben.  <br> [Einrichten der mehrstufigen Authentifizierung](../security-and-compliance/set-up-multi-factor-authentication.md)          |

Wenn im Admin Center eine Nachricht angezeigt wird, die besagt, dass Sie nicht über die Berechtigungen zum Bearbeiten einer Einstellung oder Seite verfügen, liegt dies daran, dass Ihnen eine Rolle zugewiesen ist, die nicht über die entsprechende Berechtigung verfügt.

## <a name="azure-ad-roles-available-in-the-microsoft-365-admin-center"></a>Im Microsoft 365 Admin Center verfügbare Azure AD-Rollen

Im Microsoft 365 Admin Center können Sie mehr als 30 Azure AD-Rollen verwalten. Bei diesen Rollen handelt es sich jedoch um eine Teilmenge der Rollen, die im Azure-Portal verfügbar sind. Wenn es sich bei Ihrer Organisation um ein großes Unternehmen handelt, gibt es im Azure-Portal möglicherweise Rollen, die Ihren organisatorischen Anforderungen entsprechen.

Ein Benutzer, dem eine Administratorrolle zugewiesen wurde, verfügt über die gleichen Zugriffsrechte für Clouddienste, die Ihre Organisation abonniert hat, unabhängig davon, ob Sie die Rolle im Microsoft 365 Admin Center, im Azure-Portal oder mithilfe des Azure AD-Moduls für Windows PowerShell zuweisen.

::: moniker range="o365-worldwide"

Im Microsoft 365 Admin Center können Sie zu **Rollen**wechseln und dann eine beliebige Rolle auswählen, um den entsprechenden Detailbereich zu öffnen. Wählen Sie die Registerkarte **Berechtigungen** aus, um eine detaillierte Liste der Berechtigungen anzuzeigen, über die Administratoren mit dieser Rolle verfügen. Wählen Sie die Registerkarte **Zugewiesene** oder **Zugewiesene Administratoren** aus, um Benutzer zu Rollen hinzuzufügen.

::: moniker-end

Es genügt wahrscheinlich, wenn Sie in Ihrer Organisation nur die nachstehend aufgeführten Rollen zuweisen. Standardmäßig werden zuerst die Rollen angezeigt, die von den meisten Organisationen verwendet werden. Wenn Sie eine Rolle nicht finden können, gehen Sie zum Ende der Liste, und wählen Sie **Weitere Rollen anzeigen** aus. (Ausführliche Informationen, einschließlich der mit einer Rolle verknüpften Cmdlets, finden Sie unter [Administratorrollenberechtigungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).)

|Administratorrolle     |Wem sollte diese Rolle zugewiesen werden?  |
|---------|---------|
|Exchange-Administrator     |   Weisen Sie die Exchange-Administratorrolle Benutzern zu, die die E-Mail-Postfächer Ihrer Benutzer, Microsoft 365-Gruppen und Exchange Online einsehen und verwalten müssen. <br><br> Exchange-Administratoren sind außerdem zu Folgendem berechtigt:<br> - Wiederherstellen gelöschter Elemente im Postfach eines Benutzers <br> - Einrichten von "Senden als"- und "Senden im Auftrag von"-Stellvertretungen <br>  |
|Globaler Administrator     |   Weisen Sie Benutzern, die globalen Zugriff auf die meisten Verwaltungsfunktionen und Daten in Microsoft Online-Diensten benötigen, die Rolle des globalen Administrators zu. <br><br> Wenn Sie zu vielen Benutzern globalen Zugriff gewähren, besteht ein Sicherheitsrisiko, deshalb empfiehlt es sich, nur zwei bis vier globale Administratoren vorzusehen. <br><br> Nur globale Administratoren sind zu Folgendem berechtigt:<br> - Zurücksetzen von Kennwörtern für alle Benutzer <br> - Hinzufügen und Verwalten von Domänen <br> <br> **Hinweis:** Die Person, die die Registrierung für Microsoft-Onlinedienste vorgenommen hat, wird automatisch zu einem globalen Administrator. |
|Globaler Leser    |   Weisen Sie die Rolle "Globaler Leser" Benutzern zu, die Administratorfunktionen und -einstellungen in Admin Centern einsehen müssen, die der globale Administrator anzeigen kann. Ein Administrator mit der Rolle "Globaler Leser" kann keine Einstellungen bearbeiten.   |
|Gruppenadministrator     |   Weisen Sie die Rolle des Gruppenadministrators Benutzern zu, die alle Gruppeneinstellungen in den Admin Centern verwalten müssen, einschließlich des Microsoft 365 Admin Centers und des Azure Active Directory-Portals. <br><br> Gruppenadministratoren sind zu Folgendem berechtigt:<br> - Erstellen, Bearbeiten, Löschen und Wiederherstellen von Microsoft 365-Gruppen <br> - Einrichten und Aktualisieren von Erstellung, Ablauf und Benennungsrichtlinien von bzw. für Gruppen <br> - Erstellen, Bearbeiten, Löschen und Wiederherstellen von Azure Active Directory-Sicherheitsgruppen| 
|Helpdesk-Administrator     |   Weisen Sie die Rolle des Helpdesk-Administrators Benutzern zu, die folgende Aktionen ausführen müssen:<br> - Kennwörter zurücksetzen <br> - Die Abmeldung von Benutzern erzwingen <br> - Serviceanfragen verwalten <br> - Den Dienststatus überwachen <br> <br> **Hinweis**: Der Helpdesk-Administrator kann nur Benutzern ohne Administratorrolle sowie Benutzern helfen, welchen folgende Rollen zugewiesen wurden: Verzeichnisleseberechtigter, Gasteinladender, Helpdesk-Administrator, Nachrichtencenter-Leseberechtigter und Berichtleseberechtigter.      |
|Office-Apps-Administrator    |   Weisen Sie die Rolle des Office-Apps-Administrators Benutzern zu, die folgende Aktionen ausführen müssen: <br> - Verwenden des Office-Cloudrichtliniendiensts zum Erstellen und Verwalten von cloudbasierten Richtlinien für Office <br> - Serviceanfragen erstellen und verwalten <br> - Verwalten der Inhalte im Dialogfenster "Neuigkeiten", das den Benutzern in ihren Office-Apps angezeigt wird   <br> - Den Dienststatus überwachen  |
|Dienstadministrator    |   Weisen Sie die Rolle des Dienstadministrators als zusätzliche Rolle Administratoren oder Benutzern zu, die Berechtigungen für folgende, von ihren Rollen nicht vorgesehene Aktionen benötigen: <br> - Serviceanfragen öffnen und verwalten <br> - Nachrichtencenter-Beiträge anzeigen und freigeben   |
|SharePoint-Administrator    |   Weisen Sie die SharePoint-Administratorrolle Benutzern zu, die auf das SharePoint Online Admin Center zugreifen und dieses verwalten müssen. <br><br>SharePoint-Administratoren sind zudem zu Folgendem berechtigt: <br> - Erstellen und Löschen von Websites <br> - Verwalten von Websitesammlungen und globalen SharePoint-Einstellungen   |
|Teams-Dienstadministrator    |   Weisen Sie die Teams-Dienstadministratorrolle Benutzern zu, die auf das Teams Admin Center zugreifen und es verwalten müssen. <br><br>Teams-Dienstadministratoren können auch folgende Aktionen ausführen: <br> - Verwalten von Besprechungen <br> - Verwalten von Konferenzbrücken <br> - Verwalten aller organisationsweiten Einstellungen einschließlich Partnerverbund, Microsoft Teams-Upgrades und Einstellungen des Microsoft Teams-Clients   |
|Benutzeradministrator     |    Weisen Sie die Rolle des Benutzeradministrators Benutzern zu, die folgende Aktionen für alle Benutzer ausführen müssen: <br> - Benutzer und Gruppen hinzufügen <br> - Lizenzen zuweisen <br> - Die meisten Benutzereigenschaften verwalten <br> - Benutzeransichten erstellen und verwalten <br> - Kennwortablaufrichtlinien aktualisieren <br> - Serviceanfragen verwalten <br> - Den Dienststatus überwachen <br><br>  Der Benutzeradministrator kann außerdem die unten aufgeführten Aktionen für Benutzer ohne Administratorrolle sowie für Benutzer ausführen, denen die folgenden Rollen zugewiesen sind: Verzeichnisleseberechtigter, Gasteinladender, Helpdesk-Administrator, Nachrichtencenter-Leseberechtigter und Berichtleseberechtigter. <br> - Benutzernamen verwalten<br> - Benutzerkonten löschen und wiederherstellen<br> - Kennwörter zurücksetzen <br> - Die Abmeldung von Benutzern erzwingen <br> - (FIDO)-Geräteschlüssel aktualisieren   |

### <a name="all-azure-ad-roles"></a>Alle Azure AD-Rollen

 Hier ist eine Liste aller im Microsoft 365 Admin Center verfügbaren Administratorrollen.

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

## <a name="microsoft-intune-roles-available-in-the-microsoft-365-admin-center"></a>Im Microsoft 365 Admin Center verfügbare Microsoft Intune-Rollen

|Administratorrolle     |Wem sollte diese Rolle zugewiesen werden?  |
|---------|---------|
|Anwendungsmanager     |   Weisen Sie die Rolle des Anwendungsmanagers Benutzern zu, die den Anwendungs-Lebenszyklus für mobile Anwendungen verwalten, richtlinienverwaltete Anwendungen konfigurieren und Geräteinformationen und Konfigurationsprofile anzeigen.  |
|Helpdesk-Operator     |   Weisen Sie die Helpdesk-Operator-Rolle den Benutzern zu, die Benutzern und Geräten Anwendungen und Richtlinien zuweisen. |
|Intune-Rollenadministrator    |   Weisen Sie den Intune-Rollenadministrator Benutzern zu, die anderen Administratoren Intune-Berechtigungen zuweisen und benutzerdefinierte und eingebaute Intune-Rollen verwalten können.   |
|Richtlinien- und Profilmanager     |   Weisen Sie die Rolle des Richtlinien- und Profilmanagers den Benutzern zu, die Konformitätsrichtlinien, Konfigurationsprofile und Registrierung bei Apple verwalten.   |
|Operator für „Schreibgeschützt“     |   Weisen Sie Benutzern, die nur Benutzer, Geräte, Anmeldedetails und Konfigurationen anzeigen können, die Rolle des Operators für „Schreibgeschützt“ zu.   |
|Schuladministrator     |   Weisen Sie den Benutzern die Rolle des Schuladministrators zu, damit sie vollen Zugriff auf die Verwaltung von Windows 10 und iOS-Geräten, Anwendungen und Konfigurationen in Intune for Education haben.   |

## <a name="delegated-administration-for-microsoft-partners"></a>Delegierte Administration für Microsoft-Partner

Wenn Sie mit einem Microsoft-Partner arbeiten, können Sie den entsprechenden Personen Administratorrollen zuweisen. Diese können wiederum Benutzern in Ihrem (oder deren) Unternehmen Administratorrollen zuweisen. Dies kann beispielsweise sinnvoll sein, wenn diese Personen Ihre Online-Organisation für Sie einrichten und verwalten.
  
Ein Partner kann die folgenden Rollen zuweisen: 
  
- Vollständige Verwaltung mit Berechtigungen, die jenen eines globalen Administrators entsprechen, mit der Ausnahme, dass die mehrstufige Authentifizierung über das Partner Center verwaltet wird.
    
- Eingeschränkte Verwaltung mit Berechtigungen, die jenen eines Helpdesk-Administrators entsprechen.

Bevor der Partner diese Rollen Benutzern zuweisen kann, müssen Sie ihn als delegierten Administrator zu Ihrem Konto hinzufügen. Dieser Vorgang wird von einem autorisierten Partner initiiert. Der Partner fragt Sie in einer E-Mail-Nachricht, ob Sie ihm die Berechtigung erteilen möchten, als delegierter Administrator zu fungieren. Weitere Informationen hierzu finden Sie unter [Autorisieren oder Entfernen von Partnerbeziehungen](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner).
  
## <a name="related-articles"></a>Verwandte Artikel

[Zuweisen von Administratorrollen](assign-admin-roles.md)
  
[Teams-Aktivitätsberichte im Microsoft 365 Admin Center](../activity-reports/activity-reports.md)
