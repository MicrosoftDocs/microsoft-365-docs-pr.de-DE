---
title: Bewährte Methoden für das Konfigurieren von EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Befolgen Sie diese bewährten Empfehlungen für eigenständige Exchange Online Protection (EOP), um sich für den Erfolg zu konfigurieren und häufige Konfigurationsfehler zu vermeiden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 94586d409d6d8b53ba68c22b6b4f62d2b72266db
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599475"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>Bewährte Methoden zum Konfigurieren eigenständiger EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
-  [Exchange Online Protection eigenständig](exchange-online-protection-overview.md)

Befolgen Sie diese bewährten Empfehlungen für eigenständige Exchange Online Protection (EOP), um sich für den Erfolg zu konfigurieren und häufige Konfigurationsfehler zu vermeiden. In diesem Thema wird vorausgesetzt, dass Sie den Setup-Prozess bereits abgeschlossen haben. Wenn Sie das EOP-Setup nicht abgeschlossen haben, finden Sie weitere Informationen unter [Einrichten Ihres EOP-Diensts](set-up-your-eop-service.md).

## <a name="use-a-test-domain"></a>Verwenden einer Testdomäne

Es wird empfohlen, eine Testdomäne, eine Unterdomäne oder eine Domäne von geringem Volumen zu verwenden, um Dienstfunktionen zu prüfen, bevor Sie sie auf Ihren Produktionsdomänen mit höherem Volumen implementieren.

## <a name="synchronize-recipients"></a>Synchronisieren von Empfängern

Wenn Ihre Organisation über vorhandene Benutzerkonten in einer lokalen Active Directory-Umgebung verfügt, können Sie diese Konten mit Azure Active Directory in der Cloud synchronisieren. Es wird empfohlen, Verzeichnissynchronisierung zu verwenden. Weitere Informationen über die Vorteile der Verzeichnissynchronisierung und über die Schritte zu ihrer Einrichtung finden Sie unter [Verwalten von E-Mail-Benutzern in EOP](manage-mail-users-in-eop.md).

## <a name="recommended-settings"></a>Empfohlene Einstellungen

Wir ermöglichen Sicherheitsadministratoren, ihre Sicherheitseinstellungen an die Anforderungen ihrer Organisation anzupassen. Obwohl es in der Regel zwei Sicherheitsstufen in EOP und Microsoft Defender für Office 365 gibt: Standard und Strict. Diese Einstellungen sind in den Empfohlenen [Einstellungen für EOP und Microsoft Defender für Office 365 aufgeführt.](recommended-settings-for-eop-and-office365.md)

### <a name="miscellaneousnon-policy-settings"></a>Verschiedene/nicht richtlinienfreie Einstellungen

Diese Einstellungen umfassen eine Reihe von Features, die außerhalb von Sicherheitsrichtlinien liegen.

<br>

****

|Name des Sicherheitsfeatures|Standard|Strict|Kommentar|
|---|---|---|---|
|[Einrichten von SPF zum Verhindern von Spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Ja|Ja||
|[Verwenden von DKIM zum Überprüfen ausgehender E-Mails, die von Ihrer benutzerdefinierten Domäne in Office 365 gesendet werden](use-dkim-to-validate-outbound-email.md)|Ja|Ja||
|[Verwenden von DMARC zum Validieren von E-Mails in Office 365](use-dmarc-to-validate-email.md)|Ja|Ja|Verwenden `action=quarantine` Sie für Standard und `action=reject` Strict.|
|Bereitstellen des [Berichtsnachrichten-Add-Ins](enable-the-report-message-add-in.md) oder [des Phishing-Add-Ins](enable-the-report-phish-add-in.md) zum Melden von Phishing, um die Endbenutzerberichterstellung für verdächtige E-Mails zu verbessern|Ja|Ja||
|Planen von Schadsoftware- und Spamberichten|Ja|Ja||
|Automatische Weiterleitung an externe Domänen sollte nicht zulässig oder überwacht werden|Ja|Ja||
|Einheitliche Überwachung sollte aktiviert sein|Ja|Ja||
|[IMAP-Konnektivität mit Postfach](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Deaktiviert|Deaktiviert||
|[POP-Konnektivität mit Postfach](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Deaktiviert|Deaktiviert||
|Authentifizierte SMTP-Übermittlung|Deaktiviert|Deaktiviert|Die authentifizierte Client-SMTP-Übermittlung (auch als Client-SMTP-Übermittlung oder SMTP-Authentifizierung bezeichnet) ist für POP3- und IMAP4-Clients und -Anwendungen und -Geräte erforderlich, die E-Mails generieren und senden. <p> Anweisungen zum aktivieren und Deaktivieren von SMTP AUTH global oder selektiv finden Sie unter Aktivieren oder Deaktivieren der authentifizierten [Client-SMTP-Übermittlung in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission).|
|EWS-Konnektivität mit Postfach|Deaktiviert|Deaktiviert|Outlook verwendet Exchange Webdienste für Frei/Gebucht-, Out-of-Office-Einstellungen und Kalenderfreigabe. Wenn Sie EWS nicht global deaktivieren können, haben Sie die folgenden Optionen: <ul><li>Verwenden [Sie Authentifizierungsrichtlinien,](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) um zu verhindern, dass EWS die Standardauthentifizierung verwendet, wenn Ihre Clients moderne Authentifizierung (moderne Authentifizierung) unterstützen.</li><li>Verwenden [Sie Clientzugriffsregeln,](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) um EWS auf bestimmte Benutzer oder Quell-IP-Adressen zu beschränken.</li><li>Steuern des EWS-Zugriffs auf bestimmte Anwendungen global oder pro Benutzer. Anweisungen finden Sie unter [Steuern des Zugriffs auf EWS in Exchange](/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange).</li></ul> <p> Das [Berichtsnachrichten-Add-In](enable-the-report-message-add-in.md) und das [Phishing-Add-In](enable-the-report-phish-add-in.md) Melden verwendet rest standardmäßig in unterstützten Umgebungen, wird jedoch auf EWS zurückfallen, wenn REST nicht verfügbar ist. Die unterstützten Umgebungen, die REST verwenden, sind:<ul><li>Exchange Online</li><li>Exchange 2019 oder Exchange 2016</li><li>Aktuelle Outlook für Windows 2019 Microsoft 365 abonnement oder one-time purchase Outlook 2019.</li><li>Aktuelle Outlook für Mac aus einem Microsoft 365 Abonnement oder einem Einmalkauf Outlook für Mac 2016 oder höher.</li><li>Outlook für iOS und Android</li><li>Outlook im Web</li></ul>|
|[PowerShell-Konnektivität](/powershell/exchange/disable-access-to-exchange-online-powershell)|Deaktiviert|Deaktiviert|Verfügbar für Postfachbenutzer oder E-Mail-Benutzer (vom [Cmdlet Get-User zurückgegebene](/powershell/module/exchange/get-user) Benutzerobjekte).|
|Verwenden [von Spoof Intelligence](learn-about-spoof-intelligence.md) zum Hinzufügen von Absendern zur Liste der zulässigen Nachrichten|Ja|Ja||
|[Verzeichnisbasierte Edgeblockierung (Directory-Based Edge Blocking, DBEB)](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|Aktiviert|Aktiviert|Domänentyp = Autoritative|
|[Einrichten der mehrstufigen Authentifizierung für alle Administratorkonten](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)|Aktiviert|Aktiviert||
|

## <a name="troubleshooting"></a>Problembehandlung

Behandeln Sie allgemeine Probleme und Trends mithilfe der Berichte im Admin Center. Mithilfe des Nachrichtenablaufverfolgungs-Tools können Sie nach einzelnen quellenspezifischen Daten zu einer Nachricht suchen. Weitere Informationen zu Berichten finden Sie unter [Berichterstellung und Nachrichtenablaufverfolgung in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Weitere Informationen zum Tool zur Nachrichtenverfolgung finden Sie unter [Nachrichtenverfolgung im Security & Compliance Center](message-trace-scc.md).

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>Melden falsch positiver und falsch negativer Ergebnisse an Microsoft

Um die Spamfilterung im Dienst für alle zu verbessern, sollten Sie falsch positive Ergebnisse (gute E-Mails als ungültig gekennzeichnet) und falsch negative (ungültige E-Mails zulässig) zur Analyse an Microsoft melden. Weitere Informationen finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="create-mail-flow-rules"></a>Erstellen von Nachrichtenflussregeln

Erstellen Sie Nachrichtenflussregeln (auch als Transportregeln bezeichnet) oder benutzerdefinierte Filter, um Ihre Geschäftlichen Anforderungen zu erfüllen.

Wenn Sie eine neue Regel in die Produktion übernehmen, wählen Sie zunächst einen der Testmodi aus, um die Wirkung der Regeln zu überprüfen. Wenn Sie sicher sind, dass die Regel so funktioniert wie beabsichtigt, ändern Sie den Regelmodus in **Erzwingen**.

Beim Bereitstellen neuer Regeln sollten Sie in Erwägung ziehen, als zusätzliche Aktion **Schadensbericht generieren** hinzuzufügen, um die betreffende Regel zu überwachen.

Berücksichtigen Sie in Hybridumgebungen, in denen Ihre Organisation sowohl lokale Exchange als auch Exchange Online, die Bedingungen, die Sie in Nachrichtenflussregeln verwenden. Wenn die Regeln für die gesamte Organisation gelten sollen, müssen Sie unbedingt Bedingungen verwenden, die sowohl in lokalen als auch in lokalen Exchange und in Exchange Online. Während die meisten Bedingungen in beiden Umgebungen verfügbar sind, gibt es einige, die nur in der einen oder anderen Umgebung verfügbar sind. Weitere Informationen finden Sie [unter Nachrichtenflussregeln (Transportregeln) in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).