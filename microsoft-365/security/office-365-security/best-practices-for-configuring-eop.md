---
title: Bewährte Methoden für das Konfigurieren von EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Befolgen Sie diese Best Practice-Empfehlungen für den eigenständigen Exchange Online Schutz (EoP), um sich für den Erfolg einzusetzen und häufige Konfigurationsfehler zu vermeiden.
ms.openlocfilehash: b734fe87b82c243531944bbd9cf53d22d5b42f53
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48414034"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>Bewährte Methoden für die Konfiguration eigenständiger EoP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Befolgen Sie diese Best Practice-Empfehlungen für den eigenständigen Exchange Online Schutz (EoP), um sich für den Erfolg einzusetzen und häufige Konfigurationsfehler zu vermeiden. In diesem Thema wird vorausgesetzt, dass Sie den Setup-Prozess bereits abgeschlossen haben. Wenn Sie das EOP-Setup nicht abgeschlossen haben, finden Sie weitere Informationen unter [Einrichten Ihres EOP-Diensts](set-up-your-eop-service.md).

## <a name="use-a-test-domain"></a>Verwenden einer Testdomäne

Es wird empfohlen, eine Testdomäne, eine Unterdomäne oder eine Domäne von geringem Volumen zu verwenden, um Dienstfunktionen zu prüfen, bevor Sie sie auf Ihren Produktionsdomänen mit höherem Volumen implementieren.

## <a name="synchronize-recipients"></a>Synchronisieren von Empfängern

Wenn Ihre Organisation über vorhandene Benutzerkonten in einer lokalen Active Directory Umgebung verfügt, können Sie diese Konten mit Azure Active Directory in der Cloud synchronisieren. Es wird empfohlen, Verzeichnissynchronisierung zu verwenden. Weitere Informationen über die Vorteile der Verzeichnissynchronisierung und über die Schritte zu ihrer Einrichtung finden Sie unter [Verwalten von E-Mail-Benutzern in EOP](manage-mail-users-in-eop.md).

## <a name="recommended-settings"></a>Empfohlene Einstellungen

Wir ermächtigen Sicherheitsadministratoren, Ihre Sicherheitseinstellungen anzupassen, um die Anforderungen Ihrer Organisation zu erfüllen. Obwohl es sich in der Regel um zwei Sicherheitsstufen in EoP und Office 365 ATP handelt, empfehlen wir: Standard und Strict. Diese Einstellungen werden in den [empfohlenen Einstellungen für EoP und Office 365 ATP-Sicherheit](recommended-settings-for-eop-and-office365-atp.md)aufgeführt.

### <a name="miscellaneousnon-policy-settings"></a>Verschiedene/nicht-Richtlinieneinstellungen

Diese Einstellungen umfassen eine Reihe von Features, die sich außerhalb von Sicherheitsrichtlinien befinden.

****

|Name des Sicherheitsfeatures|Standard|Strict|Kommentar|
|---|---|---|---|
|[Einrichten von SPF zum Verhindern von Spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Ja|Ja||
|[Verwenden von DKIM zum Überprüfen ausgehender E-Mails, die von Ihrer benutzerdefinierten Domäne in Office 365 gesendet werden](use-dkim-to-validate-outbound-email.md)|Ja|Ja||
|[Verwenden von DMARC zum Validieren von E-Mails in Office 365](use-dmarc-to-validate-email.md)|Ja|Ja|Verwenden Sie `action=quarantine` für Standard und `action=reject` für Strict.|
|Bereitstellen des [Berichtsnachrichten-Add-ins](enable-the-report-message-add-in.md) zur Verbesserung der Berichterstellung für verdächtige e-Mails durch Endbenutzer|Ja|Ja||
|Planen von Malware-und Spam Berichten|Ja|Ja||
|Die automatische Weiterleitung an externe Domänen sollte nicht zugelassen oder überwacht werden.|Ja|Ja||
|Einheitliche Überwachung sollte aktiviert sein|Ja|Ja||
|[IMAP-Konnektivität mit Postfach](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Deaktiviert|Deaktiviert||
|[Pop-Konnektivität mit Postfach](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Deaktiviert|Deaktiviert||
|Authentifizierte SMTP-Übermittlung|Deaktiviert|Deaktiviert|Authentifizierte Client-SMTP-Übermittlung (auch bekannt als Client-SMTP-Übermittlung oder SMTP-Authentifizierung) ist für POP3-und IMAP4-Clients zum Senden von e-Mails erforderlich.|
|EWS-Konnektivität mit Postfach|Deaktiviert|Deaktiviert||
|[PowerShell-Konnektivität](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)|Deaktiviert|Deaktiviert|Verfügbar für Postfachbenutzer oder e-Mail-Benutzer (Benutzerobjekte, die vom Cmdlet [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user) zurückgegeben werden).|
|Verwenden von [Spoof Intelligence](learn-about-spoof-intelligence.md) zum Hinzufügen von Absendern zu ihrer Zulassungsliste|Ja|Ja||
|[Verzeichnisbasierte Edge-Blockierung (Blockierung)](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|Aktiviert|Aktiviert|Domain-Typ = autorisierend|
|[Einrichten der mehrstufigen Authentifizierung für alle Administratorkonten](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)|Aktiviert|Aktiviert||
|

## <a name="troubleshooting"></a>Problembehandlung

Behandeln allgemeiner Probleme und Trends mithilfe der Berichte im Admin Center. Mithilfe des Nachrichtenablaufverfolgungs-Tools können Sie nach einzelnen quellenspezifischen Daten zu einer Nachricht suchen. Weitere Informationen zu Berichten finden Sie unter [Berichterstellung und Nachrichtenablaufverfolgung in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Weitere Informationen zum Nachrichtenablauf verfolgungstool finden Sie unter [Message Trace im Security & Compliance Center](message-trace-scc.md).

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>Falsch positive und falsch negative Meldungen an Microsoft melden

Um die Spamfilterung im Dienst für alle zu verbessern, sollten Sie falsch positive Ergebnisse (gute e-Mail-Nachrichten als ungültig markiert) und falsch negative (ungültige e-Mail-Nachrichten) zur Analyse an Microsoft melden. Weitere Informationen finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="create-mail-flow-rules"></a>Erstellen von Nachrichtenflussregeln

Erstellen Sie Nachrichtenfluss Regeln (auch als Transportregeln bezeichnet) oder benutzerdefinierte Filter, um Ihre geschäftlichen Anforderungen zu erfüllen.

Wenn Sie eine neue Regel in die Produktion übernehmen, wählen Sie zunächst einen der Testmodi aus, um die Wirkung der Regeln zu überprüfen. Wenn Sie sicher sind, dass die Regel so funktioniert wie beabsichtigt, ändern Sie den Regelmodus in **Erzwingen**.

Beim Bereitstellen neuer Regeln sollten Sie in Erwägung ziehen, als zusätzliche Aktion **Schadensbericht generieren** hinzuzufügen, um die betreffende Regel zu überwachen.

In Hybrid Umgebungen, in denen Ihre Organisation sowohl lokale Exchange-als auch Exchange Online umfasst, sollten Sie die Bedingungen beachten, die Sie in Nachrichtenfluss Regeln verwenden. Wenn die Regeln auf die gesamte Organisation angewendet werden sollen, müssen Sie unbedingt Bedingungen verwenden, die sowohl in lokalen Exchange-als auch in Exchange Online verfügbar sind. Während die meisten Bedingungen in beiden Umgebungen zur Verfügung stehen, gibt es einige wenige, die nur in der einen oder anderen Umgebung verfügbar sind. Weitere Informationen finden Sie unter [Nachrichtenfluss Regeln (Transportregeln) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).
