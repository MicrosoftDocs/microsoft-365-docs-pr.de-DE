---
title: Exportieren und Herunterladen von Inhalten aus einem Core eDiscovery-Fall
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
description: Beschreibt das Exportieren und Herunterladen von Inhalten aus einem Core eDiscovery-Fall in Microsoft 365.
ms.openlocfilehash: 8eb54e23369ef682e8aa1ebf7e681eb34444f1cd
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52310842"
---
# <a name="export-content-from-a-core-ediscovery-case"></a>Exportieren von Inhalten aus einem Core eDiscovery-Fall

Nachdem eine Einem Core eDiscovery-Fall zugeordnete Suche erfolgreich ausgeführt wurde, können Sie die Suchergebnisse exportieren. Beim Exportieren von Suchergebnissen werden Postfachelemente in PST-Dateien oder als einzelne Nachrichten heruntergeladen. Wenn Sie Inhalte aus SharePoint und OneDrive for Business exportieren, werden Kopien von systemeigenen Office und anderen Dokumenten exportiert. Eine Results.csv, die Informationen zu jedem exportierten Element enthält, und eine Manifestdatei (im XML-Format), die Informationen zu jedem Suchergebnis enthält, wird ebenfalls exportiert.
  
## <a name="export-search-results"></a>Exportieren von Suchergebnissen

1. Wechseln Sie zu, und melden Sie sich mit den Anmeldeinformationen für ein Benutzerkonto an, dem die entsprechenden [https://compliance.microsoft.com](https://compliance.microsoft.com) eDiscovery-Berechtigungen zugewiesen wurden.

2. Klicken Sie im linken Navigationsbereich Microsoft 365 Compliance Center auf Alle **anzeigen,** und klicken Sie dann auf **eDiscovery > Core**.

3. Klicken Sie auf der Seite **Core eDiscovery** auf den Namen des Falls, in dem Sie den Haltebereich erstellen möchten.

4. Klicken Sie **auf der** Startseite für den Fall auf **die** Registerkarte Suchen.

5. Klicken Sie **im** Menü Aktionen unten auf der Flyoutseite auf **Ergebnisse exportieren.**

   ![Export results option in Actions menu](../media/ActionMenuExportResults.png)

   Der Workflow zum Exportieren der Ergebnisse einer Suche, die einem Core eDiscovery-Fall zugeordnet ist, entspricht dem Exportieren der Suchergebnisse für eine Suche auf der Seite **Inhaltssuche.** Schrittweise Anweisungen finden Sie unter [Exportieren von Inhaltssuchergebnissen](export-search-results.md).

   > [!NOTE]
   > Beim Exportieren von Suchergebnissen haben Sie die Möglichkeit, die Deduplizierung zu aktivieren, sodass nur eine Kopie einer E-Mail-Nachricht exportiert wird, obwohl in den durchsuchten Postfächern möglicherweise mehrere Instanzen derselben Nachricht gefunden wurden. Weitere Informationen zur Deduplizierung und zur Ermittlung doppelter Elemente finden Sie unter [Deduplizierung in eDiscovery-Suchergebnissen.](de-duplication-in-ediscovery-search-results.md)

   Nachdem Sie den Export gestartet haben, werden die Suchergebnisse zum Herunterladen vorbereitet, d. h. sie werden an einen von Microsoft bereitgestellten Azure Storage in der Microsoft Cloud übertragen.
  
6. Klicken Sie **in der Fall** auf die Registerkarte Exporte, um die Liste der Exportaufträge anzeigen zu können.
  
   ![Exportieren von Aufträgen auf der Registerkarte Export im Fall Core eDiscovery](../media/CoreeDiscoveryExport.png)

   Möglicherweise müssen Sie auf **Aktualisieren klicken,** um die Liste der Exportaufträge so zu aktualisieren, dass der erstellte Exportauftrag angezeigt wird. Exportaufträge haben denselben Namen wie die entsprechende Suche mit **_Export** an den Suchnamen angefügt.

7. Klicken Sie auf den exportauftrag, den Sie erstellt haben, um Statusinformationen auf der Flyoutseite anzeigen zu können. Diese Informationen enthalten den Prozentsatz der Elemente, die an den Speicherort Azure Storage wurden.

8. Nachdem alle Elemente übertragen wurden, klicken Sie auf **Ergebnisse herunterladen,** um die Suchergebnisse auf Ihren lokalen Computer herunterzuladen. Weitere Informationen zum Herunterladen von Suchergebnissen finden Sie unter Schritt 2 unter [Exportieren von Inhaltssuchergebnissen.](export-search-results.md#step-2-download-the-search-results)

### <a name="more-information-about-exporting-searches-from-a-case"></a>Weitere Informationen zum Exportieren von Suchen aus einem Fall

- Weitere Informationen zu den Exportdateien, die beim Exportieren von Suchergebnissen enthalten sind, finden Sie unter [Export a Content search report](export-a-content-search-report.md#whats-included-in-the-report).

- Wenn Sie den Export neu starten, wirken sich alle Änderungen an den Abfragen der Suchanfragen, aus der der Exportauftrag ist, nicht auf die abgerufenen Suchergebnisse aus. Wenn Sie einen Export neu starten, wird derselbe kombinierte Suchabfrageauftrag, der beim Erstellen des Exportauftrags ausgeführt wurde, erneut ausgeführt.

- Wenn Sie einen Export neu starten, werden die Suchergebnisse, die an den Speicherort Azure Storage, die vorherigen Ergebnisse überschrieben. Die vorherigen kopierten Ergebnisse stehen nicht zum Herunterladen zur Verfügung.
