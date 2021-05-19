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
description: Exportieren Sie die Suchergebnisse aus einer Inhaltssuche im Microsoft 365 Compliance Center auf einen lokalen Computer. E-Mail-Ergebnisse werden als PST-Dateien exportiert. Inhalte von SharePoint und OneDrive for Business werden als systemeigene Office exportiert.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8ec09706fecbe703fa2ab38cad5f8f8304484f44
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52536058"
---
# <a name="export-content-search-results"></a>Exportieren von Inhaltssuchergebnissen

Nachdem eine Inhaltssuche erfolgreich ausgeführt wurde, können Sie die Suchergebnisse auf einen lokalen Computer exportieren. Wenn Sie E-Mail-Ergebnisse exportieren, werden diese als PST-Dateien auf Ihren Computer heruntergeladen. Wenn Sie Inhalte aus SharePoint und OneDrive for Business exportieren, werden Kopien systemeigener Office exportiert. In den exportierten Suchergebnissen sind weitere Dokumente und Berichte enthalten.
  
Beim Exportieren der Ergebnisse einer Inhaltssuche werden die Ergebnisse vorbereitet und dann auf einen lokalen Computer heruntergeladen.
  
## <a name="before-you-export-search-results"></a>Vor dem Exportieren von Suchergebnissen

- Zum Exportieren von Suchergebnissen muss Ihnen die Rolle "Exportverwaltung" im Security & Compliance Center zugewiesen werden. Diese Rolle wird der integrierten Rollengruppe eDiscovery Manager zugewiesen. Sie ist nicht standardmäßig der Rollengruppe Organisationsverwaltung zugewiesen. Weitere Informationen finden Sie unter [Zuweisen von eDiscovery-Berechtigungen](assign-ediscovery-permissions.md).

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
  
- Es wird empfohlen, Suchergebnisse auf einen lokalen Computer herunterzuladen. Um zu vermeiden, dass die Firewall oder Proxyinfrastruktur Ihres Unternehmens beim Herunterladen von Suchergebnissen Probleme verursacht, können Sie das Herunterladen von Suchergebnissen auf einen virtuellen Desktop außerhalb Ihres Netzwerks in Betracht ziehen. Dadurch können Timeouts verringert werden, die in Azure-Datenverbindungen beim Exportieren einer großen Anzahl von Dateien auftreten. Weitere Informationen zu virtuellen Desktops finden Sie [unter Windows Virtual Desktop](https://azure.microsoft.com/services/virtual-desktop).

- Um die Leistung beim Herunterladen von Suchergebnissen zu verbessern, sollten Sie Suchen, die einen großen Satz von Ergebnissen zurückgeben, in kleinere Suchen unterteilen. Beispielsweise können Sie Datumsbereiche in Suchabfragen verwenden, um einen kleineren Satz von Ergebnissen zurückzukehren, die schneller heruntergeladen werden können.
  
- Wenn Sie Suchergebnisse exportieren, werden die Daten vorübergehend an einem von Microsoft bereitgestellten Azure Storage in der Microsoft Cloud gespeichert, bevor sie auf Ihren lokalen Computer heruntergeladen werden. Stellen Sie sicher, dass Ihre Organisation eine Verbindung mit dem Endpunkt in Azure herstellen kann, der **\* .blob.core.windows.net** ist (der Platzhalter stellt einen eindeutigen Bezeichner für Ihren Export dar). Die Suchergebnisse werden zwei Wochen nach der Azure Storage aus dem Speicherort gelöscht. 
  
- Wenn Ihre Organisation einen Proxyserver verwendet, um mit dem Internet zu kommunizieren, müssen Sie die Proxyservereinstellungen auf dem Computer definieren, den Sie zum Exportieren der Suchergebnisse verwenden (damit das Exporttool von Ihrem Proxyserver authentifiziert werden kann). Öffnen Sie dazu  diemachine.config-Datei an dem Speicherort, der Ihrer Version von Windows. 
  
  - **32-Bit:**`%windir%\Microsoft.NET\Framework\[version]\Config\machine.config`
  
  - **64-Bit:**`%windir%\Microsoft.NET\Framework64\[version]\Config\machine.config`
  
    Fügen Sie der Datei die  *folgenden Zeilenmachine.config*  zwischen den Tags und  `<configuration>`  `</configuration>` hinzu. Achten Sie darauf, die richtigen Werte für Ihre Organisation zu ersetzen, z.  `ProxyServer`  `Port` B. `proxy01.contoso.com:80` . 
  
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

- Wenn die Ergebnisse einer Inhaltssuche älter als 7 Tage sind und Sie einen Exportauftrag übermitteln, wird eine Fehlermeldung angezeigt, in der Sie aufgefordert werden, die Suche erneut zu führen, um die Suchergebnisse zu aktualisieren. Brechen Sie in diesem Fall den Export ab, führen Sie die Suche erneut aus, und starten Sie den Export erneut.

## <a name="step-1-prepare-search-results-for-export"></a>Schritt 1: Vorbereiten der Suchergebnisse für Export

Der erste Schritt besteht in der Vorbereitung der Suchergebnisse für den Export. Wenn Sie Ergebnisse vorbereiten, werden sie in einen von Microsoft bereitgestellten Azure Storage in der Microsoft Cloud hochgeladen. Inhalte von Postfächern und Websites werden mit einer maximalen Rate von 2 GB pro Stunde hochgeladen.
  
1. Wählen Sie Microsoft 365 Compliance Center die Inhaltssuche aus, aus der Sie Ergebnisse exportieren möchten.
  
2. Klicken Sie **im** Menü Aktionen unten auf der Flyoutseite auf **Ergebnisse exportieren.**

   ![Export results option in Actions menu](../media/ActionMenuExportResults.png)

   Die **Flyoutseite** Ergebnisse exportieren wird angezeigt. Die zum Exportieren von Inhalten verfügbaren Exportoptionen hängen davon ab, ob sich Suchergebnisse in Postfächern oder Websites befinden oder ob beides kombiniert wird.

3. Wählen **Sie unter** Ausgabeoptionen eine der folgenden Optionen aus:
  
   ![Exportausgabeoptionen](../media/ExportOutputOptions.png)

    - **Alle Elemente, mit Ausnahme von** Elementen, die nicht ein unbekanntes Format haben, sind verschlüsselt oder wurden aus anderen Gründen nicht indiziert. Mit dieser Option werden nur indizierte Elemente exportiert.
  
    - **Alle Elemente, einschließlich** der Elemente, die ein nicht unbekanntes Format haben, sind verschlüsselt oder wurden aus anderen Gründen nicht indiziert. Mit dieser Option werden indizierte und nicht indizierte Elemente exportiert.
  
    - **Nur Elemente, die ein nicht unbekanntes** Format haben, verschlüsselt sind oder aus anderen Gründen nicht indiziert wurden. Mit dieser Option werden nur nicht indizierte Elemente exportiert.

      Im Abschnitt [Weitere Informationen finden](#more-information) Sie eine Beschreibung, wie teilweise indizierte Elemente exportiert werden. Weitere Informationen zu teilweise indizierten Elementen finden Sie unter [Teilweise indizierte Elemente in der Inhaltssuche](partially-indexed-items-in-content-search.md).

4. Wählen **Sie unter Exchange Inhalt exportieren als** eine der folgenden Optionen aus:
  
   ![Exchange-Optionen](../media/ExchangeExportOptions.png)

    - **Eine PST-Datei für jedes Postfach:** Exportiert eine PST-Datei für jedes Benutzerpostfach, das Suchergebnisse enthält. Alle Ergebnisse aus dem Archivpostfach des Benutzers sind in derselben PST-Datei enthalten. Mit dieser Option wird die Postfachordnerstruktur aus dem Quellpostfach reproduziert.
  
    - **Eine PST-Datei,** die alle Nachrichten enthält: Exportiert eine einzelne PST-Datei *(Exchange.pst),* die die Suchergebnisse aus allen Quellpostfächern enthält, die in der Suche enthalten sind. Mit dieser Option wird die Postfachordnerstruktur für jede Nachricht reproduziert.
  
    - **Eine PST-Datei,** die alle Nachrichten in einem einzigen Ordner enthält: Exportiert Suchergebnisse in eine einzelne PST-Datei, in der sich alle Nachrichten in einem einzigen Ordner auf oberster Ebene befinden. Mit dieser Option können Prüfer Elemente in chronologischer Reihenfolge überprüfen (Elemente werden nach gesendeten Datums sortiert), ohne in der ursprünglichen Postfachordnerstruktur für jedes Element navigieren zu müssen.
  
    - **Einzelne Nachrichten:** Exportiert Suchergebnisse als einzelne E-Mail-Nachrichten im MSG-Format. Wenn Sie diese Option auswählen, werden die E-Mail-Suchergebnisse in einen Ordner im Dateisystem exportiert. Der Ordnerpfad für einzelne Nachrichten ist identisch mit dem, der verwendet wird, wenn Sie die Ergebnisse in eine PST-Datei exportiert haben.
  
5. Konfigurieren Sie die folgenden zusätzlichen Optionen:

   ![Konfigurieren anderer Exportoptionen](../media/OtherExportOptions.png)

   1. Aktivieren Sie **das Kontrollkästchen Deduplizierung für Exchange aktivieren,** um doppelte Nachrichten auszuschließen.
  
      Wenn Sie diese Option auswählen, wird nur eine Kopie einer Nachricht exportiert, auch wenn in den durchsuchten Postfächern mehrere Kopien derselben Nachricht gefunden werden. Der Exportergebnisbericht (eine Datei mit dem Namen Results.csv) enthält eine Zeile für jede Kopie einer doppelten Nachricht, sodass Sie die Postfächer (oder öffentlichen Ordner) identifizieren können, die eine Kopie der doppelten Nachricht enthalten. Weitere Informationen zur Deduplizierung und zur Ermittlung doppelter Elemente finden Sie unter [Deduplizierung in eDiscovery-Suchergebnissen.](de-duplication-in-ediscovery-search-results.md)
  
   2. Aktivieren Sie das Kontrollkästchen Versionen **für SharePoint dateien enthalten,** um alle Versionen von Dokumenten SharePoint exportieren. Diese Option wird nur angezeigt, wenn die Inhaltsquellen der Suche SharePoint oder OneDrive for Business enthalten.
  
   3. Wählen Sie **die Datei exportieren in einem komprimierten (gezippten) Ordner aus. Enthält nur einzelne Nachrichten und SharePoint, um** Suchergebnisse in komprimierte Ordner zu exportieren. Diese Option wird nur angezeigt, wenn Sie auswählen, Exchange Elemente als einzelne Nachrichten zu exportieren und wenn die Suchergebnisse SharePoint oder OneDrive enthalten. Diese Option wird in erster Linie verwendet, um den Grenzwert von 260 Zeichen in Windows dateinamen beim Exportieren von Elementen zu verwenden. Weitere Informationen finden Sie unter "Dateinamen [](#more-information) exportierter Elemente".
  
6. Klicken **Sie auf Exportieren,** um den Exportvorgang zu starten. Die Suchergebnisse werden zum Herunterladen vorbereitet, d. h. sie werden von den ursprünglichen Inhaltsspeicherorten gesammelt und dann an einen Azure Storage in der Microsoft Cloud hochgeladen. Dieser Vorgang kann einige Minuten in Anspruch nehmen.

Anweisungen zum Herunterladen der exportierten Suchergebnisse finden Sie im nächsten Abschnitt.
  
## <a name="step-2-download-the-search-results"></a>Schritt 2: Herunterladen der Suchergebnisse

Im nächsten Schritt laden Sie die Suchergebnisse aus dem Azure Storage auf Ihren lokalen Computer herunter.
  
1. Wählen Sie **auf der** Seite Inhaltssuche im Microsoft 365 Compliance Center die Registerkarte **Exporte** aus.
  
   Möglicherweise müssen Sie auf **Aktualisieren klicken,** um die Liste der Exportaufträge so zu aktualisieren, dass der erstellte Exportauftrag angezeigt wird. Exportaufträge haben denselben Namen wie die entsprechende Suche mit **_Export** an den Suchnamen angefügt.
  
2. Wählen Sie den Exportauftrag aus, den Sie in Schritt 1 erstellt haben.

3. Klicken Sie auf der Flyoutseite unter **Export key** auf Kopieren in **die Zwischenablage**. Sie verwenden diesen Schlüssel in Schritt 6, um die Suchergebnisse herunterzuladen.
  
   > [!IMPORTANT]
   > Da jeder benutzer das eDiscovery-Exporttool installieren und starten kann und diesen Schlüssel zum Herunterladen der Suchergebnisse verwenden kann, sollten Sie Vorkehrungen treffen, um diesen Schlüssel zu schützen, so wie Sie Kennwörter oder andere sicherheitsrelevante Informationen schützen würden.

4. Klicken Sie oben auf der Flyoutseite auf **Ergebnisse herunterladen.**

5. Wenn Sie aufgefordert werden, das **eDiscovery-Exporttool zu** installieren, klicken Sie auf **Installieren**.

6. Gehen Sie **im eDiscovery-Exporttool** wie folgt vor:

   ![eDiscovery-Exporttool](../media/eDiscoveryExportTool.png)

   1. Fügen Sie den Exportschlüssel, den Sie in Schritt 3 kopiert haben, in das entsprechende Feld ein.
  
   2. Klicken Sie auf **Durchsuchen**, um das Verzeichnis anzugeben, in das die Dateien mit den Suchergebnissen heruntergeladen werden sollen.
  
      > [!IMPORTANT]
      >  Aufgrund der hohen Netzwerkaktivität während des Downloads sollten Sie Suchergebnisse nur an einen Speicherort auf einem internen Laufwerk auf Ihrem lokalen Computer herunterladen. Befolgen Sie die folgenden Richtlinien, um die beste Downloaderfahrung zu bieten: <br/>
      >- Laden Sie keine Suchergebnisse in einen UNC-Pfad, ein zugeordnetes Netzwerklaufwerk, ein externes USB-Laufwerk oder ein synchronisiertes OneDrive for Business herunter.<br/>
      >- Deaktivieren Sie die Virenschutzprüfung für den Ordner, in den Sie das Suchergebnis herunterladen.<br/>
      >- Laden Sie Suchergebnisse für gleichzeitige Downloadaufträge in verschiedene Ordner herunter.

6. Klicken Sie zum Herunterladen der Suchergebnisse auf Ihren Computer auf **Starten**.
  
    Das **eDiscovery-Exporttool** zeigt Statusinformationen zum Exportvorgang an, einschließlich einer Schätzung der Anzahl (und Größe) der verbleibenden Elemente, die heruntergeladen werden sollen. Wenn der Exportvorgang abgeschlossen ist, können Sie auf die Dateien am Speicherort zugreifen, an dem sie heruntergeladen wurden.

## <a name="more-information"></a>Weitere Informationen

Hier finden Sie weitere Informationen zum Exportieren von Suchergebnissen.
  
[Exportgrenzwerte](#export-limits)
  
[Exportieren von Berichten](#export-reports)
  
[Exportieren teilweise indizierter Elemente](#exporting-partially-indexed-items)

[Exportieren einzelner Nachrichten oder PST-Dateien](#exporting-individual-messages-or-pst-files)

[Entschlüsseln von RMS-geschützten E-Mail-Nachrichten und verschlüsselten Dateianlagen](#decrypting-rms-protected-email-messages-and-encrypted-file-attachments)

[Dateinamen exportierter Elemente](#filenames-of-exported-items)  
  
[Sonstiges](#miscellaneous)
  
### <a name="export-limits"></a>Exportgrenzwerte

Informationen zu Beschränkungen beim Exportieren von Inhaltssuchergebnissen finden Sie im Abschnitt "Exportlimits" unter [Limits for content search](limits-for-content-search.md#export-limits).

### <a name="export-reports"></a>Exportieren von Berichten
  
- Wenn Sie Suchergebnisse exportieren, werden zusätzlich zu den Suchergebnissen die folgenden Berichte einbezogen.
  
  - **Exportzusammenfassung** Ein Excel, das eine Zusammenfassung des Exports enthält. Dazu gehören Informationen wie die Anzahl der durchsuchten Inhaltsquellen, die geschätzten und heruntergeladenen Größen der Suchergebnisse sowie die geschätzte und heruntergeladene Anzahl der exportierten Elemente.
  
  - **Manifest** Eine Manifestdatei (im XML-Format), die Informationen zu jedem Element enthält, das in den Suchergebnissen enthalten ist.
  
  - **Ergebnisse** Ein Excel, das Informationen zu jedem Element enthält, das als Suchergebnis heruntergeladen wird. Für E-Mails enthält das Ergebnisprotokoll Informationen zu jeder Nachricht, einschließlich:
  
    - Der Speicherort der Nachricht im Quellpostfach (einschließlich der Angabe, ob die Nachricht sich im primären oder im Archivpostfach befindet).
  
    - Das Datum, an dem die Nachricht gesendet oder empfangen wurde.

    - Die Betreffzeile der Nachricht.

    - Absender und Empfänger der Nachricht.

    - Gibt an, ob es sich bei der Nachricht um eine doppelte Nachricht handelt, wenn Sie die Deduplizierungsoption beim Exportieren der Suchergebnisse aktiviert haben. Doppelte Nachrichten haben einen Wert in der Spalte **Duplizieren** in Element, der die Nachricht als Duplikat identifiziert. Der Wert in der **Spalte Duplizieren** in Element enthält die Elementidentität der nachricht, die exportiert wurde. Weitere Informationen finden Sie unter [Deduplizierung in eDiscovery-Suchergebnissen](de-duplication-in-ediscovery-search-results.md).

      Für Dokumente von SharePoint und OneDrive for Business enthält das Ergebnisprotokoll Informationen zu jedem Dokument, einschließlich:

      - Die URL für das Dokument.

      - Die URL für die Websitesammlung, in der sich das Dokument befindet.

      - Das Datum, an dem das Dokument zuletzt geändert wurde.

      - Der Name des Dokuments (das sich in der Spalte Betreff im Ergebnisprotokoll befindet).

  - **Nicht indizierte Elemente** Ein Excel, das Informationen zu teilweise indizierten Elementen enthält, die in den Suchergebnissen enthalten wären. Wenn Sie beim Generieren des Suchergebnissesberichts nicht teilweise indizierte Elemente enthalten, wird dieser Bericht weiterhin heruntergeladen, ist jedoch leer.

  - **Fehler und Warnungen** Enthält Fehler und Warnungen für Dateien, die beim Export aufgetreten sind. Informationen zu den einzelnen Fehlern oder Warnungen finden Sie in der Spalte Fehlerdetails.

  - **Übersprungene Elemente** Wenn Sie Suchergebnisse aus websites SharePoint und OneDrive for Business exportieren, enthält der Export in der Regel einen Bericht über übersprungene Elemente (SkippedItems.csv). Bei den in diesem Bericht genannten Elementen handelt es sich in der Regel um Elemente, die nicht heruntergeladen werden, z. B. ein Ordner oder eine Dokumentenmappe. Das Nichtexportieren dieser Arten von Elementen ist entwurfsweise. Für andere Elemente, die übersprungen wurden, zeigen das Feld "Fehlertyp" und "Fehlerdetails" im Bericht übersprungene Elemente den Grund an, warum das Element übersprungen wurde und nicht mit den anderen Suchergebnissen heruntergeladen wurde.

  - **Trace.log** Enthält detaillierte Protokollierungsinformationen zum Exportprozess und kann beim Aufdecken von Problemen während des Exports helfen. Wenn Sie ein Ticket mit dem Microsoft Support zu einem Problem im Zusammenhang mit dem Exportieren von Suchergebnissen öffnen, werden Sie möglicherweise aufgefordert, dieses Ablaufverfolgungsprotokoll zur Verfügung zu stellen.
  
    > [!NOTE]
    > Sie können diese Dokumente einfach exportieren, ohne die tatsächlichen Suchergebnisse exportieren zu müssen. Weitere [Informationen finden Sie unter Exportieren eines Inhaltssuchberichts.](export-a-content-search-report.md)
  
### <a name="exporting-partially-indexed-items"></a>Exportieren teilweise indizierter Elemente
  
- Wenn Sie Postfachelemente aus einer Inhaltssuche exportieren, die alle Postfachelemente in den Suchergebnissen zurückgibt (da in der Suchabfrage keine Schlüsselwörter enthalten sind), werden teilweise indizierte Elemente nicht in die PST-Datei kopiert, die die nicht indizierten Elemente enthält. Dies liegt daran, dass alle Elemente, einschließlich teilweise indizierter Elemente, automatisch in die regulären Suchergebnisse einbezogen werden. Dies bedeutet, dass teilweise indizierte Elemente in einer PST-Datei (oder als einzelne Nachrichten) enthalten sind, die die anderen indizierten Elemente enthält.

    Wenn Sie die indizierten und teilweise indizierten Elemente exportieren oder nur die indizierten Elemente aus einer Inhaltssuche exportieren, die alle Elemente zurückgibt, wird dieselbe Anzahl von Elementen heruntergeladen. Dies geschieht, obwohl die geschätzten Suchergebnisse für die Inhaltssuche (die in den Suchstatistiken im Security & Compliance Center angezeigt werden) weiterhin eine separate Schätzung für die Anzahl der teilweise indizierten Elemente enthalten. Angenommen, die Schätzung für eine Suche, die alle Elemente enthält (keine Schlüsselwörter in der Suchabfrage), zeigt, dass 1.000 Elemente gefunden wurden und dass auch 200 teilweise indizierte Elemente gefunden wurden. In diesem Fall enthalten die 1.000 Elemente die teilweise indizierten Elemente, da die Suche alle Elemente zurückgibt. Anders ausgedrückt: Es werden 1.000 Elemente insgesamt von der Suche zurückgegeben, und nicht 1.200 Elemente (wie erwartet). Wenn Sie die Ergebnisse dieser Suche exportieren und indizierte und teilweise indizierte Elemente exportieren (oder nur teilweise indizierte Elemente exportieren), werden 1.000 Elemente heruntergeladen. Dies liegt daran, dass teilweise indizierte Elemente in die regulären (indizierten) Ergebnisse eingeschlossen werden, wenn Sie eine leere Suchabfrage verwenden, um alle Elemente zurückzukehren. Wenn Sie in diesem Beispiel nur teilweise indizierte Elemente exportieren möchten, werden nur die 200 nicht indizierten Elemente heruntergeladen.

    Beachten Sie außerdem, dass im vorherigen Beispiel (wenn Sie indizierte und teilweise indizierte Elemente exportieren oder nur indizierte Elemente exportieren) im Export **summary** report, der in den exportierten Suchergebnissen enthalten ist, 1.000 geschätzte Elemente und 1.000 heruntergeladene Elemente aus denselben Gründen wie zuvor beschrieben auflistet. 

- Wenn die Suche, aus der Sie Ergebnisse exportieren, eine Suche nach bestimmten Inhaltsstandorten oder allen Inhaltsstandorten in Ihrer Organisation war, werden nur die Teilelemente von Inhaltsstandorten exportiert, die Elemente enthalten, die den Suchkriterien entsprechen. Anders ausgedrückt: Wenn keine Suchergebnisse in einem Postfach oder einer Website gefunden werden, werden teilweise indizierte Elemente in diesem Postfach oder standort nicht exportiert. Der Grund dafür ist, dass das Exportieren teilweise indizierter Elemente von vielen Speicherorten in der Organisation die Wahrscheinlichkeit von Exportfehlern erhöhen und die Zeit erhöhen kann, die zum Exportieren und Herunterladen der Suchergebnisse benötigt wird.

    Um teilweise indizierte Elemente aus allen Inhaltsverzeichnissen für eine Suche zu exportieren, konfigurieren Sie die Suche so, dass alle Elemente zurückgegeben werden (durch Entfernen von Schlüsselwörtern aus der Suchabfrage), und exportieren Sie dann nur teilweise indizierte Elemente, wenn Sie die Suchergebnisse exportieren.

    ![Verwenden der dritten Exportoption zum Exportieren nur nicht indizierter Elemente](../media/5d7be338-a0e5-425f-8ba5-92769c24bf75.png)
  
- Beim Exportieren von Suchergebnissen von SharePoint- oder OneDrive for Business-Websites hängt die Möglichkeit zum Exportieren nicht indizierter Elemente auch von der ausgewählten Exportoption und davon ab, ob eine durchsuchte Website ein indiziertes Element enthält, das den Suchkriterien entspricht. Wenn Sie beispielsweise bestimmte SharePoint- oder OneDrive for Business-Websites durchsuchen und keine Suchergebnisse gefunden werden, werden keine nicht indizierten Elemente von diesen Websites exportiert, wenn Sie die zweite Exportoption zum Exportieren indizierter und nicht indizierter Elemente auswählen. Wenn ein indiziertes Element von einer Website den Suchkriterien entspricht, werden alle nicht indizierten Elemente von dieser Website exportiert, wenn indizierte und nicht indizierte Elemente exportiert werden. In der folgenden Abbildung werden die Exportoptionen beschrieben, die darauf basieren, ob eine Website ein indiziertes Element enthält, das den Suchkriterien entspricht.

    ![Wählen Sie die Exportoption basierend darauf aus, ob eine Website ein indiziertes Element enthält, das den Suchkriterien entspricht.](../media/94f78786-c6bb-42fb-96b3-7ea3998bcd39.png)

    a. Nur indizierte Elemente, die den Suchkriterien entsprechen, werden exportiert. Es werden keine teilweise indizierten Elemente exportiert.

    b. Wenn keine indizierten Elemente von einer Website den Suchkriterien entsprechen, werden teilweise indizierte Elemente von derselben Website nicht exportiert. Wenn indizierte Elemente von einer Website in den Suchergebnissen zurückgegeben werden, werden die teilweise indizierten Elemente von dieser Website exportiert. Anders ausgedrückt: Nur die teilweise indizierten Elemente von Websites, die Elemente enthalten, die den Suchkriterien entsprechen, werden exportiert.

    c. Alle teilweise indizierten Elemente von allen Websites in der Suche werden exportiert, unabhängig davon, ob eine Website Elemente enthält, die den Suchkriterien entsprechen.

    Wenn Sie teilweise indizierte Elemente exportieren möchten, werden teilweise indizierte Postfachelemente in eine separate PST-Datei exportiert, unabhängig von der Option, die Sie unter **Export Exchange content as auswählen.**

- Wenn teilweise indizierte Elemente in den Suchergebnissen zurückgegeben werden (da andere Eigenschaften teilweise indizierter Elemente den Suchkriterien entsprechen), werden diese teilweise indizierten Elemente mit den regulären Suchergebnissen exportiert. Wenn Sie also sowohl indizierte als auch teilweise indizierte Elemente exportieren möchten (indem Sie die Option Alle Elemente auswählen, einschließlich der Elemente, die ein nicht unbekanntes Format **haben,** verschlüsselt sind oder aus anderen Gründen nicht indiziert wurden), werden die teilweise indizierten Elemente, die mit den regulären Ergebnissen exportiert wurden, im Results.csv-Bericht aufgeführt. Sie werden nicht im Bericht Nicht indizierte items.csv aufgeführt.
  
### <a name="exporting-individual-messages-or-pst-files"></a>Exportieren einzelner Nachrichten oder PST-Dateien
  
- Wenn der Dateipfadname einer Nachricht den maximalen Zeichengrenzwert für Windows, wird der Dateipfadname abgeschnitten. Der ursprüngliche Dateipfadname wird jedoch im Manifest und im ResultsLog aufgeführt.
  
- Wie bereits erläutert, werden E-Mail-Suchergebnisse in einen Ordner im Dateisystem exportiert. Der Ordnerpfad für einzelne Nachrichten würde den Ordnerpfad im Postfach des Benutzers replizieren. Bei einer Suche mit dem Namen "ContosoCase101" befinden sich beispielsweise Nachrichten im Posteingang eines Benutzers im Ordnerpfad  `~ContosoCase101\\<date of export\Exchange\user@contoso.com (Primary)\Top of Information Store\Inbox` .

- Wenn Sie E-Mail-Nachrichten in einer PST-Datei exportieren  möchten, die alle Nachrichten in einem einzigen Ordner enthält, sind ein Ordner "Gelöschte Elemente" und ein Ordner "Suchordner" in der obersten Ebene des PST-Ordners enthalten.  Diese Ordner sind leer.

- Wie bereits erwähnt, müssen Sie E-Mail-Suchergebnisse als einzelne Nachrichten exportieren, um RMS-geschützte Nachrichten zu entschlüsseln, wenn sie exportiert werden. Verschlüsselte Nachrichten bleiben verschlüsselt, wenn Sie E-Mail-Suchergebnisse als PST-Datei exportieren.
  
### <a name="decrypting-rms-protected-email-messages-and-encrypted-file-attachments"></a>Entschlüsseln von RMS-geschützten E-Mail-Nachrichten und verschlüsselten Dateianlagen

Alle rechtegeschützten (RMS-geschützten) E-Mail-Nachrichten, die in den Ergebnissen einer Inhaltssuche enthalten sind, werden beim Exportieren entschlüsselt. Darüber hinaus wird jede Datei, [](encryption.md) die mit einer Microsoft-Verschlüsselungstechnologie verschlüsselt ist und an eine E-Mail-Nachricht angefügt ist, die in den Suchergebnissen enthalten ist, auch entschlüsselt, wenn sie exportiert wird. Diese Entschlüsselungsfunktion ist standardmäßig für Mitglieder der Rollengruppe eDiscovery-Manager aktiviert. Dies liegt daran, dass dieser Rollengruppe standardmäßig die Verwaltungsrolle RMS Decrypt zugewiesen ist. Beachten Sie beim Exportieren verschlüsselter E-Mail-Nachrichten und Anlagen folgendes:
  
- Wie bereits erläutert, müssen Sie zum Entschlüsseln von RMS-geschützten Nachrichten beim Exportieren die Suchergebnisse als einzelne Nachrichten exportieren. Wenn Sie Suchergebnisse in eine PST-Datei exportieren, bleiben RMS-geschützte Nachrichten verschlüsselt.

- Entschlüsselte Nachrichten werden im **ResultsLog-Bericht** identifiziert. Dieser Bericht enthält eine Spalte mit dem Namen **Decode Status**, und der Wert **Decoded** in dieser Spalte identifiziert die entschlüsselten Nachrichten.

- Neben dem Entschlüsseln von Dateianlagen beim Exportieren von Suchergebnissen können Sie auch eine Vorschau der entschlüsselten Datei anzeigen, wenn Sie eine Vorschau der Suchergebnisse anzeigen. Sie können die durch Rechte geschützte E-Mail-Nachricht nur anzeigen, nachdem Sie sie exportiert haben.

- Zu diesem Zeitpunkt umfasst die Entschlüsselungsfunktion beim Exportieren von Suchergebnissen keine verschlüsselten Inhalte von SharePoint und OneDrive for Business Websites. In Kürze wird jedoch Unterstützung für Dokumente verfügbar sein, die mit Microsoft-Verschlüsselungstechnologien verschlüsselt und in SharePoint Online und OneDrive for Business.

- Wenn Sie verhindern müssen, dass eine Person RMS-schutznachrichten und verschlüsselte Dateianlagen entschlüsselt, müssen Sie eine benutzerdefinierte Rollengruppe erstellen (indem Sie die integrierte eDiscovery-Manager-Rollengruppe kopieren) und dann die Verwaltungsrolle RMS Decrypt aus der benutzerdefinierten Rollengruppe entfernen. Fügen Sie dann die Person hinzu, die Sie nachrichten nicht entschlüsseln möchten, als Mitglied der benutzerdefinierten Rollengruppe.
  
### <a name="filenames-of-exported-items"></a>Dateinamen exportierter Elemente
  
- Für den vollständigen Pfadnamen für E-Mail-Nachrichten und Websitedokumente, die auf Ihren lokalen Computer exportiert werden, gibt es eine Beschränkung von 260 Zeichen (vom Betriebssystem auferlegt). Der vollständige Pfadname für exportierte Elemente enthält den ursprünglichen Speicherort des Elements und den Ordnerspeicherort auf dem lokalen Computer, auf den die Suchergebnisse heruntergeladen werden. Wenn Sie beispielsweise angeben, dass die Suchergebnisse in das  `C:\Users\Admin\Desktop\SearchResults` eDiscovery-Export-Tool heruntergeladen werden sollen, ist der vollständige Pfadname für ein heruntergeladenes E-Mail-Element  `C:\Users\Admin\Desktop\SearchResults\ContentSearch1\03.15.2017-1242PM\Exchange\sarad@contoso.com (Primary)\Top of Information Store\Inbox\Insider trading investigation.msg` .

- Wenn der Grenzwert von 260 Zeichen überschritten wird, wird der vollständige Pfadname für ein Element gekürzt, basierend auf den folgenden Bedingungen:

  - Wenn der vollständige Pfadname länger als 260 Zeichen ist, wird der Dateiname verkürzt, um den Grenzwert zu überschreiten. Beachten Sie, dass der abgeschnittene Dateiname (mit Ausnahme der Dateierweiterung) nicht weniger als acht Zeichen lang ist.

  - Wenn der vollständige Pfadname nach dem Kürzen des Dateinamens noch zu lang ist, wird das Element vom aktuellen Speicherort in den übergeordneten Ordner verschoben. Wenn der Pfadname noch zu lang ist, wird der Vorgang wiederholt: Kürzen Sie den Dateinamen, und verschieben Sie gegebenenfalls erneut in den übergeordneten Ordner. Dieser Vorgang wird wiederholt, bis der vollständige Pfadname unter dem Grenzwert von 260 Zeichen liegt.

  - Wenn bereits ein abgeschnittener vollständiger Pfadname vorhanden ist, wird am Ende des Dateinamens eine Versionsnummer hinzugefügt. Beispiel: `statusmessage(2).msg` .

    Um dieses Problem zu beheben, sollten Sie das Herunterladen von Suchergebnissen an einen Speicherort mit einem kurzen Pfadnamen in Betracht ziehen. Beispielsweise würde das Herunterladen von Suchergebnissen in einen Ordner namens weniger Zeichen zu den Pfadnamen exportierter Elemente hinzufügen als das Herunterladen in einen  `C:\Results` Ordner namens  `C:\Users\Admin\Desktop\Results` .

- Wenn Sie Websitedokumente exportieren, ist es auch möglich, dass der ursprüngliche Dateiname eines Dokuments geändert wird. Dies geschieht insbesondere für Dokumente, die aus einer SharePoint oder OneDrive for Business gelöscht wurden, die in einem Halteraum platziert wurden. Nachdem ein Dokument, das sich auf einer Website befindet, die sich im Haltezustand befindet, gelöscht wurde, wird das gelöschte Dokument automatisch in die Erhaltungsarchivbibliothek für die Website verschoben (die erstellt wurde, als die Website in den Haltezustand verschoben wurde). Wenn das gelöschte Dokument in die Erhaltungsarchivbibliothek verschoben wird, wird eine zufällig generierte und eindeutige ID an den ursprünglichen Dateinamen des Dokuments angefügt. Wenn beispielsweise der Dateiname für ein Dokument ist und dieses Dokument später gelöscht und in die Erhaltungsarchivbibliothek verschoben wird, wird der Dateiname des Dokuments, das in die Erhaltungsarchivbibliothek verschoben wird, in etwa  `FY2017Budget.xlsx`  `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx` geändert. Wenn ein Dokument in der Erhaltungsarchivbibliothek der Abfrage einer Inhaltssuche entspricht und Sie die Ergebnisse dieser Suche exportieren, hat die exportierte Datei den geänderten Dateinamen. In diesem Beispiel ist der Dateiname des exportierten Dokuments  `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx` .

    Wenn ein Dokument auf einer Website geändert wird, die sich im Haltezustand befindet (und die Versionsierung für die Dokumentbibliothek auf der Website aktiviert wurde), wird automatisch eine Kopie der Datei in der Erhaltungsarchivbibliothek erstellt. In diesem Fall wird auch eine zufällig generierte und eindeutige ID an den Dateinamen des Dokuments angefügt, das in die Erhaltungsarchivbibliothek kopiert wird.

    Der Grund, warum Dateinamen von Dokumenten, die verschoben oder in die Erhaltungsarchivbibliothek kopiert werden, sind, um in Konflikt konfliktende Dateinamen zu verhindern. Weitere Informationen zum Platzieren eines Haltezustands auf Websites und zur Bibliothek für das Aufbewahrungsarchiv finden Sie unter [Overview of in-place hold in SharePoint Server 2016](https://support.office.com/article/5e400d68-cd51-444a-8fe6-e4df1d20aa95).

### <a name="miscellaneous"></a>Sonstiges
  
- Beim Herunterladen von Suchergebnissen mithilfe des eDiscovery-Exporttools wird möglicherweise der folgende Fehler angezeigt: Dies ist ein vorübergehender Fehler, der in der Regel am Speicherort Azure Storage `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` wird. Um dieses Problem zu beheben, versuchen Sie es erneut, [die Suchergebnisse herunterzuladen,](#step-2-download-the-search-results)wodurch das eDiscovery-Exporttool neu gestartet wird.

- Alle Suchergebnisse und Exportberichte sind in einem Ordner enthalten, der denselben Namen wie die Inhaltssuche hat. Die E-Mail-Nachrichten, die exportiert wurden, befinden sich in einem Ordner mit dem Namen **Exchange**. Dokumente befinden sich in einem Ordner namens **SharePoint**.

- Die Dateisystemmetadaten für Dokumente auf SharePoint und OneDrive for Business werden beibehalten, wenn Dokumente auf Ihren lokalen Computer exportiert werden. Das bedeutet, dass Dokumenteigenschaften, z. B. erstellte und zuletzt geänderte Datumsangaben, beim Exportieren von Dokumenten nicht geändert werden.

- Wenn ihre Suchergebnisse ein Listenelement aus SharePoint enthalten, das der Suchabfrage entspricht, werden alle Zeilen in der Liste zusätzlich zu dem Element exportiert, das der Suchabfrage und allen Anlagen in der Liste entspricht. Der Grund für dieses Verhalten besteht in der Bereitstellung eines Kontexts für Listenelemente, die in den Suchergebnissen zurückgegeben werden. Die zusätzlichen Listenelemente und Anlagen können dazu führen, dass die Anzahl der exportierten Elemente von der ursprünglichen Schätzung der Suchergebnisse abhing.
