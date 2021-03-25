---
title: Empfohlene Teams-Richtlinien – Microsoft 365 for Enterprise | Microsoft Docs
description: Beschreibt die Richtlinien für Microsoft-Empfehlungen zum Sichern der Microsoft-Kommunikation und des Dateizugriffs.
author: MicrosoftHeidi
manager: serdars
ms.prod: m365-security
ms.topic: article
f1.keywords:
- NOCSH
ms.author: heidip
ms.date: 09/30/2020
ms.reviewer: anmorgan
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 51dec80c541cd77a1d4813505d82429487e8381c
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206434"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>Richtlinienempfehlungen zum Schützen von Teams-Chats, -Gruppen und -Dateien

In diesem Artikel wird beschrieben, wie Sie die empfohlenen Identitäts- und Gerätezugriffsrichtlinien implementieren, um Microsoft Teams-Chats, -Gruppen und -Inhalte wie Dateien und Kalender zu schützen. Diese Anleitung basiert auf den [allgemeinen Identitäts-](identity-access-policies.md)und Gerätezugriffsrichtlinien mit zusätzlichen Teams-spezifischen Informationen. Da Teams in unsere anderen Produkte integriert ist, finden Sie auch Richtlinienempfehlungen zum Sichern [von SharePoint-Websites](sharepoint-file-access-policies.md) und -Dateien sowie Richtlinienempfehlungen zum Schützen [von E-Mails.](secure-email-recommended-policies.md)

Diese Empfehlungen basieren auf drei verschiedenen Sicherheits- und Schutzebenen für Teams, die basierend auf der Granularität Ihrer Anforderungen angewendet werden können: Basisplan, vertraulich und streng reguliert. Weitere Informationen zu diesen Sicherheitsebenen und den empfohlenen Richtlinien, auf die in diesen Empfehlungen verwiesen wird, finden Sie unter [Identity and device access configurations](microsoft-365-policies-configurations.md).

In diesem Artikel sind weitere Empfehlungen für die Bereitstellung von Teams enthalten, um bestimmte Authentifizierungsanforderungen zu abdecken, auch für Benutzer außerhalb Ihrer Organisation. Sie müssen diese Anleitung befolgen, um eine vollständige Sicherheitserfahrung zu erhalten.

## <a name="getting-started-with-teams-before-other-dependent-services"></a>Erste Schritte mit Teams vor anderen abhängigen Diensten

Sie müssen keine abhängigen Dienste aktivieren, um mit Microsoft Teams zu beginnen. Diese Dienste funktionieren alle "nur". Sie müssen jedoch darauf vorbereitet sein, die folgenden dienstbezogenen Elemente zu verwalten:

- Microsoft 365-Gruppen
- SharePoint-Teamwebsites
- OneDrive for Business
- Exchange-Postfächer
- Streamen von Videos und Planner-Plänen (wenn diese Dienste aktiviert sind)

## <a name="updating-common-policies-to-include-teams"></a>Aktualisieren gängiger Richtlinien für Teams

Zum Schutz von Chats, Gruppen und Inhalten in Teams zeigt das folgende Diagramm, welche Richtlinien aus den allgemeinen Identitäts- und Gerätezugriffsrichtlinien aktualisiert werden. Stellen Sie sicher, dass teams und abhängige Dienste in die Zuweisung von Cloud-Apps einbezogen werden, damit jede Richtlinie aktualisiert werden kann.

[![Zusammenfassung der Richtlinienupdates zum Schutz des Zugriffs auf Teams und seine abhängigen Dienste](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

Diese Dienste sind die abhängigen Dienste, die bei der Zuweisung von Cloud-Apps für Teams enthalten sein müssen:

- Microsoft Teams
- Sharepoint und OneDrive for Business
- Exchange Online
- Skype for Business Online
- Microsoft Stream (Besprechungsaufzeichnungen)
- Microsoft Planner (Planner-Aufgaben und Plandaten)

In dieser Tabelle sind die Richtlinien aufgeführt, die erneut durchdacht werden müssen, und Links zu jeder Richtlinie in den allgemeinen Identitäts- und Gerätezugriffsrichtlinien [,](identity-access-policies.md)die den allgemeinen Richtliniensatz für alle Office-Anwendungen enthalten.

|Schutzebene|Richtlinien|Weitere Informationen zur Implementierung von Teams|
|---|---|---|
|**Basisplan**|[MFA erforderlich, wenn das Anmelderisiko *mittel oder* hoch *ist*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Stellen Sie sicher, dass Teams und abhängige Dienste in der Liste der Apps enthalten sind. Teams hat auch Gastzugriffs- und Externe Zugriffsregeln zu berücksichtigen. Weitere Informationen zu diesen Regeln finden Sie weiter später in diesem Artikel.|
||[Blockieren von Clients, die die moderne Authentifizierung nicht unterstützen](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Schließen Sie Teams und abhängige Dienste in die Zuweisung von Cloud-Apps ein.|
||[Nutzer mit hohem Risiko müssen das Kennwort ändern](identity-access-policies.md#high-risk-users-must-change-password)|Erzwingt Teams-Benutzer, ihr Kennwort bei der Anmeldung zu ändern, wenn für ihr Konto Aktivitäten mit hohem Risiko erkannt werden. Stellen Sie sicher, dass Teams und abhängige Dienste in der Liste der Apps enthalten sind.|
||[Anwenden von APP-Datenschutzrichtlinien](identity-access-policies.md#apply-app-data-protection-policies)|Stellen Sie sicher, dass Teams und abhängige Dienste in der Liste der Apps enthalten sind. Aktualisieren Sie die Richtlinie für jede Plattform (iOS, Android, Windows).|
||[Definieren von Richtlinien zur Gerätekonformität](identity-access-policies.md#define-device-compliance-policies)|Schließen Sie Teams und abhängige Dienste in diese Richtlinie ein.|
||[Kompatible PCs erforderlich](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Schließen Sie Teams und abhängige Dienste in diese Richtlinie ein.|
|**Vertraulich**|[MFA erforderlich, wenn das Anmelderisiko *niedrig,* *mittel oder* hoch *ist*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Teams hat auch Gastzugriffs- und Externe Zugriffsregeln zu berücksichtigen. Weitere Informationen zu diesen Regeln finden Sie weiter später in diesem Artikel. Schließen Sie Teams und abhängige Dienste in diese Richtlinie ein.|
||[Erfordern kompatibler PCs *und* mobiler Geräte](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Schließen Sie Teams und abhängige Dienste in diese Richtlinie ein.|
|**Streng geregelt**|[*MFA* immer erforderlich](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Unabhängig von der Benutzeridentität wird MFA von Ihrer Organisation verwendet. Schließen Sie Teams und abhängige Dienste in diese Richtlinie ein. |
|

## <a name="teams-dependent-services-architecture"></a>Architektur abhängiger Dienste von Teams

Als Referenz veranschaulicht das folgende Diagramm die Dienste, auf die Teams basiert. Weitere Informationen und Illustrationen finden Sie unter Microsoft Teams und zugehörige Produktivitätsdienste [in Microsoft 365 für IT-Architekten](../../solutions/productivity-illustrations.md).

[![Diagramm mit #A0 von SharePoint, OneDrive for Business und Exchange](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

[Eine größere Version dieses Bilds sehen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="guest-and-external-access-for-teams"></a>Gast- und externer Zugriff für Teams

Microsoft Teams definiert die folgenden Zugriffstypen:

- **Der Gastzugriff** verwendet ein Azure AD B2B-Konto für einen Gast oder externen Benutzer, das als Mitglied eines Teams hinzugefügt werden kann und über alle berechtigten Zugriffsrechte auf die Kommunikation und Ressourcen des Teams verfügt.

- **Der externe Zugriff** ist für einen externen Benutzer ohne Azure AD B2B-Konto. Der externe Zugriff kann Einladungen und die Teilnahme an Anrufen, Chats und Besprechungen umfassen, umfasst jedoch keine Teammitgliedschaft und keinen Zugriff auf die Ressourcen des Teams.

Richtlinien für bedingten Zugriff gelten nur für den Gastzugriff in Teams, da es ein entsprechendes Azure AD B2B-Konto gibt.

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both.

-->

Empfohlene Richtlinien zum Zulassen des Zugriffs für Gastbenutzer und externe Benutzer mit einem Azure AD B2B-Konto finden Sie unter Richtlinien zum Zulassen des Gast- und [externen B2B-Kontozugriffs.](identity-access-policies-guest-access.md)

### <a name="guest-access-in-teams"></a>Gastzugriff in Teams

Zusätzlich zu den Richtlinien für Benutzer, die in Ihrem Unternehmen oder Ihrer Organisation intern sind, können Administratoren Gastzugriff aktivieren, um Benutzern, die sich außerhalb Ihres Unternehmens oder Ihrer Organisation befinden, den Zugriff auf Teams-Ressourcen zu ermöglichen und mit internen Personen für Dinge wie Gruppenunterhaltungen, Chats und Besprechungen zu interagieren.

Weitere Informationen zum Gastzugriff und zur Implementierung finden Sie unter  [Teams guest access](/microsoftteams/guest-access).

### <a name="external-access-in-teams"></a>Externer Zugriff in Teams

Der externe Zugriff wird manchmal mit dem Gastzugriff verwechselt, daher ist es wichtig, klar zu sein, dass diese beiden nicht internen Zugriffsmechanismen unterschiedliche Arten von Zugriff sind.

Der externe Zugriff ist eine Möglichkeit für Teams-Benutzer aus einer gesamten externen Domäne, Besprechungen mit Ihren Benutzern in Teams zu finden, zu anrufen, zu chatten und zu richten. Teams-Administratoren konfigurieren den externen Zugriff auf Organisationsebene. Weitere Informationen finden Sie unter [Verwalten des externen Zugriffs in Microsoft Teams](/microsoftteams/manage-external-access).

Benutzer mit externem Zugriff haben weniger Zugriff und Funktionalität als eine Person, die über den Gastzugriff hinzugefügt wurde. Beispielsweise können Benutzer mit externem Zugriff mit Ihren internen Benutzern mit Teams chatten, aber nicht auf Teamkanäle, Dateien oder andere Ressourcen zugreifen.

Der externe Zugriff verwendet keine Azure AD B2B-Benutzerkonten und verwendet daher keine Richtlinien für bedingten Zugriff.

## <a name="teams-policies"></a>Teams-Richtlinien

Außerhalb der oben aufgeführten allgemeinen Richtlinien gibt es Teams-spezifische Richtlinien, die für die Verwaltung verschiedener Teams-Funktionen konfiguriert werden können und sollten.

### <a name="teams-and-channels-policies"></a>Richtlinien für Teams und Kanäle

Teams und Kanäle sind zwei häufig verwendete Elemente in Microsoft Teams, und es gibt Richtlinien, mit denen Sie steuern können, was Benutzer bei der Verwendung von Teams und Kanälen tun können. Sie können zwar ein globales Team erstellen, aber wenn Ihre Organisation über 5000 Benutzer oder weniger verfügt, ist es wahrscheinlich hilfreich, kleinere Teams und Kanäle für bestimmte Zwecke in Einklang mit Ihren Organisatorischen Anforderungen zu haben.

Es wird empfohlen, die Standardrichtlinie zu ändern oder benutzerdefinierte Richtlinien zu erstellen. Weitere Informationen zum Verwalten Ihrer Richtlinien finden Sie unter diesem Link: Verwalten von [Teams-Richtlinien in Microsoft Teams](/microsoftteams/teams-policies).

### <a name="messaging-policies"></a>Messagingrichtlinien

Messaging oder Chats können auch über die globale Standardrichtlinie oder über benutzerdefinierte Richtlinien verwaltet werden, und dies kann Ihren Benutzern dabei helfen, auf eine für Ihre Organisation geeignete Weise miteinander zu kommunizieren. Diese Informationen finden Sie unter [Managing messaging policies in Teams](/microsoftteams/messaging-policies-in-teams).

### <a name="meeting-policies"></a>Besprechungsrichtlinien

Ohne die Planung und Implementierung von Richtlinien rund um Teams-Besprechungen wäre keine Diskussion über Teams abgeschlossen. Besprechungen sind eine wesentliche Komponente von Teams, mit der Personen viele Benutzer auf einmal treffen und präsentieren und inhalte freigeben können, die für die Besprechung relevant sind. Das Festlegen der richtigen Richtlinien für Ihre Organisation im Rahmen von Besprechungen ist unerlässlich.

Weitere Informationen finden Sie unter [Verwalten von Besprechungsrichtlinien in Teams](/microsoftteams/meeting-policies-in-teams).

### <a name="app-permission-policies"></a>Richtlinien für App-Berechtigungen

Mit Teams können Sie apps auch an verschiedenen Orten verwenden, z. B. kanälen oder persönlichen Chats. Richtlinien darüber zu haben, welche Apps hinzugefügt und verwendet werden können und wo, ist für die Aufrechterhaltung einer inhaltsreichen Umgebung, die ebenfalls sicher ist, unerlässlich.

Weitere Informationen zu App-Berechtigungsrichtlinien finden Sie unter [Verwalten von App-Berechtigungsrichtlinien in Microsoft Teams](/microsoftteams/teams-app-permission-policies).

## <a name="next-steps"></a>Nächste Schritte

![Schritt 4: Richtlinien für Microsoft 365-Cloud-Apps](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Konfigurieren von Richtlinien für bedingten Zugriff für:

- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)