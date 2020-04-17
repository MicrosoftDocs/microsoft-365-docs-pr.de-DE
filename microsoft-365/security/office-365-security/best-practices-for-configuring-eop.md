---
title: Bewährte Methoden für die Konfiguration von EoP und Office 365 ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Beachten Sie die folgenden Empfehlungen für Exchange Online Protection (EOP), um allgemeine Konfigurationsfehler zu vermeiden und eine erfolgreiche Funktion zu gewährleisten.
ms.openlocfilehash: 9bddb736d41b4fd56790b8bbe9dbb00d07e75553
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "43528617"
---
# <a name="best-practices-for-configuring-eop-and-office-365-atp"></a>Bewährte Methoden für die Konfiguration von EoP und Office 365 ATP

Beachten Sie die folgenden Empfehlungen für Exchange Online Protection (EOP), um allgemeine Konfigurationsfehler zu vermeiden und eine erfolgreiche Funktion zu gewährleisten. In diesem Thema wird vorausgesetzt, dass Sie den Setup-Prozess bereits abgeschlossen haben. Wenn Sie das EOP-Setup nicht abgeschlossen haben, finden Sie weitere Informationen unter [Einrichten Ihres EOP-Diensts](set-up-your-eop-service.md).

## <a name="use-a-test-domain"></a>Verwenden einer Testdomäne

Es wird empfohlen, eine Testdomäne, eine Unterdomäne oder eine Domäne von geringem Volumen zu verwenden, um Dienstfunktionen zu prüfen, bevor Sie sie auf Ihren Produktionsdomänen mit höherem Volumen implementieren.

## <a name="synchronize-recipients"></a>Synchronisieren von Empfängern

Wenn Ihre Organisation über vorhandene Benutzerkonten in einer lokalen Active Directory Umgebung verfügt, können Sie diese Konten mit Azure Active Directory in der Cloud synchronisieren. Es wird empfohlen, Verzeichnissynchronisierung zu verwenden. Weitere Informationen über die Vorteile der Verzeichnissynchronisierung und über die Schritte zu ihrer Einrichtung finden Sie unter [Verwalten von E-Mail-Benutzern in EOP](manage-mail-users-in-eop.md).

## <a name="recommended-settings"></a>Empfohlene Einstellungen

Wir ermächtigen Sicherheitsadministratoren, Ihre Sicherheitseinstellungen anzupassen, um die Anforderungen Ihrer Organisation zu erfüllen. Obwohl es sich in der Regel um zwei Sicherheitsstufen in EoP und Office 365 ATP handelt, empfehlen wir: Standard und Strict. Diese Einstellungen werden in den [empfohlenen Einstellungen für EoP und Office 365 ATP-Sicherheit](recommended-settings-for-eop-and-office365-atp.md)aufgeführt.

### <a name="miscellaneousnon-policy-settings"></a>Verschiedene/nicht-Richtlinieneinstellungen

Diese Einstellungen umfassen eine Reihe von Features, die sich außerhalb von Sicherheitsrichtlinien befinden.

|Name des Sicherheitsfeatures|Standard|Strict|Kommentar|
|---------|---------|---------|---------|
|[Einrichten von SPF in Office 365 zum Verhindern von Spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Ja|Ja||
|[Verwenden von DKIM zum Überprüfen ausgehender E-Mails, die von Ihrer benutzerdefinierten Domäne in Office 365 gesendet werden](use-dkim-to-validate-outbound-email.md)|Ja|Ja||
|[Verwenden von DMARC zum Validieren von E-Mails in Office 365](use-dmarc-to-validate-email.md)|Ja|Ja|Use Action = Quarantine for Standard und Action = Reject for Strict.|
|Bereitstellen des Berichtsnachrichten-Add-ons zur Verbesserung der Berichterstellung für verdächtige e-Mails durch Endbenutzer|Ja|Ja||
|Planen von Malware-und Spam Berichten|Ja|Ja||
|Die automatische Weiterleitung an externe Domänen sollte nicht zugelassen oder überwacht werden.|Ja|Ja||
|Einheitliche Überwachung sollte aktiviert sein|Ja|Ja||
|[IMAP-Konnektivität mit Postfach](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Deaktiviert|Deaktiviert||
|[Pop-Konnektivität mit Postfach](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Deaktiviert|Deaktiviert||
|SMTP-authentifizierte Übermittlung an Postfach|Deaktiviert|Deaktiviert||
|EWS-Konnektivität mit Postfach|Deaktiviert|Deaktiviert||
|[PowerShell-Konnektivität](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)|Deaktiviert|Deaktiviert|Verfügbar für Postfachbenutzer oder e-Mail-Benutzer (Benutzerobjekte, die vom Cmdlet [Get-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user) zurückgegeben werden).|
|Verwenden von [Spoofing Intelligence](learn-about-spoof-intelligence.md) zum Whitelisting von Absendern, wann immer möglich|Ja|Ja||
|Verzeichnisbasierte Edge-Blockierung (Blockierung)|Aktiviert|Aktiviert|Domain-Typ = autorisierend|
|[Einrichten der mehrstufigen Authentifizierung für alle Administratorkonten](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)|Aktiviert|Aktiviert||

## <a name="troubleshooting"></a>Problembehandlung

Behandeln allgemeiner Probleme und Trends mithilfe der Berichte im Admin Center. Mithilfe des Nachrichtenablaufverfolgungs-Tools können Sie nach einzelnen quellenspezifischen Daten zu einer Nachricht suchen. Weitere Informationen zu Berichten finden Sie unter [Berichterstellung und Nachrichtenablaufverfolgung in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Weitere Informationen zum Nachrichtenablauf verfolgungstool finden Sie unter [Message Trace im Security & Compliance Center](message-trace-scc.md).

## <a name="report-false-positive-and-false-negatives-to-microsoft"></a>Falsch positive und falsch negative Ergebnisse an Microsoft melden

Um die Spamfilterung im Dienst für alle zu verbessern, sollten Sie falsch positive Ergebnisse (gute e-Mail-Nachrichten als ungültig markiert) und falsch negative (ungültige e-Mail-Nachrichten) zur Analyse an Microsoft melden. Weitere Informationen finden Sie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="create-mail-flow-rules"></a>Erstellen von Nachrichtenflussregeln

Erstellen von Nachrichtenfluss Regeln oder benutzerdefinierten Filtern, um Ihre geschäftlichen Anforderungen zu erfüllen.

Wenn Sie eine neue Regel in die Produktion übernehmen, wählen Sie zunächst einen der Testmodi aus, um die Wirkung der Regeln zu überprüfen. Wenn Sie sicher sind, dass die Regel so funktioniert wie beabsichtigt, ändern Sie den Regelmodus in **Erzwingen**.

Beim Bereitstellen neuer Regeln sollten Sie in Erwägung ziehen, als zusätzliche Aktion **Schadensbericht generieren** hinzuzufügen, um die betreffende Regel zu überwachen.

In Hybrid Umgebungen, in denen Ihre Organisation sowohl lokale Exchange-als auch Office 365 umfasst, sollten Sie die Bedingungen beachten, die Sie in Nachrichtenfluss Regeln verwenden. Wenn die Regeln auf die gesamte Organisation angewendet werden sollen, müssen Sie unbedingt Bedingungen verwenden, die sowohl in lokalen Exchange-als auch in Office 365 verfügbar sind. Während die meisten Bedingungen in beiden Umgebungen zur Verfügung stehen, gibt es einige wenige, die nur in der einen oder anderen Umgebung verfügbar sind. Weitere Informationen finden Sie unter [Nachrichtenfluss Regeln (Transportregeln) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).
