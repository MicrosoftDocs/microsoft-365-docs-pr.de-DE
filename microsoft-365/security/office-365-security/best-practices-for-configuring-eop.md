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
description: Befolgen Sie diese bewährten Empfehlungen für eigenständigen Exchange Online Protection (EOP), um sich für den Erfolg zu konfigurieren und häufige Konfigurationsfehler zu vermeiden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c64a9592d93ef046ad1c023a49bf378ccf6cf503
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290833"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>Bewährte Methoden für die Konfiguration von EOP als eigenständige Lösung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
-  [Exchange Online Protection als eigenständige Lösung](exchange-online-protection-overview.md)

Befolgen Sie diese bewährten Empfehlungen für eigenständigen Exchange Online Protection (EOP), um sich für den Erfolg zu konfigurieren und häufige Konfigurationsfehler zu vermeiden. In diesem Thema wird vorausgesetzt, dass Sie den Setup-Prozess bereits abgeschlossen haben. Wenn Sie das EOP-Setup nicht abgeschlossen haben, finden Sie weitere Informationen unter [Einrichten Ihres EOP-Diensts](set-up-your-eop-service.md).

## <a name="use-a-test-domain"></a>Verwenden einer Testdomäne

Es wird empfohlen, eine Testdomäne, eine Unterdomäne oder eine Domäne von geringem Volumen zu verwenden, um Dienstfunktionen zu prüfen, bevor Sie sie auf Ihren Produktionsdomänen mit höherem Volumen implementieren.

## <a name="synchronize-recipients"></a>Synchronisieren von Empfängern

Wenn Ihre Organisation über vorhandene Benutzerkonten in einer lokalen Active Directory-Umgebung verfügt, können Sie diese Konten mit Azure Active Directory in der Cloud synchronisieren. Es wird empfohlen, Verzeichnissynchronisierung zu verwenden. Weitere Informationen über die Vorteile der Verzeichnissynchronisierung und über die Schritte zu ihrer Einrichtung finden Sie unter [Verwalten von E-Mail-Benutzern in EOP](manage-mail-users-in-eop.md).

## <a name="recommended-settings"></a>Empfohlene Einstellungen

Wir befähigen Sicherheitsadministratoren, ihre Sicherheitseinstellungen an die Anforderungen ihrer Organisation anzupassen. Obwohl es in der Regel zwei Sicherheitsebenen in EOP und Microsoft Defender für Office 365 gibt, die empfohlen werden: Standard und Streng. Diese Einstellungen sind in den empfohlenen Einstellungen für [EOP und Microsoft Defender für Office 365-Sicherheit aufgeführt.](recommended-settings-for-eop-and-office365-atp.md)

### <a name="miscellaneousnon-policy-settings"></a>Verschiedene/Nicht-Richtlinien-Einstellungen

Diese Einstellungen umfassen eine Reihe von Features, die sich außerhalb von Sicherheitsrichtlinien befinden.

****

|Name des Sicherheitsfeatures|Standard|Streng|Kommentar|
|---|---|---|---|
|[Einrichten von SPF zum Verhindern von Spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Ja|Ja||
|[Verwenden von DKIM zum Überprüfen ausgehender E-Mails, die von Ihrer benutzerdefinierten Domäne in Office 365 gesendet werden](use-dkim-to-validate-outbound-email.md)|Ja|Ja||
|[Verwenden von DMARC zum Validieren von E-Mails in Office 365](use-dmarc-to-validate-email.md)|Ja|Ja|Wird `action=quarantine` für "Standard" und `action=reject` "Strict" verwendet.|
|Bereitstellen des [Berichtsnachrichten-Add-Ins](enable-the-report-message-add-in.md) oder [des Phishing-Add-Ins](enable-the-report-phish-add-in.md) "Melden" zur Verbesserung der Endbenutzerberichterstattung über verdächtige E-Mails|Ja|Ja||
|Planen von Schadsoftware- und Spamberichten|Ja|Ja||
|Die automatische Weiterleitung an externe Domänen sollte nicht zugelassen oder überwacht werden|Ja|Ja||
|Einheitliche Überwachung sollte aktiviert sein|Ja|Ja||
|[IMAP-Konnektivität mit Postfach](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Deaktiviert|Deaktiviert||
|[POP-Konnektivität mit Postfach](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Deaktiviert|Deaktiviert||
|Authentifizierte SMTP-Übermittlung|Deaktiviert|Deaktiviert|Authentifizierte Client-SMTP-Übermittlung (auch bekannt als Client-SMTP-Übermittlung oder SMTP-Authentifizierung) ist erforderlich, damit POP3- und IMAP4-Clients E-Mails senden können.|
|EWS-Konnektivität mit Postfach|Deaktiviert|Deaktiviert||
|[PowerShell-Konnektivität](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)|Deaktiviert|Deaktiviert|Verfügbar für Postfachbenutzer oder E-Mail-Benutzer (vom [Cmdlet "Get-User" zurückgegebene](https://docs.microsoft.com/powershell/module/exchange/get-user) Benutzerobjekte).|
|Verwenden [von Spoofintelligenz](learn-about-spoof-intelligence.md) zum Hinzufügen von Absendern zu Ihrer Liste zulässiger Absender|Ja|Ja||
|[Verzeichnisbasierte Edgeblockierung (Directory-Based Edge Blocking, DBEB)](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|Aktiviert|Aktiviert|Domänentyp = Autoritativ|
|[Einrichten der mehrstufigen Authentifizierung für alle Administratorkonten](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)|Aktiviert|Aktiviert||
|

## <a name="troubleshooting"></a>Problembehandlung

Behandeln Sie allgemeine Probleme und Trends mithilfe der Berichte im Admin Center. Mithilfe des Nachrichtenablaufverfolgungs-Tools können Sie nach einzelnen quellenspezifischen Daten zu einer Nachricht suchen. Weitere Informationen zu Berichten finden Sie unter [Berichterstellung und Nachrichtenablaufverfolgung in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Weitere Informationen zum Tool für die Nachrichtenverfolgung finden Sie im [Security & Compliance Center.](message-trace-scc.md)

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>Melden falsch positiver ergebnisse und falsch negativer Ergebnisse an Microsoft

Um die Spamfilterung im Dienst für alle zu verbessern, sollten Sie falsch positive Ergebnisse (gute E-Mails als schlecht gekennzeichnet) und falsch negative Ergebnisse (ungültige E-Mails sind zulässig) zur Analyse an Microsoft melden. Weitere Informationen finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="create-mail-flow-rules"></a>Erstellen von Nachrichtenflussregeln

Erstellen Sie Nachrichtenflussregeln (auch als Transportregeln bezeichnet) oder benutzerdefinierte Filter, um Ihre Geschäftsanforderungen zu erfüllen.

Wenn Sie eine neue Regel in die Produktion übernehmen, wählen Sie zunächst einen der Testmodi aus, um die Wirkung der Regeln zu überprüfen. Wenn Sie sicher sind, dass die Regel so funktioniert wie beabsichtigt, ändern Sie den Regelmodus in **Erzwingen**.

Beim Bereitstellen neuer Regeln sollten Sie in Erwägung ziehen, als zusätzliche Aktion **Schadensbericht generieren** hinzuzufügen, um die betreffende Regel zu überwachen.

Berücksichtigen Sie in Hybridumgebungen, in denen Ihre Organisation sowohl lokales Exchange als auch Exchange Online umfasst, die Bedingungen, die Sie in Nachrichtenflussregeln verwenden. Wenn die Regeln auf die gesamte Organisation angewendet werden sollen, müssen Sie bedingungen verwenden, die sowohl im lokalen Exchange als auch in Exchange Online verfügbar sind. Während die meisten Bedingungen in beiden Umgebungen verfügbar sind, gibt es einige, die nur in der einen oder der anderen Umgebung verfügbar sind. Weitere Informationen finden Sie [unter Nachrichtenflussregeln (Transportregeln) in Exchange Online.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
