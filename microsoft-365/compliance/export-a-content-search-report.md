---
title: Exportieren eines Berichts für die Inhaltssuche
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: Anstatt die tatsächlichen Ergebnisse einer Inhaltssuche im Security & Compliance Center in Office 365 zu exportieren, können Sie einen Suchergebnisseinbericht exportieren. Der Bericht enthält eine Zusammenfassung der Suchergebnisse und ein Dokument mit detaillierten Informationen zu jedem element, das exportiert werden würde.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 094e67812b45ab1544d629ba6ddabcd86c70c633
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311573"
---
# <a name="export-a-content-search-report"></a>Bericht zur Inhaltssuche exportieren

Anstatt den vollständigen Satz von Suchergebnissen aus einer Inhaltssuche im Microsoft 365 Compliance Center (oder aus einer Suche, die einem Core eDiscovery-Fall zugeordnet ist) zu exportieren, können Sie dieselben Berichte exportieren, die beim Exportieren der tatsächlichen Suchergebnisse generiert werden.
  
Wenn Sie einen Bericht exportieren, werden die Berichtsdateien in einen Ordner auf Ihrem lokalen Computer heruntergeladen, der denselben Namen wie die Inhaltssuche hat, aber dieser wird mit _ReportsOnly *.* Wenn die Inhaltssuche beispielsweise den Namen  *ContosoCase0815* hat, wird der Bericht in einen Ordner mit dem Namen *ContosoCase0815_ReportsOnly*. Eine Liste der Dokumente, die im Bericht enthalten sind, finden Sie unter [What's included in the report](#whats-included-in-the-report).

## <a name="before-you-export-a-search-report"></a>Vor dem Exportieren eines Suchberichts

- Zum Exportieren eines Suchberichts muss Ihnen die Verwaltungsrolle Compliancesuche im Security & Compliance Center zugewiesen werden. Diese Rolle wird standardmäßig den integrierten Rollengruppen eDiscovery Manager und Organization Management zugewiesen. Weitere Informationen finden Sie unter [Zuweisen von eDiscovery-Berechtigungen](assign-ediscovery-permissions.md).

- Wenn Sie einen Bericht exportieren, werden die Daten vorübergehend an einem Azure Storage in der Microsoft Cloud gespeichert, bevor sie auf Ihren lokalen Computer heruntergeladen werden. Stellen Sie sicher, dass Ihre Organisation eine Verbindung mit dem Endpunkt in Azure herstellen kann, der **\* .blob.core.windows.net** ist (der Platzhalter stellt einen eindeutigen Bezeichner für Ihren Export dar). Die Suchergebnisse werden zwei Wochen nach der Azure Storage aus dem Speicherort gelöscht.

- Der Computer, den Sie zum Exportieren der Suchergebnisse verwenden, muss die folgenden Voraussetzungen erfüllen:

  - Neueste Version von Windows (32-Bit- oder 64-Bit-Version)

  - Microsoft .NET Framework 4.7

- Sie müssen einen der folgenden unterstützten Browser verwenden, um das eDiscovery Export Tool<sup>1 ausführen zu können:</sup>

  - Microsoft Edge <sup>2</sup>

    ODER

  - Microsoft Internet Explorer 10 und höher

  > [!NOTE]
  > <sup>1</sup> Microsoft stellt keine Erweiterungen oder Add-Ons von Drittanbietern für ClickOnce her. Das Exportieren von Suchergebnissen mithilfe eines nicht unterstützten Browsers mit Drittanbietererweiterungen oder -add-ons wird nicht unterstützt.<br/>
  > <sup>2</sup> Als Ergebnis der letzten Änderungen an Microsoft Edge ist ClickOnce unterstützung standardmäßig nicht mehr aktiviert. Anweisungen zum Aktivieren ClickOnce in Edge finden Sie unter [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).

- Wenn die geschätzte Gesamtgröße der von der Suche zurückgegebenen Ergebnisse 2 TB überschreitet, schlägt das Exportieren der Berichte fehl. Um die Berichte erfolgreich zu exportieren, versuchen Sie, den Bereich zu einengt und die Suche erneut ausführen, sodass die geschätzte Größe der Ergebnisse kleiner als 2 TB ist.

- Wenn die Ergebnisse einer Suche älter als 7 Tage sind und Sie einen Exportberichtsauftrag übermitteln, wird eine Fehlermeldung angezeigt, in der Sie aufgefordert werden, die Suche erneut zu führen, um die Suchergebnisse zu aktualisieren. Brechen Sie in diesem Fall den Export ab, führen Sie die Suche erneut aus, und starten Sie den Export erneut.

- Das Exportieren von Suchberichten gilt für die maximale Anzahl von Exporten, die gleichzeitig ausgeführt werden, und die maximale Anzahl von Exporten, die ein einzelner Benutzer ausführen kann. Weitere Informationen zu Exportbeschränkungen finden Sie [unter Exportieren von Inhaltssuchergebnissen](export-search-results.md#export-limits).
  
## <a name="step-1-generate-the-report-for-export"></a>Schritt 1: Generieren des Berichts für den Export

Der erste Schritt besteht in der Vorbereitung des Berichts für das Herunterladen auf Ihren Computer, der exportiert wird. Wenn Sie den Bericht exportieren, werden die Berichtsdokumente in einen Azure Storage in der Microsoft Cloud hochgeladen.
  
1. Wählen Sie Microsoft 365 Compliance Center die Inhaltssuche aus, aus der Sie den Bericht exportieren möchten.
  
2. Klicken Sie **im** Menü Aktionen unten auf der Suchf flyout-Seite auf **Bericht exportieren.**

   ![Export report option in Actions menu](../media/ActionMenuExportReport.png)

   Die **Flyoutseite** Export report wird angezeigt. Die Exportberichtsoptionen, die zum Exportieren von Informationen zur Suche verfügbar sind, hängen davon ab, ob sich suchergebnisse in Postfächern oder Websites oder in einer Kombination aus beiden befinden.
  
3. Wählen **Sie unter** Ausgabeoptionen eine der folgenden Optionen aus:
  
   ![Exportausgabeoptionen](../media/ExportOutputOptions.png)

    - **Alle Elemente, mit Ausnahme von** Elementen, die nicht ein unbekanntes Format haben, sind verschlüsselt oder wurden aus anderen Gründen nicht indiziert. Mit dieser Option werden nur Informationen zu indizierten Elementen exportiert.
  
    - **Alle Elemente, einschließlich** der Elemente, die ein nicht unbekanntes Format haben, sind verschlüsselt oder wurden aus anderen Gründen nicht indiziert. Mit dieser Option werden Informationen zu indizierten und nicht indizierten Elementen exportiert.
  
    - **Nur Elemente, die ein nicht unbekanntes** Format haben, verschlüsselt sind oder aus anderen Gründen nicht indiziert wurden. Mit dieser Option werden nur Informationen zu nicht indizierten Elementen exportiert.

4. Konfigurieren Sie **die Option Deduplizierung für Exchange aktivieren.**
  
   - Wenn Sie diese Option auswählen, wird die Anzahl doppelter Nachrichten (vor Deduplizierung und nach Deduplizierung) in den Exportzusammenfassungsbericht aufgenommen. Außerdem wird nur eine Kopie einer Nachricht in die Datei manifest.xml eingeschlossen. Der Exportergebnisbericht enthält jedoch eine Zeile für jede Kopie einer doppelten Nachricht, damit Sie die Postfächer identifizieren können, die eine Kopie der doppelten Nachricht enthalten. Weitere Informationen zu den exportierten Berichten finden Sie unter [What's included in the report](#whats-included-in-the-report).

   - Wenn Sie diese Option nicht auswählen, enthalten die Exportberichte Informationen zu allen nachrichten, die von der Suche zurückgegeben werden, einschließlich Duplikaten.

     Weitere Informationen zur Deduplizierung und zur Ermittlung doppelter Elemente finden Sie unter [Deduplizierung in eDiscovery-Suchergebnissen.](de-duplication-in-ediscovery-search-results.md)

5. Klicken Sie **auf Bericht generieren**.

   Die Suchberichte werden zum Herunterladen vorbereitet, d. h. die Berichtsdokumente werden an einen Azure Storage in der Microsoft Cloud hochgeladen. Dieser Vorgang kann einige Minuten in Anspruch nehmen.

Anweisungen zum Herunterladen der exportierten Suchberichte finden Sie im nächsten Abschnitt.
  
## <a name="step-2-download-the-report"></a>Schritt 2: Herunterladen des Berichts

Im nächsten Schritt laden Sie den Bericht aus dem Azure Storage auf Ihren lokalen Computer herunter.

1. Wählen Sie **auf der** Seite Inhaltssuche im Microsoft 365 Compliance Center die Registerkarte **Exporte** aus.
  
   Möglicherweise müssen Sie auf **Aktualisieren klicken,** um die Liste der Exportaufträge so zu aktualisieren, dass der erstellte Exportauftrag angezeigt wird. Exportberichtsaufträge haben denselben Namen wie die entsprechende Suche, _ReportsOnly **an** den Suchnamen angefügt ist.
  
2. Wählen Sie den Exportauftrag aus, den Sie in Schritt 1 erstellt haben.

3. Klicken Sie **auf der** Flyoutseite Export report unter **Export key** auf Kopieren in **die Zwischenablage.** Sie verwenden diesen Schlüssel in Schritt 6, um die Suchergebnisse herunterzuladen.
  
   > [!IMPORTANT]
   > Da jeder benutzer das eDiscovery-Export-Tool installieren und starten kann und diesen Schlüssel dann zum Herunterladen des Suchberichts verwenden kann, sollten Sie Vorkehrungen treffen, um diesen Schlüssel so zu schützen, wie Sie Kennwörter oder andere sicherheitsrelevante Informationen schützen würden.

4. Klicken Sie oben auf der Flyoutseite auf **Ergebnisse herunterladen.**

5. Wenn Sie aufgefordert werden, das **eDiscovery-Exporttool zu** installieren, klicken Sie auf **Installieren**.

6. Gehen Sie **im eDiscovery-Exporttool** wie folgt vor:

   ![eDiscovery-Exporttool](../media/eDiscoveryExportTool.png)

   1. Fügen Sie den Exportschlüssel, den Sie in Schritt 3 kopiert haben, in das entsprechende Feld ein.
  
   2. Klicken **Sie auf Durchsuchen,** um den Speicherort anzugeben, an dem Sie die Suchberichtsdateien herunterladen möchten.

7. Klicken Sie zum Herunterladen der Suchergebnisse auf Ihren Computer auf **Starten**.
  
    Das **eDiscovery-Exporttool** zeigt Statusinformationen zum Exportvorgang an, einschließlich einer Schätzung der Anzahl (und Größe) der verbleibenden Elemente, die heruntergeladen werden sollen. Wenn der Exportvorgang abgeschlossen ist, können Sie auf die Dateien am Speicherort zugreifen, an dem sie heruntergeladen wurden.
  
## <a name="whats-included-in-the-report"></a>Was im Bericht enthalten ist

Wenn Sie einen Bericht über die Ergebnisse einer Inhaltssuche generieren und exportieren, werden die folgenden Dokumente heruntergeladen:
  
- **Exportzusammenfassung:** Ein Excel, das eine Zusammenfassung des Exports enthält. Dazu gehören Informationen wie die Anzahl der durchsuchten Inhaltsquellen, die Anzahl der Suchergebnisse aus den einzelnen Inhaltsspeicherorten, die geschätzte Anzahl der Elemente, die tatsächliche Anzahl der exportierten Elemente und die geschätzte und tatsächliche Größe der exportierten Elemente.

   Wenn Sie beim Exportieren des Berichts nicht indizierte Elemente enthalten, wird die Anzahl der nicht indizierten Elemente in der Gesamtanzahl der geschätzten Suchergebnisse und in der Gesamtzahl der heruntergeladenen Suchergebnisse (wenn Sie die Suchergebnisse exportieren) enthalten, die im Zusammenfassenden Exportbericht aufgeführt sind. Anders ausgedrückt: Die Gesamtanzahl der heruntergeladenen Elemente entspricht der Gesamtzahl der geschätzten Ergebnisse und der Gesamtzahl der nicht indizierten Elemente.
  
- **Manifest:** Eine Manifestdatei (im XML-Format), die Informationen zu jedem Element enthält, das in den Suchergebnissen enthalten ist. Wenn Sie die Deduplizierungsoption aktiviert haben, sind doppelte Nachrichten nicht in der Manifestdatei enthalten.

- **Ergebnisse:** Ein Excel, das eine Zeile mit Informationen zu jedem indizierten Element enthält, das mit den Suchergebnissen exportiert würde. Für E-Mails enthält das Ergebnisprotokoll Informationen zu jeder Nachricht, einschließlich: 

  - Der Speicherort der Nachricht im Quellpostfach (einschließlich der Angabe, ob die Nachricht sich im primären oder im Archivpostfach befindet).

  - Das Datum, an dem die Nachricht gesendet oder empfangen wurde.

  - Die Betreffzeile der Nachricht.

  - Absender und Empfänger der Nachricht.

  Für Dokumente von SharePoint und OneDrive for Business enthält das Ergebnisprotokoll Informationen zu jedem Dokument, einschließlich:

  - Die URL für das Dokument.

  - Die URL für die Websitesammlung, in der sich das Dokument befindet.

  - Das Datum, an dem das Dokument zuletzt geändert wurde.

  - Der Name des Dokuments (das sich in der Spalte Betreff im Ergebnisprotokoll befindet).

  > [!NOTE]
  > Die Anzahl der Zeilen im **Ergebnisbericht** sollte gleich der Gesamtzahl der Suchergebnisse minus der Gesamtzahl der im Bericht **Nicht indizierte Elemente aufgeführten Elemente** sein.
  
- **Trace.log**: Ein Ablaufverfolgungsprotokoll, das detaillierte Protokollierungsinformationen zum Exportprozess enthält und beim Aufdecken von Problemen beim Export helfen kann. Wenn Sie ein Ticket mit dem Microsoft Support zu einem Problem im Zusammenhang mit dem Exportieren von Suchberichten öffnen, werden Sie möglicherweise aufgefordert, dieses Ablaufverfolgungsprotokoll zur Verfügung zu stellen.

- **Nicht indizierte Elemente:** Ein Excel, das Informationen zu nicht indizierten Elementen enthält, die in den Suchergebnissen enthalten sind. Wenn Sie beim Generieren des Suchergebnissesberichts keine nicht indizierten Elemente verwenden, wird dieser Bericht weiterhin heruntergeladen, ist jedoch leer.
