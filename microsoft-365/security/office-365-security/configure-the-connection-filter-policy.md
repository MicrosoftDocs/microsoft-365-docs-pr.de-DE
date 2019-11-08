---
title: Konfigurieren der Verbindungsfilter Richtlinie, Zulassungsliste, Sperrliste
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
description: Um sicherzustellen, dass e-Mails, die von vertrauenswürdigen Personen gesendet werden, nicht blockiert werden, können Sie die Verbindungsfilter Richtlinie verwenden, um eine Zulassungsliste (auch als Liste sicherer Absender bezeichnet) von IP-Adressen zu erstellen, denen Sie vertrauen. Sie können auch eine Liste blockierter Absender erstellen.
ms.openlocfilehash: 541960ce5339e1334cdc61e1f88bff9be48fe2bd
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "38032430"
---
# <a name="configure-the-connection-filter-policy"></a>Konfigurieren der Verbindungsfilterrichtlinie

Die meisten von uns haben Freunde und Geschäftspartnern, denen wir vertrauen. Es kann ärgerlich sein, E-Mail dieser Absender in Ihrem Junk-E-Mail-Ordner zu finden oder festzustellen, dass sie vom Spamfilter gänzlich blockiert wurden. Wenn Sie sicherstellen möchten, dass von diesen vertrauenswürdigen Absendern gesendete E-Mail nicht blockiert wird, können Sie die Verbindungsfilterrichtlinie zum Erstellen einer Zulassungsliste (bzw. „Liste sicherer Absender") mit vertrauenswürdigen IP-Adressen nutzen. Sie können auch eine Liste blockierter Absender mit IP-Adressen (zumeist von Spammern) erstellen, von denen Sie nie wieder E-Mail-Nachrichten empfangen möchten.
  
- Beachten Sie beim Nachdenken über *[Zulassungslisten](create-safe-sender-lists-in-office-365.md)*, dass sich Verbindungsfilter Richtlinien mit den vom Filter *zugelassenen vertrauenswürdigen Konten* befassen. Dies geschieht im Interesse einer genaueren Filterung weniger vertrauenswürdiger oder nicht vertrauenswürdiger e-Mail-Nachrichten, während Sie Ihre Anforderungen beibehalten. In einer Liste der zugelassenen Verbindungsfilter Richtlinie geht es um das Filtern nach den wenigen vertrauenswürdigen IPS aus einem weitaus größeren Konto-und IPS-Pool und um sicherzustellen, dass Ihre vertrauenswürdigen e-Mail-Adressen leichter zugänglich sind

- Eine Verbindungsfilter Richtlinie zum Erstellen einer Sperrliste kann stattdessen als Abfangen von less-oder nicht vertrauenswürdigen Konten im Filter betrachtet werden.

 Weitere Antispameinstellungen, die für die gesamte Organisation gelten, finden Sie unter [Sicherstellen, dass eine Nachricht nicht als Spam gekennzeichnet wird](https://go.microsoft.com/fwlink/p/?LinkId=534224) oder [Blockieren von E-Mail-Spam mit dem Office 365-Spamfilter zum Verhindern von falsch negativen Ergebnissen](https://go.microsoft.com/fwlink/p/?LinkId=534225). Diese sind hilfreich, wenn Sie über die Steuerung auf Administratorebene verfügen und wenn Sie falsch positive Ergebnisse oder falsch negative Ergebnisse vermeiden möchten.

> [!TIP]
> Möglicherweise möchten Sie das Erstellen von [Listen für zugelassene (oder sichere Absender)](create-safe-sender-lists-in-office-365.md) und [Blockieren von Listen](create-block-sender-lists-in-office-365.md)anhalten und lesen.
  
Im folgenden Video wird die Vorgehensweise zur Konfiguration der Verbindungsfilterrichtlinie gezeigt:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/b2f5bea3-e1a7-44b3-b7e2-07fac0d0ca40?autoplay=false]
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Geschätzte Zeit bis zum Abschließen des Vorgangs: 15 Minuten

- Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Informationen zu den von Ihnen benötigten Berechtigungen finden Sie unter "Anti-Spam" im Thema [Feature Permissions in Exchange Online](https://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) .

- Um die IP-Adresse des Absenders zu ermitteln, dessen Nachrichten Sie zulassen oder blockieren möchten, können Sie die Internetkopfzeile der Nachricht prüfen. Suchen Sie, wie in [Antispam-Nachrichtenkopfzeilen](anti-spam-message-headers.md) beschrieben, nach der CIP-Kopfzeile. Informationen zum Anzeigen einer Nachrichtenkopfzeile in verschiedenen e-Mail-Clients finden Sie unter [Message Header Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=306583).

- E-Mails, die von einer IP-Adresse aus der IP-Sperrliste gesendet werden, werden abgelehnt, nicht als Spam gekennzeichnet, und es werden keine weiteren Filter angewendet.

- Das folgende Verbindungsfilterverfahren kann auch über Remote-PowerShell erfolgen. Mit dem Cmdlet [Get-HostedConnectionFilterPolicy](https://technet.microsoft.com/library/bd751db2-3f26-495b-8e5a-4fcab53b17fd.aspx) können Sie Ihre Einstellungen überprüfen und mit dem Cmdlet [Set-HostedConnectionFilterPolicy](https://technet.microsoft.com/library/ccb5731b-3fca-4d69-a91f-5049ea963fac.aspx) Ihre Einstellungen für die Verbindungsfilterrichtlinie bearbeiten. Wie Sie mit Windows PowerShell eine Verbindung mit Exchange Online Protection herstellen, können Sie unter [Verbinden mit Exchange Online Protection mithilfe von Remote-PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290) nachlesen. Wie Sie mit Windows PowerShell eine Verbindung mit Exchange Online herstellen, können Sie unter [Mit Exchange Online PowerShell verbinden](https://go.microsoft.com/fwlink/p/?linkid=396554) nachlesen.

## <a name="use-the-eac-to-edit-the-default-connection-filter-policy"></a>Bearbeiten der Standardrichtlinie für Verbindungsfilter mithilfe der Exchange-Verwaltungskonsole

Durch Bearbeiten der Verbindungsfilterrichtlinie in der Exchange-Verwaltungskonsole können Sie eine IP-Zulassungs- bzw. -Sperrliste erstellen. Die Einstellungen für die Verbindungsfilterrichtlinie werden nur auf eingehende Nachrichten angewendet.
  
1. Navigieren Sie in der Exchange-Verwaltungskonsole zu **Schutz** \> **Verbindungsfilter**, und doppelklicken Sie dann auf die Standardrichtlinie.

2. Klicken Sie auf die Menüoption **Verbindungsfilterung**, und erstellen Sie dann die gewünschten Listen: eine IP-Zulassungsliste, eine IP-Sperrliste oder beides.

   Klicken Sie zum Erstellen dieser Listen auf ![Hinzufügen (Symbol)](../media/ITPro-EAC-AddIcon.gif). Geben Sie im folgenden Dialogfeld die IP-Adressen oder den IP-Adressbereich an, und klicken Sie dann auf **OK**. Wiederholen Sie diesen Vorgang, um weitere Adressen hinzuzufügen. (Sie können IP-Adressen auch bearbeiten oder entfernen, nachdem sie hinzugefügt wurden.)

   Geben Sie IPv4-IP-Adressen im Format nnn. nnn. nnn. nnn an, wobei nnn eine Zahl zwischen 0 und 255 ist. Sie können auch CIDR-Bereiche (Classless Inter-Domain Routing) im Format nnn.nnn.nnn.nnn/rr angeben, wobei rr eine Zahl von 24 bis 32 ist. Um Bereiche außerhalb des Bereichs von 24 bis 32 anzugeben, lesen Sie den nächsten Abschnitt, [Weitere Überlegungen beim Konfigurieren von IP-Zulassungslisten](#additional-considerations-when-configuring-ip-allow-lists).

   > [!NOTE]
   > Wenn Sie beide Listen eine IP-Adresse hinzufügen, werden von dieser IP-Adresse gesendete e-Mails zugelassen. <br/><br/> Sie können maximal 1273 Einträge angeben, wobei ein Eintrag einer einzelnen IP-Adresse oder einem CIDR-Bereich von IP-Adressen von /24 bis /32 entspricht.<br/><br/> Wenn Sie TLS-verschlüsselte Nachrichten senden, werden IPv6-Adressen und-Adressbereiche nicht unterstützt.
  
3. Aktivieren Sie optional das Kontrollkästchen **Liste sicherer Adressen aktivieren**, um zu verhindern, dass Sie E-Mail von bestimmten bekannten Absendern verpassen. Wie? Microsoft hat verschiedene Quellen von Drittanbietern mit vertrauenswürdigen Absendern abonniert. Mithilfe dieser sicheren Liste sorgen Sie dafür, dass diese vertrauenswürdigen Absender nicht versehentlich als Spammer gekennzeichnet werden. Es wird empfohlen, diese Option auszuwählen, da Sie die Anzahl falsch positiver e-Mail-Nachrichten (gute e-Mails, die als Spam klassifiziert werden) reduzieren sollte. 

4. Klicken Sie auf **Speichern**. Im Bereich auf der rechten Seite wird eine Zusammenfassung der Standardrichtlinieneinstellungen angezeigt.

## <a name="additional-considerations-when-configuring-ip-allow-lists"></a>Weitere Überlegungen zum Konfigurieren von Listen zugelassener IP-Adressen

Folgende Überlegungen sollten Sie anstellen, wenn Sie eine Liste zugelassener IP-Adressen konfigurieren möchten.
  
### <a name="specifying-a-cidr-range-that-falls-outside-of-the-recommended-range"></a>Angeben eines CIDR-Bereichs, der außerhalb des empfohlenen Bereichs liegt

Um einen CIDR-IP-Adressbereich von/1 bis/23 anzugeben, müssen Sie eine e-Mail-Fluss Regel erstellen, die auf dem IP-Adressbereich arbeitet, der die SCL-Bewertung (Spam Confidence Level) zur **Umgehung der Spamfilterung** festlegt (d. h., alle Nachrichten, die in diesem IP-Adressbereich empfangen werden, werden auf "nicht Spam" festgelegt Wenn jedoch eine dieser IP-Adressen in einer der proprietären Sperrlisten von Microsoft oder in einem unserer Sperrlisten von Drittanbietern angezeigt wird, werden diese Nachrichten weiterhin blockiert. Es wird daher dringend empfohlen, den IP-Adressbereich/24 to/32 zu verwenden.
  
Führen Sie die folgenden Schritte aus, um diese e-Mail-Fluss Regel zu erstellen.
  
1. Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.

2. Klicken Sie auf ![Hinzufügen (Symbol)](../media/ITPro-EAC-AddIcon.gif) und wählen Sie dann **Neue Regel erstellen** aus.

3. Benennen Sie die Regel, und klicken Sie dann auf **Weitere Optionen**.

4. Wählen Sie unter **Diese Regel wird ausgeführt, wenn** die Option **Absender**, und wählen Sie dann **IP-Adresse ist in keinem dieser Bereiche oder stimmt mit keinem Bereich völlig überein**.

5. Geben Sie in die IP- **Adressen angeben**den IP-Adressbereich ein, klicken](../media/ITPro-EAC-AddIcon.gif)Sie auf Add-Symbol **Hinzufügen** ![, und klicken Sie dann auf **OK**.

6. Legen Sie unter **Gehen Sie folgendermaßen vor:** die Aktion fest, indem Sie erst **Nachrichteneigenschaften ändern** wählen und dann die **SCL-Bewertung (Spam Confidence Level) festlegen**. Wählen Sie im Feld **SCL angeben** die Option **Spamfilter umgehen**, und klicken Sie auf **OK**.

7. Auf Wunsch können Sie unter anderem auch Einstellungen zur Überwachung der Regel, zum Testen der Regel und zum Aktivieren der Regel in einem bestimmten Zeitraum vornehmen. Wir empfehlen, die Regel über eine bestimmte Zeit zu testen, bevor Sie sie erzwingen. [Verfahren für Nachrichtenfluss Regeln in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures) enthält weitere Informationen zu diesen Auswahlmöglichkeiten.

8. Klicken Sie auf **Speichern** , um die Regel zu speichern. Die Regel wird in der Liste der Regeln angezeigt.

Nachdem Sie die Regel erstellt und erzwungen haben, wird die Spamfilterung für den angegebenen IP-Adressbereich von dem Dienst umgangen.

### <a name="scoping-an-ip-allow-list-exception-for-a-specific-domain"></a>Bereichsfestlegung für Ausnahmen von einer Liste der zugelassenen IP-Adressen einer bestimmten Domäne

Sie sollten die IP-Adresse (oder IP-Adressbereiche) für alle Ihre Domänen, die Sie als sicher einschätzen, der Liste der zugelassenen IP-Adressen hinzufügen. Wenn Ihr IP-Zulassungslisten Eintrag jedoch nicht auf alle Ihre Domänen angewendet werden soll, können Sie eine e-Mail-Fluss Regel (auch als Transportregel bezeichnet) erstellen, die bestimmte Domänen außer Kraft tritt.
  
Angenommen, Sie verfügen über drei Domänen: ContosoA.com, ContosoB.com und ContosoC.com, und Sie möchten die IP-Adresse hinzufügen (aus Gründen der Einfachheit, Let es Use 1.2.3.4) und die Filterung nur für Domänen ContosoB.com überspringen. Sie würden eine IP-Zulassungsliste für 1.2.3.4 erstellen, mit der die SCL-Bewertung (Spam Confidence Level) auf-1 (d. h., dass Sie als nicht-Spam klassifiziert ist) für alle Domänen festgelegt wird. Anschließend können Sie eine e-Mail-Fluss Regel erstellen, mit der die SCL-Bewertung für alle Domänen außer ContosoB.com auf 0 festgelegt wird. Dies führt dazu, dass die Nachricht für alle der IP-Adresse zugeordneten Domänen mit Ausnahme von ContosoB.com, die als Ausnahme in der Regel aufgeführt sind, erneut gescannt wird. ContosoB.com hat weiterhin den SCL-Wert von-1, was bedeutet, dass die Filterung übersprungen werden kann, wohingegen ContosoA.com und ContosoC.com über SCLs von 0 verfügen, was bedeutet, dass Sie vom Inhaltsfilter erneut überprüft werden.
  
Führen Sie dazu die folgenden Schritte aus:
  
1. Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.

2. Klicken Sie auf ![Hinzufügen (Symbol)](../media/ITPro-EAC-AddIcon.gif) und wählen Sie dann **Neue Regel erstellen** aus.

3. Benennen Sie die Regel, und klicken Sie dann auf **Weitere Optionen**.

4. Wählen Sie unter **Diese Regel wird ausgeführt, wenn** die Option **Absender**, und wählen Sie dann **IP-Adresse ist in keinem dieser Bereiche oder stimmt mit keinem Bereich völlig überein**.

5. Geben Sie im Feld **IP-Adressen angeben** die IP-Adresse oder den IP-Adressbereich an, den Sie in die IP-Zulassungs](../media/ITPro-EAC-AddIcon.gif)Liste eingegeben haben, klicken Sie auf Add-Symbol **Hinzufügen** ![, und klicken Sie dann auf **OK**.

6. Legen **Sie untergehen Sie folgen**dermaßen vor fest, indem Sie die Aktion **Nachrichteneigenschaften ändern** auswählen und dann **die SCL-Bewertung (Spam Confidence Level) festlegen**. Wählen Sie im Feld **SCL angeben** die Option **0**aus, und klicken Sie auf **OK**.

7. Klicken Sie auf **Ausnahme hinzufügen**, und wählen Sie unter **außer wenn**, **den Absender** aus, und wählen Sie **Domäne ist**.

8. Geben Sie in das Feld **Domäne angeben** die Domäne ein, für die Sie die Spamfilterung umgehen möchten, beispielsweise **contosob.com**. Klicken Sie auf Add](../media/ITPro-EAC-AddIcon.gif) -Symbol **Hinzufügen** ![, um es in die Liste der Ausdrücke zu versetzen. Wiederholen Sie diesen Schritt, falls Sie zusätzliche Domänen als Ausnahmen hinzufügen möchten, und klicken Sie abschließend auf **OK**. 

9. Auf Wunsch können Sie unter anderem auch Einstellungen zur Überwachung der Regel, zum Testen der Regel und zum Aktivieren der Regel in einem bestimmten Zeitraum vornehmen. Wir empfehlen, die Regel über eine bestimmte Zeit zu testen, bevor Sie sie erzwingen. [Verfahren für Nachrichtenfluss Regeln in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures) enthält weitere Informationen zu diesen Auswahlmöglichkeiten.

10. Klicken Sie auf **Speichern** , um die Regel zu speichern. Die Regel wird in der Liste der Regeln angezeigt.

Nach Erstellen und Erzwingen der Regel wird der Spamfilter für die von Ihnen angegebene IP-Adresse bzw. IP-Adressbereich nur für die von Ihnen eingegebene Domänenausnahme umgangen.

### <a name="scenarios-where-allowed-ip-addresses-are-still-filtered"></a>Szenarien, in denen zulässige IP-Adressen noch gefiltert werden

Nachrichten von zulässigen IP-Adressen, die Sie in Verbindungsfilter Richtlinien konfiguriert haben, unterliegenweiterhin Spamfilterung in den folgenden Szenarien:

- Die Quell-IP-Adresse in ihrer Verbindungsfilter Richtlinie wird auch in einem lokalen, IP-basierten eingehenden Connector in *einem beliebigen* Mandanten (nennen wir diesen Mandanten a) **und** dem Mandanten a und dem Exchange Online Schutz Server, der zuerst die Nachricht in Office 365 findet, in der gleichen Active Directory Gesamtstruktur in den Microsoft-Datencentern aufgeführt ist, konfiguriert. In diesem Szenario wird **IPV: Cal** zu den [Antispam-Nachrichtenkopf Zeilen](anti-spam-message-headers.md) der Nachricht hinzugefügt (womit die Nachricht umgangen wird Spamfilterung), aber die Nachricht ist weiterhin Gegenstand der Spamfilterung.

- Ihr Mandant (in dem Sie die Verbindungsfilter Richtlinie konfiguriert haben) und der Exchange Online Schutz Server, der die Nachricht zuerst in Office 365 trifft, in denen sich beide in unterschiedlichen Active Directory Gesamtstrukturen in den Microsoft-Rechenzentren befinden. In diesem Szenario wird **IPV: Cal** nicht den Nachrichtenkopfzeilen hinzugefügt, sodass die Nachricht weiterhin der Spamfilterung unterliegt.

Wenn Sie auf eines dieser Szenarien stoßen, können Sie eine Nachrichtenfluss Regel in der Exchange-Verwaltungskonsole mit (mindestens) den folgenden Einstellungen erstellen, um sicherzustellen, dass Nachrichten von der IP-Adresse oder Adressen die Spamfilterung umgehen:

- Regelbedingung: **diese Regel anwenden, wenn** \> sich die IP-Adresse **des Absenders** \> **in einem dieser Bereiche befindet oder genau übereinstimmt** \> (Ihre IP-Adresse oder Adressen).

- Regelaktion: **Ändern der Nachrichteneigenschaften** \> **legen Sie die Spam Confidence Level (SCL) Bypass-** \> **Spamfilterung**fest.

Dies ist im Wesentlichen die gleiche Regel Erstellungs Prozedur aus dem vorherigen [Scoping einer IP-Zulassungslisten Ausnahme für einen bestimmten Domänen](#scoping-an-ip-allow-list-exception-for-a-specific-domain) Abschnitt.

## <a name="new-to-office-365"></a>Neu bei Office 365?

||
|:-----|
|![Das Kurzsymbol für LinkedIn Learning](../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Neu bei Office 365?** Entdecken Sie die kostenlosen Videokurse für **Office 365 admins and IT pros**, präsentiert von LinkedIn Learning.|

## <a name="for-more-information"></a>Weitere Informationen

[Listen sicherer und blockierter Absender in Exchange Online](safe-sender-and-blocked-sender-lists-faq.md)
  
[Konfigurieren von Spamfilterrichtlinien](configure-your-spam-filter-policies.md)
  
[Konfigurieren der Richtlinie für ausgehende Spamnachrichten](configure-the-outbound-spam-policy.md)
  
[So können Sie dazu beitragen, dass eine Nachricht nicht als Spam gekennzeichnet wird](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[Blockieren von E-Mail-Spam mit dem Office 365-Spamfilter zur Vermeidung von falsch negativen Einträgen](https://go.microsoft.com/fwlink/p/?LinkId=534225)
