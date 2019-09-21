---
title: Vermeiden falsch positiver Ergebnisse in Office 365
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/7/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Erfahren Sie, wie Sie falsch positive Ergebnisse verhindern und echte E-Mail-Nachrichten davor schützen, im Junk-E-Mail-Ordner von Office 365 zu landen.
ms.openlocfilehash: 18b360f4cb3900aad3a6dbf7cc0a098750099f01
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082145"
---
# <a name="how-to-prevent-real-email-from-being-marked-as-spam-in-office-365"></a>Verhindern, dass echte E-Mails in Office 365 als Spam gekennzeichnet werden

 **Werden echte E-Mails in Office 365 als Spam gekennzeichnet? Hier kommt die Lösung.**
  
Wenn Sie ein falsch positives Ergebnis erhalten, sollten Sie die Nachricht an Microsoft melden. [Verwenden Sie dazu das Add-In "Nachricht melden"](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2). Zusätzlich können Sie die Nachricht mittels[ Übermittlungen-Explorer](/security/office-365-security/admin-submission.md) übermitteln.
    
## <a name="determine-the-reason-why-the-message-was-marked-as-spam"></a>Ermitteln der Ursache, warum die Nachricht als Spam gekennzeichnet wurde

Viele Probleme bezüglich Spam in Office 365 können gelöst werden, indem Sie die [Kopfzeilen von E-Mail-Nachrichten anzeigen](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c) und bestimmen, wo der Fehler liegt. Sie müssen nach einer Kopfzeile mit dem Namen X-Forefront-Antispam-Report suchen. Weitere Informationen zu Antispam-Nachrichtenkopfzeilen finden Sie [hier](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx).
  
Suchen Sie in der Kopfzeile nach den folgenden Überschriften und Werten.
  
### <a name="x-forefront-antispam-report"></a>X-Forefront-Antispam-Report

- **SFV:SPM** Gibt an, dass die Nachricht aufgrund der EOP-Spamfilter als Spam markiert wurde. 

- **SFV:BLK** Gibt an, dass die Nachricht als Spam gekennzeichnet wurde, da sich die Absenderadresse auf der Liste blockierter Absender befindet. 
    
- **SFV:SKS**Gibt an, dass die Nachricht vor dem Inhaltsfilter als Spam markiert wurde. Dies könnte eine E-Mail-Flussregel (auch als Transportregel bezeichnet) umfassen, durch die die Nachricht als Spam gekennzeichnet wird. Führen Sie eine Nachrichtenablaufverfolgung aus, um festzustellen, ob eine E-Mail-Flussregel ausgelöst wurde, die eine hohe SCL-Bewertung (Spam Confidence Level, SCL) festgelegt hat. 
    
- **SFV:SKB** Gibt an, dass die Nachricht als Spam markiert, da sie einer Sperrliste in der Richtlinie für den Spamfilter entsprach. 
    
- **SFV:BULK** Gibt an, dass der BCL-Wert (Bulk Complaint Level) in der Kopfzeile x-microsoft-antispam über dem Schwellenwert für Massen-E-Mails liegt, der für den Inhaltsfilter festgelegt wurde. Bei Massen-E-Mails handelt es sich um E-Mails, für die sich Benutzer vielleicht registriert haben, die aber dennoch unerwünscht sind. Suchen Sie im Nachrichtenkopf die BCL-Eigenschaft (Bulk Complaint Level) in der Kopfzeile „X-Microsoft-Antispam“. Wenn der BCL-Wert niedriger als der im Spamfilter festgelegte Wert ist, können Sie den Schwellenwert so anpassen, dass stattdessen diese Typen von Massen-E-Mails als Spam markiert werden. Unterschiedliche Benutzer haben unterschiedliche Toleranzen und Vorlieben dafür, wie [Massen-E-Mails behandelt werden](https://docs.microsoft.com/de-DE/office365/SecurityCompliance/bulk-complaint-level-values). Sie können unterschiedliche Richtlinien oder Regel für die unterschiedlichen Wünsche der Benutzer erstellen.
    
- **CAT:SPOOF** oder **CAT:PHISH** Gibt an, dass die Nachricht gefälscht zu sein scheint, was bedeutet , dass die Nachrichtenquelle nicht überprüft werden kann und verdächtig sein könnte. Wenn die Nachricht gültig ist, muss der Absender sicherstellen, dass sie über eine korrekte SPF- und DKIM-Konfiguration verfügt. Überprüfen Sie die Kopfzeile „Authentication-Results“, um weitere Informationen zu erhalten. Es ist zwar schwierig, alle Absender dazu zu veranlassen, gültige E-Mail-Authentifizierungsmethoden zu verwenden, werden diese Überprüfungen jedoch übergangen, kann dies eine große Gefahr darstellen. 
    
### <a name="x-customspam"></a>x-customspam

- Das Vorhandensein dieser Kopfzeile gibt an, dass die Nachricht als Spam gekennzeichnet wurde, da eine der [erweiterten Spamoptionen](https://technet.microsoft.com/library/jj200750%28v=exchg.150%29.aspx) in Ihrem Spamfilter aktiviert ist. Es wird empfohlen, dass Sie die Standardeinstellungen verwenden, sofern Sie diese Features nicht benötigen. 
    
## <a name="solutions-to-additional-causes-of-too-much-spam"></a>Lösungen für weitere Ursachen von zu viel Spam

Um effektiv zu arbeiten, müssen Administratoren in Exchange Online Protection (EOP) ein paar Aufgaben ausführen. Wenn Sie nicht der Administrator für Ihren Office 365-Mandanten sind und zu viel Spam erhalten, sollten Sie diese Aufgaben zusammen mit Ihrem Administrator ausführen. Andernfalls können Sie mit dem Abschnitt für Benutzer fortfahren.
  
### <a name="for-admins"></a>Für Administratoren

- **DNS-Einträge auf Office 365 zeigen lassen** Damit EOP Schutz bieten kann, müssen die MX-DNS-Einträge (Mail Exchanger) für alle Domänen ausschließlich auf Office 365 zeigen. Wenn die MX-Einträge nicht auf Office 365 zeigen, bietet EOP keinen Spamfilter für Ihre Benutzer. Wenn Sie einen anderen Dienst oder eine andere Anwendung für den Spamfilter für Ihre Domäne verwenden möchten, sollten Sie den Spamschutz in EOP deaktivieren. Erstellen Sie hierfür eine E-Mail-Flussregel, durch die der SCL-Wert auf -1 festgelegt wird. Wenn Sie sich später entschließen, doch EOP zu verwenden, entfernen Sie diese E-Mail-Flussregel. 
    
- **Aktivieren des Add-Ins "Nachricht melden" für Benutzer** Es wird dringend empfohlen, dass Sie das [Add-In "Nachricht melden" für Ihre Benutzer aktivieren](/security/office-365-security/enable-the-report-message-add-in.md).

- **Verwenden Sie [Übermittlungen-Explorer](/security/office-365-security/admin-submission.md)** -Administratoren können jetzt E-Mails mithilfe von Datei-oder Netzwerknachrichten-ID,-URLs und-Dateien zum Scannen durch Microsoft in Office 365 senden. Als Administrator können Sie ggf. auch das Feedback anzeigen, das Ihre Benutzer senden, und beliebige Muster verwenden, um alle Einstellungen anzupassen, die möglicherweise Probleme verursachen.

- **Stellen Sie sicher, dass sich die Benutzer innerhalb der zulässigen Grenzwerte** zum Senden und Empfangen von E-Mails befinden, wie [hier](https://docs.microsoft.com/de-DE/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits) gezeigt.

 - **Überprüfen Sie die Massenebenen, **wie [hier](/security/office-365-security/bulk-complaint-level-values.md) angegeben.
    
### <a name="for-users"></a>Für Benutzer
    
- **Erstellen einer Liste sicherer Absender** Benutzer können Adressen vertrauenswürdiger Absender in [Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065) oder [Outlook im Web](https://go.microsoft.com/fwlink/p/?LinkId=294862) ihrer Liste sicherer Absender hinzufügen. Um mit Outlook im Web zu beginnen, wählen Sie **Einstellungen**![ConfigureAPowerBIAnalysisServicesConnector_settingsIcon](media/24bd5467-c8d2-4936-9c37-a179bd0e21ec.png) \> **Optionen** \> **Blockieren oder Zulassen** aus. Das folgende Diagramm zeigt ein Beispiel zum Hinzufügen von Elementen zu einer Liste sicherer Absender.
  
![Hinzufügen eines sicheren Absenders in Outlook im Web](media/8de6b24e-429e-4e8f-8ce8-53ba659cbfcb.png)
  
Von EOP werden die sicheren Absender und Empfänger Ihrer Benutzer berücksichtigt, nicht jedoch sichere Domänen. Dies gilt unabhängig davon, ob die Domäne in Outlook im Web oder in Outlook hinzugefügt und über die Verzeichnissynchronisierung synchronisiert wurde.

- **Deaktivieren des SmartScreen-Filters in Outlook** Wenn Ihre Benutzer den Outlook-Desktopclient verwenden, sollten sie den SmartScreen-Filter deaktivieren, da dieser nicht mehr unterstützt wird. Wenn dieses Feature aktiviert ist, kann es zu falsch positiven Ergebnissen führen. führen. Dies sollte nicht erforderlich sein, wenn ein aktualisierter Desktopclient für Outlook ausgeführt wird.

## <a name="troubleshooting-a-message-ends-up-in-the-junk-folder-even-though-eop-marked-the-message-as-non-spam"></a>Problembehandlung: Eine Nachricht befindet sich im Ordner "Junk", obwohl EOP die Nachricht als Nicht-Spam-Nachricht gekennzeichnet hat

Wenn die Benutzer in Outlook die Option "Nur sichere Absender und Empfänger: Es werden nur Nachrichten von Personen und Domänen auf den Listen 'Sichere Absender' und 'Sichere Empfänger' in den Posteingang übermittelt" aktiviert haben, werden alle E-Mails von einem Absender in den Junk-E-Mail-Ordner verschoben, es sei denn, dieser Absender ist auf der Liste sicherer Absender des Empfängers verzeichnet. Dies erfolgt unabhängig davon, ob EOP eine Nachricht als Nicht-Spam-Nachricht kennzeichnet oder Sie in EOP eine Regel eingerichtet haben, um eine Nachricht als Nicht-Spam-Nachricht zu kennzeichnen.
  
Sie können die Option "Nur sichere Absender und Empfänger" für Outlook-Benutzer deaktivieren. Folgen Sie dazu den Anweisungen unter [Outlook: Richtlinieneinstellung zum Deaktivieren der Benutzeroberfläche für den Junk-E-Mail-Filtermechanismus](https://support.microsoft.com/de-DE/kb/2180568).
  
Wenn Sie eine Nachricht in Outlook im Web anzeigen, wird ein gelber Sicherheitshinweis eingeblendet, der darauf hinweist, dass sich die Nachricht im Ordner "Junk" befindet, da der Absender nicht auf der Liste sicherer Absender des Empfängers verzeichnet ist.
  
Wenn Sie sich den Kopf einer Nachricht ansehen, finden Sie darin möglicherweise den Stempel "SFV:SKN (IP Allow or ETR Allow)" oder "SFV:NSPM (non-spam)", die Nachricht wird jedoch trotzdem in den Junk-E-Mail-Ordner des Benutzers verschoben. Nichts im Nachrichtenkopf weist darauf hin, dass der Benutzer "Nur sichere Absender und Empfänger" aktiviert hat. Dazu kommt es, weil die in Outlook von Benutzern festgelegte Option "Nur sichere Absender und Empfänger" die EOP-Einstellung überschreibt. 
  
 **So überprüfen Sie, warum eine Nachricht von einem sicheren Absender im Nachrichtenkopf als Nicht-Spam-Nachricht gekennzeichnet ist, aber trotzdem im Junk-E-Mail-Ordner des Benutzers landet**
  
1. Wenn Sie erfahren möchten, wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, lesen Sie [Herstellen einer Verbindung mit Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554). 
    
2. Führen Sie den folgenden Befehl aus, um die Junk-E-Konfigurationseinstellungen des Benutzers anzuzeigen:
    
  ```Powershell
  Get-MailboxJunkEmailConfiguration example@contoso.com | fl TrustedListsOnly,ContactsTrusted,TrustedSendersAndDomains
  ```

- Wenn "TrustedListsOnly" auf "True" festgelegt ist, bedeutet dies, dass die Einstellung aktiviert ist.
- Wenn "ContactsTrusted" auf "True" festgelegt ist, vertraut der Benutzer sowohl den Kontakten als auch den sicheren Absendern.
- In "TrustedSendersAndDomains" ist der Inhalt der Liste sicherer Absender des Benutzers aufgeführt.


## <a name="eop-only-customers-use-directory-synchronization"></a>Kunden, die nur EOP nutzen: Verzeichnissynchronisierung verwenden

Wenn Sie nur EOP nutzen, d. h. den EOP-Dienst für die Verwendung mit Ihrem lokalen (Exchange) E-Mail-Server abonnieren, sollten Sie Benutzereinstellungen mithilfe der Verzeichnissynchronisierung mit dem Dienst synchronisieren. Auf diese Weise wird sichergestellt, dass die Liste sicherer Absender von EOP berücksichtigt wird. Weitere Informationen finden Sie unter "Verwenden der Verzeichnissynchronisierung zum Verwalten von E-Mail-Benutzern" in [Verwalten von E-Mail-Benutzern in EOP](https://go.microsoft.com/fwlink/?LinkId=534098).
