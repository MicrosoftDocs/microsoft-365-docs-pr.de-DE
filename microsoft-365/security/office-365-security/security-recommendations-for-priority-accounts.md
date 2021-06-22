---
title: Sicherheitsempfehlungen für Prioritätskonten in Microsoft 365, Prioritätskonten, Prioritätskonten in Office 365, Prioritätskonten in Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-protecthve
description: Administratoren können erfahren, wie Sie die Sicherheitseinstellungen erhöhen und Berichte, Warnungen und Untersuchungen für Prioritätskonten in ihren Microsoft 365 Organisationen verwenden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e7617dd5af6a7e3b66fb33818208f01c8d8a338e
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53055258"
---
# <a name="security-recommendations-for-priority-accounts-in-microsoft-365"></a>Sicherheitsempfehlungen für Prioritätskonten in Microsoft 365

Nicht alle Benutzerkonten haben Zugriff auf dieselben Unternehmensinformationen. Einige Konten haben Zugriff auf vertrauliche Informationen, z. B. Finanzdaten, Produktentwicklungsinformationen, Partnerzugriff auf wichtige Buildsysteme und vieles mehr. Bei kompromittierten Konten, die Zugriff auf streng vertrauliche Informationen haben, stellen sie eine schwerwiegende Bedrohung dar. Wir bezeichnen diese Arten von Konten als _Prioritätskonten._ Zu den Prioritätskonten gehören (aber nicht beschränkt auf) CEOs, CISOs, CFOs, Infrastrukturadministratorkonten, Erstellen von Systemkonten und vieles mehr.

Für Angreifer sind normale Phishingangriffe, die ein zufälliges Netz für gewöhnliche oder unbekannte Benutzer bilden, ineffizient. Andererseits sind _Phishing-_ oder _Whalingangriffe,_ die auf Prioritätskonten abzielen, für Angreifer sehr ansprechend. Daher erfordern Prioritätskonten einen stärkeren als normalen Schutz, um kontokompromittieren zu verhindern.

Microsoft 365 und Microsoft Defender für Office 365 enthalten mehrere wichtige Features, die zusätzliche Sicherheitsebenen für Ihre Prioritätskonten bieten. In diesem Artikel werden diese Funktionen und ihre Verwendung beschrieben.

![Zusammenfassung der Sicherheitsempfehlungen in Symbolform](../../media/security-recommendations-for-priority-users.png)

<br>

****

|Aufgabe|Alle Office 365 Enterprise-Pläne|Microsoft 365 E3|Microsoft 365 E5|
|---|:---:|:---:|:---:|
|[Erhöhen der Anmeldesicherheit für Prioritätskonten](#increase-sign-in-security-for-priority-accounts)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Verwenden streng voreingestellter Sicherheitsrichtlinien für Prioritätskonten](#use-strict-preset-security-policies-for-priority-accounts)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Anwenden von Benutzertags auf Prioritätskonten](#apply-user-tags-to-priority-accounts)|||![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Überwachen von Prioritätskonten in Warnungen, Berichten und Erkennungen](#monitor-priority-accounts-in-alerts-reports-and-detections)|||![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Schulung der Benutzer](#train-users)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Enthalten](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|

> [!NOTE]
> Informationen zum Schützen _privilegierter Konten_ (Administratorkonten) finden Sie in [diesem Thema.](/azure/architecture/framework/security/critical-impact-accounts)

## <a name="increase-sign-in-security-for-priority-accounts"></a>Erhöhen der Anmeldesicherheit für Prioritätskonten

Prioritätskonten erfordern erhöhte Anmeldesicherheit. Sie können die Anmeldesicherheit erhöhen, indem Sie mehrstufige Authentifizierung (MFA) erfordern und legacy-Authentifizierungsprotokolle deaktivieren.

Anweisungen finden Sie in [Schritt 1. Erhöhen Sie die Anmeldesicherheit für Remotemitarbeiter mit MFA.](../../solutions/empower-people-to-work-remotely-secure-sign-in.md) Obwohl es in diesem Artikel um Remotemitarbeiter geht, gelten dieselben Konzepte für Prioritätsbenutzer.

**Hinweis:** Es wird dringend empfohlen, legacy-Authentifizierungsprotokolle für alle Prioritätsbenutzer global zu deaktivieren, wie im vorherigen Artikel beschrieben. Wenn Ihre geschäftlichen Anforderungen dies verhindern, bietet Exchange Online die folgenden Steuerelemente, um den Umfang der Legacyauthentifizierungsprotokolle zu begrenzen:

- Sie können [Authentifizierungsrichtlinien](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) und [Clientzugriffsregeln](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) in Exchange Online verwenden, um Standardauthentifizierungs- und Legacyauthentifizierungsprotokolle wie POP3, IMAP4 und authentifiziertes SMTP für bestimmte Benutzer zu blockieren oder zuzulassen.

- Sie können den POP3- und IMAP4-Zugriff auf einzelne Postfächer deaktivieren. Sie können authentifiziertes SMTP auf Organisationsebene deaktivieren und für bestimmte Postfächer aktivieren, für die es weiterhin erforderlich ist. Anweisungen finden Sie in den folgenden Artikeln:
  - [Aktivieren oder Deaktivieren des POP3- oder IMAP4-Zugriffs für einen Benutzer](/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)
  - [Aktivieren oder Deaktivieren der authentifizierten CLIENT-SMTP-Übermittlung (SMTP AUTH)](/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)

Beachten Sie außerdem, dass die Standardauthentifizierung in Exchange Online für Exchange Webdienste (EWS), Exchange ActiveSync, POP3, IMAP4 und Remote-PowerShell veraltet ist. Weitere Informationen finden Sie in diesem [Blogbeitrag.](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/)

## <a name="use-strict-preset-security-policies-for-priority-accounts"></a>Verwenden streng voreingestellter Sicherheitsrichtlinien für Prioritätskonten

Prioritätsbenutzer erfordern strengere Aktionen für die verschiedenen Schutzmaßnahmen, die in Exchange Online Protection (EOP) und Defender für Office 365 verfügbar sind.

Anstatt nachrichten, die als Spam klassifiziert wurden, beispielsweise an den Junk-E-Mail-Ordner zu übermitteln, sollten Sie dieselben Nachrichten unter Quarantäne stellen, wenn sie für Prioritätskonten vorgesehen sind.

Sie können diesen strikten Ansatz für Prioritätskonten mithilfe des Strict-Profils in voreingestellten Sicherheitsrichtlinien implementieren.

Voreingestellte Sicherheitsrichtlinien sind ein praktischer und zentraler Ort, um unsere empfohlenen strengen Richtlinieneinstellungen für alle Schutzmaßnahmen in EOP und Defender für Office 365 anzuwenden. Weitere Informationen finden Sie unter ["Voreingestellte Sicherheitsrichtlinien" in EOP und Microsoft Defender für Office 365.](preset-security-policies.md)

Ausführliche Informationen dazu, wie sich die Strict-Richtlinieneinstellungen von den Standard- und Standardrichtlinieneinstellungen unterscheiden, finden Sie unter [Empfohlene Einstellungen für EOP und Microsoft Defender für Office 365 Sicherheit.](recommended-settings-for-eop-and-office365.md)

## <a name="apply-user-tags-to-priority-accounts"></a>Anwenden von Benutzertags auf Prioritätskonten

Benutzertags in Microsoft Defender für Office 365 Plan 2 (als Teil von Microsoft 365 E5 oder einem Add-On-Abonnement) sind eine Möglichkeit, bestimmte Benutzer oder Benutzergruppen in Berichten und Vorfalluntersuchungen schnell zu identifizieren und zu klassifizieren.

**Bei Prioritätskonten** handelt es sich um eine Art integriertes Benutzertag _(systemtag),_ mit dem Sie Vorfälle und Warnungen identifizieren können, die Prioritätskonten betreffen. Weitere Informationen zu **Prioritätskonten** finden Sie unter [Verwalten und Überwachen von Prioritätskonten.](../../admin/setup/priority-accounts.md)

Sie können auch benutzerdefinierte Tags erstellen, um Ihre Prioritätskonten weiter zu identifizieren und zu klassifizieren. Weitere Informationen finden Sie unter [Benutzertags.](user-tags.md) Sie können **Prioritätskonten** (Systemtags) auf derselben Benutzeroberfläche wie benutzerdefinierte Benutzertags verwalten.

## <a name="monitor-priority-accounts-in-alerts-reports-and-detections"></a>Überwachen von Prioritätskonten in Warnungen, Berichten und Erkennungen

Nachdem Sie Ihre Prioritätsbenutzer gesichert und gekennzeichnet haben, können Sie die verfügbaren Berichte, Warnungen und Untersuchungen in EOP und Defender für Office 365 verwenden, um Vorfälle oder Erkennungen, die Prioritätskonten betreffen, schnell zu identifizieren. Die Features, die Benutzertags unterstützen, werden in der folgenden Tabelle beschrieben.

<br>

****

|Feature|Beschreibung|
|---|---|
|Warnungen|Die Benutzertags der betroffenen Benutzer sind sichtbar und als Filter auf der Seite **"Warnungen"** im Microsoft 365 Defender-Portal verfügbar. Weitere Informationen finden Sie unter [Anzeigen von Warnungen.](../../compliance/alert-policies.md#viewing-alerts)|
|Explorer <p> Echtzeiterkennungen|In **Explorer** (Defender für Office 365 Plan 2) oder **Echtzeiterkennungen** (Defender für Office 365 Plan 1) sind Benutzertags in der E-Mail-Rasteransicht und im Flyout für E-Mail-Details sichtbar. Benutzertags sind auch als filterbare Eigenschaft verfügbar. Weitere Informationen finden Sie unter  [Tags im Explorer](threat-explorer.md#tags-in-threat-explorer).|
|Kampagnenansichten|Benutzertags sind eine von vielen filterbaren Eigenschaften in Kampagnenansichten in Microsoft Defender für Office 365 Plan 2. Weitere Informationen finden Sie unter [Kampagnenansichten.](campaigns.md)|
|Threat Protection-Statusbericht|In praktisch allen Ansichten und Detailtabellen im **Bedrohungsschutzstatusbericht** können Sie die Ergebnisse nach **Prioritätskonten** filtern. Weitere Informationen finden Sie unter [Bedrohungsschutzstatusbericht.](view-email-security-reports.md#threat-protection-status-report)|
|E-Mail-Probleme für Bericht über Prioritätskonten|Der Bericht **"E-Mail-Probleme bei Prioritätskonten"** im Exchange Admin Center (EAC) enthält Informationen zu nicht zugestellten und verzögerten Nachrichten für **Prioritätskonten.** Weitere Informationen finden Sie unter ["E-Mail-Probleme bei Prioritätskontenbericht".](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)|
|

## <a name="train-users"></a>Schulung der Benutzer

Das Trainieren von Benutzern mit Prioritätskonten kann dazu beitragen, dass diese Benutzer und Ihr Sicherheitsteam viel Zeit und Frustration sparen. Erfahrene Benutzer öffnen weniger Anlagen oder klicken auf Links in fraglichen E-Mail-Nachrichten, und sie vermeiden eher verdächtige Websites.

Das [Cybersicherheitskampagnenhandbuch](https://www.belfercenter.org/CyberPlaybook) der Schule Stellt hervorragende Anleitungen bereit, um eine starke Kultur des Sicherheitsbewusstseins in Ihrer Organisation zu schaffen, einschließlich der Schulung von Benutzern zur Identifizierung von Phishingangriffen.

Microsoft 365 bietet die folgenden Ressourcen, um Benutzer in Ihrer Organisation zu informieren:

<br>

****

|Konzept|Ressourcen|Beschreibung|
|---|---|---|
|Microsoft 365|[Anpassbare Lernpfade](/office365/customlearning/)|Diese Ressourcen können Ihnen helfen, Schulungen für Benutzer in Ihrer Organisation zusammenzustellen.|
|Microsoft 365 Security|[Learning Modul: Sichern Ihrer Organisation mit integrierter, intelligenter Sicherheit vor Microsoft 365](/learn/modules/security-with-microsoft-365)|In diesem Modul können Sie beschreiben, wie Microsoft 365 Sicherheitsfeatures zusammenarbeiten und die Vorteile dieser Sicherheitsfeatures erläutern.|
|Mehrstufige Authentifizierung|[Zweistufige Überprüfung: Was ist die zusätzliche Überprüfungsseite?](/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time)|Dieser Artikel hilft Endbenutzern zu verstehen, was die mehrstufige Authentifizierung ist und warum sie in Ihrer Organisation verwendet wird.|
|Angriffssimulationstraining|[Erste Schritte mit dem Angriffssimulationstraining](attack-simulation-training-get-started.md)|Die Angriffssimulationsschulung in Microsoft Defender für Office 365 Plan 2 ermöglicht Administratoren das Konfigurieren, Starten und Nachverfolgen simulierter Phishingangriffe auf bestimmte Benutzergruppen.|

Darüber hinaus empfiehlt Microsoft, dass Benutzer die in diesem Artikel beschriebenen Aktionen ausführen: [Schützen Ihres Kontos und Ihrer Geräte vor Hackern und Schadsoftware.](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6) Diese setzen sich wie folgt zusammen:

- Verwenden sicherer Kennwörter
- Schützen von Geräten
- Aktivieren von Sicherheitsfeatures auf Windows 10 und Mac-PCs (für nicht verwaltete Geräte)

## <a name="see-also"></a>Siehe auch

[Ankündigung des Prioritätskontoschutzes in Microsoft Defender für Office 365](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/announcing-priority-account-protection-in-microsoft-defender-for/ba-p/1696385)
