---
title: Anwenden der Verwaltung von Informationsrechten (Information Rights Management, IRM) auf eine Liste oder Bibliothek
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 3bdb5c4e-94fc-4741-b02f-4e7cc3c54aa1
ms.collection:
- M365-security-compliance
- SPO_Content
description: Sie können die Verwaltung von Informationsrechten (Information Rights Management, IRM) zum Steuern und schützen von Dateien verwenden, die aus Listen oder Bibliotheken heruntergeladen werden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: de0105bf61b4abbddd938a4ec7286c1919bf3985
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948483"
---
# <a name="apply-information-rights-management-irm-to-a-list-or-library"></a>Anwenden der Verwaltung von Informationsrechten (Information Rights Management, IRM) auf eine Liste oder Bibliothek

Sie können die Verwaltung von Informationsrechten (Information Rights Management, IRM) zum Steuern und schützen von Dateien verwenden, die aus Listen oder Bibliotheken heruntergeladen werden.
  
## <a name="administrator-preparations-before-applying-irm"></a>Administrator Vorbereitungen vor dem Anwenden von IRM

- Der Azure Rights Management Service (Azure RMS) von Azure Information Protection und die lokale Entsprechung, Active Directory Rights Management Services (AD RMS), unterstützen die Verwaltung von Informationsrechten für Websites. Es sind keine separaten oder zusätzlichen Installationen erforderlich.
    
- Bevor Sie IRM auf eine Liste oder Bibliothek anwenden, muss Sie zunächst von einem Administrator für Ihre Website aktiviert werden.
    
- Um IRM auf eine Liste oder Bibliothek anzuwenden, benötigen Sie Administratorberechtigungen für diese Liste oder Bibliothek.
    
- Wenn Sie SharePoint Online verwenden, können die Benutzer beim Herunterladen größerer IRM-geschützter Dateien möglicherweise Timeouts auftreten. In diesem Fall wenden Sie den IRM-Schutz mithilfe Ihrer Office-Programme an und speichern größere Dateien in einer SharePoint-Bibliothek, die nicht IRM verwendet.
    
> [!NOTE]
> Wenn Sie SharePoint Server 2013 verwenden, muss ein Server Administrator auf allen Front-End-Webservern Schutzprogramme für jeden Dateityp installieren, den die Personen in Ihrer Organisation mithilfe von IRM schützen möchten. 
  
## <a name="apply-irm-to-a-list-or-library"></a>Anwenden von IRM auf eine Liste oder Bibliothek
<a name="__toc256598179"> </a>

![Einstellungen für die Verwaltung von Informationsrechten](../media/1b708102-9c90-42b0-b255-ef0e72d0be88.png)
  
1. Wechseln Sie zu der Liste oder Bibliothek, für die Sie IRM konfigurieren möchten.
    
2. Klicken Sie auf dem Menüband auf die Registerkarte **Bibliothek** , und klicken Sie dann auf **Bibliothekseinstellungen**. (Wenn Sie in einer Liste arbeiten, klicken Sie auf die Registerkarte **Liste** , und klicken Sie dann auf **Listeneinstellungen**).
    
    ![Schaltflächen für die SharePoint-Bibliothekseinstellungen auf dem Menüband](../media/cdf718fa-d792-40fc-8026-00c3b80b9e05.png)
  
3. Klicken Sie unter **Berechtigungen und Verwaltung**auf **Verwaltung von Informationsrechten**. Wenn der Link zur Verwaltung von Informationsrechten nicht angezeigt wird, ist IRM möglicherweise nicht für Ihre Website aktiviert. Wenden Sie sich an den Server Administrator, um zu prüfen, ob IRM für Ihre Website aktiviert werden kann. Der Link zur Verwaltung von Informationsrechten wird nicht für Bildbibliotheken angezeigt.
    
4. Aktivieren Sie auf der Seite Einstellungen für die **Verwaltung von Informationsrechten** das Kontrollkästchen **Berechtigung für Dokumente in dieser Bibliothek beim Herunterladen einschränken** , um eingeschränkte Berechtigungen auf Dokumente anzuwenden, die aus dieser Liste oder Bibliothek heruntergeladen werden. 
    
5. Geben Sie im Feld **Berechtigungsrichtlinien Titel erstellen** einen beschreibenden Namen für die Richtlinie ein, die Sie später verwenden können, um diese Richtlinie von anderen Richtlinien zu unterscheiden. Sie können beispielsweise " **Company Confidential** " eingeben, wenn Sie eingeschränkte Berechtigungen auf eine Liste oder Bibliothek anwenden, die vertrauliche Unternehmensdokumente enthalten soll. 
    
6. Geben Sie im Feld **Beschreibung der Berechtigungsrichtlinie hinzufügen** eine Beschreibung ein, die den Benutzern angezeigt wird, die diese Liste oder Bibliothek verwenden, um zu erläutern, wie die Dokumente in dieser Liste oder Bibliothek behandelt werden sollen. Beispielsweise können Sie **den Inhalt dieses Dokuments nur für andere Mitarbeiter besprechen** , wenn Sie den Zugriff auf die Informationen in diesen Dokumenten auf interne Mitarbeiter beschränken möchten. 
    
7. Wenn Sie zusätzliche Einschränkungen für die Dokumente in dieser Liste oder Bibliothek anwenden möchten, klicken Sie auf **Optionen anzeigen**, und führen Sie eine der folgenden Aktionen aus:
    
|**Gehen Sie hierfür folgendermaßen vor:**|**Gehen Sie wie folgt vor:**|
|:-----|:-----|
|Zulassen, dass Benutzer Dokumente aus dieser Liste oder Bibliothek drucken können  <br/> |Aktivieren Sie das Kontrollkästchen **Betrachter dürfen das Drucken erlauben** .  <br/> |
|Zulassen, dass Personen mit mindestens der Berechtigung "Elemente anzeigen" eingebetteten Code oder Makros in einem Dokument ausführen können.  <br/> |Aktivieren Sie das Kontrollkästchen **Viewer dürfen Skripts und Bildschirm Lesefunktionen für heruntergeladene Dokumente ausführen** .  <br/> Wenn Sie diese Option auswählen, können Benutzercode ausführen, um den Inhalt eines Dokuments zu extrahieren.           |
|Wählen Sie diese Option aus, wenn Sie den Zugriff auf Inhalte auf einen bestimmten Zeitraum beschränken möchten. Wenn Sie diese Option auswählen, laufen die Ausstellungs Lizenzen der Personen für den Zugriff auf den Inhalt nach der angegebenen Anzahl von Tagen ab, und die Benutzer müssen zum Server zurückkehren, um Ihre Anmeldeinformationen zu überprüfen und eine neue Kopie herunterzuladen.  <br/> |Aktivieren Sie das Kontrollkästchen **nach dem Download werden Dokument Zugriffsrechte nach Ablauf dieser Anzahl von Tagen ablaufen (1-365)** , und geben Sie dann die Anzahl der Tage an, für die das Dokument angezeigt werden soll.  <br/> |
| Verhindern, dass Personen Dokumente hochladen, die IRM nicht unterstützen, für diese Liste oder Bibliothek.  <br/>  Wenn Sie diese Option auswählen, können Benutzer keine der folgenden Dateitypen hochladen:  <br/>  Dateitypen, für die keine entsprechenden IRM-Schutzkomponenten auf allen Front-End-Webservern installiert sind.  <br/>  Dateitypen, die SharePoint Server 2010 nicht entschlüsseln können.  <br/>  Dateitypen, die in einem anderen Programm IRM-geschützt sind  <br/> |Aktivieren Sie das Kontrollkästchen **Benutzer dürfen keine Dokumente hochladen, die IRM nicht unterstützen** .  <br/> |
|Entfernen Sie eingeschränkte Berechtigungen aus dieser Liste oder Bibliothek an einem bestimmten Datum.  <br/> |Aktivieren Sie das Kontrollkästchen **Einschränken des Zugriffs auf die Bibliothek** deaktivieren, und wählen Sie dann das gewünschte Datum aus.  <br/> |
|Steuern Sie das Intervall, in dem Anmeldeinformationen für das Programm zwischengespeichert werden, das zum Öffnen des Dokuments lizenziert ist.  <br/> |Aktivieren Sie das Kontrollkästchen **Benutzer müssen Ihre Anmeldeinformationen über dieses Intervall (Tage) überprüfen** , und geben Sie dann das Intervall für die Zwischenspeicherung von Anmeldeinformationen in Tagen ein.  <br/> |
|Gruppen Schutz zulassen, damit Benutzer mit Mitgliedern derselben Gruppe teilen können.  <br/> |Wählen Sie **Gruppen Schutz zulassen**aus, und geben Sie den Namen der Gruppe für die Freigabe ein.  <br/> |
   
8. Klicken Sie nach Abschluss der Auswahl der gewünschten Optionen auf **OK**.
  
## <a name="what-is-information-rights-management"></a>Was ist die Verwaltung von Informationsrechten?
<a name="__toc256598175"> </a>

Mit der Verwaltung von Informationsrechten (Information Rights Management, IRM) können Sie die Aktionen einschränken, die Benutzer für Dateien ausführen können, die aus Listen oder Bibliotheken heruntergeladen wurden. IRM verschlüsselt die heruntergeladenen Dateien und beschränkt die Gruppe von Benutzern und Programmen, von denen diese Dateien entschlüsselt werden dürfen. IRM kann auch die Rechte der Benutzer, die Dateien lesen dürfen, so einschränken, dass sie keine Aktionen wie das Drucken von Kopien der Dateien oder das Kopieren von Text aus ihnen ausführen können.
  
Sie können IRM in Listen oder Bibliotheken verwenden, um die Verbreitung von vertraulichen Inhalten einzuschränken. Wenn Sie beispielsweise eine Dokumentbibliothek erstellen, um Informationen über kommende Produkte mit ausgewählten Marketingmitarbeitern freizugeben, können Sie mithilfe von IRM verhindern, dass diese Personen diese Inhalte für andere Mitarbeiter im Unternehmen freigeben.
  
Auf einer Website wenden Sie IRM auf eine gesamte Liste oder Bibliothek anstatt auf einzelne Dateien an. Dadurch wird es einfacher, einen einheitlichen Schutzgrad für eine ganze Gruppe von Dokumenten oder Dateien sicherzustellen. IRM kann somit Ihrer Organisation helfen, Unternehmensrichtlinien zu erzwingen, die die Verwendung und Verbreitung von vertraulichen oder proprietären Informationen Regeln.
  
> [!NOTE]
> Die Informationen auf dieser Seite im Zusammenhang mit der Verwaltung von Informationsrechten ersetzen alle Ausdrücke, die auf "Verwaltung von Informationsrechten" in Microsoft SharePoint Server 2013-und SharePoint Server 2016-Lizenzlaufzeit-Vereinbarungen verweisen. 
  
### <a name="how-irm-can-help-protect-content"></a>Wie IRM zum Schutz von Inhalten beitragen kann
<a name="__toc256598176"> </a>

IRM hilft, eingeschränkten Inhalt auf folgende Weise zu schützen:
  
- Verhindert, dass ein autorisierter Viewer das Kopieren, ändern, drucken, Faxen oder kopieren und Einfügen der Inhalte zur nicht autorisierten Verwendung unterstützt.
    
- Verhindert, dass ein autorisierter Viewer den Inhalt mithilfe der Druck Bildschirm Funktion in Microsoft Windows kopiert
    
- Verhindert, dass ein nicht autorisierter Betrachter den Inhalt anzeigen kann, wenn er per e-Mail gesendet wird, nachdem er vom Server heruntergeladen wurde.
    
- Beschränkt den Zugriff auf Inhalte auf einen bestimmten Zeitraum, nach dem Benutzer ihre Anmeldeinformationen bestätigen und den Inhalt erneut herunterladen müssen.
    
- Unterstützt die Durchsetzung von Unternehmensrichtlinien, die die Verwendung und Verbreitung von Inhalten in Ihrer Organisation steuern.
    
### <a name="how-irm-cannot-help-protect-content"></a>Wie IRM nicht zum Schutz von Inhalten beitragen kann
<a name="__toc256598177"> </a>

IRM kann eingeschränkte Inhalte nicht aus folgenden Bereichen schützen:
  
- Löschung, Diebstahl, Erfassung oder Übertragung durch bösartige Programme wie Trojanische Pferde, Keylogger und bestimmte Arten von Spyware
    
- Verlust oder Beschädigung aufgrund der Aktionen von Computerviren
    
- Manuelles Kopieren oder erneutes Eingeben von Inhalten aus der Anzeige auf einem Bildschirm
    
- Digitale oder filmische Fotografie von Inhalten, die auf einem Bildschirm angezeigt werden
    
- Kopieren mithilfe von Drittanbieterprogrammen für die Bildschirmaufzeichnung
    
- Kopieren von Inhaltsmetadaten (Spaltenwerte) durch die Verwendung von Drittanbieter-Bildschirmaufnahmeprogrammen oder von Copy-and-Paste-Aktionen
    
[Anwenden von Information Rights Management auf eine Liste oder Bibliothek](https://support.office.com/article/6714cfe3-ef39-43b0-bb65-a887726bb63c)
  
## <a name="how-irm-works-for-lists-and-libraries"></a>Funktionsweise von IRM für Listen und Bibliotheken
<a name="__toc256598178"> </a>

Der IRM-Schutz wird auf Dateien auf Listen-oder Bibliotheksebene angewendet. Wenn IRM für eine Bibliothek aktiviert ist, gilt die Rechteverwaltung für alle Dateien in dieser Bibliothek. Wenn IRM für eine Liste aktiviert ist, gilt die Rechteverwaltung nur für Dateien, die Listenelementen zugeordnet sind, nicht die tatsächlichen Listenelemente.
  
Wenn Personen Dateien in einer IRM-fähigen Liste oder Bibliothek herunterladen, werden die Dateien verschlüsselt, sodass nur autorisierte Personen Sie anzeigen können. Jede Datei mit verwalteten Rechten enthält auch eine Veröffentlichungslizenz, die den Personen, die die Datei anzeigen, Einschränkungen auferlegt. Zu den typischen Einschränkungen gehören das schreibgeschützte Erstellen einer Datei, das Deaktivieren des Kopierens von Text, das verhindern, dass Benutzer eine lokale Kopie speichern, und das verhindern, dass Benutzer die Datei drucken. Client Programme, die IRM-Unterstützte Dateitypen lesen können, verwenden die Veröffentlichungslizenz in der Datei mit verwalteten Rechten, um diese Einschränkungen zu erzwingen. Auf diese Weise behält eine Datei mit verwalteten Rechten ihren Schutz, auch wenn Sie vom Server heruntergeladen wurde.
  
Die Typen von Einschränkungen, die auf eine Datei angewendet werden, wenn Sie aus einer Liste oder Bibliothek heruntergeladen werden, basieren auf den Berechtigungen des einzelnen Benutzers für die Website, die die Datei enthält. In der folgenden Tabelle wird erläutert, wie die Berechtigungen auf Websites den IRM-Berechtigungen entsprechen.
  
|**Berechtigungen**|**IRM-Berechtigungen**|
|:-----|:-----|
|Berechtigungen verwalten, Website verwalten  <br/> |**Vollzugriff** (wie vom Clientprogramm definiert): mit dieser Berechtigung können Benutzerberechtigungen für Inhalte mit verwalteten Rechten in der Regel lesen, bearbeiten, kopieren, speichern und ändern.  <br/> |
|Bearbeiten von Elementen, Verwalten von Listen, hinzufügen und Anpassen von Seiten  <br/> |**Bearbeiten**, **Kopieren**und **Speichern**: ein Benutzer kann eine Datei nur drucken, wenn das Kontrollkästchen **Benutzern das Drucken von Dokumenten erlauben** aktiviert ist, auf der Seite Einstellungen für die Verwaltung von Informationsrechten für die Liste oder Bibliothek.  <br/> |
|Elemente anzeigen  <br/> |**Lesen**: ein Benutzer kann das Dokument lesen, aber seinen Inhalt nicht kopieren oder ändern. Ein Benutzer kann nur drucken, wenn das Kontrollkästchen **Benutzern das Drucken von Dokumenten erlauben** aktiviert ist, auf der Seite Einstellungen für die Verwaltung von Informationsrechten für die Liste oder Bibliothek.  <br/> |
|Andere  <br/> |Keine anderen Berechtigungen entsprechen direkt IRM-Berechtigungen.  <br/> |
   
Wenn Sie IRM für eine Liste oder Bibliothek in SharePoint Server 2013 aktivieren, können Sie nur Dateitypen in dieser Liste oder Bibliothek schützen, für die ein Schutz auf allen Front-End-Webservern installiert ist. Ein Protector ist ein Programm, das die Verschlüsselung und Entschlüsselung von Dateien mit verwalteten Rechten eines bestimmten Dateiformats steuert. SharePoint umfasst Schutz für die folgenden Dateitypen:
  
- Microsoft Office von InfoPath-Formularen
    
- Die 97-2003-Dateiformate für die folgenden Microsoft Office Programme: Word, Excel und PowerPoint
    
- Die Office Open XML Formate für die folgenden Microsoft Office-Programme: Word, Excel und PowerPoint
    
- Das XML Paper Specification (XPS)-Format
    
Wenn Ihre Organisation die Verwendung von IRM zum Schutz von anderen Dateitypen zusätzlich zu den oben aufgeführten plant, muss Ihr Server Administrator Protektoren für diese zusätzlichen Dateiformate installieren.
  

