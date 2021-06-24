---
title: Exportieren von Inhaltssuchergebnissen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.CustomizeExport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ed48d448-3714-4c42-85f5-10f75f6a4278
description: Exportieren Sie die Suchergebnisse aus einer Inhaltssuche im Microsoft 365 Compliance Center auf einen lokalen Computer. E-Mail-Ergebnisse werden als PST-Dateien exportiert. Inhalte aus SharePoint und OneDrive for Business Websites werden als systemeigene Office Dokumente exportiert.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d3ae14fc0ac31e50d579668c7fafba5390c5b8fc
ms.sourcegitcommit: 8b79d276f71f22bcaeb150e78e35101cb1ae0375
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53114764"
---
# <a name="export-content-search-results"></a>Exportieren von Inhaltssuchergebnissen

Nachdem eine Inhaltssuche erfolgreich ausgeführt wurde, können Sie die Suchergebnisse auf einen lokalen Computer exportieren. Wenn Sie E-Mail-Ergebnisse exportieren, werden diese als PST-Dateien auf Ihren Computer heruntergeladen. Wenn Sie Inhalte aus SharePoint und OneDrive for Business Websites exportieren, werden Kopien systemeigener Office Dokumente exportiert. In den exportierten Suchergebnissen sind weitere Dokumente und Berichte enthalten.
  
Beim Exportieren der Ergebnisse einer Inhaltssuche müssen Die Ergebnisse vorbereitet und dann auf einen lokalen Computer heruntergeladen werden. Diese Schritte zum Exportieren von Suchergebnissen gelten auch für das Exportieren der Ergebnisse einer Suche, die core eDiscovery-Fällen zugeordnet ist.
  
## <a name="before-you-export-search-results"></a>Vor dem Exportieren von Suchergebnissen

- Um Suchergebnisse zu exportieren, muss Ihnen die Rolle "Exportverwaltung" im Security & Compliance Center zugewiesen werden. Diese Rolle wird der integrierten Rollengruppe "eDiscovery-Manager" zugewiesen. Sie ist nicht standardmäßig der Rollengruppe "Organisationsverwaltung" zugewiesen. Weitere Informationen finden Sie unter [Zuweisen von eDiscovery-Berechtigungen](assign-ediscovery-permissions.md).

- Der Computer, den Sie zum Exportieren der Suchergebnisse verwenden, muss die folgenden Voraussetzungen erfüllen:
  
  - Neueste Version von Windows (32-Bit oder 64-Bit)
  
  - Microsoft .NET Framework 4.7
  
- Sie müssen einen der folgenden unterstützten Browser verwenden, um das eDiscovery-Exporttool<sup>1</sup>auszuführen:

  - Microsoft Edge <sup>2</sup>
  
    ODER

  - Microsoft Internet Explorer 10 und höher
  
  > [!NOTE]
  > <sup>1</sup> Microsoft stellt keine Drittanbietererweiterungen oder Add-Ons für ClickOnce Anwendungen her. Das Exportieren von Suchergebnissen mit einem nicht unterstützten Browser mit Drittanbietererweiterungen oder Add-Ons wird nicht unterstützt.<br/>
  > <sup>2</sup> Aufgrund der letzten Änderungen an Microsoft Edge ist ClickOnce Unterstützung nicht mehr standardmäßig aktiviert. Anweisungen zum Aktivieren der ClickOnce-Unterstützung in Edge finden Sie unter [Verwenden des eDiscovery-Exporttools in Microsoft Edge.](configure-edge-to-export-search-results.md)
  
- Das eDiscovery-Exporttool, das Sie in Schritt 2 zum Herunterladen von Suchergebnissen verwenden, unterstützt keine Automatisierung (mithilfe eines Skripts oder ausführen von Cmdlets). Es wird dringend empfohlen, den Vorbereitungsprozess in Schritt 1 oder den Downloadprozess in Schritt 2 nicht zu automatisieren. Wenn Sie einen dieser Prozesse automatisieren, bietet der Microsoft-Support keine Unterstützung, wenn Probleme auftreten.

- Es wird empfohlen, Suchergebnisse auf einen lokalen Computer herunterzuladen. Um zu verhindern, dass die Firewall- oder Proxyinfrastruktur Ihres Unternehmens Probleme beim Herunterladen von Suchergebnissen verursacht, sollten Sie Suchergebnisse auf einen virtuellen Desktop außerhalb Ihres Netzwerks herunterladen. Dadurch können Timeouts verringert werden, die in Azure-Datenverbindungen auftreten, wenn eine große Anzahl von Dateien exportiert wird. Weitere Informationen zu virtuellen Desktops finden Sie unter [Windows Virtual Desktop](https://azure.microsoft.com/services/virtual-desktop).

- Um die Leistung beim Herunterladen von Suchergebnissen zu verbessern, sollten Sie Suchvorgänge, die eine große Menge von Ergebnissen zurückgeben, in kleinere Suchen unterteilen. Beispielsweise können Sie Datumsbereiche in Suchabfragen verwenden, um eine kleinere Gruppe von Ergebnissen zurückzugeben, die schneller heruntergeladen werden können.
  
- Wenn Sie Suchergebnisse exportieren, werden die Daten vorübergehend an einem von Microsoft bereitgestellten Azure Storage Speicherort in der Microsoft-Cloud gespeichert, bevor sie auf Ihren lokalen Computer heruntergeladen werden. Stellen Sie sicher, dass Ihre Organisation eine Verbindung mit dem Endpunkt in Azure herstellen kann, der **\* blob.core.windows.net** ist (der Platzhalter stellt einen eindeutigen Bezeichner für Ihren Export dar). Die Suchergebnisse werden zwei Wochen nach ihrer Erstellung aus dem Azure Storage Speicherort gelöscht. 
  
- Wenn Ihre Organisation einen Proxyserver für die Kommunikation mit dem Internet verwendet, müssen Sie die Proxyservereinstellungen auf dem Computer definieren, den Sie zum Exportieren der Suchergebnisse verwenden (damit das Exporttool von Ihrem Proxyserver authentifiziert werden kann). Öffnen Sie dazu die *machine.config* Datei an dem Speicherort, der Ihrer Version von Windows entspricht. 
  
  - **32-Bit:**`%windir%\Microsoft.NET\Framework\[version]\Config\machine.config`
  
  - **64-Bit:**`%windir%\Microsoft.NET\Framework64\[version]\Config\machine.config`
  
    Fügen Sie die folgenden Zeilen zur  *machine.config*  Datei zwischen den  `<configuration>` Tags  `</configuration>` hinzu. Achten Sie darauf, die richtigen Werte für Ihre Organisation zu  `ProxyServer`  `Port` ersetzen, z. `proxy01.contoso.com:80` B. . 
  
    ```xml
    <system.net>
       <defaultProxy enabled="true" useDefaultCredentials="true">
         <proxy proxyaddress="https://ProxyServer :Port " 
                usesystemdefault="False" 
                bypassonlocal="True" 
                autoDetect="False" />
       </defaultProxy>
    </system.net>
    ```

- Wenn die Ergebnisse einer Suche älter als 7 Tage sind und Sie einen Exportauftrag übermitteln, wird eine Fehlermeldung angezeigt, in der Sie aufgefordert werden, die Suche erneut auszuführen, um die Suchergebnisse zu aktualisieren. Wenn dies geschieht, brechen Sie den Export ab, führen Sie die Suche erneut aus, und starten Sie dann den Export erneut.

## <a name="step-1-prepare-search-results-for-export"></a>Schritt 1: Vorbereiten der Suchergebnisse für Export

Der erste Schritt besteht darin, die Suchergebnisse für den Export vorzubereiten. Wenn Sie Ergebnisse vorbereiten, werden sie an einen von Microsoft bereitgestellten Azure Storage Speicherort in der Microsoft-Cloud hochgeladen. Inhalte aus Postfächern und Websites werden mit einer maximalen Rate von 2 GB pro Stunde hochgeladen.
  
1. Wählen Sie im Microsoft 365 Compliance Center die Inhaltssuche aus, aus der Sie Ergebnisse exportieren möchten.
  
2. Klicken Sie im Menü **"Aktionen"** am unteren Rand der Flyoutseite auf **"Ergebnisse exportieren".**

   ![Option "Ergebnisse exportieren" im Menü "Aktionen"](../media/ActionMenuExportResults.png)

   Die Flyoutseite **"Ergebnisse exportieren"** wird angezeigt. Welche Exportoptionen zum Exportieren von Inhalten verfügbar sind, hängt davon ab, ob sich die Suchergebnisse in Postfächern oder Websites oder in einer Kombination aus beiden befinden.

3. Wählen Sie unter **Ausgabeoptionen** eine der folgenden Optionen aus:
  
   ![Exportieren von Ausgabeoptionen](../media/ExportOutputOptions.png)

    - **Alle Elemente, mit Ausnahme von Elementen mit nicht erkanntem Format, werden verschlüsselt oder wurden aus anderen Gründen nicht indiziert.** Diese Option exportiert nur indizierte Elemente.
  
    - **Alle Elemente, einschließlich elemente mit nicht erkanntem Format, werden verschlüsselt oder wurden aus anderen Gründen nicht indiziert.** Diese Option exportiert indizierte und nicht indizierte Elemente.
  
    - **Nur Elemente mit einem nicht erkannten Format werden verschlüsselt oder wurden aus anderen Gründen nicht indiziert.** Diese Option exportiert nur nicht indizierte Elemente.

      Im Abschnitt ["Weitere Informationen"](#more-information) finden Sie eine Beschreibung dazu, wie teilweise indizierte Elemente exportiert werden. Weitere Informationen zu teilweise indizierten Elementen finden Sie unter [teilweise indizierte Elemente in der Inhaltssuche.](partially-indexed-items-in-content-search.md)

4. Wählen Sie unter **"Exchange Inhalt exportieren als"** eine der folgenden Optionen aus:
  
   ![Exchange-Optionen](../media/ExchangeExportOptions.png)

    - **Eine PST-Datei für jedes Postfach:** Exportiert eine PST-Datei für jedes Benutzerpostfach, das Suchergebnisse enthält. Alle Ergebnisse aus dem Archivpostfach des Benutzers sind in derselben PST-Datei enthalten. Diese Option reproduziert die Postfachordnerstruktur aus dem Quellpostfach.
  
    - **Eine PST-Datei mit allen Nachrichten:** Exportiert eine einzelne PST-Datei (mit dem Namen *Exchange.pst),* die die Suchergebnisse aus allen in der Suche enthaltenen Quellpostfächern enthält. Mit dieser Option wird die Postfachordnerstruktur für jede Nachricht reproduziert.
  
    - **Eine PST-Datei, die alle Nachrichten in einem einzigen Ordner enthält:** Exportiert Suchergebnisse in eine einzelne PST-Datei, in der sich alle Nachrichten in einem einzigen Ordner auf oberster Ebene befinden. Mit dieser Option können Prüfer Elemente in chronologischer Reihenfolge überprüfen (Elemente werden nach Sendedatum sortiert), ohne in der ursprünglichen Postfachordnerstruktur für jedes Element navigieren zu müssen.
  
    - **Einzelne Nachrichten:** Exportiert Suchergebnisse als einzelne E-Mail-Nachrichten im MSG-Format. Wenn Sie diese Option auswählen, werden die E-Mail-Suchergebnisse in einen Ordner im Dateisystem exportiert. Der Ordnerpfad für einzelne Nachrichten entspricht dem Pfad, der beim Exportieren der Ergebnisse in eine PST-Datei verwendet wurde.
  
5. Konfigurieren Sie die folgenden zusätzlichen Optionen:

   ![Konfigurieren anderer Exportoptionen](../media/OtherExportOptions.png)

   1. Aktivieren Sie das Kontrollkästchen **"Deduplizierung für Exchange Inhalte aktivieren",** um doppelte Nachrichten auszuschließen.
  
      Wenn Sie diese Option auswählen, wird nur eine Kopie einer Nachricht exportiert, auch wenn mehrere Kopien derselben Nachricht in den durchsuchten Postfächern gefunden werden. Der Exportergebnisbericht (bei dem es sich um eine Datei mit dem Namen Results.csv handelt) enthält eine Zeile für jede Kopie einer duplizierten Nachricht, sodass Sie die Postfächer (oder öffentlichen Ordner) identifizieren können, die eine Kopie der duplizierten Nachricht enthalten. Weitere Informationen zur Deduplizierung und zur Identifizierung doppelter Elemente finden Sie unter ["Deduplizierung" in eDiscovery-Suchergebnissen.](de-duplication-in-ediscovery-search-results.md)
  
   2. Aktivieren Sie das Kontrollkästchen **"Versionen für SharePoint Dateien einschließen",** um alle Versionen SharePoint Dokumente zu exportieren. Diese Option wird nur angezeigt, wenn die Inhaltsquellen der Suche SharePoint oder OneDrive for Business Websites enthalten.
  
   3. Wählen Sie die **Dateien in einem komprimierten (gezippten) Ordner exportieren aus. Enthält nur einzelne Nachrichten und SharePoint Dokumente,** um Suchergebnisse in komprimierte Ordner zu exportieren. Diese Option wird nur angezeigt, wenn Sie Exchange Elemente als einzelne Nachrichten exportieren und wenn die Suchergebnisse SharePoint oder OneDrive Dokumente enthalten. Diese Option wird in erster Linie verwendet, um den Grenzwert von 260 Zeichen in Windows Dateipfadnamen zu umgehen, wenn Elemente exportiert werden. Weitere [Informationen](#more-information) finden Sie unter "Dateinamen exportierter Elemente".
   > [!IMPORTANT]
   > Das Exportieren von Dateien in einem komprimierten (gezippten) Ordner erhöht die Exportzeiten.
  
6. Klicken Sie auf **"Exportieren",** um den Exportvorgang zu starten. Die Suchergebnisse werden für den Download vorbereitet, was bedeutet, dass sie von den ursprünglichen Inhaltsspeicherorten gesammelt und dann an einen Azure Storage Speicherort in der Microsoft-Cloud hochgeladen werden. Dieser Vorgang kann einige Minuten in Anspruch nehmen.

Anweisungen zum Herunterladen der exportierten Suchergebnisse finden Sie im nächsten Abschnitt.
  
## <a name="step-2-download-the-search-results"></a>Schritt 2: Herunterladen der Suchergebnisse

Der nächste Schritt besteht darin, die Suchergebnisse aus dem Azure Storage Speicherort auf Ihren lokalen Computer herunterzuladen.
  
1. Wählen Sie auf der Seite **"Inhaltssuche"** im Microsoft 365 Compliance Center die Registerkarte **"Exporte" aus.**
  
   Möglicherweise müssen Sie auf **"Aktualisieren"** klicken, um die Liste der Exportaufträge so zu aktualisieren, dass der von Ihnen erstellte Exportauftrag angezeigt wird. Exportaufträge haben denselben Namen wie die entsprechende Suche, **wobei _Export** an den Suchnamen angefügt ist.
  
2. Wählen Sie den Exportauftrag aus, den Sie in Schritt 1 erstellt haben.

3. Klicken Sie auf der Flyoutseite unter **Exportschlüssel** auf **"In Zwischenablage kopieren".** Sie verwenden diesen Schlüssel in Schritt 6, um die Suchergebnisse herunterzuladen.
  
   > [!IMPORTANT]
   > Da jeder das eDiscovery-Exporttool installieren und starten und dann diesen Schlüssel zum Herunterladen der Suchergebnisse verwenden kann, müssen Sie vorsichtsmaßnahmen ergreifen, um diesen Schlüssel genau so zu schützen, wie Sie Kennwörter oder andere sicherheitsrelevante Informationen schützen würden.

4. Klicken Sie oben auf der Flyoutseite auf **"Ergebnisse herunterladen".**

5. Wenn Sie aufgefordert werden, das **eDiscovery-Exporttool** zu installieren, klicken Sie auf **"Installieren".**

6. Führen Sie im **eDiscovery-Exporttool** die folgenden Schritte aus:

   ![eDiscovery-Exporttool](../media/eDiscoveryExportTool.png)

   1. Fügen Sie den Exportschlüssel, den Sie in Schritt 3 kopiert haben, in das entsprechende Feld ein.
  
   2. Klicken Sie auf **Durchsuchen**, um das Verzeichnis anzugeben, in das die Dateien mit den Suchergebnissen heruntergeladen werden sollen.
  
      > [!IMPORTANT]
      >  Aufgrund der hohen Netzwerkaktivität während des Downloads sollten Sie Suchergebnisse nur an einen Speicherort auf einem internen Laufwerk auf Ihrem lokalen Computer herunterladen. Befolgen Sie die folgenden Richtlinien, um eine optimale Downloaderfahrung zu erzielen: <br/>
      >- Laden Sie suchergebnisse nicht in einen UNC-Pfad, ein zugeordnetes Netzlaufwerk, ein externes USB-Laufwerk oder ein synchronisiertes OneDrive for Business Konto herunter.<br/>
      >- Deaktivieren Sie die Virenprüfung für den Ordner, in den Sie das Suchergebnis herunterladen.<br/>
      >- Laden Sie Suchergebnisse für gleichzeitige Downloadaufträge in verschiedene Ordner herunter.

7. Klicken Sie zum Herunterladen der Suchergebnisse auf Ihren Computer auf **Starten**.
  
    Das **eDiscovery-Export-Tool** zeigt Statusinformationen zum Export an, z. B. die geschätzte Anzahl (und Größe) der verbleibenden herunterzuladenden Elemente. Nach Abschluss des Exportvorgangs können Sie in dem Verzeichnis auf die Dateien zugreifen, in das sie heruntergeladen wurden.

## <a name="more-information"></a>Weitere Informationen

Hier finden Sie weitere Informationen zum Exportieren von Suchergebnissen.
  
[Exportgrenzwerte](#export-limits)
  
[Exportieren von Berichten](#export-reports)
  
[Exportieren teilweise indizierter Elemente](#exporting-partially-indexed-items)

[Exportieren einzelner Nachrichten oder PST-Dateien](#exporting-individual-messages-or-pst-files)

[Entschlüsseln von RMS-geschützten E-Mail-Nachrichten und verschlüsselten Dateianlagen](#decrypting-rms-protected-email-messages-and-encrypted-file-attachments)

[Dateinamen der exportierten Elemente](#filenames-of-exported-items)  
  
[Sonstiges](#miscellaneous)
  
### <a name="export-limits"></a>Exportgrenzwerte

Informationen zu Grenzwerten beim Exportieren von Inhaltssuchergebnissen finden Sie im Abschnitt "Exportbeschränkungen" unter ["Grenzwerte für die Inhaltssuche".](limits-for-content-search.md#export-limits)

### <a name="export-reports"></a>Exportieren von Berichten
  
- Wenn Sie Suchergebnisse exportieren, werden zusätzlich zu den Suchergebnissen die folgenden Berichte einbezogen.
  
  - **Exportzusammenfassung** Ein Excel Dokument, das eine Zusammenfassung des Exports enthält. Dazu gehören Informationen wie die Anzahl der durchsuchten Inhaltsquellen, die geschätzten und heruntergeladenen Größen der Suchergebnisse sowie die geschätzte und heruntergeladene Anzahl der exportierten Elemente.
  
  - **Manifest** Eine Manifestdatei (im XML-Format), die Informationen zu jedem element enthält, das in den Suchergebnissen enthalten ist.
  
  - **Ergebnisse** Ein Excel Dokument, das Informationen zu jedem Element enthält, das als Suchergebnis heruntergeladen wird. Bei E-Mails enthält das Ergebnisprotokoll Informationen zu jeder Nachricht, einschließlich:
  
    - Der Speicherort der Nachricht im Quellpostfach (einschließlich der Angabe, ob die Nachricht sich im primären oder im Archivpostfach befindet).
  
    - Das Datum, an dem die Nachricht gesendet oder empfangen wurde.

    - Die Betreffzeile der Nachricht.

    - Absender und Empfänger der Nachricht.

    - Gibt an, ob es sich bei der Nachricht um eine doppelte Nachricht handelt, wenn Sie die Deduplizierungsoption beim Exportieren der Suchergebnisse aktiviert haben. Doppelte Nachrichten haben einen Wert in der Spalte **"Duplizieren in Element",** der die Nachricht als Duplikat identifiziert. Der Wert in der Spalte **"In Element duplizieren"** enthält die Elementidentität der Nachricht, die exportiert wurde. Weitere Informationen finden Sie unter [Deduplizierung in eDiscovery-Suchergebnissen.](de-duplication-in-ediscovery-search-results.md)

      Für Dokumente von SharePoint und OneDrive for Business Websites enthält das Ergebnisprotokoll Informationen zu jedem Dokument, einschließlich:

      - Die URL für das Dokument.

      - Die URL für die Websitesammlung, in der sich das Dokument befindet.

      - Das Datum, an dem das Dokument zuletzt geändert wurde.

      - Der Name des Dokuments (das sich in der Spalte Betreff im Ergebnisprotokoll befindet).

  - **Nicht indizierte Elemente** Ein Excel Dokument, das Informationen zu teilweise indizierten Elementen enthält, die in den Suchergebnissen enthalten wären. Wenn Sie beim Generieren des Suchergebnissenberichts nicht teilweise indizierte Elemente einschließen, wird dieser Bericht weiterhin heruntergeladen, ist aber leer.

  - **Fehler und Warnungen** Enthält Fehler und Warnungen für Dateien, die beim Export aufgetreten sind. Informationen zu den einzelnen Fehlern oder Warnungen finden Sie in der Spalte "Fehlerdetails".

  - **Übersprungene Elemente** Wenn Sie Suchergebnisse aus SharePoint und OneDrive for Business Websites exportieren, enthält der Export in der Regel einen Bericht über übersprungene Elemente (SkippedItems.csv). Die in diesem Bericht genannten Elemente sind in der Regel Elemente, die nicht heruntergeladen werden, z. B. einen Ordner oder eine Dokumentenmappe. Das Exportieren dieser Elementtypen ist beabsichtigt. Für andere Elemente, die übersprungen wurden, zeigen das Feld "Fehlertyp" und "Fehlerdetails" im Bericht über übersprungene Elemente den Grund an, warum das Element übersprungen wurde und nicht mit den anderen Suchergebnissen heruntergeladen wurde.

  - **Trace.log** enthält detaillierte Protokollierungsinformationen zum Exportprozess und kann beim Aufdecken von Problemen beim Export helfen. Wenn Sie ein Ticket beim Microsoft-Support zu einem Problem im Zusammenhang mit dem Exportieren von Suchergebnissen öffnen, werden Sie möglicherweise aufgefordert, dieses Ablaufverfolgungsprotokoll anzugeben.
  
    > [!NOTE]
    > Sie können diese Dokumente einfach exportieren, ohne die tatsächlichen Suchergebnisse exportieren zu müssen. Siehe ["Exportieren eines Inhaltssuchberichts".](export-a-content-search-report.md)
  
### <a name="exporting-partially-indexed-items"></a>Exportieren teilweise indizierter Elemente
  
- Wenn Sie Postfachelemente aus einer Inhaltssuche exportieren, die alle Postfachelemente in den Suchergebnissen zurückgibt (da in der Suchabfrage keine Schlüsselwörter enthalten sind), werden teilweise indizierte Elemente nicht in die PST-Datei kopiert, die die nicht indizierten Elemente enthält. Dies liegt daran, dass alle Elemente, einschließlich teilweise indizierter Elemente, automatisch in die regulären Suchergebnisse einbezogen werden. Dies bedeutet, dass teilweise indizierte Elemente in eine PST-Datei (oder als einzelne Nachrichten) eingeschlossen werden, die die anderen indizierten Elemente enthält.

    Wenn Sie sowohl die indizierten als auch teilweise indizierten Elemente exportieren oder nur die indizierten Elemente aus einer Inhaltssuche exportieren, die alle Elemente zurückgibt, wird die gleiche Anzahl von Elementen heruntergeladen. Dies geschieht, obwohl die geschätzten Suchergebnisse für die Inhaltssuche (angezeigt in der Suchstatistik im Security & Compliance Center) weiterhin eine separate Schätzung für die Anzahl der teilweise indizierten Elemente enthalten. Nehmen wir beispielsweise an, dass die Schätzung für eine Suche, die alle Elemente enthält (keine Schlüsselwörter in der Suchabfrage), anzeigt, dass 1.000 Elemente gefunden wurden und dass auch 200 teilweise indizierte Elemente gefunden wurden. In diesem Fall enthalten die 1.000 Elemente die teilweise indizierten Elemente, da die Suche alle Elemente zurückgibt. Mit anderen Worten: Die Suche gibt insgesamt 1.000 Elemente zurück, nicht 1.200 Elemente (wie sie erwarten können). Wenn Sie die Ergebnisse dieser Suche exportieren und indizierte und teilweise indizierte Elemente exportieren (oder nur teilweise indizierte Elemente exportieren), werden 1.000 Elemente heruntergeladen. Dies liegt daran, dass teilweise indizierte Elemente in den regulären (indizierten) Ergebnissen enthalten sind, wenn Sie eine leere Suchabfrage verwenden, um alle Elemente zurückzugeben. Wenn Sie in diesem Beispiel nur teilweise indizierte Elemente exportieren möchten, werden nur die 200 nicht indizierten Elemente heruntergeladen.

    Beachten Sie außerdem, dass im vorherigen Beispiel (wenn Sie indizierte und teilweise indizierte Elemente exportieren oder nur indizierte Elemente exportieren) der **Exportzusammenfassungsbericht,** der in den exportierten Suchergebnissen enthalten ist, aus den gleichen Gründen wie zuvor beschrieben 1.000 Elemente mit geschätzten Elementen und 1.000 heruntergeladenen Elementen auflistet. 

- Wenn die Suche, aus der Sie Ergebnisse exportieren, eine Suche nach bestimmten Inhaltsspeicherorten oder allen Inhaltsspeicherorten in Ihrer Organisation war, werden nur die teilweisen Elemente aus Inhaltsspeicherorten exportiert, die Elemente enthalten, die den Suchkriterien entsprechen. Wenn also keine Suchergebnisse in einem Postfach oder einer Website gefunden werden, werden alle teilweise indizierten Elemente in diesem Postfach oder dieser Website nicht exportiert. Der Grund dafür ist, dass das Exportieren teilweise indizierter Elemente aus vielen Speicherorten in der Organisation die Wahrscheinlichkeit von Exportfehlern erhöhen und die Zeit erhöhen kann, die zum Exportieren und Herunterladen der Suchergebnisse benötigt wird.

    Um teilweise indizierte Elemente aus allen Inhaltsspeicherorten für eine Suche zu exportieren, konfigurieren Sie die Suche so, dass alle Elemente zurückgegeben werden (durch Entfernen von Schlüsselwörtern aus der Suchabfrage), und exportieren Sie dann nur teilweise indizierte Elemente, wenn Sie die Suchergebnisse exportieren.

    ![Verwenden sie die dritte Exportoption, um nur nicht indizierte Elemente zu exportieren.](../media/5d7be338-a0e5-425f-8ba5-92769c24bf75.png)
  
- Beim Exportieren von Suchergebnissen aus SharePoint oder OneDrive for Business Websites hängt die Möglichkeit zum Exportieren nicht indizierter Elemente auch von der ausgewählten Exportoption ab und davon, ob eine durchsuchte Website ein indiziertes Element enthält, das den Suchkriterien entspricht. Wenn Sie beispielsweise bestimmte SharePoint oder OneDrive for Business Websites durchsuchen und keine Suchergebnisse gefunden werden, werden keine nicht indizierten Elemente von diesen Websites exportiert, wenn Sie die zweite Exportoption auswählen, um indizierte und nicht indizierte Elemente zu exportieren. Wenn ein indiziertes Element von einer Website den Suchkriterien entspricht, werden alle nicht indizierten Elemente von dieser Website exportiert, wenn sowohl indizierte als auch nicht indizierte Elemente exportiert werden. In der folgenden Abbildung werden die Exportoptionen basierend darauf beschrieben, ob eine Website ein indiziertes Element enthält, das den Suchkriterien entspricht.

    ![Wählen Sie die Exportoption basierend darauf, ob eine Website ein indiziertes Element enthält, das den Suchkriterien entspricht.](../media/94f78786-c6bb-42fb-96b3-7ea3998bcd39.png)

    a. Es werden nur indizierte Elemente exportiert, die den Suchkriterien entsprechen. Es werden keine teilweise indizierten Elemente exportiert.

    b. Wenn keine indizierten Elemente einer Website den Suchkriterien entsprechen, werden teilweise indizierte Elemente von derselben Website nicht exportiert. Wenn indizierte Elemente von einer Website in den Suchergebnissen zurückgegeben werden, werden die teilweise indizierten Elemente von dieser Website exportiert. Mit anderen Worten, nur die teilweise indizierten Elemente von Websites, die Elemente enthalten, die den Suchkriterien entsprechen, werden exportiert.

    c. Alle teilweise indizierten Elemente von allen Websites in der Suche werden exportiert, unabhängig davon, ob eine Website Elemente enthält, die den Suchkriterien entsprechen.

    Wenn Sie teilweise indizierte Elemente exportieren möchten, werden teilweise indizierte Postfachelemente in einer separaten PST-Datei exportiert, unabhängig von der Option, die Sie unter **Exportieren Exchange Inhalte als** auswählen.

- Wenn teilweise indizierte Elemente in den Suchergebnissen zurückgegeben werden (da andere Eigenschaften teilweise indizierter Elemente mit den Suchkriterien übereinstimmten), werden diese teilweise indizierten Elemente mit den regulären Suchergebnissen exportiert. Wenn Sie also sowohl indizierte elemente als auch teilweise indizierte Elemente exportieren möchten (indem Sie die Option **"Alle Elemente" auswählen, einschließlich elemente, die nicht erkanntes Format haben, verschlüsselt sind oder aus anderen Gründen nicht indiziert wurden),** werden die teilweise indizierten Elemente, die mit den regulären Ergebnissen exportiert wurden, im bericht Results.csv aufgeführt. Sie werden nicht im Bericht "Nicht indizierte items.csv" aufgeführt.
  
### <a name="exporting-individual-messages-or-pst-files"></a>Exportieren einzelner Nachrichten oder PST-Dateien
  
- Wenn der Dateipfadname einer Nachricht den maximalen Zeichengrenzwert für Windows überschreitet, wird der Dateipfadname abgeschnitten. Der ursprüngliche Dateipfadname wird jedoch im Manifest und ResultsLog aufgeführt.
  
- Wie zuvor erläutert, werden die E-Mail-Suchergebnisse in einen Ordner im Dateisystem exportiert. Der Ordnerpfad für einzelne Nachrichten würde den Ordnerpfad im Postfach des Benutzers replizieren. For example, for a search named "ContosoCase101" messages in a user's in post would be located in the folder path  `~ContosoCase101\\<date of export\Exchange\user@contoso.com (Primary)\Top of Information Store\Inbox` .

- Wenn Sie E-Mail-Nachrichten in einer PST-Datei exportieren möchten, die alle Nachrichten in einem einzigen Ordner enthält, sind ein Ordner **"Gelöschte Elemente"** und ein **Ordner "Suchordner"** in der obersten Ebene des PST-Ordners enthalten. Diese Ordner sind leer.

- Wie bereits erwähnt, müssen Sie E-Mail-Suchergebnisse als einzelne Nachrichten exportieren, um RMS-geschützte Nachrichten zu entschlüsseln, wenn sie exportiert werden. Verschlüsselte Nachrichten bleiben verschlüsselt, wenn Sie E-Mail-Suchergebnisse als PST-Datei exportieren.
  
### <a name="decrypting-rms-protected-email-messages-and-encrypted-file-attachments"></a>Entschlüsseln von RMS-geschützten E-Mail-Nachrichten und verschlüsselten Dateianlagen

Alle rechtegeschützten (RMS-geschützten) E-Mail-Nachrichten, die in den Ergebnissen einer Inhaltssuche enthalten sind, werden beim Exportieren entschlüsselt. Darüber hinaus wird jede Datei, die mit einer [Microsoft-Verschlüsselungstechnologie](encryption.md) verschlüsselt ist und an eine E-Mail-Nachricht angehängt ist, die in den Suchergebnissen enthalten ist, auch entschlüsselt, wenn sie exportiert wird. Diese Entschlüsselungsfunktion ist standardmäßig für Mitglieder der Rollengruppe "eDiscovery-Manager" aktiviert. Dies liegt daran, dass die RMS Decrypt-Verwaltungsrolle dieser Rollengruppe standardmäßig zugewiesen ist. Beachten Sie beim Exportieren verschlüsselter E-Mail-Nachrichten und Anlagen Folgendes:
  
- Wie zuvor erläutert, müssen Sie die Suchergebnisse als einzelne Nachrichten exportieren, um RMS-geschützte Nachrichten zu entschlüsseln, wenn Sie sie exportieren. Wenn Sie Suchergebnisse in eine PST-Datei exportieren, bleiben RMS-geschützte Nachrichten verschlüsselt.

- Entschlüsselte Nachrichten werden im **ResultsLog-Bericht** identifiziert. Dieser Bericht enthält eine Spalte mit dem Namen **"Decodieren des Status",** und der Wert **"Decodiert"** in dieser Spalte identifiziert die Nachrichten, die entschlüsselt wurden.

- Zusätzlich zum Entschlüsseln von Dateianlagen beim Exportieren von Suchergebnissen können Sie bei der Vorschau der Suchergebnisse auch eine Vorschau der entschlüsselten Datei anzeigen. Sie können die E-Mail-Nachricht mit geschützten Rechten nur anzeigen, nachdem Sie sie exportiert haben.

- Zu diesem Zeitpunkt enthält die Entschlüsselungsfunktion beim Exportieren von Suchergebnissen keine verschlüsselten Inhalte von SharePoint und OneDrive for Business Websites. In Kürze wird jedoch Unterstützung für Dokumente bereitgestellt, die mit Microsoft-Verschlüsselungstechnologien verschlüsselt und in SharePoint Online und OneDrive for Business gespeichert sind.

- Wenn Sie verhindern möchten, dass jemand RMS-schützende Nachrichten und verschlüsselte Dateianlagen entschlüsselt, müssen Sie eine benutzerdefinierte Rollengruppe erstellen (durch Kopieren der integrierten eDiscovery-Manager-Rollengruppe) und dann die RMS Decrypt-Verwaltungsrolle aus der benutzerdefinierten Rollengruppe entfernen. Fügen Sie dann die Person hinzu, die Sie als Mitglied der benutzerdefinierten Rollengruppe nicht entschlüsseln möchten.
  
### <a name="filenames-of-exported-items"></a>Dateinamen der exportierten Elemente
  
- Es gibt eine Beschränkung von 260 Zeichen (vom Betriebssystem festgelegt) für den vollständigen Pfadnamen für E-Mail-Nachrichten und Websitedokumente, die auf Ihren lokalen Computer exportiert werden. Der vollständige Pfadname für exportierte Elemente enthält den ursprünglichen Speicherort des Elements und den Ordnerspeicherort auf dem lokalen Computer, auf den die Suchergebnisse heruntergeladen werden. Wenn Sie beispielsweise angeben, dass die Suchergebnisse  `C:\Users\Admin\Desktop\SearchResults` im eDiscovery-Exporttool heruntergeladen werden sollen, lautet der vollständige Pfadname für ein heruntergeladenes E-Mail-Element  `C:\Users\Admin\Desktop\SearchResults\ContentSearch1\03.15.2017-1242PM\Exchange\sarad@contoso.com (Primary)\Top of Information Store\Inbox\Insider trading investigation.msg` .

- Wenn der Grenzwert von 260 Zeichen überschritten wird, wird der vollständige Pfadname für ein Element basierend auf folgenden Elementen abgeschnitten:

  - Wenn der vollständige Pfadname länger als 260 Zeichen ist, wird der Dateiname gekürzt, um unter das Limit zu gelangen. Beachten Sie, dass der abgeschnittene Dateiname (mit Ausnahme der Dateierweiterung) nicht weniger als acht Zeichen lang sein wird.

  - Wenn der vollständige Pfadname nach dem Kürzen des Dateinamens noch zu lang ist, wird das Element vom aktuellen Speicherort in den übergeordneten Ordner verschoben. Wenn der Pfadname noch zu lang ist, wird der Vorgang wiederholt: Kürzen Sie den Dateinamen, und wechseln Sie bei Bedarf erneut zum übergeordneten Ordner. Dieser Vorgang wird wiederholt, bis der vollständige Pfadname unter dem Grenzwert von 260 Zeichen liegt.

  - Wenn bereits ein abgeschnittener vollständiger Pfadname vorhanden ist, wird am Ende des Dateinamens eine Versionsnummer hinzugefügt. Beispiel: `statusmessage(2).msg` .

    Um dieses Problem zu beheben, sollten Sie Suchergebnisse an einen Speicherort mit einem kurzen Pfadnamen herunterladen. Beispielsweise würde das Herunterladen von Suchergebnissen in einen Ordner mit dem Namen  `C:\Results` den Pfadnamen exportierter Elemente weniger Zeichen hinzufügen als das Herunterladen in einen Ordner mit dem Namen  `C:\Users\Admin\Desktop\Results` .

- Beim Exportieren von Websitedokumenten ist es auch möglich, dass der ursprüngliche Dateiname eines Dokuments geändert wird. Dies geschieht speziell für Dokumente, die aus einer SharePoint oder OneDrive for Business Website gelöscht wurden, die in die Warteschleife versetzt wurde. Nachdem ein Dokument, das sich auf einer Website befindet, die sich in der Warteschleife befindet, gelöscht wurde, wird das gelöschte Dokument automatisch in das permanente Dokumentarchiv für die Website verschoben (das erstellt wurde, als die Website in den Haltebereich versetzt wurde). Wenn das gelöschte Dokument in das permanente Dokumentarchiv verschoben wird, wird eine zufällig generierte und eindeutige ID an den ursprünglichen Dateinamen des Dokuments angefügt. Wenn z. B. der Dateiname für ein Dokument vorhanden  `FY2017Budget.xlsx` ist und dieses Dokument später gelöscht und in das permanente Dokumentarchiv verschoben wird, wird der Dateiname des Dokuments, das in das permanente Dokumentarchiv verschoben wird, in etwa wie folgt  `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx` geändert. Wenn ein Dokument im permanenten Dokumentarchiv mit der Abfrage einer Inhaltssuche übereinstimmt und Sie die Ergebnisse dieser Suche exportieren, hat die exportierte Datei den geänderten Dateinamen; In diesem Beispiel lautet der Dateiname des exportierten Dokuments  `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx` .

    Wenn ein Dokument auf einer Website geändert wird, die in der Warteschleife gespeichert ist (und die Versionsverwaltung für die Dokumentbibliothek auf der Website aktiviert wurde), wird automatisch eine Kopie der Datei im permanenten Dokumentarchiv erstellt. In diesem Fall wird auch eine zufällig generierte und eindeutige ID an den Dateinamen des Dokuments angehängt, das in das permanente Dokumentarchiv kopiert wird.

    Der Grund dafür, warum Dateinamen von Dokumenten, die in das permanente Dokumentarchiv verschoben oder kopiert werden, darin bestehen, konflikte verursachende Dateinamen zu vermeiden. Weitere Informationen zum Platzieren eines Haltebereichs auf Websites und zum permanenten Dokumentarchiv finden Sie unter Übersicht über das [in-situ-Archiv in SharePoint Server 2016.](https://support.office.com/article/5e400d68-cd51-444a-8fe6-e4df1d20aa95)

### <a name="miscellaneous"></a>Sonstiges
  
- Beim Herunterladen von Suchergebnissen mit dem eDiscovery-Exporttool wird möglicherweise der folgende Fehler angezeigt: `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` Dies ist ein vorübergehender Fehler, der in der Regel im Azure Storage-Speicherort auftritt. Um dieses Problem zu beheben, versuchen Sie erneut, [die Suchergebnisse herunterzuladen,](#step-2-download-the-search-results)wodurch das eDiscovery-Exporttool neu gestartet wird.

- Alle Suchergebnisse und die Exportberichte sind in einem Ordner enthalten, der denselben Namen wie die Inhaltssuche hat. Die E-Mail-Nachrichten, die exportiert wurden, befinden sich in einem Ordner mit dem Namen **Exchange**. Dokumente befinden sich in einem Ordner mit dem Namen **SharePoint**.

- Die Dateisystemmetadaten für Dokumente auf SharePoint und OneDrive for Business Websites werden beibehalten, wenn Dokumente auf Ihren lokalen Computer exportiert werden. Dies bedeutet, dass Dokumenteigenschaften, z. B. Erstellungs- und Datumsangaben der letzten Änderung, beim Exportieren von Dokumenten nicht geändert werden.

- Wenn Ihre Suchergebnisse ein Listenelement aus SharePoint enthalten, das der Suchabfrage entspricht, werden alle Zeilen in der Liste zusätzlich zu dem Element exportiert, das der Suchabfrage und allen Anlagen in der Liste entspricht. Der Grund für dieses Verhalten besteht darin, einen Kontext für Listenelemente bereitzustellen, die in den Suchergebnissen zurückgegeben werden. Die zusätzlichen Listenelemente und Anlagen können dazu führen, dass sich die Anzahl der exportierten Elemente von der ursprünglichen Schätzung der Suchergebnisse unterscheidet.
