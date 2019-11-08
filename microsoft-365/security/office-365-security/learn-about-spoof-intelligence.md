---
title: Wissenswertes zur Spoofintelligenz
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/22/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
description: Verwenden Sie Spoof Intelligence im Security &amp; Compliance Center auf der Seite Anti-Spam-Einstellungen, um alle Absender zu überprüfen, die entweder Spoofing von Domänen sind, die Teil Ihrer Organisation sind, oder Spoofing externer Domänen. Spoof Intelligence steht als Teil von Office 365 Enterprise E5 oder separat im Rahmen von Advanced Threat Protection und Exchange Online Protection zur Verfügung.
ms.openlocfilehash: 2b426679818832d95b93d7795aaed7b5316ea5fc
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "38032330"
---
# <a name="learn-more-about-spoof-intelligence"></a>Wissenswertes zur Spoofintelligenz

Verwenden Sie Spoof Intelligence im Security &amp; Compliance Center auf der **Seite Anti-Spam-Einstellungen** , um alle Absender zu überprüfen, die entweder Spoofing von Domänen sind, die Teil Ihrer Organisation sind, oder Spoofing externer Domänen. Spoof Intelligence steht als Teil von Office 365 Enterprise E5 oder separat im Rahmen von Advanced Threat Protection (ATP) und ab Oktober 2018 Exchange Online Protection (EoP) zur Verfügung. 
  
## <a name="what-types-of-email-spoofing-can-i-review-and-which-should-i-protect-against-with-spoof-intelligence"></a>Welche Arten von e-Mail-Spoofing kann ich überprüfen und welche sollte ich gegen Spoof Intelligence schützen?

Für Domänen, die Sie besitzen, können Sie Absender überprüfen, die Ihre Domäne Spoofing durchführen und dann festlegen, dass der Absender fortgesetzt oder der Absender blockiert werden soll. Für externe Domänen können Sie die Absenderdomäne in Kombination mit der sendenden Infrastruktur zulassen, obwohl es sich nicht um eine einzelne sendende e-Mail-Adresse handelt.
  
Wenn ein Absender eine e-Mail-Adresse fälscht, scheinen diese e-Mails im Auftrag eines oder mehrerer Benutzerkonten in einer der Domänen Ihrer Organisation oder einer externen Domäne zu senden, die an Ihre Organisation gesendet wird. Erstaunlicherweise gibt es einige legitime geschäftliche Gründe für Spoofing. In diesen Fällen können Sie den Absender beispielsweise nicht daran hindern, Ihre Domäne zu fälschen:
  
- Sie haben Drittanbieter Absender, die Ihre Domäne verwenden, um Massen-e-Mails an Ihre eigenen Mitarbeiter für Unternehmensumfragen zu senden.
    
- Sie haben ein externes Unternehmen angeheuert, um Werbung oder Produktupdates in Ihrem Auftrag zu generieren und zu senden.
    
- Ein Assistent, der regelmäßig e-Mails für eine andere Person in Ihrer Organisation senden muss.
    
- Eine Anwendung, die so konfiguriert ist, dass Sie Ihre eigene Organisation fälscht, um interne Benachrichtigungen per e-Mail zu senden.
    
Externe Domänen senden häufig gefälschte e-Mail-Nachrichten, und viele dieser Gründe sind legitim. Hier sind beispielsweise einige legitime Fälle, in denen externe Absender gefälschte e-Mail-Nachrichten senden:
  
- Der Absender befindet sich in einer Diskussions-Mailingliste, und die Mailingliste leitet die e-Mail vom ursprünglichen Absender an alle Teilnehmer der Mailingliste weiter.
    
- Ein externes Unternehmen sendet e-Mail-Nachrichten im Auftrag eines anderen Unternehmens (beispielsweiseeines automatisierten Berichts oder eines Software-as-a-Service-Unternehmens).
    
Sie benötigen eine Möglichkeit, um sicherzustellen, dass die von legitimen spoofern gesendeten e-Mails nicht in Spamfiltern in Office 365 oder externen e-Mail-Systemen erfasst werden. Normalerweise werden diese e-Mail-Nachrichten von Office 365 als Spam behandelt. Als Office 365 Administrator haben Sie die Möglichkeit, dies zu verhindern, indem Sie Spoof-Filter im Security &amp; Compliance Center einrichten. Wenn Sie die Domäne besitzen, können Sie SPF, DKIM und DMARC konfigurieren, um diese Absender zuzulassen.
  
Auf der anderen Seite müssen böswillige Spoofer, die Absender, die Ihre Domäne Spoofing oder externe Domänen, Spam-oder Phishing-e-Mails senden, blockiert werden. Spoofing ist auch eine häufige Möglichkeit für Phishers, Benutzeranmeldeinformationen zu erhalten. Office 365 verfügt über einen integrierten spoofschutz, um Ihre Organisation vor Absendern dieser böswilligen e-Mails zu schützen. Spoof Protection für die Domänen Ihrer Organisation ist für alle Office 365 Kunden immer aktiviert, und der externe Domänen spoofschutz ist standardmäßig für Advanced Threat Protection-Kunden und ab Oktober 2018 EoP-Kunden ebenfalls aktiviert. Um diesen Schutz weiter zu verbessern, teilen Sie uns mit, welche Absender autorisiert sind, die Domänen Ihrer Organisation zu spoofen und e-Mails in Ihrem Namen zu senden, und ob externe Domänen Spoofing zulässig sind. Jede e-Mail, die von einem Absender gesendet wird, den Sie nicht autorisieren, wird von Office 365 als Spam oder Spoofing behandelt. Achten Sie auf die Absender, die Ihre Domäne Spoofing durchführen, und helfen Sie uns dabei, spoof &amp; Intelligence mithilfe des Security Compliance Center zu verbessern.
  
## <a name="managing-spoof-intelligence-in-the-security-amp-compliance-center"></a>Verwalten von Spoof Intelligence im Security &amp; Compliance Center
<a name="Managespooflist"> </a>

Die von Ihnen eingerichteten Spoof Intelligence-Richtlinien werden immer von Office 365 erzwungen. Sie können es nicht deaktivieren, aber Sie können auswählen, wie viel Sie es aktiv verwalten möchten.
  
Sie können die Absender, die Ihre Domäne Spoofing durchführen, oder externe Domänen überprüfen und dann entscheiden, ob jeder Absender über das Security &amp; Compliance Center dazu berechtigt sein sollte. Für jedes gefälschte Benutzerkonto, das von einem Absender von Ihrer Domäne oder einer externen Domäne gefälscht wird, können Sie die Informationen in der folgenden Tabelle anzeigen.
  
|**Parameter**|**Beschreibung**|
|:-----|:-----|
|Absender  <br/> |Wird auch als echter Absender bezeichnet. Dies ist normalerweise die Domäne, aus der die Spoof-e-Mail stammt. Office 365 bestimmt die Domäne des Zeiger-DNS-Eintrags (PTR) der sendenden IP-Adresse, die Ihre Organisation fälscht. Wenn keine Domäne gefunden wird, zeigt der Bericht stattdessen die IP-Adresse des Absenders an.  <br/> |
|Spoofing-Benutzer  <br/> |Das Benutzerkonto, das vom Absender gefälscht wird.  <br/> Nur **interne** Registerkarte. Dieses Feld enthält eine einzelne e-Mail-Adresse, oder wenn der Absender mehrere Benutzerkonten fälscht, enthält er **mehr als einen**.  <br/> Nur **externe** Registerkarte. Externe Domänen enthalten nur eine sendende Domäne und enthalten keine vollständige e-Mail-Adresse.  <br/> **Tipp! Für fortgeschrittene Administratoren.** Der Spoofing-Benutzer ist die Absenderadresse (5322. from), die auch als Absenderadresse vom e-Mail-Client angezeigt wird. Dies wird manchmal als Header. from-Adresse bezeichnet. Die Gültigkeit dieser Adresse wird von SPF nicht überprüft.           |
|Anzahl der Nachrichten  <br/> |Die Anzahl der e-Mail-Nachrichten, die der Absender innerhalb der letzten 30 Tage im Namen des identifizierten gefälschten Absenders oder Absenders an Ihre Organisation gesendet hat.  <br/> |
|Anzahl von Benutzer Reklamationen  <br/> |Beschwerden, die von Benutzern innerhalb der letzten 30 Tage gegen diesen Absender von Ihren Benutzern eingereicht wurden. Beschwerden sind in der Regel in Form von Junk-Übermittlungen an Microsoft.  <br/> |
|Authentifizierungsergebnis  <br/> |Dieser Wert wird **übergeben** , wenn der Absender Exchange Online Protection (EoP)-Absender Authentifizierungsüberprüfung (beispielsweise SPF oder DKIM) **fehlgeschlagen** ist, wenn der Absender EoP Absender Authentifizierungsprüfungen fehlgeschlagen ist, oder **unbekannt** , wenn das Ergebnis dieser Prüfungen nicht bekannt ist.  <br/> |
|Entscheidungs-Festlegung durch  <br/> |Zeigt an, ob der Office 365 Administrator oder die Spoof Intelligence-Richtlinie bestimmt, ob der Absender den Benutzer Spoofing erlaubt.  <br/> |
|Zuletzt gesehen  <br/> |Das letzte Datum, an dem eine Nachricht von diesem Absender im Namen dieses gefälschten Benutzers empfangen wurde.  <br/> |
|Spoofing zulässig?  <br/> | Zeigt an, ob dieser Absender e-Mails im Namen des gefälschten Benutzers senden darf. Mögliche Werte sind:  <br/> **Yes** Alle gefälschten Adressen dieses Spoofing-Absenders können Ihre Organisation Spoofing.  <br/> **Nein** Spoofing-Adressen von diesem Spoofing-Absender dürfen Ihre Organisation nicht spoofen. Stattdessen werden Nachrichten von diesem Absender Office 365 als Spam gekennzeichnet.  <br/> **Einige Benutzer** Wenn ein Absender mehrere Benutzer Spoofing durchführt, können einige gefälschte Adressen dieses Absenders Ihre Organisation Spoofing, der Rest wird als Spam gekennzeichnet. Verwenden Sie die **detaillierte** Registerkarte, um die spezifischen Adressen anzuzeigen.  <br/> |
|Spoof-Typ  <br/> |Dieser Wert ist **intern** , wenn die Domäne eine der in Ihrer Organisation gestellten Domänen ist, andernfalls ist der Wert **extern**.  <br/> |
   
 **So verwalten Sie Absender, die Ihre Domäne Spoofing mithilfe des Security &amp; Compliance Center**
  
1. Wechseln Sie zum [Security &amp; Compliance Center](https://protection.office.com).
    
2. Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Office 365 an. Ihr Konto muss über Administratoranmeldeinformationen in Ihrer Office 365 Organisation verfügen.
    
3. Erweitern Sie im &amp; Security Compliance Center den Knoten **Threat Management** \> **Policy** \> **Anti-Spam**.  
  
    ![Screenshot mit Zugriff auf die Anti-Spam-Seite](../media/0a098e68-5ecf-40d7-984f-d15fcc1f958d.jpg)
  
4. Wählen Sie auf der Seite **Anti-Spam-Einstellungen** im rechten Bereich die Registerkarte **Benutzerdefiniert** aus, und führen Sie einen Bildlauf nach unten durch, und erweitern Sie **Spoof Intelligence Policy**.  
  
    ![Screenshot mit Zugriff auf die benutzerdefinierten Anti-Spam-Einstellungen](../media/a5112100-0b37-460f-932d-5b2f98157871.jpg)
  
5. Um die Liste der Absender anzuzeigen, die Ihre Domäne Spoofing haben, wählen Sie **neue Absender überprüfen** und dann die Registerkarte **Domänen** aus. 
    
    Wenn Sie bereits Absender überprüft haben und einige der vorherigen Optionen ändern möchten, können Sie stattdessen die Option **mir Absender anzeigen auswählen, die ich bereits überprüft habe** . In beiden Fällen wird der folgende Bereich angezeigt.  
  
    ![Screenshot mit Zugriff auf die Registerkarte "gefälschte Absender"](../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)
  
    Jeder Spoofing-Benutzer wird in einer separaten Zeile angezeigt, sodass Sie auswählen können, ob der Absender jeden Benutzer einzeln Spoofing zulassen oder blockieren darf.  
  
    Wenn Sie einen Absender zur Zulassungsliste für einen Benutzer hinzufügen möchten, wählen Sie **Ja** aus der Spalte **zulässig für Spoofing** aus. Wenn Sie der Sperrliste eines Benutzers einen Absender hinzufügen möchten, wählen Sie **Nein**aus.
     
    Um die Richtlinie für Domänen festzulegen, die Ihnen nicht gehören, wählen Sie die Registerkarte **externe Domänen** aus. ändern Sie in der Spalte **zulässiges Spoofing** den Absender in **Ja** , um dem Absender das Senden nicht authentifizierter e-Mails an Ihre Organisation zu gestatten. Wenn Sie der Meinung sind, dass Office 365 einen Fehler gemacht hat, um dem Absender die Möglichkeit zu geben, gefälschte e-Mail-Nachrichten zu senden, ändern Sie die Spalte **zulässig in Spoof** auf **Nein**.  
  
    ![Screenshot, der angibt, ob ein Absender Spoofing zulässig ist](../media/5dbef9cf-103f-49cd-9638-4b0083d6baa7.jpg)
  
6. Klicken Sie auf **Speichern** , um alle Änderungen zu speichern. 

Wenn Sie ein Office 365 Enterprise E5-Abonnement haben oder Advanced Threat Protection als Add-on separat erworben haben, können Sie auch Absender verwalten, die Ihre Domäne durch Spoof [Intelligence Insight](https://docs.microsoft.com/office365/securitycompliance/walkthrough-spoof-intelligence-insight)manipulieren.
    
## <a name="configuring-the-anti-spoofing-policy"></a>Konfigurieren der Richtlinie zum Schutz vor Spoofing
<a name="Managespooflist"> </a>

Zusätzlich zum Zulassen oder Blockieren eines bestimmten Absenders beim Senden von gefälschten e-Mail-Nachrichten an Ihre Organisation können Sie auch konfigurieren, wie streng der Filter sein soll und welche Aktion ausgeführt werden soll, wenn eine Spoofing-Nachricht gefunden wird.
  
Anti-Spoofing-Schutz wird auf e-Mails von Absendern von Domänen angewendet, die sich außerhalb Ihrer Office 365 Organisation befinden. Sie können die Richtlinie auf Empfänger anwenden, deren Postfächer für Office 365 Enterprise E5, Advanced Threat Protection und ab Oktober 2018 EoP-Kunden lizenziert sind. Sie verwalten die Antispoofing-Richtlinie zusammen mit den anderen Einstellungen für die Phishing-Abwehr. Weitere Informationen zu Anti-Phishing-Einstellungen finden Sie unter [Einrichten der Office 365 Anti-Phishing-Richtlinien](https://support.office.com/article/set-up-office-365-atp-anti-phishing-policies-5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578?ui=en-US&amp;rs=en-US&amp;ad=US#phishpolicyoptions).
  
Office 365 enthält standardmäßigen Antispoofing-Schutz, der immer aktiv ist. Dieser Standardschutz ist im Security &amp; Compliance Center nicht sichtbar oder kann über Windows PowerShell-Cmdlets abgerufen werden. Sie können den standardmäßigen Schutz gegen Spoofing nicht ändern. Stattdessen können Sie konfigurieren, wie streng Office 365 den Schutz vor Spoofing in jeder von Ihnen erstellten Anti-Phishing-Richtlinie erzwingt. 
  
Auch wenn die Richtlinie zum Schutz vor Spoofing im Security &amp; Compliance Center unter der Richtlinie zum Schutz vor Phishing angezeigt wird, erbt Sie Ihr Standardverhalten nicht von der vorhandenen Phishing-Einstellung unter der Antispam-Konfiguration. Wenn Sie über Einstellungen unter **Anti-Spam** \> - **Phishing** verfügen, die Sie für Antispoofing replizieren möchten, müssen Sie eine Anti-Phishing-Richtlinie erstellen und dann den Spoof-Teil der Anti-Phishing-Richtlinie so bearbeiten, dass Ihre spoofeinstellungen wie im folgenden Abschnitt beschrieben berücksichtigt werden, anstatt die Standardeinstellungen zu akzeptieren, die im Hintergrund ausgeführt werden. 
  
 **So konfigurieren Sie den Schutz gegen Spoofing in einer Anti-Phishing-Richtlinie mithilfe des &amp; Security Compliance Center**
  
1. Wechseln Sie zum [Security &amp; Compliance Center](https://protection.office.com).
    
2. Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Office 365 an. Ihr Konto muss über Administratoranmeldeinformationen in Ihrer Office 365 Organisation verfügen.
    
3. Erweitern Sie im &amp; Security Compliance Center den Knoten **Threat Management** \> **Policy** \> **Anti-Phishing**. 
    
4. Wählen Sie auf der Seite **Anti-Phishing** im rechten Bereich die AntiPhishing-Richtlinie aus, die Sie konfigurieren möchten. 
    
5. Wählen Sie auf der angezeigten Seite in der Zeile **Spoof** die Option **Bearbeiten**aus. 
    
6. Konfigurieren Sie als nächstes die Aktionen, die ausgeführt werden sollen, wenn eine Nachricht als domänenübergreifendes Spoof erkannt wird. Das Standardverhalten besteht darin, die Nachricht in den Junk-e-Mail-Ordner des Empfängers zu verlagern. Die andere Option besteht darin, die Nachricht an die Quarantäne zu senden. Weitere Informationen zum Verwalten von Nachrichten, die an die Quarantäne gesendet werden, finden Sie unter [Quarantäne von e-Mail-Nachrichten in Office 365](quarantine-email-messages.md).  
  
    ![Screenshot mit Optionen zur Bearbeitung von Antispoofing-Richtlinien](../media/7a868dff-2c4b-46b9-88ca-f2d523ca2307.jpg)
  
7. Treffen Sie Ihre Auswahl, und wählen Sie dann **Speichern**aus. 
    
## <a name="other-ways-to-manage-spoofing-and-phishing-with-office-365"></a>Andere Methoden zum Verwalten von Spoofing und Phishing mit Office 365
<a name="Managespooflist"> </a>

Sie sollten sich sorgfältig mit Spoofing und Phishing-Schutz bemühen. Im folgenden finden Sie ähnliche Möglichkeiten zum Überprüfen von Absendern, die Ihre Domäne Spoofing und dazu beitragen, dass Sie Ihre Organisation nicht schädigen:
  
- Überprüfen Sie den Bericht zum Spoofing-e-Mail-Exchange Online Schutz als Teil Ihrer Routine. Sie können diesen Bericht häufig verwenden, um gefälschte Absender anzuzeigen und zu verwalten. Weitere Informationen finden Sie unter **Spoof-e-Mail-Bericht** in [use Mail Protection Reports in Office 365, um Daten über Schadsoftware, Spam und Regel Erkennungen anzuzeigen](https://technet.microsoft.com/library/dn500744%28v=exchg.150%29.aspx).
    
Für fortgeschrittene Office 365 Administratoren können Sie diese Prüfungen auch ausführen:
    
    
- Überprüfen Sie die SPF-Konfiguration (Sender Policy Framework). Eine kurze Einführung in SPF und seine schnelle Konfiguration finden Sie unter [Einrichten von SPF in Office 365 zur Verhinderung von Spoofing](https://technet.microsoft.com/library/dn789058%28v=exchg.150%29.aspx). Ausführlichere Informationen zur Verwendung von SPF durch Office 365 oder zur Problembehandlung oder zu nicht standardmäßigen Bereitstellungen, z. B. Hybridbereitstellungen, finden Sie unter [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](https://technet.microsoft.com/library/mt712724%28v=exchg.150%29.aspx).
    
- Überprüfen Sie Ihre DomainKeys Identified Mail (DKIM)-Konfiguration. Sie sollten DKIM zusätzlich zu SPF und DMARC verwenden, um zu verhindern, dass Spoofers Nachrichten senden, die aussehen, als würden sie von Ihrer Domäne stammen. Mit DKIM können Sie E-Mail-Nachrichten in der Kopfzeile der Nachricht eine digitale Signatur hinzufügen. Weitere Informationen finden Sie unter [Verwenden von DKIM zum Überprüfen von ausgehenden e-Mails, die von Ihrer Domäne in Office 365 gesendet wurden](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx).
    
- Überprüfen Sie die Konfiguration der domänenbasierten Nachrichtenauthentifizierung, Berichterstellung und Konformität (DMARC). Die Implementierung von DMARC zusammen mit SPF und DKIM bietet zusätzlichen Schutz vor Spoofing- und Phishing-E-Mails. DMARC unterstützt die E-Mail-Systeme der Empfänger bei der Behandlung von Nachrichten, die von Ihrer Domäne gesendet wurden, jedoch die SPF- oder DKIM-Prüfungen nicht bestanden haben. Weitere Informationen finden Sie unter [Verwenden von DMARC zum Überprüfen von e-Mails in Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).
    
- Verwenden Sie das Cmdlet [Get-PhishFilterPolicy](https://technet.microsoft.com/library/mt735158%28v=exchg.160%29.aspx) Windows PowerShell, um detaillierte Daten zu gefälschten Absendern zu sammeln, Zulassungs-und Sperrlisten zu generieren und Ihnen zu helfen, zu bestimmen, wie Sie umfassendere SPF-, DKIM-und DMARC-DNS-Einträge generieren, ohne dass ihre legitimen e-Mails in externen Spamfiltern erfasst werden. Weitere Informationen finden Sie unter [Funktionsweise des Antispoofing-Schutzes in Office 365](https://blogs.msdn.microsoft.com/tzink/2016/02/23/how-antispoofing-protection-works-in-office-365/).
    

