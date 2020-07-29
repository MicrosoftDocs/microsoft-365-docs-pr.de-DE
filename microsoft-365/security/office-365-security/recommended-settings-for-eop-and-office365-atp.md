---
title: Microsoft-Empfehlungen für EoP und Office 365 ATP-Sicherheitseinstellungen, Empfehlungen, Sender Policy Framework, domänenbasierte Nachrichtenberichterstattung und Konformität, DomainKeys identifizierte e-Mails, Schritte, Arbeitsweise, Sicherheitsbasislinien, Baselines für EoP, Baselines für ATP, Setup ATP, Setup EoP, configure ATP, configure EoP, Security Configuration
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: ''
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
ms.openlocfilehash: f34c4e0aad2413fdeb082c37f980e6e4548db6b3
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430375"
---
# <a name="recommended-settings-for-eop-and-office-365-atp-security"></a>Empfohlene Einstellungen für EoP und Office 365 ATP-Sicherheit

**Exchange Online Protection (EoP)** ist das Herzstück der Sicherheit für Microsoft 365-Abonnements und verhindert, dass böswillige e-Mails die Posteingänge ihrer Mitarbeiter erreichen. Bei neuen, anspruchsvolleren Angriffen, die täglich auftreten, sind häufig verbesserte Schutzmaßnahmen erforderlich. **Office 365 Advanced Threat Protection (ATP)** ATP-Plan 1 oder ATP-Plan 2 enthalten zusätzliche Features, die Administratoren mehr Ebenen der Sicherheit, Steuerung und Untersuchung bieten.

Obwohl wir Sicherheitsadministratoren die Möglichkeit geben, Ihre Sicherheitseinstellungen anzupassen, gibt es zwei Sicherheitsstufen in EoP und Office 365 ATP, die wir empfehlen: **Standard** und **Strict**. Die Umgebung und die Anforderungen jedes Kunden unterscheiden sich, aber wir glauben, dass diese Ebenen der e-Mail-Filterkonfigurationen dazu beitragen können, dass unerwünschte e-Mails in den meisten Fällen den Posteingang Ihrer Mitarbeiter erreichen.

Informationen zum automatischen anwenden der Standard-oder Strict-Einstellungen auf Benutzer finden Sie unter [Preset Security Policies in EoP und Office 365 ATP](preset-security-policies.md).

> [!IMPORTANT]
> Die Junk-e-Mail-Regel muss für ein Postfach aktiviert sein, damit die Filterung ordnungsgemäß funktioniert. Sie ist standardmäßig aktiviert, Sie sollten Sie jedoch überprüfen, wenn die Filterung nicht zu funktionieren scheint. Weitere Informationen finden Sie unter [Konfigurieren der Einstellungen für Junk-E-Mails für Exchange Online-Postfächer in Office 365](configure-junk-email-settings-on-exo-mailboxes.md).

In diesem Thema werden diese von Microsoft empfohlenen Einstellungen beschrieben, die zum Schutz Ihrer Benutzer dienen.

> [!TIP]
> Es gibt ein neues PowerShell-Modul, das Sie als Office 365 Advanced Threat Protection Recommended Configuration Analyzer (Orca) herunterladen können, mit dem einige dieser Einstellungen ermittelt werden können. Wenn Sie als Administrator in Ihrem Mandanten ausgeführt wird, hilft Get-ORCAReport bei der Erstellung einer Bewertung der Anti-Spam-, Anti-Phishing-und anderer Nachrichten Hygiene Einstellungen. Sie können dieses Modul unter herunterladen https://www.powershellgallery.com/packages/ORCA/ .

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Antispam-, Antischadsoftware-und Anti-Phishing-Schutz in EoP

Antispam-, Antischadsoftware-und Anti-Phishing-Funktionen sind Features von EoP, die von Administratoren konfiguriert werden können. Wir empfehlen die folgenden Konfigurationen.

### <a name="eop-anti-spam-policy-settings"></a>EoP-Anti-Spam-Richtlinieneinstellungen

Informationen zum Erstellen und Konfigurieren von Anti-Spam-Richtlinien finden Sie unter [configure Anti-Spam Policies in Office 365](configure-your-spam-filter-policies.md).

|Name des Sicherheitsfeatures|Standard|Strict|Kommentar|
|---|---|---|---|
|**Spam** erkennungsaktion <br/><br/> _Folgenden_|**Nachricht in Junk-E-Mail-Ordner verschieben** <br/><br/> `MoveToJmf`|**Nachricht in Quarantäne verschieben** <br/><br/> `Quarantine`||
|Spam erkennungsaktion mit **hoher Vertrauens** Würdigkeit <br/><br/> _: Highconfidencespamaction_|**Nachricht in Quarantäne verschieben** <br/><br/> `Quarantine`|**Nachricht in Quarantäne verschieben** <br/><br/> `Quarantine`||
|**Phishing-e-Mail-** erkennungsaktion <br/><br/> _PhishSpamAction_|**Nachricht in Quarantäne verschieben** <br/><br/> `Quarantine`|**Nachricht in Quarantäne verschieben** <br/><br/> `Quarantine`||
|**Phishing-e-Mail-** erkennungsaktion mit hoher Vertrauenswürdigkeit <br/><br/> _HighConfidencePhishAction_|**Nachricht in Quarantäne verschieben** <br/><br/> `Quarantine`|**Nachricht in Quarantäne verschieben** <br/><br/> `Quarantine`||
|**Massen-e-Mail-** erkennungsaktion <br/><br/> _BulkSpamAction_|**Nachricht in Junk-E-Mail-Ordner verschieben** <br/><br/> `MoveToJmf`|**Nachricht in Quarantäne verschieben** <br/><br/> `Quarantine`||
|Massen-e-Mail-Schwellenwert <br/><br/> _BulkThreshold_|6 |4 |Der Standardwert ist derzeit 7, aber es wird empfohlen, dass Sie ihn in 6 ändern. Ausführliche Informationen finden Sie unter [Bulk Complaint Level (BCL) in Office 365](bulk-complaint-level-values.md).|
|Aufbewahrungszeitraum für Quarantäne <br/><br/> _QuarantineRetentionPeriod_|30 Tage|30 Tage||
|**Sicherheitstipps** <br/><br/> _InlineSafetyTipsEnabled_|Ein <br/><br/> `$true`|Ein <br/><br/> `$true`||
|Zugelassene Absender <br/><br/> _AllowedSenders_|Keine|Keine||
|Zulässige Absenderdomänen <br/><br/> _AllowedSenderDomains_|Keine|Keine|Das Hinzufügen von Domänen, die Sie besitzen (auch als _akzeptierte Domänen_bezeichnet), ist in der Liste der zulässigen Absender nicht erforderlich. Tatsächlich wird es als hohes Risiko betrachtet, da es Möglichkeiten für ungültige Akteure schafft, Ihnen e-Mails zu senden, die andernfalls herausgefiltert würden. Verwenden Sie [Spoof Intelligence](learn-about-spoof-intelligence.md) im Security & Compliance Center auf der Seite **Anti-Spam-Einstellungen** , um alle Absender zu überprüfen, die e-Mail-Adressen von Absendern in den e-Mail-Domänen Ihrer Organisation Spoofing oder Absender-e-Mail-Adressen in externen Domänen Spoofing durchführen.|
|Blockierte Absender <br/><br/> _BlockedSenders_|Keine|Keine||
|Blockierte Absenderdomänen <br/><br/> _BlockedSenderDomains_|Keine|Keine||
|**Spambenachrichtigungen für Endbenutzer aktivieren** <br/><br/> _EnableEndUserSpamNotifications_|Aktiviert <br/><br/> `$true`|Aktiviert <br/><br/> `$true`||
|**Spambenachrichtigungen an Endbenutzer senden alle ... Tage** <br/><br/> _EndUserSpamNotificationFrequency_|3 Tage|3 Tage||
|**Spam zap** <br/><br/> _SpamZapEnabled_|Aktiviert <br/><br/> `$true`|Aktiviert <br/><br/> `$true`||
|**Phishing-zap** <br/><br/> _PhishZapEnabled_|Aktiviert <br/><br/> `$true`|Aktiviert <br/><br/> `$true`||
|_MarkAsSpamBulkMail_|Ein|Ein|Diese Einstellung ist nur in PowerShell verfügbar.|
|

Es gibt verschiedene andere Einstellungen für den erweiterten Spam Filter (ASF) in Anti-Spam-Richtlinien, die gerade veraltet sind. Weitere Informationen zu den Zeitrahmen für die Abschreibung dieser Features werden außerhalb dieses Themas mitgeteilt.

Es wird empfohlen, dass Sie diese ASF-Einstellungen für **Standard** -und **Strict** -Stufen **Deaktivieren** . Weitere Informationen zu ASF-Einstellungen finden Sie unter [Advanced Spam Filter (ASF) Settings in Office 365](advanced-spam-filtering-asf-options.md).

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

Weitere Informationen zu den standardmäßigen Sende Grenzwerten im Dienst finden Sie unter [Senden von Grenz](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1) Werten

|Name des Sicherheitsfeatures|Standard|Strict|Kommentar|
|---|---|---|---|
|**Maximale Anzahl von Empfängern pro Benutzer: externer stündlicher Grenzwert** <br/><br/> _RecipientLimitExternalPerHour_|500|400||
|**Maximale Anzahl von Empfängern pro Benutzer: interne stündliche Begrenzung** <br/><br/> _RecipientLimitInternalPerHour_|1000|800||
|**Maximale Anzahl von Empfängern pro Benutzer: Tagesgrenzwert** <br/><br/> _RecipientLimitPerDay_|1000|800||
|**Aktion, wenn ein Benutzer die Grenzwerte überschreitet** <br/><br/> _ActionWhenThresholdReached_|**Einschränken des Sendens von e-Mails durch den Benutzer** <br/><br/> `BlockUser`|**Einschränken des Sendens von e-Mails durch den Benutzer** <br/><br/> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>EoP-Anti-Malware-Richtlinieneinstellungen

Informationen zum Erstellen und Konfigurieren von Anti-Malware-Richtlinien finden Sie unter [configure Anti-Malware Policies in Office 365](configure-anti-malware-policies.md).

|Name des Sicherheitsfeatures|Standard|Strict|Kommentar|
|---|---|---|---|
|**Möchten Sie Empfänger Benachrichtigen, wenn Ihre Nachrichten unter Quarantäne gestellt werden?** <br/><br/> _Action_|Nein <br/><br/> _DeleteMessage_|Nein <br/><br/> _DeleteMessage_|Wenn Schadsoftware in einer e-Mail-Anlage erkannt wird, wird die Nachricht isoliert und kann nur von einem Administrator freigegeben werden.|
|**Filter "allgemeine Anlagentypen"** <br/><br/> _EnableFileFilter_|Ein <br/><br/> `$true`|Ein <br/><br/> `$true`|Diese Einstellung isoliert Nachrichten, die ausführbare Anlagen basierend auf dem Dateityp enthalten, unabhängig vom Anlage Inhalt.|
|**Malware Zero-Hour Auto Purge** <br/><br/> _ZapEnabled_|Ein <br/><br/> `$true`|Ein <br/><br/> `$true`||
|**Interne Absender** der nicht zugestellten Nachricht Benachrichtigen <br/><br/> _EnableInternalSenderNotifications_|Deaktiviert <br/><br/> `$false`|Deaktiviert <br/><br/> `$false`||
|**Benachrichtigen externer Absender** der nicht zugestellten Nachricht <br/><br/> _EnableExternalSenderNotifications_|Deaktiviert <br/><br/> `$false`|Deaktiviert <br/><br/> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>EoP Standardeinstellungen für Anti-Phishing-Richtlinien

Weitere Informationen zu diesen Einstellungen finden Sie unter [Spoof Settings](set-up-anti-phishing-policies.md#spoof-settings). Informationen zum Konfigurieren dieser Einstellungen finden Sie unter [configure Anti-Phishing Policies in EoP](configure-anti-phishing-policies-eop.md).

|Name des Sicherheitsfeatures|Standard|Strict|Kommentar|
|---|---|---|---|
|**Aktivieren des Schutzes gegen Spoofing** <br/><br/> _EnableAntispoofEnforcement_|Ein <br/><br/> `$true`|Ein <br/><br/> `$true`||
|**Nicht authentifizierten Absender aktivieren** <br/><br/> _EnableUnauthenticatedSender_|Ein <br/><br/> `$true`|Ein <br/><br/> `$true`|Fügt dem Foto des Absenders in Outlook ein Fragezeichen (?) für nicht identifizierte gefälschte Absender hinzu. Weitere Informationen finden Sie unter [Spoof Settings in Anti-Phishing Policies](set-up-anti-phishing-policies.md).|
|**Wenn e-Mails von Benutzern gesendet werden, die Ihre Domäne nicht spoofen dürfen** <br/><br/> _AuthenticationFailAction_|**Nachricht in die Junk-e-Mail-Ordner der Empfänger verlagern** <br/><br/> `MoveToJmf`|**Nachricht isolieren** <br/><br/> `Quarantine`|Dies gilt für blockierte Absender in [Spoof Intelligence](learn-about-spoof-intelligence.md).|
|

## <a name="office-365-advanced-threat-protection-security"></a>Office 365 Advanced Threat Protection-Sicherheit

Zusätzliche Sicherheitsvorteile bieten ein Office 365 Advanced Threat Protection (ATP)-Abonnement. Die neuesten Nachrichten und Informationen finden Sie unter [What es New in Office 365 ATP](whats-new-in-office-365-atp.md).

Office 365 ATP enthält die Richtlinien für sichere Anlagen und sichere Links, um zu verhindern, dass e-Mails mit potenziell böswilligen Anlagen zugestellt werden, und um Benutzer daran zu hindern, auf potenziell nicht sichere URLs zu klicken.

> [!IMPORTANT]
> Advanced Anti-Phishing ist einer der Vorteile eines Office 365 ATP-Abonnements. Obwohl es standardmäßig aktiviert ist, ***müssen*** Sie mindestens eine Anti-Phishing-Richtlinie konfigurieren, bevor Sie mit dem Filtern von e-Mails beginnen kann. Vergessen Sie nicht, die Anti-Phishing-Richtlinien zu konfigurieren, könnte Benutzern riskante e-Mails verfügbar gemacht werden. Achten Sie darauf, Ihre Anti-Phishing-Richtlinien zu konfigurieren, nachdem Sie ein Office 365 ATP-Abonnement hinzugefügt haben.

Wenn Sie Ihrem EoP ein Office 365 ATP-Abonnement hinzugefügt haben, legen Sie die folgenden Konfigurationen fest.

### <a name="office-atp-anti-phishing-policy-settings"></a>Office ATP-Einstellungen für Anti-Phishing-Richtlinien

EoP-Kunden erhalten grundlegende Anti-Phishing-Funktionen, wie zuvor beschrieben, aber Office 365 ATP umfasst weitere Features und Steuerelemente, um das verhindern, erkennen und Beheben von Angriffen zu unterstützen. Informationen zum Erstellen und Konfigurieren dieser Richtlinien finden Sie unter [configure ATP Anti-Phishing Policies in Office 365](configure-atp-anti-phishing-policies.md).

#### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a>Identitätswechseleinstellungen in ATP-Richtlinien zum Schutz vor Phishing

Weitere Informationen zu diesen Einstellungen finden Sie unter [Identitätswechseleinstellungen in ATP-Richtlinien zum Schutz vor Phishing](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies). Informationen zum Konfigurieren dieser Einstellungen finden Sie unter [configure ATP Anti-Phishing Policies](configure-atp-anti-phishing-policies.md).

|Name des Sicherheitsfeatures|Standard|Strict|Kommentar|
|---|---|---|---|
|Geschützte Benutzer: **zu schützende Benutzer hinzufügen** <br/><br/> _EnableTargetedUserProtection_ <br/><br/> _TargetedUsersToProtect_|Ein <br/><br/> `$true` <br/><br/> \<list of users\>|Ein <br/><br/> `$true` <br/><br/> \<list of users\>|Hängt von Ihrer Organisation ab, es wird jedoch empfohlen, Benutzer in Schlüsselrollen hinzuzufügen. Intern sind dies möglicherweise Ihr CEO, CFO und andere Führungskräfte. Diese können extern auch Ratsmitglieder oder ihren Verwaltungsrat umfassen.|
|Geschützte Domänen: **Automatisches einschließen der Domänen, die ich besitze** <br/><br/> _EnableOrganizationDomainsProtection_|Ein <br/><br/> `$true`|Ein <br/><br/> `$true`||
|Geschützte Domänen: **benutzerdefinierte Domänen einschließen** <br/><br/> _EnableTargetedDomainsProtection_ <br/><br/> _TargetedDomainsToProtect_|Ein <br/><br/> `$true` <br/><br/> \<list of domains\>|Ein <br/><br/> `$true` <br/><br/> \<list of domains\>|Hängt von Ihrer Organisation ab, es wird jedoch empfohlen, Domänen hinzuzufügen, mit denen Sie häufig interagieren, die Sie nicht besitzen.|
|Geschützte Benutzer: **Wenn e-Mail von einem imitierten Benutzer gesendet wird** <br/><br/> _TargetedUserProtectionAction_|**Nachricht isolieren** <br/><br/> `Quarantine`|**Nachricht isolieren** <br/><br/> `Quarantine`||
|Geschützte Domänen: **Wenn e-Mails von einer imitierten Domäne gesendet werden** <br/><br/> _TargetedDomainProtectionAction_|**Nachricht isolieren** <br/><br/> `Quarantine`|**Nachricht isolieren** <br/><br/> `Quarantine`||
|**Tipp für imitierte Benutzer anzeigen** <br/><br/> _EnableSimilarUsersSafetyTips_|Ein <br/><br/> `$true`|Ein <br/><br/> `$true`||
|**Tipp für imitierte Domänen anzeigen** <br/><br/> _EnableSimilarDomainsSafetyTips_|Ein <br/><br/> `$true`|Ein <br/><br/> `$true`||
|**Tipp für ungewöhnliche Zeichen anzeigen** <br/><br/> _EnableUnusualCharactersSafetyTips_|Ein <br/><br/> `$true`|Ein <br/><br/> `$true`||
|**Mailbox Intelligence aktivieren?** <br/><br/> _EnableMailboxIntelligence_|Ein <br/><br/> `$true`|Ein <br/><br/> `$true`||
|**Aktivieren des Post Fach informationsbasierten Identitätswechsel Schutzes?** <br/><br/> _EnableMailboxIntelligenceProtection_|Ein <br/><br/> `$true`|Ein <br/><br/> `$true`||
|**Wenn e-Mails von einem imitierten Benutzer gesendet werden, der durch Post Fach Intelligenz geschützt ist** <br/><br/> _MailboxIntelligenceProtectionAction_|**Nachricht in die Junk-e-Mail-Ordner der Empfänger verlagern** <br/><br/> `MoveToJmf`|**Nachricht isolieren** <br/><br/> `Quarantine`||
|**Trusted senders** <br/><br/> _ExcludedSenders_|Keine|Keine|Hängt von Ihrer Organisation ab, es wird jedoch empfohlen, Benutzer hinzuzufügen, die aufgrund eines Identitätswechsels und nicht anderer Filter fälschlicherweise als Phishing gekennzeichnet werden.|
|**Vertrauenswürdige Domänen** <br/><br/> _ExcludedDomains_|Keine|Keine|Hängt von Ihrer Organisation ab, es wird jedoch empfohlen, Domänen hinzuzufügen, die aufgrund eines Identitätswechsels und nicht anderer Filter fälschlicherweise als Phishing gekennzeichnet werden.|
|

#### <a name="spoof-settings-in-atp-anti-phishing-policies"></a>Spoofeinstellungen in ATP-Anti-Phishing-Richtlinien

Beachten Sie, dass es sich dabei um dieselben Einstellungen handelt, die in den [Antispameinstellungen in EoP](#eop-anti-spam-policy-settings)zur Verfügung stehen.

|Name des Sicherheitsfeatures|Standard|Strict|Kommentar|
|---|---|---|---|
|**Aktivieren des Schutzes gegen Spoofing** <br/><br/> _EnableAntispoofEnforcement_|Ein <br/><br/> `$true`|Ein <br/><br/> `$true`||
|**Nicht authentifizierten Absender aktivieren** <br/><br/> _EnableUnauthenticatedSender_|Ein <br/><br/> `$true`|Ein <br/><br/> `$true`|Fügt dem Foto des Absenders in Outlook ein Fragezeichen (?) für nicht identifizierte gefälschte Absender hinzu. Weitere Informationen finden Sie unter [Spoof Settings in Anti-Phishing Policies](set-up-anti-phishing-policies.md).|
|**Wenn e-Mails von Benutzern gesendet werden, die Ihre Domäne nicht spoofen dürfen** <br/><br/> _AuthenticationFailAction_|**Nachricht in die Junk-e-Mail-Ordner der Empfänger verlagern** <br/><br/> `MoveToJmf`|**Nachricht isolieren** <br/><br/> `Quarantine`|Dies gilt für blockierte Absender in [Spoof Intelligence](learn-about-spoof-intelligence.md).|
|

#### <a name="advanced-settings-in-atp-anti-phishing-policies"></a>Erweiterte Einstellungen in ATP-Richtlinien für Anti-Phishing

Weitere Informationen zu dieser Einstellung finden Sie unter [Advanced Phishing Thresholds in ATP Anti-Phishing Policies](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies). Informationen zum Konfigurieren dieser Einstellung finden Sie unter [configure ATP Anti-Phishing Policies](configure-atp-anti-phishing-policies.md).

|Name des Sicherheitsfeatures|Standard|Strict|Kommentar|
|---|---|---|---|
|**Erweiterte Phishing-Schwellenwerte** <br/><br/> _PhishThresholdLevel_|**2-aggressiv** <br/><br/> `2`|**3-aggressiver** <br/><br/> `3`||

### <a name="atp-safe-links-policy-settings"></a>Richtlinieneinstellungen für ATP-sichere Links

Informationen zum Konfigurieren dieser Einstellungen finden Sie unter [Einrichten Office 365 ATP-Richtlinien für sichere Links](set-up-atp-safe-links-policies.md).

#### <a name="safe-links-policy-settings-in-the-default-policy-for-all-users"></a>Richtlinieneinstellungen für sichere Links in der Standardrichtlinie für alle Benutzer

**Hinweis**: in PowerShell verwenden Sie das Cmdlet " [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) " für diese Einstellungen.

|Name des Sicherheitsfeatures|Standard|Strict|Kommentar|
|---|---|---|---|
|**Verwenden von sicheren Links in: Office 365-Anwendungen** <br/><br/> _EnableSafeLinksForO365Clients_|Ein <br/><br/> `$true`|Ein <br/><br/> `$true`|Verwenden Sie ATP-sichere Links in Office 365-Desktop-und Mobile-Clients (IOS und Android).|
|**Verwenden von sicheren Links in: Office-Webzugriffs-Gefährten** <br/><br/> _EnableSafeLinksForWebAccessCompanion_|Ein <br/><br/> `$true`|Ein <br/><br/> `$true`|Verwenden Sie ATP-sichere Links in Office-Webanwendungen.|
|**Nicht nachverfolgen, wenn Benutzer auf sichere Links klicken** <br/><br/> _TrackClicks_|Off <br/><br/> `$true`|Off <br/><br/> `$true`||
|**Nicht zulassen, dass Benutzer über sichere Links auf die ursprüngliche URL klicken** <br/><br/> _AllowClickThrough_|Ein <br/><br/> `$false`|Ein <br/><br/> `$false`||
|

#### <a name="safe-links-policy-settings-in-custom-policies-for-specific-users"></a>Richtlinieneinstellungen für sichere Links in benutzerdefinierten Richtlinien für bestimmte Benutzer

**Hinweis**: in PowerShell verwenden Sie die Cmdlets [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy) und [Sets-SafeLinksPolicy] ( https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy ] für diese Einstellungen.

|Name des Sicherheitsfeatures|Standard|Strict|Kommentar|
|---|---|---|---|
|**Auswählen der Aktion für unbekannte potenziell bösartige URLs in Nachrichten** <br/><br/> _IsEnabled_|Ein <br/><br/> `$true`|Ein <br/><br/> `$true`||
|**Auswählen der Aktion für unbekannte oder potenziell bösartige URLs in Microsoft Teams** <br/><br/> _EnableSafeLinksForTeams_|Ein <br/><br/> `$true`|Ein <br/><br/> `$true`||
|**Übernehmen der Echt Zeit-URL-Überprüfung auf verdächtige Links und Links, die auf Dateien verweisen** <br/><br/> _ScanUrls_|Ein <br/><br/> `$true`|Ein <br/><br/> `$true`||
|**Warten Sie, bis die URL-Überprüfung abgeschlossen ist, bevor Sie die Nachricht liefern** <br/><br/> _DeliverMessageAfterScan_|Ein <br/><br/> `$true`|Ein <br/><br/> `$true`||
|**Anwenden von sicheren Links auf e-Mail-Nachrichten, die innerhalb der Organisation gesendet werden** <br/><br/> _EnableForInternalSenders_|Ein <br/><br/> `$true`|Ein <br/><br/> `$true`||
|**Nicht nachverfolgen, wenn Benutzer auf sichere Links klicken** <br/><br/> _DoNotTrackUserClicks_|Off <br/><br/> `$false`|Off <br/><br/> `$false`|
|**Nicht zulassen, dass Benutzer über sichere Links auf die ursprüngliche URL klicken** <br/><br/> _DoNotAllowClickThrough_|Ein <br/><br/> `$true`|Ein <br/><br/> `$true`||
|

### <a name="atp-safe-attachments-policy-settings"></a>Richtlinieneinstellungen für ATP-sichere Anlagen

Informationen zum Konfigurieren dieser Einstellungen finden Sie unter [Einrichten Office 365 ATP-Richtlinien für sichere Anlagen](set-up-atp-safe-attachments-policies.md).

#### <a name="safe-attachments-policy-settings-in-the-default-policy-for-all-users"></a>Richtlinieneinstellungen für sichere Anlagen in der Standardrichtlinie für alle Benutzer

**Hinweis**: in PowerShell verwenden Sie das Cmdlet " [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) " für diese Einstellungen.

|Name des Sicherheitsfeatures|Standard|Strict|Kommentar|
|---|---|---|---|
|**Aktivieren von ATP für SharePoint, OneDrive und Microsoft Teams** <br/><br/> _EnableATPForSPOTeamsODB_|Ein <br/><br/> `$true`|Ein <br/><br/> `$true`||
|**Aktivieren sicherer Dokumente für Office-Clients**<bt/><br/> _EnableSafeDocs_|Ein <br/><br/> `$true`|Ein <br/><br/> `$true`||Diese Einstellung ist nur mit Microsoft 365 E5-oder Microsoft 365 E5-Sicherheits Lizenzen verfügbar. Weitere Informationen finden Sie unter [sichere Dokumente in Office 365 Advanced Threat Protection](safe-docs.md).|
|**Personen können durch die geschützte Ansicht klicken, selbst wenn die Datei von sicheren Dokumenten als bösartig gekennzeichnet** wurde.<bt/><br/> _AllowSafeDocsOpen_|Off <br/><br/> `$false`|Off <br/><br/> `$false`||
|

#### <a name="safe-attachments-policy-settings-in-custom-policies-for-specific-users"></a>Richtlinieneinstellungen für sichere Anlagen in benutzerdefinierten Richtlinien für bestimmte Benutzer

**Hinweis**: in PowerShell verwenden Sie die Cmdlets [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy) und [Sets-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) für diese Einstellungen.

|Name des Sicherheitsfeatures|Standard|Strict|Kommentar|
|---|---|---|---|
|**Sichere Anlagen unbekannte Malware Antwort** <br/><br/> _Action_|Block <br/><br/> `Block`|Block <br/><br/> `Block`||
|**Umleitungs Anlage bei Erkennung** : **Umleitung aktivieren** <br/><br/> _Redirect_ <br/><br/> _RedirectAddress_|Ein, und geben Sie eine e-Mail-Adresse an. <br/><br/> `$true` <br/><br/> eine e-Mail-Adresse|Ein, und geben Sie eine e-Mail-Adresse an. <br/><br/> `$true` <br/><br/> eine e-Mail-Adresse|Umleiten von Nachrichten an einen Sicherheitsadministrator zur Überarbeitung.|
|**Wenden Sie die obige Auswahl an, wenn bei der Malwareüberprüfung nach Anlagen ein Timeout oder ein Fehler auftritt.** <br/><br/> _ActionOnError_|Ein <br/><br/> `$true`|Ein <br/><br/> `$true`||
|

## <a name="related-topics"></a>Verwandte Themen

- Suchen Sie nach bewährten Methoden mit **Exchange-Nachrichtenfluss/Exchange-Transport Regeln**? Ausführliche Informationen finden Sie in [diesem Artikel](https://docs.microsoft.com/microsoft-365/security/office-365-security/best-practices-for-configuring-eop) .

- Administratoren und Benutzer können falsch positive Ergebnisse (gute e-Mail-Nachrichten als ungültig markiert) und falsch negative (ungültige e-Mail-Nachrichten) zur Analyse an Microsoft senden. Weitere Informationen finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).

- Verwenden Sie diese Links, um Informationen zum **Einrichten** des [EoP-Diensts](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-your-eop-service)und zum **Konfigurieren** [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)zu erhalten. (Vergessen Sie nicht, die hilfreichen Anweisungen unter "[Protect Against Threats in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)" anzuzeigen.)

- **Sicherheitsgrundlagen für Windows** [finden Sie hier für GPO](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) /lokale Optionen und für die Intune-basierte Sicherheit [hier](https://docs.microsoft.com/intune/protect/security-baselines). Schließlich finden Sie [hier](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)einen Vergleich zwischen Microsoft Defender Advanced Threat Protection (ATP) und Windows InTune-Sicherheitsbasislinien.
