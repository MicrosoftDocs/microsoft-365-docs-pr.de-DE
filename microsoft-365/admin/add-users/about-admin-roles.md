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
description: Administratorrollen sind Geschäftsfunktionen zugeordnet. Über sie werden Berechtigungen für bestimmte Aufgaben im Admin Center erteilt. So kann beispielsweise der Dienstadministrator Supporttickets über das Admin Center öffnen.
ms.openlocfilehash: ddea8a06af2b529a369ea045913b639b84c6f9d4
ms.sourcegitcommit: c1f9a1b2a34146c51c9e33c4119a388b249ce7a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "49867982"
---
# <a name="about-admin-roles"></a>Info zu Administratorrollen

Das Microsoft 365- oder Office 365-Abonnement bietet eine Reihe von Administratorrollen, die Sie Benutzern in Ihrer Organisation mithilfe von Microsoft 365 Admin Center zuweisen können. Jede Administratorrolle ist häufig genutzten Geschäftsfunktionen zugeordnet. Über diese Rollen erhalten Personen in Ihrer Organisation die Berechtigung zum Ausführen bestimmter Aufgaben in den Admin Centern.

Im Microsoft 365 Admin Center können Sie Azure AD-Rollen und Microsoft Intune-Rollen verwalten. Bei diesen Rollen handelt es sich jedoch um eine Teilmenge der Rollen, die im Azure AD-Portal und im Intune Admin Center verfügbar sind.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Suchen Sie nach der vollständigen Liste der detaillierten Azure AD-Rollenbeschreibungen, die Sie im Microsoft 365 Admin Center verwalten können? Diese finden Sie unter "Administratorrollenberechtigungen in Azure Active Directory". [Administratorrollenberechtigungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).

Suchen Sie nach der vollständigen Liste der detaillierten Intune-Rollenbeschreibungen, die Sie im Microsoft 365 Admin Center verwalten können?  Siehe [Rollenbasierte Zugriffssteuerung (RBAC) mit Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control).

Weitere Informationen zum Zuweisen von Rollen im Microsoft 365 Admin Center finden Sie unter [Zuweisen von Administratorrollen](assign-admin-roles.md).

### <a name="watch-what-is-an-admin"></a>Schauen Sie sich an: Was ist ein Administrator?

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1SRc0]

## <a name="security-guidelines-for-assigning-roles"></a>Sicherheitsrichtlinien für das Zuweisen von Rollen

Da Administratoren Zugriff auf vertrauliche Daten und Dateien haben, empfiehlt es sich, diese Richtlinien zu befolgen, um die Daten Ihrer Organisation besser zu schützen.

| Empfehlung                  | Warum ist das wichtig?                 |
| :------------------- | :------------------- |
| 2 bis 4 globale Administratoren vorsehen  | Da nur ein anderer globaler Administrator das Kennwort eines globalen Administrators zurücksetzen kann, empfiehlt es sich, in Ihrer Organisation mindestens zwei globale Administratoren vorzusehen für den Fall, dass es zu einer Kontosperre kommt. Ein globaler Administrator hat jedoch fast unbegrenzten Zugriff auf die Einstellungen Ihrer Organisation und die meisten Daten. Daher wird empfohlen, nicht mehr als vier globale Administratoren einzurichten, da dies ein Sicherheitsrisiko darstellt. |
| Die Rolle *mit den wenigsten Berechtigungen* zuweisen    | Die Rolle *mit den wenigsten Berechtigungen* zuweisen bedeutet, Administratoren nur den Zugriff zu gewähren, den sie zum Erledigen einer Aufgabe benötigen. Wenn Sie beispielsweise möchten, dass jemand Mitarbeiterkennwörter zurücksetzen kann, sollten Sie ihm nicht die unbegrenzte Rolle des globalen Administrators zuweisen, sondern eine Rolle mit eingeschränkten Befugnissen wie jene des Kennwortadministrators oder des Helpdesk-Administrators. Dies trägt dazu bei, Ihre Daten zu schützen.                 |
| Mehrstufige Authentifizierung vorschreiben                  |    Es ist zwar sinnvoll, die mehrstufige Authentifizierung für alle Benutzer vorzuschreiben, für Administratoren sollte sie jedoch unbedingt zur Anmeldung vorgesehen sein. Bei der mehrstufigen Authentifizierung müssen Benutzer eine zweite Identifikationsmethode eingeben, um sicherzustellen, dass sie tatsächlich die Person sind, die sie behaupten zu sein. Administratoren können auf eine Vielzahl von Kunden- und Mitarbeiterdaten zugreifen. Wenn Sie die mehrstufige Authentifizierung vorschreiben, ist ein kompromittiertes Administratorkennwort ohne die zweite Art der Identifizierung nutzlos.  <br><br>Wenn Sie die mehrstufige Authentifizierung aktivieren, müssen die Benutzer bei der nächsten Anmeldung eine alternative E-Mail-Adresse und Telefonnummer für die Kontowiederherstellung angeben.  <br> [Einrichten der mehrstufigen Authentifizierung](../security-and-compliance/set-up-multi-factor-authentication.md)          |

Wenn im Admin Center eine Nachricht angezeigt wird, die besagt, dass Sie nicht über die Berechtigungen zum Bearbeiten einer Einstellung oder Seite verfügen, liegt dies daran, dass Ihnen eine Rolle zugewiesen ist, die nicht über die entsprechende Berechtigung verfügt.

## <a name="commonly-used-microsoft-365-admin-center-roles"></a>Häufig verwendete Microsoft 365 Admin Center-Rollen

::: moniker range="o365-worldwide"

Im Microsoft 365 Admin Center können Sie zu **Rollen** wechseln und dann eine beliebige Rolle auswählen, um den entsprechenden Detailbereich zu öffnen. Wählen Sie die Registerkarte **Berechtigungen** aus, um eine detaillierte Liste der Berechtigungen anzuzeigen, über die Administratoren mit dieser Rolle verfügen. Wählen Sie die Registerkarte **Zugewiesene** oder **Zugewiesene Administratoren** aus, um Benutzer zu Rollen hinzuzufügen.

::: moniker-end

Es genügt wahrscheinlich, wenn Sie in Ihrer Organisation nur die nachstehend aufgeführten Rollen zuweisen. Standardmäßig werden zuerst die Rollen angezeigt, die von den meisten Organisationen verwendet werden. Wenn Sie eine Rolle nicht finden können, gehen Sie zum Ende der Liste, und wählen Sie **Alle nach Kategorie anzeigen** aus. (Ausführliche Informationen, einschließlich der mit einer Rolle verknüpften Cmdlets, finden Sie unter [Administratorrollenberechtigungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).)

|Administratorrolle     |Wem sollte diese Rolle zugewiesen werden?  |
|---------|---------|
|Exchange-Administrator     |   Weisen Sie die Exchange-Administratorrolle Benutzern zu, die die E-Mail-Postfächer Ihrer Benutzer, Microsoft 365-Gruppen und Exchange Online einsehen und verwalten müssen. <br><br> Exchange-Administratoren sind außerdem zu Folgendem berechtigt:<br> - Wiederherstellen gelöschter Elemente im Postfach eines Benutzers <br> - Einrichten von "Senden als"- und "Senden im Auftrag von"-Stellvertretungen <br>  |
|Globaler Administrator     |   Weisen Sie Benutzern, die globalen Zugriff auf die meisten Verwaltungsfunktionen und Daten in Microsoft Online-Diensten benötigen, die Rolle des globalen Administrators zu. <br><br> Wenn Sie zu vielen Benutzern globalen Zugriff gewähren, besteht ein Sicherheitsrisiko, deshalb empfiehlt es sich, nur zwei bis vier globale Administratoren vorzusehen. <br><br> Nur globale Administratoren sind zu Folgendem berechtigt:<br> - Zurücksetzen von Kennwörtern für alle Benutzer <br> - Hinzufügen und Verwalten von Domänen <br> <br> **Hinweis:** Die Person, die die Registrierung für Microsoft-Onlinedienste vorgenommen hat, wird automatisch zu einem globalen Administrator. |
|Globaler Leser    |   Weisen Sie die Rolle "Globaler Leser" Benutzern zu, die Administratorfunktionen und -einstellungen in Admin Centern einsehen müssen, die der globale Administrator anzeigen kann. Ein Administrator mit der Rolle "Globaler Leser" kann keine Einstellungen bearbeiten.   |
|Gruppenadministrator     |   Weisen Sie die Rolle des Gruppenadministrators Benutzern zu, die alle Gruppeneinstellungen in den Admin Centern verwalten müssen, einschließlich des Microsoft 365 Admin Centers und des Azure Active Directory-Portals. <br><br> Gruppenadministratoren sind zu Folgendem berechtigt:<br> - Erstellen, Bearbeiten, Löschen und Wiederherstellen von Microsoft 365-Gruppen <br> - Einrichten und Aktualisieren von Erstellung, Ablauf und Benennungsrichtlinien von bzw. für Gruppen <br> - Erstellen, Bearbeiten, Löschen und Wiederherstellen von Azure Active Directory-Sicherheitsgruppen| 
|Helpdesk-Administrator     |   Weisen Sie die Rolle des Helpdesk-Administrators Benutzern zu, die folgende Aktionen ausführen müssen:<br> - Kennwörter zurücksetzen <br> - Die Abmeldung von Benutzern erzwingen <br> - Serviceanfragen verwalten <br> - Den Dienststatus überwachen <br> <br> **Hinweis**: Der Helpdesk-Administrator kann nur Benutzern ohne Administratorrolle sowie Benutzern helfen, welchen folgende Rollen zugewiesen wurden: Verzeichnisleseberechtigter, Gasteinladender, Helpdesk-Administrator, Nachrichtencenter-Leseberechtigter und Berichtleseberechtigter.      |
|Office-Apps-Administrator    |   Weisen Sie die Rolle des Office-Apps-Administrators Benutzern zu, die folgende Aktionen ausführen müssen: <br> - Verwenden des Office-Cloudrichtliniendiensts zum Erstellen und Verwalten von cloudbasierten Richtlinien für Office <br> - Serviceanfragen erstellen und verwalten <br> - Verwalten der Inhalte im Dialogfenster "Neuigkeiten", das den Benutzern in ihren Office-Apps angezeigt wird   <br> - Den Dienststatus überwachen  |
|Dienstsupportadministrator   |   Weisen Sie die Rolle des Dienstsupportadministrators als zusätzliche Rolle Administratoren oder Benutzern zu, die Berechtigungen für folgende, von ihren Rollen nicht vorgesehene Aktionen benötigen: <br> - Serviceanfragen öffnen und verwalten <br> - Nachrichtencenter-Beiträge anzeigen und freigeben   |
|SharePoint-Administrator    |   Weisen Sie die SharePoint-Administratorrolle Benutzern zu, die auf das SharePoint Online Admin Center zugreifen und dieses verwalten müssen. <br><br>SharePoint-Administratoren sind zudem zu Folgendem berechtigt: <br> - Erstellen und Löschen von Websites <br> - Verwalten von Websitesammlungen und globalen SharePoint-Einstellungen   |
|Teams-Dienstadministrator    |   Weisen Sie die Teams-Dienstadministratorrolle Benutzern zu, die auf das Teams Admin Center zugreifen und es verwalten müssen. <br><br>Teams-Dienstadministratoren können auch folgende Aktionen ausführen: <br> - Verwalten von Besprechungen <br> - Verwalten von Konferenzbrücken <br> - Verwalten aller organisationsweiten Einstellungen einschließlich Partnerverbund, Microsoft Teams-Upgrades und Einstellungen des Microsoft Teams-Clients   |
|Benutzeradministrator     |    Weisen Sie die Rolle des Benutzeradministrators Benutzern zu, die folgende Aktionen für alle Benutzer ausführen müssen: <br> - Benutzer und Gruppen hinzufügen <br> - Lizenzen zuweisen <br> - Die meisten Benutzereigenschaften verwalten <br> - Benutzeransichten erstellen und verwalten <br> - Kennwortablaufrichtlinien aktualisieren <br> - Serviceanfragen verwalten <br> - Den Dienststatus überwachen <br><br>  Der Benutzeradministrator kann außerdem die unten aufgeführten Aktionen für Benutzer ohne Administratorrolle sowie für Benutzer ausführen, denen die folgenden Rollen zugewiesen sind: Verzeichnisleseberechtigter, Gasteinladender, Helpdesk-Administrator, Nachrichtencenter-Leseberechtigter und Berichtleseberechtigter. <br> - Benutzernamen verwalten<br> - Benutzerkonten löschen und wiederherstellen<br> - Kennwörter zurücksetzen <br> - Die Abmeldung von Benutzern erzwingen <br> - (FIDO)-Geräteschlüssel aktualisieren   |

## <a name="delegated-administration-for-microsoft-partners"></a>Delegierte Administration für Microsoft-Partner

Wenn Sie mit einem Microsoft-Partner arbeiten, können Sie den entsprechenden Personen Administratorrollen zuweisen. Diese können wiederum Benutzern in Ihrem (oder deren) Unternehmen Administratorrollen zuweisen. Dies kann beispielsweise sinnvoll sein, wenn diese Personen Ihre Online-Organisation für Sie einrichten und verwalten.
  
Ein Partner kann die folgenden Rollen zuweisen: 
  
- **Administrator-Agent**: Berechtigungen, die jenen eines globalen Administrators entsprechen, mit der Ausnahme, dass die mehrstufige Authentifizierung über das Partner Center verwaltet wird.

- **Helpdesk-Agent**: Berechtigungen, die jenen eines Helpdesk-Administrators entsprechen.

Bevor der Partner diese Rollen Benutzern zuweisen kann, müssen Sie ihn als delegierten Administrator zu Ihrem Konto hinzufügen. Dieser Vorgang wird von einem autorisierten Partner initiiert. Der Partner fragt Sie in einer E-Mail-Nachricht, ob Sie ihm die Berechtigung erteilen möchten, als delegierter Administrator zu fungieren. Weitere Informationen hierzu finden Sie unter [Autorisieren oder Entfernen von Partnerbeziehungen](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner).
  
## <a name="related-articles"></a>Verwandte Artikel

[Zuweisen von Administratorrollen](assign-admin-roles.md)

[Azure AD-Rollen im Microsoft 365 Admin Center](azure-ad-roles-in-the-mac.md)

[Exchange Online-Administratorrolle](about-exchange-online-admin-role.md)
  
[Teams-Aktivitätsberichte im Microsoft 365 Admin Center](../activity-reports/activity-reports.md)
