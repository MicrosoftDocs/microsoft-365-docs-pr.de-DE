---
title: Bewährte Methoden für die Konfiguration von EoP und Office 365 ATP-Sicherheit, bewährte Methoden, Einstellungen, Empfehlungen, Absender Richtlinien Framework, domänenbasierte Nachrichtenberichterstattung und Konformität, DomainKeys identifizierte e-Mails, Schritte, wie funktioniert das?
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 09/18/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: Was sind bewährte Methoden für Exchange Online Protection (EoP) und ATP-Sicherheitseinstellungen (Advanced Threat Protection)? Was wird empfohlen? Was sollte aggressiv verwendet werden? Und welche Extras erhalten Sie, wenn Sie auch Advanced Threat Protection (ATP) verwenden?
ms.openlocfilehash: fb6a39756c54e46f5ac8208c9c92af30bc144a57
ms.sourcegitcommit: d4aa94716b33e6c270ae7adfbdc4c19cf4a0087d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "37387152"
---
# <a name="best-practices-for-configuring-eop-and-office-365-atp-security"></a>Bewährte Methoden für die Konfiguration von EoP und Office 365 ATP-Sicherheit

Exchange Online Protection (EoP) ist das Herzstück der Sicherheit für E3-Office 365-Abonnements. Es ist optional und sogar erwünscht, dass E3-Kunden ein Abonnement für Office 365 Advanced Threat Protection (ATP), ex erwerben. ATP-Plan 1 oder ATP-Plan 2, um die in E5 Office 365-Abonnements verfügbare zusätzliche Sicherheit zu nutzen.

Wir besprechen zwei Sicherheitsstufen, die in EoP als "empfohlen" und "aggressiv" bezeichnet werden, sowie Kommentare zur Verwendung von Features auf beiden Sicherheitsebenen. Die Abschnitte beginnen mit e-Mail-Validierung und Authentifizierung, die einige basteln außerhalb Office 365, in DNS, und sichert ausgehende e-Mails, wodurch Mandanten gute Bürger auf die Ressourcen, die Sie Mail umfasst. Diese Einstellungen schützen Ihr Abonnement am besten.


## <a name="email-authentication"></a>E-Mail-Authentifizierung

SPF-, DKIM-und DMARC sind Akronyme für Sender Policy Framework, DomainKeys identifizierte e-Mails und domänenbasierte Nachrichtenauthentifizierung, Berichterstellung und Konformität (ganz ein Biss) und bilden die Grundlage für die e-Mail-Authentifizierung und-Validierung.

Diese Methoden verarbeiten ausgehende e-Mails von Office 365 und helfen Zielsystemen zu vertrauen, dass e-Mails von Ihrer Domäne gültig sind. Sie sind die einzigen Best Practices, die wir abdecken, die Konfigurationen umfassen, die *außerhalb* von Office 365 in Ihrem DNS vorgenommen werden. Spezifische Konfigurationsschritte finden Sie im Abschnitt über die [e-Mail-Validierung und-Authentifizierung](https://docs.microsoft.com/en-us/office365/securitycompliance/how-office-365-uses-spf-to-prevent-spoofing) im Inhaltsverzeichnis Sicherheit und Kompatibilität.


|Name des Sicherheitsfeatures  |Empfohlen |Aggressive  |Kommentar  |
|---------|---------|---------|---------|
|[Erstellen von SPF-Einträgen](https://docs.microsoft.com/en-us/office365/securitycompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)    | v        |    v     |   -      |
|[Konfigurieren der DKIM-Signierung für Domänen](https://docs.microsoft.com/en-us/office365/securitycompliance/use-dkim-to-validate-outbound-email)     |  v       |    v     |  -       |
|[Implementieren von DMARC mit Reject-oder Quarantine-Aktion](https://docs.microsoft.com/en-us/office365/securitycompliance/use-dmarc-to-validate-email)     |   v      |     v    |   Verwenden Sie Action = None für Recommended, und Action = Reject für aggressive.     |

> [!IMPORTANT]
> Wenn Sie mit Sicherheitsrollen und-Berechtigungen arbeiten möchten, stellen Sie sicher, dass Sie über die richtigen Rollen in Office 365 oder über das Security and Compliance Center verfügen. Wenn Sie ein *Sicherheitsadministrator* in Azure Active Directory, ein *globaler Administrator* in Office 365 oder ein *Exchange Onlineer Organisations Manager* in Exchange Online/Exchange Online PowerShell sind, können Sie loslegen.

## <a name="anti-spam-anti-malware-and-anti-phishing"></a>Antispam-, Antischadsoftware-und Anti-Phishing-Schutz

Sowohl Anti-Spam als auch Antischadsoftware sind Features von EoP. Spamfilterung (standardmäßig in Office 365) scannt alle e-Mails und weist jeder e-Mail einen SCL-Nummernwert (Spam Confidence Level) zu. Lediglich um zu klären, ist der Zweck der Aufzählung, wie sicher der Filter ist, dass die e-Mail Spam ist (oder nicht). Niedrige Werte wie-1 sind nicht-Spam von sicheren Absendern und landet in einem Benutzer Posteingang. High Scores, wie 7, 8 oder 9 sind entweder sehr verdächtig oder bekannte Spammer und Heads für die Junk-e-Mail eines Benutzers oder die vom Administrator zugängliche Quarantäne.

Die Malware Filterung ist auch in Office 365 standardmäßig aktiviert. Wie Anti-Spam-Filterung funktionieren Antischadsoftware-Filter sowohl an eingehenden als auch an ausgehenden e-Mails. In beiden Fällen kann dieser Schutz von Administratoren für eine bessere Anpassung konfiguriert werden.

Phishing-Filter sind in Office 365 standardmäßig aktiviert, sollten jedoch für eine bessere Anpassung konfiguriert werden. Hier erfahren Sie, was wir für Anti-Phishing in EoP empfehlen würden.

### <a name="anti-spam"></a>Anti-Spam

|Name des Sicherheitsfeatures  |Empfohlen |Aggressive  |Kommentar  |
|---------|---------|---------|---------|
|Aufbewahrungszeitraum für Quarantäne    |   v      |     v    |   30 Tage   |
|Spam Benachrichtigungshäufigkeit für Endbenutzer   |   v      |     v    |   3 Tage   |
|Nullstunde AUTOPURGE sollte aktiviert sein   |   v      |     v    |   Wahr  |
|Spam erkennungsaktion sollte an gesendet werden | JMF | Quarantäne | - |
|Spam erkennungsaktion mit hoher Vertrauenswürdigkeit sollte an gesendet werden | Quarantäne | Quarantäne| - |
|Massen erkennungsaktion sollte auf festgelegt werden | JMF | Quarantäne | - |
|Schwellenwert für Massen-e-Mail festlegen | 6 | 4 | - |
|Sicherheitstipps sollten aktiviert sein| True | True | - |
|Spambenachrichtigung für Endbenutzer aktivieren| Wahr | False | - |
|Zugelassene Absender | Keine | Keine | - |
|Zulässige Absenderdomänen | Keine | Keine | - |
|Blockierte Absender | Keine | Keine | - |
|Blockierte Absenderdomänen | Keine | Keine | - |
|Richtlinie für ausgehende Spam RRL | 500 | 500 | - |

Empfohlen für **Off** in empfohlenen und aggressiven Ebenen:

|Name des Sicherheitsfeatures  |
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

Empfohlen für **on** in Recommended and aggressiv Levels:

|Name des Sicherheitsfeatures  |
|---------|
|MarkAsSpamSpfRecordHardFail|
|MarkAsSpamBulkMail|

### <a name="anti-malware"></a>Anti-Malware

|Name des Sicherheitsfeatures  |Empfohlen |Aggressive  |Kommentar  |
|---------|---------|---------|---------|
|Konfigurieren von Schadsoftware-Benachrichtigungen für interne Quellen |Ja |Ja |- |
|Deaktivieren der Benachrichtigung externer Absender zur Erkennung von Schadsoftware |Ja |Ja |- |
|Verwenden des Typs "allgemeiner Anlagentyp Filter" zum Blockieren verdächtiger Dateitypen | Ja |Ja |- |
|Malware zap |True |True |- |
|Schadsoftware-Aktion |Block |Block |- |

### <a name="anti-phishing"></a>Anti-Phishing

|Name des Sicherheitsfeatures  |Empfohlen |Aggressive  |Kommentar  |
|---------|---------|---------|---------|
|Nullstunde AUTOPURGE sollte aktiviert sein-Phishing| True | True | - | 
|Die Phishing-erkennungsaktion sollte auf festgelegt werden. | Quarantäne – Anforderung | Quarantäne – Administrator | - |
|Die Phishing-erkennungsaktion für hohe Zuverlässigkeit sollte auf festgelegt werden. | Quarantäne – Administrator | Quarantäne – Administrator | - |
|EnableMailboxIntelligence | True | True | - |
|EnableSimilarUsersSafetyTips | True | True | - |
|EnableSimilarDomainsSafetyTips | True | True | - |
|EnableUnusualCharactersSafetyTips | True | True | - |
|TargetedUserProtectionAction |NoAction |Block | - |
|MailboxIntelligenceProtectionAction |NoAction |Block | - |
|TargetedDomainProtectionAction |NoAction |Block | - |
|AuthenticationFailAction |MoveToJmf |Quarantäne | - |
|AntiSpoofEnforcementType |Hoch |Hoch | - |
|EnableAuthenticationSafetyTip |False |Wahr | - |
|EnableAntiSpoofEnforcement |True |True | - |
|EnableUnauthenticatedSender |True |True | - |
|EnableAuthenticationSoftPassSafetyTip |False |Wahr | - |
|TreatSoftPassAsAuthenticated |Wahr |False | - |
|EnableSuspiciousSafetyTip |True |True | - |

## <a name="office-365-advanced-threat-protection-atp-security"></a>Office 365 Advanced Threat Protection (ATP)-Sicherheit

Früher sagte ich, dass es für E3-Abonnements empfohlen wurde, einen Office 365 ATP-Plan 1 hinzuzufügen, oder den vollständig realisierten ATP-Plan 2. Erweitertes Anti-Phishing ist ein Grund, warum. Standardmäßig aktiviert ist, ***muss*** Anti-Phishing mit Richtlinien konfiguriert werden, die ausgeführt werden sollen. Wenn Sie vergessen, die Konfiguration von Anti-Phishing-Richtlinien zu Unternehmen, müssen Sie sicherstellen, dass der Schritt-2 nach dem Hinzufügen eines ATP-Abonnements besteht.

> [!IMPORTANT]
>  Wenn Sie über ein E5-Abonnement verfügen, haben Sie derzeit [ATP-Plan 2](https://products.office.com/en-us/exchange/advance-threat-protection). Überprüfen Sie diesen Link, wenn Sie herausfinden möchten, [was in ATP neu ist](https://review.docs.microsoft.com/en-us/microsoft-365/security/office-365-security/whats-new-in-office-365-atp?branch=oatp-newstuff).

### <a name="advanced-anti-phishing"></a>Erweitertes Anti-Phishing

Phishing ist ein Versuch, sich als seriöses Unternehmen oder eine Person zu tarnen, um persönliche Informationen wie Kreditkartennummern oder Computer-oder Geräte Pins oder Kennwörter zu stehlen. Phishing kann Folgendes beinhalten:

- **Spoofing**, bei dem Spoofer versuchen, e-Mails im Namen eines bestimmten Ziels in einer Domäne zu senden (beispielsweise Ellar@2020contoso.com, die versuchen, e-Mails für Ellar@2020litware.com zu senden (ein Szenario mit e-Mail-Authentifizierungsmethoden kann helfen zu vereiteln). 

- **Identitätswechsel**, bei dem e-Mail-Nachrichten empfangen werden, deren Absender einer Zieldomäne oder einem Benutzernamen optisch ähnlich (oder gleich aussehen). Der ungültige Akteur hier imitiert einen bestimmten Benutzernamen oder gibt vor, dass er e-Mails von einer Zieldomäne sendet. Hier ist ein Schein Domäne: Ellar @ 2020 | itware. com, und hier ist ein Vorwand Benutzer: ellαr @ 2020litware. com (sehen Sie genau die Domänen-und Benutzernamen in diesen Beispielen, um den Domänen-und Benutzeridentitätswechsel abzufangen).

Wenn Sie Ihrem EoP ein Office 365 ATP-Abonnement hinzugefügt haben, müssen Sie die folgenden Konfigurationen festlegen.

|Name des Sicherheitsfeatures  |Empfohlen |Aggressive  |Kommentar  |
|---------|---------|---------|---------|
|Festlegen des erweiterten Phishing-Schwellenwerts auf | 2 | 4 | - |
|Aktivieren des Schutzes gegen Identitätswechsel | Ja | Ja | - |
|Aktivieren von Post Fach Intelligenz in Richtlinien zum Schutz vor Identitätswechsel | Ja | Ja | - |
|Aktivieren des Post Fach informationsbasierten Identitätswechsel Schutzes | Ja | Ja | - |
|Die Aktion für den Domänen Identitätswechsel sollte | JMF | Quarantäne | - |
|Die Aktion für den Benutzeridentitätswechsel sollte | JMF | Benachrichtigungs | - |
|Die Aktion zum Schutz von Postfachinformationen basierend auf Identitätswechsel sollte |Tipp  |JMF | - |

### <a name="safe-links-and-safe-attachments"></a>Sichere Links und sichere Anlagen

 ATP enthält die Richtlinien für sichere Anlagen und sichere Links, um zu verhindern, dass e-Mails mit potenziell böswilligen Anlagen zugestellt werden, und um zu verhindern, dass Benutzer auf potenziell unsichere URLs klicken und auf Sie Reisen.

#### <a name="safe-links"></a>Sichere Links

|Name des Sicherheitsfeatures  |Empfohlen |Aggressive  |Kommentar  |
|---------|---------|---------|---------|
|ATP-sichere Links sollten Benutzerklicks für Antwort Zwecke nachverfolgen |Ja |Ja |- |
|ATP-sichere Links sollten für Office-Anwendungen aktiviert werden |Ja |Ja |- |
|ATP-sichere Links sollten für Intra-Domäne aktiviert werden |Ja |Ja |- |
|ATP-sichere Links sollten die Echt Zeit-URL-Überprüfung auf verdächtige Links und Links anwenden, die auf Dateien verweisen. |Ja |Ja |- |
|ATP-sichere Links sollten warten, bis die URL-Überprüfung abgeschlossen ist, bevor die Nachricht gesendet wird. |Ja |Ja |- |
<!--
|URLs to block | | | |
|URLs not to wrap | | | |-->

#### <a name="safe-attachments"></a>Sichere Anlagen

|Name des Sicherheitsfeatures  |Empfohlen |Aggressive  |Kommentar  |
|---------|---------|---------|---------|
|Richtlinie für ATP-sichere Anlagen sollte |Quarantäne |Quarantäne |- |
|ATP-Schutz sollte für OneDrive, SharePoint und Microsoft Teams aktiviert werden |Ja |Ja |- |
<!--
|Allowed file hashes | | | |
|Blocked file hashes | | | |
-->

## <a name="miscellaneous-settings"></a>Verschiedene Einstellungen

Diese Einstellungen umfassen eine Reihe von Features, die nicht unbedingt in bestimmte Kategorien oben passt. Möglicherweise finden Sie hier auch einige 1-Off-Einstellungen.

Name des Sicherheitsfeatures  |Empfohlen |Aggressive  |Kommentar  |
|---------|---------|---------|---------|
|Erstellen von SPF-Einträgen |Ja |Ja |- |
|Konfigurieren der DKIM-Signierung für Domänen |Ja |Ja |- |
|Implementieren von domänenbasierter Nachrichtenberichterstattung und Konformität (DMARC) mit Ablehnungs-oder Quarantäneaktionen |Action = keine |Action = ablehnen | |
|Bereitstellen des Berichtsnachrichten-Add-ons zur Verbesserung der Berichterstellung für verdächtige e-Mails durch Endbenutzer |Ja |Ja |- |
|Planen von Malware-und Spam Berichten |Ja |Ja |- |
|Automatische FOWARDING in externe Domänen sollten nicht zugelassen oder überwacht werden |- |Ja |- |
|Einheitliche Überwachung sollte aktiviert sein |Ja |Ja |- |
|IMAP sollte deaktiviert werden, wenn nicht erforderlich |- |deaktiviert |- |
|Pop sollte deaktiviert werden, wenn nicht erforderlich |- |deaktiviert |- |
|Die SMTP-authentifizierte Übermittlung sollte deaktiviert werden, wenn Sie für Anwendungen nicht erforderlich ist. |- |deaktiviert |- |
|EWS sollte deaktiviert werden |- |deaktiviert |- |
|PowerShell |- |deaktiviert |- |
|Konfigurieren des Sender Policy-Frameworks auf einen harten Fehler |-all |-all |- |
|Verwenden von Spoofing Intelligence zum Whitelisting von Absendern, wann immer möglich |Ja |Ja |- |
|Verzeichnisbasierte Edge-Blockierung (Blockierung) |Aktiviert |Aktiviert |Domain-Typ = autorisierend |
