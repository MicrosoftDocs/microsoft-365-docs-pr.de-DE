---
title: Steuern des Zugriffs in Microsoft 365-Gruppen,-Teams und-SharePoint
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Informationen zum Steuern des Zugriffs in Microsoft 365-Gruppen, Teams und SharePoint.
ms.openlocfilehash: fb1bec219ef0d27c2a908f5f385185a1a70e01e1
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613466"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a>Steuern des Zugriffs in Microsoft 365-Gruppen,-Teams und-SharePoint

Es gibt zahlreiche Steuerelemente, mit denen Sie steuern können, wie Personen auf Ressourcen in Gruppen, Teams und SharePoint zugreifen. Überprüfen Sie diese Optionen, und überprüfen Sie, wie Sie Ihre geschäftlichen Anforderungen, die Vertraulichkeit Ihrer Daten und den Umfang der Personen abbilden, mit denen Ihre Benutzer zusammenarbeiten müssen.

Die folgende Tabelle enthält eine Kurzübersicht über die in Microsoft 365 verfügbaren Zugriffssteuerelemente. Weitere Informationen finden Sie in den folgenden Abschnitten.

|Kategorie|Beschreibung|Referenz|
|:-------|:----------|:--------|
|Mitgliedschaft|||
||Ermittlung privater Teams|[Verwalten der Ermittlung von privaten Teams in Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)|
||Dynamische Gruppenmitgliedschaft basierend auf Regeln|[Erstellen oder Aktualisieren einer dynamischen Gruppe in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)|
||Steuern, wer Dateien, Ordner und Websites freigeben kann.|[Einrichten und Verwalten der Funktion „Zugriffsanforderungen“](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|Bedingter Zugriff|||
||Mehrstufige Authentifizierung|[Azure AD Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)|
||Steuern des Gerätezugriffs basierend auf Gruppen-, Team-oder Standort Sensitivität.|[Vertraulichkeitsbezeichnungen zum Schutz von Inhalten in Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites verwenden](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Einschränken des Websitezugriffs für nicht verwaltete Geräte.|[Steuern des SharePoint-Zugriffs von nicht verwalteten Geräten](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)|
||Steuern des Websitezugriffs basierend auf dem Standort|[Steuern des Zugriffs auf SharePoint- und OneDrive-Daten anhand der Netzwerkadresse](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)|
|Gastzugriff|||
||Zulassen oder Blockieren der SharePoint-Freigabe aus bestimmten Domänen.|[Einschränken der Freigabe von SharePoint- und OneDrive-Inhalten nach Domäne](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)|
||Zulassen oder Blockieren von Team-oder Gruppenmitgliedschaften in bestimmten Domänen|[Zulassen oder Blockieren von Einladungen an B2B-Benutzer aus bestimmten Organisationen](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
||Anonyme Freigabe verhindern.|[Deaktivieren von "Jeder"-Links](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)|
||Steuern der Berechtigungen für anonyme Zugriffs Links.|[Festlegen von Link Berechtigungen für alle Links](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)|
||Steuern des Ablaufs anonymer Freigabelinks.|[Festlegen eines Ablaufdatums für Jeder-Links](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)|
||Steuern Sie den Typ des Freigabelinks, der standardmäßig Benutzern angezeigt wird.|[Ändern des Standardlinktyps für eine Site](https://docs.microsoft.com/sharepoint/change-default-sharing-link)|
||Beschränken Sie die externe Freigabe auf bestimmte Personen.|[Einschränken der externen Freigabe auf angegebene Sicherheitsgruppen](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||Steuern des Gastzugriffs auf eine Gruppe, ein Team oder eine Website basierend auf der Informations Empfindlichkeit.|[Vertraulichkeitsbezeichnungen zum Schutz von Inhalten in Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites verwenden](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Deaktivieren Sie die Freigabeoptionen.|[Einschränken der Freigabe in Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)|
|Benutzerverwaltung|||
||Überprüfen Sie die Team-und Gruppenmitgliedschaft regelmäßig.|[Was sind Azure AD Zugriffsüberprüfungen?](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)|
||Automatisieren Sie die Zugriffsverwaltung für Gruppen und Teams.|[Was ist Azure AD Berechtigungsverwaltung?](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)|
||Zulassen oder blockieren, dass Personen private Kanäle in Microsoft Teams erstellen.|[Verwalten des Lebenszyklus privater Kanäle in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a>Mitgliedschaft

Die Mitgliedschaft von Teams und Gruppen wird von den Besitzern gesteuert. Mitglieder können andere Personen einladen, die Einladungen werden jedoch zur Genehmigung an die Besitzer gesendet. Während öffentliche Teams und Gruppen von beliebigen Personen in der Organisation erkannt werden, können Sie steuern, ob private Teams und Gruppen auffindbar sind:

- [Verwalten der Ermittlung von privaten Teams in Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)

Sie können die Mitgliedschaft einer Gruppe oder eines Teams dynamisch basierend auf einigen Kriterien wie Abteilung verwalten. In diesem Fall können Mitglieder und Besitzer keine Personen zum Team einladen.

- [Erstellen oder Aktualisieren einer dynamischen Gruppe in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

SharePoint-Websites bieten die Möglichkeit, Besitzer, Mitglieder und Besucher außer der Gruppen-oder Teammitgliedschaft hinzuzufügen. Je nach Ihren Anforderungen können Sie einschränken, wer Personen zur Website einladen kann. In Abhängigkeit von der Vertraulichkeit der Informationen in einer bestimmten Website können Sie auch einschränken, wer Dateien und Ordner freigeben kann. Diese Einschränkungen werden vom Team, der Gruppe oder dem Websitebesitzer konfiguriert:

- [Einrichten und Verwalten der Funktion „Zugriffsanforderungen“](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a>Bedingter Zugriff

Mit Microsoft 365 können Sie die mehrstufige Authentifizierung für Personen innerhalb und außerhalb Ihrer Organisation benötigen. Es gibt viele Optionen für die Umstände, wenn Personen zur Eingabe eines zweiten Authentifizierungsfaktors aufgefordert werden. Es wird dringend empfohlen, die mehrstufige Authentifizierung für Ihre Organisation bereitzustellen:

- [Azure AD Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)

Wenn Sie in einigen ihrer Gruppen und Teams vertrauliche Informationen haben, können Sie Richtlinien für die Geräteverwaltung basierend auf der Vertraulichkeits Bezeichnung einer Gruppe oder eines Teams erzwingen. Sie können den Zugriff vollständig von nicht verwalteten Geräten blockieren oder nur eingeschränkten Zugriff auf die Webanwendung gewähren:

- [Vertraulichkeitsbezeichnungen zum Schutz von Inhalten in Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites verwenden](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

In SharePoint können Sie den Zugriff auf Websites von bestimmten Netzwerkstandorten einschränken.

- [Steuern des Zugriffs auf SharePoint- und OneDrive-Daten anhand der Netzwerkadresse](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)


Zusätzliche Ressourcen:

- [Planen einer Bereitstellung für bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)

- [Übersicht über Microsoft InTune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

- [Steuern des SharePoint-Zugriffs von nicht verwalteten Geräten](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a>Gastzugriff

Sie können Gäste basierend auf der Domäne Ihrer e-Mail-Adresse einschränken. SharePoint bietet organisationsweite und standortspezifische Domänen Einschränkungseinstellungen. Gruppen und Teams verwenden die Listen der zugelassenen und verweigerten Domäne in Azure AD. Achten Sie darauf, beide Einstellungen zu konfigurieren, um unerwünschte Freigaben zu vermeiden und eine konsistente Benutzeroberfläche sicherzustellen:

- [Einschränken der Freigabe von SharePoint- und OneDrive-Inhalten nach Domäne](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)

- [Zulassen oder Blockieren von Einladungen an B2B-Benutzer aus bestimmten Organisationen](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)

Microsoft 365 ermöglicht die anonyme Freigabe von Dateien und Ordnern mithilfe von *beliebigen* Freigabelinks. *Alle* Links können weitergeleitet werden, und jeder, der über den Link verfügt, kann auf das freigegebene Element zugreifen. In Abhängigkeit von der Vertraulichkeit Ihrer Daten sollten Sie sich für die Verwendung von Links entscheiden, einschließlich der vollständigen Deaktivierung, der Beschränkung der Verknüpfungsberechtigungen auf schreibgeschützt oder der Festlegung eines Ablauf Zeitaufwands für diese *Personen* :

- [Deaktivieren von "Jeder"-Links](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)

- [Festlegen von Link Berechtigungen für alle Links](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)

- [Festlegen eines Ablaufdatums für Jeder-Links](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)

Bei der Freigabe von Dateien oder Ordnern stehen Benutzern mehrere Linktypen zur Auswahl. Um das Risiko einer versehentlichen unbeabsichtigten Freigabe zu verringern, können Sie den Standardverknüpfungstyp, der Benutzern bei der Freigabe angezeigt wird, ändern. Wenn Sie beispielsweise die Standardeinstellung für *alle* Links ändern, die den anonymen Zugriff für *Personen in Ihrer Organisation* ermöglichen, können Sie das Risiko einer unerwünschten externen Freigabe vertraulicher Informationen reduzieren:

- [Ändern des Standardlinktyps für eine Site](https://docs.microsoft.com/sharepoint/change-default-sharing-link)

Wenn Ihre Organisation über vertrauliche Daten verfügt, die Sie für die Gäste freigeben müssen, Sie jedoch über eine ungeeignete Freigabe besorgt sind, können Sie die externe Freigabe von Dateien und Ordnern auf die Mitglieder der angegebenen Sicherheitsgruppen beschränken. Auf diese Weise können Sie die Freigabe extern für eine bestimmte Gruppe von Personen einschränken oder festlegen, dass Ihre Benutzerschulungen für die entsprechende externe Freigabe durchführen müssen, bevor Sie Sie der Sicherheitsgruppe hinzufügen:

- [Einschränken der externen Freigabe auf angegebene Sicherheitsgruppen](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

Gruppen und Teams verfügen über eine Einstellung auf Organisationsebene, die den Gastzugriff zulässt oder ablehnt. Sie können zwar den [Gastzugriff auf bestimmte Teams oder Gruppen mithilfe von Microsoft PowerShell einschränken](per-group-guest-access.md), dies wird jedoch mithilfe einer Vertraulichkeits Bezeichnung empfohlen. Mit Sensitivitäts Bezeichnungen können Sie den Gastzugriff basierend auf der angewendeten Bezeichnung automatisch zulassen oder verweigern:

- [Vertraulichkeitsbezeichnungen zum Schutz von Inhalten in Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites verwenden](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

Microsoft 365 bietet viele verschiedene Methoden zum Freigeben von Informationen. Wenn Sie über vertrauliche Informationen verfügen und deren Freigabe einschränken möchten, überprüfen Sie die Optionen zum Einschränken der Freigabe:

- [Einschränken der Freigabe in Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)

Zusätzliche Ressourcen:

- [Sichere Zusammenarbeit mit Microsoft 365 einrichten](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

- [Bewährte Methoden zum Freigeben von Dateien und Ordnern für nicht authentifizierte Benutzer](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing)

- [Begrenzen der versehentlichen Gefährdung von Dateien bei der Freigabe für Personen außerhalb Ihrer Organisation](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)

- [Erstellen einer sicheren Gastfreigabeumgebung](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

- [Aktivieren der externen B2B-Zusammenarbeit und Verwalten von Personen, die Gäste einladen können](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a>Benutzerverwaltung

Wenn sich Gruppen und Teams in Ihrer Organisation entwickeln, empfiehlt es sich, die Team-und Gruppenmitgliedschaft regelmäßig zu überprüfen. Dies kann besonders nützlich sein, wenn Teams und Gruppen mit einer geänderten Mitgliedschaft, mit vertraulichen Informationen oder mit Gästen ausgestattet sind. Sie sollten Zugriffsüberprüfungen für diese Teams und Gruppen einrichten:

- [Was sind Azure AD Zugriffsüberprüfungen?](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

Viele Organisationen verfügen über Geschäftspartnerschaften mit anderen Organisationen oder wichtigen Anbietern, mit denen Sie eingehend zusammenarbeiten. Die Benutzerverwaltung und der Zugriff auf Ressourcen können in diesen Szenarien eine Herausforderung für die Verwaltung darstellen. Sie sollten einige Benutzerverwaltungsaufgaben automatisieren und sogar einige dieser Aufgaben in Ihre Partnerorganisation umleiten:

- [Was ist Azure AD Berechtigungsverwaltung?](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)

Private Kanäle in Microsoft Teams ermöglichen das bereichsbezogene Unterhaltungen und die Dateifreigabe zwischen einer Teilmenge der Teammitglieder. Je nach Ihren spezifischen geschäftlichen Anforderungen können Sie diese Funktion zulassen oder blockieren.

- [Private Kanäle in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels)

- [Verwalten des Lebenszyklus privater Kanäle in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)

Zusätzliche Ressourcen:

- [Azure Active Directory Identity Governance](https://docs.microsoft.com/azure/active-directory/governance)

## <a name="related-topics"></a>Verwandte Themen

[Planung der Collaboration-Steuerung Schritt für Schritt](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Erstellen eines Steuerungsplans für die Zusammenarbeit](collaboration-governance-first.md)

[Sicherheit und Compliance in Microsoft Teams](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

[Verwalten von Freigabeeinstellungen in SharePoint](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)

[Erstellen und Verwalten eines externen Netzwerks in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-an-external-network)

[Konfigurieren von Teams mit drei Schutzebenen](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
