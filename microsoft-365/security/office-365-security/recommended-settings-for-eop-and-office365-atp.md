---
title: Microsoft-Empfehlungen für EoP und Defender für Office 365 Sicherheitseinstellungen, Empfehlungen, Sender Policy Framework, domänenbasierte Nachrichtenberichterstattung und Konformität, DomainKeys identifizierte e-Mails, Schritte, Arbeitsweise, Sicherheitsbasislinien, Baselines für EoP, Baselines für Defender für Office 365, Einrichten von Defender für Office 365, Einrichten von EoP, Konfigurieren von Defender für Office 365, Konfigurieren von EoP, Sicherheitskonfiguration
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: ''
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Was sind bewährte Methoden für Exchange Online Schutz (EoP) und Defender für Office 365 Sicherheitseinstellungen? Was sind die aktuellen Empfehlungen für Standardschutz? Was sollte verwendet werden, wenn Sie strenger sein möchten? Und welche Extras erhalten Sie, wenn Sie auch Defender für Office 365 verwenden?
ms.openlocfilehash: af741e1af412d535c53beb83c36c0cbe3fcd617b
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357121"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>Empfohlene Einstellungen für EoP und Microsoft Defender für Office 365 Sicherheit

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Exchange Online Protection (EoP)** ist das Herzstück der Sicherheit für Microsoft 365-Abonnements und verhindert, dass böswillige e-Mails die Posteingänge ihrer Mitarbeiter erreichen. Bei neuen, anspruchsvolleren Angriffen, die täglich auftreten, sind häufig verbesserte Schutzmaßnahmen erforderlich. **Microsoft Defender für Office 365** Plan 1 oder Plan 2 enthalten zusätzliche Features, die Administratoren mehr Ebenen der Sicherheit, Steuerung und Untersuchung bieten.

Obwohl wir Sicherheitsadministratoren die Möglichkeit geben, Ihre Sicherheitseinstellungen anzupassen, gibt es zwei Sicherheitsstufen in EoP und Microsoft Defender für Office 365, die wir empfehlen: **Standard** und **Strict**. Die Umgebung und die Anforderungen jedes Kunden unterscheiden sich, aber wir glauben, dass diese Filterungs Stufen dazu beitragen können, dass unerwünschte e-Mails in den meisten Fällen den Posteingang Ihrer Mitarbeiter erreichen.

Informationen zum automatischen anwenden der Standard-oder Strict-Einstellungen auf Benutzer finden Sie unter [Preset Security Policies in EoP und Microsoft Defender for Office 365](preset-security-policies.md).

> [!NOTE]
> Die Junk-e-Mail-Regel muss für Postfächer aktiviert sein, damit die Filterung ordnungsgemäß funktioniert. Sie ist standardmäßig aktiviert, Sie sollten Sie jedoch überprüfen, wenn die Filterung nicht zu funktionieren scheint. Weitere Informationen finden Sie unter [Konfigurieren der Einstellungen für Junk-E-Mails für Exchange Online-Postfächer in Office 365](configure-junk-email-settings-on-exo-mailboxes.md).

In diesem Artikel werden die Standardeinstellungen sowie die empfohlenen standardmäßigen und strengen Einstellungen beschrieben, die zum Schutz Ihrer Benutzer dienen.

> [!TIP]
> Das Office 365 Advanced Threat Protection Recommended Configuration Analyzer (Orca)-Modul für PowerShell kann Ihnen helfen (Administratoren), die aktuellen Werte dieser Einstellungen zu finden. Das **Get-ORCAReport-** Cmdlet generiert insbesondere eine Bewertung der Einstellungen für Antispam, Antiphishing und andere Nachrichten Hygiene. Sie können das Orca-Modul unter herunterladen <https://www.powershellgallery.com/packages/ORCA/> .

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Antispam-, Antischadsoftware-und Anti-Phishing-Schutz in EoP

Antispam-, Antischadsoftware-und Anti-Phishing-Funktionen sind EoP-Features, die von Administratoren konfiguriert werden können. Wir empfehlen die folgenden Standard-oder Strict-Konfigurationen.

### <a name="eop-anti-spam-policy-settings"></a>EoP-Anti-Spam-Richtlinieneinstellungen

Informationen zum Erstellen und Konfigurieren von Anti-Spam-Richtlinien finden Sie unter [configure Anti-Spam Policies in Office 365](configure-your-spam-filter-policies.md).

****

|Name des Sicherheitsfeatures|Standard|Standard|Strict|Kommentar|
|---|:---:|:---:|:---:|---|
|**Spam** erkennungsaktion <p> _Folgenden_|**Nachricht in Junk-E-Mail-Ordner verschieben** <p> `MoveToJmf`|**Nachricht in Junk-E-Mail-Ordner verschieben** <p> `MoveToJmf`|**Nachricht in Quarantäne verschieben** <p> `Quarantine`||
|Spam erkennungsaktion mit **hoher Vertrauens** Würdigkeit <p> _: Highconfidencespamaction_|**Nachricht in Junk-E-Mail-Ordner verschieben** <p> `MoveToJmf`|**Nachricht in Quarantäne verschieben** <p> `Quarantine`|**Nachricht in Quarantäne verschieben** <p> `Quarantine`||
|**Phishing-e-Mail-** erkennungsaktion <p> _PhishSpamAction_|**Nachricht in Junk-E-Mail-Ordner verschieben** <p> `MoveToJmf`|**Nachricht in Quarantäne verschieben** <p> `Quarantine`|**Nachricht in Quarantäne verschieben** <p> `Quarantine`||
|**Phishing-e-Mail-** erkennungsaktion mit hoher Vertrauenswürdigkeit <p> _HighConfidencePhishAction_|**Nachricht in Quarantäne verschieben** <p> `Quarantine`|**Nachricht in Quarantäne verschieben** <p> `Quarantine`|**Nachricht in Quarantäne verschieben** <p> `Quarantine`||
|**Massen-e-Mail-** erkennungsaktion <p> _BulkSpamAction_|**Nachricht in Junk-E-Mail-Ordner verschieben** <p> `MoveToJmf`|**Nachricht in Junk-E-Mail-Ordner verschieben** <p> `MoveToJmf`|**Nachricht in Quarantäne verschieben** <p> `Quarantine`||
|Massen-e-Mail-Schwellenwert <p> _BulkThreshold_|7 |6 |4 |Ausführliche Informationen finden Sie unter [Bulk Complaint Level (BCL) in Office 365](bulk-complaint-level-values.md).|
|Aufbewahrungszeitraum für Quarantäne <p> _QuarantineRetentionPeriod_|15 Tage|30 Tage|30 Tage||
|**Sicherheitstipps** <p> _InlineSafetyTipsEnabled_|Ein <p> `$true`|Ein <p> `$true`|Ein <p> `$true`||
|Zugelassene Absender <p> _AllowedSenders_|Keine|Keine|Keine||
|Zulässige Absenderdomänen <p> _AllowedSenderDomains_|Keine|Keine|Keine|Das Hinzufügen von Domänen zur Liste zulässiger Absender ist eine sehr schlechte Idee. Angreifer können Ihnen eine e-Mail senden, die andernfalls herausgefiltert würde. <p> Verwenden Sie [Spoof Intelligence](learn-about-spoof-intelligence.md) im Security & Compliance Center auf der Seite **Anti-Spam-Einstellungen** , um alle Absender zu überprüfen, die e-Mail-Adressen von Absendern in den e-Mail-Domänen Ihrer Organisation Spoofing oder Absender-e-Mail-Adressen in externen Domänen Spoofing durchführen.|
|Blockierte Absender <p> _BlockedSenders_|Keine|Keine|Keine||
|Blockierte Absenderdomänen <p> _BlockedSenderDomains_|Keine|Keine|Keine||
|**Spambenachrichtigungen für Endbenutzer aktivieren** <p> _EnableEndUserSpamNotifications_|Deaktiviert <p> `$false`|Aktiviert <p> `$true`|Aktiviert <p> `$true`||
|**Spambenachrichtigungen an Endbenutzer senden alle ... Tage** <p> _EndUserSpamNotificationFrequency_|3 Tage|3 Tage|3 Tage||
|**Spam zap** <p> _SpamZapEnabled_|Aktiviert <p> `$true`|Aktiviert <p> `$true`|Aktiviert <p> `$true`||
|**Phishing-zap** <p> _PhishZapEnabled_|Aktiviert <p> `$true`|Aktiviert <p> `$true`|Aktiviert <p> `$true`||
|_MarkAsSpamBulkMail_|Ein|Ein|Ein|Diese Einstellung ist nur in PowerShell verfügbar.|
|

Es gibt verschiedene andere Einstellungen für den erweiterten Spam Filter (ASF) in Anti-Spam-Richtlinien, die gerade veraltet sind. Weitere Informationen zu den Zeitrahmen für die Abschreibung dieser Features werden außerhalb dieses Artikels mitgeteilt.

Es wird empfohlen, dass Sie diese ASF-Einstellungen für **Standard** -und **Strict** -Stufen **Deaktivieren** . Weitere Informationen zu ASF-Einstellungen finden Sie unter [Advanced Spam Filter (ASF) Settings in Office 365](advanced-spam-filtering-asf-options.md).

****

|Name des Sicherheitsfeatures|Kommentar|
|---|---|
|**Bild Links zu Remotestandorten** (_IncreaseScoreWithImageLinks_)||
|**Numerische IP-Adresse in URL** (_IncreaseScoreWithNumericIps_)||
|**UL-Umleitung zu anderem Port** (_IncreaseScoreWithRedirectToOtherPort_)||
|**URL zu. biz oder. info Websites** (_IncreaseScoreWithBizOrInfoUrls_)||
|**Leere Nachrichten** (_MarkAsSpamEmptyMessages_)||
|**JavaScript oder VBScript in HTML** (_MarkAsSpamJavaScriptInHtml_)||
|**Frame-oder IFRAME-Tags in HTML** (_MarkAsSpamFramesInHtml_)||
|**Object-Tags in HTML** (_MarkAsSpamObjectTagsInHtml_)||
|**Einbetten von Tags in HTML** (_MarkAsSpamEmbedTagsInHtml_)||
|**Formulartags in HTML** (_MarkAsSpamFormTagsInHtml_)||
|**Webfehler im HTML-Format** (_MarkAsSpamWebBugsInHtml_)||
|**Anwenden einer vertraulichen Wörterliste** (_MarkAsSpamSensitiveWordList_)||
|**SPF-Eintrag: Hard Fail** (_MarkAsSpamSpfRecordHardFail_)||
|**Bedingte Sender ID-Filterung: schwerer Fehler** (_MarkAsSpamFromAddressAuthFail_)||
|**NDR** -Rückläufer (_MarkAsSpamNdrBackscatter_)||
|

#### <a name="eop-outbound-spam-policy-settings"></a>EoP-Einstellungen für ausgehende Spam Richtlinien

Informationen zum Erstellen und Konfigurieren von ausgehenden Spam Richtlinien finden Sie unter [Configure outbound Spam Filtering in Office 365](configure-the-outbound-spam-policy.md).

Weitere Informationen zu den standardmäßigen Sende Grenzwerten im Dienst finden Sie unter [sending Limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).

****

|Name des Sicherheitsfeatures|Standard|Standard|Strict|Kommentar|
|---|:---:|:---:|:---:|---|
|**Maximale Anzahl von Empfängern pro Benutzer: externer stündlicher Grenzwert** <p> _RecipientLimitExternalPerHour_|0|500|400|Der Standardwert 0 bedeutet, dass die Dienst Standardwerte verwendet werden.|
|**Maximale Anzahl von Empfängern pro Benutzer: interne stündliche Begrenzung** <p> _RecipientLimitInternalPerHour_|0|1000|800|Der Standardwert 0 bedeutet, dass die Dienst Standardwerte verwendet werden.|
|**Maximale Anzahl von Empfängern pro Benutzer: Tagesgrenzwert** <p> _RecipientLimitPerDay_|0|1000|800|Der Standardwert 0 bedeutet, dass die Dienst Standardwerte verwendet werden.|
|**Aktion, wenn ein Benutzer die Grenzwerte überschreitet** <p> _ActionWhenThresholdReached_|**Einschränken, dass der Benutzer e-Mails bis zum nächsten Tag sendet** <p> `BlockUserForToday`|**Einschränken des Sendens von e-Mails durch den Benutzer** <p> `BlockUser`|**Einschränken des Sendens von e-Mails durch den Benutzer** <p> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>EoP-Anti-Malware-Richtlinieneinstellungen

Informationen zum Erstellen und Konfigurieren von Anti-Malware-Richtlinien finden Sie unter [configure Anti-Malware Policies in Office 365](configure-anti-malware-policies.md).

****

|Name des Sicherheitsfeatures|Standard|Standard|Strict|Kommentar|
|---|:---:|:---:|:---:|---|
|**Möchten Sie Empfänger Benachrichtigen, wenn Ihre Nachrichten unter Quarantäne gestellt werden?** <p> _Aktion_|Nein <p> _DeleteMessage_|Nein <p> _DeleteMessage_|Nein <p> _DeleteMessage_|Wenn Schadsoftware in einer e-Mail-Anlage erkannt wird, wird die Nachricht isoliert und kann nur von einem Administrator freigegeben werden.|
|**Filter "allgemeine Anlagentypen"** <p> _EnableFileFilter_|Off <p> `$false`|Ein <p> `$true`|Ein <p> `$true`|Diese Einstellung isoliert Nachrichten, die ausführbare Anlagen basierend auf dem Dateityp enthalten, unabhängig vom Anlage Inhalt.|
|**Malware Zero-Hour Auto Purge** <p> _ZapEnabled_|Ein <p> `$true`|Ein <p> `$true`|Ein <p> `$true`||
|**Interne Absender** der nicht zugestellten Nachricht Benachrichtigen <p> _EnableInternalSenderNotifications_|Deaktiviert <p> `$false`|Deaktiviert <p> `$false`|Deaktiviert <p> `$false`||
|**Benachrichtigen externer Absender** der nicht zugestellten Nachricht <p> _EnableExternalSenderNotifications_|Deaktiviert <p> `$false`|Deaktiviert <p> `$false`|Deaktiviert <p> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>EoP Standardeinstellungen für Anti-Phishing-Richtlinien

Weitere Informationen zu diesen Einstellungen finden Sie unter [Spoof Settings](set-up-anti-phishing-policies.md#spoof-settings). Informationen zum Konfigurieren dieser Einstellungen finden Sie unter [configure Anti-Phishing Policies in EoP](configure-anti-phishing-policies-eop.md).

****

|Name des Sicherheitsfeatures|Standard|Standard|Strict|Kommentar|
|---|:---:|:---:|:---:|---|
|**Aktivieren des Schutzes gegen Spoofing** <p> _EnableAntispoofEnforcement_|Ein <p> `$true`|Ein <p> `$true`|Ein <p> `$true`||
|**Nicht authentifizierten Absender aktivieren** <p> _EnableUnauthenticatedSender_|Ein <p> `$true`|Ein <p> `$true`|Ein <p> `$true`|Fügt dem Foto des Absenders in Outlook ein Fragezeichen (?) für nicht identifizierte gefälschte Absender hinzu. Weitere Informationen finden Sie unter [Spoof Settings in Anti-Phishing Policies](set-up-anti-phishing-policies.md).|
|**Wenn e-Mails von Benutzern gesendet werden, die Ihre Domäne nicht spoofen dürfen** <p> _AuthenticationFailAction_|**Nachricht in die Junk-e-Mail-Ordner der Empfänger verlagern** <p> `MoveToJmf`|**Nachricht in die Junk-e-Mail-Ordner der Empfänger verlagern** <p> `MoveToJmf`|**Nachricht isolieren** <p> `Quarantine`|Diese Einstellung gilt für blockierte Absender in [Spoof Intelligence](learn-about-spoof-intelligence.md).|
|

## <a name="microsoft-defender-for-office-365-security"></a>Microsoft Defender für Office 365 Sicherheit

Zusätzliche Sicherheitsvorteile bieten Microsoft Defender für Office 365 Abonnement. Die neuesten Nachrichten und Informationen finden Sie unter [What es New in Defender for Office 365](whats-new-in-office-365-atp.md).

> [!IMPORTANT]
>
> - Die standardmäßige Anti-Phishing-Richtlinie in Microsoft Defender für Office 365 bietet [spoofschutz](set-up-anti-phishing-policies.md#spoof-settings) und Post Fach Intelligenz für alle Empfänger. Die anderen verfügbaren Features für [Identitätswechsel Schutz](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) und [Erweiterte Einstellungen](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) sind jedoch in der Standardrichtlinie nicht konfiguriert oder aktiviert. Um alle Schutzfunktionen zu aktivieren, ändern Sie die standardmäßige Anti-Phishing-Richtlinie, oder erstellen Sie zusätzliche Anti-Phishing-Richtlinien.
>
> - Es gibt keine Standardrichtlinien für sichere Links oder Richtlinien für sichere Anlagen, die alle Empfänger in der Organisation automatisch schützen. Um den Schutz zu erhalten, müssen Sie mindestens eine Richtlinie für sichere Links und Richtlinien für sichere Anlagen erstellen.
>
> - [ATP für SharePoint, OneDrive und Microsoft Teams](atp-for-spo-odb-and-teams.md) Protection und [Safe Documents](safe-docs.md) Protection haben keine Abhängigkeiten von Richtlinien zu sicheren Links.

Wenn Ihr Abonnement Microsoft Defender für Office 365 enthält oder wenn Sie Defender für Office 365 als Add-on erworben haben, legen Sie die folgenden Standard-oder Strict-Konfigurationen fest.

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Einstellungen für die Anti-Phishing-Richtlinie in Microsoft Defender für Office 365

EoP-Kunden erhalten grundlegende Anti-Phishing-Informationen wie zuvor beschrieben, Microsoft Defender für Office 365 enthält jedoch weitere Features und Steuerelemente, um Angriffe zu verhindern, zu erkennen und zu beheben. Informationen zum Erstellen und Konfigurieren dieser Richtlinien finden Sie unter [configure Anti-Phishing Policies in Defender for Office 365](configure-atp-anti-phishing-policies.md).

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Einstellungen für Identitätswechsel in Anti-Phishing-Richtlinien in Microsoft Defender für Office 365

Weitere Informationen zu diesen Einstellungen finden Sie unter [Identitätswechseleinstellungen in Anti-Phishing-Richtlinien in Microsoft Defender für Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Informationen zum Konfigurieren dieser Einstellungen finden Sie unter [configure Anti-Phishing Policies in Defender for Office 365](configure-atp-anti-phishing-policies.md).

****

|Name des Sicherheitsfeatures|Standard|Standard|Strict|Kommentar|
|---|:---:|:---:|:---:|---|
|Geschützte Benutzer: **zu schützende Benutzer hinzufügen** <p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|Off <p> `$false` <p> n/v|Ein <p> `$true` <p> \<list of users\>|Ein <p> `$true` <p> \<list of users\>|In Abhängigkeit von Ihrer Organisation wird empfohlen, Benutzer (Nachrichtenabsender) in Schlüsselrollen hinzuzufügen. Intern sind möglicherweise geschützte Absender Ihr CEO, CFO und andere Führungskräfte. Extern können geschützte Absender Ratsmitglieder oder ihren Verwaltungsrat umfassen.|
|Geschützte Domänen: **Automatisches einschließen der Domänen, die ich besitze** <p> _EnableOrganizationDomainsProtection_|Off <p> `$false`|Ein <p> `$true`|Ein <p> `$true`||
|Geschützte Domänen: **benutzerdefinierte Domänen einschließen** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|Off <p> `$false` <p> n/v|Ein <p> `$true` <p> \<list of domains\>|Ein <p> `$true` <p> \<list of domains\>|In Abhängigkeit von Ihrer Organisation wird empfohlen, Domänen (Absenderdomänen) hinzuzufügen, die Sie nicht besitzen, jedoch häufig mit interagieren.|
|Geschützte Benutzer: **Wenn e-Mail von einem imitierten Benutzer gesendet wird** <p> _TargetedUserProtectionAction_|**Keine Aktion anwenden** <p> `NoAction`|**Nachricht isolieren** <p> `Quarantine`|**Nachricht isolieren** <p> `Quarantine`||
|Geschützte Domänen: **Wenn e-Mails von einer imitierten Domäne gesendet werden** <p> _TargetedDomainProtectionAction_|**Keine Aktion anwenden** <p> `NoAction`|**Nachricht isolieren** <p> `Quarantine`|**Nachricht isolieren** <p> `Quarantine`||
|**Tipp für imitierte Benutzer anzeigen** <p> _EnableSimilarUsersSafetyTips_|Off <p> `$false`|Ein <p> `$true`|Ein <p> `$true`||
|**Tipp für imitierte Domänen anzeigen** <p> _EnableSimilarDomainsSafetyTips_|Off <p> `$false`|Ein <p> `$true`|Ein <p> `$true`||
|**Tipp für ungewöhnliche Zeichen anzeigen** <p> _EnableUnusualCharactersSafetyTips_|Off <p> `$false`|Ein <p> `$true`|Ein <p> `$true`||
|**Mailbox Intelligence aktivieren?** <p> _EnableMailboxIntelligence_|Ein <p> `$true`|Ein <p> `$true`|Ein <p> `$true`||
|**Aktivieren des Post Fach informationsbasierten Identitätswechsel Schutzes?** <p> _EnableMailboxIntelligenceProtection_|Off <p> `$false`|Ein <p> `$true`|Ein <p> `$true`||
|**Wenn e-Mails von einem imitierten Benutzer gesendet werden, der durch Post Fach Intelligenz geschützt ist** <p> _MailboxIntelligenceProtectionAction_|**Keine Aktion anwenden** <p> `NoAction`|**Nachricht in die Junk-e-Mail-Ordner der Empfänger verlagern** <p> `MoveToJmf`|**Nachricht isolieren** <p> `Quarantine`||
|**Trusted senders** <p> _ExcludedSenders_|Keine|Keine|Keine|In Abhängigkeit von Ihrer Organisation wird empfohlen, Benutzer hinzuzufügen, die aufgrund eines Identitätswechsels und nicht anderer Filter fälschlicherweise als Phishing markiert werden.|
|**Vertrauenswürdige Domänen** <p> _ExcludedDomains_|Keine|Keine|Keine|In Abhängigkeit von Ihrer Organisation wird empfohlen, Domänen hinzuzufügen, die aufgrund eines Identitätswechsels und nicht anderer Filter fälschlicherweise als Phishing gekennzeichnet werden.|
|

#### <a name="spoof-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Spoof-Einstellungen in Anti-Phishing-Richtlinien in Microsoft Defender für Office 365

Beachten Sie, dass es sich dabei um dieselben Einstellungen handelt, die in den [Antispameinstellungen in EoP](#eop-anti-spam-policy-settings)zur Verfügung stehen.

****

|Name des Sicherheitsfeatures|Standard|Standard|Strict|Kommentar|
|---|---|---|---|---|
|**Aktivieren des Schutzes gegen Spoofing** <p> _EnableAntispoofEnforcement_|Ein <p> `$true`|Ein <p> `$true`|Ein <p> `$true`||
|**Nicht authentifizierten Absender aktivieren** <p> _EnableUnauthenticatedSender_|Ein <p> `$true`|Ein <p> `$true`|Ein <p> `$true`|Fügt dem Foto des Absenders in Outlook ein Fragezeichen (?) für nicht identifizierte gefälschte Absender hinzu. Weitere Informationen finden Sie unter [Spoof Settings in Anti-Phishing Policies](set-up-anti-phishing-policies.md).|
|**Wenn e-Mails von Benutzern gesendet werden, die Ihre Domäne nicht spoofen dürfen** <p> _AuthenticationFailAction_|**Nachricht in die Junk-e-Mail-Ordner der Empfänger verlagern** <p> `MoveToJmf`|**Nachricht in die Junk-e-Mail-Ordner der Empfänger verlagern** <p> `MoveToJmf`|**Nachricht isolieren** <p> `Quarantine`|Diese Einstellung gilt für blockierte Absender in [Spoof Intelligence](learn-about-spoof-intelligence.md).|
|

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Erweiterte Einstellungen in Anti-Phishing-Richtlinien in Microsoft Defender für Office 365

Weitere Informationen zu dieser Einstellung finden Sie unter [Advanced Phishing Thresholds in Anti-Phishing Policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Informationen zum Konfigurieren dieser Einstellung finden Sie unter [configure Anti-Phishing Policies in Defender for Office 365](configure-atp-anti-phishing-policies.md).

****

|Name des Sicherheitsfeatures|Standard|Standard|Strict|Kommentar|
|---|:---:|:---:|:---:|---|
|**Erweiterte Phishing-Schwellenwerte** <p> _PhishThresholdLevel_|**1-Standard** <p> `1`|**2-aggressiv** <p> `2`|**3-aggressiver** <p> `3`||
|

### <a name="safe-links-settings"></a>Einstellungen für sichere Links

Sichere Links in Defender für Office 365 umfasst globale Einstellungen, die für alle Benutzer gelten, die in Active Safe Links-Richtlinien enthalten sind, und für Einstellungen, die für jede Richtlinie für sichere Links spezifisch sind. Weitere Informationen finden Sie unter [sichere Links in Defender für Office 365](atp-safe-links.md).

#### <a name="global-settings-for-safe-links"></a>Globale Einstellungen für sichere Links

Informationen zum Konfigurieren dieser Einstellungen finden Sie unter [Konfigurieren globaler Einstellungen für sichere Links in Defender für Office 365](configure-global-settings-for-safe-links.md).

In PowerShell verwenden Sie das Cmdlet " [Sets-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) " für diese Einstellungen.

****

|Name des Sicherheitsfeatures|Standard|Standard|Strict|Kommentar|
|---|:---:|:---:|:---:|---|
|**Verwenden von sicheren Links in: Office 365-Anwendungen** <p> _EnableSafeLinksForO365Clients_|Ein <p> `$true`|Ein <p> `$true`|Ein <p> `$true`|Verwenden Sie sichere Links in unterstützten Office 365-Desktop-und Mobile-Apps (IOS und Android). Weitere Informationen finden Sie unter [Einstellungen für sichere Links für Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).|
|**Nicht nachverfolgen, wenn Benutzer auf sichere Links klicken** <p> _TrackClicks_|Ein <p> `$false`|Off <p> `$true`|Off <p> `$true`|Durch Deaktivieren dieser Einstellung (Festlegen von _TrackClicks_ auf `$true` ) werden Benutzerklicks in unterstützten Office 365-apps verfolgt.|
|**Nicht zulassen, dass Benutzer über sichere Links auf die ursprüngliche URL klicken** <p> _AllowClickThrough_|Ein <p> `$false`|Ein <p> `$false`|Ein <p> `$false`|Durch Aktivieren dieser Einstellung (Festlegen von _AllowClickThrough_ auf `$false` ) wird verhindert, dass durch Klicken auf die ursprüngliche URL in unterstützten Office 365-apps.|
|

#### <a name="safe-links-policy-settings"></a>Richtlinieneinstellungen für sichere Links

Informationen zum Konfigurieren dieser Einstellungen finden Sie unter [Einrichten von Richtlinien zu sicheren Links in Microsoft Defender für Office 365](set-up-atp-safe-links-policies.md).

In PowerShell verwenden Sie die Cmdlets [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy) und [Sets-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) für diese Einstellungen.

> [!NOTE]
> Wie zuvor beschrieben, gibt es keine Standardrichtlinie für sichere Links. Die Werte in der Standardspalte sind die Standardwerte in neuen Richtlinien für sichere Links, die Sie erstellen.

****

|Name des Sicherheitsfeatures|Standard|Standard|Strict|Kommentar|
|---|:---:|:---:|:---:|---|
|**Auswählen der Aktion für unbekannte potenziell bösartige URLs in Nachrichten** <p> _IsEnabled_|Off <p> `$false`|Ein <p> `$true`|Ein <p> `$true`||
|**Auswählen der Aktion für unbekannte oder potenziell bösartige URLs in Microsoft Teams** <p> _EnableSafeLinksForTeams_|Off <p> `$false`|Ein <p> `$true`|Ein <p> `$true`||
|**Übernehmen der Echt Zeit-URL-Überprüfung auf verdächtige Links und Links, die auf Dateien verweisen** <p> _ScanUrls_|Off <p> `$false`|Ein <p> `$true`|Ein <p> `$true`||
|**Warten Sie, bis die URL-Überprüfung abgeschlossen ist, bevor Sie die Nachricht liefern** <p> _DeliverMessageAfterScan_|Off <p> `$false`|Ein <p> `$true`|Ein <p> `$true`||
|**Anwenden von sicheren Links auf e-Mail-Nachrichten, die innerhalb der Organisation gesendet werden** <p> _EnableForInternalSenders_|Off <p> `$false`|Ein <p> `$true`|Ein <p> `$true`||
|**Benutzerklicks nicht nachverfolgen** <p> _DoNotTrackUserClicks_|Off <p> `$false`|Off <p> `$false`|Off <p> `$false`|Durch Deaktivieren dieser Einstellung (Festlegen von _DoNotTrackUserClicks_ auf `$false` ) werden Benutzerklicks nachverfolgt.|
|**Benutzer dürfen nicht auf die ursprüngliche URL klicken.** <p> _DoNotAllowClickThrough_|Off <p> `$false`|Ein <p> `$true`|Ein <p> `$true`|Durch Aktivieren dieser Einstellung (Festlegen von _DoNotAllowClickThrough_ auf `$true` ) wird verhindert, dass Sie die ursprüngliche URL durch klicken.|
|

### <a name="safe-attachments-settings"></a>Einstellungen für sichere Anlagen

Sichere Anlagen in Microsoft Defender für Office 365 umfasst globale Einstellungen ohne Beziehung zu Richtlinien zu sicheren Anlagen und Einstellungen, die für jede Richtlinie für sichere Links spezifisch sind. Weitere Informationen finden Sie unter [sichere Anlagen in Defender für Office 365](atp-safe-attachments.md).

#### <a name="global-settings-for-safe-attachments"></a>Globale Einstellungen für sichere Anlagen

Informationen zum Konfigurieren dieser Einstellungen finden Sie unter [Aktivieren von ATP für SharePoint, OneDrive und Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) und [sichere Dokumente in Microsoft 365 E5](safe-docs.md).

In PowerShell verwenden Sie das Cmdlet " [Sets-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) " für diese Einstellungen.

****

|Name des Sicherheitsfeatures|Standard|Standard|Strict|Kommentar|
|---|:---:|:---:|:---:|---|
|**Aktivieren von ATP für SharePoint, OneDrive und Microsoft Teams** <p> _EnableATPForSPOTeamsODB_|Ein <p> `$true`|Ein <p> `$true`||
|**Aktivieren sicherer Dokumente für Office-Clients**<bt/><br/> _EnableSafeDocs_|Ein <p> `$true`|Ein <p> `$true`|Diese Einstellung ist nur mit Microsoft 365 E5-oder Microsoft 365 E5-Sicherheits Lizenzen verfügbar. Weitere Informationen finden Sie unter [sichere Dokumente in Microsoft Defender für Office 365](safe-docs.md).|
|**Personen können durch die geschützte Ansicht klicken, selbst wenn die Datei von sicheren Dokumenten als bösartig gekennzeichnet** wurde. <bt/><br/> _AllowSafeDocsOpen_|Off <p> `$false`|Off <p> `$false`|Diese Einstellung bezieht sich auf sichere Dokumente.|
|

#### <a name="safe-attachments-policy-settings"></a>Richtlinieneinstellungen für sichere Anlagen

Informationen zum Konfigurieren dieser Einstellungen finden Sie unter [Einrichten von Richtlinien für sichere Anlagen in Defender für Office 365](set-up-atp-safe-attachments-policies.md).

In PowerShell verwenden Sie die Cmdlets [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy) und [Sets-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) für diese Einstellungen.

> [!NOTE]
> Wie zuvor beschrieben, gibt es keine Standardrichtlinie für sichere Anlagen. Die Werte in der Standardspalte sind die Standardwerte in neuen Richtlinien für sichere Anlagen, die Sie erstellen.

****

|Name des Sicherheitsfeatures|Standard|Standard|Strict|Kommentar|
|---|:---:|:---:|:---:|---|
|**Sichere Anlagen unbekannte Malware Antwort** <p> _Aktion_|Blockieren <p> `Block`|Blockieren <p> `Block`|Blockieren <p> `Block`||
|**Umleitungs Anlage bei Erkennung** : **Umleitung aktivieren** <p> _Redirect_ <p> _RedirectAddress_|Aus, und es wurde keine e-Mail-Adresse angegeben. <p> `$true` <p> n/v|Ein, und geben Sie eine e-Mail-Adresse an. <p> `$true` <p> eine e-Mail-Adresse|Ein, und geben Sie eine e-Mail-Adresse an. <p> `$true` <p> eine e-Mail-Adresse|Umleiten von Nachrichten an einen Sicherheitsadministrator zur Überarbeitung.|
|**Wenden Sie die obige Auswahl an, wenn bei der Malwareüberprüfung nach Anlagen ein Timeout oder ein Fehler auftritt.** <p> _ActionOnError_|Ein <p> `$true`|Ein <p> `$true`|Ein <p> `$true`||
|

## <a name="related-articles"></a>Verwandte Artikel

- Suchen Sie nach bewährten Methoden für **Exchange-Nachrichtenfluss Regeln (auch bekannt als Transportregeln**)? Weitere Informationen finden Sie unter [bewährte Methoden für das Konfigurieren von Nachrichtenfluss Regeln in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices).

- Administratoren und Benutzer können falsch positive Ergebnisse (gute e-Mail-Nachrichten als ungültig markiert) und falsch negative (ungültige e-Mail-Nachrichten) zur Analyse an Microsoft senden. Weitere Informationen finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).

- Verwenden Sie diese Links, um Informationen zum **Einrichten** des [EoP-Diensts](set-up-your-eop-service.md)und zum **Konfigurieren** [von Microsoft Defender für Office 365](office-365-atp.md)zu erhalten. Vergessen Sie nicht die hilfreichen Anweisungen in "[Protect Against Threats in Office 365](protect-against-threats.md)".

- **Sicherheitsgrundlagen für Windows** finden Sie hier: [woher erhalte ich die Sicherheitsbasislinien?](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) für GPO/lokale Optionen und [Verwenden von Sicherheitsbasislinien zum Konfigurieren von Windows 10-Geräten in InTune für die](https://docs.microsoft.com/intune/protect/security-baselines) InTune-basierte Sicherheit. Schließlich steht ein Vergleich zwischen Microsoft Defender für Endpoint und Microsoft InTune-Sicherheitsbasislinien unter [vergleichen der Sicherheitsbasis Pläne von Microsoft Defender for Endpoint und Windows InTune](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)zur Verfügung.
