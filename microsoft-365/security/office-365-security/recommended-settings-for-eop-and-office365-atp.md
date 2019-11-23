---
title: Microsoft-Empfehlungen für EoP und Office 365 ATP-Sicherheitseinstellungen, Empfehlungen, Sender Policy Framework, domänenbasierte Nachrichtenberichterstattung und Konformität, DomainKeys identifizierte e-Mails, Schritte, wie funktioniert Sie usw.
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: Was sind bewährte Methoden für Exchange Online Protection (EoP) und ATP-Sicherheitseinstellungen (Advanced Threat Protection)? Was sind die aktuellen Empfehlungen für Standardschutz? Was sollte verwendet werden, wenn Sie strenger sein möchten? Und welche Extras erhalten Sie, wenn Sie auch Advanced Threat Protection (ATP) verwenden?
ms.openlocfilehash: d49f465aa66cd3c720e83b28569da2770300067e
ms.sourcegitcommit: 2de2faea7da80712f448e35c2d6c425944013b7e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "39204256"
---
# <a name="recommended-settings-for-eop-and-office-365-atp-security"></a>Empfohlene Einstellungen für EoP und Office 365 ATP-Sicherheit

**Exchange Online Protection (EoP)** ist der Kern der Sicherheit für Office 365 Abonnements und verhindert, dass böswillige e-Mails die Posteingänge ihrer Mitarbeiter erreichen. Bei neuen, anspruchsvolleren Angriffen, die täglich auftreten, sind häufig verbesserte Schutzmaßnahmen erforderlich. **Office 365 Advanced Threat Protection (ATP)** ATP-Plan 1 oder ATP-Plan 2 enthalten zusätzliche Features, die Administratoren mehr Ebenen der Sicherheit, Steuerung und Untersuchung bieten.

Obwohl wir Sicherheitsadministratoren die Möglichkeit geben, Ihre Sicherheitseinstellungen anzupassen, gibt es zwei Sicherheitsstufen in EoP und Office 365 ATP, die wir empfehlen: **Standard** und **Strict**. Die Umgebung und die Anforderungen jedes Kunden unterscheiden sich, aber wir glauben, dass diese Ebenen der e-Mail-Filterkonfigurationen dazu beitragen können, dass unerwünschte e-Mails in den meisten Fällen den Posteingang Ihrer Mitarbeiter erreichen.

In diesem Thema werden diese von Microsoft empfohlenen Einstellungen beschrieben, die zum Schutz Ihrer Office 365 Benutzer beitragen.

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Antispam-, Antischadsoftware-und Anti-Phishing-Schutz in EoP

Antispam-, Antischadsoftware-und Anti-Phishing-Funktionen sind Features von EoP, die von Administratoren konfiguriert werden können. Wir empfehlen die folgenden Konfigurationen.

### <a name="eop-anti-spam-policy-settings"></a>EoP-Anti-Spam-Richtlinieneinstellungen

|Name des Sicherheitsfeatures|Standard|Strict|Kommentar|
|---------|---------|---------|---------|
|Spam erkennungsaktion|Nachricht in Junk-E-Mail-Ordner verschieben|Nachricht in Quarantäne verschieben||
|Spam erkennungsaktion mit hoher Vertrauenswürdigkeit|Nachricht in Quarantäne verschieben|Nachricht in Quarantäne verschieben||
|Phishing-e-Mail-erkennungsaktion|Nachricht in Quarantäne verschieben|Nachricht in Quarantäne verschieben||
|Phishing-e-Mail-erkennungsaktion mit hoher Zuverlässigkeit|Nachricht in Quarantäne verschieben|Nachricht in Quarantäne verschieben||
|Massen-e-Mail-erkennungsaktion|Nachricht in Junk-E-Mail-Ordner verschieben|Nachricht in Quarantäne verschieben||
|Schwellenwert für Massen-e-Mail festlegen|6|4||
|Aufbewahrungszeitraum für Quarantäne|30 Tage|30 Tage||
|Sicherheitstipps|Ein|Ein||
|Zugelassene Absender|Keine|Keine||
|Zulässige Absenderdomänen|Keine|Keine|Das Hinzufügen von Domänen, die Sie besitzen (auch als _akzeptierte Domänen_bezeichnet), ist in der Liste der zulässigen Absender nicht erforderlich. Tatsächlich wird es als hohes Risiko betrachtet, da es Möglichkeiten für ungültige Akteure schafft, Ihnen e-Mails zu senden, die andernfalls herausgefiltert würden. Verwenden Sie [Spoof Intelligence](learn-about-spoof-intelligence.md) im Security #a0 Compliance Center auf der Seite **Anti-Spam-Einstellungen** , um alle Absender zu überprüfen, die entweder Spoofing von Domänen sind, die Teil Ihrer Organisation sind, oder Spoofing externer Domänen.|
|Blockierte Absender|Keine|Keine||
|Blockierte Absenderdomänen|Keine|Keine||
|Spam Benachrichtigungshäufigkeit für Endbenutzer|Aktiviert|Aktiviert|3 Tage|
|Automatische Bereinigung ohne Stunde|Ein|Ein|Für Spam und Phishing zap|
|MarkAsSpamBulkMail|Ein|Ein|Diese Einstellung ist nur in PowerShell verfügbar.|

In der Antispampolitik "Advanced Spamfilter" gibt es verschiedene andere Parameter, die zum Zeitpunkt des Schreibens veraltet sind. Unsere empfohlenen Einstellungen für diese sind, Sie für Standard mäßige und strenge Stufen **zu deaktivieren:**

|Name des Sicherheitsfeatures|
|---------|
|IncreaseScoreWithImageLinks|
|IncreaseScoreWithNumericIps|
|IncreaseScoreWithRedirectToOtherPort|
|IncreaseScoreWithBizOrInfoUrls|
|MarkAsSpamEmptyMessages|
|MarkAsSpamJavaScriptInHtml|
|MarkAsSpamFramesInHtml|
|MarkAsSpamObjectTagsInHtml|
|MarkAsSpamEmbedTagsInHtml|
|MarkAsSpamFormTagsInHtml|
|MarkAsSpamWebBugsInHtml|
|MarkAsSpamSensitiveWordList|
|MarkAsSpamFromAddressAuthFail|
|MarkAsSpamNdrBackscatter|
|MarkAsSpamSpfRecordHardFail|

#### <a name="eop-outbound-spam-filter-policy-settings"></a>EoP-Einstellungen für ausgehende Spamfilter Richtlinien

|Name des Sicherheitsfeatures|Standard|Strict|Kommentar|
|---------|---------|---------|---------|
|Empfänger Grenzwerte für ausgehende Spam Richtlinien – externer Stunden Grenzwert|400|500||
|Empfänger Grenzwerte für ausgehende Spam Richtlinien – interne stündliche Begrenzung|800|1000||
|Empfänger Grenzwerte für ausgehende Spam Richtlinien – tägliche Begrenzung|800|1000||
|Aktion, wenn ein Benutzer die Grenzwerte überschreitet|Einschränken des Sendens von e-Mails durch den Benutzer|Einschränken des Sendens von e-Mails durch den Benutzer||

### <a name="eop-anti-malware-policy-settings"></a>EoP-Anti-Malware-Richtlinieneinstellungen

|Name des Sicherheitsfeatures|Standard|Strict|Kommentar|
|---------|---------|---------|---------|
|Reaktion auf die Malware Erkennung|Nein|Nein|Wenn Schadsoftware in einer e-Mail-Anlage erkannt wird, wird die Nachricht isoliert und kann nur von einem Administrator freigegeben werden.|
|"Allgemeiner Anlagentyp Filter" zum Blockieren verdächtiger Dateitypen|Ein|Ein||
|Malware Zero-Hour Auto Purge|Ein|Ein||
|Interne Absender der nicht zugestellten Nachricht Benachrichtigen|Deaktiviert|Deaktiviert||
|Benachrichtigen externer Absender der nicht zugestellten Nachricht|Deaktiviert|Deaktiviert||

### <a name="eop-anti-phishing-policy-settings"></a>EoP-Einstellungen für Anti-Phishing-Richtlinien

|Name des Sicherheitsfeatures|Standard|Strict|Kommentar|
|---------|---------|---------|---------|
|Aktivieren des Schutzes gegen Spoofing|Ein|Ein||
|Aktivieren eines nicht authentifizierten Absenders (Tagging)|Ein|Ein||
|Wenn e-Mails von Benutzern gesendet werden, die Ihre Domäne nicht spoofen dürfen|Nachricht in die Junk-e-Mail-Ordner der Empfänger verlagern|Nachricht isolieren||

## <a name="office-365-advanced-threat-protection-security"></a>Office 365 Advanced Threat Protection-Sicherheit

Zusätzliche Sicherheitsvorteile bieten ein Office 365 Advanced Threat Protection (ATP)-Abonnement. Die neuesten Nachrichten und Informationen finden Sie unter [What es New in Office 365 ATP](whats-new-in-office-365-atp.md).

Office 365 ATP enthält die Richtlinien für sichere Anlagen und sichere Links, um zu verhindern, dass e-Mails mit potenziell böswilligen Anlagen zugestellt werden, und um Benutzer daran zu hindern, auf potenziell nicht sichere URLs zu klicken.

> [!IMPORTANT]
> Advanced Anti-Phishing ist einer der Vorteile eines Office 365 ATP-Abonnements. Obwohl es standardmäßig aktiviert ist, ***müssen*** Sie mindestens eine Anti-Phishing-Richtlinie konfigurieren, bevor Sie mit dem Filtern von e-Mails beginnen kann. Vergessen Sie nicht, die Anti-Phishing-Richtlinien zu konfigurieren, könnte Benutzern riskante e-Mails verfügbar gemacht werden. Achten Sie darauf, Ihre Anti-Phishing-Richtlinien zu konfigurieren, nachdem Sie ein Office 365 ATP-Abonnement hinzugefügt haben.

Wenn Sie Ihrem EoP ein Office 365 ATP-Abonnement hinzugefügt haben, legen Sie die folgenden Konfigurationen fest.

### <a name="office-atp-anti-phishing-policy-settings"></a>Office ATP-Einstellungen für Anti-Phishing-Richtlinien

EoP-Kunden erhalten grundlegende Anti-Phishing-Funktionen, wie zuvor beschrieben, aber Office 365 ATP umfasst weitere Features und Steuerelemente, um das verhindern, erkennen und Beheben von Angriffen zu unterstützen.

|Name des Sicherheitsfeatures für Identitätswechsel|Standard|Strict|Kommentar|
|---------|---------|---------|---------|
|(Richtlinie zum Bearbeiten von Identitätswechsel) Hinzufügen von Benutzern zum Schutz|Ein|Ein|Hängt von Ihrer Organisation ab, es wird jedoch empfohlen, Benutzer in Schlüsselrollen hinzuzufügen. Intern sind dies möglicherweise Ihr CEO, CFO und andere Führungskräfte. Diese können extern auch Ratsmitglieder oder ihren Verwaltungsrat umfassen.|
|(Richtlinie zum Bearbeiten von Identitätswechsel) Automatisches einschließen der Domänen, die ich besitze|Ein|Ein||
|(Richtlinie zum Bearbeiten von Identitätswechsel) Benutzerdefinierte Domänen einschließen|Ein|Ein|Hängt von Ihrer Organisation ab, wir empfehlen jedoch das Hinzufügen von Domänen, mit denen Sie interagieren, die Sie nicht besitzen.|
|Wenn e-Mail von einem imitierten Benutzer gesendet wird, den Sie angegeben haben|Nachricht isolieren|Nachricht isolieren||
|Wenn e-Mail von einer von Ihnen angegebenen imitierten Domäne gesendet wird|Nachricht isolieren|Nachricht isolieren||
|Tipp für imitierte Benutzer anzeigen|Ein|Ein||
|Tipp für imitierte Domänen anzeigen|Ein|Ein||
|Tipp für ungewöhnliche Zeichen anzeigen|Ein|Ein||
|Aktivieren der Post Fach Intelligenz|Ein|Ein||
|Aktivieren des Post Fach informationsbasierten Identitätswechsel Schutzes|Ein|Ein||
|Wenn e-Mails von einem imitierten Benutzer gesendet werden, der durch Post Fach Intelligenz geschützt ist|Nachricht in die Junk-e-Mail-Ordner der Empfänger verlagern|Nachricht isolieren||
|(Richtlinie zum Bearbeiten von Identitätswechsel) Hinzufügen von vertrauenswürdigen Absendern und Domänen|Keine|Keine|Hängt von Ihrer Organisation ab, es wird jedoch empfohlen, Benutzer oder Domänen hinzuzufügen, die aufgrund eines Identitätswechsels und nicht anderer Filter fälschlicherweise als Phishing gekennzeichnet werden.|

|Spoof Security Feature Name|Standard|Strict|Kommentar|
|---------|---------|---------|---------|
|Aktivieren des Schutzes gegen Spoofing|Ein|Ein||
|Aktivieren eines nicht authentifizierten Absenders (Tagging)|Ein|Ein||
|Wenn e-Mails von Benutzern gesendet werden, die Ihre Domäne nicht spoofen dürfen|Nachricht in die Junk-e-Mail-Ordner der Empfänger verlagern|Nachricht isolieren||
|EnableAuthenticationSafetyTip|True|True|Diese Einstellung ist nur in PowerShell verfügbar.|
|EnableAuthenticationSoftPassSafetyTip|False|Wahr|Diese Einstellung ist nur in PowerShell verfügbar.|
|EnableSuspiciousSafetyTip|False|Wahr|Diese Einstellung ist nur in PowerShell verfügbar.|
|TreatSoftPassAsAuthenticated|Wahr|Falsch|Diese Einstellung ist nur in PowerShell verfügbar.|

|Name der erweiterten Einstellungen-Sicherheitsfeature|Standard|Strict|Kommentar|
|---------|---------|---------|---------|
|Erweiterte Phishing-Schwellenwerte|2-aggressiv|3-aggressiver||

### <a name="safe-links-settings"></a>Einstellungen für sichere Links

|Name des Sicherheitsfeatures|Standard|Strict|Kommentar|
|---------|---------|---------|---------|
|Verwenden von ATP-sicheren Links in Office 365-apps, Office für IOS und Android|Aktiviert|Aktiviert|Dies fällt unter die Richtlinien für ATP-sichere Links, die für die gesamte Organisation gelten.|
Nicht nachverfolgen, wenn Benutzer auf sichere Links klicken|Deaktiviert|Deaktiviert|Dies fällt unter die Richtlinien für ATP-sichere Links, die für die gesamte Organisation gelten.|
|Nicht zulassen, dass Benutzer über sichere Links auf die ursprüngliche URL klicken|Aktiviert|Aktiviert|Dies fällt unter die Richtlinien für ATP-sichere Links, die für die gesamte Organisation gelten.|
|Aktion für unbekannte potenziell bösartige URLs in Nachrichten|Ein|Ein||
|Übernehmen der Echt Zeit-URL-Überprüfung auf verdächtige Links und Links, die auf Dateien verweisen|Aktiviert|Aktiviert||
|Warten Sie, bis die URL-Überprüfung abgeschlossen ist, bevor Sie die Nachricht liefern|Aktiviert|Aktiviert||
|Anwenden von sicheren Links auf e-Mail-Nachrichten, die innerhalb der Organisation gesendet werden|Aktiviert|Aktiviert||

### <a name="safe-attachments"></a>Sichere Anlagen

|Name des Sicherheitsfeatures|Standard|Strict|Kommentar|
|---------|---------|---------|---------|
|Aktivieren von ATP für SharePoint, OneDrive und Microsoft Teams|Aktiviert|Aktiviert||
|ATP-sichere Anlagen unbekannte Malware Antwort|Block|Block||
|Umleitungs Anlage bei der Erkennung|Aktiviert|Aktiviert|Umleitung zur e-Mail-Adresse eines Sicherheitsadministrators, der weiß, wie Sie feststellen können, ob die Anlage Schadsoftware ist oder nicht|
|Antwort bei ATP Safe Attachments, wenn Malwarescans für Anlagen ein Timeout oder ein Fehler auftritt|Aktiviert|Aktiviert||

## <a name="miscellaneous-settings"></a>Verschiedene Einstellungen

Diese Einstellungen umfassen eine Reihe von Features, die nicht unbedingt in bestimmte Kategorien oben passt. Einige der Einstellungen befinden sich außerhalb des Sicherheits #a0 Compliance Centers.

Name des Sicherheitsfeatures|Standard|Strict|Kommentar|
|---------|---------|---------|---------|
|[Einrichten von SPF in Office 365 zum Verhindern von Spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Ja|Ja||
|[Verwenden von DKIM zum Überprüfen ausgehender E-Mails, die von Ihrer benutzerdefinierten Domäne in Office 365 gesendet werden](use-dkim-to-validate-outbound-email.md)|Ja|Ja||
|[Verwenden von DMARC zum Validieren von E-Mails in Office 365](use-dmarc-to-validate-email.md)|Ja|Ja|Use Action = Quarantine for Standard und Action = Reject for Strict.|
|Bereitstellen des Berichtsnachrichten-Add-ons zur Verbesserung der Berichterstellung für verdächtige e-Mails durch Endbenutzer|Ja|Ja||
|Planen von Malware-und Spam Berichten|Ja|Ja||
|Die automatische Weiterleitung an externe Domänen sollte nicht zugelassen oder überwacht werden.|Ja|Ja||
|Einheitliche Überwachung sollte aktiviert sein|Ja|Ja||
|IMAP-Konnektivität mit Postfach|Deaktiviert|Deaktiviert||
|Pop-Konnektivität mit Postfach|Deaktiviert|Deaktiviert||
|SMTP-authentifizierte Übermittlung an Postfach|Deaktiviert|Deaktiviert||
|EWS-Konnektivität mit Postfach|Deaktiviert|Deaktiviert||
|PowerShell-Konnektivität|Deaktiviert|Deaktiviert||
|Verwenden von Spoofing Intelligence zum Whitelisting von Absendern, wann immer möglich|Ja|Ja||
|Verzeichnisbasierte Edge-Blockierung (Blockierung)|Aktiviert|Aktiviert|Domain-Typ = autorisierend|
|[Einrichten der mehrstufigen Authentifizierung für alle Administratorkonten](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)|Aktiviert|Aktiviert||
