---
title: Informationen zur Verhinderung von Datenverlust
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Erfahren Sie, wie Sie Ihre vertraulichen Informationen mithilfe Microsoft 365 Richtlinien und Tools zur Verhinderung von Datenverlust schützen und einen Rundgang durch den DLP-Lebenszyklus unternehmen.
ms.openlocfilehash: 451622d15b1f422304dd498264ff2fe4a343bb6c
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52127789"
---
# <a name="learn-about-data-loss-prevention"></a>Informationen zur Verhinderung von Datenverlust

Organisationen haben vertrauliche Informationen unter ihrer Kontrolle, z. B. Finanzdaten, proprietäre Daten, Kreditkartennummern, Gesundheitsdatensätze oder Sozialversicherungsnummern. Um diese vertraulichen Daten zu schützen und Risiken zu reduzieren, benötigen sie eine Möglichkeit, um zu verhindern, dass ihre Benutzer sie unangemessen für Personen freigeben, die sie nicht haben sollten. Diese Vorgehensweise wird als Verhinderung von Datenverlust (Data Loss Prevention, DLP) bezeichnet.

In Microsoft 365 implementieren Sie die Verhinderung von Datenverlust, indem Sie DLP-Richtlinien definieren und anwenden. Mit einer DLP-Richtlinie können Sie vertrauliche Elemente in den bereichen identifizieren, überwachen und automatisch schützen:

- Microsoft 365 Dienste wie Teams, Exchange, SharePoint und OneDrive
- Office wie Word, Excel und PowerPoint
- Windows 10 Endpunkte
- Nicht-Microsoft-Cloud-Apps
- Lokale Dateifreigaben und lokale SharePoint.

Microsoft 365 erkennt vertrauliche Elemente mithilfe einer tiefen Inhaltsanalyse, nicht nur durch einen einfachen Textscan. Inhalte werden auf Übereinstimmungen primärer Daten mit Schlüsselwörtern, durch die Auswertung regulärer Ausdrücke, durch interne Funktionsüberprüfung und sekundäre Daten übereinstimmungen analysiert, die sich in der Nähe der primären Daten übereinstimmung befinden. Darüber hinaus verwendet DLP auch Algorithmen für maschinelles Lernen und andere Methoden, um Inhalte zu erkennen, die Ihren DLP-Richtlinien entspricht.
  
## <a name="dlp-is-part-of-the-larger-microsoft-365-compliance-offering"></a>DLP ist Teil des größeren Microsoft 365 Complianceangebots

Microsoft 365 DLP ist nur eines der Microsoft 365 Compliance-Tools, die Sie verwenden, um Ihre vertraulichen Elemente zu schützen, unabhängig davon, wo sie leben oder reisen. Sie sollten die anderen Tools im Microsoft 365 compliance tools set verstehen, wie sie miteinander in Einklang stehen und besser zusammenarbeiten.  Weitere Informationen [zum Information Protection-Prozess finden](protect-information.md) Sie unter Microsoft 365 compliance tools.

## <a name="protective-actions-of-dlp-policies"></a>Schutzaktionen von DLP-Richtlinien

Microsoft 365 Mithilfe von DLP-Richtlinien überwachen Sie die Aktivitäten, die Benutzer für vertrauliche Elemente im Ruhebereich, vertrauliche Elemente bei der Übertragung oder vertrauliche Elemente, die verwendet werden, und ergreifen Schutzmaßnahmen. Wenn ein Benutzer beispielsweise versucht, eine unzulässige Aktion zu ergreifen, z. B. das Kopieren eines vertraulichen Elements an einen nicht genehmigten Speicherort oder das Freigeben medizinischer Informationen in einer E-Mail oder anderen Bedingungen, die in einer Richtlinie festgelegt sind, kann DLP folgendes:

- Anzeigen eines Popuprichtlinientipps für den Benutzer, der ihn warnt, dass er möglicherweise versucht, ein vertrauliches Element unangemessen zu teilen
- blockieren Sie die Freigabe, und ermöglichen Sie dem Benutzer über einen Richtlinientipp, den Block zu überschreiben und die Begründung der Benutzer zu erfassen.
- Blockieren der Freigabe ohne die Außerkraftsetzungsoption
- Für ruhende Daten können vertrauliche Elemente gesperrt und an einen sicheren Quarantänespeicherort verschoben werden.
- Für Teams werden die vertraulichen Informationen nicht angezeigt

Alle von DLP überwachten Aktivitäten werden standardmäßig im überwachungsprotokoll [Microsoft 365 aufgezeichnet](search-the-audit-log-in-security-and-compliance.md) und an den [Aktivitäts-Explorer geroutet.](data-classification-activity-explorer.md) Wenn ein Benutzer eine Aktion ausführt, die den Kriterien einer DLP-Richtlinie entspricht und Warnungen konfiguriert sind, stellt DLP Warnungen im DLP-Warnungsverwaltungsdashboard [zur Verfügung.](dlp-configure-view-alerts-policies.md)

## <a name="dlp-lifecycle"></a>DLP-Lebenszyklus

Eine DLP-Implementierung folgt in der Regel diesen Hauptphasen.

- [Planen von DLP](#plan-for-dlp)
- [Vorbereiten auf DLP](#prepare-for-dlp)
- [Bereitstellen Ihrer Richtlinien in der Produktion](#deploy-your-policies-in-production)


<!--ADD DIAGRAM OF THE DLP LIFECYCLE WORK ON WITH MAS-->

### <a name="plan-for-dlp"></a>Planen von DLP

Microsoft 365 DLP-Überwachung und -Schutz sind systemeigene Anwendungen, die Benutzer täglich verwenden. Dies trägt dazu bei, die vertraulichen Elemente Ihrer Organisation vor riskanten Aktivitäten zu schützen, auch wenn Ihre Benutzer nicht für das Denken und die Methoden zur Verhinderung von Datenverlusten gekonnt sind. Wenn Ihre Organisation und Ihre Benutzer mit methoden zur Verhinderung von Datenverlust neu sind, kann die Einführung von DLP eine Änderung ihrer Geschäftsprozesse erfordern, und es gibt eine Kulturverschiebung für Ihre Benutzer. Bei ordnungsgemäßer Planung, Tests und Optimierung schützen Ihre DLP-Richtlinien ihre vertraulichen Elemente und minimieren gleichzeitig potenzielle Unterbrechungen von Geschäftsprozessen.

**Technologieplanung für DLP**

Denken Sie daran, dass DLP als Technologie Ihre ruhen, verwendeten und bewegten Daten über Microsoft 365-Dienste, Windows 10-Geräte, lokale Dateifreigaben und lokale Dateifreigaben hinweg überwachen und schützen SharePoint. Es gibt Planungsauswirkungen für die verschiedenen Speicherorte, die Art der Daten, die Sie überwachen und schützen möchten, und die Aktionen, die beim Auftreten einer Richtlinien übereinstimmung ergriffen werden müssen.  

**Planung von Geschäftsprozessen für DLP**

DLP-Richtlinien können verbotene Aktivitäten blockieren, z. B. die unangemessene Freigabe vertraulicher Informationen per E-Mail. Bei der Planung Ihrer DLP-Richtlinien müssen Sie die Geschäftsprozesse identifizieren, die Ihre vertraulichen Elemente berühren. Die Besitzer von Geschäftsprozessen können Ihnen dabei helfen, geeignete Benutzerverhalten zu identifizieren, die zulässig sein sollten, und unangemessene Benutzerverhalten, vor dem geschützt werden sollte. Sie sollten Ihre Richtlinien planen und im Testmodus [](data-classification-activity-explorer.md) bereitstellen und ihre Auswirkungen zunächst über den Aktivitäts-Explorer auswerten, bevor Sie sie in restriktiveren Modi anwenden.

**Organisationskulturplanung für DLP**

Eine erfolgreiche DLP-Implementierung hängt genauso davon ab, dass Ihre Benutzer geschult und für Methoden zur Verhinderung von Datenverlust aklimiert werden wie für gut geplante und abgestimmte Richtlinien. Da Ihre Benutzer stark eingebunden sind, sollten Sie auch schulungen für sie planen. Sie können Richtlinientipps strategisch verwenden, um ihre Benutzer zu sensibilisieren, bevor Sie die Richtliniendurchsetzung vom Testmodus in restriktivere Modi ändern.

<!--For more information on planning for DLP, including suggestions for deployment based on your needs and resources, see [Planning for Microsoft 365 data loss prevention](dlp-plan-for-dlp.md).-->

### <a name="prepare-for-dlp"></a>Vorbereiten auf DLP

Sie können DLP-Richtlinien auf Ruhedaten, daten in Verwendung und daten in Bewegung an Speicherorten anwenden, z. B.:

- Exchange Online E-Mail
- SharePoint Online-Websites
- OneDrive-Konten
- Teams-Chat- und Teams-Kanalnachrichten
- Microsoft Cloud App Security
- Windows 10-Geräte
- Lokale Repositorys

Jeder hat unterschiedliche Voraussetzungen. Vertrauliche Elemente an einigen Orten, z. B. Exchange Online, können unter den DLP-Regenschirm gebracht werden, indem sie lediglich eine Richtlinie konfigurieren, die für sie gilt. Andere, z. B. lokale Dateirepositorys, erfordern eine Bereitstellung des Azure Information Protection (AIP)-Scanners. Sie müssen Ihre Umgebung vorbereiten, Richtlinienentwürfe codieren und gründlich testen, bevor Sie blockierende Aktionen aktivieren.

### <a name="deploy-your-policies-in-production"></a>Bereitstellen Ihrer Richtlinien in der Produktion

#### <a name="design-your-policies"></a>Entwerfen Ihrer Richtlinien

Beginnen Sie mit der Definition Ihrer Steuerungsziele und deren Anwendung auf die jeweilige Arbeitsauslastung. Entwurf einer Richtlinie, die Ihre Ziele verkörpert. Beginnen Sie mit einer Arbeitsauslastung gleichzeitig oder über alle Workloads hinweg – es gibt noch keine Auswirkungen.

#### <a name="implement-policy-in-test-mode"></a>Implementieren der Richtlinie im Testmodus

Bewerten Sie die Auswirkungen der Steuerelemente, indem Sie sie mit einer DLP-Richtlinie im Testmodus implementieren. Es ist in Ordnung, die Richtlinie auf alle Arbeitsauslastungen im Testmodus anzuwenden, damit Sie die vollständige Bandbreite der Ergebnisse erhalten können. Sie können jedoch bei Bedarf mit einer Arbeitsauslastung beginnen.

#### <a name="monitor-outcomes-and-fine-tune-the-policy"></a>Überwachen der Ergebnisse und Optimieren der Richtlinie

Überwachen Sie im Testmodus die Ergebnisse der Richtlinie, und optimieren Sie sie so, dass sie Ihre Kontrollziele erfüllt, und stellen Sie sicher, dass Sie keine negativen oder unbeabsichtigten Auswirkungen auf gültige Benutzerworkflows und Produktivität haben. Im Folgenden finden Sie einige Beispiele für die Feinabstimmung:

- Anpassen der Standorte und Personen/Orte, die sich in oder nicht im Bereich befinden
- Optimieren der Bedingungen und Ausnahmen, die verwendet werden, um zu bestimmen, ob ein Element und was damit geschieht, mit der Richtlinie
- definition/s für vertrauliche Informationen
- die Aktionen
- Die Stufe der Einschränkungen
- Hinzufügen neuer Steuerelemente
- Hinzufügen neuer Personen
- Hinzufügen neuer eingeschränkter Apps
- Hinzufügen neuer eingeschränkter Websites

#### <a name="enable-the-control-and-tune-your-policies"></a>Aktivieren des Steuerelements und Optimieren Ihrer Richtlinien

Sobald die Richtlinie alle Ihre Ziele erfüllt, aktivieren Sie sie. Überwachen Sie weiterhin die Ergebnisse der Richtlinienanwendung, und stimmen Sie sie nach Bedarf ab. Im Allgemeinen werden Richtlinien etwa eine Stunde nach dem Aktivierten wirksam. <!--See, LINK TO topic for SLAs for location specific details- >

## <a name="dlp-policy-configuration-overview"></a>Übersicht über die Konfiguration von DLP-Richtlinien

Sie haben Flexibilität bei der Erstellung und Konfiguration Ihrer DLP-Richtlinien. Sie können mit einer vordefinierten Vorlage beginnen und mit nur wenigen Klicks eine Richtlinie erstellen, oder Sie können ihre eigene von Grund auf entwerfen. Unabhängig davon, welche Option Sie auswählen, benötigen alle DLP-Richtlinien dieselben Informationen von Ihnen.

1. **Wählen Sie aus,** was Sie überwachen Microsoft 365 enthält viele vordefinierte Richtlinienvorlagen, die Ihnen beim Einstieg helfen oder eine benutzerdefinierte Richtlinie erstellen können.
    - Eine vordefinierte Richtlinienvorlage: Finanzdaten, Medizinische und Gesundheitsdaten, Datenschutzdaten für verschiedene Länder und Regionen.
    - Eine benutzerdefinierte Richtlinie, die die verfügbaren Typen vertraulicher Informationen, Aufbewahrungsbezeichnungen und Vertraulichkeitsbezeichnungen verwendet.
2. **Wählen Sie aus, wo Sie überwachen möchten:** Wählen Sie einen oder mehrere Speicherorte aus, die von DLP auf vertrauliche Informationen überwacht werden soll. Sie können:
    
Speicherort | einschließen/ausschließen nach|
|---------|---------|
|Exchange-E-Mail| Verteilergruppen|
|Microsoft Office SharePoint Online-Websites |Websites |
|OneDrive-Konten |Konten oder Verteilergruppen |
|Teams-Chat- und Teams-Kanalnachrichten |Konten |
|Windows 10-Geräte |Benutzer oder Gruppe |
|Microsoft Cloud App Security |Instanz |
|Lokale Repositorys| Pfad der Repositorydatei|

3. **Wählen Sie die Bedingungen** aus, die erfüllt werden müssen, damit eine Richtlinie auf ein Element angewendet werden kann. Sie können vorkonfigurierte Bedingungen akzeptieren oder benutzerdefinierte Bedingungen definieren. Einige Beispiele:

- element enthält eine bestimmte Art vertraulicher Informationen, die in einem bestimmten Kontext verwendet werden. Beispielsweise werden 95 Sozialversicherungsnummern per E-Mail an Empfänger außerhalb Ihrer Organisation gesendet.
- Element hat eine angegebene Vertraulichkeitsbezeichnung
- Element mit vertraulichen Informationen wird intern oder extern freigegeben

4. **Wählen Sie die Aktion aus, die** sie ausführen soll, wenn die Richtlinienbedingungen erfüllt sind : Die Aktionen hängen vom Ort ab, an dem die Aktivität gerade geschieht.  Einige Beispiele:

- SharePoint/Exchange/OneDrive: Personen außerhalb Ihres Organisationsformulars den Zugriff auf den Inhalt blockieren. Zeigen Sie dem Benutzer einen Tipp an, und senden Sie eine E-Mail-Benachrichtigung, dass er eine Aktion unternimmt, die durch die DLP-Richtlinie verboten ist.
- Teams Chat und Kanal: Blockieren der Freigabe vertraulicher Informationen im Chat oder Kanal
- Windows 10 Geräte: Überwachen oder Einschränken des Kopierens eines vertraulichen Elements auf ein entfernbares USB-Gerät 
- Office Apps: Zeigen Sie ein Popup an, das den Benutzer darüber informiert, dass er ein riskantes Verhalten einrät, blockiert oder blockiert, außer Kraft setzen lässt.
- Lokale Dateifreigaben: Verschieben der Datei in einen Quarantäneordner

> [!NOTE]
> Die Bedingungen und die zu ergreifende Aktion werden in einem Objekt definiert, das als Rule bezeichnet wird.

<!--## Create a DLP policy

All DLP policies are created and maintained in the Microsoft 365 Compliance center. See, INSERT LINK TO ARTICLE THAT WILL START WALKING THEM THROUGH THE POLICY CREATION PROCEDURES for more information.-->

Nachdem Sie eine DLP-Richtlinie im Compliance Center erstellt haben, wird sie in einem zentralen Richtlinienspeicher gespeichert und dann mit den verschiedenen Inhaltsquellen synchronisiert, einschließlich:
  
- Exchange Online und von dort aus mit Outlook im Web und Outlook.
- OneDrive for Business-Websites.
- SharePoint Online-Websites.
- Office-Desktopprogrammen (Excel, PowerPoint und Word).
- Microsoft Teams-Kanälen und Chatnachrichten.
    
Nachdem die Richtlinie mit den richtigen Speicherorten synchronisiert wurde, werden Inhalte ausgewertet und Aktionen erzwungen.

## <a name="viewing-policy-application-results"></a>Anzeigen von Richtlinienanwendungsergebnissen

DLP meldet eine große Menge von Informationen Microsoft 365 Überwachung, Richtlinien übereinstimmungen und Aktionen sowie Benutzeraktivitäten. Sie müssen diese Informationen nutzen und darauf reagieren, um Ihre Richtlinien und Triageaktionen für vertrauliche Elemente zu optimieren. Die Telemetrie wird zuerst Microsoft 365 [Compliance Center Audit Logs](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log-in-the-compliance-center) verwendet, wird verarbeitet und führt zu unterschiedlichen Berichterstellungstools. Jedes Berichterstellungstool hat einen anderen Zweck.  

### <a name="dlp-alerts-dashboard"></a>Dashboard für DLP-Warnungen

Wenn DLP eine Aktion für ein vertrauliches Element ergreift, können Sie über eine konfigurierbare Warnung benachrichtigt werden. Anstatt diese Warnungen in einem Postfach aufstapeln zu lassen, damit Sie sie durchspiften können, stellt das Compliance Center sie im [DLP Alerts Management Dashboard zur Verfügung.](dlp-configure-view-alerts-policies.md) Verwenden Sie das DLP-Benachrichtigungsdashboard, um Warnungen zu konfigurieren, zu überprüfen, zu verdingen und die Auflösung von DLP-Warnungen nachverfolgt zu werden. Im Folgenden finden Sie ein Beispiel für Warnungen, die durch Richtlinien übereinstimmungen und Aktivitäten von Windows 10 werden.

> [!div class="mx-imgBorder"]
> ![Warninformationen](../media/Alert-info-1.png)

Sie können ebenfalls Details des zugehörigen Ereignisses mit umfangreichen Metadaten im gleichen Dashboard anzeigen.

> [!div class="mx-imgBorder"]
> ![Ereignisinformationen](../media/Event-info-1.png)

### <a name="reports"></a>Berichte

Die [DLP-Berichte](view-the-dlp-reports.md#view-the-reports-for-data-loss-prevention) zeigen im Laufe der Zeit breite Trends und geben spezifische Einblicke in:

- **DLP Policy Matches** over time and filter by date range, location, policy, or action
- **Übereinstimmungen mit DLP-Vorfällen** zeigen auch Übereinstimmungen im Laufe der Zeit an, drehen sich jedoch nicht auf die Richtlinienregeln, sondern auf die Elemente.
- **Bei falsch positiven** Und Außerkraftsetzungen von DLP wird die Anzahl der falsch positiven Werte und, falls konfiguriert, benutzerüberschreibungen zusammen mit der Begründung des Benutzers angezeigt.

### <a name="dlp-activity-explorer"></a>DLP-Aktivitäts-Explorer

Auf der Registerkarte Aktivitäts-Explorer auf der Seite DLP ist der *Aktivitätsfilter* auf *DLPRuleMatch voreingestellt.* Verwenden Sie dieses Tool, um Aktivitäten im Zusammenhang mit Inhalten zu überprüfen, die vertrauliche Informationen enthalten oder Bezeichnungen angewendet wurden, z. B. welche Bezeichnungen geändert wurden, dateien geändert wurden und einer Regel entsprechen.

![Screenshot des DLPRuleMatch-Bereichsaktivitäts-Explorers ](../media/dlp-activity-explorer.png)

Weitere Informationen finden Sie unter [Erste Schritte mit dem Aktivitäts-Explorer.](data-classification-activity-explorer.md)

Weitere Informationen zu Microsoft 365 DLP finden Sie unter:

- [Informationen zu Microsoft 365 Endpunkt-DLP (Data Loss Prevention, Verhinderung von Datenverlust)](endpoint-dlp-learn-about.md)
- [Weitere Informationen zur Standardrichtlinie zur Verhinderung von Datenverlust in Microsoft Teams (Vorschau)](dlp-teams-default-policy.md)
- [Erfahren Sie mehr über den lokalen Microsoft 365-Scanner zur Verhinderung von Datenverlust (Vorschau)](dlp-on-premises-scanner-learn.md)
- [Erfahren Sie mehr über die Microsoft Compliance-Erweiterung (Vorschau)](dlp-chrome-learn-about.md)
- [Informationen zum Dashboard zur Verhinderung von Datenverlust](dlp-alerts-dashboard-learn.md)