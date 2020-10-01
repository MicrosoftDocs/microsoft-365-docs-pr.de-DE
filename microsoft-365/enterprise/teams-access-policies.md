---
title: Empfohlene Teams-Richtlinien – Microsoft 365 für Unternehmen | Microsoft-Dokumente
description: Beschreibt die Richtlinien für Microsoft-Empfehlungen zum Sichern von Team Kommunikation und Dateizugriff.
author: MicrosoftHeidi
manager: serdars
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: b9a9044a063c01724710679682e1edbe458dec0f
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327135"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a>Richtlinien Empfehlungen für das Sichern von teamchats,-Gruppen und-Dateien

In diesem Artikel wird beschrieben, wie Sie die empfohlenen Identitäts-und Gerätezugriffs Richtlinien implementieren, um Microsoft Teams-Chats,-Gruppen und-Inhalte wie Dateien und Kalender zu schützen. Dieser Leitfaden basiert auf den [allgemeinen Richtlinien für Identitäts-und Geräte Zugriff](identity-access-policies.md)mit zusätzlichen Informationen, die für Teams spezifisch sind. Da Teams in unsere anderen Produkte integriert werden, finden Sie weitere Informationen unter [Richtlinien Empfehlungen zum Sichern von SharePoint-Websites und-Dateien](sharepoint-file-access-policies.md) und [Richtlinien Empfehlungen zum Sichern von e-Mails](secure-email-recommended-policies.md).

Diese Empfehlungen basieren auf drei verschiedenen Ebenen der Sicherheit und des Schutzes für Teams, die basierend auf der Granularität Ihrer Anforderungen angewendet werden können: Baseline, sensibel und stark reguliert. Weitere Informationen zu diesen Sicherheitsebenen und den empfohlenen Richtlinien, auf die diese Empfehlungen verweisen, finden Sie unter [Identitäts-und Gerätezugriffs Konfigurationen](microsoft-365-policies-configurations.md).

In diesem Artikel werden zusätzliche Empfehlungen speziell für die Microsoft Teams-Bereitstellung aufgeführt, um bestimmte Authentifizierungs Bedingungen, einschließlich für Benutzer außerhalb Ihrer Organisation, abzudecken. Sie müssen diese Anleitung befolgen, um eine vollständige Sicherheitserfahrung zu erhalten.

## <a name="getting-started-with-teams-before-other-dependent-services"></a>Erste Schritte mit Microsoft Teams vor anderen abhängigen Diensten

Sie müssen abhängige Dienste nicht für den Einstieg in Microsoft Teams aktivieren. Diese werden alle "nur arbeiten". Sie müssen jedoch bereit sein, Folgendes zu verwalten:

- Microsoft 365-Gruppen
- SharePoint-Teamwebsites
- OneDrive for Business
- Exchange-Postfächer
- Stream Videos and Planner Plans (wenn diese Dienste aktiviert sind)

## <a name="updating-common-policies-to-include-teams"></a>Aktualisieren allgemeiner Richtlinien für die Einbeziehung von Teams

Um Chat, Gruppen und Inhalte in Microsoft Teams zu schützen, zeigt das folgende Diagramm, welche Richtlinien aus den allgemeinen Richtlinien für Identitäts-und Geräte Zugriff zu aktualisieren sind. Stellen Sie sicher, dass für jede zu aktualisierende Richtlinie Teams und abhängige Dienste in der Zuweisung von Cloud-Apps enthalten sind.

[![Zusammenfassung der Richtlinienaktualisierungen für den Schutz des Zugriffs auf Teams und deren abhängigen Dienste](../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

[Anzeigen einer größeren Version dieses Bilds](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

Hierbei handelt es sich um die abhängigen Dienste, die in die Zuweisung von Cloud-Apps für Teams einbezogen werden sollen:

- Microsoft Teams
- SharePoint und OneDrive for Business
- Exchange Online
- Skype for Business Online
- Microsoft-Datenstrom (Besprechungsaufzeichnungen)
- Microsoft Planner (planerische Aufgaben und Plandaten)

Diese Tabelle enthält eine Liste der Richtlinien, die erneut besucht werden müssen, sowie Links zu den einzelnen Richtlinien in den allgemeinen [Identitäts-und Gerätezugriffs Richtlinien](identity-access-policies.md), bei denen die umfassendere Richtlinie für alle Office-Anwendungen festgelegt ist.

|Schutzebene|Richtlinien|Weitere Informationen für die Implementierung von Teams|
|:---------------|:-------|:----------------|
|**Basisplan**|[MFA erforderlich, wenn das Anmelde Risiko *Mittel* groß oder *hoch* ist](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Stellen Sie sicher, dass Microsoft Teams und abhängige Dienste in der Liste der Apps enthalten sind. Microsoft Teams verfügt über Gastzugriff und Regeln für den externen Zugriff, die Sie später in diesem Artikel erfahren sollten.|
|        |[Blockieren von Clients, die die moderne Authentifizierung nicht unterstützen](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Einbeziehen von Teams und abhängigen Diensten in die Zuweisung von Cloud-apps.|
|        |[Nutzer mit hohem Risiko müssen das Kennwort ändern](identity-access-policies.md#high-risk-users-must-change-password)|Zwingt Teams-Benutzer, Ihr Kennwort zu ändern, wenn Sie sich anmelden, wenn hochriskante Aktivitäten für Ihr Konto erkannt werden. Stellen Sie sicher, dass Microsoft Teams und abhängige Dienste in der Liste der Apps enthalten sind.|
|        |[Anwenden von App-Datenschutzrichtlinien](identity-access-policies.md#apply-app-data-protection-policies)|Stellen Sie sicher, dass Microsoft Teams und abhängige Dienste in der Liste der Apps enthalten sind. Aktualisieren Sie die Richtlinie für jede Plattform (Ios, Android, Windows).|
|        |[Definieren von Geräte Konformitätsrichtlinien](identity-access-policies.md#define-device-compliance-policies)|Schließen Sie Teams und abhängige Dienste in diese Richtlinie ein.|
|        |[Kompatible PCs erforderlich](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Schließen Sie Teams und abhängige Dienste in diese Richtlinie ein.|
|**Vertraulich**|[MFA erforderlich, wenn das Anmelde Risiko *niedrig*, *Mittel* oder *hoch* ist](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Microsoft Teams verfügt über Gastzugriff und Regeln für den externen Zugriff, die Sie später in diesem Artikel erfahren sollten. Schließen Sie Teams und abhängige Dienste in diese Richtlinie ein.|
|         |[Erfordern von kompatiblen PCs *und* mobilen Geräten](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Schließen Sie Teams und abhängige Dienste in diese Richtlinie ein.|
|**Streng geregelt**|[*Immer* MFA erforderlich](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Unabhängig von der Benutzeridentität wird MFA von Ihrer Organisation verwendet. Schließen Sie Teams und abhängige Dienste in diese Richtlinie ein. |
| | |

## <a name="teams-dependent-services-architecture"></a>Architektur der Teams-abhängigen Dienste

Als Referenz zeigt das folgende Diagramm die Dienste, auf denen Teams basiert. Weitere Informationen und weitere Illustrationen finden Sie unter [Microsoft Teams und verwandte Produktivitätsdienste in Microsoft 365 für IT-Architekten](../solutions/productivity-illustrations.md).

[![Diagramm mit Microsoft Teams-Abhängigkeiten von SharePoint, OneDrive für Unternehmen und Exchange](../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

[Anzeigen einer größeren Version dieses Bilds](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="guest-and-external-access-for-teams"></a>Gast-und externer Zugriff für Teams

Microsoft Teams definiert Folgendes:

- **Gastzugriff** verwendet ein Azure AD B2B-Konto für einen Gast oder einen externen Benutzer, der als Mitglied eines Teams hinzugefügt werden kann und über alle Berechtigungen verfügt, die auf die Kommunikation und die Ressourcen des Teams zugreifen können.

- **Externer Zugriff** ist für einen externen Benutzer, der über kein Azure AD B2B-Konto verfügt. Externer Zugriff kann Einladungen und Teilnahme an anrufen, Chats und Besprechungen umfassen, umfasst jedoch nicht die Teammitgliedschaft und den Zugriff auf die Ressourcen des Teams.

Richtlinien für den bedingten Zugriff gelten nur für Gastzugriff in Microsoft Teams, da ein entsprechendes Azure AD B2B-Konto vorhanden ist.

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both. 

--> 

Empfohlene Richtlinien für den Zugriff für Gast-und externe Benutzer mit einem Azure AD B2B-Konto finden Sie unter [Richtlinien für das Zulassen von Gast-und externen B2B-Konto Zugriffen](identity-access-policies-guest-access.md).

### <a name="guest-access-in-teams"></a>Gastzugriff in Teams

Zusätzlich zu den Richtlinien für Benutzer, die für Ihr Unternehmen oder Ihre Organisation intern sind, können Administratoren den Gastzugriff aktivieren, um Personen, die sich außerhalb Ihres Unternehmens oder Ihrer Organisation befinden, für den Zugriff auf Microsoft Teams-Ressourcen und die Interaktion mit internen Personen für Gruppenunterhaltungen, Chats und Besprechungen zu ermöglichen. 

Weitere Informationen zum Gastzugriff und zur Implementierung finden Sie unter  [Teams Gastzugriff](https://docs.microsoft.com/microsoftteams/guest-access).

### <a name="external-access-in-teams"></a>Externer Zugriff in Microsoft Teams

Der externe Zugriff ist manchmal mit Gastzugriff verwechselt, daher ist es wichtig zu beachten, dass diese beiden nicht internen Zugriffsmechanismen tatsächlich ganz unterschiedlich sind. 

Externer Zugriff ist eine Möglichkeit für Microsoft Teams-Benutzer aus einer ganzen externen Domäne, Besprechungen mit ihren Benutzern in Microsoft Teams zu finden, anzurufen, zu chatten und einzurichten. Microsoft Teams-Administratoren konfigurieren den externen Zugriff auf Organisationsebene. Weitere Informationen finden Sie unter [Verwalten von externem Zugriff in Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-external-access).

Benutzer mit externem Zugriff haben weniger Zugriff und Funktionalität als eine Person, die über Gastzugriff hinzugefügt wurde. Beispielsweise können externe Benutzer mit ihren internen Benutzern mit Microsoft Teams chatten, aber nicht auf Team Kanäle, Dateien oder andere Ressourcen zugreifen.

Der externe Zugriff verwendet keine Azure AD B2B-Benutzerkonten und verwendet daher keine Richtlinien für den bedingten Zugriff. 

## <a name="teams-policies"></a>Teams-Richtlinien

Außerhalb der oben aufgeführten allgemeinen Richtlinien gibt es Teams-spezifische Richtlinien, die für die Verwaltung verschiedener Teams-Funktionen konfiguriert werden können und sollten.

### <a name="teams-and-channels-policies"></a>Richtlinien für Teams und Kanäle

Teams und Kanäle sind zwei häufig verwendete Elemente in Microsoft Teams, und es gibt Richtlinien, die Sie einführen können, um zu steuern, was Benutzer bei der Verwendung von Teams und Kanälen tun können und was nicht. Sie können zwar ein globales Team erstellen, aber wenn Ihre Organisation 5000 oder weniger Benutzer hat, ist es wahrscheinlich hilfreich, kleinere Teams und Kanäle für bestimmte Zwecke im Einklang mit Ihren organisatorischen Anforderungen zu haben.

Es empfiehlt sich, die Standardrichtlinie zu ändern oder benutzerdefinierte Richtlinien zu erstellen, und weitere Informationen zum Verwalten von Richtlinien finden Sie unter diesem Link: [Verwalten von Teams-Richtlinien in Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-policies).

### <a name="messaging-policies"></a>Messaging Richtlinien

Messaging oder Chat können auch über die standardmäßige globale Richtlinie oder durch benutzerdefinierte Richtlinien verwaltet werden, was dazu beitragen kann, dass Ihre Benutzer miteinander auf eine Weise kommunizieren, die für Ihre Organisation geeignet ist. Diese Informationen können unter [Managing Messaging Policies in Teams](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams)überprüft werden.

### <a name="meeting-policies"></a>Besprechungsrichtlinien

Keine Besprechung von Teams wäre ohne Planung und Implementierung von Richtlinien in Teams-Besprechungen abgeschlossen. Besprechungen stellen eine wesentliche Komponente von Teams dar und ermöglichen es den Benutzern, viele Benutzer gleichzeitig formell zu treffen und vorzustellen, sowie Inhalte für die Besprechung freizugeben. Das Festlegen der richtigen Richtlinien für Ihre Organisation in Besprechungen ist unerlässlich.

Weitere Informationen finden Sie [unter Manage Meeting Policies in Teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) .

### <a name="app-permission-policies"></a>Richtlinien für App-Berechtigungen

Mit Microsoft Teams können Sie auch apps an verschiedenen Orten wie Kanälen oder persönlichen Chats verwenden. Wenn Sie Richtlinien dazu haben, welche apps hinzugefügt und verwendet werden können, und wo dies erforderlich ist, ist dies für die Verwaltung einer inhaltsreichen Umgebung unerlässlich, die auch sicher ist.

Weitere Informationen zu app-Berechtigungsrichtlinien finden Sie [unter Verwalten von App-Berechtigungsrichtlinien in Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies).

## <a name="next-steps"></a>Nächste Schritte

![Schritt 4: Richtlinien für Microsoft 365 Cloud-apps](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Konfigurieren von Richtlinien für bedingten Zugriff für:

- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](secure-email-recommended-policies.md)

