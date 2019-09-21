---
title: Konfigurieren von Spamfilterrichtlinien
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/05/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: Zu den grundlegenden Spamfiltereinstellungen zählt das Festlegen der Aktionen, die im Hinblick auf als Spam identifizierte Nachrichten durchgeführt werden sollen.
ms.openlocfilehash: 38160952827d8e60884877a67aea15521000f63f
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081645"
---
# <a name="configure-your-spam-filter-policies"></a>Konfigurieren von Spamfilterrichtlinien
Zu den Spamfiltereinstellungen zählt das Festlegen der Aktionen, die im Hinblick auf als Spam identifizierte Nachrichten durchgeführt werden sollen. Die Einstellungen für die Spamfilterrichtlinie werden nur auf eingehende Nachrichten angewendet. Es gibt zwei Optionen:

  - Standard: Die standardmäßige Spamfilterrichtlinie wird verwendet, um unternehmensweite Spamfiltereinstellungen zu konfigurieren. Diese Richtlinie kann nicht umbenannt werden und ist immer aktiviert.

  - Benutzerdefiniert: Benutzerdefinierte Spamfilterrichtlinien können granular sein und auf bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation angewendet werden. Benutzerdefinierte Richtlinien haben immer Vorrang vor der Standardrichtlinie. Sie können die Reihenfolge ändern, in der die benutzerdefinierten Richtlinien ausgeführt werden, indem Sie die Priorität der einzelnen benutzerdefinierten Richtlinien ändern. Wenn mehrere Richtlinien den festgelegten Kriterien entsprechen, wird allerdings nur die Richtlinie mit der höchsten Priorität (d. h. die Zahl, die Null am nächsten liegt) angewandt.

## <a name="what-you-must-know-before-you-begin"></a>Was Sie wissen müssen, bevor Sie beginnen

Geschätzte Zeit bis zum Abschließen des Vorgangs: 30 Minuten
  
Bevor Sie dieses Verfahren bzw. diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Informationen zu den von Ihnen benötigten Berechtigungen finden Sie unter dem Eintrag „Antispam“ im Thema [Featureberechtigungen in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx).

Die Einstellungen für Spamfilterrichtlinien befinden sich im Security & Compliance Center (SCC). Weitere Informationen finden Sie unter [Wechseln zum Office 365 Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md). Die Seite "Antispameinstellungen" befindet sich in SCC im Abschnitt \>**Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.

## <a name="access-and-create-spam-filter-policies"></a>Zugreifen auf und Erstellen von Spamfilterrichtlinien

Auf der Seite "Antispameinstellungen" können Sie auf der Registerkarte "Standard" die Standardeinstellungen anzeigen. Wenn Sie diese Einstellungen ändern möchten, wechseln Sie zur Registerkarte **Benutzerdefiniert**. Hier können Sie einige der Standardeinstellungen in der standardmäßigen Spamfilterrichtlinie anzeigen und konfigurieren.

Wenn Sie mehr benutzerdefinierte Einstellungen aktivieren oder benutzerdefinierte Richtlinien hinzufügen möchten, ändern Sie die Auswahl der **benutzerdefinierten Einstellungen** in **Ein**, um benutzerdefinierte Spamfilterrichtlinien zu aktivieren. Hier können Sie vorhandene benutzerdefinierte Richtlinien einsehen, indem Sie sie ausklappen.

## <a name="configure-custom-spam-filter-policy-settings"></a>Konfigurieren von benutzerdefinierten Einstellungen für Spamfilterrichtlinien

1. Wählen Sie durch Anklicken **Richtlinie bearbeiten** aus, um eine Richtlinie zu bearbeiten. Klicken Sie andernfalls auf **Richtlinie erstellen**.

2. Sie können einen eindeutigen Namen für benutzerdefinierte Richtlinien angeben, die Standardeinstellung können hingegen nicht umbenannt werden. Optional können Sie zusätzlich eine detailliertere Beschreibung für jede beliebige Richtlinie angeben.

3. Gehen Sie unter dem Abschnitt **Spam- und Massenaktionen** folgendermaßen vor:

  - Wählen Sie jeweils eine Aktion für den Typ **Spam**, **Nachricht mit hoher Spamwahrscheinlichkeit**, **Phishing-E-Mail** und **Massen-E-Mail** aus. Die verfügbaren Werte sind: 

    - **Nachricht in Junk-E-Mail-Ordner verschieben:** Sendet die Nachricht an den Ordner "Junk-E-Mail" der angegebenen Empfänger. Hierbei handelt es sich um die Standardaktion für Spam, Nachrichten mit hoher Spamwahrscheinlichkeit und Massen-E-Mails.<br/><br/>

    > [!NOTE]
    > Damit diese Aktion bei lokalen Postfächern funktioniert, müssen Sie zwei Exchange-Nachrichtenflussregeln (auch Transportrichtlinien genannt) auf Ihren lokalen Servern konfigurieren, um von EOP hinzugefügte Spam-Kopfzeilen zu erkennen. Weitere Informationen finden Sie unter [Sicherstellen, dass Spam an die Junk-E-Mail-Ordner der einzelnen Benutzer geleitet wird](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). Dieser Schritt ist für eigenständige EOP-Kunden (Exchange Online Protection) besonders wichtig.

    - **X-Header hinzufügen:** Sendet die Nachricht an die angegebenen Empfänger, fügt aber dem Nachrichtenheader X-Header-Text hinzu, um sie als Spam zu kennzeichnen. Wenn Sie diesen Text als Kennzeichnung verwenden, können Sie optional Posteingangsregeln erstellen oder ein Downstream-Gerät verwenden, um auf die Nachricht zu reagieren. Der standardmäßige X-Headertext lautet in etwa **Diese Nachricht ist offenbar Spam**.<br/>Über das Eingabefeld **Diesen X-Header-Text hinzufügen** können Sie den X-Header-Text anpassen. Wenn Sie den X-Headertext anpassen, beachten Sie folgende Bedingungen: 
    
      - Wenn Sie nur den Header im Format \< *header*  \> angeben, wobei der \<  *Header*  \> keine Leerzeichen enthält, wird ein Doppelpunkt, gefolgt vom Standardtext an den benutzerdefinierten Text angehängt. Wenn Sie beispielsweise angeben „Dies-ist-mein-benutzerdefinierter-Header", lautet der X-Headertext „Dies-ist-mein-benutzerdefinierter-Header: Diese Nachricht ist offenbar Spam." 
        
      - Wenn der benutzerdefinierte Headertext Leerzeichen enthält oder Sie den Doppelpunkt selbst hinzufügen, beispielsweise „X Dies ist mein benutzerdefinierter Header" oder „X-Dies-ist-mein-benutzerdefinierter-Header:", wird der X-Header-Text zurückgesetzt auf den Standardtext „X-This-Is-Spam: Diese Nachricht ist offenbar Spam".
    
      - Sie können den Headertext nicht im Format \< *header*  \>:\<  *value*  \>angeben. In diesem Fall werden beide Werte vor und nach dem Doppelpunkt ignoriert und stattdessen der standardmäßige X-Header-Text angezeigt: „X-This-Is-Spam: Diese Nachricht ist offenbar Spam." 
      
      - Beachten Sie, dass E-Mails mit diesem X-Header aufgrund der Junk-E-Mail-Konfiguration weiterhin in den Junk-E-Mail-Ordner verschoben werden könnten. Sie können dies ändern, indem Sie diese Funktion mithilfe von "Set-MailboxJunkEmailConfiguration" deaktivieren.

    - **Text in Betreffzeile voranstellen:** Sendet die Nachricht an die vorgesehenen Empfänger, dabei wird jedoch der Betreffzeile der Text vorangestellt, den Sie im Eingabefeld **Text in Betreffzeile voranstellen** eingegeben haben. Bei Verwenden dieses Texts als Kennzeichnung können Sie optional Regeln erstellen, um die Nachrichten wie gewünscht zu filtern oder weiterzuleiten. 

    - **Nachricht an E-Mail-Adresse umleiten:** Sendet die Nachricht an eine ausgewählte E-Mail-Adresse anstatt an die vorgesehenen Empfänger. Geben Sie im Eingabefeld **Nachricht an E-Mail-Adresse umleiten** die Adresse ein, an die die Umleitung erfolgen soll.

    - **Nachricht löschen:** Löscht die gesamte Nachricht, einschließlich aller Anlagen. 
        
    - **Nachricht in Quarantäne verschieben:** Verschiebt die Nachricht in Quarantäne, anstatt sie an die vorgesehenen Empfänger zu senden. Hierbei handelt es sich um die Standardaktion bei Phishing-Nachrichten. Geben Sie bei Auswahl dieser Option im Eingabefeld **Spamnachrichten aufbewahren für (Tage)** die Anzahl der Tage an, für die die Nachricht in Quarantäne bleiben soll. (Nach Ablauf des angegebenen Zeitraums wird die Nachricht automatisch gelöscht. Der Standardwert beträgt 30 Tage (dies ist der Maximalwert). Der Mindestwert ist 1 Tag.<br/><br/>TIPP: Informationen dazu, wie Administratoren E-Mails verwalten können, die sich in der Exchange-Verwaltungskonsole in Quarantäne befinden, finden Sie unter [Quarantäne](quarantine.md) und [Finden und Freigeben von Nachrichten in Quarantäne als Administrator](find-and-release-quarantined-messages-as-an-administrator.md). > Informationen zur Konfiguration von Spambenachrichtigungen, die an Benutzer gesendet werden sollen, finden Sie unter [Konfigurieren von Spambenachrichtigungen für Endbenutzer in EOP](configure-end-user-spam-notifications-in-eop.md) oder [Konfigurieren von Spambenachrichtigungen für Endbenutzer in Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md). 

  - Konfigurieren Sie **Schwellenwert auswählen** um festzulegen, wie mit Massen-E-Mails auf der Grundlage des BCL-Werts (Bulk Complaint Level) der Nachricht umgegangen werden soll. Sie können eine Schwellenwerteinstellung zwischen 1–9 auswählen, wobei 1 die meisten Massensendungen als Spam markiert und 9 die meisten Massensendungen als übermittelbar zulässt. Der Dienst führt dann die konfigurierte Aktion aus, z. B. das Verschieben der Nachricht in den Junk-E-Mail-Ordner des Empfängers. Weitere Informationen finden Sie unter [BCL-Werte (Bulk Complaint Level)](bulk-complaint-level-values.md) und [Worin besteht der Unterschied zwischen Junk-E-Mails und Massen-E-Mails?](what-s-the-difference-between-junk-email-and-bulk-email.md). 

4. Auf der Seite **Spameigenschaften** können Sie die Testmodus-Optionen für die Richtlinie festlegen, indem Sie Folgendes konfigurieren: 
    
      - **Keine** Es werden keine Testmodusaktionen bezüglich der Nachricht ausgeführt. Dies ist die Standardeinstellung. 
        
      - **Standardtesttext für X-Header hinzufügen** Wenn Sie diese Option auswählen, wird die Nachricht an die angegebenen Empfänger gesendet. Dabei wird der Nachricht jedoch ein spezieller X-Header hinzugefügt, dem zu entnehmen ist, dass die Nachricht den Kriterien für eine erweiterte Spamfilteroption entspricht. 
        
      - **Bcc-Nachricht an diese Adresse senden** Bei Auswahl dieser Option wird eine Kopie der Nachricht an einen nicht sichtbaren Empfänger (Bcc) unter der von Ihnen im Eingabefeld angegebenen E-Mail-Adresse gesendet. <br/><br/>Weitere Informationen zu den erweiterten Spamfilteroptionen, einschließlich Beschreibungen zu jeder Option und des jeweils verknüpften X-Headertexts, finden Sie unter [Erweiterte Spamfilterungsoptionen](advanced-spam-filtering-asf-options.md).

5. Klicken Sie für benutzerdefinierte Richtlinien auf die Menüoption **Anwenden auf**, und erstellen Sie dann eine auf Bedingungen basierende Regel, mit der die Benutzer, Gruppen und/oder Domänen angegeben werden, auf die diese Richtlinie angewendet wird. Sie können mehrere Bedingungen angeben, wenn diese eindeutig sind. 
    
      - Um Benutzer auszuwählen, wählen Sie **Der Empfänger ist** aus. Wählen Sie im folgenden Dialogfeld in der Benutzerauswahlliste den bzw. die Absender in Ihrem Unternehmen aus, und klicken Sie dann auf **Hinzufügen**. Wenn Sie Absender hinzufügen möchten, die nicht in der Liste enthalten sind, geben Sie deren E-Mail-Adressen ein, und klicken Sie auf **Namen überprüfen**. In diesem Feld können Sie auch Platzhalterzeichen für mehrere E-Mail-Adressen verwenden (z. B.: \*@ _domainname_). Wenn Sie Ihre Auswahl getroffen haben, klicken Sie auf **OK**, um zum Hauptbildschirm zurückzukehren. 
        
      - Um Gruppen auszuwählen, wählen Sie **Der Empfänger ist Mitglied von** aus, und wählen Sie dann im folgenden Dialogfeld die Gruppen aus oder geben Sie diese an. Klicken Sie auf **OK**, um zum Hauptbildschirm zurückzukehren. 
        
      - Um Domänen auszuwählen, wählen Sie **Empfängerdomäne ist** aus, und fügen Sie dann im folgenden Dialogfeld die Domänen hinzu. Klicken Sie auf **OK**, um zum Hauptbildschirm zurückzukehren. <br/><br/>Sie können Ausnahmen innerhalb der Regel erstellen. So können Sie beispielsweise Nachrichten aus allen Domänen mit Ausnahme einer bestimmten Domäne filtern. Klicken Sie auf **Ausnahme hinzufügen**, und erstellen Sie dann Ihre Ausnahmebedingungen ähnlich wie die anderen Bedingungen.<br/><br/>Das Anwenden einer Spamrichtlinie auf eine Gruppe wird nur für **E-Mail-aktivierte Sicherheitsgruppen** unterstützt. 
  
6. Klicken Sie auf **Speichern**. Im Bereich auf der rechten Seite wird eine Zusammenfassung der Richtlinieneinstellungen angezeigt.

Die Standardrichtlinie kann nicht deaktiviert oder gelöscht werden, und benutzerdefinierte Richtlinien haben immer Vorrang vor der Standardrichtlinie. Sie können die Kontrollkästchen in der Spalte **AKTIVIERT** aktivieren beziehungsweise deaktivieren, um Ihre benutzerdefinierten Richtlinien zu aktivieren oder zu deaktivieren. Standardmäßig sind alle Richtlinien aktiviert. Klicken Sie zum Löschen einer benutzerdefinierten Richtlinie auf das ![Symbol „Löschen“](../media/ITPro-EAC-DeleteIcon.gif) Symbol **Löschen**, und bestätigen Sie dann, dass Sie die Richtlinie tatsächlich löschen möchten.

> [!TIP]
> Sie können die Priorität (Ausführungsreihenfolge) Ihrer benutzerdefinierten Richtlinien ändern, indem Sie auf den ![Symbol „Aufwärtspfeil“](../media/ITPro-EAC-UpArrowIcon.gif) Aufwärtspfeil bzw. den ![Symbol „Abwärtspfeil“](../media/ITPro-EAC-DownArrowIcon.gif) Abwärtspfeil klicken. Die Richtlinie mit einer **PRIORITÄT** von **0** wird zuerst ausgeführt, gefolgt von **1**, dann **2** usw. 
  
## <a name="use-remote-powershell-to-configure-spam-filter-policies"></a>Konfigurieren der Richtlinien für die Spamfilterung mit Remote-PowerShell

Sie können auch in PowerShell Richtlinien für die Spamfilterung konfigurieren und anwenden. Wie Sie mit Windows PowerShell eine Verbindung mit Exchange Online herstellen, können Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554) nachlesen. Wie Sie mit Windows PowerShell eine Verbindung mit Exchange Online Protection herstellen, können Sie unter [Verbinden mit Exchange Online Protection mithilfe von Remote-PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290) nachlesen.
  
- [Get-HostedContentFilterPolicy](http://technet.microsoft.com/library/d510471a-dda5-4df7-b3f8-2ee7a1948436.aspx) Dient zum Anzeigen Ihrer Einstellungen für die Spamfilterung. 
    
- [Set-HostedContentFilterPolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx) Dient zum Bearbeiten Ihrer Einstellungen für die Spamfilterung. 
    
- [New-HostedContentFilterPolicy](http://technet.microsoft.com/library/4d15128d-9e16-42a1-8ac5-36f07d4bbbf0.aspx) Dient zum Erstellen einer neuen benutzerdefinierten Richtlinie für die Spamfilterung. 
    
- [Remove-HostedContentFilterPolicy](http://technet.microsoft.com/library/9fe1fe03-8f83-41e3-9bf5-084a392784d6.aspx) Dient zum Löschen einer benutzerdefinierten Richtlinie für die Spamfilterung. 
    
Zum Anwenden einer benutzerdefinierten Richtlinie für die Spamfilterung auf Benutzer, Gruppen und/oder Domänen verwenden Sie das Cmdlet [New-HostedContentFilterRule](http://technet.microsoft.com/library/2df13ba9-1eb0-4da3-bd72-a79d5fa15e26.aspx) (um eine neue Filterregel zu erstellen, die auf benutzerdefinierte Richtlinien angewendet werden kann) oder das Cmdlet [Set-HostedContentFilterRule](http://technet.microsoft.com/library/ba259260-ffd3-43f3-8ef4-9d8659679d02.aspx) (um eine vorhandene Filterregel zu bearbeiten, die auf benutzerdefinierte Richtlinien angewendet werden kann). Mit dem Cmdlet [Enable-HostedContentFilterRule](http://technet.microsoft.com/library/354ece28-dcde-4b5f-88ed-475115e7ea78.aspx) oder [Disable-HostedContentFilterRule](http://technet.microsoft.com/library/c1f8dafc-ef5d-47e3-b0fb-71a88e145fc5.aspx) können Sie die für die Richtlinie geltende Regel aktivieren oder deaktivieren. 
  
## <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Um sicherzustellen, dass Spam ordnungsgemäß erkannt und behandelt wird, können Sie über den Dienst eine GTUBE-Nachricht senden. Ähnlich wie die EICAR-Antivirustestdatei, beinhaltet GTUBE einen Test, mit dem Sie überprüfen können, ob der Dienst eingehende Spamnachrichten erkennt. Eine GTUBE-Nachricht sollte vom Spamfilter immer als Spam erkannt werden, und die daraufhin bezüglich der Nachricht ausgeführten Aktionen sollten den Einstellungen entsprechen, die Sie konfiguriert haben.
  
Geben Sie den folgenden GTUBE-Text in eine E-Mail in einer Zeile ohne Leerzeichen und Zeilenumbrüche ein:
  
```
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="fine-tuning-your-spam-filter-policy-to-prevent-false-positives-and-false-negatives"></a>Optimieren Ihrer Spamfilterrichtlinie, um falsch positive Ergebnisse und falsch negative Ergebnisse zu verhindern

Sie können erweiterte Spamfiltertechniken aktivieren, wenn Sie einen aggressiveren Ansatz für die Spamfilterung verfolgen möchten. Allgemeine Antispameinstellungen, die für die gesamte Organisation gelten, finden Sie unter [Verwenden einer Liste sicherer Adressen oder anderer Techniken, um zu verhindern, dass falsch positive E-Mails als Spam markiert werden](https://go.microsoft.com/fwlink/p/?LinkId=534224) oder [Blockieren von E-Mail-Spam mit dem Office 365-Spamfilter zum Verhindern von falsch negativen Ergebnissen](reduce-spam-email.md). Diese sind hilfreich, wenn Sie über die Steuerung auf Administratorebene verfügen und wenn Sie falsch positive Ergebnisse oder falsch negative Ergebnisse vermeiden möchten.

## <a name="allowblock-lists"></a>Zulassungs- und Sperrlisten

Es kann vorkommen, dass eine Nachricht von unseren Filtern übersehen wird, oder dass es einige Zeit dauert, bis sich unsere Systeme darauf einstellen. Für diese Fälle bietet die Antispamrichtlinie Zulassungs- und Sperrlisten, um die aktuelle Bewertung außer Kraft zu setzen. Diese Option sollte sehr sparsam genutzt werden, weil die Verwaltung der Listen mühsam werden kann, und nur vorübergehend, da unser Filter-Stack seinen Zweck normalerweise wie vorgesehen erfüllen sollte.

Sowohl Zulassungs- als auch Sperrlisten werden als Elemente einer Kunden-Antispamrichtlinie konfiguriert:

1. Im Abschnitt **Zulassungslisten** können Sie Einträge angeben, z. B. Absender oder Domänen, die immer an den Posteingang übermittelt werden. E-Mails von diesen Einträgen werden nicht vom Spamfilter verarbeitet. 
    
      - Fügen Sie der Zulassungsliste für Absender vertrauenswürdige Absender hinzu. Klicken Sie auf **Bearbeiten**![Symbol „Hinzufügen“](../media/ITPro-EAC-AddIcon.gif), und fügen Sie dann im Auswahldialogfeld die Absenderadressen hinzu, die Sie zulassen möchten. Sie können mehrere Einträge mithilfe eines Semikolons oder einer neuen Zeile trennen. Klicken Sie auf **Speichern**, um zur Seite **Zulassungslisten** zurückzukehren. 
        
      - Fügen Sie der Zulassungsliste für Domänen vertrauenswürdige Domänen hinzu. Klicken Sie auf **Bearbeiten**![Symbol „Hinzufügen“](../media/ITPro-EAC-AddIcon.gif), und fügen Sie dann im Auswahldialogfeld die Domänen hinzu, die Sie zulassen möchten. Sie können mehrere Einträge mithilfe eines Semikolons oder einer neuen Zeile trennen. Klicken Sie auf **Speichern**, um zur Seite **Zulassungslisten** zurückzukehren. 

> [!CAUTION]
> Sie sollten niemals akzeptierte Domänen (Ihre eigenen Domänen) oder allgemeine Domänen wie Microsoft.com, Office.com usw. in einer Zulassungsliste auflisten. Dies würde Spoofern das uneingeschränkte Senden von E-Mails in Ihre Organisation ermöglichen.

2. Auf der Seite **Sperrlisten** können Sie Einträge, wie z. B. Absender oder Domänen, angeben, die immer als Spam markiert werden. Der Dienst wendet die konfigurierte Spamaktion bei hoher Vertrauenswürdigkeit auf E-Mails an, die diesen Einträgen entsprechen. 
    
      - Fügen Sie der Absendersperrliste unerwünschte Absender hinzu. Klicken Sie auf **Bearbeiten**![Symbol „Hinzufügen“](../media/ITPro-EAC-AddIcon.gif), und fügen Sie dann im Auswahldialogfeld die Absenderadressen hinzu, die Sie blockieren möchten. Sie können mehrere Einträge mithilfe eines Semikolons oder einer neuen Zeile trennen. Klicken Sie auf **Speichern**, um zur Seite **Sperrlisten** zurückzukehren. 
        
      - Fügen Sie der Domänensperrliste unerwünschte Domänen hinzu. Klicken Sie auf **Bearbeiten**![Symbol „Hinzufügen“](../media/ITPro-EAC-AddIcon.gif), und fügen Sie dann im Auswahldialogfeld die Domänen hinzu, die Sie blockieren möchten. Sie können mehrere Einträge mithilfe eines Semikolons oder einer neuen Zeile trennen. Klicken Sie auf **Speichern**, um zur Seite **Sperrlisten** zurückzukehren.

> [!TIP]
>  Es kann vorkommen, dass Ihre Organisation mit einer Bewertung von Seiten des Dienstes nicht einverstanden ist. In diesem Fall können Sie die Zulassungs- bzw. Sperrlisteneinträge dauerhaft beibehalten. Wenn Sie allerdings beabsichtigen, eine Domäne einer Zulassungsliste für längere Zeiträume hinzuzufügen, sollten Sie den Sender bitten, sicherzustellen, dass seine Domäne authentifiziert ist und, falls dies nicht der Fall ist, die DMARC-Option „Ablehnen“ dafür festlegen.

## <a name="for-more-information"></a>Weitere Informationen
<a name="sectionSection6"> </a>

[Einrichtung Ihrer Domäne für DMARC](use-dmarc-to-validate-email.md)
  
[Quarantäne](quarantine.md)
  
[Verwenden einer Liste sicherer IP-Adressen oder anderer Techniken, um zu verhindern, dass falsch positive E-Mails als Spam markiert werden](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[Blockieren von E-Mail-Spam mit dem Office 365-Spamfilter zur Vermeidung von falsch negativen Einträgen](https://go.microsoft.com/fwlink/p/?LinkId=534225)

[SCL-Bewertungen (Spam Confidence Level)](spam-confidence-levels.md)
  

