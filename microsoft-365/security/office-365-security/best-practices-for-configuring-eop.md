---
title: Bewährte Methoden für die Konfiguration von EoP und Office 365 ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Beachten Sie die folgenden Empfehlungen für Exchange Online Protection (EOP), um allgemeine Konfigurationsfehler zu vermeiden und eine erfolgreiche Funktion zu gewährleisten.
ms.openlocfilehash: 053b5f551be528e7eedb3c218bb1e49ab6b8be91
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599742"
---
# <a name="best-practices-for-configuring-eop-and-office-365-atp"></a>Bewährte Methoden für die Konfiguration von EoP und Office 365 ATP

Beachten Sie die folgenden Empfehlungen für Exchange Online Protection (EOP), um allgemeine Konfigurationsfehler zu vermeiden und eine erfolgreiche Funktion zu gewährleisten. In diesem Thema wird vorausgesetzt, dass Sie den Setup-Prozess bereits abgeschlossen haben. Wenn Sie das EOP-Setup nicht abgeschlossen haben, finden Sie weitere Informationen unter [Einrichten Ihres EOP-Diensts](set-up-your-eop-service.md).

## <a name="use-a-test-domain"></a>Verwenden einer Testdomäne

Es wird empfohlen, eine Testdomäne, eine Unterdomäne oder eine Domäne von geringem Volumen zu verwenden, um Dienstfunktionen zu prüfen, bevor Sie sie auf Ihren Produktionsdomänen mit höherem Volumen implementieren.

## <a name="synchronize-recipients"></a>Synchronisieren von Empfängern

Wenn Ihre Organisation über vorhandene Benutzerkonten in einer lokalen Active Directory Umgebung verfügt, können Sie diese Konten mit Azure Active Directory in der Cloud synchronisieren. Es wird empfohlen, Verzeichnissynchronisierung zu verwenden. Weitere Informationen über die Vorteile der Verzeichnissynchronisierung und über die Schritte zu ihrer Einrichtung finden Sie unter [Verwalten von E-Mail-Benutzern in EOP](manage-mail-users-in-eop.md).

## <a name="recommended-settings"></a>Empfohlene Einstellungen

Wir ermächtigen Sicherheitsadministratoren, Ihre Sicherheitseinstellungen anzupassen, die die Anforderungen ihrer Umgebungen anspruchvollen Kunden befriedigt. Obwohl es sich in der Regel um zwei Sicherheitsstufen in EoP und Office 365 ATP handelt, empfehlen wir: Standard und Strict. Diese Einstellungen werden in den [empfohlenen Einstellungen für EoP und Office 365 ATP-Sicherheit](recommended-settings-for-eop-and-office365-atp.md)aufgeführt. 

### <a name="miscellaneousnon-policy-settings"></a>Verschiedene/nicht-Richtlinieneinstellungen

Diese Einstellungen umfassen eine Reihe von Features, die sich außerhalb von Sicherheitsrichtlinien befinden.

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

## <a name="troubleshooting"></a>Problembehandlung

Behandeln allgemeiner Probleme und Trends mithilfe der Berichte im Admin Center. Mithilfe des Nachrichtenablaufverfolgungs-Tools können Sie nach einzelnen quellenspezifischen Daten zu einer Nachricht suchen. Weitere Informationen zu Berichten finden Sie unter [Berichterstellung und Nachrichtenablaufverfolgung in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Weitere Informationen zum Nachrichtenablaufverfolgungs-Tool finden Sie unter [Trace an Email Message](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message).

## <a name="reporting-false-positive-and-false-negatives-to-microsoft"></a>Melden von falsch positiven und falschen negativen Ergebnissen an Microsoft

Administratoren sollten falsch negative (Spam) und falsch positive Ergebnisse (nicht-Spam) über unser admin-Übermittlungen-Portal an Microsoft übermitteln. E-Mails, Dateien und URLs können an Administratoren übermittelt werden, um zu ermitteln, warum Nachrichten an Endbenutzer übermittelt oder nicht bereitgestellt wurden. Ausführliche Informationen finden Sie unter [Vorgehensweise übermitteln von verdächtigen Spam, Phishing, URLs und Dateien an Microsoft für Office 365](admin-submission.md)-Überprüfung.

Endbenutzer können falsch negative (Spam) und falsch positive Ergebnisse (nicht-Spam) auch direkt an Microsoft zur Analyse melden, wenn Sie mit den gegebenen Urteilen nicht einverstanden sind. Ausführliche Informationen finden Sie unter [Submit Spam, Non-Spam, and Phishing Scam messages to Microsoft for Analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).


## <a name="create-mail-flow-rules"></a>Erstellen von Nachrichtenflussregeln

Erstellen von Nachrichtenfluss Regeln oder benutzerdefinierten Filtern, um Ihre geschäftlichen Anforderungen zu erfüllen.

Wenn Sie eine neue Regel in die Produktion übernehmen, wählen Sie zunächst einen der Testmodi aus, um die Wirkung der Regeln zu überprüfen. Wenn Sie sicher sind, dass die Regel so funktioniert wie beabsichtigt, ändern Sie den Regelmodus in **Erzwingen**.

Beim Bereitstellen neuer Regeln sollten Sie in Erwägung ziehen, als zusätzliche Aktion **Schadensbericht generieren** hinzuzufügen, um die betreffende Regel zu überwachen.

In Hybrid Umgebungen, in denen Ihre Organisation sowohl lokale Exchange-als auch Office 365 umfasst, sollten Sie die Bedingungen beachten, die Sie in Nachrichtenfluss Regeln verwenden. Wenn die Regeln auf die gesamte Organisation angewendet werden sollen, müssen Sie unbedingt Bedingungen verwenden, die sowohl in lokalen Exchange-als auch in Office 365 verfügbar sind. Während die meisten Bedingungen in beiden Umgebungen zur Verfügung stehen, gibt es einige wenige, die nur in der einen oder anderen Umgebung verfügbar sind. Weitere Informationen finden Sie unter [Nachrichtenfluss Regeln (Transportregeln) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).


