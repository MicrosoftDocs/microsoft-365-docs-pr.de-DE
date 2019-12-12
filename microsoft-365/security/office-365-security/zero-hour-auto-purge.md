---
title: Automatische Bereinigung zur Nullstunde – Schutz vor Spam und Schadsoftware
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
description: Zero-Hour Auto Purge (zap) ist eine e-Mail-Schutzfunktion, die Nachrichten mit Spam oder Schadsoftware erkennt, die bereits an die Posteingänge Ihrer Benutzer übermittelt wurden, und dann den schädlichen Inhalt harmlos macht. Wie zap Dies bewirkt, hängt vom Typ der erkannten schädlichen Inhalte ab.
ms.openlocfilehash: 3a888e6a6b4de57efcb0a8b8284432a2b9f1095a
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971383"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a>Automatische Bereinigung zur Nullstunde – Schutz vor Spam und Schadsoftware

## <a name="overview"></a>Übersicht

Zero-Hour Auto Purge (zap) ist eine e-Mail-Schutzfunktion, die Nachrichten mit Phishing, Spam oder Schadsoftware erkennt, die bereits an die Posteingänge Ihrer Benutzer übermittelt wurden, und dann den schädlichen Inhalt harmlos macht. Wie zap Dies bewirkt, hängt vom Typ der erkannten schädlichen Inhalte ab. E-Mails können aufgrund von e-Mail-Inhalten, URLs oder Anlagen gezappt werden.

ZAP ist mit dem Standard Exchange Online Schutz verfügbar, der in jedem Office 365-Abonnement enthalten ist, das Exchange Online Postfächer enthält.

## <a name="how-zap-works"></a>Funktionsweise von zap

Office 365 aktualisiert das Anti-Spam-Modul und die Malware Signaturen in Echtzeit auf täglicher Basis. Allerdings erhalten Ihre Benutzer möglicherweise weiterhin Schadsoftware-Nachrichten, die aus einer Vielzahl von Gründen an ihre Posteingänge gesendet werden, einschließlich, wenn der Inhalt nach der Zustellung an die Benutzer Waffen basiert. Zap behebt dies, indem Updates für die Office 365 Spam-und Malware Signaturen kontinuierlich überwacht werden. Zap kann zuvor zugestellte Nachrichten, die sich bereits in den Posteingängen von Benutzern befinden, suchen und entfernen.

Die ZAP-Aktion ist nahtlos für den Postfachbenutzer; Sie werden nicht benachrichtigt, wenn eine e-Mail-Nachricht verschoben wird. Die Nachricht darf nicht älter als 2 Tage sein.

Zulassungslisten, [Nachrichtenfluss Regeln](use-transport-rules-to-configure-bulk-email-filtering.md) (auch bekannt als Transportregeln) und Endbenutzer Regeln oder zusätzliche Filter haben Vorrang vor zap.

### <a name="malware-zap"></a>Malware zap

Für neu erkannte Schadsoftware verschiebt zap die gesamte Nachricht, einschließlich der Anlage, in die Quarantäne für Schadsoftware. Nachrichten werden unabhängig vom Lesestatus der e-Mail verschoben. Wenn wir ein Schadsoftware-Signal für eine Nachricht im Prozess der dynamischen Übermittlungs Überprüfung erhalten, wird zap in der Nachricht zu einer Junk-Aktion übergehen. Anschließend wird die dynamische Zustellung so abgeschlossen, dass die Zeit der Übermittlung überprüft wird, und Sie können die entsprechende Aktion durchführen.

Malware zap ist in der Schadsoftware-Richtlinie standardmäßig aktiviert. Sie können Malware zap mithilfe des Parameters *ZapEnabled* im Cmdlet " [MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) " in Exchange Online PowerShell oder Exchange Online Protection PowerShell deaktivieren. Malware zap kann auch durch Bearbeiten der Schadsoftware-Richtlinie im Security and Compliance Center aktiviert oder deaktiviert werden.

### <a name="phish-zap"></a>Phishing-zap

Bei e-Mails, die nach der Zustellung als "Phishing" identifiziert werden, nimmt zap eine Aktion gemäß der Spam Richtlinie vor, die einen bestimmten Benutzer abdeckt, unabhängig vom Lesestatus der e-Mail. Wenn die Richtlinie Phishing-Aktion so festgelegt ist, dass *keine* Aktion ausgeführt wird (X-Header hinzufügen, Betreff ändern, keine Aktion), wird zap keine Aktion für die e-Mail durchführen. Wenn die Phishing-Aktion auf "Junk verschieben" festgelegt ist, verschiebt zap die Nachricht in den Ordner "Junk-e-Mail" des Posteingangs des Benutzers. **Bei jeder anderen Phishing-Aktion (Redirect, DELETE, Quarantine) verschiebt zap die Nachricht in die Phishing-Quarantäne**. Lesen Sie weiter unten für Konfigurationsanforderungen und-Ausschlüsse. Weitere Informationen zum [Konfigurieren ihrer Spamfilter Richtlinien](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) finden Sie hier.

Phishing-zap ist in der Spam Richtlinie standardmäßig aktiviert. Phishing-zap kann mithilfe des *PhishZapEnabled* -Parameters von [sethostedcontentfilterpolicy dient zum](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy), einem EoP-Cmdlet, deaktiviert werden.

### <a name="spam-zap"></a>Spam zap

Bei e-Mail-Nachrichten, die nach der Zustellung als Spam identifiziert werden, erfolgt die Aktion gemäß der Spam Richtlinie, die den jeweiligen Benutzer abdeckt, nur, wenn die Nachricht ungelesen ist.  Wenn die Spam Aktion der Richtlinie so festgelegt ist, dass keine Aktion ausgeführt wird (X-Header hinzufügen, Betreff ändern, keine Aktion), wird zap keine Aktion für die e-Mail durchführen. Wenn die Spam Aktion auf "Junk" verschoben wird, verschiebt zap die Nachricht in den Ordner "Junk-e-Mail" des Posteingangs des Benutzers. **Bei anderen Spam Aktionen (Redirect, DELETE, Quarantine) verschiebt zap die Nachricht in die Quarantäne für Spam**. Lesen Sie weiter unten für Konfigurationsanforderungen und-Ausschlüsse. Weitere Informationen zum [Konfigurieren ihrer Spamfilter Richtlinien](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) finden Sie hier.

Spam zap ist in der Spam Richtlinie standardmäßig aktiviert. Sie können Spam zap mithilfe des *SpamZapEnabled* -Parameters von [sethostedcontentfilterpolicy dient zum-](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy) Cmdlet in Exchange Online PowerShell oder Exchange Online Protection PowerShell deaktivieren.

### <a name="phish-and-spam-zap-requirements-exclusions-and-notices"></a>Phishing-und Spam zap-Anforderungen, Ausschlüsse und Benachrichtigungen

> [!IMPORTANT]
> der vorherige *ZapEnabled* -Cmdlet-Parameter, der sowohl Phishing als auch Spam zap gesteuert **hat, wird am 1. Februar 2020 veraltet**. Wenn Sie Skripts geschrieben haben, die den ZapEnabled-Parameter verwenden, wird empfohlen, diese für die Verwendung von SpamZapEnabled und PhishZapEnabled zu aktualisieren. In der Übergangsphase werden alle drei Parameter (ZapEnabled, PhishZapEnabled und SpamZapEnabled) über das Cmdlet zur Verfügung gestellt. Bis zur expliziten Festlegung über UI oder PowerShell wird PhishZapEnabled und SpamZapEnabled einen geerbten Wert aus dem ZapEnabled-Parameter anzeigen. Nachdem die neuen Parameter festgelegt wurden, werden Sie nicht mehr vom ZapEnabled-Parameter geerbt. Nachdem die Einstellung veraltet ist, hat ZapEnabled keine Auswirkung auf die Eigenschaften PhishZapEnabled oder SpamZapEnabled, und ZapEnabled wird aus der Liste der Parameter in Cmdlets entfernt.

Zap verschiebt keine Nachrichten in den Quarantänebereich, die sich im Prozess der dynamischen Übermittlungs Überprüfung befinden oder die bereits über ein Schadsoftware-Urteil mit einer ersetzten Anlage verfügt. Wenn ein Phishing-oder Spam Signal für diese Arten von Nachrichten empfangen wird und die Spam-Richtlinie/Phishing-Aktion so eingestellt ist, dass eine Aktion ausgeführt wird (in Junk-e-Mails verschieben, umleiten, löschen, isolieren), wird zap standardmäßig auf die Aktion "in Junk-e-Mail verschieben" gesetzt. Damit zap eine Aktion "zu Junk" in einer Nachricht durchführen kann, muss der Junk-e-Mail-Schutz für den Benutzer mit den Standardeinstellungen für Junk-e-Mail aktiviert sein. (Weitere Informationen zu Benutzeroptionen in Outlook finden Sie unter [Ändern der Schutzebene im Junk-e-Mail-Filter](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b) .)

## <a name="how-to-see-if-zap-moved-your-message"></a>Wie Sie sehen, ob zap Ihre Nachricht verschoben hat

Um festzustellen, ob zap Ihre Nachricht verschoben hat, können Sie entweder den [Threat Protection-Status Bericht](../../compliance/view-email-security-reports.md#threat-protection-status-report) oder den [Threat-Explorer (und Echt Zeit Erkennungen)](threat-explorer.md)verwenden.

## <a name="disable-zap"></a>Zap deaktivieren

Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit Exchange Online Protection PowerShell finden Sie unter [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

### <a name="disable-malware-zap"></a>Deaktivieren von Malware zap * *

"Malware Zap" kann über den Parameter " *ZapEnabled* " im Cmdlet " [MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) " in Exchange Online PowerShell oder Exchange Online Protection PowerShell deaktiviert werden. Malware zap kann auch durch Bearbeiten der Schadsoftware-Richtlinie im Security and Compliance Center aktiviert oder deaktiviert werden.

In diesem Beispiel wird zap in der Malware Filterrichtlinie mit dem Namen "Test" deaktiviert.

```Powershell
Set-MalwareFilterPolicy -Identity Test -ZapEnabled $false
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy).

### <a name="disable-phish-zap-and-spam-zap"></a>Deaktivieren von Phishing Zap und Spam zap

Um Phishing und Spam zap für Ihren O365-Mandanten oder eine Gruppe von Benutzern zu deaktivieren, verwenden Sie die Parameter *PhishZapEnabled* und *SpamZapEnabled* von [sethostedcontentfilterpolicy dient zum](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy), ein EoP-Cmdlet.

Im folgenden Beispiel sind Phishing und Spam zap für eine Inhaltsfilter Richtlinie mit dem Namen "Test" deaktiviert.

```Powershell
Set-HostedContentFilterPolicy -Identity Test -PhishZapEnabled $false -SpamZapEnabled $false
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-hostedcontentfilterpolicy dient zum](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy).

## <a name="faq"></a>Häufig gestellte Fragen

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a>Was passiert, wenn eine legitime Nachricht in den Junk-e-Mail-Ordner verschoben wird?

Sie sollten den normalen Berichtsprozess für [falsch positive](../../compliance/prevent-email-from-being-marked-as-spam.md)Vorgänge ausführen. Der einzige Grund, warum die Nachricht aus dem Posteingang in den Junk-e-Mail-Ordner verschoben würde, liegt daran, dass der Dienst festgestellt hat, dass die Nachricht als Spam oder böswillig eingestuft wurde.

### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a>Was kann ich tun, wenn ich die Office 365 Quarantäne anstelle des Junk-e-Mail-Ordners verwende?

Zap wird entsprechend der Konfiguration der Einstellungen für Phishing und Spam Aktionen in ihrer Anti-Spam-Richtlinie Maßnahmen ergreifen. Siehe oben für weitere Details zu Schadsoftware, Phishing und Spam zap.

### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a>Was geschieht, wenn ich über eine benutzerdefinierte Nachrichtenfluss Regel (Block/Zulassungsregel) verfüge?

Von Administratoren erstellte Regeln (Nachrichtenfluss Regeln) oder Block-und Zulassungsregeln haben Vorrang. Solche Nachrichten werden von den Funktionskriterien ausgeschlossen, sodass die Nachrichtenübermittlung der Regelaktion (Block/Zulassungsregel) folgt.

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rule"></a>Was passiert, wenn eine Nachricht in einen anderen Ordner verschoben wird (z.b. Posteingangsregel)?

Zap funktioniert in diesem Fall weiterhin, es sei denn, die Nachricht wurde gelöscht oder ist in Junk.

## <a name="related-topics"></a>Verwandte Themen

[Antispamschutz für Office 365-E-Mails](anti-spam-protection.md)

[Blockieren von E-Mail-Spam mit dem Office 365-Spamfilter zur Vermeidung von falsch negativen Einträgen](reduce-spam-email.md)
