---
title: Sicherheitsempfehlungen für Prioritätskonten in Microsoft 365
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
- m365solution-overview
- m365solution-protecthve
description: Administratoren können erfahren, wie Sie die Sicherheitseinstellungen erhöhen und Berichte, Warnungen und Untersuchungen für Prioritätskonten in ihren Microsoft 365-Organisationen verwenden.
ms.openlocfilehash: acd2eba0acd533d0cd8223f2c433cc023fc23287
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790126"
---
# <a name="security-recommendations-for-priority-accounts-in-microsoft-365"></a>Sicherheitsempfehlungen für Prioritätskonten in Microsoft 365

Nicht alle Benutzerkonten haben Zugriff auf dieselben Unternehmensinformationen. Einige Konten haben Zugriff auf vertrauliche Informationen, z. B. Finanzdaten, Produktentwicklungsinformationen, Partnerzugriff auf kritische Buildsysteme und vieles mehr. Konten, die Zugriff auf streng vertrauliche Informationen haben, stellen eine schwerwiegende Bedrohung dar, wenn sie gefährdet sind. Wir bezeichnen diese Arten von Konten _als Prioritätskonten._ Zu den Prioritätskonten gehören CEOs, CISOs, CFOs, Infrastrukturadministratorkonten, Buildsystemkonten und vieles mehr.

Für Angreifer sind gewöhnliche Phishingangriffe, die ein zufälliges Netz für gewöhnliche oder unbekannte Benutzer umvariablen, ineffizient. Andererseits sind _Phishing- oder_ _Whalingangriffe,_ die auf Prioritätskonten zielen, für Angreifer sehr lohnend. Daher erfordern Prioritätskonten einen stärkeren Als gewöhnlichen Schutz, um eine Kontoberomittung zu verhindern.

Microsoft 365 und Microsoft Defender für Office 365 enthalten mehrere wichtige Features, die zusätzliche Sicherheitsebenen für Ihre Prioritätskonten bereitstellen. In diesem Artikel werden diese Funktionen und deren Verwendung beschrieben.

![Zusammenfassung der Sicherheitsempfehlungen in Symbolform](../../media/security-recommendations-for-priority-users.png)

****

|Aufgabe|Alle Office 365 Enterprise-Pläne|Microsoft 365 E3|Microsoft 365 E5|
|---|:---:|:---:|:---:|
|[Erhöhen der Anmeldesicherheit für Prioritätskonten](#increase-sign-in-security-for-priority-accounts)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Verwenden von strengen voreingestellten Sicherheitsrichtlinien für Prioritätskonten](#use-strict-preset-security-policies-for-priority-accounts)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Anwenden von Benutzertags auf Prioritätskonten](#apply-user-tags-to-priority-accounts)|||![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Überwachen von Prioritätskonten in Warnungen, Berichten und Erkennungen](#monitor-priority-accounts-in-alerts-reports-and-detections)|||![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|

## <a name="increase-sign-in-security-for-priority-accounts"></a>Erhöhen der Anmeldesicherheit für Prioritätskonten

Prioritätskonten erfordern erhöhte Anmeldesicherheit. Sie können die Anmeldesicherheit erhöhen, indem Sie die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) erfordern und Legacyauthentifizierungsprotokolle deaktivieren.

Anweisungen finden Sie unter [Schritt 1. Erhöhen Sie die Anmeldesicherheit für Remotemitarbeiter mit MFA.](https://docs.microsoft.com/microsoft-365/solutions/empower-people-to-work-remotely-secure-sign-in) Obwohl es in diesem Artikel um Remotemitarbeiter geht, gelten die gleichen Konzepte für Benutzer mit Priorität.

**Hinweis:** Es wird dringend empfohlen, legacybasierte Authentifizierungsprotokolle für alle Benutzer mit Priorität global zu deaktivieren, wie im vorherigen Artikel beschrieben. Wenn Ihre geschäftlichen Anforderungen Sie daran hindern, bietet Exchange Online die folgenden Steuerelemente, um den Umfang der Legacyauthentifizierungsprotokolle zu begrenzen:

- Sie können [Authentifizierungsrichtlinien](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) und [Clientzugriffsregeln](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) in Exchange Online verwenden, um Standardauthentifizierungs- und Legacyauthentifizierungsprotokolle wie POP3, IMAP4 und authentifizierte SMTP für bestimmte Benutzer zu blockieren oder zu erlauben.

- Sie können den POP3- und den IMAP4-Zugriff auf einzelne Postfächer deaktivieren. Sie können authentifizierte SMTP auf Organisationsebene deaktivieren und für bestimmte Postfächer aktivieren, für die dies noch erforderlich ist. Anweisungen finden Sie in den folgenden Themen:
  - [Aktivieren oder Deaktivieren des POP3- oder IMAP4-Zugriffs für einen Benutzer](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)
  - [Aktivieren oder Deaktivieren der authentifizierten Client-SMTP-Übermittlung (SMTP AUTH)](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)

Es ist auch erwähnenswert, dass die Standardauthentifizierung in Exchange Online für Exchange Web Services (EWS), Exchange ActiveSync, POP3, IMAP4 und Remote PowerShell veraltet ist. Weitere Informationen finden Sie in diesem [Blogbeitrag.](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/)

## <a name="use-strict-preset-security-policies-for-priority-accounts"></a>Verwenden von strengen voreingestellten Sicherheitsrichtlinien für Prioritätskonten

Benutzer mit Priorität erfordern strengere Aktionen für die verschiedenen Schutzmaßnahmen, die in Exchange Online Protection (EOP) und Defender für Office 365 verfügbar sind.

Anstatt beispielsweise Nachrichten, die als Spam klassifiziert wurden, in den Junk-E-Mail-Ordner zu senden, sollten Sie dieselben Nachrichten unter Quarantäne stellen, wenn sie für Prioritätskonten vorgesehen sind.

Sie können diesen strikten Ansatz für Prioritätskonten implementieren, indem Sie das Profil "Strict" in voreingestellten Sicherheitsrichtlinien verwenden.

Voreingestellte Sicherheitsrichtlinien sind ein bequemer und zentraler Ort, um die empfohlenen "Strict"-Richtlinieneinstellungen für alle Schutzmaßnahmen in EOP und Defender für Office 365 anzuwenden. Weitere Informationen finden Sie unter [voreingestellte Sicherheitsrichtlinien in EOP und Microsoft Defender für Office 365](preset-security-policies.md).

Weitere Informationen dazu, wie sich die Strikte Richtlinieneinstellungen von den Standard- und Standardrichtlinieneinstellungen unterscheiden, finden Sie unter "Empfohlene Einstellungen für EOP und [Microsoft Defender für Office 365-Sicherheit".](recommended-settings-for-eop-and-office365-atp.md)

## <a name="apply-user-tags-to-priority-accounts"></a>Anwenden von Benutzertags auf Prioritätskonten

Benutzertags in Microsoft Defender für Office 365 Plan 2 (als Teil von Microsoft 365 E5 oder einem Add-On-Abonnement) sind eine Möglichkeit, bestimmte Benutzer oder Benutzergruppen in Berichten und Vorfalluntersuchungen schnell zu identifizieren und zu klassifizieren.

**Bei Prioritätskonten** handelt es sich um eine Art von integriertem Benutzertag (auch als Systemtag bezeichnet), mit dem Sie Vorfälle und Warnungen identifizieren können, die Prioritätskonten betreffen. Weitere Informationen zu **Prioritätskonten finden** Sie unter ["Verwalten und Überwachen von Prioritätskonten".](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)

Sie können auch benutzerdefinierte Tags erstellen, um Ihre Prioritätskonten weiter zu identifizieren und zu klassifizieren. Weitere Informationen finden Sie unter [Benutzertags.](user-tags.md) Beachten Sie, dass Sie **Prioritätskonten** (Systemtags) auf derselben Benutzeroberfläche wie benutzerdefinierte Benutzertags verwalten können.

## <a name="monitor-priority-accounts-in-alerts-reports-and-detections"></a>Überwachen von Prioritätskonten in Warnungen, Berichten und Erkennungen

Nachdem Sie Ihre Prioritätsbenutzer gesichert und identifiziert haben, können Sie die verfügbaren Berichte, Warnungen und Untersuchungen in EOP und Defender für Office 365 verwenden, um Vorfälle oder Erkennungen mit Prioritätskonten schnell zu identifizieren. Die Features, die Benutzertags unterstützen, werden in der folgenden Tabelle beschrieben.

<br>

****

|Feature|Beschreibung|
|---|---|
|Warnungen|Die Benutzertags der betroffenen Benutzer sind als  Filter auf der Seite Benachrichtigungen anzeigen im Security & Compliance Center sichtbar und verfügbar. Weitere Informationen finden Sie unter Anzeigen [von Warnungen.](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#viewing-alerts)|
|Sicherheitsrisiken-Explorer <p> Echtzeiterkennungen|Im **Bedrohungs-Explorer** (Microsoft Defender für Office 365 Plan 2) oder in Echtzeiterkennungen (Microsoft Defender für Office 365 Plan 1) werden Benutzertags in der Ansicht "E-Mail-Raster" und im Flyout **"E-Mail-Details"** angezeigt. Benutzertags sind auch als filterbare Eigenschaft verfügbar. Weitere Informationen finden Sie unter [Tags im Bedrohungs-Explorer.](threat-explorer.md#tags-in-threat-explorer)|
|Kampagnenansichten|Benutzertags sind eine von vielen filterbaren Eigenschaften in Kampagnenansichten in Microsoft Defender für Office 365 Plan 2. Weitere Informationen finden Sie unter [Kampagnenansichten](campaigns.md).|
|Threat Protection-Statusbericht|In praktisch allen Ansichten und Detailtabellen im Statusbericht zum Bedrohungsschutz können Sie die Ergebnisse nach **Prioritätskonten filtern.**  Weitere Informationen finden Sie im [Statusbericht zum Bedrohungsschutz.](view-email-security-reports.md#threat-protection-status-report)|
|Bericht zu E-Mail-Problemen bei Prioritätskonten|Der **Bericht "E-Mail-Probleme** bei Prioritätskonten" im Exchange Admin Center (EAC) enthält Informationen zu nicht zugestellten und verzögerten Nachrichten für **Prioritätskonten.** Weitere Informationen finden Sie im Bericht [zu E-Mail-Problemen mit Prioritätskonten.](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)|
|

## <a name="see-also"></a>Siehe auch

[Ankündigung von Prioritätskontoschutz in Microsoft Defender für Office 365](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/announcing-priority-account-protection-in-microsoft-defender-for/ba-p/1696385)
