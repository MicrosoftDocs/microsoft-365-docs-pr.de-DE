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
description: Erfahren Sie, wie Sie Ihre vertraulichen Informationen mithilfe Microsoft 365 Richtlinien und Tools zur Verhinderung von Datenverlust schützen und eine Tour durch den DLP-Lebenszyklus unternehmen.
ms.openlocfilehash: 291a9ab09d14e24d58604644d77381d7f41214d6
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226851"
---
# <a name="learn-about-data-loss-prevention"></a>Informationen zur Verhinderung von Datenverlust

Organisationen haben vertrauliche Informationen unter ihrer Kontrolle, z. B. Finanzdaten, proprietäre Daten, Kreditkartennummern, Gesundheitsdatensätze oder Sozialversicherungsnummern. Um diese vertraulichen Daten zu schützen und Risiken zu verringern, benötigen sie eine Möglichkeit, um zu verhindern, dass ihre Benutzer sie unangemessen an Personen weitergeben, die sie nicht haben sollten. Diese Vorgehensweise wird als Verhinderung von Datenverlust (Data Loss Prevention, DLP) bezeichnet.

In Microsoft 365 implementieren Sie die Verhinderung von Datenverlust, indem Sie DLP-Richtlinien definieren und anwenden. Mit einer DLP-Richtlinie können Sie vertrauliche Elemente in folgendem Bereich identifizieren, überwachen und automatisch schützen:

- Microsoft 365 Dienste wie Teams, Exchange, SharePoint und OneDrive
- Office Anwendungen wie Word, Excel und PowerPoint
- Windows 10 Endpunkte
- Nicht von Microsoft stammende Cloud-Apps
- Lokale Dateifreigaben und lokale SharePoint.

Microsoft 365 erkennt vertrauliche Elemente mithilfe einer umfassenden Inhaltsanalyse, nicht nur durch eine einfache Textüberprüfung. Der Inhalt wird auf primäre Datenüberstimmungen mit Schlüsselwörtern, durch die Auswertung regulärer Ausdrücke, durch interne Funktionsüberprüfung und durch sekundäre Datenüberstimmungen analysiert, die sich in der Nähe der primären Datenüberstimmung befinden. Darüber hinaus verwendet DLP auch Machine Learning-Algorithmen und andere Methoden, um Inhalte zu erkennen, die Ihren DLP-Richtlinien entsprechen.

## <a name="dlp-is-part-of-the-larger-microsoft-365-compliance-offering"></a>DLP ist Teil des größeren Microsoft 365 Compliance-Angebots.

Microsoft 365 DLP ist nur eines der Microsoft 365 Compliance-Tools, mit denen Sie Ihre vertraulichen Elemente überall dort schützen können, wo sie sich befinden oder unterwegs sind. Sie sollten die anderen Tools in den Microsoft 365 Compliance-Tools kennen, verstehen, wie sie miteinander interagieren und besser zusammenarbeiten.  Weitere Informationen zum Informationsschutzprozess finden Sie [unter Microsoft 365 Compliancetools.](protect-information.md)

## <a name="protective-actions-of-dlp-policies"></a>Schutzaktionen von DLP-Richtlinien

Microsoft 365 Mit DLP-Richtlinien überwachen Sie die Aktivitäten, die Benutzer für vertrauliche Elemente im Ruhezustand, vertrauliche Elemente während der Übertragung oder vertrauliche Elemente, die verwendet werden, und ergreifen Schutzmaßnahmen. Wenn ein Benutzer beispielsweise versucht, eine unzulässige Aktion auszuführen, z. B. ein vertrauliches Element an einen nicht genehmigten Speicherort zu kopieren oder medizinische Informationen in einer E-Mail oder andere Bedingungen in einer Richtlinie freizugeben, kann DLP Folgendes tun:

- Zeigen Sie dem Benutzer einen Popup-Richtlinientipp an, der sie warnt, dass er möglicherweise versucht, ein vertrauliches Element unangemessen freizugeben.
- blockieren Sie die Freigabe, und ermöglichen Sie dem Benutzer über einen Richtlinientipp, die Blockierung außer Kraft zu setzen und die Begründung der Benutzer zu erfassen.
- Blockieren der Freigabe ohne Die Außerkraftsetzungsoption
- für ruhenden Daten können vertrauliche Elemente gesperrt und an einen sicheren Quarantänespeicherort verschoben werden.
- für Teams Chat werden die vertraulichen Informationen nicht angezeigt.

Alle überwachten DLP-Aktivitäten werden standardmäßig im [Microsoft 365 Überwachungsprotokoll](search-the-audit-log-in-security-and-compliance.md) aufgezeichnet und an den [Aktivitäten-Explorer](data-classification-activity-explorer.md)weitergeleitet. Wenn ein Benutzer eine Aktion ausführt, die den Kriterien einer DLP-Richtlinie entspricht, und Sie Warnungen konfiguriert haben, stellt DLP Warnungen im [DLP-Warnungsverwaltungsdashboard](dlp-configure-view-alerts-policies.md)bereit.

## <a name="dlp-lifecycle"></a>DLP-Lebenszyklus

Eine DLP-Implementierung folgt in der Regel diesen hauptphasen.

- [Plan für DLP](#plan-for-dlp)
- [Vorbereiten von DLP](#prepare-for-dlp)
- [Bereitstellen ihrer Richtlinien in der Produktion](#deploy-your-policies-in-production)


<!--ADD DIAGRAM OF THE DLP LIFECYCLE WORK ON WITH MAS-->

### <a name="plan-for-dlp"></a>Plan für DLP

Microsoft 365 DLP-Überwachung und -Schutz sind systemeigen für die Anwendungen, die Benutzer täglich verwenden. Dies trägt dazu bei, die vertraulichen Elemente Ihrer Organisation vor riskanten Aktivitäten zu schützen, auch wenn Ihre Benutzer nicht an das Denken und Vorgehen zur Verhinderung von Datenverlust angepasst sind. Wenn Ihre Organisation und Ihre Benutzer noch nicht mit den Methoden zur Verhinderung von Datenverlust in Verbindung stehen, kann die Einführung von DLP eine Änderung Ihrer Geschäftsprozesse erfordern, und es gibt einen Kulturwechsel für Ihre Benutzer. Bei ordnungsgemäßer Planung, Tests und Optimierung schützen Ihre DLP-Richtlinien ihre vertraulichen Elemente, während potenzielle Geschäftsprozessunterbrechungen minimiert werden.

**Technologieplanung für DLP**

Bedenken Sie, dass DLP als Technologie Ihre ruhenden Daten, die verwendeten Daten und daten in Bewegung über Microsoft 365 Dienste, Windows 10 Geräte, lokale Dateifreigaben und lokale SharePoint überwachen und schützen kann. Es gibt Planungsauswirkungen für die verschiedenen Speicherorte, den Typ der Daten, die Sie überwachen und schützen möchten, und die Aktionen, die ausgeführt werden sollen, wenn eine Richtlinienübersprechung auftritt.

**Planen von Geschäftsprozessen für DLP**

DLP-Richtlinien können unzulässige Aktivitäten blockieren, z. B. unangemessene Freigabe vertraulicher Informationen per E-Mail. Bei der Planung Ihrer DLP-Richtlinien müssen Sie die Geschäftsprozesse identifizieren, die Ihre vertraulichen Elemente betreffen. Die Besitzer von Geschäftsprozessen können Ihnen dabei helfen, geeignete Benutzerverhalten zu identifizieren, die zulässig sein sollten, und unangemessene Benutzerverhalten, vor denen geschützt werden sollte. Sie sollten Ihre Richtlinien planen und im Testmodus bereitstellen und deren Auswirkungen zuerst über [den Aktivitäten-Explorer](data-classification-activity-explorer.md) auswerten, bevor Sie sie in restriktiveren Modi anwenden.

**Planung der Organisationskultur für DLP**

Eine erfolgreiche DLP-Implementierung hängt ebenso davon ab, dass Ihre Benutzer geschult und an die Praktiken zur Verhinderung von Datenverlust angepasst werden, wie von gut geplanten und abgestimmten Richtlinien. Da Ihre Benutzer stark beteiligt sind, sollten Sie auch die Schulung für sie planen. Sie können Richtlinientipps strategieweise verwenden, um die Aufmerksamkeit ihrer Benutzer zu erhöhen, bevor Sie die Richtlinienerzwingung vom Testmodus in restriktiveren Modus ändern.

<!--For more information on planning for DLP, including suggestions for deployment based on your needs and resources, see [Planning for Microsoft 365 data loss prevention](dlp-plan-for-dlp.md).-->

### <a name="prepare-for-dlp"></a>Vorbereiten von DLP

Sie können DLP-Richtlinien auf Ruhedaten, verwendete Daten und Daten in Bewegung an Orten anwenden, z. B.:

- Exchange Online E-Mail
- SharePoint Online-Sites
- OneDrive-Konten
- Teams-Chat- und Teams-Kanalnachrichten
- Microsoft Cloud App Security
- Windows 10-Geräte
- Lokale Repositorys

Jede hat unterschiedliche Voraussetzungen. Vertrauliche Elemente an einigen Orten, z. B. Exchange Online, können unter den DLP-Schirm gestellt werden, indem Sie einfach eine Richtlinie konfigurieren, die für sie gilt. Andere, z. B. lokale Dateirepositorys, erfordern eine Bereitstellung des Azure Information Protection (AIP)-Scanners. Sie müssen Ihre Umgebung vorbereiten, Richtlinien entwerfen und sorgfältig testen, bevor Sie blockierende Aktionen aktivieren.

### <a name="deploy-your-policies-in-production"></a>Bereitstellen ihrer Richtlinien in der Produktion

#### <a name="design-your-policies"></a>Entwerfen Ihrer Richtlinien

Beginnen Sie mit der Definition Ihrer Steuerungsziele und deren Anwendung für die einzelnen Workloads. Entwerfen Sie eine Richtlinie, die Ihre Ziele darstellt. Sie können jederzeit mit einer Workload oder über alle Workloads hinweg beginnen – es gibt noch keine Auswirkungen.

#### <a name="implement-policy-in-test-mode"></a>Implementieren von Richtlinien im Testmodus

Bewerten Sie die Auswirkungen der Steuerelemente, indem Sie sie mit einer DLP-Richtlinie im Testmodus implementieren. Es ist in Ordnung, die Richtlinie auf alle Workloads im Testmodus anzuwenden, damit Sie die vollständige Breite der Ergebnisse erhalten, aber Sie können bei Bedarf mit einer Workload beginnen.

#### <a name="monitor-outcomes-and-fine-tune-the-policy"></a>Überwachen der Ergebnisse und Optimieren der Richtlinie

Überwachen Sie im Testmodus die Ergebnisse der Richtlinie, und optimieren Sie sie so, dass sie Ihren Kontrollzielen entspricht und gleichzeitig sicherstellt, dass Sie sich nicht negativ oder versehentlich auf gültige Benutzerworkflows und die Produktivität auswirken. Hier sind einige Beispiele für Dinge, die Sie optimieren müssen:

- Anpassen der Speicherorte und Personen/Orte, die sich in oder außerhalb des Bereichs befinden
- Optimieren der Bedingungen und Ausnahmen, die verwendet werden, um festzustellen, ob ein Element und was damit ausgeführt wird, der Richtlinie entspricht
- Die Definitionen vertraulicher Informationen
- die Aktionen
- Das Maß an Einschränkungen
- Hinzufügen neuer Steuerelemente
- Neue Personen hinzufügen
- Hinzufügen neuer eingeschränkter Apps
- Hinzufügen neuer eingeschränkter Websites

#### <a name="enable-the-control-and-tune-your-policies"></a>Aktivieren des Steuerelements und Optimieren Ihrer Richtlinien

Sobald die Richtlinie alle Ihre Ziele erfüllt, aktivieren Sie sie. Überwachen Sie weiterhin die Ergebnisse der Richtlinienanwendung, und optimieren Sie sie nach Bedarf. Im Allgemeinen werden Richtlinien etwa eine Stunde nach dem Aktivieren wirksam.

<!--See, LINK TO topic for SLAs for location specific  details-->

## <a name="dlp-policy-configuration-overview"></a>Übersicht über die DLP-Richtlinienkonfiguration

Sie haben Flexibilität bei der Erstellung und Konfiguration Ihrer DLP-Richtlinien. Sie können mit einer vordefinierten Vorlage beginnen und mit nur wenigen Klicks eine Richtlinie erstellen, oder Sie können Ihre eigene von Grund auf entwerfen. Unabhängig davon, welcheN Sie auswählen, benötigen alle DLP-Richtlinien die gleichen Informationen von Ihnen.

1. **Wählen Sie aus, was Sie überwachen möchten** – Microsoft 365 enthält viele vordefinierte Richtlinienvorlagen, die Ihnen bei den ersten Schritten helfen, oder Sie können eine benutzerdefinierte Richtlinie erstellen.
    - Eine vordefinierte Richtlinienvorlage: Finanzdaten, Gesundheits- und Gesundheitsdaten, Datenschutzdaten für verschiedene Länder und Regionen.
    - Eine benutzerdefinierte Richtlinie, die die verfügbaren Typen vertraulicher Informationen, Aufbewahrungsbezeichnungen und Vertraulichkeitsbezeichnungen verwendet.
2. **Wählen Sie aus, wo Sie überwachen möchten–** Wählen Sie einen oder mehrere Speicherorte aus, die DLP auf vertrauliche Informationen überwachen soll. Sie können Folgendes überwachen:

Speicherort | einschließen/ausschließen nach|
|---------|---------|
|Exchange-E-Mail| Verteilergruppen|
|Microsoft Office SharePoint Online-Websites |Websites |
|OneDrive-Konten |Konten oder Verteilergruppen |
|Teams-Chat- und Teams-Kanalnachrichten |Konten |
|Windows 10-Geräte |Benutzer oder Gruppe |
|Microsoft Cloud App Security |Instanz |
|Lokale Repositorys| Repositorydateipfad|

3. **Wählen Sie die Bedingungen aus, die erfüllt werden müssen, damit eine Richtlinie auf ein Element angewendet werden kann.** Sie können vorkonfigurierte Bedingungen akzeptieren oder benutzerdefinierte Bedingungen definieren. Einige Beispiele:

- enthält eine bestimmte Art vertraulicher Informationen, die in einem bestimmten Kontext verwendet werden. Beispielsweise werden 95 Sozialversicherungsnummern per E-Mail an Empfänger außerhalb Ihrer Organisation gesendet.
- Element hat eine angegebene Vertraulichkeitsbezeichnung
- Element mit vertraulichen Informationen wird entweder intern oder extern freigegeben

4. **Wählen Sie die Aktion aus, die ausgeführt werden soll, wenn die Richtlinienbedingungen erfüllt sind** . Die Aktionen hängen vom Ort ab, an dem die Aktivität stattfindet.  Einige Beispiele:

- SharePoint/Exchange/OneDrive: Personen außerhalb Ihres Organisationsformulars den Zugriff auf den Inhalt blockieren. Zeigen Sie dem Benutzer einen Tipp und senden Sie eine E-Mail-Benachrichtigung, dass er eine Aktion ausführt, die durch die DLP-Richtlinie verboten ist.
- Teams Chat und Kanal: Blockieren der Freigabe vertraulicher Informationen im Chat oder Kanal
- Windows 10 Geräte: Überwachen oder Einschränken des Kopierens eines vertraulichen Elements auf ein usb-Gerät, das entfernt werden kann
- Office Apps: Zeigen Sie ein Popup an, in dem der Benutzer benachrichtigt wird, dass er ein riskantes Verhalten eingibt und die Außerkraftsetzung blockiert oder blockiert, aber die Außerkraftsetzung zulässt.
- Lokale Dateifreigaben: Verschieben der Datei von ihrem Speicherort in einen Quarantäneordner

> [!NOTE]
> Die Bedingungen und die auszuführenden Aktionen werden in einem Objekt definiert, das als Regel bezeichnet wird.

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

DLP meldet eine große Menge an Informationen in Microsoft 365 aus Überwachung, Richtlinienüberstimmungen und -aktionen sowie Benutzeraktivitäten. Sie müssen diese Informationen nutzen und darauf reagieren, um Ihre Richtlinien zu optimieren und Aktionen für vertrauliche Elemente zu selektieren. Die Telemetriedaten werden zuerst in das [Microsoft 365 Compliance Center Audit Logs](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log-in-the-compliance-center) aufgenommen, verarbeitet und gelangen zu unterschiedlichen Berichterstellungstools. Jedes Berichterstellungstool hat einen anderen Zweck.

### <a name="dlp-alerts-dashboard"></a>Dashboard für DLP-Warnungen

Wenn DLP eine Aktion für ein vertrauliches Element ausführt, können Sie über eine konfigurierbare Warnung über diese Aktion benachrichtigt werden. Anstatt diese Warnungen in einem Postfach zu durchsuchen, stellt das Compliance Center sie im [Verwaltungsdashboard für DLP-Warnungen](dlp-configure-view-alerts-policies.md)zur Verfügung. Verwenden Sie das Dashboard für DLP-Warnungen, um Warnungen zu konfigurieren, zu überprüfen, zu selektieren und die Auflösung von DLP-Warnungen nachzuverfolgen. Hier ist ein Beispiel für Warnungen, die von Richtlinienüberstimmungen und Aktivitäten von Windows 10 Geräten generiert werden.

> [!div class="mx-imgBorder"]
> ![Warninformationen](../media/Alert-info-1.png)

Sie können ebenfalls Details des zugehörigen Ereignisses mit umfangreichen Metadaten im gleichen Dashboard anzeigen.

> [!div class="mx-imgBorder"]
> ![Ereignisinformationen](../media/Event-info-1.png)

### <a name="reports"></a>Berichte

Die [DLP-Berichte](view-the-dlp-reports.md#view-the-reports-for-data-loss-prevention) zeigen allgemeine Trends im Laufe der Zeit und geben spezifische Einblicke in:

- **DLP-Richtlinienüberstimmungen** im Laufe der Zeit und Filtern nach Datumsbereich, Speicherort, Richtlinie oder Aktion
- **DLP-Vorfallübereinstimmungen** zeigen auch Übereinstimmungen im Laufe der Zeit an, aber Pivots für die Elemente und nicht für die Richtlinienregeln.
- **Falsch positive DLP-Ergebnisse und Außerkraftsetzungen** zeigen die Anzahl falsch positiver Ergebnisse und, falls konfiguriert, Benutzerüberschreibungen zusammen mit der Benutzerausrichtung an.

### <a name="dlp-activity-explorer"></a>DLP-Aktivitäts-Explorer

Auf der Registerkarte "Aktivitäten-Explorer" auf der DLP-Seite ist der *Aktivitätsfilter* auf *DLPRuleMatch* voreingestellt. Verwenden Sie dieses Tool, um Aktivitäten im Zusammenhang mit Inhalten zu überprüfen, die vertrauliche Informationen enthalten oder Bezeichnungen angewendet haben, z. B. welche Bezeichnungen geändert wurden, Dateien geändert wurden und mit einer Regel übereinstimmten.

![Screenshot des DLPRuleMatch-Aktivitäten-Explorers mit Bereichsdefinition](../media/dlp-activity-explorer.png)

Weitere Informationen finden Sie unter [Erste Schritte mit dem Aktivitäten-Explorer](data-classification-activity-explorer.md)

Weitere Informationen zu Microsoft 365 DLP finden Sie unter:

- [Informationen zu Microsoft 365 Endpunkt-DLP (Data Loss Prevention, Verhinderung von Datenverlust)](endpoint-dlp-learn-about.md)
- [Weitere Informationen zur Standardrichtlinie zur Verhinderung von Datenverlust in Microsoft Teams (Vorschau)](dlp-teams-default-policy.md)
- [Erfahren Sie mehr über den lokalen Microsoft 365-Scanner zur Verhinderung von Datenverlust (Vorschau)](dlp-on-premises-scanner-learn.md)
- [Erfahren Sie mehr über die Microsoft Compliance-Erweiterung (Vorschau)](dlp-chrome-learn-about.md)
- [Informationen zum Dashboard zur Verhinderung von Datenverlust](dlp-alerts-dashboard-learn.md)

Informationen zur Verwendung der Verhinderung von Datenverlust zur Einhaltung von Datenschutzbestimmungen finden Sie unter [Bereitstellen des Informationsschutzes für Datenschutzbestimmungen mit Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy).
