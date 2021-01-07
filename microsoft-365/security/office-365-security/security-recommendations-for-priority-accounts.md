---
title: Sicherheitsempfehlungen für Prioritäts Konten in Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie die Sicherheitseinstellungen erhöhen und Berichte, Warnungen und Untersuchungen für Prioritäts Konten in Ihren Microsoft 365-Organisationen verwenden.
ms.openlocfilehash: 9788131ea881a1cb3c36a60dfaac01ed5daf0901
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769245"
---
# <a name="security-recommendations-for-priority-accounts-in-microsoft-365"></a>Sicherheitsempfehlungen für Prioritäts Konten in Microsoft 365

Was würden Sie tun, wenn Sie eine dringende Nachricht von einer Führungskraft in Ihrer Organisation erhalten haben, in der Sie aufgefordert wurden, etwas zu tun? Würdest du es tun? Die meisten Personen würden die Anforderung erfüllen.

Für Angreifer sind gewöhnliche Phishing-Angriffe, die ein zufälliges Netz umwandeln, um die Anmeldeinformationen von zufälligen oder unbekannten Benutzern abzurufen, ineffizient. Auf der anderen Seite sind _Speer-Phishing_ -oder _Walfang_ Angriffe, die sich an die Benutzer in macht-oder Autoritätspositionen richten, für Angreifer weitaus lohnender. Wenn diese Prioritäts Konten kompromittiert werden, erhält der Angreifer möglicherweise Zugriff auf Konten mit Administrator-, Finanz-, Produkt-oder sogar physischen Zugriffsfunktionen innerhalb der Organisation.

Microsoft 365 und Microsoft Defender für Office 365 enthalten viele verschiedene Features, die Sie bei der Bereitstellung zusätzlicher Sicherheitsebenen für Ihre Prioritäts Konten unterstützen können. In diesem Artikel werden die verfügbaren Features und deren Verwendung erläutert.

![Zusammenfassung der Sicherheitsempfehlungen in Form von Symbolen](../../media/security-recommendations-for-priority-users.png)

## <a name="increase-sign-in-security-for-priority-accounts"></a>Verbessern der Anmeldesicherheit für Prioritäts Konten

Priority-Konten erfordern eine erhöhte Anmeldesicherheit. Sie können Ihre Anmeldesicherheit erweitern, indem Sie die mehrstufige Authentifizierung (MFA) und die Deaktivierung von Legacy-Authentifizierungsprotokollen benötigen.

Anweisungen finden Sie unter [Schritt 1. Erhöht die Anmeldesicherheit für Remotemitarbeiter mit MFA](https://docs.microsoft.com/microsoft-365/solutions/empower-people-to-work-remotely-secure-sign-in). Obwohl es sich bei diesem Artikel um Remote-Arbeitskräfte handelt, gelten dieselben Konzepte für Prioritäts Benutzer.

**Hinweise**:

- Die Standardauthentifizierung wird derzeit in Exchange Online für Exchange-Webdienste, Exchange ActiveSync, POP3, IMAP4 und Remote-PowerShell veraltet. Ausführliche Informationen finden Sie in diesem [Blogbeitrag](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/).

- Sie können [Authentifizierungsrichtlinien](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) und [Client Zugriffsregeln](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) in Exchange Online verwenden, um grundlegende Authentifizierungs-und Legacy Authentifizierungsprotokolle wie POP3, IMAP4 und authentifiziertes SMTP zu blockieren.

- Sie können den POP3-und IMAP4-Zugriff für einzelne Postfächer deaktivieren. Sie können authentifizierte SMTP-Authentifizierung auf Organisationsebene deaktivieren und für bestimmte Postfächer aktivieren, die Sie weiterhin benötigen. Anweisungen finden Sie in den folgenden Themen:
  - [Aktivieren oder Deaktivieren des POP3-oder IMAP4-Zugriffs für einen Benutzer](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)
  - [Aktivieren oder Deaktivieren der authentifizierten SMTP-Übermittlung für Clients (SMTP-Authentifizierung)](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)

## <a name="use-strict-preset-security-policies-for-priority-accounts"></a>Verwenden strenger vordefinierter Sicherheitsrichtlinien für Prioritäts Konten

Priority-Benutzer benötigen strengere Aktionen für die verschiedenen Schutzmaßnahmen, die in Exchange Online Protection (EoP) und Defender für Office 365 verfügbar sind.

Anstatt beispielsweise Nachrichten, die als Spam klassifiziert wurden, in den Junk-e-Mail-Ordner zu übermitteln, sollten Sie die gleichen Nachrichten isolieren, wenn Sie für Prioritäts Konten vorgesehen sind.

Sie können diesen stringenten Ansatz für Prioritäts Konten implementieren, indem Sie das strenge Profil in vordefinierten Sicherheitsrichtlinien verwenden.

Voreingestellte Sicherheitsrichtlinien sind eine bequeme und zentrale Position, um unsere empfohlenen strengen Richtlinieneinstellungen für alle Schutzmaßnahmen in EoP und Defender für Office 365 anzuwenden. Weitere Informationen finden Sie unter [Preset Security Policies in EoP und Microsoft Defender für Office 365](preset-security-policies.md).

Ausführliche Informationen dazu, wie sich die strengen Richtlinieneinstellungen von den Standardrichtlinieneinstellungen unterscheiden, finden Sie unter [recommended settings for EoP and Microsoft Defender for Office 365 Security](recommended-settings-for-eop-and-office365-atp.md).

## <a name="apply-user-tags-to-priority-accounts"></a>Anwenden von Benutzer Tags auf Prioritäts Konten

Benutzer Tags in Microsoft Defender für Office 365 Plan 2 (als Teil von Microsoft 365 E5 oder einem Add-on-Abonnement) sind eine Möglichkeit, bestimmte Benutzer oder Benutzergruppen in Berichten und Vorfall Ermittlungen schnell zu identifizieren und zu klassifizieren.

**Priority Accounts** ist ein integrierter Benutzertag (als _SystemTag_ bezeichnet), mit dem Sie Vorfälle und Warnungen identifizieren können, bei denen es sich um Prioritäts Konten handelt. Weitere Informationen zu **Prioritäts Konten** finden Sie unter [Manage and Monitor Priority Accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).

Sie können auch benutzerdefinierte Tags erstellen, um Ihre Prioritäts Konten weiter zu identifizieren und zu klassifizieren. Weitere Informationen finden Sie unter [User Tags](user-tags.md). Beachten Sie, dass Sie **Prioritäts Konten** (System Tags) in derselben Schnittstelle wie benutzerdefinierte Benutzer Tags verwalten können.

## <a name="monitor-priority-accounts-in-alerts-reports-and-detections"></a>Überwachen von Prioritäts Konten in Warnungen, Berichten und Erkennungen

Nachdem Sie Ihre Prioritäts Benutzer gesichert und markiert haben, können Sie die verfügbaren Berichte, Warnungen und Untersuchungen in EoP und Defender für Office 365 verwenden, um schnell Vorfälle oder Erkennungen zu identifizieren, die vorrangige Konten umfassen. Die Features, die Benutzer Tags unterstützen, werden in der folgenden Tabelle beschrieben.

<br>

****

|Feature|Beschreibung|
|---|---|
|Warnungen|Die Benutzer Tags der betroffenen Benutzer sind sichtbar und sind als Filter auf der Seite **Benachrichtigungen anzeigen** im Security & Compliance Center verfügbar. Weitere Informationen finden Sie unter [Anzeigen von Benachrichtigungen](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#viewing-alerts).|
|Sicherheitsrisiken-Explorer <p> Echtzeiterkennungen|In **Threat Explorer** (Microsoft Defender for Office 365 Plan 2) oder **Real-Time Detections** (Microsoft Defender for Office 365 Plan 1) werden Benutzer Tags in der e-Mail-Rasteransicht und im e-Mail-Detail-Flyout angezeigt. Benutzer Tags stehen auch als filterbare Eigenschaft zur Verfügung. Weitere Informationen finden Sie unter  [Tags in Threat Explorer](threat-explorer.md#tags-in-threat-explorer).|
|Kampagnenansichten|Benutzer Tags sind eine von vielen filterbaren Eigenschaften in Kampagnen Ansichten in Microsoft Defender für Office 365 Plan 2. Weitere Informationen finden Sie unter [Kampagnen Ansichten](campaigns.md).|
|Threat Protection-Statusbericht|In nahezu allen Ansichten und Detailtabellen des **Threat Protection-Statusberichts** können Sie die Ergebnisse nach **Prioritäts Konten** filtern. Weitere Informationen finden Sie unter [Threat Protection-Statusbericht](view-email-security-reports.md#threat-protection-status-report).|
|E-Mail-Probleme für Bericht über Prioritäten Konten|Der Bericht über **e-Mail-Probleme für die Priorität "Konten** " im Exchange Admin Center (EAC) enthält Informationen zu nicht zugestellten und verzögerten Nachrichten für **Prioritäts Konten**. Weitere Informationen finden Sie unter [e-Mail-Probleme für den Bericht über vorrangige Konten](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).|
|

## <a name="see-also"></a>Siehe auch

[Ankündigen des Prioritäts Konto Schutzes in Microsoft Defender für Office 365](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/announcing-priority-account-protection-in-microsoft-defender-for/ba-p/1696385)
