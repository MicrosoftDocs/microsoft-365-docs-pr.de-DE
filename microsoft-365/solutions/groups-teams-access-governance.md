---
title: Regeln des Zugriffs in Microsoft 365-Gruppen, Teams und SharePoint
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
description: Erfahren Sie mehr über die Verwaltung des Zugriffs in Microsoft 365-Gruppen, Teams und SharePoint.
ms.openlocfilehash: 44b90e461c81875fa5ccf728c890d5eaebf7d613
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922280"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a>Regeln des Zugriffs in Microsoft 365-Gruppen, Teams und SharePoint

Es gibt viele Steuerelemente, mit denen Sie steuern können, wie Personen auf Ressourcen in Gruppen, Teams und SharePoint zugreifen. Überprüfen Sie diese Optionen, und überlegen Sie, wie sie Ihren Geschäftlichen Anforderungen, der Vertraulichkeit Ihrer Daten und dem Umfang der Personen entsprechen, mit der Ihre Benutzer zusammenarbeiten müssen.

Die folgende Tabelle enthält eine Kurzübersicht zu den in Microsoft 365 verfügbaren Zugriffssteuerelementen. Weitere Informationen finden Sie in den folgenden Abschnitten.

|Kategorie|Beschreibung|Referenz|
|:-------|:----------|:--------|
|Mitgliedschaft|||
||Ermittlung privater Teams|[Verwalten der Ermittlung privater Teams in Microsoft Teams](/microsoftteams/manage-discovery-of-private-teams)|
||Dynamische Gruppenmitgliedschaft basierend auf Regeln|[Erstellen oder Aktualisieren einer dynamischen Gruppe in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-create-rule)|
||Steuern, wer Dateien, Ordner und Websites freigeben kann.|[Einrichten und Verwalten der Funktion „Zugriffsanforderungen“](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|Bedingter Zugriff|||
||Mehrstufige Authentifizierung|[Azure AD Multi-Factor Authentication](/azure/active-directory/authentication/concept-mfa-howitworks)|
||Steuern des Gerätezugriffs basierend auf der Vertraulichkeit von Gruppen, Teams oder Website|[Vertraulichkeitsbezeichnungen zum Schutz von Inhalten in Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites verwenden](../compliance/sensitivity-labels-teams-groups-sites.md)|
||Einschränken des Websitezugriffs für nicht verwaltete Geräte.|[Steuern des SharePoint-Zugriffs von nicht verwalteten Geräten](/sharepoint/control-access-from-unmanaged-devices)|
||Steuern des Websitezugriffs basierend auf dem Standort|[Steuern des Zugriffs auf SharePoint- und OneDrive-Daten anhand der Netzwerkadresse](/sharepoint/control-access-based-on-network-location)|
|Gastzugriff|||
||Zulassen oder Blockieren der SharePoint-Freigabe von angegebenen Domänen.|[Einschränken der Freigabe von SharePoint- und OneDrive-Inhalten nach Domäne](/sharepoint/restricted-domains-sharing)|
||Zulassen oder Blockieren der Team- oder Gruppenmitgliedschaft von angegebenen Domänen.|[Zulassen oder Blockieren von Einladungen an B2B-Benutzer aus bestimmten Organisationen](/azure/active-directory/b2b/allow-deny-list)|
||Verhindern der anonymen Freigabe.|[Deaktivieren von "Jeder"-Links](./share-limit-accidental-exposure.md#turn-off-anyone-links)|
||Steuern der Berechtigungen für anonyme Zugriffslinks.|[Festlegen von Linkberechtigungen für Jeder-Links](./best-practices-anonymous-sharing.md#set-link-permissions)|
||Steuern des Ablaufs anonymer Freigabelinks.|[Festlegen eines Ablaufdatums für Jeder-Links](./best-practices-anonymous-sharing.md#set-an-expiration-date-for-anyone-links)|
||Steuern Sie den Typ des Freigabelinks, der Benutzern standardmäßig angezeigt wird.|[Ändern des Standardlinktyps für eine Site](/sharepoint/change-default-sharing-link)|
||Beschränken Sie die externe Freigabe auf bestimmte Personen.|[Beschränken der externen Freigabe auf angegebene Sicherheitsgruppen](./share-limit-accidental-exposure.md#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||Steuern des Gastzugriffs auf eine Gruppe, ein Team oder eine Website basierend auf der Informationssensitivität.|[Vertraulichkeitsbezeichnungen zum Schutz von Inhalten in Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites verwenden](../compliance/sensitivity-labels-teams-groups-sites.md)|
||Deaktivieren Sie Freigabeoptionen.|[Einschränken der Freigabe in Microsoft 365](./microsoft-365-limit-sharing.md)|
|Benutzerverwaltung|||
||Überprüfen Sie die Team- und Gruppenmitgliedschaft regelmäßig.|[Was sind Azure AD-Zugriffsüberprüfungen?](/azure/active-directory/governance/access-reviews-overview)|
||Automatisieren sie die Zugriffsverwaltung für Gruppen und Teams.|[Was ist Azure AD-Berechtigungsverwaltung?](/azure/active-directory/governance/entitlement-management-overview)|
||Zulassen oder Blockieren von Personen, private Kanäle in Teams zu erstellen.|[Verwalten des Lebenszyklus privater Kanäle in Microsoft Teams](/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a>Mitgliedschaft

Die Mitgliedschaft in Teams und Gruppen wird von Besitzern gesteuert. Mitglieder können andere Einladen, aber die Einladungen werden zur Genehmigung an besitzer gesendet. Während öffentliche Teams und Gruppen von allen Personen in der Organisation ermittelt werden können, können Sie steuern, ob private Teams und Gruppen ermittelt werden können:

- [Verwalten der Ermittlung privater Teams in Microsoft Teams](/microsoftteams/manage-discovery-of-private-teams)

Sie können die Mitgliedschaft in einer Gruppe oder einem Team dynamisch basierend auf einigen Kriterien verwalten, z. B. Abteilung. In diesem Fall können Mitglieder und Besitzer keine Personen zum Team einladen. Dynamische Gruppen verwenden Metadaten, die Sie in Azure Active Directory definieren, um zu steuern, wer Mitglied der Gruppe ist. Stellen Sie sicher, dass die von Ihnen verwendeten Metadaten vollständig und aktuell sind, da falsche Metadaten dazu führen können, dass Benutzer nicht in Gruppen oder falschen Benutzern hinzugefügt werden.

- [Erstellen oder Aktualisieren einer dynamischen Gruppe in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-create-rule)

SharePoint-Websites bieten die Möglichkeit, Besitzer, Mitglieder und Besucher zusätzlich zur Gruppen- oder Teammitgliedschaft hinzuzufügen. Je nach Ihren Anforderungen möchten Sie möglicherweise einschränken, wer Personen zur Website einladen kann. Je nach Vertraulichkeit der Informationen auf einer bestimmten Website können Sie auch einschränken, wer Dateien und Ordner freigeben kann. Diese Einschränkungen werden vom Team, der Gruppe oder dem Websitebesitzer konfiguriert:

- [Einrichten und Verwalten der Funktion „Zugriffsanforderungen“](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a>Bedingter Zugriff

Mit Microsoft 365 können Sie eine mehrstufige Authentifizierung für Personen innerhalb und außerhalb Ihrer Organisation benötigen. Es gibt viele Optionen für die Umstände, in denen Personen zur Eingabe eines zweiten Authentifizierungsfaktors aufgefordert werden. Es wird dringend empfohlen, dass Sie die mehrstufige Authentifizierung für Ihre Organisation bereitstellen:

- [Azure AD Multi-Factor Authentication](/azure/active-directory/authentication/concept-mfa-howitworks)

Wenn Sie über vertrauliche Informationen in einigen Ihrer Gruppen und Teams verfügen, können Sie Geräteverwaltungsrichtlinien basierend auf der Vertraulichkeitsbezeichnung einer Gruppe oder eines Teams erzwingen. Sie können den Zugriff vollständig von nicht verwalteten Geräten blockieren oder nur eingeschränkten Zugriff auf das Web zulassen:

- [Vertraulichkeitsbezeichnungen zum Schutz von Inhalten in Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites verwenden](../compliance/sensitivity-labels-teams-groups-sites.md)

In SharePoint können Sie den Zugriff auf Websites von angegebenen Netzwerkstandorten einschränken.

- [Steuern des Zugriffs auf SharePoint- und OneDrive-Daten anhand der Netzwerkadresse](/sharepoint/control-access-based-on-network-location)


Zusätzliche Ressourcen:

- [Planen einer Bereitstellung für bedingten Zugriff](/azure/active-directory/conditional-access/plan-conditional-access)

- [Übersicht über Microsoft Intune](/mem/intune/fundamentals/what-is-intune)

- [Steuern des SharePoint-Zugriffs von nicht verwalteten Geräten](/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a>Gastzugriff

Sie können Gäste basierend auf der Domäne ihrer E-Mail-Adresse einschränken. SharePoint bietet organisationsweite und websitespezifische Domäneneinschränkungseinstellungen. Gruppen und Teams verwenden die Listen "Domänen zulassen" und "Verweigern" in Azure AD. Konfigurieren Sie unbedingt beide Einstellungen, um unerwünschte Freigaben zu vermeiden und eine konsistente Benutzeroberfläche sicherzustellen:

- [Einschränken der Freigabe von SharePoint- und OneDrive-Inhalten nach Domäne](/sharepoint/restricted-domains-sharing)

- [Zulassen oder Blockieren von Einladungen an B2B-Benutzer aus bestimmten Organisationen](/azure/active-directory/b2b/allow-deny-list)

Microsoft 365 ermöglicht die anonyme Freigabe von Dateien und Ordnern mithilfe von *Jeder-Freigabelinks.* *Jeder* Link kann weitergeleitet werden, und jeder, der den Link verwendet, kann auf das freigegebene Element zugreifen. In Abhängigkeit von der Vertraulichkeit Ihrer Daten sollten Sie festlegen, wie *Jeder-Links* verwendet werden – einschließlich des vollständigen Deaktivierens, Einschränken von Linkberechtigungen auf schreibgeschützt oder Festlegen einer Ablaufzeit für sie:

- [Deaktivieren von "Jeder"-Links](./share-limit-accidental-exposure.md#turn-off-anyone-links)

- [Festlegen von Linkberechtigungen für Jeder-Links](./best-practices-anonymous-sharing.md#set-link-permissions)

- [Festlegen eines Ablaufdatums für Jeder-Links](./best-practices-anonymous-sharing.md#set-an-expiration-date-for-anyone-links)

Bei der Freigabe von Dateien oder Ordnern stehen Benutzern mehrere Linktypen zur Auswahl. Um das Risiko einer versehentlichen unangemessenen Freigabe zu verringern, können Sie den Standardlinktyp ändern, der Benutzern bei der Freigabe angezeigt wird. Wenn Sie beispielsweise die Standardeinstellung von *Jeder-Links* - die anonymen Zugriff zulassen - auf Personen *in* Ihren Organisationslinks ändern, kann das Risiko einer unerwünschten externen Freigabe vertraulicher Informationen reduziert werden:

- [Ändern des Standardlinktyps für eine Site](/sharepoint/change-default-sharing-link)

Wenn Ihre Organisation über vertrauliche Daten verfügt, die Sie für Gäste freigeben müssen, Sie jedoch bedenken, dass die Freigabe unangemessen ist, können Sie die externe Freigabe von Dateien und Ordnern auf die Mitglieder der angegebenen Sicherheitsgruppen beschränken. Auf diese Weise können Sie die externe Freigabe auf eine bestimmte Gruppe von Personen beschränken oder ihre Benutzer zur Schulung der entsprechenden externen Freigaben vor dem Hinzufügen zur Sicherheitsgruppe benötigen:

- [Beschränken der externen Freigabe auf angegebene Sicherheitsgruppen](./share-limit-accidental-exposure.md#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

Gruppen und Teams verfügen über Einstellungen auf Organisationsebene, die den Gastzugriff zulassen oder verweigern. Während Sie den Gastzugriff auf bestimmte Teams oder Gruppen mithilfe von [Microsoft PowerShell](per-group-guest-access.md)einschränken können, wird empfohlen, dies mithilfe einer Vertraulichkeitsbezeichnung zu tun. Mit Vertraulichkeitsbezeichnungen können Sie den Gastzugriff basierend auf der angewendeten Bezeichnung automatisch zulassen oder verweigern:

- [Vertraulichkeitsbezeichnungen zum Schutz von Inhalten in Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites verwenden](../compliance/sensitivity-labels-teams-groups-sites.md)

In einer Umgebung, in der Sie häufig Gäste zu Gruppen und Teams einladen, sollten Sie regelmäßig geplante Gastzugriffsüberprüfungen einrichten. Besitzer können aufgefordert werden, Gäste in ihren Gruppen und Teams zu überprüfen und den Zugriff zu genehmigen oder zu verweigern.

- [Einrichten von Gastzugriff-Überprüfungen](/microsoft-365/solutions/create-secure-guest-sharing-environment#set-up-guest-access-reviews)

Microsoft 365 bietet viele verschiedene Methoden zum Teilen von Informationen. Wenn Sie über vertrauliche Informationen verfügen und die Freigabe einschränken möchten, überprüfen Sie die Optionen zum Einschränken der Freigabe:

- [Einschränken der Freigabe in Microsoft 365](./microsoft-365-limit-sharing.md)

Zusätzliche Ressourcen:

- [Sichere Zusammenarbeit mit Microsoft 365 einrichten](./setup-secure-collaboration-with-teams.md)

- [Bewährte Methoden zum Freigeben von Dateien und Ordnern für nicht authentifizierte Benutzer](./best-practices-anonymous-sharing.md)

- [Begrenzen der versehentlichen Gefährdung von Dateien bei der Freigabe für Personen außerhalb Ihrer Organisation](./share-limit-accidental-exposure.md)

- [Erstellen einer sicheren Gastfreigabeumgebung](./create-secure-guest-sharing-environment.md)

- [Aktivieren der externen B2B-Zusammenarbeit und Verwalten, wer Gäste einladen kann](/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a>Benutzerverwaltung

Wenn sich Gruppen und Teams in Ihrer Organisation weiterentwickeln, ist es eine bewährte Methode, die Team- und Gruppenmitgliedschaft regelmäßig zu überprüfen. Dies kann besonders für Teams und Gruppen mit wechselnder Mitgliedschaft, für Solche mit vertraulichen Informationen oder für Gäste nützlich sein. Erwägen Sie das Einrichten von Zugriffsüberprüfungen für diese Teams und Gruppen:

- [Was sind Azure AD-Zugriffsüberprüfungen?](/azure/active-directory/governance/access-reviews-overview)

Viele Organisationen verfügen über Geschäftspartnerschaften mit anderen Organisationen oder wichtigen Anbietern, mit denen sie eng zusammenarbeiten. Die Benutzerverwaltung und der Zugriff auf Ressourcen können in diesen Szenarien schwierig sein. Erwägen Sie, einige der Benutzerverwaltungsaufgaben zu automatisieren und sogar einige von ihnen in Ihre Partnerorganisation zu überwechseln:

- [Was ist Azure AD-Berechtigungsverwaltung?](/azure/active-directory/governance/entitlement-management-overview)

Private Kanäle in Teams ermöglichen Bereichsunterhaltungen und Dateifreigabe zwischen einer Teilmenge von Teammitgliedern. Je nach Ihren spezifischen Geschäftsanforderungen können Sie diese Funktion zulassen oder blockieren.

- [Private Kanäle in Microsoft Teams](/MicrosoftTeams/private-channels)

- [Verwalten des Lebenszyklus privater Kanäle in Microsoft Teams](/MicrosoftTeams/private-channels-life-cycle-management)

Zusätzliche Ressourcen:

- [Azure Active Directory Identity Governance](/azure/active-directory/governance)

## <a name="related-topics"></a>Verwandte Themen

[Schritt-für-Schritt-Planung für die Zusammenarbeitsgovernance](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Erstellen eines Plans für die Zusammenarbeitsgovernance](collaboration-governance-first.md)

[Sicherheit und Compliance in Microsoft Teams](/microsoftteams/security-compliance-overview)

[Verwalten von Freigabeeinstellungen in SharePoint](/sharepoint/turn-external-sharing-on-or-off)

[Erstellen und Verwalten eines externen Netzwerks in Yammer](/yammer/work-with-external-users/create-and-manage-an-external-network)

[Konfigurieren von Teams mit drei Schutzebenen](./configure-teams-three-tiers-protection.md)