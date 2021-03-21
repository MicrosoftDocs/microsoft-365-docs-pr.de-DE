---
title: Microsoft-Empfehlungen für EOP- und Defender for Office 365-Sicherheitseinstellungen
keywords: Office 365-Sicherheitsempfehlungen, Sender Policy Framework, Domänenbasierte Nachrichtenberichterstattung und -konformität, DomainKeys Identified Mail, Schritte, Funktionsweise, Sicherheitsgrundwerte, Baselines für EOP, Baselines für Defender for Office 365 , Einrichten von Defender für Office 365, Einrichten von EOP, Konfigurieren von Defender für Office 365, Konfigurieren von EOP, Sicherheitskonfiguration
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: ''
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Was sind bewährte Methoden für Exchange Online Protection (EOP) und Defender for Office 365-Sicherheitseinstellungen? Was sind die aktuellen Empfehlungen für Standardschutz? Was sollte verwendet werden, wenn Sie strenger sein möchten? Und welche Extras erhalten Sie, wenn Sie auch Defender für Office 365 verwenden?
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5beceebdc32c3bbc3073e595aa9d25f109cbe85a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926736"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>Empfohlene Einstellungen für EOP und Microsoft Defender für Office 365-Sicherheit

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

**Exchange Online Protection (EOP)** ist der Kern der Sicherheit für Microsoft 365-Abonnements und verhindert, dass schädliche E-Mails die Posteingange Ihrer Mitarbeiter erreichen. Da jedoch täglich neue, komplexere Angriffe entstehen, sind häufig verbesserte Schutzmaßnahmen erforderlich. **Microsoft Defender für Office 365** Plan 1 oder Plan 2 enthalten zusätzliche Features, die Administratoren mehr Ebenen an Sicherheit, Kontrolle und Untersuchung bieten.

Obwohl wir Sicherheitsadministratoren die Möglichkeit geben, ihre Sicherheitseinstellungen anzupassen, gibt es zwei Sicherheitsstufen in EOP und Microsoft Defender für Office 365, die wir empfehlen: **Standard** und **Strict**. Die Umgebung und die Anforderungen der einzelnen Kunden unterscheiden sich, aber wir sind der Meinung, dass diese Filterstufen dazu beitragen, zu verhindern, dass unerwünschte E-Mails in den meisten Situationen den Posteingang Ihrer Mitarbeiter erreichen.

Informationen zum automatischen Anwenden der Standard- oder Strikt-Einstellungen auf Benutzer finden Sie unter [Preset security policies in EOP and Microsoft Defender for Office 365](preset-security-policies.md).

> [!NOTE]
> Die Junk-E-Mail-Regel muss für Postfächer aktiviert sein, damit die Filterung ordnungsgemäß funktioniert. Es ist standardmäßig aktiviert, sie sollte jedoch überprüft werden, wenn die Filterung scheinbar nicht funktioniert. Weitere Informationen finden Sie unter [Konfigurieren der Einstellungen für Junk-E-Mails für Exchange Online-Postfächer in Office 365](configure-junk-email-settings-on-exo-mailboxes.md).

In diesem Artikel werden die Standardeinstellungen sowie die empfohlenen Standard- und Strict-Einstellungen beschrieben, um Ihre Benutzer zu schützen.

> [!TIP]
> Das Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)-Modul für PowerShell kann Ihnen (Administratoren) dabei helfen, die aktuellen Werte dieser Einstellungen zu finden. Insbesondere generiert das **Cmdlet Get-ORCAReport** eine Bewertung von Antispam-, Antiphishing- und anderen Nachrichtenhygieneeinstellungen. Sie können das ORCA-Modul unter <https://www.powershellgallery.com/packages/ORCA/> herunterladen.

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Antispam-, Malware- und Antiphishingschutz in EOP

Antispam, Schadsoftware und Antiphishing sind EOP-Features, die von Administratoren konfiguriert werden können. Wir empfehlen die folgenden Standard- oder Strict-Konfigurationen.

### <a name="eop-anti-spam-policy-settings"></a>EOP-Antispamrichtlinieneinstellungen

Informationen zum Erstellen und Konfigurieren von Antispamrichtlinien finden Sie unter [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).

****

|Name des Sicherheitsfeatures|Standard|Standard|Strict|Kommentar|
|---|:---:|:---:|:---:|---|
|**Spamerkennungsaktion** <p> _SpamAction_|**Nachricht in Junk-E-Mail-Ordner verschieben** <p> `MoveToJmf`|**Nachricht in Junk-E-Mail-Ordner verschieben** <p> `MoveToJmf`|**Nachricht in Quarantäne verschieben** <p> `Quarantine`||
|**Spamerkennungsaktion** mit hoher Vertrauenssicherheit <p> _HighConfidenceSpamAction_|**Nachricht in Junk-E-Mail-Ordner verschieben** <p> `MoveToJmf`|**Nachricht in Quarantäne verschieben** <p> `Quarantine`|**Nachricht in Quarantäne verschieben** <p> `Quarantine`||
|**Phishing-E-Mail-Erkennungsaktion** <p> _PhishSpamAction_|**Nachricht in Junk-E-Mail-Ordner verschieben** <p> `MoveToJmf`|**Nachricht in Quarantäne verschieben** <p> `Quarantine`|**Nachricht in Quarantäne verschieben** <p> `Quarantine`||
|**Phishing-E-Mail-Erkennungsaktion** mit hoher Vertrauen <p> _HighConfidencePhishAction_|**Nachricht in Quarantäne verschieben** <p> `Quarantine`|**Nachricht in Quarantäne verschieben** <p> `Quarantine`|**Nachricht in Quarantäne verschieben** <p> `Quarantine`||
|**Massen-E-Mail-Erkennungsaktion** <p> _BulkSpamAction_|**Nachricht in Junk-E-Mail-Ordner verschieben** <p> `MoveToJmf`|**Nachricht in Junk-E-Mail-Ordner verschieben** <p> `MoveToJmf`|**Nachricht in Quarantäne verschieben** <p> `Quarantine`||
|Schwellenwert für Massen-E-Mails <p> _BulkThreshold_|7 |6 |4 |Weitere Informationen finden Sie unter [Bulk Complaint Level (BCL) in Office 365](bulk-complaint-level-values.md).|
|Aufbewahrungszeitraum für Quarantäne <p> _QuarantineRetentionPeriod_|15 Tage|30 Tage|30 Tage||
|**Sicherheitstipps** <p> _InlineSafetyTipsEnabled_|Ein <p> `$true`|Ein <p> `$true`|Ein <p> `$true`||
|Zugelassene Absender <p> _AllowedSenders_|Keine|Keine|Keine||
|Zulässige Absenderdomänen <p> _AllowedSenderDomains_|Keine|Keine|Keine|Das Hinzufügen von Domänen zur Liste der zulässigen Absender ist eine sehr schlechte Idee. Angreifer können Ihnen E-Mails senden, die andernfalls herausgefiltert würden. <p> Verwenden Sie [spoof intelligence](learn-about-spoof-intelligence.md) im Security & Compliance Center auf der Seite Antispameinstellungen, um alle Absender zu überprüfen, die Absender-E-Mail-Adressen in den **E-Mail-Domänen** Ihrer Organisation spoofieren oder Absender-E-Mail-Adressen in externen Domänen spoofieren.|
|Blockierte Absender <p> _BlockedSenders_|Keine|Keine|Keine||
|Blockierte Absenderdomänen <p> _BlockedSenderDomains_|Keine|Keine|Keine||
|**Spambenachrichtigungen für Endbenutzer aktivieren** <p> _EnableEndUserSpamNotifications_|Deaktiviert <p> `$false`|Aktiviert <p> `$true`|Aktiviert <p> `$true`||
|**Spambenachrichtigungen an Endbenutzer senden alle ... Tage** <p> _EndUserSpamNotificationFrequency_|3 Tage|3 Tage|3 Tage||
|**Spam-ZAP** <p> _SpamZapEnabled_|Aktiviert <p> `$true`|Aktiviert <p> `$true`|Aktiviert <p> `$true`||
|**Phish ZAP** <p> _PhishZapEnabled_|Aktiviert <p> `$true`|Aktiviert <p> `$true`|Aktiviert <p> `$true`||
|_MarkAsSpamBulkMail_|Ein|Ein|Ein|Diese Einstellung ist nur in PowerShell verfügbar.|
|

Es gibt mehrere andere Erweiterte Spamfiltereinstellungen (Advanced Spam Filter, ASF) in Antispamrichtlinien, die derzeit veraltet sind. Weitere Informationen zu den Zeitachsen für die Abschreibung dieser Features werden außerhalb dieses Artikels mitgeteilt.

Es wird empfohlen, diese ASF-Einstellungen **für Standard-** und  **Strict-Ebenen zu** deaktivieren. Weitere Informationen zu den ASF-Einstellungen finden Sie unter [Advanced Spam Filter (ASF) settings in Office 365](advanced-spam-filtering-asf-options.md).

****

|Name des Sicherheitsfeatures|Kommentar|
|---|---|
|**Bildlinks zu Remotewebsites** (_IncreaseScoreWithImageLinks_)||
|**Numerische IP-Adresse in URL** (_IncreaseScoreWithNumericIps_)||
|**UL-Umleitung zu einem anderen Port** (_IncreaseScoreWithRedirectToOtherPort_)||
|**URL zu .biz- oder .info-Websites** (_IncreaseScoreWithBizOrInfoUrls_)||
|**Leere Nachrichten** (_MarkAsSpamEmptyMessages_)||
|**JavaScript oder VBScript in HTML** (_MarkAsSpamJavaScriptInHtml_)||
|**Frame- oder IFrame-Tags in HTML** (_MarkAsSpamFramesInHtml_)||
|**Objekttags in HTML** (_MarkAsSpamObjectTagsInHtml_)||
|**Einbetten von Tags in HTML** (_MarkAsSpamEmbedTagsInHtml_)||
|**Formulartags in HTML** (_MarkAsSpamFormTagsInHtml_)||
|**Webfehler in HTML** (_MarkAsSpamWebBugsInHtml_)||
|**Anwenden einer Liste vertraulicher Wörter** (_MarkAsSpamSensitiveWordList_)||
|**SPF-Eintrag: harter Fehler** (_MarkAsSpamSpfRecordHardFail_)||
|**Bedingte Absender-ID-Filterung: Harter Fehler** (_MarkAsSpamFromAddressAuthFail_)||
|**NDR backscatter** (_MarkAsSpamNdrBackscatter_)||
|

#### <a name="eop-outbound-spam-policy-settings"></a>EOP-Einstellungen für ausgehende Spamrichtlinien

Informationen zum Erstellen und Konfigurieren ausgehender Spamrichtlinien finden Sie unter [Configure outbound spam filtering in Office 365](configure-the-outbound-spam-policy.md).

Weitere Informationen zu den standardmäßigen Sendegrenzwerte im Dienst finden Sie unter [Senden von Grenzwerten](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).

****

|Name des Sicherheitsfeatures|Standard|Standard|Strict|Kommentar|
|---|:---:|:---:|:---:|---|
|**Maximale Anzahl von Empfängern pro Benutzer: Externe Stündlich-Grenze** <p> _RecipientLimitExternalPerHour_|0|500|400|Der Standardwert 0 bedeutet, dass die Diensteinstellungen verwendet werden.|
|**Maximale Anzahl von Empfängern pro Benutzer: Interner Stundengrenzwert** <p> _RecipientLimitInternalPerHour_|0|1000|800|Der Standardwert 0 bedeutet, dass die Diensteinstellungen verwendet werden.|
|**Maximale Anzahl von Empfängern pro Benutzer: Tägliche Grenze** <p> _RecipientLimitPerDay_|0|1000|800|Der Standardwert 0 bedeutet, dass die Diensteinstellungen verwendet werden.|
|**Aktion, wenn ein Benutzer die Grenzwerte überschreitet** <p> _ActionWhenThresholdReached_|**Einschränken des Sendens von E-Mails durch den Benutzer bis zum folgenden Tag** <p> `BlockUserForToday`|**Einschränken des Sendens von E-Mails durch den Benutzer** <p> `BlockUser`|**Einschränken des Sendens von E-Mails durch den Benutzer** <p> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>EOP-Anti-Malware-Richtlinieneinstellungen

Informationen zum Erstellen und Konfigurieren von An malware-Richtlinien finden Sie unter [Configure anti-malware policies in Office 365](configure-anti-malware-policies.md).

****

|Name des Sicherheitsfeatures|Standard|Standard|Strict|Kommentar|
|---|:---:|:---:|:---:|---|
|**Möchten Sie Empfänger benachrichtigen, wenn ihre Nachrichten unter Quarantäne gestellt werden?** <p> _Aktion_|Nein <p> _DeleteMessage_|Nein <p> _DeleteMessage_|Nein <p> _DeleteMessage_|Wenn Schadsoftware in einer E-Mail-Anlage erkannt wird, wird die Nachricht in Quarantäne gestellt und kann nur von einem Administrator freigegeben werden.|
|**Filter für häufige Anlagentypen** <p> _EnableFileFilter_|Off <p> `$false`|Ein <p> `$true`|Ein <p> `$true`|Mit dieser Einstellung werden Nachrichten isoliert, die ausführbare Anlagen basierend auf dem Dateityp enthalten, unabhängig vom Anlageninhalt.|
|**Schadsoftware Null-Stunden-Autobereinigung** <p> _ZapEnabled_|Ein <p> `$true`|Ein <p> `$true`|Ein <p> `$true`||
|**Benachrichtigen interner Absender** über die nicht zugestellte Nachricht <p> _EnableInternalSenderNotifications_|Deaktiviert <p> `$false`|Deaktiviert <p> `$false`|Deaktiviert <p> `$false`||
|**Benachrichtigen externer Absender** über die nicht zugestellte Nachricht <p> _EnableExternalSenderNotifications_|Deaktiviert <p> `$false`|Deaktiviert <p> `$false`|Deaktiviert <p> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>EOP-Standardeinstellungen für Antiphishingrichtlinien

Weitere Informationen zu diesen Einstellungen finden Sie unter [Spoof-Einstellungen](set-up-anti-phishing-policies.md#spoof-settings). Informationen zum Konfigurieren dieser Einstellungen finden Sie [unter Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).

****

|Name des Sicherheitsfeatures|Standard|Standard|Strict|Kommentar|
|---|:---:|:---:|:---:|---|
|**Aktivieren des Antis spoofing-Schutzes** <p> _EnableSpoofIntelligence_|Ein <p> `$true`|Ein <p> `$true`|Ein <p> `$true`||
|**Aktivieren des nicht authentifizierten Absenders** <p> _EnableUnauthenticatedSender_|Ein <p> `$true`|Ein <p> `$true`|Ein <p> `$true`|Fügt dem Foto des Absenders in Outlook ein Fragezeichen (?) für nicht identifizierte gefälschte Absender hinzu. Weitere Informationen finden Sie unter [Spoofeinstellungen in Antiphishingrichtlinien](set-up-anti-phishing-policies.md).|
|**Wenn E-Mails von einer Person gesendet werden, die Ihre Domäne nicht spoofen darf** <p> _AuthenticationFailAction_|**Verschieben von Nachrichten in die Junk-E-Mail-Ordner der Empfänger** <p> `MoveToJmf`|**Verschieben von Nachrichten in die Junk-E-Mail-Ordner der Empfänger** <p> `MoveToJmf`|**Isolieren der Nachricht** <p> `Quarantine`|Diese Einstellung gilt für blockierte Absender in [Spoof Intelligence](learn-about-spoof-intelligence.md).|
|

## <a name="microsoft-defender-for-office-365-security"></a>Microsoft Defender für Office 365-Sicherheit

Zusätzliche Sicherheitsvorteile bieten ein Microsoft Defender for Office 365-Abonnement. Aktuelle Nachrichten und Informationen finden Sie unter [Neuigkeiten in Defender for Office 365](whats-new-in-office-365-atp.md).

> [!IMPORTANT]
>
> - Die standardmäßige Antiphishingrichtlinie in Microsoft Defender für Office 365 bietet [Spoofschutz](set-up-anti-phishing-policies.md#spoof-settings) und Postfachintelligenz für alle Empfänger. Die anderen verfügbaren [](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) Identitätswechselschutzfeatures und erweiterten Einstellungen sind jedoch in der Standardrichtlinie nicht konfiguriert oder aktiviert. [](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) Um alle Schutzfunktionen zu aktivieren, ändern Sie die Standardmäßige Antiphishingrichtlinie, oder erstellen Sie zusätzliche Antiphishingrichtlinien.
>
> - Es gibt keine standardmäßigen Richtlinien für sichere Links oder Richtlinien für sichere Anlagen, die automatisch alle Empfänger in der Organisation schützen. Um die Schutzmaßnahmen zu erhalten, müssen Sie mindestens eine Richtlinie für sichere Links und eine Richtlinie für sichere Anlagen erstellen.
>
> - Der Schutz von sicheren Anlagen für [SharePoint, OneDrive und Microsoft Teams](atp-for-spo-odb-and-teams.md) sowie der Schutz sicherer Dokumente sind nicht von Richtlinien für sichere Links abhängig. [](safe-docs.md)

Wenn Ihr Abonnement Microsoft Defender für Office 365 enthält oder Sie Defender für Office 365 als Add-On erworben haben, legen Sie die folgenden Standard- oder Strict-Konfigurationen ein.

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Einstellungen für Antiphishingrichtlinien in Microsoft Defender für Office 365

EOP-Kunden erhalten grundlegende Antiphishing, wie zuvor beschrieben, aber Microsoft Defender für Office 365 enthält mehr Features und Steuerung, um Angriffe zu verhindern, zu erkennen und zu abwehren. Informationen zum Erstellen und Konfigurieren dieser Richtlinien finden Sie unter [Configure anti-phishing policies in Defender for Office 365](configure-atp-anti-phishing-policies.md).

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Identitätswechseleinstellungen in Antiphishingrichtlinien in Microsoft Defender für Office 365

Weitere Informationen zu diesen Einstellungen finden Sie unter [Identitätswechseleinstellungen in Antiphishingrichtlinien in Microsoft Defender für Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Informationen zum Konfigurieren dieser Einstellungen finden Sie unter [Configure anti-phishing policies in Defender for Office 365](configure-atp-anti-phishing-policies.md).

****

|Name des Sicherheitsfeatures|Standard|Standard|Strict|Kommentar|
|---|:---:|:---:|:---:|---|
|Geschützte Benutzer: **Benutzer zum Schutz hinzufügen** <p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|Off <p> `$false` <p> keine|Ein <p> `$true` <p> \<list of users\>|Ein <p> `$true` <p> \<list of users\>|Je nach Organisation wird empfohlen, Benutzer (Nachrichtensender) in Schlüsselrollen zu hinzufügen. Intern können geschützte Absender Ihr CEO, CFO und andere leitende Führungskräfte sein. Extern könnten geschützte Absender Auch Ratsmitglieder oder Ihr Board of Directors enthalten.|
|Geschützte Domänen: **Schließen Sie automatisch die Domänen ein, die ich selbst habe.** <p> _EnableOrganizationDomainsProtection_|Off <p> `$false`|Ein <p> `$true`|Ein <p> `$true`||
|Geschützte Domänen: **Benutzerdefinierte Domänen enthalten** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|Off <p> `$false` <p> keine|Ein <p> `$true` <p> \<list of domains\>|Ein <p> `$true` <p> \<list of domains\>|Je nach Organisation empfehlen wir das Hinzufügen von Domänen (Absenderdomänen), die Sie nicht besitzen, mit denen Sie jedoch häufig interagieren.|
|Geschützte **Benutzer: Wenn E-Mails von einem identitätswechselten Benutzer gesendet werden** <p> _TargetedUserProtectionAction_|**Keine Aktion anwenden** <p> `NoAction`|**Isolieren der Nachricht** <p> `Quarantine`|**Isolieren der Nachricht** <p> `Quarantine`||
|Geschützte Domänen: **Wenn E-Mails von einer identitätswechselten Domäne gesendet werden** <p> _TargetedDomainProtectionAction_|**Keine Aktion anwenden** <p> `NoAction`|**Isolieren der Nachricht** <p> `Quarantine`|**Isolieren der Nachricht** <p> `Quarantine`||
|**Tipps für imitierte Benutzer anzeigen** <p> _EnableSimilarUsersSafetyTips_|Off <p> `$false`|Ein <p> `$true`|Ein <p> `$true`||
|**Tipps für identitätswechselte Domänen anzeigen** <p> _EnableSimilarDomainsSafetyTips_|Off <p> `$false`|Ein <p> `$true`|Ein <p> `$true`||
|**Tipps für ungewöhnliche Zeichen anzeigen** <p> _EnableUnusualCharactersSafetyTips_|Off <p> `$false`|Ein <p> `$true`|Ein <p> `$true`||
|**Aktivieren der Postfachintelligenz?** <p> _EnableMailboxIntelligence_|Ein <p> `$true`|Ein <p> `$true`|Ein <p> `$true`||
|**Aktivieren des Schutzes von Identitätswechseln auf Postfachintelligenz?** <p> _EnableMailboxIntelligenceProtection_|Off <p> `$false`|Ein <p> `$true`|Ein <p> `$true`||
|**Wenn E-Mails von einem durch Postfachintelligenz geschützten imitierten Benutzer gesendet werden** <p> _MailboxIntelligenceProtectionAction_|**Keine Aktion anwenden** <p> `NoAction`|**Verschieben von Nachrichten in die Junk-E-Mail-Ordner der Empfänger** <p> `MoveToJmf`|**Isolieren der Nachricht** <p> `Quarantine`||
|**Trusted senders** <p> _ExcludedSenders_|Keine|Keine|Keine|Abhängig von Ihrer Organisation wird empfohlen, Benutzer hinzufügungen, die aufgrund von Identitätswechsel und nicht aufgrund anderer Filter fälschlicherweise als Phishing gekennzeichnet werden.|
|**Vertrauenswürdige Domänen** <p> _ExcludedDomains_|Keine|Keine|Keine|Je nach Organisation empfehlen wir das Hinzufügen von Domänen, die aufgrund von Identitätswechseln fälschlicherweise als Phishing gekennzeichnet werden, und nicht durch andere Filter.|
|

#### <a name="spoof-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Spoofeinstellungen in Antiphishingrichtlinien in Microsoft Defender für Office 365

Beachten Sie, dass es sich um dieselben Einstellungen handelt, die in den [Antispamrichtlinieneinstellungen in EOP verfügbar sind.](#eop-anti-spam-policy-settings)

****

|Name des Sicherheitsfeatures|Standard|Standard|Strict|Kommentar|
|---|---|---|---|---|
|**Aktivieren des Antis spoofing-Schutzes** <p> _EnableSpoofIntelligence_|Ein <p> `$true`|Ein <p> `$true`|Ein <p> `$true`||
|**Aktivieren des nicht authentifizierten Absenders** <p> _EnableUnauthenticatedSender_|Ein <p> `$true`|Ein <p> `$true`|Ein <p> `$true`|Fügt dem Foto des Absenders in Outlook ein Fragezeichen (?) für nicht identifizierte gefälschte Absender hinzu. Weitere Informationen finden Sie unter [Spoofeinstellungen in Antiphishingrichtlinien](set-up-anti-phishing-policies.md).|
|**Wenn E-Mails von einer Person gesendet werden, die Ihre Domäne nicht spoofen darf** <p> _AuthenticationFailAction_|**Verschieben von Nachrichten in die Junk-E-Mail-Ordner der Empfänger** <p> `MoveToJmf`|**Verschieben von Nachrichten in die Junk-E-Mail-Ordner der Empfänger** <p> `MoveToJmf`|**Isolieren der Nachricht** <p> `Quarantine`|Diese Einstellung gilt für blockierte Absender in [Spoof Intelligence](learn-about-spoof-intelligence.md).|
|

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Erweiterte Einstellungen in Antiphishingrichtlinien in Microsoft Defender für Office 365

Weitere Informationen zu dieser Einstellung finden Sie unter [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Informationen zum Konfigurieren dieser Einstellung finden Sie [unter Configure anti-phishing policies in Defender for Office 365](configure-atp-anti-phishing-policies.md).

****

|Name des Sicherheitsfeatures|Standard|Standard|Strict|Kommentar|
|---|:---:|:---:|:---:|---|
|**Erweiterte Phishingschwellenwerte** <p> _PhishThresholdLevel_|**1 – Standard** <p> `1`|**2 – Aggressiv** <p> `2`|**3 – Aggressiver** <p> `3`||
|

### <a name="safe-links-settings"></a>Einstellungen für sichere Links

Sichere Links in Defender for Office 365 umfassen globale Einstellungen, die für alle Benutzer gelten, die in aktiven Richtlinien für sichere Links enthalten sind, sowie Einstellungen, die für jede Richtlinie für sichere Links spezifisch sind. Weitere Informationen finden Sie unter [Sichere Links in Defender for Office 365](atp-safe-links.md).

#### <a name="global-settings-for-safe-links"></a>Globale Einstellungen für sichere Links

Informationen zum Konfigurieren dieser Einstellungen finden Sie unter [Configure global settings for Safe Links in Defender for Office 365](configure-global-settings-for-safe-links.md).

In PowerShell verwenden Sie das [Cmdlet Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) für diese Einstellungen.

****

|Name des Sicherheitsfeatures|Standard|Standard|Strict|Kommentar|
|---|:---:|:---:|:---:|---|
|**Verwenden sicherer Links in: Office 365-Anwendungen** <p> _EnableSafeLinksForO365Clients_|Ein <p> `$true`|Ein <p> `$true`|Ein <p> `$true`|Verwenden Sie sichere Links in unterstützten Office 365-Desktop- und mobilen Apps (iOS und Android). Weitere Informationen finden Sie unter [Einstellungen für sichere Links für Office 365-Apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).|
|**Nicht nachverfolgen, wenn Benutzer auf sichere Links klicken** <p> _TrackClicks_|Ein <p> `$false`|Off <p> `$true`|Off <p> `$true`|Wenn Sie diese Einstellung deaktivieren _(TrackClicks_ auf festlegen), werden `$true` Benutzerklicks in unterstützten Office 365-Apps nachverfolgt.|
|**Benutzer dürfen nicht auf sichere Links zur ursprünglichen URL klicken** <p> _AllowClickThrough_|Ein <p> `$false`|Ein <p> `$false`|Ein <p> `$false`|Durch Aktivieren dieser Einstellung (Festlegen _von AllowClickThrough_ auf ) wird das Durchklicken zur ursprünglichen URL in unterstützten `$false` Office 365-Apps verhindert.|
|

#### <a name="safe-links-policy-settings"></a>Richtlinieneinstellungen für sichere Links

Informationen zum Konfigurieren dieser Einstellungen finden Sie unter Einrichten von Richtlinien für sichere Links [in Microsoft Defender für Office 365](set-up-atp-safe-links-policies.md).

In PowerShell verwenden Sie die [Cmdlets New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy) und [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy) für diese Einstellungen.

> [!NOTE]
> Wie bereits beschrieben, gibt es keine Standardmäßige Richtlinie für sichere Links. Die Werte in der Spalte Standard sind die Standardwerte in den neuen Richtlinien für sichere Links, die Sie erstellen.

****

|Name des Sicherheitsfeatures|Standard|Standard|Strict|Kommentar|
|---|:---:|:---:|:---:|---|
|**Auswählen der Aktion für unbekannte potenziell schädliche URLs in Nachrichten** <p> _IsEnabled_|Off <p> `$false`|Ein <p> `$true`|Ein <p> `$true`||
|**Auswählen der Aktion für unbekannte oder potenziell schädliche URLs in Microsoft Teams** <p> _EnableSafeLinksForTeams_|Off <p> `$false`|Ein <p> `$true`|Ein <p> `$true`||
|**Anwenden der Echtzeit-URL-Überprüfung auf verdächtige Links und Links, die auf Dateien verweisen** <p> _ScanUrls_|Off <p> `$false`|Ein <p> `$true`|Ein <p> `$true`||
|**Warten Sie, bis die URL-Überprüfung abgeschlossen ist, bevor sie die Nachricht zu senden.** <p> _DeliverMessageAfterScan_|Off <p> `$false`|Ein <p> `$true`|Ein <p> `$true`||
|**Anwenden sicherer Links auf E-Mail-Nachrichten, die innerhalb der Organisation gesendet werden** <p> _EnableForInternalSenders_|Off <p> `$false`|Ein <p> `$true`|Ein <p> `$true`||
|**Benutzerklicks nicht nachverfolgen** <p> _DoNotTrackUserClicks_|Off <p> `$false`|Off <p> `$false`|Off <p> `$false`|Wenn Sie diese Einstellung deaktivieren _(DoNotTrackUserClicks_ auf `$false` festlegen), werden Benutzerklicks verfolgt.|
|**Benutzer dürfen nicht zur ursprünglichen URL klicken** <p> _DoNotAllowClickThrough_|Off <p> `$false`|Ein <p> `$true`|Ein <p> `$true`|Durch Aktivieren dieser Einstellung (Festlegen _von DoNotAllowClickThrough_ auf ) wird das Durchklicken `$true` zur ursprünglichen URL verhindert.|
|

### <a name="safe-attachments-settings"></a>Einstellungen für sichere Anlagen

Sichere Anlagen in Microsoft Defender für Office 365 umfassen globale Einstellungen, die keine Beziehung zu Richtlinien für sichere Anlagen haben, und Einstellungen, die für jede Richtlinie für sichere Links spezifisch sind. Weitere Informationen finden Sie unter [Sichere Anlagen in Defender for Office 365](atp-safe-attachments.md).

#### <a name="global-settings-for-safe-attachments"></a>Globale Einstellungen für sichere Anlagen

Informationen zum Konfigurieren dieser Einstellungen finden Sie unter Aktivieren sicherer [Anlagen für SharePoint, OneDrive und Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) und sichere Dokumente in Microsoft [365 E5](safe-docs.md).

In PowerShell verwenden Sie das [Cmdlet Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) für diese Einstellungen.

****

|Name des Sicherheitsfeatures|Standard|Standard|Strict|Kommentar|
|---|:---:|:---:|:---:|---|
|**Defender für Office 365 für SharePoint, OneDrive und Microsoft Teams aktivieren** <p> _EnableATPForSPOTeamsODB_|Ein <p> `$true`|Ein <p> `$true`||
|**Aktivieren sicherer Dokumente für Office-Clients** <p> _EnableSafeDocs_|Ein <p> `$true`|Ein <p> `$true`|Diese Einstellung ist nur mit Microsoft 365 E5- oder Microsoft 365 E5-Sicherheitslizenzen verfügbar. Weitere Informationen finden Sie unter [Sichere Dokumente in Microsoft Defender für Office 365](safe-docs.md).|
|**Zulassen, dass Personen durch die geschützte Ansicht klicken, auch wenn sichere Dokumente die Datei als schädlich identifiziert haben** <p> _AllowSafeDocsOpen_|Off <p> `$false`|Off <p> `$false`|Diese Einstellung steht im Zusammenhang mit sicheren Dokumenten.|
|

#### <a name="safe-attachments-policy-settings"></a>Richtlinieneinstellungen für sichere Anlagen

Informationen zum Konfigurieren dieser Einstellungen finden Sie unter [Set up Safe Attachments policies in Defender for Office 365](set-up-atp-safe-attachments-policies.md).

In PowerShell verwenden Sie die [Cmdlets New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy) und [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safelinkspolicy) für diese Einstellungen.

> [!NOTE]
> Wie bereits beschrieben, gibt es keine Standardmäßige Richtlinie für sichere Anlagen. Die Werte in der Spalte Standard sind die Standardwerte in den neuen Richtlinien für sichere Anlagen, die Sie erstellen.

****

|Name des Sicherheitsfeatures|Standard|Standard|Strict|Kommentar|
|---|:---:|:---:|:---:|---|
|**Sichere Anlagen unbekannte Schadsoftwareantwort** <p> _Aktion_|Blockieren <p> `Block`|Blockieren <p> `Block`|Blockieren <p> `Block`||
|**Umleitungsanlage bei Erkennung:** **Umleitung aktivieren** <p> _Redirect_ <p> _RedirectAddress_|Aus und keine E-Mail-Adresse angegeben. <p> `$true` <p> keine|Ein, und geben Sie eine E-Mail-Adresse an. <p> `$true` <p> eine E-Mail-Adresse|Ein, und geben Sie eine E-Mail-Adresse an. <p> `$true` <p> eine E-Mail-Adresse|Umleiten von Nachrichten an einen Sicherheitsadministrator zur Überprüfung.|
|**Wenden Sie die oben aufgeführte Auswahl an, wenn bei der Schadsoftwareprüfung auf Anlagen ein Zeitfehler auftritt oder ein Fehler auftritt.** <p> _ActionOnError_|Ein <p> `$true`|Ein <p> `$true`|Ein <p> `$true`||
|

## <a name="related-articles"></a>Verwandte Artikel

- Suchen Sie nach bewährten Methoden für **Exchange-Nachrichtenflussregeln (auch** als Transportregeln bekannt) Weitere [Informationen finden Sie unter Bewährte Methoden zum Konfigurieren von Nachrichtenflussregeln in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices).

- Administratoren und Benutzer können falsch positive Ergebnisse (gute E-Mails, die als ungültig gekennzeichnet sind) und falsch negative (ungültige E-Mails sind zulässig) zur Analyse an Microsoft übermitteln. Weitere Informationen finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).

- Verwenden Sie diese Links,  um Informationen zum Einrichten  Ihres [EOP-Diensts](set-up-your-eop-service.md)und zum Konfigurieren von [Microsoft Defender für Office 365 zu erhalten.](office-365-atp.md) Vergessen Sie nicht die hilfreichen Anweisungen in "[Schutz vor Bedrohungen in Office 365](protect-against-threats.md)".

- **Sicherheitsgrundwerte** für Windows finden Sie hier: Wo kann ich die Sicherheitsgrundwerte [erhalten?](/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) für Gruppenrichtlinienobjekt-/lokale Optionen und Verwenden von Sicherheitsgrundwerten zum Konfigurieren von [Windows 10-Geräten in Intune](/intune/protect/security-baselines) für Intune-basierte Sicherheit. Abschließend finden Sie unter Vergleichen der Microsoft Defender for Endpoint- und Windows Intune-Sicherheitsgrundwerte einen Vergleich zwischen Microsoft Defender for Endpoint und [den Windows Intune-Sicherheitsgrundwerten.](/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)