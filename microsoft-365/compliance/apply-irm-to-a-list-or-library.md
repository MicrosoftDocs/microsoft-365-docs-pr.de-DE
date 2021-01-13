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
description: Mithilfe der Verwaltung von Informationsrechten (Information Rights Management, IRM) können Sie Dateien steuern und schützen, die aus Listen oder Bibliotheken heruntergeladen werden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5b0b541619e7bd969072755eacf103d53da6fc6a
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840526"
---
# <a name="apply-information-rights-management-irm-to-a-list-or-library"></a>Anwenden der Verwaltung von Informationsrechten (Information Rights Management, IRM) auf eine Liste oder Bibliothek

Mithilfe der Verwaltung von Informationsrechten (Information Rights Management, IRM) können Sie Dateien steuern und schützen, die aus Listen oder Bibliotheken heruntergeladen werden.
  
## <a name="administrator-preparations-before-applying-irm"></a>Administratorvorbereitungen vor dem Anwenden von IRM

- Der Azure Rights Management Service (Azure RMS) von Azure Information Protection und das lokale Äquivalent, Active Directory-Rechteverwaltungsdienste (AD RMS), unterstützen Die Verwaltung von Informationsrechten für Websites. Es sind keine separaten oder zusätzlichen Installationen erforderlich.

- Bevor Sie IRM auf eine Liste oder Bibliothek anwenden, müssen Sie IRM für Ihre Website aktivieren. Sie benötigen Administratorberechtigungen, um IRM zu aktivieren.

- Zum Anwenden von IRM auf eine Liste oder Bibliothek müssen Sie über Administratorberechtigungen für diese Liste oder Bibliothek verfügen.

- Wenn Sie SharePoint Online verwenden, kann es beim Herunterladen größerer IRM-geschützter Dateien zu Timeouts für Die Benutzer geben. Um Timeouts zu vermeiden, verwenden Sie Ihre Office-Programme, um den IrM-Schutz anzuwenden, und speichern Sie größere Dateien in einer SharePoint-Bibliothek, die IRM nicht verwendet.

> [!NOTE]
> Wenn Sie SharePoint Server 2013 verwenden, muss ein Serveradministrator Schutzschutz auf allen Front-End-Webservern für jeden Dateityp installieren, den die Personen in Ihrer Organisation mithilfe von IRM schützen möchten.
  
## <a name="apply-irm-to-a-list-or-library"></a>Anwenden von IRM auf eine Liste oder Bibliothek
<a name="__toc256598179"> </a>

![Einstellungen für die Verwaltung von Informationsrechten](../media/1b708102-9c90-42b0-b255-ef0e72d0be88.png)
  
1. Wechseln Sie zu der Liste oder Bibliothek, für die Sie IRM konfigurieren möchten.

2. Wählen Sie auf dem Menüband die Registerkarte **"Bibliothek"** und dann **"Bibliothekseinstellungen" aus.** (Wenn Sie in einer Liste arbeiten, wählen Sie die Registerkarte **"Liste"** und dann **"Listeneinstellungen" aus.**
    
    ![Schaltflächen "Einstellungen für die SharePoint-Bibliothek" im Menüband](../media/cdf718fa-d792-40fc-8026-00c3b80b9e05.png)
  
3. Wählen **Sie unter "Berechtigungen und Verwaltung"** die Option **"Verwaltung von Informationsrechten" aus.** Wenn der Link "Verwaltung von Informationsrechten" nicht angezeigt wird, ist IRM möglicherweise nicht für Ihre Website aktiviert. Wenden Sie sich an Ihren Serveradministrator, um zu erfahren, ob Sie IRM für Ihren Standort aktivieren können. Der **Link "Verwaltung von** Informationsrechten" wird für Bildbibliotheken nicht angezeigt.

4. Aktivieren Sie **auf** der Seite "Einstellungen für die Verwaltung von Informationsrechten" beim Herunterladen das Kontrollkästchen "Berechtigung auf Dokumente **in** dieser Bibliothek einschränken", um eingeschränkte Berechtigungen auf Dokumente anzuwenden, die Benutzer aus dieser Liste oder Bibliothek herunterladen.

5. Geben Sie **im Titelfeld "Berechtigungsrichtlinie erstellen"** einen beschreibenden Namen für die Richtlinie ein. Verwenden Sie einen Namen, mit dem Sie diese Richtlinie aus anderen Richtlinien identifizieren können. Verwenden Sie beispielsweise **"Company Confidential",** um eingeschränkte Berechtigungen auf eine Liste oder Bibliothek anzuwenden, die vertrauliche Unternehmensdokumente enthält.

6. Geben Sie im Feld Beschreibung **einer** Berechtigungsrichtlinie eine Beschreibung ein, die Personen angezeigt wird, die diese Liste oder Bibliothek verwenden, in der erläutert wird, wie sie mit den Dokumenten in dieser Liste oder Bibliothek umgehen sollten. Beispielsweise können Sie  den Inhalt dieses Dokuments nur mit anderen Mitarbeitern besprechen eingeben, wenn Sie den Zugriff auf die Informationen in diesen Dokumenten auf interne Mitarbeiter beschränken möchten. 

7. Um zusätzliche Einschränkungen auf die Dokumente in dieser Liste oder Bibliothek anzuwenden, wählen Sie Optionen anzeigen **aus,** und gehen Sie wie folgt vor:

|**Gehen Sie hierfür folgendermaßen vor:**|**Gehen Sie wie hier vor:**|
|:-----|:-----|
|Zulassen, dass Benutzer Dokumente aus dieser Liste oder Bibliothek drucken|Aktivieren Sie das **Kontrollkästchen "Anzeigende Anzeigen zulassen".**|
|Zulassen, dass Personen mit mindestens der Berechtigung "Elemente anzeigen" eingebetteten Code oder Makros für ein Dokument ausführen können.|Aktivieren Sie **das Kontrollkästchen** Zum Ausführen von Skript und Bildschirmleseprogramm für heruntergeladene Dokumente zulassen. Wenn Sie diese Option auswählen, können Benutzer Code ausführen, um den Inhalt eines Dokuments zu extrahieren.           |
|Wählen Sie diese Option aus, wenn Sie den Zugriff auf Inhalte auf einen bestimmten Zeitraum beschränken möchten. Wenn Sie diese Option auswählen, laufen die Ausstellungslizenzen der Personen für den Zugriff auf den Inhalt nach der angegebenen Anzahl von Tagen ab, und die Benutzer müssen zum Server zurückkehren, um ihre Anmeldeinformationen zu überprüfen und eine neue Kopie herunterzuladen.|Aktivieren Sie nach dem Download das Kontrollkästchen "Dokumentzugriffsrechte" nach dieser Anzahl von Tagen **(1-365),** und geben Sie dann die Anzahl der Tage an, für die das Dokument angezeigt werden soll.|
| Verhindern Sie, dass Personen Dokumente hochladen, die IRM nicht in diese Liste oder Bibliothek unterstützen. Wenn Sie diese Option auswählen, können Benutzer keine der folgenden Dateitypen hochladen: Dateitypen, auf denen auf allen Front-End-Webservern keine entsprechenden IRM-Schutzvorrichtung installiert sind. Dateitypen, die SharePoint Server 2010 nicht entschlüsseln kann. Dateitypen, die in einem anderen Programm IRM-geschützt sind.|Aktivieren Sie **das Kontrollkästchen "Benutzer dürfen keine Dokumente hochladen, die IRM nicht** unterstützen".|
|Entfernen Sie eingeschränkte Berechtigungen aus dieser Liste oder Bibliothek an einem bestimmten Datum.|Aktivieren Sie **das Kontrollkästchen Zum Einschränken des Zugriffs** auf die Bibliothek beenden, und wählen Sie dann das von Ihnen ausgewählte Datum aus.|
|Steuern des Intervalls, in dem Anmeldeinformationen für das Programm zwischengespeichert werden, das zum Öffnen des Dokuments lizenziert ist. Diese Einstellung wird nur in der globalen Cloud von Microsoft unterstützt. Die Einstellung ist in nationalen Cloudbereitstellungen nicht verfügbar.|Aktivieren Sie das Kontrollkästchen "Benutzer müssen ihre Anmeldeinformationen mithilfe dieses **Intervalls (Tage)"** überprüfen, und geben Sie dann das Intervall für das Zwischenspeichern von Anmeldeinformationen in der Anzahl der Tage ein.|
|Zulassen des Gruppenschutzes, damit Benutzer mit Mitgliedern derselben Gruppe teilen können.|Wählen **Sie "Gruppenschutz zulassen"** aus, und geben Sie den Namen der Gruppe für die Freigabe ein.|

8. Nachdem Sie die Auswahl der optionen abgeschlossen haben, wählen Sie **OK aus.**
  
## <a name="what-is-information-rights-management"></a>Was ist Verwaltung von Informationsrechten?
<a name="__toc256598175"> </a>

Mit der Verwaltung von Informationsrechten (Information Rights Management, IRM) können Sie die Aktionen einschränken, die Benutzer für Dateien ausführen können, die aus Listen oder Bibliotheken heruntergeladen wurden. IRM verschlüsselt die heruntergeladenen Dateien und beschränkt die Gruppe von Benutzern und Programmen, von denen diese Dateien entschlüsselt werden dürfen. IRM kann auch die Rechte der Benutzer, die Dateien lesen dürfen, so einschränken, dass sie keine Aktionen wie das Drucken von Kopien der Dateien oder das Kopieren von Text aus ihnen ausführen können.
  
Sie können IRM für Listen oder Bibliotheken verwenden, um die Verbreitung vertraulicher Inhalte zu begrenzen. Wenn Sie beispielsweise eine Dokumentbibliothek erstellen, um Informationen zu bevorstehenden Produkten mit ausgewählten Marketingmitarbeitern zu teilen, können Sie IRM verwenden, um zu verhindern, dass diese Personen diese Inhalte für andere Mitarbeiter im Unternehmen freigeben.
  
Auf einer Website wenden Sie IRM auf eine gesamte Liste oder Bibliothek anstatt auf einzelne Dateien an. Dadurch wird es einfacher, ein einheitliches Schutzniveau für eine ganze Gruppe von Dokumenten oder Dateien sicherzustellen. IRM kann Ihrer Organisation somit helfen, Unternehmensrichtlinien zu erzwingen, die die Verwendung und Verbreitung vertraulicher oder proprietärer Informationen regeln.
  
> [!NOTE]
> Die Informationen auf dieser Seite zur Verwaltung von Informationsrechten haben keineRlei Bestimmungen, die auf "Verwaltung von Informationsrechten" in microsoft SharePoint Server 2013- und SharePoint Server 2016-Lizenzvertragsverträgen verweisen. 
  
### <a name="how-irm-can-help-protect-content"></a>Wie IRM zum Schutz von Inhalten beitragen kann
<a name="__toc256598176"> </a>

IRM trägt auf folgende Weise zum Schutz eingeschränkter Inhalte bei:
  
- Verhindert das Kopieren, Ändern, Drucken, Faxen oder Kopieren und Einfügen von Inhalten für unbefugte Verwendung durch einen autorisierten Benutzer.
    
- Verhindert mithilfe der Druckbildschirmfunktion in Microsoft Windows, dass ein autorisierter Benutzer den Inhalt kopiert.
    
- Verhindert, dass ein nicht autorisierter Benutzer den Inhalt anzeigen kann, wenn er nach dem Herunterladen vom Server per E-Mail gesendet wird.
    
- Beschränkt den Zugriff auf Inhalte auf einen bestimmten Zeitraum, nach dem Benutzer ihre Anmeldeinformationen bestätigen und den Inhalt erneut herunterladen müssen.
    
- Hilft bei der Durchsetzung von Unternehmensrichtlinien, die die Verwendung und Verbreitung von Inhalten in Ihrer Organisation regeln
    
### <a name="how-irm-cannot-help-protect-content"></a>Wie IRM nicht zum Schutz von Inhalten beitragen kann
<a name="__toc256598177"> </a>

IRM kann eingeschränkte Inhalte nicht vor folgendem Inhalt schützen:
  
- Erasure, theft, capture, or transmission by malicious programs such as Trojan trojan trojan, keystroke loggers, and certain types of spyware
    
- Verlust oder Beschädigung aufgrund der Aktionen von Computerviren
    
- Manuelles Kopieren oder erneutes Kopieren von Inhalten aus der Anzeige auf einem Bildschirm
    
- Digitale oder Filmaufnahmen von Inhalten, die auf einem Bildschirm angezeigt werden
    
- Kopieren mithilfe von Bildschirmaufnahmeprogrammen von Drittanbietern
    
- Kopieren von Inhaltsmetadaten (Spaltenwerten) mithilfe von Bildschirmaufnahmeprogrammen von Drittanbietern oder Kopieren und Einfügen
  
## <a name="how-irm-works-for-lists-and-libraries"></a>Funktionsweise von IRM für Listen und Bibliotheken
<a name="__toc256598178"> </a>

Der Schutz von Irm wird auf Dateien auf Listen- oder Bibliotheksebene angewendet. Wenn IRM für eine Bibliothek aktiviert ist, gilt die Rechteverwaltung für alle Dateien in dieser Bibliothek. Wenn IRM für eine Liste aktiviert ist, gilt die Rechteverwaltung nur für Dateien, die an Listenelemente angefügt sind, nicht für die eigentlichen Listenelemente.
  
Wenn Benutzer Dateien in einer IRM-fähigen Liste oder Bibliothek herunterladen, werden die Dateien verschlüsselt, sodass nur autorisierte Personen sie anzeigen können. Jede Datei mit verwalteten Rechten enthält auch eine Ausstellungslizenz, die den Personen, die die Datei anzeigen, Einschränkungen auferlegt. Typische Einschränkungen sind das Schreibgeschütztmachen einer Datei, das Deaktivieren des Kopierens von Text, das Verhindern, dass Personen eine lokale Kopie speichern, und das Drucken der Datei. Clientprogramme, die IRM-unterstützte Dateitypen lesen können, verwenden die Ausstellungslizenz innerhalb der Datei mit verwalteten Rechten, um diese Einschränkungen zu erzwingen. Auf diese Weise behält eine Datei mit verwalteten Rechten ihren Schutz auch nach dem Herunterladen vom Server bei.
  
Die Arten von Einschränkungen, die auf eine Datei angewendet werden, wenn sie aus einer Liste oder Bibliothek heruntergeladen wird, basieren auf den Berechtigungen des einzelnen Benutzers auf der Website, die die Datei enthält. In der folgenden Tabelle wird erläutert, wie die Berechtigungen für Websites den Berechtigungen von IRM entsprechen.
  
|**Berechtigungen**|**IRM-Berechtigungen**|
|:-----|:-----|
|Berechtigungen verwalten, Website verwalten|**Vollzugriff** (wie vom Clientprogramm definiert): Mit dieser Berechtigung kann ein Benutzer in der Regel Berechtigungen von Inhalten mit verwalteten Rechten lesen, bearbeiten, kopieren, speichern und ändern.|
|Elemente bearbeiten, Listen verwalten, Seiten hinzufügen und anpassen|**Bearbeiten,** **Kopieren** und **Speichern:** Ein Benutzer kann  eine Datei nur drucken, wenn das Kontrollkästchen Zum Drucken von Dokumenten durch Benutzer auf der Seite "Einstellungen für die Verwaltung von Informationsrechten" für die Liste oder Bibliothek aktiviert ist.|
|Elemente anzeigen|**Lesen:** Ein Benutzer kann das Dokument lesen, seinen Inhalt jedoch nicht kopieren oder ändern. Ein Benutzer kann nur  drucken, wenn das Kontrollkästchen "Benutzern das Drucken von Dokumenten erlauben" auf der Seite "Einstellungen für die Verwaltung von Informationsrechten" für die Liste oder Bibliothek aktiviert ist.|
|Andere|Keine anderen Berechtigungen entsprechen direkt den IRM-Berechtigungen.|
   
Wenn Sie IRM für eine Liste oder Bibliothek in SharePoint Server 2013 aktivieren, können Sie nur Dateitypen in dieser Liste oder Bibliothek schützen, für die eine Schutzvorrichtung auf allen Front-End-Webservern installiert ist. Eine Schutzvorrichtung ist ein Programm, das die Ver- und Entschlüsselung von Dateien mit verwalteten Rechten in einem bestimmten Dateiformat steuert. SharePoint enthält Schutzvorrichtung für die folgenden Dateitypen:
  
- Microsoft Office von InfoPath-Formularen
    
- Die Dateiformate 97-2003 für die folgenden Microsoft Office: Word, Excel und PowerPoint
    
- Die Office Open XML-Formate für die folgenden Microsoft Office: Word, Excel und PowerPoint
    
- Das FORMAT der XML Paper Specification (XPS)
    
Wenn Ihre Organisation die Verwendung von IRM zum Schutz anderer Dateitypen zusätzlich zu den oben aufgeführten plant, muss Der Serveradministrator Schutzschutz für diese zusätzlichen Dateiformate installieren.
  

