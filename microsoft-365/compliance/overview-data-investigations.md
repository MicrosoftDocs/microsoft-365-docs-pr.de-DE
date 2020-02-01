---
title: Übersicht über Daten Untersuchungen (Vorschau) in Microsoft 365
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: In diesem Artikel wird das Tool für neue Daten Untersuchungen (Preview) in Microsoft 365 beschrieben.
ms.openlocfilehash: cd60b16f6d0f968c0c87f3e44ee2f643c90ebb10
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597792"
---
# <a name="overview-of-data-investigations-preview-in-microsoft-365"></a>Übersicht über Daten Untersuchungen (Vorschau) in Microsoft 365

Ein Datenüberlauf tritt auf, wenn ein Dokument mit vertraulichen, vertraulichen oder böswilligen Inhalten in einer nicht vertrauenswürdigen Umgebung freigegeben wird. Wenn ein Datenüberlauf erkannt wird, ist es wichtig, die Umgebung schnell einzudämmen, die Größe und die Speicherorte des Verfalls zu bewerten, Benutzeraktivitäten um Sie herum zu untersuchen und dann die verschütteten Daten aus dem Dienst zu löschen. Mit dem Tool neue Daten Untersuchungen (Vorschau) können Sie nach vertraulichen, böswilligen oder verfallenen Daten in Office 365 suchen, die Ereignisse untersuchen und die entsprechenden Aktionen zum Beheben des Verfalls durchführen.  

In diesem Artikel wird die Verwendung der Funktionen im Tool für die neue Daten Untersuchung (Preview) beschrieben, mit denen ein Szenario mit Datenüberlauf behandelt wird.

## <a name="permissions"></a>Berechtigungen

Sie müssen Mitglied der Rollengruppe "Data Investigator" sein, um auf eine Daten Untersuchung zugreifen und diese durchführen zu können. Weitere Informationen finden Sie unter [assign Permissions for Data Investigations](permissions.md).

## <a name="data-investigations-preview-workflow"></a>Workflow für Daten Untersuchungen (Vorschau) 

In den folgenden Abschnitten werden die einzelnen Schritte des integrierten Workflows in Data Investigations (Preview) beschrieben. Der folgende Screenshot zeigt die Registerkarte **Startseite** einer Untersuchung mit dem Namen " *High Risk: Finance Documents Leak*". 

![Workflow im Data Investigations-Tool](media/DataInvestigationsWorkflow.png)

## <a name="search-for-sensitive-malicious-or-misplaced-data"></a>Suchen nach vertraulichen, böswilligen oder verlegenen Daten

Verwenden Sie die Registerkarte **Suchen** , um Suchvorgänge zu erstellen, um nach der Office 365 für Daten zu suchen, die Sie korrigieren möchten. Sie können abfragebasierte Suchvorgänge erstellen und ausführen, um festgelegte e-Mail-Nachrichten und Dokumente zu identifizieren, die möglicherweise verschüttete Daten enthalten, und diese dann als Beweise zum Überprüfen und analysieren sammeln. Außerdem können Sie das Such Tool verwenden, um eine Vorschau von Beispiel Dokumenten anzuzeigen und Suchstatistiken anzuzeigen, mit denen Sie die Suchergebnisse verfeinern und verbessern können. Nachdem Sie sichergestellt haben, dass die Suchergebnisse alle für die Untersuchung relevanten Daten enthalten, fügen Sie die Suchergebnisse dem festgelegten Beweis zur weiteren Überprüfung, zur Folgenabschätzung und gegebenenfalls zur Beachtung von Korrekturaktionen hinzu. Weitere Informationen finden Sie unter [Suchen nach Daten in einer Untersuchung](search-for-data.md).

## <a name="review-and-investigate-evidence"></a>Überprüfen und untersuchen von beweisen

Verwenden Sie die Registerkarte **Beweise** , um die Daten zu untersuchen, die Sie im Live-Dienst gesammelt haben, was in diesem Fall Office 365 ist. Die Daten im Beweissatzes sind eine Momentaufnahme der Suchergebnisse, die Sie gesammelt haben. Wenn Sie Suchergebnisse als Beweise hinzufügen, wird ein Prozess ausgelöst, um Dateien, Metadaten und Text zu extrahieren. Wenn dieser Vorgang abgeschlossen ist, erstellt das Tool Daten Untersuchungen einen neuen Index aller Daten und fügt ihn einem Beweissatz hinzu. Bei zeitkritischen Untersuchungen können Sie dadurch die Umgebung schnell eindämmen, indem Sie Daten löschen, die sich an den ursprünglichen Inhaltsspeicherorten (im Live-Dienst) befinden, während Sie die in einer isolierten Umgebung gesammelten Beweise untersuchen. Nachdem Sie Beweise gesammelt haben, können Sie weitere Abfragen ausführen, um die Daten nach Zeitbereich, Dateitypen, Datenbesitzern und anderen Arten von Bedingungen einzugrenzen. Beispielsweise können Sie mithilfe der Bedingungen des Autors, des Absenders und des Empfängers schnell erkennen, wer am Datenüberlauf beteiligt war und ob eine der verschütteten Daten für Personen außerhalb Ihrer Organisation freigegeben wurde.

Sie können auch erweiterte Analysen für die gesammelten Beweise ausführen. Dadurch können Sie allgemeine Designs bereitstellen und Beweise per e-Mail-Threads, exakte Duplikate und nahe Duplikate organisieren, um Ihre Untersuchung zu erleichtern. Sie können Dokumente in extrahierter Textansicht oder im systemeigenen Dateiformat überprüfen und mit Ermittlungsergebnissen versehen. Weitere Informationen finden Sie unter:

  - [Überprüfen von Nachweisdaten](review-data-in-evidence.md)

  - [Durchführen von Analysen zur schnelleren Untersuchung](run-analytics-to-investigate-faster.md)


## <a name="managing-people-of-interest"></a>Verwalten von Personen von Interesse

Verwenden Sie die Registerkarte **Personen von Interesse** , um die Personen hinzuzufügen und zu verwalten, die Sie während der Untersuchung der Beweise als interessante Personen identifiziert haben. Wenn Sie interessante Personen hinzufügen, werden Ihre Datenquellen, wie Ihr Postfach und Ihr OneDrive-Konto, identifiziert und zugeordnet. Anschließend können Sie Suchbereiche durchsuchen, indem Sie nur die inhaltsspeicherorte dieser Personen durchsuchen. Wenn der Bereich von Personen von Interesse ist, sind Suchvorgänge effizienter und genauer, da das Tool alle nicht indizierten Daten wie Bilder oder nicht unterstützte Dateitypen neu verarbeitet. Auf der Registerkarte **Personen von Interesse** können Sie auch die Überwachungsprotokoll Aktivität dieser Personen anzeigen und Durchsuchen, um die Untersuchung weiter zu unterstützen. Sie können während der Untersuchung weitere interessante Personen hinzufügen. Weitere Informationen finden Sie unter [Verwalten von Personen mit Interesse einer Untersuchung](manage-people-of-interest.md).

## <a name="indexing-the-data-of-people-of-interest"></a>Indizieren der Daten von Personen von Interesse

Durch das Hinzufügen einer Person, die für eine Untersuchung interessant ist, werden alle teilweise indizierten Elemente aus den Datenquellen der Person neu indiziert. Dieser Vorgang wird als *Erweiterte Indizierung*bezeichnet. Durch die erweiterte Indizierung werden Daten wie Bilder und nicht unterstützte Dateitypen erneut verarbeitet, sodass diese Daten vollständig auffindbar sind, wenn Sie Suchvorgänge ausführen, um Daten für eine Untersuchung zu erfassen. Verwenden Sie die Registerkarte **Verarbeitung** , um den Status der erweiterten Indizierung zu überwachen und etwaige Verarbeitungsfehler zu beheben, die bei einem Prozess mit dem Namen *Fehlerbehebung*auftreten können. Weitere Informationen finden Sie unter [Fehlerkorrektur bei der Verarbeitung von Daten für eine Untersuchung](error-remediation.md).

## <a name="exporting-data"></a>Exportieren von Daten

Wenn Sie Daten exportieren möchten, verwenden Sie die Registerkarte **Exports** , um einen Exportauftrag zu verwalten und Daten aus dem Evidence-Datensatz herunterzuladen. Wenn Sie Beweise exportieren, werden die Daten in einen Azure-Speicherort hochgeladen und stehen dann auf einem lokalen Computer heruntergeladen. Auf der Registerkarte **Exports** können Sie die Azure-Speicherorts-URL und den Speicher Bewertungsschlüssel abrufen, die beide zum Herunterladen der exportierten Daten erforderlich sind. Weitere Informationen finden Sie unter [Exportieren von Daten aus einer Untersuchung](export-data.md).

## <a name="managing-jobs"></a>Verwalten der Aufträge

Verwenden Sie die Registerkarte **Aufträge** , um die langwierigen Prozesse für Aufgaben im Zusammenhang mit der Untersuchung zu überwachen. Dies umfasst Aufträge zum Ausführen von suchen, Hinzufügen von Daten zu einem Beweissatz, Neuindizieren von Daten und Exportieren von nachweisen. Sie können beispielsweise eine Suche auf der Registerkarte **Suchen** erstellen, die viele Datenquellen enthält. Der Status dieses Suchvorgangs wird auf der Registerkarte **Aufträge** angezeigt. Weitere Informationen finden Sie unter [Manage Jobs in a Data Investigation](manage-jobs.md).

## <a name="configuring-investigation-settings"></a>Konfigurieren von Untersuchungseinstellungen

Verwenden Sie die Registerkarte **Einstellungen** , um Untersuchungs weite Einstellungen zu konfigurieren. Dies umfasst das Hinzufügen von Mitgliedern zu einer Untersuchung, das Schließen oder Löschen einer Untersuchung und das Konfigurieren des Such-und Analyse Verhaltens.
