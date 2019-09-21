---
title: Finden und Freigeben von Nachrichten in Quarantäne als Administrator
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 06/16/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ab95bf17-bb09-4dd1-9990-ddd02ddecf05
ms.collection:
- M365-security-compliance
description: In diesem Thema wird beschrieben, wie Administratoren von Exchange Online und Exchange Online Protection (EOP) isolierte Nachrichten finden, freigeben und Berichte dazu erstellen, die sich im Exchange Admin Center (EAC).
ms.openlocfilehash: 479766e573f5b7fefc334d70c7f44a664944dc16
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081282"
---
# <a name="find-and-release-quarantined-messages-as-an-administrator"></a>Finden und Freigeben von Nachrichten in Quarantäne als Administrator

In diesem Thema wird beschrieben, wie Administratoren von Exchange Online und Exchange Online Protection (EOP) isolierte Nachrichten finden, freigeben und Berichte dazu erstellen, die sich im Exchange Admin Center (EAC). Office 365 leitet Nachrichten in Quarantäne, da Sie entweder als Spam identifiziert wurden oder mit einer Nachrichtenfluss Regel (auch als Transportregel bezeichnet) übereinstimmten. 
  
Verwenden Sie das &amp; Security Compliance Center anstelle der Exchange-Verwaltungskonsole, um diese Aufgaben auszuführen und um Nachrichten anzuzeigen und zu bearbeiten, die an die Quarantäne gesendet wurden, da Sie Schadsoftware enthalten. Weitere Informationen finden Sie unter [Quarantäne für e-Mail-Nachrichten in Office 365](https://support.office.com/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b).
  
Isolierte Nachrichten werden im EAC auf der Seite **Quarantäne** aufgeführt. Standardmäßig sind die Nachrichten aufsteigend nach Alter im Feld **EMPFANGEN** sortiert. Auch die Werte **ABSENDER**, **BETREFF** und **LÄUFT AB** werden für jede Nachricht aufgelistet. Sie können nach jedem dieser Felder sortieren, indem Sie auf ihre Kopfzeile klicken. Durch ein zweites Klicken auf eine Spaltenüberschrift wird die Sortierreihenfolge umgekehrt. Auf der Seite **Quarantäne** können maximal 500 Nachrichten angezeigt werden. 
  
Sie können eine Liste aller isolierten Nachrichten anzeigen oder durch Angabe von Filterkriterien nach bestimmten Nachrichten suchen (durch Filtern können Sie auch die Anzahl der Ergebnisse verringern, wenn Sie mehr als 500 Nachrichten haben). Nachdem Sie eine bestimmte isolierte Nachricht gesucht und gefunden haben, können Sie nähere Informationen zur Nachricht anzeigen. Des Weiteren können Sie Folgendes:
  
- Sie können die Nachricht auch für einen oder mehrere Empfänger freigeben und optional als falsch positives Ergebnis (kein Junk) dem Microsoft-Spamanalyseteam melden, das die Nachricht bewertet und analysiert. Abhängig vom Ergebnis der Analyse werden die Filterregeln für Spaminhalte des Diensts angepasst, damit die Nachricht zugestellt werden kann.
    
- Sie können die Nachricht freigeben und alle zukünftigen Nachrichten von diesem Absender zulassen.
    
## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?
<a name="sectionSection0"> </a>

- Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Informationen zu den von Ihnen benötigten Berechtigungen finden Sie unter "Quarantäne" in den [Features Berechtigungen in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) Thema. 
    
- Sie können auf der Seite **Quarantäne** mehrere Nachrichten auf einmal freizugeben oder melden. Alternativ können Sie dazu ein Windows PowerShellRemoteskript erstellen. Verwenden Sie das [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx)-Cmdlet, um nach Nachrichten zu suchen, und das [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx)-Cmdlet, um sie freizugeben. 
    
- Informationen zu Tastenkombinationen, die möglicherweise für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen für das Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).
    
> [!TIP]
> Liegt ein Problem vor? Bitten Sie in den Exchange-Foren um Hilfe. Besuchen Sie die Foren unter [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542) oder [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351). 
  
## <a name="use-advanced-search-to-filter-and-locate-quarantined-messages"></a>Filtern und Auffinden von Nachrichten in Quarantäne anhand der erweiterten Suche
<a name="BKMK_UseAdvancedSearchtoFilterMessages"> </a>

Im Exchange Admin Center (EAC) können Sie mithilfe der erweiterten Suche anhand mehrerer verschiedener Bedingungen nach Elementen in Quarantäne suchen. Sie können diese Bedingungen separat oder in Kombination miteinander verwenden. Die Suche gibt eine Liste von Nachrichten zurück, die mit all Ihren Filterkriterien übereinstimmen.
  
1. Navigieren Sie im Exchange Admin Center zu **Schutz** \> **Quarantäne**, und klicken Sie dann auf **Erweiterte Suche**.
    
2. Wählen Sie im Fenster **Erweiterte Suche** eine beliebige Kombination der folgenden Felder aus. Aktivieren Sie das zugehörige Kontrollkästchen, um eine Bedingung auszuwählen. Platzhalter werden nicht unterstützt. 
    
1. **Nachrichten-ID** Anhand dieses Parameters können Sie eine gezielte Suche nach einer spezifischen Nachricht durchführen. Wenn eine bestimmte Nachricht beispielsweise von einem Benutzer in Ihrer Organisation gesendet wird oder für diesen bestimmt ist, aber ihr Ziel nicht erreicht, können Sie mit der Nachrichtenablaufverfolgung nach der Nachricht suchen. Weitere Informationen finden Sie unter [Ausführen einer Nachrichtenablaufverfolgung und Anzeigen der Ergebnisse](http://technet.microsoft.com/library/74a9fc59-7e0e-4832-baf9-2a86418b0079.aspx). Wenn Sie feststellen, dass die Nachricht in Quarantäne gesendet wurde, möglicherweise aufgrund der Übereinstimmung mit einer Regel oder ihrer Identifizierung als Spam, können Sie diese Nachricht einfach in der Quarantäne finden, indem Sie ihre Nachrichten-ID angeben. Dabei müssen Sie die vollständige Zeichenfolge der Nachrichten-ID angeben. Hierzu können auch spitze Klammern (\<\>) gehören. 
    
2. **E-Mail-Adresse des Absenders** Geben Sie die E-Mail-Adresse der Person an, die die Nachricht gesendet hat. 
    
3. **E-Mail-Adresse des Empfängers** Geben Sie die E-Mail-Adresse der Person an, die die Nachricht empfangen soll. 
    
4. **Betreff** Geben Sie den Betreffzeilentext der Nachricht an. 
    
5. **Empfangen** Sie können wählen, dass die Nachricht innerhalb der letzten 24 Stunden ( **Heute**) in der Quarantäne eingegangen ist, innerhalb der letzten 48 Stunden ( **Letzte 2 Tage**), innerhalb der letzten Woche ( **Letzte 7 Tage**), oder Sie können einen individuellen Zeitraum auswählen, während dem die Nachricht in der Quarantäne eingegangen ist. 
    
6. **Läuft ab** Sie können wählen, dass die Nachricht innerhalb der nächsten 24 Stunden ( **Heute**) aus der Quarantäne gelöscht wird, innerhalb der nächsten 48 Stunden ( **Nächste 2 Tage**), innerhalb der nächsten Woche ( **Nächste 7 Tage**), oder Sie können einen individuellen Zeitraum auswählen, während dem die Nachricht aus der Quarantäne gelöscht wird.
    
    > [!IMPORTANT]
    > Standardmäßig werden Spam isolierte Nachrichten 15 Tage lang in Quarantäne aufbewahrt, während in Quarantäne befindliche Nachrichten, die einer e-Mail-Fluss Regel entsprechen, für 7 Tage in der Quarantäne aufbewahrt werden. Nach dieser Zeitspanne Office 365 die Nachrichten gelöscht und können nicht abgerufen werden. Der Aufbewahrungszeitraum für isolierte Nachrichten, die mit einer e-Mail-Fluss Regel übereinstimmen, kann nicht konfiguriert werden. Der Aufbewahrungszeitraum für Nachrichten mit Spamquarantäne kann jedoch über die Einstellung **Spam für (Tage)** in den Inhaltsfilter Richtlinien beibehalten werden. Weitere Informationen finden Sie unter [Konfigurieren von Spamfilterrichtlinien](configure-your-spam-filter-policies.md). 
  
7. **Geben** Sie Sie können angeben, ob nach isolierten Nachrichten gesucht werden soll, die als **Spam**identifiziert wurden, oder ob nach Nachrichten gesucht werden soll, die mit einer Nachrichtenfluss Regel übereinstimmen (**Transport Regel**).
    
3. Klicken Sie auf **OK**, um die erweiterte Suche zu starten. 
    
    > [!NOTE]
    > Um Ihre Suchkriterien zu löschen und alle Nachrichten in der Quarantäne anzuzeigen, deaktivieren Sie im Fenster **Erweiterte Suche** alle Kontrollkästchen, und klicken Sie dann auf **OK**. 
  
Dann wird nach Nachrichten gesucht, und die Ergebnisse, die den angegebenen Kriterien entsprechen, werden an der Benutzeroberfläche angezeigt. Maximal 500 Nachrichten können in der Exchange-Verwaltungskonsole angezeigt werden. 
  
## <a name="view-details-about-a-specific-quarantined-message"></a>Anzeigen von Details zu einer bestimmten Quarantänenachricht
<a name="BKMK_ViewDetailsAboutaSpecificQuarantinedMessage"> </a>

Nachdem Sie auf der Seite **Quarantäne** eine bestimmte isolierte Nachricht gefunden haben, können Sie Details zu dieser anzeigen. 
  
1. Wenn Sie auf der Seite **Quarantäne** eine bestimmte Nachricht auswählen, wird im Detailbereich auf der rechten Seite des Bildschirms eine Zusammenfassung der Eigenschaften dieser Nachricht angezeigt. 
    
    Für **Nachrichtenstatus** sind folgende Werte möglich: 
    
  - **Geben** Sie Gibt an, ob die Nachricht als **Spam** identifiziert wurde oder mit einer Nachrichtenfluss Regel übereinstimmt (**Transport Regel**).
    
  - **Läuft ab** Das Datum, an dem die Nachricht aus der Quarantäne gelöscht wird. 
    
    Für **Nachrichtendetails** sind folgende Werte möglich: 
    
  - **Absender** Die E-Mail-Adresse der Person, die die Nachricht gesendet hat. 
    
  - **Betreff** Der Betreffzeilentext der Nachricht. 
    
  - **Empfangen** Das Datum, an dem die Nachricht von der Quarantäne empfangen wurde. 
    
  - **Größe** Die Größe der Nachricht in KB, oder, falls die Größe 999 KB überschreitet, in MB. 
    
  - **Nachrichtenkopfzeile anzeigen** Klicken Sie auf diesen Link, um das Dialogfeld **Nachrichtenkopfzeile** zu öffnen, das den Text der Nachrichtenkopfzeile anzeigt. Sie können den Text der Nachrichtenkopfzeile auch in die Zwischenablage kopieren und in die [Nachrichtenkopfanalyse](https://testconnectivity.microsoft.com/?tabid=mha) einfügen. Klicken Sie im Tool für de Nachrichtenkopfanalyse auf **Kopfzeilen analysieren**, um Informationen zur Kopfzeile abzurufen. 
    
    > [!TIP]
    > Informationen zu spezifischen, vom Dienst eingefügten Antispam-Nachrichtenkopfzeilenfeldern finden Sie unter [Antispam-Nachrichtenkopfzeilen](anti-spam-message-headers.md). 
  
  - **Vorschau für E-Mail** Klicken Sie auf diesen Link, um den Text der Nachricht zu prüfen. 
    
2. Wenn Sie auf eine Quarantänenachricht doppelklicken, wird das Fenster **Quarantined message** (Quarantänenachricht) geöffnet, und die folgenden Informationen werden angezeigt: 
    
  - **Freigegeben für** Eine Liste aller E-Mail-Adressen, für die die Nachricht freigegeben wurde, falls vorhanden. 
    
  - **Noch nicht freigegeben für** Eine Liste aller E-Mail-Adressen, für die die Nachricht nicht freigegeben wurde, falls vorhanden. Sie können auf den Link **Freigeben für** klicken, um die Nachricht freizugeben; weitere Informationen zum Freigeben einer Nachricht finden Sie im nächsten Abschnitt. 
    
  - **Nachrichten-ID** Die Internetnachrichten-ID (auch als Client-ID bezeichnet), die sich in den Kopfzeilen der Nachricht befindet. 
    
    Klicken Sie auf **Schließen**, um zum Hauptfenster für die Quarantäne zurückzukehren. 
    
## <a name="release-messages-from-quarantine"></a>Freigeben von Nachrichten aus der Quarantäne
<a name="sectionSection3"> </a>

Wenn Sie Nachrichten für Empfänger freigeben möchten, stehen dazu folgende Möglichkeiten zur Verfügung:
  
- [Freigeben einer isolierten Nachricht und Zulassen aller zukünftigen Nachrichten vom Absender](find-and-release-quarantined-messages-as-an-administrator.md#Releasequarantinedmessageallowfuturemessagesfromsender)
    
- [Freigeben einer isolierten Nachricht für bestimmte Empfänger, ohne sie als falsch positives Ergebnis zu melden](find-and-release-quarantined-messages-as-an-administrator.md#Releasequarantinedmessagetospecificrecipientswithoutreportingasfalsepositive)
    
- [Freigeben einer oder mehrerer isolierten Nachrichten für alle Empfänger](find-and-release-quarantined-messages-as-an-administrator.md#Releaseoneormorequarantinedmessagestoallrecipients)
    
- [Freigeben einer oder mehrerer isolierten Nachrichten für alle Empfänger und Melden der Nachrichten als falsch positive Ergebnisse](find-and-release-quarantined-messages-as-an-administrator.md#Releaseoneormorequarantinedmessagestoallrecipientsandreportfalsepositives)
    
### <a name="release-a-quarantined-message-and-allow-future-messages-from-the-sender"></a>Freigeben einer isolierten Nachricht und Zulassen aller zukünftigen Nachrichten vom Absender
<a name="Releasequarantinedmessageallowfuturemessagesfromsender"> </a>

1. Navigieren Sie im Exchange Admin Center zu **Schutz** \> **Quarantäne**.
    
2. Klicken Sie auf eine Nachricht, um Sie auszuwählen, und klicken Sie dann auf das Symbol **Nachricht freigeben** wie im folgenden Screenshot dargestellt. 
  
![Zeigt die Quarantäneseite an, auf der das Symbol zum Freigeben von Nachrichten hervorgehoben und die Freigabeoptionen angezeigt werden](../media/36ee081f-3e30-40c9-8ce3-240cee1970cc.png)
  
Wählen Sie **Ausgewählte Nachricht freigeben und Absender zulassen** aus der Dropdownliste aus. 
    
3. Das Dialogfeld **Nachricht freizugeben und Absender zulassen** wird geöffnet. Optional können Sie die Nachricht an Microsoft melden und dann auf **Freigeben und zulassen** klicken. Die Nachricht wird für alle Empfänger freigegeben, an die sie gerichtet ist, und alle zukünftigen Nachrichten von diesem Absender werden zugelassen. Wenn diese Nachricht jedoch aufgrund einer Nachrichtenfluss Regel oder eines blockierten Absenders unter Quarantäne gestellt wurde, wird der Absender weiterhin für zukünftige Nachrichten blockiert. 
    
### <a name="release-a-quarantined-message-to-specific-recipients-without-reporting-it-as-a-false-positive"></a>Freigeben einer isolierten Nachricht für bestimmte Empfänger, ohne sie als falsch positives Ergebnis zu melden
<a name="Releasequarantinedmessagetospecificrecipientswithoutreportingasfalsepositive"> </a>

1. Navigieren Sie im Exchange Admin Center zu **Schutz** \> **Quarantäne**.
    
2. Wählen Sie eine Nachricht aus, klicken Sie auf das Symbol **Nachricht freigeben**, und wählen Sie dann in der Dropdownliste **Nachricht an bestimmte Empfänger freigeben** aus. 
    
3. Wählen Sie im Dialogfeld **Nachricht freigeben** eine der folgenden Optionen aus: 
    
  - **Nachricht für alle Empfänger freigeben** Beachten Sie beim Auswählen dieser Option, dass die Nachricht nur einmal für denselben Empfänger freigegeben werden kann. Hat ein Empfänger die Nachricht bereits zuvor empfangen, wird sie ihm nicht noch einmal zugestellt. 
    
  - **Nachricht für angegebene Empfänger freigeben** Wählen Sie die Empfänger aus, für die die Nachricht freigegeben werden soll. Da eine Nachricht nur einmal für denselben Empfänger freigegeben werden kann, werden in dieser Liste nur die Empfänger aufgeführt, für die die Nachricht noch freigegeben werden kann. Mehrfachauswahl möglich. Klicken Sie anschließend auf **Hinzufügen**.
    
4. Klicken Sie auf **Freigeben**. 
    
Wenn Sie auf das Symbol **Aktualisieren**![Aktualisieren (Symbol)](../media/ITPro-EAC-RefreshIcon.gif) klicken, um Ihre Daten zu aktualisieren, und dann auf die Nachricht doppelklicken, sollte die Nachricht an die beabsichtigten Empfänger freigegeben werden. 
  
### <a name="release-one-or-more-quarantined-messages-to-all-recipients"></a>Freigeben einer oder mehrerer isolierten Nachrichten für alle Empfänger
<a name="Releaseoneormorequarantinedmessagestoallrecipients"> </a>

1. Navigieren Sie im Exchange Admin Center zu **Schutz** \> **Quarantäne**.
    
2. Klicken Sie auf eine Nachricht, um sie auszuwählen, oder verwenden Sie die UMSCHALTTASTE, um mehrere Nachrichten auszuwählen. Klicken Sie dann auf das Symbol **Nachricht freigeben**. 
    
3. Wählen Sie in der Dropdownliste **Ausgewählte Nachrichten für alle Empfänger freigeben**. 
    
4. Es wird ein Dialogfeld mit einer Warnung geöffnet. Lesen Sie die Warnung, und wählen Sie **Ja**, wenn Sie fortfahren möchten. Beachten Sie beim Auswählen dieser Option, dass die Nachricht nur einmal für denselben Empfänger freigegeben werden kann. Hat ein Empfänger die Nachricht bereits zuvor empfangen, wird sie ihm nicht noch einmal zugestellt. 
    
### <a name="release-one-or-more-quarantined-messages-to-all-recipients-and-report-false-positives"></a>Freigeben einer oder mehrerer isolierten Nachrichten für alle Empfänger und Melden der Nachrichten als falsch positive Ergebnisse
<a name="Releaseoneormorequarantinedmessagestoallrecipientsandreportfalsepositives"> </a>

1. Navigieren Sie im Exchange Admin Center zu **Schutz** \> **Quarantäne**.
    
2. Klicken Sie auf eine Nachricht, um sie auszuwählen, oder verwenden Sie die UMSCHALTTASTE, um mehrere Nachrichten auszuwählen. Klicken Sie dann auf das Symbol **Nachricht freigeben**. 
    
3. Wählen Sie in der Dropdownliste **Ausgewählte Nachrichten freigeben und als falsch positive Ergebnisse melden**. 
    
4. Es wird ein Dialogfeld mit einer Warnung geöffnet. Lesen Sie die Warnung, und wählen Sie **Ja**, wenn Sie fortfahren möchten. Beachten Sie beim Auswählen dieser Option, dass die Nachricht nur einmal für denselben Empfänger freigegeben werden kann. Hat ein Empfänger die Nachricht bereits zuvor empfangen, wird sie ihm nicht noch einmal zugestellt. 
    
     Wenn Sie diese Option auswählen, wird die Nachricht für alle Empfänger freigegeben, die sie noch nicht erhalten haben. Falls es sich um eine Nachricht in der Spamquarantäne handelt, wird sie außerdem dem Microsoft-Spamanalyseteam gemeldet, das die Nachricht bewertet und analysiert. Abhängig vom Ergebnis der Analyse werden die Filterregeln für Spaminhalte des Diensts angepasst, damit die Nachricht zugestellt werden kann. 
    
> [!TIP]
> Stellen Sie durch folgende Schritte in [Sicherstellen, dass eine Nachricht nicht als Spam gekennzeichnet wird](how-to-help-ensure-that-a-message-isn-t-marked-as-spam.md) sicher, dass eine Nachricht nicht als Spam markiert wird. 
  
Wenn Sie auf das Symbol **Aktualisieren**![Aktualisieren (Symbol)](../media/ITPro-EAC-RefreshIcon.gif) klicken, um Ihre Daten zu aktualisieren, und dann auf die Nachricht doppelklicken, sollte die Nachricht an die beabsichtigten Empfänger freigegeben werden. 
  
## <a name="for-more-information"></a>Weitere Informationen
<a name="sectionSection4"> </a>

[Häufig gestellte Fragen (FAQ) zur Quarantäne](quarantine-faq.md)
  

