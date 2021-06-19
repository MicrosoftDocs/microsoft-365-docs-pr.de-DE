---
title: Microsoft-Empfehlungen für EOP und Defender für Office 365 Sicherheitseinstellungen
keywords: Office 365 Sicherheitsempfehlungen, Sender Policy Framework, domänenbasierte Nachrichtenberichterstattung und Konformität, DomainKeys Identified Mail, Schritte, Funktionsweise, Sicherheitsgrundwerte, Basispläne für EOP, Baselines für Defender für Office 365, Einrichten von Defender für Office 365, Einrichten von EOP, Konfigurieren von Defender für Office 365, Konfigurieren von EOP, Sicherheitskonfiguration
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
description: Was sind bewährte Methoden für Exchange Online Protection (EOP) und Defender für Office 365 Sicherheitseinstellungen? Was sind die aktuellen Empfehlungen für den Standardschutz? Was sollte verwendet werden, wenn Sie strenger sein möchten? Und welche Extras erhalten Sie, wenn Sie Defender auch für Office 365 verwenden?
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 031dd6ffe05c700b65fb56da90a49ed194c17321
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029513"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>Empfohlene Einstellungen für EOP und Microsoft Defender für Office 365 Sicherheit

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Exchange Online Protection (EOP)** ist der Kern der Sicherheit für Microsoft 365 Abonnements und trägt dazu bei, schädliche E-Mails davon abzuhalten, die Postfächer Ihrer Mitarbeiter zu erreichen. Aber da täglich neue, komplexere Angriffe auftreten, sind häufig verbesserte Schutzmaßnahmen erforderlich. **Microsoft Defender für Office 365** Plan 1 oder Plan 2 enthalten zusätzliche Features, die Administratoren mehr Sicherheit, Kontrolle und Untersuchung bieten.

Obwohl wir Sicherheitsadministratoren die Möglichkeit geben, ihre Sicherheitseinstellungen anzupassen, gibt es zwei Sicherheitsebenen in EOP und Microsoft Defender für Office 365, die wir empfehlen: **Standard** und **Strict**. Die Umgebung und Die Anforderungen jedes Kunden sind unterschiedlich, aber wir glauben, dass diese Filterstufen dazu beitragen, zu verhindern, dass unerwünschte E-Mails in den meisten Situationen den Posteingang Ihrer Mitarbeiter erreichen.

Informationen zum automatischen Anwenden der Standard- oder Strict-Einstellungen auf Benutzer finden Sie [unter "Voreingestellte Sicherheitsrichtlinien" in EOP und Microsoft Defender für Office 365.](preset-security-policies.md)

> [!NOTE]
> Die Junk-E-Mail-Regel muss für Postfächer aktiviert werden, damit die Filterung ordnungsgemäß funktioniert. Es ist standardmäßig aktiviert, Sie sollten es jedoch überprüfen, wenn die Filterung nicht zu funktionieren scheint. Weitere Informationen finden Sie unter [Konfigurieren der Einstellungen für Junk-E-Mails für Exchange Online-Postfächer](configure-junk-email-settings-on-exo-mailboxes.md).

In diesem Artikel werden die Standardeinstellungen sowie die empfohlenen Standard- und Strict-Einstellungen zum Schutz Ihrer Benutzer beschrieben. Die Tabellen enthalten die Einstellungen im Microsoft 365 Defender-Portal und in PowerShell (Exchange Online PowerShell oder eigenständige Exchange Online Protection PowerShell für Organisationen ohne Exchange Online Postfächer).

> [!TIP]
> Das Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)-Modul für PowerShell kann Ihnen (Administratoren) helfen, die aktuellen Werte dieser Einstellungen zu finden. Insbesondere generiert das Cmdlet **"Get-ORCAReport"** eine Bewertung von Antispam-, Antiphishing- und anderen Nachrichtenschutzeinstellungen. Sie können das ORCA-Modul unter <https://www.powershellgallery.com/packages/ORCA/> herunterladen.

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Antispam-, Antischadsoftware- und Antiphishingschutz in EOP

Antispam, Antischadsoftware und Antiphishing sind EOP-Features, die von Administratoren konfiguriert werden können. Wir empfehlen die folgenden Standard- oder Strict-Konfigurationen.

### <a name="eop-anti-spam-policy-settings"></a>EOP-Antispamrichtlinieneinstellungen

Informationen zum Erstellen und Konfigurieren von Antispamrichtlinien finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP.](configure-your-spam-filter-policies.md)

<br>

****

|Name des Sicherheitsfeatures|Standard|Standard|Streng|Kommentar|
|---|:---:|:---:|:---:|---|
|**Spamerkennungsaktion** <p> _SpamAction_|**Nachricht in Junk-E-Mail-Ordner verschieben** <p> `MoveToJmf`|**Nachricht in Junk-E-Mail-Ordner verschieben** <p> `MoveToJmf`|**Nachricht in Quarantäne verschieben** <p> `Quarantine`||
|**Spamerkennungsaktion mit hoher Vertrauenswürdigkeit** <p> _HighConfidenceSpamAction_|**Nachricht in Junk-E-Mail-Ordner verschieben** <p> `MoveToJmf`|**Nachricht in Quarantäne verschieben** <p> `Quarantine`|**Nachricht in Quarantäne verschieben** <p> `Quarantine`||
|**Phishingerkennungsaktion** <p> _PhishSpamAction_|**Nachricht in Junk-E-Mail-Ordner verschieben** <p> `MoveToJmf`|**Nachricht in Quarantäne verschieben** <p> `Quarantine`|**Nachricht in Quarantäne verschieben** <p> `Quarantine`||
|Phishing-Erkennungsaktion **mit hoher Vertrauenswürdigkeit** <p> _HighConfidencePhishAction_|**Nachricht in Quarantäne verschieben** <p> `Quarantine`|**Nachricht in Quarantäne verschieben** <p> `Quarantine`|**Nachricht in Quarantäne verschieben** <p> `Quarantine`||
|**Massenerkennungsaktion** <p> _BulkSpamAction_|**Nachricht in Junk-E-Mail-Ordner verschieben** <p> `MoveToJmf`|**Nachricht in Junk-E-Mail-Ordner verschieben** <p> `MoveToJmf`|**Nachricht in Quarantäne verschieben** <p> `Quarantine`||
|**Schwellenwert für Massen-E-Mails** <p> _BulkThreshold_|7 |6 |4 |Ausführliche Informationen finden Sie unter [BCL (Bulk Complaint Level) in EOP.](bulk-complaint-level-values.md)|
|_MarkAsSpamBulkMail_|Ein|Ein|Ein|Diese Einstellung ist nur in PowerShell verfügbar.|
|**Aufbewahrung von Spam in Quarantäne für diese viele Tage** <p> _QuarantineRetentionPeriod_|15 Tage|30 Tage|30 Tage||
|**Aktivieren von Spamsicherheitstipps** <p> _InlineSafetyTipsEnabled_|Ein <p> `$true`|Ein <p> `$true`|Ein <p> `$true`||
|Zulässige Absender <p> _AllowedSenders_|Keine|Keine|Keine||
|Domänen zulässiger Absender <p> _Allowedsenderdomains_|Keine|Keine|Keine|Das Hinzufügen von Domänen zur Liste der zulässigen Absender ist eine sehr schlechte Idee. Angreifer könnten Ihnen E-Mails senden, die andernfalls herausgefiltert würden. <p> Verwenden Sie den Einblick in die [Spoofintelligenz](learn-about-spoof-intelligence.md) und die [Mandanten-Zulassungs-/Sperrliste,](tenant-allow-block-list.md) um alle Absender zu überprüfen, die Absender-E-Mail-Adressen in den E-Mail-Domänen Ihrer Organisation spoofing oder Absender-E-Mail-Adressen in externen Domänen spoofing.|
|Blockierte Absender <p> _BlockedSenders_|Keine|Keine|Keine||
|Blockierte Absenderdomänen <p> _BlockedSenderDomains_|Keine|Keine|Keine||
|**Spambenachrichtigungen für Endbenutzer aktivieren** <p> _EnableEndUserSpamNotifications_|Deaktiviert <p> `$false`|Aktiviert <p> `$true`|Aktiviert <p> `$true`||
|**Spambenachrichtigungen an Endbenutzer senden alle ... Tage** <p> _EndUserSpamNotificationFrequency_|3 Tage|3 Tage|3 Tage||
|Aktivieren der automatischen Bereinigung zur Nullstunde (ZAP) für Phishingnachrichten <p> _PhishZapEnabled_|Aktiviert <p> `$true`|Aktiviert <p> `$true`|Aktiviert <p> `$true`||
|Aktivieren von ZAP für Spamnachrichten <p> _SpamZapEnabled_|Aktiviert <p> `$true`|Aktiviert <p> `$true`|Aktiviert <p> `$true`||
|

Es gibt viele ASF-Einstellungen (Advanced Spam Filter) in Antispamrichtlinien, die veraltet sind. Weitere Informationen zu den Zeitplänen für die Abschreibung dieser Features werden außerhalb dieses Artikels mitgeteilt.

Es wird empfohlen, die folgenden ASF-Einstellungen für **standard-** und **strict-Stufen** **deaktiviert** zu lassen. Weitere Informationen zu ASF-Einstellungen finden Sie unter [Advanced Spam Filter (ASF)-Einstellungen in EOP.](advanced-spam-filtering-asf-options.md)

<br>

****

|Name des Sicherheitsfeatures|Kommentar|
|---|---|
|**Bildlinks zu Remotewebsites** (_IncreaseScoreWithImageLinks_)||
|**Numerische IP-Adresse in URL** (_IncreaseScoreWithNumericIps_)||
|**URL-Umleitung zu einem anderen Port** (_IncreaseScoreWithRedirectToOtherPort_)||
|**Links zu BIZ- oder INFO-Websites** (_IncreaseScoreWithBizOrInfoUrls_)||
|**Leere Nachrichten** (_MarkAsSpamEmptyMessages_)||
|**Einbetten von Tags in HTML** (_MarkAsSpamEmbedTagsInHtml_)||
|**JavaScript oder VBScript in HTML** (_MarkAsSpamJavaScriptInHtml_)||
|**Formulartags in HTML** (_MarkAsSpamFormTagsInHtml_)||
|**Frame- oder iframe-Tags in HTML** (_MarkAsSpamFramesInHtml_)||
|**Webfehler in HTML** (_MarkAsSpamWebBugsInHtml_)||
|**Objekttags in HTML** (_MarkAsSpamObjectTagsInHtml_)||
|**Vertrauliche Wörter** (_MarkAsSpamSensitiveWordList_)||
|**SPF-Eintrag: Hard Fail** (_MarkAsSpamSpfRecordHardFail_)||
|Fehler beim **Filtern der Absender-ID** (_MarkAsSpamFromAddressAuthFail_)||
|**Backscatter** (_MarkAsSpamNdrBackscatter_)||
|

#### <a name="eop-outbound-spam-policy-settings"></a>EOP-Richtlinieneinstellungen für ausgehende Spamnachrichten

Informationen zum Erstellen und Konfigurieren ausgehender Spamrichtlinien finden Sie unter [Konfigurieren der ausgehenden Spamfilterung in EOP.](configure-the-outbound-spam-policy.md)

Weitere Informationen zu den standardmäßigen Sendegrenzwerten im Dienst finden Sie unter [Senden von Grenzwerten.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)

<br>

****

|Name des Sicherheitsfeatures|Standard|Standard|Streng|Kommentar|
|---|:---:|:---:|:---:|---|
|**Festlegen eines Grenzwerts für externe Nachrichten** <p> _RecipientLimitExternalPerHour_|0|500|400|Der Standardwert 0 bedeutet, dass die Dienststandardwerte verwendet werden.|
|**Festlegen eines internen Nachrichtenlimits** <p> _RecipientLimitInternalPerHour_|0|1000|800|Der Standardwert 0 bedeutet, dass die Dienststandardwerte verwendet werden.|
|**Festlegen eines Grenzwerts für tägliche Nachrichten** <p> _RecipientLimitPerDay_|0|1000|800|Der Standardwert 0 bedeutet, dass die Dienststandardwerte verwendet werden.|
|**Einschränkung für Benutzer, die das Nachrichtenlimit erreichen** <p> _ActionWhenThresholdReached_|**Einschränken des Sendens von E-Mails durch den Benutzer bis zum folgenden Tag** <p> `BlockUserForToday`|**Einschränken des Sendens von E-Mails durch den Benutzer** <p> `BlockUser`|**Einschränken des Sendens von E-Mails durch den Benutzer** <p> `BlockUser`||
|**Regeln für die automatische Weiterleitung** <p> _AutoForwardingMode_|**Automatisch – vom System gesteuert** <p> `Automatic`|**Automatisch – vom System gesteuert** <p> `Automatic`|**Automatisch – vom System gesteuert** <p> `Automatic`|
|

### <a name="eop-anti-malware-policy-settings"></a>EOP-Richtlinieneinstellungen für Antischadsoftware

Informationen zum Erstellen und Konfigurieren von Antischadsoftwarerichtlinien finden Sie unter [Konfigurieren von Antischadsoftwarerichtlinien in EOP.](configure-anti-malware-policies.md)

<br>

****

|Name des Sicherheitsfeatures|Standard|Standard|Streng|Kommentar|
|---|:---:|:---:|:---:|---|
|**Benachrichtigen von Empfängern, wenn Nachrichten als Schadsoftware unter Quarantäne gestellt werden** <p> _Action_|Nein <p> _DeleteMessage_|Nein <p> _DeleteMessage_|Nein <p> _DeleteMessage_|Wenn Schadsoftware in einer E-Mail-Anlage erkannt wird, wird die Nachricht unter Quarantäne gestellt und kann nur von einem Administrator freigegeben werden.|
|**Aktivieren des allgemeinen Anlagenfilters** <p> _EnableFileFilter_|Aus <p> `$false`|Ein <p> `$true`|Ein <p> `$true`|Diese Einstellung isoliert Nachrichten, die ausführbare Anlagen basierend auf dem Dateityp enthalten, unabhängig vom Anlageninhalt.|
|**Aktivieren der automatischen Bereinigung zur Nullstunde für Schadsoftware** <p> _ZapEnabled_|Ein <p> `$true`|Ein <p> `$true`|Ein <p> `$true`||
|**Benachrichtigen interner Absender, wenn Nachrichten als Schadsoftware isoliert werden** <p> _EnableInternalSenderNotifications_|Deaktiviert <p> `$false`|Deaktiviert <p> `$false`|Deaktiviert <p> `$false`||
|**Benachrichtigen externer Absender, wenn Nachrichten als Schadsoftware isoliert werden** <p> _EnableExternalSenderNotifications_|Deaktiviert <p> `$false`|Deaktiviert <p> `$false`|Deaktiviert <p> `$false`||
|

### <a name="eop-anti-phishing-policy-settings"></a>EOP-Antiphishingrichtlinieneinstellungen

Weitere Informationen zu diesen Einstellungen finden Sie unter [Spoofingeinstellungen.](set-up-anti-phishing-policies.md#spoof-settings) Informationen zum Konfigurieren dieser Einstellungen finden Sie unter [Konfigurieren von Antiphishingrichtlinien in EOP.](configure-anti-phishing-policies-eop.md)

<br>

****

|Name des Sicherheitsfeatures|Standard|Standard|Streng|Kommentar|
|---|:---:|:---:|:---:|---|
|**Spoofintelligenz aktivieren** <p> _EnableSpoofIntelligence_|Ein <p> `$true`|Ein <p> `$true`|Ein <p> `$true`||
|**Wenn E-Mails als Spoofing erkannt werden** <p> _AuthenticationFailAction_|**Verschieben der Nachricht in die Junk-E-Mail-Ordner des Empfängers** <p> `MoveToJmf`|**Verschieben der Nachricht in die Junk-E-Mail-Ordner des Empfängers** <p> `MoveToJmf`|**Quarantäne der Nachricht** <p> `Quarantine`|Diese Einstellung gilt für gefälschte Absender, die automatisch blockiert wurden, wie im Einblick in die [Spoofintelligenz](learn-about-spoof-intelligence.md) gezeigt oder manuell in der [Mandanten-Zulassungs-/Sperrliste](tenant-allow-block-list.md)blockiert wurden.|
|**Anzeigen (?) für nicht authentifizierte Absender für Spoofing** <p> _EnableUnauthenticatedSender_|Ein <p> `$true`|Ein <p> `$true`|Ein <p> `$true`|Fügt dem Foto des Absenders in Outlook für nicht identifizierte gefälschte Absender ein Fragezeichen (?) hinzu. Weitere Informationen finden Sie unter [Spoofeinstellungen in Antiphishingrichtlinien](set-up-anti-phishing-policies.md).|
|**"via"-Tag anzeigen** <p> _EnableViaTag_|Ein <p> `$true`|Ein <p> `$true`|Ein <p> `$true`|Fügt der Absenderadresse ein Via-Tag (chris@contoso.com über fabrikam.com) hinzu, wenn es sich von der Domäne in der DKIM-Signatur oder der **MAIL FROM-Adresse** unterscheidet. <p> Wenn diese Einstellung für Sie nicht verfügbar ist, werden sowohl das **Fragezeichen** als auch das Via-Tag von der **Show (?) für nicht authentifizierte Absender für spoofing-Einstellungen** in Ihrer Organisation gesteuert.|
|

## <a name="microsoft-defender-for-office-365-security"></a>Microsoft Defender für Office 365 Sicherheit

Zusätzliche Sicherheitsvorteile bieten ein Microsoft Defender für Office 365 Abonnement. Die neuesten Nachrichten und Informationen finden Sie unter ["Neuigkeiten" in Defender für Office 365.](whats-new-in-defender-for-office-365.md)

> [!IMPORTANT]
>
> - Die standardmäßige Antiphishingrichtlinie in Microsoft Defender für Office 365 bietet [Spoofschutz](set-up-anti-phishing-policies.md#spoof-settings) und Postfachintelligenz für alle Empfänger. Die anderen verfügbaren [Identitätswechselschutzfeatures](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) und [erweiterten Einstellungen](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) sind jedoch in der Standardrichtlinie nicht konfiguriert oder aktiviert. Um alle Schutzfunktionen zu aktivieren, ändern Sie die Standardmäßige Antiphishingrichtlinie, oder erstellen Sie zusätzliche Antiphishingrichtlinien.
>
> - Es gibt keine Standardrichtlinien für Safe Links oder Safe Anlagenrichtlinien, die automatisch alle Empfänger in der Organisation schützen. Um die Schutzmaßnahmen zu erhalten, müssen Sie mindestens eine Safe Verknüpfungsrichtlinie und Safe Anlagenrichtlinie erstellen.
>
> - [Safe Anlagen für SharePoint, OneDrive und Microsoft Teams](mdo-for-spo-odb-and-teams.md) Schutz und Safe [Schutz von Dokumenten](safe-docs.md) sind nicht von Safe Verknüpfungsrichtlinien abhängig.

Wenn Ihr Abonnement Microsoft Defender für Office 365 enthält oder Wenn Sie Defender für Office 365 als Add-On erworben haben, legen Sie die folgenden Standard- oder Strict-Konfigurationen fest.

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Antiphishingrichtlinieneinstellungen in Microsoft Defender für Office 365

EOP-Kunden erhalten grundlegendes Antiphishing wie zuvor beschrieben, aber Microsoft Defender für Office 365 bietet mehr Features und Kontrolle, um Angriffe zu verhindern, zu erkennen und zu beheben. Informationen zum Erstellen und Konfigurieren dieser Richtlinien finden Sie unter [Konfigurieren von Antiphishingrichtlinien in Defender für Office 365.](configure-mdo-anti-phishing-policies.md)

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Identitätswechseleinstellungen in Antiphishingrichtlinien in Microsoft Defender für Office 365

Weitere Informationen zu diesen Einstellungen finden Sie unter [Identitätswechseleinstellungen in Antiphishingrichtlinien in Microsoft Defender für Office 365.](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) Informationen zum Konfigurieren dieser Einstellungen finden Sie unter [Konfigurieren von Antiphishingrichtlinien in Defender für Office 365.](configure-mdo-anti-phishing-policies.md)

<br>

****

|Name des Sicherheitsfeatures|Standard|Standard|Streng|Kommentar|
|---|:---:|:---:|:---:|---|
|Geschützte Benutzer (Absender): **Benutzer zum Schutz aktivieren** <p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|Aus <p> `$false` <p> keine|Ein <p> `$true` <p> \<list of users\>|Ein <p> `$true` <p> \<list of users\>|Je nach Organisation wird empfohlen, Benutzer (Nachrichtensender) in Schlüsselrollen hinzuzufügen. Intern können geschützte Absender Ihr CEO, MOF und andere leitende Führungskräfte sein. Extern könnten geschützte Absender Mitglieder des Rates oder Ihr Board of Directors umfassen.|
|Geschützte Benutzer: **Wenn eine Nachricht als angenommener Benutzer erkannt wird** <p> _TargetedUserProtectionAction_|**Keine Aktion anwenden** <p> `NoAction`|**Quarantäne der Nachricht** <p> `Quarantine`|**Quarantäne der Nachricht** <p> `Quarantine`||
|Geschützte Domänen: **Domänen einschließen, die ich besitze** <p> _EnableOrganizationDomainsProtection_|Aus <p> `$false`|Ein <p> `$true`|Ein <p> `$true`||
|Geschützte Domänen: **Benutzerdefinierte Domänen einschließen** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|Aus <p> `$false` <p> keine|Ein <p> `$true` <p> \<list of domains\>|Ein <p> `$true` <p> \<list of domains\>|Je nach Organisation wird empfohlen, Domänen (Absenderdomänen) hinzuzufügen, die Sie nicht besitzen, aber häufig mit ihnen interagieren.|
|Geschützte Domänen: **Wenn eine Nachricht als imitierte Domäne erkannt wird** <p> _TargetedDomainProtectionAction_|**Keine Aktion anwenden** <p> `NoAction`|**Quarantäne der Nachricht** <p> `Quarantine`|**Quarantäne der Nachricht** <p> `Quarantine`||
|**Vertrauenswürdige Absender und Domänen hinzufügen** <p> _ExcludedSenders_ <p> _ExcludedDomains_|Keine|Keine|Keine|Je nach Organisation wird empfohlen, Absender oder Domänen hinzuzufügen, die fälschlicherweise als Identitätswechselversuche identifiziert wurden.|
|**Aktivieren der Postfachintelligenz** <p> _EnableMailboxIntelligence_|Ein <p> `$true`|Ein <p> `$true`|Ein <p> `$true`||
|**Aktivieren der Intelligenz für identitätswechselschutz** <p> _EnableMailboxIntelligenceProtection_|Aus <p> `$false`|Ein <p> `$true`|Ein <p> `$true`|Diese Einstellung ermöglicht die angegebene Aktion für Identitätswechselerkennungen durch Postfachintelligenz.|
|**Wenn die Postfachintelligenz Benutzer erkennt und die Identität angenommen hat** <p> _MailboxIntelligenceProtectionAction_|**Keine Aktion anwenden** <p> `NoAction`|**Verschieben der Nachricht in die Junk-E-Mail-Ordner des Empfängers** <p> `MoveToJmf`|**Quarantäne der Nachricht** <p> `Quarantine`||
|**Anzeigen des Benutzeridentitätswechsels Sicherheitstipp** <p> _EnableSimilarUsersSafetyTips_|Aus <p> `$false`|Ein <p> `$true`|Ein <p> `$true`||
|**Anzeigen des Domänenidentitätswechsels Sicherheitstipp** <p> _EnableSimilarDomainsSafetyTips_|Aus <p> `$false`|Ein <p> `$true`|Ein <p> `$true`||
|**Ungewöhnliche Zeichen für den Benutzeridentitätswechsel anzeigen Sicherheitstipp** <p> _EnableUnusualCharactersSafetyTips_|Aus <p> `$false`|Ein <p> `$true`|Ein <p> `$true`||
|

#### <a name="spoof-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Spoofingeinstellungen in Antiphishingrichtlinien in Microsoft Defender für Office 365

Beachten Sie, dass dies die gleichen Einstellungen sind, die in [den Antispamrichtlinieneinstellungen in EOP](#eop-anti-spam-policy-settings)verfügbar sind.

<br>

****

|Name des Sicherheitsfeatures|Standard|Standard|Streng|Kommentar|
|---|:---:|:---:|:---:|---|
|**Spoofintelligenz aktivieren** <p> _EnableSpoofIntelligence_|Ein <p> `$true`|Ein <p> `$true`|Ein <p> `$true`||
|**Wenn E-Mails als Spoofing erkannt werden** <p> _AuthenticationFailAction_|**Verschieben der Nachricht in die Junk-E-Mail-Ordner des Empfängers** <p> `MoveToJmf`|**Verschieben der Nachricht in die Junk-E-Mail-Ordner des Empfängers** <p> `MoveToJmf`|**Quarantäne der Nachricht** <p> `Quarantine`|Diese Einstellung gilt für gefälschte Absender, die automatisch blockiert wurden, wie im Einblick in die [Spoofintelligenz](learn-about-spoof-intelligence.md) gezeigt oder manuell in der [Mandanten-Zulassungs-/Sperrliste](tenant-allow-block-list.md)blockiert wurden.|
|**Anzeigen (?) für nicht authentifizierte Absender für Spoofing** <p> _EnableUnauthenticatedSender_|Ein <p> `$true`|Ein <p> `$true`|Ein <p> `$true`|Fügt dem Foto des Absenders in Outlook für nicht identifizierte gefälschte Absender ein Fragezeichen (?) hinzu. Weitere Informationen finden Sie unter [Spoofeinstellungen in Antiphishingrichtlinien](set-up-anti-phishing-policies.md).|
|**"via"-Tag anzeigen** <p> _EnableViaTag_|Ein <p> `$true`|Ein <p> `$true`|Ein <p> `$true`|Fügt der Absenderadresse ein Via-Tag (chris@contoso.com über fabrikam.com) hinzu, wenn es sich von der Domäne in der DKIM-Signatur oder der **MAIL FROM-Adresse** unterscheidet. <p> Wenn diese Einstellung für Sie nicht verfügbar ist, werden sowohl das **Fragezeichen** als auch das Via-Tag von der **Show (?) für nicht authentifizierte Absender für spoofing-Einstellungen** in Ihrer Organisation gesteuert.|
|

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Erweiterte Einstellungen in Antiphishingrichtlinien in Microsoft Defender für Office 365

Weitere Informationen zu dieser Einstellung finden Sie unter [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Informationen zum Konfigurieren dieser Einstellung finden Sie unter [Konfigurieren von Antiphishingrichtlinien in Defender für Office 365.](configure-mdo-anti-phishing-policies.md)

<br>

****

|Name des Sicherheitsfeatures|Standard|Standard|Streng|Kommentar|
|---|:---:|:---:|:---:|---|
|**Schwellenwert für Phishing-E-Mails** <p> _PhishThresholdLevel_|**1 – Standard** <p> `1`|**2 – Aggressiv** <p> `2`|**3 – Aggressiver** <p> `3`||
|

### <a name="safe-links-settings"></a>Safe Links-Einstellungen

Safe Links in Defender für Office 365 umfassen globale Einstellungen, die für alle Benutzer gelten, die in aktiven Richtlinien für Safe Links enthalten sind, sowie Einstellungen, die für jede Safe Links-Richtlinie spezifisch sind. Weitere Informationen finden Sie unter [Safe Links in Defender für Office 365](safe-links.md).

#### <a name="global-settings-for-safe-links"></a>Globale Einstellungen für Safe Links

Informationen zum Konfigurieren dieser Einstellungen finden Sie unter [Konfigurieren globaler Einstellungen für Safe Links in Defender für Office 365.](configure-global-settings-for-safe-links.md)

In PowerShell verwenden Sie das Cmdlet ["Set-AtpPolicyForO365"](/powershell/module/exchange/set-atppolicyforo365) für diese Einstellungen.

<br>

****

|Name des Sicherheitsfeatures|Standard|Standard|Streng|Kommentar|
|---|:---:|:---:|:---:|---|
|**Verwenden von Safe Links in: Office 365 Apps** <p> _EnableSafeLinksForO365Clients_|Ein <p> `$true`|Ein <p> `$true`|Ein <p> `$true`|Verwenden Sie Safe Links in unterstützten Office 365 Desktop- und Mobilen Apps (iOS und Android). Weitere Informationen finden Sie unter [Safe Links-Einstellungen für Office 365 Apps.](safe-links.md#safe-links-settings-for-office-365-apps)|
|**Nicht nachverfolgen, wenn Benutzer in Office 365 Apps auf geschützte Links klicken** <p> _TrackClicks_|Ein <p> `$false`|Aus <p> `$true`|Aus <p> `$true`|Durch Deaktivieren dieser Einstellung (Festlegen von _TrackClicks_ auf `$true` ) werden Benutzerklicks in unterstützten Office 365-Apps nachverfolgt.|
|**Benutzer dürfen in Office 365 Apps nicht auf die ursprüngliche URL klicken** <p> _AllowClickThrough_|Ein <p> `$false`|Ein <p> `$false`|Ein <p> `$false`|Durch Aktivieren dieser Einstellung (Festlegen von _AllowClickThrough_ auf `$false` ) wird verhindert, dass in unterstützten Office 365-Apps auf die ursprüngliche URL geklickt wird.|
|

#### <a name="safe-links-policy-settings"></a>Safe Richtlinieneinstellungen für Links

Informationen zum Konfigurieren dieser Einstellungen finden Sie unter ["Einrichten Safe Links"-Richtlinien in Microsoft Defender für Office 365.](set-up-safe-links-policies.md)

In PowerShell verwenden Sie die [Cmdlets New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy) und [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy) für diese Einstellungen.

> [!NOTE]
> Wie zuvor beschrieben, gibt es keine Standardrichtlinie für Safe Links. Die Werte in der Spalte "Standard" sind die Standardwerte in neuen Safe Verknüpfungsrichtlinien, die Sie erstellen.

<br>

****

|Name des Sicherheitsfeatures|Standard|Standard|Streng|Kommentar|
|---|:---:|:---:|:---:|---|
|**Wählen Sie die Aktion für unbekannte potenziell schädliche URLs in Nachrichten aus.** <p> _Isenabled_|Aus <p> `$false`|Ein <p> `$true`|Ein <p> `$true`||
|**Wählen Sie die Aktion für unbekannte oder potenziell schädliche URLs in Microsoft Teams** <p> _EnableSafeLinksForTeams_|Aus <p> `$false`|Ein <p> `$true`|Ein <p> `$true`||
|**Anwenden der Echtzeit-URL-Überprüfung auf verdächtige Links und Links, die auf Dateien verweisen** <p> _ScanUrls_|Aus <p> `$false`|Ein <p> `$true`|Ein <p> `$true`||
|**Warten Sie, bis die URL-Überprüfung abgeschlossen ist, bevor Sie die Nachricht übermitteln.** <p> _DeliverMessageAfterScan_|Aus <p> `$false`|Ein <p> `$true`|Ein <p> `$true`||
|**Anwenden Safe Links auf E-Mail-Nachrichten, die innerhalb der Organisation gesendet werden** <p> _EnableForInternalSenders_|Aus <p> `$false`|Ein <p> `$true`|Ein <p> `$true`||
|**Benutzerklicks nicht nachverfolgen** <p> _DoNotTrackUserClicks_|Aus <p> `$false`|Aus <p> `$false`|Aus <p> `$false`|Durch Deaktivieren dieser Einstellung (Festlegen von _DoNotTrackUserClicks_ auf `$false` ) werden Benutzerklicks verfolgt.|
|**Benutzern nicht gestatten, zur ursprünglichen URL zu klicken** <p> _DoNotAllowClickThrough_|Aus <p> `$false`|Ein <p> `$true`|Ein <p> `$true`|Durch Aktivieren dieser Einstellung (Festlegen von _"DoNotAllowClickThrough"_ auf `$true` ) wird das Klicken auf die ursprüngliche URL verhindert.|
|

### <a name="safe-attachments-settings"></a>Safe Anlageneinstellungen

Safe Anlagen in Microsoft Defender für Office 365 umfassen globale Einstellungen, die keine Beziehung zu Safe Anlagenrichtlinien haben, sowie Einstellungen, die für jede Safe Verknüpfungsrichtlinie spezifisch sind. Weitere Informationen finden Sie unter [Safe Anlagen in Defender für Office 365](safe-attachments.md).

#### <a name="global-settings-for-safe-attachments"></a>Globale Einstellungen für Safe Anlagen

Informationen zum Konfigurieren dieser Einstellungen finden Sie unter [Aktivieren von Safe Anlagen für SharePoint, OneDrive und Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) und Safe Dokumente in [Microsoft 365 E5.](safe-docs.md)

In PowerShell verwenden Sie das Cmdlet ["Set-AtpPolicyForO365"](/powershell/module/exchange/set-atppolicyforo365) für diese Einstellungen.

<br>

****

|Name des Sicherheitsfeatures|Standard|Standard|Streng|Kommentar|
|---|:---:|:---:|:---:|---|
|**Defender für Office 365 für SharePoint, OneDrive und Microsoft Teams aktivieren** <p> _EnableATPForSPOTeamsODB_|Ein <p> `$true`|Ein <p> `$true`||
|**Aktivieren Safe Dokumente für Office Clients** <p> _EnableSafeDocs_|Ein <p> `$true`|Ein <p> `$true`|Diese Einstellung ist nur mit Microsoft 365 E5 oder Microsoft 365 E5 Security Lizenzen verfügbar. Weitere Informationen finden Sie unter [Safe Dokumente in Microsoft Defender für Office 365](safe-docs.md).|
|**Zulassen, dass Benutzer durch geschützte Ansicht klicken, auch wenn Safe Dokumente die Datei als bösartig erkannt haben** <p> _AllowSafeDocsOpen_|Aus <p> `$false`|Aus <p> `$false`|Diese Einstellung bezieht sich auf Safe Dokumente.|
|

#### <a name="safe-attachments-policy-settings"></a>Safe Richtlinieneinstellungen für Anlagen

Informationen zum Konfigurieren dieser Einstellungen finden Sie unter [Einrichten Safe Anlagenrichtlinien in Defender für Office 365.](set-up-safe-attachments-policies.md)

In PowerShell verwenden Sie die Cmdlets [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy) und [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safelinkspolicy) für diese Einstellungen.

> [!NOTE]
> Wie zuvor beschrieben, gibt es keine Standardrichtlinie für Safe Anlagen. Die Werte in der Spalte "Standard" sind die Standardwerte in neuen Safe Anlagenrichtlinien, die Sie erstellen.

<br>

****

|Name des Sicherheitsfeatures|Standard|Standard|Streng|Kommentar|
|---|:---:|:---:|:---:|---|
|**Safe Anlagen unbekannte Schadsoftwareantwort** <p> _Action_|Blockieren <p> `Block`|Blockieren <p> `Block`|Blockieren <p> `Block`||
|**Anlage bei Erkennung umleiten:** **Umleitung aktivieren** <p> _Redirect_ <p> _RedirectAddress_|Deaktiviert und keine E-Mail-Adresse angegeben. <p> `$true` <p> keine|Aktivieren und Angeben einer E-Mail-Adresse. <p> `$true` <p> eine E-Mail-Adresse|Aktivieren und Angeben einer E-Mail-Adresse. <p> `$true` <p> eine E-Mail-Adresse|Leiten Sie Nachrichten zur Überprüfung an einen Sicherheitsadministrator weiter.|
|**Wenden Sie die oben genannte Auswahl an, wenn bei der Schadsoftwareüberprüfung nach Anlagen ein Zeitüberschreitung auftritt oder ein Fehler auftritt.** <p> _ActionOnError_|Ein <p> `$true`|Ein <p> `$true`|Ein <p> `$true`||
|

## <a name="related-articles"></a>Verwandte Artikel

- Suchen Sie nach bewährten Methoden für **Exchange Nachrichtenflussregeln (auch als Transportregeln bezeichnet)?** Bewährte [Methoden zum Konfigurieren von Nachrichtenflussregeln in Exchange Online.](/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices)

- Administratoren und Benutzer können falsch positive Ergebnisse (gute E-Mails als falsch markiert) und falsch negative (ungültige E-Mails sind zulässig) zur Analyse an Microsoft übermitteln. Weitere Informationen finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).

- Verwenden Sie diese Links, um Informationen zum **Einrichten** Ihres [EOP-Diensts](/exchange/standalone-eop/set-up-your-eop-service)und **zum Konfigurieren von** Microsoft Defender für Office 365 zu [erhalten.](defender-for-office-365.md) Vergessen Sie nicht die hilfreichen Anweisungen in "[Schutz vor Bedrohungen in Office 365".](protect-against-threats.md)

- **Sicherheitsgrundwerte für Windows** finden Sie hier: [Wo erhalte ich die Sicherheitsgrundwerte?](/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) für GPO/lokale Optionen, und [verwenden Sie Sicherheitsgrundwerte, um Windows 10 Geräte in Intune](/intune/protect/security-baselines) für Intune-basierte Sicherheit zu konfigurieren. Schließlich ist ein Vergleich zwischen Microsoft Defender für Endpunkt und Microsoft Intune Sicherheitsgrundwerten in [Microsoft Defender für Endpunkt vergleichen und den Windows Intune-Sicherheitsgrundwerten](/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)verfügbar.
