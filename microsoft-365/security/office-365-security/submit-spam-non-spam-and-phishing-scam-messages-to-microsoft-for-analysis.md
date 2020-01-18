---
title: Übermitteln von Spam-, Nicht-Spamnachrichten und Nachrichten, die als betrügerische Phishing-Angriffe angesehen werden, an Microsoft zur Analyse
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 'Sie und Ihre Benutzer können falsche Negative und falsch positive Spamnachrichten zur Analyse an Microsoft übermitteln. '
ms.openlocfilehash: 6ca4c99d5e8803fdf7f41ff00cc2a5e65ab38049
ms.sourcegitcommit: a122fd1fce523171529c7f610bb7faf09d30a8bb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/18/2020
ms.locfileid: "41238432"
---
# <a name="submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis"></a>Übermitteln von Spam-, Nicht-Spamnachrichten und Nachrichten, die als betrügerische Phishing-Angriffe angesehen werden, an Microsoft zur Analyse

Es kann frustrierend sein, wenn Benutzer in Ihrer Organisation Junk-Nachrichten (Spam) oder Phishing-Scam-Nachrichten in Ihrem Posteingang empfangen oder wenn Sie keine legitime e-Mail-Nachricht erhalten, weil Sie als Junk gekennzeichnet ist. Wir optimieren unsere Spamfilter ständig, um genauere Angaben zu machen. Sie und Ihre Benutzer können diesen Prozess unterstützen, indem Sie falsche Negative und falsch positive Spamnachrichten zur Analyse an Microsoft senden. Eine "falsche Negative" ist eine Spamnachricht, die zwar hätte, aber nicht als Spam identifiziert worden sein sollte. Ein falsch positives Ergebnis ist eine legitime e-Mail-Nachricht, die fälschlicherweise als Spam identifiziert wurde. 
  
> [!NOTE]
> Aufgrund der hohen Anzahl von Übermittlungen, die wir erhalten, können wir möglicherweise nicht alle Anfragen zur Analyse beantworten. 

Administratoren können e-Mails, URLs und Anlagen zur Überarbeitung an Microsoft senden. Siehe [Admin Übermittlungen in Office 365 ATP](admin-submission.md).
  
## <a name="submit-junk-or-phishing-messages-that-passed-through-the-spam-filters"></a>Weiterleiten von Junk-E-Mails und Phishingnachrichten, die den Spamfilter passiert haben
<a name="sectionSection0"> </a>

Wenn Sie eine Nachricht erhalten, die die Spamfilter durchlaufen hat und als Junk-oder Phishing-Betrüger klassifiziert werden sollte, können Sie die Meldung "falsch negativ" nach Bedarf an die Microsoft-Spam Analyse-und Microsoft-Phishing-Analyseteams senden. Die Analysten überprüfen die Nachricht und fügen Sie den Dienst weiten Filtern hinzu, wenn Sie die Klassifizierungskriterien erfüllen. 
  
Informationen zu weiteren Spameinstellungen, die für die gesamte Organisation gelten, finden Sie unter [Blockieren von E-Mail-Spam mit dem Office 365-Spamfilter zum Verhindern von falsch negativen Ergebnissen](reduce-spam-email.md). Dieser Artikel enthält Tipps, mit denen Sie verhindern können, dass falsch negative Ergebnisse aufweisen.
  
Sie können Junk-E-Mails wie folgt weiterleiten:
  
- Verwenden Sie für Outlook-und Outlook im-Webbenutzern das Add-in "Berichtsnachricht" für Microsoft Outlook. Informationen zum Installieren und verwenden dieses Tools finden Sie unter [enable the Report Message Add-in](enable-the-report-message-add-in.md). 
        
- Sie können auch e-Mails verwenden, um Nachrichten an Microsoft zu übermitteln, die als Junk-oder Phishing-Scams klassifiziert werden sollen, wie im folgenden Verfahren beschrieben.
    
### <a name="use-email-to-submit-junk-spam-or-phishing-scam-messages-to-microsoft"></a>Weiterleiten von Junk-E-Mails oder Nachrichten, die als betrügerischer Phishingversuch gelten, per E-Mail an Microsoft 
<a name="Useemailtosubmitjunkspamorphishingscammessages"> </a>

So leiten Sie Junk-E-Mails oder Nachrichten, die als betrügerischer Phishingversuch gelten, per E-Mail an Microsoft
  
1. Erstellen Sie eine leere e-Mail-Nachricht.
    
2. Adressieren Sie die Nachricht an das Microsoft-Team, das Nachrichten wie folgt überprüft: 
    
  - Für Junk-e-Mails: Junk@office365.Microsoft.com
    
  - Für Phishing-Nachrichten: Phish@office365.Microsoft.com
    
3. Kopieren Sie die Junk-oder Phishing-Scam-Nachricht in die neue Nachricht als Anlage, und fügen Sie Sie ein. 
    
   > [!NOTE]
   > • Sie können mehrere Nachrichten in der neuen Nachricht anfügen. Stellen Sie sicher, dass alle Nachrichten vom gleichen Typ sind: entweder Phishing-Scam-Nachrichten oder Junk-e-Mail-Nachrichten. <br/><br/>• Lassen Sie den Text der neuen Nachricht leer. <br/><br/>• Verwenden Sie entweder. msg (standardmäßiges Outlook-Format) oder. eml (standardmäßige Outlook im Internetformat) Formate für die angefügten Nachrichten.
  
4. Klicken Sie auf **Senden**.
    
## <a name="submit-messages-that-were-tagged-as-junk-but-should-have-been-allowed-through"></a>Weiterleiten von Nachrichten, die als Junk markiert wurden, aber durchgelassen werden sollten
<a name="sectionSection1"> </a>

Wenn eine Nachricht fälschlicherweise als Junk identifiziert wurde, können Sie die Meldung "falsch positiv" an das Microsoft-Spam Analyse Team übermitteln. Die Analysten werden die Nachricht bewerten und analysieren. Abhängig vom Ergebnis der Analyse werden die Filterregeln für Spaminhalte des Diensts angepasst, damit die Nachricht zugestellt werden kann.
  
Administratoren können weitere Informationen zur Spam Einstellung überprüfen, die für eine ganze Organisation gelten. Hier erfahren Sie [, wie Sie sicherstellen können, dass eine Nachricht nicht als Spam gekennzeichnet ist](prevent-email-from-being-marked-as-spam.md). Diese Informationen sind nützlich, wenn Sie über die Steuerung auf Administratorebene verfügen und wenn Sie falsch positive Ergebnisse vermeiden möchten.
  
Leiten Sie Nichtspamnachrichten wie folgt weiter:
  
- Wenn Sie die Aktion **Nachricht in Junk-e-Mail-Ordner senden** verwenden, wenn Sie Ihre Inhaltsfilter konfigurieren (Dies ist die Standardaktion), können Benutzer falsch positive Nachrichten in Ihrem Junk-e-Mail-Ordner "Outlook" oder "Outlook im Internet" (früher als "Outlook Web App" bezeichnet) freigeben. 
    
  - Outlook-Benutzer können falsch positive Nachrichten mit der Rechtsklickmenü Option **nicht Junk** freigeben. Sie müssen die Nachricht jedoch über e-Mail an Microsoft übermitteln, wie im Verfahren in diesem Artikel dargestellt. 
    
  - Benutzer von Outlook im Internet können falsch positive Nachrichten freigeben und Sie zur Analyse mithilfe der Aktion **Markierung als nicht-Junk-e-Mail** an Microsoft übermitteln. Weitere Informationen zur Vorgehensweise finden Sie unter [melden von Junk-e-Mails und Phishing-Scams in Outlook im Internet ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).
    
- Wenn Sie die Aktion **Quarantäne Nachricht** anstelle der Aktion **Nachricht in Junk-e-Mail-Ordner verschieben** beim Konfigurieren der Inhaltsfilter verwenden: 
    
  - Administratoren können Spamnachrichten in Quaratäne freigeben und diese als falsch positive Nachrichten vom Exchange-Admin Center übermitteln. Weitere Informationen finden Sie unter [Finden und Freigeben von Nachrichten in Quarantäne als Administrator](find-and-release-quarantined-messages-as-an-administrator.md).
    
  - Benutzer können Ihre eigenen Nachrichten in Spamquarantäne freigeben und Sie über die folgenden Kanäle als falsch positive Ergebnisse melden: 
    
  - Auf der Benutzeroberfläche von Exchange Admin Center (EAC). Weitere Informationen finden Sie unter [Find and Release Quarantined Messages (End Users)](find-and-release-quarantined-messages-as-a-user.md).
    
  - Über Nachrichten zur Spambenachrichtigung für Endbenutzer (falls vom Administrator aktiviert). 
    
- Sie können Nachrichten, die nicht als Spam klassifiziert werden sollen, auch per E-Mail an Microsoft weiterleiten. Wenn Sie dies tun, stellen Sie sicher, dass Sie die Schritte im folgenden Verfahren verwenden.
    
### <a name="use-email-to-submit-false-positive-messages"></a>Übermitteln falsch positiver Nachrichten per E-Mail

Verwenden Sie dasselbe Verfahren wie im Abschnitt "[Verwenden von e-Mails zum Übermitteln von Junk-e-Mails (Spam) oder Phishing-Scam-Nachrichten an Microsoft ](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md#Useemailtosubmitjunkspamorphishingscammessages)", aber senden Sie die Nachricht an not_junk@office365.Microsoft.com.
  
## <a name="spam-evaluation-and-rules-deployment"></a>Spam Auswertung und Regel Bereitstellung
<a name="sectionSection2"> </a>

Das Spam Analyseteam untersucht Nachrichten, die Sie übermitteln, und passt die Spamfilter an, um künftige Junk-e-Mails zu verhindern. Das Ergebnis ist, dass Office 365 Spamfilter areconstantly verfeinert wurden. Alle übermittelten Elemente werden auf Netzwerkebene bewertet. Falsch positive Übermittlungen werden überprüft und für eine mögliche Regelanpassung bewertet, um zukünftige Nachrichten über die Spamfilter zuzulassen. Daher ist es für Sie und alle Kunden, die das globale Netzwerk verwenden, vorteilhaft, den Dienst über falsch positive Meldungen und auch falsche Negative (ungefilterte Spam) zu informieren. Das Spam-Team untersucht Indikatoren innerhalb jeder übermittelten Nachricht, wie etwa die folgenden:
  
- Von Adresse
    
- Sendende IP-Adresse
    
- Schlüsselwörter
    
- Ausdrücke
    
- Häufigkeit der Übertragung
    
- Andere Trends und Muster
    
Nachdem Sie diese Informationen überprüft haben, kann das Spam-Team möglicherweise Änderungen an den Spamfilter Ebenen des Diensts vornehmen. Weitere Informationen zum Spam-Team finden Sie im folgenden englischsprachigen Video:
  
[Video zu Microsoft Exchange Spam-Team](https://youtu.be/-TpX_-GMC7o?hd=1)
  
Die Spambewertung ist ein kontinuierlicher Prozess, der unabhängig von der ursprünglichen Sprache oder dem ursprünglichen Zeichensatz angewendet wird. Da eine Spamnachricht vage sein oder keinen Text im Betreff oder Nachrichtentext enthalten kann, nutzt das Spamteam sehr oft andere Nachrichtenmerkmale zum Filtern. Dies bedeutet, dass – nachdem das Spamteam eine bestimmte Nachricht als Spam markiert und die erforderlichen Änderungen an der Regelbasis vorgenommen hat – diese Nachricht zukünftig so lange gesperrt wird, bis ihre Merkmale ausreichend geändert wurden, dass sie unsere Filter passiert. Neue Spamregeln werden laufend bereitgestellt. Der Zeitrahmen für Regeln für einzelne Übermittlungen variiert je nach Menge und Qualität der Übermittlungen. Da neue Spamregeln global für alle Kunden festgelegt werden, führt nicht jede einzelne übermittelte Spamnachricht zu einer neuen Spamregel.
   
## <a name="for-more-information"></a>Weitere Informationen
<a name="sectionSection4"> </a>

[Schutz vor Spam und Schadsoftware](anti-spam-and-anti-malware-protection.md)
  
[So können Sie dazu beitragen, dass eine Nachricht nicht als Spam gekennzeichnet wird](prevent-email-from-being-marked-as-spam.md)
  
[Blockieren von E-Mail-Spam mit dem Office 365-Spamfilter zur Vermeidung von falsch negativen Einträgen](reduce-spam-email.md)
  

