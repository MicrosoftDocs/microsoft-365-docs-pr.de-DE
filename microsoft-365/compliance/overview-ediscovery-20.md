---
title: Übersicht über die Advanced eDiscovery-Lösung in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Dieser Artikel gibt eine Übersicht über Advanced eDiscovery in Microsoft 365, ein Tool für interne und externe Ermittlungen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6225411bcd3051c19e22fcb205cc7dee92f99f82
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131028"
---
# <a name="overview-of-the-advanced-ediscovery-solution-in-microsoft-365"></a>Übersicht über die Advanced eDiscovery-Lösung in Microsoft 365

Die Advanced eDiscovery-Lösung in Microsoft 365 basiert auf den vorhandenen eDiscovery- und Analysefunktionen in Office 365. Diese neue Lösung mit dem Namen *Advanced eDiscovery* bietet einen End-to-End-Workflow zum Beibehalten, Sammeln, Überprüfen, Analysieren und Exportieren von Inhalten, die auf die internen und externen Ermittlungen Ihrer Organisation abgestimmt sind. Außerdem können Rechtsteams den gesamten Benachrichtigungs-Workflow einsehen, der für juristische Zwecke aufbewahrt wurde, und so mit den an einem Fall beteiligten Verwahrern kommunizieren. 

> [!NOTE]
> Für Advanced eDiscovery ist ein Abonnement für Office 365 oder Microsoft 365 E5 Enterprise erforderlich. Weitere Informationen zur erweiterten eDiscovery-Lizenzierung finden Sie unter [Microsoft 365 Licensing Guidance for Security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#advanced-ediscovery).

## <a name="alignment-with-edrm"></a>Angepasste EDRM

Der integrierte Arbeitsablauf von Advanced eDiscovery stimmt mit dem eDiscovery-Prozess überein, der durch das EDRM (Electronic Discovery Reference Model) beschrieben wird. 

![Das EDRM (Electronic Discovery Reference Model)](../media/EDRMv1.png)

(Bildquelle mit freundlicher Genehmigung von edrm.net. Das Quellbild wurde unter der nicht portierbaren Lizenz von Creative Commons-Namensnennung 3.0 bereitgestellt.)

So unterstützt Advanced eDiscovery den EDRM-Workflow auf hohem Niveau:

- **Erkennen.** Nachdem Sie potenzielle Personen von Interesse in einer Ermittlung identifiziert haben, können Sie diese als Verwahrer (auch *Datenverwahrer* genannt, da sie möglicherweise über Informationen verfügen, die für die Ermittlung relevant sind) zu einem Advanced eDiscovery-Fall hinzufügen. Nachdem Sie Verwalter identifiziert und zu einem Fall hinzugefügt haben, können Sie die zugeordneten Freiheits Daten auf einfache Weise beibehalten, sammeln, überprüfen und analysieren.

- **Beibehaltung.** Um Daten, die für eine Ermittlung relevant sind, zu erhalten und zu schützen, können Sie mit Advanced eDiscovery die Datenquellen, die mit den Verwahrern eines Falles in Verbindung stehen, im Aufbewahrung für juristische Zwecke setzen. Sie können auch Daten für nicht-Freiheitsentzug (in der Regel freigegebene Gruppen Ressourcen wie SharePoint-Websites oder Kanäle für freigegebene Teams) speichern. Advanced eDiscovery verfügt auch über einen integrierten Kommunikations-Workflow, so dass Sie Benachrichtigungen per Aufbewahrung für juristische Zwecke an Verwahrer senden und deren Bestätigungen verfolgen können.

- **Sammlung.** Nachdem Sie die für die Untersuchung relevanten Datenquellen identifiziert (und optional aufbewahrt) haben, können Sie das integrierte Such Tool in Advanced eDiscovery verwenden, um Live-Daten aus den Datenquellen für den Freiheitsentzug (und ggf. aus Datenquellen ohne Freiheitsentzug) zu suchen und zu sammeln, die für den Fall relevant sein können.

- **Verarbeitung.** Nachdem Sie alle für den Fall relevanten Daten gesammelt haben, besteht der nächste Schritt darin, Sie zur weiteren Überprüfung und Analyse zu verarbeiten. In Advanced eDiscovery werden die in der Sammlungsphase identifizierten in-Place-Daten in einen Azure-Speicherort (als *Überprüfungsgruppe* bezeichnet) kopiert, der eine statische Ansicht der Falldaten bereitstellt.

- **Prüfung.** Nachdem einem Überprüfungs Satzes Daten hinzugefügt wurden, können Sie bestimmte Dokumente anzeigen und weitere Abfragen innerhalb des Überprüfungs Satzes ausführen, um die Daten auf die relevantesten Dokumente zu reduzieren. Sie können auch bestimmte Dokumente mit Anmerkungen versehen und kennzeichnen.

- **Analyse.** Advanced eDiscovery bietet eine leistungsstarke Reihe integrierter Analysetools, mit denen Sie irrelevante Daten aus dem Überprüfungspaket Intelligent ausmerzen können, wodurch Sie die Kosten für die rechtliche Überprüfung durch eine effiziente Verringerung der Menge relevanter Daten für die Produktion sparen.

- **Erstellung** und **Präsentation.** Wenn Sie so weit sind, können Sie Dokumente aus einem Prüfdateisatz zur rechtlichen Prüfung exportieren. Sie können Dokumente in Ihrem von EDRM angegebenen Format exportieren, damit Sie in Überprüfungs Anwendungen von Drittanbietern importiert werden können.

## <a name="advanced-ediscovery-architecture"></a>Erweiterte eDiscovery-Architektur

Im folgenden finden Sie ein erweitertes eDiscovery-Architekturdiagramm, das den End-to-End-Workflow in einer Umgebung mit einem einzelnen Geo und einer Multi-Geo-Umgebung zeigt. Der End-to-End-Datenfluss wird mit dem EDRM ausgerichtet.

[![Modell Poster: Erweiterte eDiscovery-Architektur in Microsoft 365](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[Als Bild anzeigen](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[Als PDF-Datei herunterladen](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.pdf)

[Als Visio-Datei herunterladen](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.vsdx)

Weitere Informationen über den End-to-End-Workflow in Advanced eDiscovery finden Sie in diesem [Microsoft Mechanics-Video](https://go.microsoft.com/fwlink/?linkid=2066133).

In den folgenden Abschnitten werden die einzelnen Schritte des integrierten Workflows in Advanced eDiscovery beschrieben. Der folgende Screenshot zeigt die Registerkarte **Übersicht** eines Falls mit dem Namen *2020.11.03-Contoso v. fabrikam*.

![Registerkarten im integrierten erweiterten eDiscovery-Workflow](../media/AeD-Case-Screenshot1.png)

## <a name="managing-custodians-and-non-custodial-data-sources"></a>Verwalten von Depotbanken und Datenquellen ohne Freiheitsentzug

Verwenden Sie die Registerkarte **Datenquellen** , um Personen hinzuzufügen und zu verwalten, die Sie im Fall als interessierte Personen identifiziert haben, und andere Datenquellen, die möglicherweise nicht einer Depotbank zugeordnet sind. Wenn Sie Verwalter oder Datenquellen ohne Freiheitsentzug hinzufügen, können Sie schnell Aktionen durchführen, wie das Aufbewahren einer Aufbewahrungspflicht für Depotbank-und nicht-Freiheitsentzug-Datenquellen, die Kommunikation mit den Verwaltern und das Durchsuchen von Depotbank-und nicht-Freiheitsentzug-Datenquellen, um relevante Inhalte für den Fall zu sammeln. Wenn der Fall fortschreitet, ist es ganz einfach, neue Verwalter oder Datenquellen ohne Freiheitsentzug hinzuzufügen oder aus dem Fall freizugeben. Weitere Informationen finden Sie unter [Arbeiten mit Verwahrern in Advanced eDiscovery](managing-custodians.md).

## <a name="managing-legal-hold-notifications"></a>Verwaltung von Benachrichtigungen über Aufbewahrung für juristische Zwecke

Verwenden Sie die Registerkarte **Kommunikation**, um den Prozess der Kommunikation mit den Verwahrern des Falls zu verwalten. Eine Mitteilung zum Aufbewahrung für juristische Zwecke weist die Verwahrer an, alle Inhalte, die für den Fall relevant sind, aufzubewahren. Zugelassene Teams müssen die Benachrichtigungen nachverfolgen, die von den Verwaltern empfangen, gelesen und bestätigt wurden. Der Kommunikations-Workflow in Advanced eDiscovery ermöglicht es Ihnen, Erstbenachrichtigungen, Erinnerungen, Freigabebescheide und Eskalationen zu erstellen und zu versenden, wenn die Verwahrer eine Hold-Benachrichtigung nicht bestätigen. Weitere Informationen finden Sie unter [Arbeiten mit Kommunikationen in Advanced eDiscovery](managing-custodian-communications.md).

## <a name="managing-content-preservation"></a>Verwaltung der Beibehaltung von Inhalten

Wenn Sie einen Verwahrer zu einem Fall hinzufügen, können Sie die Verwahrungsdaten im Haltebereich setzen. Verwenden Sie die Registerkarte **halten** , um den beim Hinzufügen von Depot erstellen erstellten Haltestatus zu verwalten und andere dem Fall zugeordnete Rechtliche Aufbewahrungspflicht zu verwalten. Sie können beispielsweise Datenquellen ohne Freiheitsentzug identifizieren und aufbewahren. Sie können auch jeden Haltebereich in dem Fall bearbeiten und ihn zu einem abfragebasierten Haltebereich machen, um nur den Inhalt zu erhalten, der der Abfrage entspricht. Sie könnten beispielsweise einen Datumsbereich zum Haltebereich hinzufügen, so dass nur Inhalte, die innerhalb eines bestimmten Datums erstellt wurden, erhalten bleiben. Sie können auch Statistiken über Inhalte im Haltebereich abrufen, den Haltebereich entfernen, nachdem er für den Fall nicht mehr relevant ist, oder ihn löschen. Weitere Informationen finden Sie unter [Verwalten von Haltebereichen in Advanced eDiscovery](managing-holds.md).

## <a name="indexing-custodian-data"></a>Indizierung von Verwahrungsdaten

Wenn Sie einem Fall eine Depotstelle und die entsprechenden Datenquellen für den Freiheitsentzug hinzufügen, wird jedes teilweise indizierte Element aus einer Depotbank-Datenquelle durch einen Prozess mit dem Namen *Erweiterte Indizierung* neu indiziert. Dadurch können Verwahrungsinhalte wie Bilder, nicht unterstützte Dateitypen und andere potenziell nicht indizierte Inhalte vollständig durchsuchbar sein, wenn Sie Suchvorgänge durchführen, um Daten für den Fall zu sammeln. Verwenden Sie die Registerkarte **Verarbeitung**, um den Status der erweiterten Indizierung zu überwachen und Verarbeitungsfehler mit Hilfe eines Prozesses namens *Fehlerbehebung* zu beheben. Weitere Informationen finden Sie unter [Fehlerbehebung von Verarbeitungsfehlern in Advanced eDiscovery](processing-data-for-case.md).

## <a name="collecting-case-data"></a>Erfassen von Falldaten

Verwenden Sie die Registerkarte **Suchvorgänge**, um Suchvorgänge zu erstellen, mit denen die lokalen und nicht-verwahrten Datenquellen nach für den Fall relevanten Inhalten durchsucht werden können. Sie können abfragebasierte Suchvorgänge erstellen und ausführen (unter Verwendung von Schlüsselwörtern und Bedingungen), um eine Gruppe von e-Mail-Nachrichten und Dokumenten zu identifizieren, die für den Fall relevant sind und die Sie in den folgenden Schritten im eDiscovery-Workflow weiter überprüfen und analysieren möchten. Sie können eine oder mehrere Suchvorgänge im Zusammenhang mit dem Fall erstellen. Sie können das Suchtool auch zur Vorschau von Beispieldokumenten und zur Anzeige von Suchstatistiken verwenden, um die Suchergebnisse zu verfeinern und zu verbessern. Nachdem Sie alle für den Fall relevanten Daten durchsucht und gesammelt haben, können Sie die Suchergebnisse zu einer Überprüfungsgruppe hinzufügen, um Sie zu überprüfen, zu analysieren und zu Keulen. Weitere Informationen finden Sie unter [Sammeln von Daten für einen Fall in Advanced eDiscovery](collecting-data-for-ediscovery.md).

## <a name="reviewing-and-analyzing-case-data"></a>Prüfen und Analysieren von Falldaten

Verwenden Sie die Registerkarte **Überprüfungs Sätze** zum Überprüfen und Analysieren der Inhalte, die Sie im Live-System gesammelt haben, und zu einem Überprüfungs Satz hinzugefügt. Ein *Überprüfungs Satz* ist eine statische Sammlung dieser Daten (mit anderen Worten: eine Offlinekopie von Daten) von Daten für den Freiheitsentzug (und, falls zutreffend, Daten ohne Freiheitsentzug), die Sie in der vorherigen Phase des eDiscovery-Workflows gesammelt haben. Wenn Sie einer Überprüfungsgruppe Suchergebnisse hinzufügen, wird ein Prozess ausgelöst, um Dateien aus Containern zu extrahieren, Metadaten zu extrahieren und Text zu extrahieren. Wenn dieser Prozess abgeschlossen ist, erstellt das System einen neuen Index aller von den Verwahrern gesammelten Daten und fügt sie dem Prüfdateisatz hinzu. Nachdem die Daten dem Prüfdateisatz hinzugefügt wurden, können Sie weitere Abfragen ausführen, um die Falldaten einzugrenzen, Daten als Text oder im nativen Dateiformat anzuzeigen und Dokumente im Prüfdateisatz zu kommentieren, zu redigieren und zu bezeichnen. Sie können auch erweiterte Analysen durchführen, beispielsweise das Identifizieren von Dokument Duplikaten, e-Mail-Threads und Designs. Nachdem Sie die Daten nur auf die für den Fall relevanten Daten selektiert haben, können Sie die Dokumente entweder direkt herunterladen oder zusammen mit Dateimetadaten, Anmerkungen und beliebigen Tags exportieren. Weitere Informationen finden Sie unter:

- [Anzeigen von Dokumenten in einem Prüfdateisatz](view-documents-in-review-set.md)

- [Abfragen der Daten in einem Prüfdateisatz](review-set-search.md)

- [Markieren von Dokumenten in einem Prüfdateisatz](tagging-documents.md)

- [Analysieren von Daten in einem Prüfdateisatz](analyzing-data-in-review-set.md)

## <a name="exporting-data-for-review-and-presentation"></a>Exportieren von Daten für die Prüfung und Präsentation

Nachdem Sie die Daten aus einem Prüfdateisatz exportiert haben, verwenden Sie die Registerkarte **Exporte**, um einen Exportauftrag zu verwalten und Daten aus einem Prüfdateisatz herunterzuladen. Wenn Sie einen Prüfdateisatz exportieren, werden die Daten in einen von Microsoft bereitgestellten Azure-Speicherort (oder einen von Ihrer Organisation verwalteten Azure-Speicherort) hochgeladen. Nachdem er auf Azure hochgeladen wurde, steht er dann zum Download auf einen lokalen Computer zur Verfügung. Sie können die Speicherzugriffs Taste abrufen, die zum Herunterladen der exportierten Daten auf der Registerkarte **Exports** erforderlich ist. Weitere Informationen finden Sie unter [Exportieren von Case-Daten in Advanced eDiscovery](exporting-data-ediscover20.md).

## <a name="managing-jobs"></a>Verwalten der Aufträge

Verwenden Sie die Registerkarte **Aufträge**, um lang andauernde Prozesse für fallbezogene Aufgaben, die Sie initiiert haben, zu überwachen. Beispiele für Aufträge sind solche, die sich auf das erneute Indizieren, Suche und den Export von Falldaten beziehen. Wenn Sie z. B. auf der Registerkarte **Suchvorgänge** eine Suche erstellen, die viele Datenquellen umfasst, wird der Status dieses Suchvorgangs auf der Registerkarte **Aufträge** angezeigt. Weitere Informationen finden Sie unter [Verwalten von Aufträgen in Advanced eDiscovery](managing-jobs-ediscovery20.md).

## <a name="configuring-case-settings"></a>Konfigurieren von Falleinstellungen

Verwenden Sie die Registerkarte **Einstellungen**, um fallweite Einstellungen zu konfigurieren. Dazu gehören das Hinzufügen von Mitgliedern zu einem Fall, das Schließen oder Löschen eines Falls und die Konfiguration von Such- und Analyseeinstellungen.
