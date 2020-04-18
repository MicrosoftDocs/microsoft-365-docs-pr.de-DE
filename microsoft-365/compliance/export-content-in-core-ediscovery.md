---
title: Exportieren und Herunterladen von Inhalten aus einem zentralen eDiscovery-Fall
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: In diesem Artikel wird beschrieben, wie Sie Inhalte aus einem zentralen eDiscovery-Fall exportieren und herunterladen.
ms.openlocfilehash: e0d4315c48a0d0878b8052265ff8663cd1987169
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551385"
---
# <a name="export-content-from-a-core-ediscovery-case"></a>Exportieren von Inhalten aus einem zentralen eDiscovery-Fall

Nachdem eine Suche erfolgreich ausgeführt wurde, können Sie die Suchergebnisse exportieren. Wenn Sie Suchergebnisse exportieren, werden Postfachelemente in PST-Dateien oder als einzelne Nachrichten heruntergeladen. Wenn Sie Inhalte aus SharePoint und OneDrive für Unternehmen Websites exportieren, werden Kopien von systemeigenen Office-Dokumenten und anderen Dokumenten exportiert. Eine results. CSV-Datei, die Informationen zu jedem exportierten Element enthält, und eine Manifestdatei (im XML-Format), die Informationen zu jedem Suchergebnis enthält, wird ebenfalls exportiert.
  
Sie können die Ergebnisse einer einzelnen Suche exportieren, die [einem Fall zugeordnet](#export-the-results-of-a-single-search) ist, oder Sie können die Ergebnisse [mehrerer Suchvorgänge exportieren, die einem Fall zugeordnet sind](#export-the-results-of-multiple-searches).
  
## <a name="export-the-results-of-a-single-search"></a>Exportieren der Ergebnisse einer einzelnen Suche

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) zu, und melden Sie sich mit den Anmeldeinformationen für das Benutzerkonto an, dem die entsprechenden eDiscovery-Berechtigungen zugewiesen wurden.

2. Klicken Sie im linken Navigationsbereich des Microsoft 365 Compliance Center auf **Alle anzeigen**, und klicken Sie dann auf **eDiscovery > Kern**.

3. Wählen Sie auf der **zentralen eDiscovery** -Seite den Fall aus, aus dem Sie Suchergebnisse exportieren möchten, und klicken Sie dann auf **Groß-/Kleinschreibung öffnen**.

4. Klicken Sie auf der **Start** Seite für den Fall auf die Registerkarte **Suchen** .

5. Klicken Sie in der Liste der Suchvorgänge für den Fall auf die Suche, aus der Sie Suchergebnisse exportieren möchten, und klicken Sie dann im Flyout auf **Ergebnisse exportieren** .

    Die Seite **Ergebnisse exportieren** wird angezeigt. 

    ![Seite "Ergebnisse exportieren"](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    Der Workflow zum Exportieren der Ergebnisse einer Suche, die einem zentralen eDiscovery-Fall zugeordnet ist, entspricht dem Exportieren der Suchergebnisse für eine Suche auf der Seite **Inhaltssuche** . Eine Schritt-für-Schritt-Anleitung finden Sie unter [Exportieren von Inhalts Suchergebnissen](export-search-results.md).

    > [!NOTE]
    > Wenn Sie Suchergebnisse exportieren, haben Sie die Möglichkeit, die Deduplizierung zu aktivieren, sodass nur eine Kopie einer e-Mail-Nachricht exportiert wird, obwohl in den durchsuchten Postfächern möglicherweise mehrere Instanzen derselben Nachricht gefunden wurden. Weitere Informationen zur Deduplizierung und zur Identifizierung von doppelten Elementen finden Sie unter [Deduplizierung in eDiscovery-Suchergebnissen](de-duplication-in-ediscovery-search-results.md).

    Nachdem Sie den Export gestartet haben, werden die Suchergebnisse zum Herunterladen vorbereitet, was bedeutet, dass Sie in einen von Microsoft bereitgestellten Azure-Speicherort in der Microsoft-Cloud hochgeladen werden.
  
6. Klicken Sie auf die Registerkarte **exportieren** , um die Liste der Exportaufträge für den Fall anzuzeigen.
  
    Möglicherweise müssen Sie auf **Aktualisieren** klicken, um die Liste der Exportaufträge so zu aktualisieren, dass der von Ihnen erstellte Exportauftrag angezeigt wird. Export Aufträge haben den gleichen Namen wie die entsprechende Suche, wobei **_Export** an den Such Namen angehängt wird.

7. Klicken Sie auf den von Ihnen erstellten Exportauftrag, um Statusinformationen auf der Flyout-Seite anzuzeigen. Diese Informationen enthalten den Prozentsatz der Elemente, die an den Azure-Speicherort übertragen wurden.

8. Nachdem alle Elemente übertragen wurden, klicken Sie auf **Ergebnisse herunterladen** , um die Suchergebnisse auf den lokalen Computer herunterzuladen. Weitere Informationen zum Herunterladen von Suchergebnissen finden Sie unter Schritt 2 in [Exportieren von Inhalts Suchergebnissen](export-search-results.md#step-2-download-the-search-results)

## <a name="export-the-results-of-multiple-searches"></a>Exportieren der Ergebnisse mehrerer Suchvorgänge

Als Alternative zum Exportieren der Ergebnisse einer einzelnen Suche, die einem Fall zugeordnet ist, können Sie die Ergebnisse mehrerer Suchvorgänge aus demselben Fall in einem einzelnen Exportauftrag exportieren. Das Exportieren der Ergebnisse von mehreren Suchvorgängen ist schneller und einfacher als das Exportieren der Ergebnisse um die Suche nach dem anderen.
  
> [!NOTE]
> Sie können die Ergebnisse mehrerer Suchvorgänge nicht exportieren, wenn eine dieser Suchvorgänge für Suchspeicher Orte in der Warteschleife konfiguriert wurde.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) zu, und melden Sie sich mit den Anmeldeinformationen für das Benutzerkonto an, dem die entsprechenden eDiscovery-Berechtigungen zugewiesen wurden.

2. Klicken Sie im linken Navigationsbereich des Microsoft 365 Compliance Center auf **Alle anzeigen**, und klicken Sie dann auf **eDiscovery > Kern**.

3. Wählen Sie auf der **zentralen eDiscovery** -Seite den Fall aus, aus dem Sie Suchergebnisse exportieren möchten, und klicken Sie dann auf **Groß-/Kleinschreibung öffnen**.

4. Klicken Sie auf der **Start** Seite für den Fall auf die Registerkarte **Suchen** .
    
5. Aktivieren Sie in der Liste der Suchvorgänge für den Fall das Kontrollkästchen neben mindestens zwei Suchvorgängen, aus denen Suchergebnisse exportiert werden sollen. 

   Die Flyout-Seite für **Massenaktionen** wird angezeigt. 

    ![Klicken Sie auf der Seite Massenaktionen auf Ergebnisse exportieren.](../media/f34e3707-a9c1-494f-91a4-da1165aa730a.png)
  
6. Klicken Sie auf **Ergebnisse exportieren**.

   Die Seite **Ergebnisse exportieren** wird angezeigt. 

    ![Seite "Ergebnisse exportieren"](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    An diesem Punkt ist der Workflow zum Exportieren der Ergebnisse mehrerer Suchvorgänge, die einem zentralen eDiscovery-Fall zugeordnet sind, identisch mit dem Exportieren der Suchergebnisse für eine einzelne Suche. Siehe Schritt 5 im vorherigen Abschnitt.

### <a name="more-information-about-exporting-the-results-of-multiple-searches"></a>Weitere Informationen zum Exportieren der Ergebnisse mehrerer Suchvorgänge

- Wenn Sie die Ergebnisse mehrerer Suchvorgänge exportieren, werden die Suchabfragen von allen suchen mit **oder** -Operatoren kombiniert, und dann wird die kombinierte Suche gestartet. Die geschätzten Ergebnisse der kombinierten Suche werden auf der Flyout-Seite des ausgewählten Exportauftrags angezeigt. Die Suchergebnisse werden dann in den Azure-Speicherort in der Microsoft-Cloud kopiert. Der Status des Kopierauftrags wird auch auf der Flyout-Seite angezeigt. Wie bereits erwähnt, können Sie Sie nach dem Kopieren aller Suchergebnisse auf einen lokalen Computer herunterladen.

- Die maximale Anzahl von Schlüsselwörtern aus Abfragen für alle Suchvorgänge, die Sie exportieren möchten, lautet 500. Dies ist der gleiche Grenzwert für eine einzelne Suche. Das liegt daran, dass der Exportauftrag alle Suchabfragen mit dem **or** -Operator kombiniert. Wenn Sie diesen Grenzwert überschreiten, wird ein Fehler zurückgegeben. In diesem Fall müssen Sie die Ergebnisse aus weniger Suchvorgängen exportieren oder die Suchabfragen der ursprünglichen Suchvorgänge vereinfachen, die Sie exportieren möchten.

- Die exportierten Suchergebnisse werden nach dem Inhaltsspeicherort organisiert, in dem das Element gefunden wurde. Das bedeutet, dass für eine Inhaltsposition in den Export Ergebnissen möglicherweise Elemente von unterschiedlichen Suchvorgängen zurückgegeben werden. Wenn Sie beispielsweise e-Mail-Nachrichten in einer PST-Datei für jedes Postfach exportieren möchten, hat die PST-Datei möglicherweise Ergebnisse aus mehreren Suchvorgängen.

- Wenn dasselbe e-Mail-Element oder Dokument vom gleichen Inhaltsspeicherort von mehr als einer der Suchvorgänge zurückgegeben wird, die Sie exportieren, wird nur eine Kopie des Elements exportiert.

- Sie können einen Export für mehrere Suchvorgänge nach dem Erstellen nicht bearbeiten. Beispielsweise können Sie dem Exportauftrag keine Suchvorgänge hinzufügen oder daraus entfernen. Sie müssen einen Exportauftrag erstellen, um die exportierten Suchergebnisse zu ändern. Nachdem ein Exportauftrag erstellt wurde, können Sie die Ergebnisse nur auf einen Computer herunterladen, den Export neu starten oder den Exportauftrag löschen.

- Wenn Sie den Export neu starten, wirken sich Änderungen an den Abfragen der Suchvorgänge, aus denen der Exportauftrag besteht, nicht auf die abgerufenen Suchergebnisse aus. Wenn Sie einen Export neu starten, wird derselbe kombinierte Suchabfrage Auftrag, der beim Erstellen des Exportauftrags ausgeführt wurde, erneut ausgeführt.

- Wenn Sie einen Export neu starten, überschreiben die Suchergebnisse, die an den Azure-Speicherort kopiert werden, auch die vorherigen Ergebnisse. Die vorherigen Ergebnisse, die kopiert wurden, stehen nicht zum Herunterladen zur Verfügung.

- Das Vorbereiten der Ergebnisse mehrerer Suchvorgänge für die Analyse in Advanced eDiscovery (Classic) ist nicht verfügbar. Sie können nur die Ergebnisse einer einzelnen Suche für die Analyse in Advanced eDiscovery (Classic) vorbereiten.
