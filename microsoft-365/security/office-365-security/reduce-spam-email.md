---
title: Reduzieren von Spam-E-Mails in Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 06/07/2018
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: 07824c51-2c45-4005-8596-03c0d7c4ff2a
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_IP
description: Erfahren Sie mehr über die am häufigsten verwendeten Verfahren zur Reduzierung von Spam und Junk-E-Mails in Office 365.
ms.openlocfilehash: d99b5e1452c60be713f0f4cfbab965d30eeeb8ef
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082397"
---
# <a name="how-to-reduce-spam-email-in-office-365"></a>Reduzieren von Spam-E-Mails in Office 365

 **Erhalten Sie zu viel Spam in Office 365? Hier ist die Lösung.**
  
Es wird dringend empfohlen, uns über falsch negative Nachrichten [mit dem Add-In "Nachricht melden"](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) zu informieren, damit wir unsere Filter verbessern können. Zusätzlich können Sie die Nachricht über den [Übermittlungen-Explorer](admin-submission.md) übermitteln.

> [!TIP]
> Wenn Sie davon ausgehen, dass es sich bei der Nachricht um eine Junk-E-Mail handelt, und diese sich im Junk-E-Mail-Ordner befindet, sollte dies kein Problem darstellen. Soll die Nachricht in gar keinem Postfach angezeigt werden, müssen Sie die Antispamrichtlinie so ändern, dass die Nachricht unter Quarantäne gestellt wird. Weitere Informationen zur Quarantäne für eine Nachricht finden Sie im Artikel [Unter Quarantäne stellen von E-Mail-Nachrichten in Office 365](quarantine-email-messages.md).

## <a name="fixing-allowed-spam"></a>Korrigieren zulässiger Spam

Wir stellen häufig fest, dass Kunden aufgrund falscher Konfigurationen Junk-E-Mails in ihrem Posteingang erhalten. Die häufigste Ursache ist das Konfigurieren von Domänen in einer E-Mail-Flussregel (auch als Transportregel bezeichnet) zum Umgehen von Filtern oder Auflisten der Domäne(n) in der Liste der zulässigen/sicheren Absender. Dies ist keine gute Vorgehensweise, da diese Nachrichten die Spamfilterung überspringen, obwohl sie andernfalls hätten abgefangen werden können.  

## <a name="solutions-to-other-common-causes-of-getting-too-much-spam"></a>Lösungen für andere häufige Ursachen von zu viel Spam

Um Sie vor zu viel Spam zu schützen, müssen Administratoren in Exchange Online Protection (EOP) ein paar Aufgaben ausführen. Wenn Sie nicht der Administrator für Ihren Office 365-Mandanten sind und zu viel Spam erhalten, sollten Sie diese Aufgaben zusammen mit Ihrem Administrator ausführen. Andernfalls können Sie mit dem Abschnitt für Benutzer fortfahren.
  
### <a name="for-admins"></a>Für Administratoren

- **Ihre DNS-Einträge auf Office 365 zeigen lassen** Damit EOP Schutz bietet, müssen Ihre MX-Einträge (Mail Exchange) ausschließlich auf Office 365 verweisen. Lesen Sie die Informationen unter [Erstellen von DNS-Einträgen für Office 365 beim Verwalten von DNS-Einträgen.](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23)
    
- **Die Junk-E-Mail-Regel für alle Postfächer aktivieren** Standardmäßig ist die Aktion des Spamfilters auf **Nachricht in den Junk-E-Mail-Ordner verschieben** festgelegt. Wenn dies die bevorzugte und aktuelle Spamrichtlinienaktion ist, so muss für jedes Postfach [auch die Junk-E-Mail-Regel aktiviert sein](https://support.office.com/de-DE/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). Um dies zu überprüfen, können Sie das Cmdlet „Get-MailboxJunkEmailConfiguration“ für ein oder mehrere Postfächer ausführen. Sie können z. B. alle Postfächer überprüfen, indem Sie Folgendes ausführen: Get-MailboxJunkEmailConfiguration -Identity \* | Where {$_.Enabled -eq $false}
    
    Wenn Sie die Ausgabe anzeigen, sollte die Enable-Eigenschaft auf "True" festgelegt sein. Wenn sie auf "False" festgelegt ist, können Sie "Set-MailboxJunkEmailConfiguration" ausführen, um dies wie folgt in "True" zu ändern: Set-MailboxJunkEmailConfiguration -Identity $values.UserPrincipalName -Enabled $true.
    
- **Nachrichtenflussregeln auf dem lokalen Exchange Server erstellen** Wenn Sie Exchange Online Protection verwenden, Ihre Postfächer sich aber auf dem lokalen Exchange Server befinden, müssen Sie ein paar Nachrichtenflussregeln auf dem lokalen Exchange Server erstellen. Lesen Sie [Anweisungen für EOP](https://docs.microsoft.com/previous-versions/exchange-server/exchange-150/jj900470(v=exchg.150)).
    
- **Massen-E-Mails als Spam kennzeichnen** Bei Massen-E-Mails handelt es sich um E-Mails, für die sich Benutzer vielleicht registriert haben, die aber dennoch unerwünscht sind. Suchen Sie im Nachrichtenkopf die BCL-Eigenschaft (Bulk Complaint Level) in der Kopfzeile „X-Microsoft-Antispam“. Wenn der BCL-Wert niedriger als der im Spamfilter festgelegte Wert ist, können Sie den Schwellenwert so anpassen, dass stattdessen diese Typen von Massen-E-Mails als Spam markiert werden. Unterschiedliche Benutzer haben unterschiedliche Toleranzen und Vorlieben dafür, [wie Massen-E-Mails behandelt werden](https://docs.microsoft.com/de-DE/office365/SecurityCompliance/bulk-complaint-level-values). Sie können unterschiedliche Richtlinien oder Regel für die unterschiedlichen Wünsche der Benutzer erstellen. 
    
- **Einen Absender sofort blockieren** Wenn Sie einen Absender sofort blockieren müssen, können Sie anhand der E-Mail-Adresse, der Domäne oder der IP-Adresse blockieren. Lesen Sie die Informationen unter [Erstellen von Listen der blockierten Absender in Office 365](create-block-sender-lists-in-office-365.md). Ein Eintrag in einer Liste zulässiger Absender eines Benutzers kann eine vom Administrator festgelegte Sperre überschreiben.
    
- **Aktivieren des Add-Ins "Nachricht melden" für Benutzer** Es wird dringend empfohlen, dass Sie das [Add-In "Nachricht melden" für Ihre Benutzer aktivieren](enable-the-report-message-add-in.md).

- **Verwenden Sie [Übermittlungen-Explorer](admin-submission.md)** -Administratoren können jetzt E-Mails mithilfe von Datei-oder Netzwerknachrichten-ID,-URLs und-Dateien zum Scannen durch Microsoft in Office 365 senden. Als Administrator können Sie ggf. auch das Feedback anzeigen, das Ihre Benutzer senden, und beliebige Muster verwenden, um alle Einstellungen anzupassen, die möglicherweise Probleme verursachen.

- **Aktivieren der [DKIM](use-dkim-to-validate-outbound-email.md)**, um alle ausgehenden Nachrichten zu signieren, damit die Sicherheit in Ihrer Domäne und in Ihrem Mandanten gesteigert wird.
 > [!TIP]
> Nachdem Sie DKIM aktiviert haben, müssen Sie [DMARC](use-dkim-to-validate-outbound-email.md) aktivieren, da dieser Eintrag überprüft, ob DKIM und SPF korrekt arbeiten. Spoofing-E-Mails weisen die Signatur im Allgemeinen nicht auf, da O365 Ihren privaten und öffentlichen symmetrischen Schlüssel verwaltet.
    
### <a name="for-users"></a>Für Benutzer

- **Die Junk-E-Mail-Regel aktivieren und die Zulassungsliste überprüfen** Überprüfen Sie, ob die Regel für die Junk-E-Mail-Aktion aktiviert wurde und dass der Absender oder die Domäne des Absenders in Ihrer persönlichen Liste zulässiger Adressen nicht übergangen wird. Die beste Möglichkeit, um auf diese Einstellungen zuzugreifen, ist über [Blockieren oder Zulassen (Junk-E-Mail-Einstellungen)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46). An dieser Stelle können Sie auch festlegen, dass die E-Mail-Adresse oder Domäne des Absenders blockiert werden soll.
    
- **Melden von Spam an Microsoft** Melden Sie Spamnachrichten [mit dem Add-In "Nachricht melden"](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) an Microsoft.
       
- **Abonnement von Massen-E-Mails kündigen** Wenn Sie sich für die Nachricht registriert haben (Newsletter, Produktankündigungen usw.) und diese einen Link zum Kündigen des Abonnements von einer vertrauenswürdigen Quelle enthält, können Sie das Abonnement einfach kündigen. In Office 365 werden diese Nachrichten in der Regel nicht als Spam behandelt. Sie können auch den Absender blockieren oder Ihren Administrator bitten, eine Änderung vorzunehmen, die bewirkt, dass alle Massen-E-Mails als Spam behandelt werden.
