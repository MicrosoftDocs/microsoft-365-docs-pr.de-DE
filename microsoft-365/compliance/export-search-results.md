---
title: Exportieren von Inhaltssuchergebnissen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
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
description: 'Exportieren Sie die Suchergebnisse aus einer Inhaltssuche im Compliance Center des Sicherheits & auf einen lokalen Computer. E-Mail-Ergebnisse werden als PST-Dateien exportiert. Inhalte aus SharePoint-und OneDrive für Unternehmen-Websites werden als systemeigene Office-Dokumente exportiert. '
ms.openlocfilehash: 3b9997b11763d91357e53d12ef70ffb025a04d74
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43615989"
---
# <a name="export-content-search-results"></a>Exportieren von Inhaltssuchergebnissen

Nachdem eine Inhaltssuche erfolgreich ausgeführt wurde, können Sie die Suchergebnisse auf einen lokalen Computer exportieren. Wenn Sie E-Mail-Ergebnisse exportieren, werden diese als PST-Dateien auf Ihren Computer heruntergeladen. Wenn Sie Inhalte aus SharePoint und OneDrive für Unternehmen Websites exportieren, werden Kopien von systemeigenen Office-Dokumenten exportiert. In den exportierten Suchergebnissen sind andere Dokumente und Berichte enthalten.
  
Alle RMS-verschlüsselten e-Mail-Nachrichten, die in den Ergebnissen einer Inhaltssuche enthalten sind, werden beim Exportieren (als einzelne Nachrichten) entschlüsselt. Diese Entschlüsselungsfunktion ist für Mitglieder der eDiscovery-Manager-Rollengruppe standardmäßig aktiviert. Dies liegt daran, dass die Verwaltungsrolle "RMS Decrypt" dieser Rollengruppe zugewiesen ist. Im Abschnitt [Weitere Informationen](#more-information) finden Sie ausführliche Informationen zur RMS-Entschlüsselung beim Exportieren von Suchergebnissen. 
  
Das Exportieren der Ergebnisse einer Inhaltssuche umfasst das Vorbereiten der Ergebnisse und das anschließende herunterladen auf einen lokalen Computer.
  
## <a name="before-you-begin"></a>Bevor Sie beginnen

- Um Suchergebnisse zu exportieren, müssen Sie der Rolle "Exportverwaltung" im Security & Compliance Center zugewiesen sein. Diese Rolle wird der integrierten eDiscovery-Manager-Rollengruppe zugewiesen. Sie wird nicht standardmäßig der Rollengruppe "Organisationsverwaltung" zugewiesen. Weitere Informationen finden Sie unter [Zuweisen von eDiscovery-Berechtigungen](assign-ediscovery-permissions.md).
    
- Der Computer, den Sie zum Exportieren der Suchergebnisse verwenden, muss die folgenden Voraussetzungen erfüllen:
    
  - 32-Bit-oder 64-Bit-Versionen von Windows 7 und höheren Versionen
    
  - Microsoft .NET Framework 4,7
    
- Sie müssen einen der folgenden unterstützten Browser verwenden, um das eDiscovery-Export Tool<sup>1</sup>auszuführen:

  - Microsoft Edge <sup>2</sup>
  
    ODER

  - Microsoft Internet Explorer 10 und höhere Versionen
    
  > [!NOTE]
  > <sup>1</sup> Microsoft stellt keine Drittanbietererweiterungen oder Add-ons für ClickOnce-Anwendungen her. Das Exportieren von Suchergebnissen mit einem nicht unterstützten Browser mit Erweiterungen oder Add-ons von Drittanbietern wird nicht unterstützt.<br/>
  > <sup>2</sup> aufgrund der letzten Änderungen an Microsoft Edge ist die ClickOnce-Unterstützung standardmäßig nicht mehr aktiviert. Anweisungen zum Aktivieren der ClickOnce-Unterstützung in Edge finden Sie unter [Verwenden des eDiscovery-Export Tools in Microsoft Edge](configure-edge-to-export-search-results.md).
    
- Wenn Sie Suchergebnisse herunterladen (in Schritt 2 beschrieben), können Sie die Downloadgeschwindigkeit durch Konfigurieren einer Windows-Registrierungseinstellung auf dem Computer, den Sie zum Exportieren der Suchergebnisse verwenden, verbessern. Weitere Informationen finden Sie unter [höhere Downloadgeschwindigkeit beim Exportieren von eDiscovery-Suchergebnissen aus Office 365](increase-download-speeds-when-exporting-ediscovery-results.md).
    
- Wenn Sie Suchergebnisse exportieren, werden die Daten vorübergehend in einem von Microsoft bereitgestellten Azure-Speicherort in der Microsoft-Cloud gespeichert, bevor Sie auf Ihren lokalen Computer heruntergeladen werden. Stellen Sie sicher, dass Ihre Organisation eine Verbindung mit dem Endpunkt in Azure herstellen kann, also ** \*. BLOB.Core.Windows.net** (der Platzhalter stellt einen eindeutigen Bezeichner für den Export dar). Die Suchergebnis Daten werden zwei Wochen nach ihrer Erstellung aus dem Azure-Speicherort gelöscht. 
    
- Wenn Ihre Organisation einen Proxy Server für die Kommunikation mit dem Internet verwendet, müssen Sie die Proxyservereinstellungen auf dem Computer definieren, den Sie zum Exportieren der Suchergebnisse verwenden (sodass das Export Tool von Ihrem Proxy Server authentifiziert werden kann). Öffnen Sie dazu die Datei *Machine. config* an dem Speicherort, der Ihrer Windows-Version entspricht. 
    
  - **32-Bit:**`%windir%\Microsoft.NET\Framework\[version]\Config\machine.config`
    
  - **64-Bit:**`%windir%\Microsoft.NET\Framework64\[version]\Config\machine.config`
    
    Fügen Sie die folgenden Zeilen zur Datei *Machine. config* hinzu, die `<configuration>` sich `</configuration>` irgendwo zwischen den Tags und befinden. Achten Sie darauf, `ProxyServer` dass `Port` Sie und die richtigen Werte für Ihre Organisation ersetzen. Beispiel: `proxy01.contoso.com:80` . 
    
    ```text
    <system.net>
       <defaultProxy enabled="true" useDefaultCredentials="true">
         <proxy proxyaddress="https://ProxyServer :Port " 
                usesystemdefault="False" 
                bypassonlocal="True" 
                autoDetect="False" />
       </defaultProxy>
    </system.net>
    ```

## <a name="step-1-prepare-search-results-for-export"></a>Schritt 1: Vorbereiten der Suchergebnisse für Export

Der erste Schritt besteht darin, die Suchergebnisse für den Export vorzubereiten. Wenn Sie Ergebnisse vorbereiten, werden Sie in einen von Microsoft bereitgestellten Azure-Speicherort in der Microsoft-Cloud hochgeladen. Inhalte von Postfächern und Websites werden mit einer maximalen Rate von 2 GB pro Stunde hochgeladen.
  
1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com).
    
2. Melden Sie sich mit ihrem geschäftlichen oder Schulkonto an.
    
3. Klicken Sie im linken Bereich des Security & Compliance Centers auf **Such** \> **Inhaltssuche**.
    
4. Wählen Sie auf der Seite **Inhaltssuche** eine Suche aus. 
    
5. Klicken Sie im Detailbereich unter **Ergebnisse auf einem Computer exportieren** auf **Export starten**. 
    
    > [!NOTE]
    > Wenn die Suchergebnisse älter als 7 Tage sind, werden Sie aufgefordert, die Suchergebnisse zu aktualisieren. Brechen Sie in diesem Fall den Export ab, klicken Sie im Detailbereich für die ausgewählte Suche auf **Suchergebnisse aktualisieren** und starten Sie dann den Export erneut, nachdem die Ergebnisse aktualisiert wurden.  
  
6. Wählen Sie auf der Seite **Suchergebnisse exportieren** unter **Ausgabeoptionen**eine der folgenden Optionen aus:
    
    - Alle Elemente, ausgenommen diejenigen, die nicht erkannt wurden, werden verschlüsselt oder aus anderen Gründen nicht indiziert.
    
    - Alle Elemente, einschließlich unerkannter Formate, werden verschlüsselt oder aus anderen Gründen nicht indiziert.
    
    - Nur Elemente, die über ein nicht erkanntes Format verfügen, verschlüsselt sind oder aus anderen Gründen nicht indiziert wurden
    
    Eine Beschreibung dazu, wie teilweise indizierte Elemente exportiert werden, finden Sie im Abschnitt [Weitere Informationen](#more-information) . Weitere Informationen zu teilweise indizierten Elementen finden Sie unter [teilweise indizierte Elemente in der Inhaltssuche](partially-indexed-items-in-content-search.md).
    
7. Wählen Sie unter **Exchange-Inhalt exportieren als**eine der folgenden Optionen aus:
    
    - **Eine PST-Datei für jedes Postfach:** Exportiert eine PST-Datei für jedes Benutzerpostfach, das Suchergebnisse enthält. Alle Ergebnisse aus dem Archivpostfach des Benutzers sind in derselben PST-Datei enthalten. Mit dieser Option wird die Postfachordnerstruktur aus dem Quellpostfach wiedergegeben. 
    
    - **Eine PST-Datei mit allen Nachrichten:** Exportiert eine einzelne PST-Datei (mit dem Namen " *Exchange. PST*"), die die Suchergebnisse aus allen Quellpostfächern enthält, die in der Suche enthalten sind. Mit dieser Option wird die Postfachordnerstruktur für jede Nachricht wiedergegeben. 
    
    - **Eine PST-Datei mit allen Nachrichten in einem einzelnen Ordner:** Exportiert Suchergebnisse in eine einzelne PST-Datei, in der sich alle Nachrichten in einem einzelnen Ordner auf oberster Ebene befinden. Mit dieser Option können Bearbeiter Elemente in chronologischer Reihenfolge überprüfen (Elemente werden nach dem gesendeten Datum sortiert), ohne dass Sie durch die ursprüngliche Postfachordnerstruktur für jedes Element navigieren müssen. 
    
    - **Einzelne Nachrichten:** Exportiert Suchergebnisse als einzelne e-Mail-Nachrichten unter Verwendung des msg-Formats. Wenn Sie diese Option auswählen, werden e-Mail-Suchergebnisse in einen Ordner im Dateisystem exportiert. Der Ordnerpfad für einzelne Nachrichten entspricht dem, der verwendet wird, wenn Sie die Ergebnisse in PST-Dateien exportiert haben. 
    
      > [!IMPORTANT]
      > Zum Entschlüsseln von RMS-verschlüsselten Nachrichten beim Export müssen Sie e-Mail-Suchergebnisse als einzelne Nachrichten exportieren. Verschlüsselte Nachrichten werden verschlüsselt bleiben, wenn Sie die Suchergebnisse als PST-Datei exportieren. 
  
8. Klicken Sie auf das Kontrollkästchen **Deduplizierung aktivieren** , um doppelte Nachrichten auszuschließen. Diese Option wird nur angezeigt, wenn die Inhaltsquellen der Suche Exchange-Postfächer oder öffentliche Ordner enthalten. 
    
    Wenn Sie diese Option auswählen, wird nur eine Kopie einer Nachricht exportiert, auch wenn in den durchsuchten Postfächern mehrere Kopien derselben Nachricht gefunden werden. Der Bericht Exportergebnisse (results. CSV) enthält eine Zeile für jede Kopie einer doppelten Nachricht, sodass Sie die Postfächer (oder öffentlichen Ordner) identifizieren können, die eine Kopie der doppelten Nachricht enthalten. Weitere Informationen zur Deduplizierung und zur Identifizierung von doppelten Elementen finden Sie unter [Deduplizierung in eDiscovery-Suchergebnissen](de-duplication-in-ediscovery-search-results.md).
    
9. Aktivieren Sie das Kontrollkästchen **Versionen für SharePoint-Dokumente einschließen** , um alle Versionen von SharePoint-Dokumenten zu exportieren. Diese Option wird nur angezeigt, wenn die Inhaltsquellen der Suche SharePoint-oder OneDrive für Unternehmen-Websites enthalten. 
    
10. Klicken Sie auf das Kontrollkästchen **Dateien in einem komprimierten Ordner exportieren (gezippt)** , um Suchergebnisse in komprimierte Ordner zu exportieren. Diese Option ist nur verfügbar, wenn Sie Exchange-Elemente als einzelne Nachrichten exportieren möchten und wenn die Suchergebnisse SharePoint-oder OneDrive-Dokumente enthalten. Diese Option wird in erster Linie verwendet, um die 260-Zeichenbegrenzung in Windows-Datei Pfad Namen zu umgehen, wenn Elemente exportiert werden. Siehe "Dateinamen von exportierten Elementen" im Abschnitt [Weitere Informationen](#more-information) . 
    
11. Klicken Sie auf **Export starten**.
    
    Die Suchergebnisse werden zum Herunterladen vorbereitet, was bedeutet, dass Sie in den Azure-Speicherort in der Microsoft-Cloud hochgeladen werden. Wenn die Suchergebnisse zum Download bereit sind, wird der Link **exportierte Ergebnisse herunterladen** unter **Ergebnisse exportieren auf einen Computer** im Detailbereich angezeigt. 
  
## <a name="step-2-download-the-search-results"></a>Schritt 2: Herunterladen der Suchergebnisse

Der nächste Schritt besteht darin, die Suchergebnisse vom Azure-Speicherort auf Ihren lokalen Computer herunterzuladen.
  
Wie bereits erläutert, können Sie die Downloadgeschwindigkeit durch Konfigurieren einer Windows-Registrierungseinstellung auf dem Computer, den Sie zum Exportieren der Suchergebnisse verwenden, verbessern. Weitere Informationen finden Sie unter [höhere Downloadgeschwindigkeit beim Exportieren von eDiscovery-Suchergebnissen aus Office 365](increase-download-speeds-when-exporting-ediscovery-results.md).
  
1. Klicken Sie im Detailbereich für die Suche, für die Sie den Exportvorgang gestartet haben, auf **exportierte Ergebnisse herunterladen**unter **Ergebnisse exportieren auf einen Computer**.
    
    Das Fenster **exportierte Ergebnisse herunterladen** wird angezeigt und enthält die folgenden Informationen zu den Suchergebnissen, die auf Ihren Computer heruntergeladen werden. 
    
    - Die Anzahl der Elemente, die heruntergeladen werden.
    
    - Die geschätzte Gesamtgröße der Elemente, die heruntergeladen werden sollen.
    
    - Ob indiziert oder nicht indiziert exportiert wird. Nicht indizierte Elemente sind Elemente, die ein erkanntes Format aufweisen, verschlüsselt sind oder aus anderen Gründen nicht indiziert wurden. Weitere Informationen finden Sie unter nicht [indizierte Elemente in der Inhaltssuche](partially-indexed-items-in-content-search.md).
    
    - Gibt an, ob Versionen von SharePoint-Dokumenten heruntergeladen werden.
    
    - Der Status des Vorbereitungsvorgangs für den Export. Sie können mit dem Herunterladen der Suchergebnisse auch dann beginnen, wenn die Vorbereitung der Daten nicht vollständig ist.
    
2. Klicken Sie unter **Schlüssel exportieren** auf **In Zwischenablage kopieren**. Sie verwenden diesen Schlüssel in Schritt 5, um die Suchergebnisse herunterzuladen.
    
    > [!NOTE]
    > Da jeder Benutzer das eDiscovery-Export Tool installieren und starten kann und dann mit diesem Schlüssel die Suchergebnisse herunterlädt, müssen Sie Vorkehrungen treffen, um diesen Schlüssel zu schützen, genauso wie Sie Kennwörter oder andere sicherheitsrelevante Informationen schützen würden. 
  
3. Klicken Sie auf **Ergebnisse herunterladen**.
    
4. Wenn Sie aufgefordert werden, das **eDiscovery-Export Tool**zu installieren, klicken Sie auf **Installieren**.
    
5. Fügen Sie im **eDiscovery-Exporttool** den Export-Schlüssel, den Sie in Schritt 2 kopiert haben, in das entsprechende Feld ein.
    
6. Klicken Sie auf **Durchsuchen**, und geben Sie das Verzeichnis an, in das die Dateien mit den Suchergebnissen heruntergeladen werden sollen. 
    
    > [!NOTE]
    > Aufgrund der hohen Menge an Datenträgeraktivität (Lese-und Schreibvorgänge) sollten Sie Suchergebnisse auf ein lokales Laufwerk herunterladen. Laden Sie Sie nicht auf ein zugeordnetes Netzlaufwerk oder einen anderen Netzwerkspeicherort herunter. 
  
1. Klicken Sie zum Herunterladen der Suchergebnisse auf Ihren Computer auf **Starten**. 
    
    Im **eDiscovery-Export Tool** werden Statusinformationen zum Exportprozess angezeigt, einschließlich einer Schätzung der Zahl (und der Größe) der restlichen Elemente, die heruntergeladen werden sollen. Wenn der Exportvorgang abgeschlossen ist, können Sie auf die Dateien an dem Speicherort zugreifen, an dem Sie heruntergeladen wurden. 
    

  
## <a name="more-information"></a>Weitere Informationen

Hier finden Sie weitere Informationen zum Exportieren von Suchergebnissen.
  
[Exportgrenzwerte](#export-limits)
  
[Exportieren von Berichten](#export-reports)
  
[Exportieren von teilweise indizierten Elementen](#exporting-partially-indexed-items)

[Exportieren einzelner Nachrichten oder PST-Dateien](#exporting-individual-messages-or-pst-files)
  
[Entschlüsseln von RMS-verschlüsselten Nachrichten](#decrypting-rms-encrypted-messages)

[Dateinamen von exportierten Elementen](#filenames-of-exported-items)  
  
[Sonstiges](#miscellaneous)
  
 ### <a name="export-limits"></a>Exportgrenzwerte
  
- Das Exportieren von Suchergebnissen aus dem Security & Compliance Center hat folgende Grenzen:
    
  - Sie können maximal 2 TB Daten aus einer einzelnen Inhaltssuche exportieren. Wenn die Suchergebnisse größer als 2 TB sind, sollten Sie die Verwendung von Datumsbereichen oder anderen Filtertypen verwenden, um die Gesamtgröße der Suchergebnisse zu verringern.
    
  - Ihre Organisation kann maximal 2 TB Daten an einem einzigen Tag exportieren.
    
  - In Ihrer Organisation können maximal zehn Exporte gleichzeitig durchführen.
    
  - Ein einzelner Benutzer kann maximal drei Exporte gleichzeitig ausführen.

  > [!NOTE]
  > Das Exportieren von Berichten aus einer Inhaltssuche gilt auch für die Anzahl der gleichzeitig ausgeführten Exporte und für die Anzahl der Exporte, die ein einzelner Benutzer ausführen kann.
    
- Wie bereits erwähnt, werden Suchergebnisse von Postfächern und Websites in einen von Microsoft bereitgestellten Azure-Speicherort hochgeladen (wie in [Schritt 1: Vorbereiten der Suchergebnisse für den Export](#step-1-prepare-search-results-for-export)beschrieben) mit einer maximalen Rate von 2 GB pro Stunde.
    
- Die maximale Größe einer PST-Datei, die exportiert werden kann, ist standardmäßig 10 GB. Das heißt, wenn die Suchergebnisse aus dem Postfach eines Benutzers größer als 10 GB sind, werden die Suchergebnisse für das Postfach in zwei (oder mehr) getrennten PST-Dateien exportiert. Wenn Sie alle Suchergebnisse in einer einzigen PST-Datei exportieren, wird die PST-Datei in zusätzliche PST-Dateien verschüttet, wenn die Gesamtgröße der Suchergebnisse größer als 10 GB ist. Wenn Sie diese Standardgröße ändern möchten, können Sie die Windows-Registrierung auf dem Computer bearbeiten, mit dem Sie die Suchergebnisse exportieren. Weitere Informationen finden Sie unter [Ändern der Größe von PST-Dateien beim Exportieren von eDiscovery-Suchergebnissen](change-the-size-of-pst-files-when-exporting-results.md).
    
    Außerdem werden die Suchergebnisse eines bestimmten Postfachs nicht auf mehrere PST-Dateien aufgeteilt, es sei denn, der Inhalt eines einzelnen Postfachs beträgt mehr als 10 GB. Wenn Sie die Suchergebnisse in einer PST-Datei exportieren, die alle Nachrichten in einem einzelnen Ordner enthält und die Suchergebnisse größer als 10 GB sind, sind die Elemente immer noch in chronologischer Reihenfolge angeordnet, sodass Sie basierend auf dem gesendeten Datum in zusätzliche PST-Dateien aufgeteilt werden.
     
 ### <a name="export-reports"></a>Exportieren von Berichten
  
- Wenn Sie Suchergebnisse exportieren, werden zusätzlich zu den Suchergebnissen die folgenden Berichte hinzugefügt.
    
  - **Export Zusammenfassung** Ein Excel-Dokument, das eine Zusammenfassung des Exports enthält. Dies umfasst Informationen wie die Anzahl der durchsuchten Inhaltsquellen, die geschätzte und heruntergeladene Größe der Suchergebnisse sowie die geschätzte und heruntergeladene Anzahl von exportierten Elementen. 
    
  - **Manifest** Eine Manifestdatei (im XML-Format), die Informationen zu jedem Element enthält, das in den Suchergebnissen enthalten ist. 
    
  - **Ergebnisse** Ein Excel-Dokument, das Informationen zu jedem Element enthält, das als Suchergebnis heruntergeladen wird. Bei e-Mails enthält das Ergebnisprotokoll Informationen zu den einzelnen Nachrichten, einschließlich: 
    
      - Der Speicherort der Nachricht im Quellpostfach (einschließlich der Angabe, ob die Nachricht sich im primären oder im Archivpostfach befindet).
        
      - Das Datum, an dem die Nachricht gesendet oder empfangen wurde.
        
      - Die Betreffzeile der Nachricht.
        
      - Absender und Empfänger der Nachricht.
        
      - Gibt an, ob es sich bei der Nachricht um eine doppelte Nachricht handelt, wenn Sie beim Exportieren der Suchergebnisse die Option "Deduplizierung" aktiviert haben. Doppelte Nachrichten enthalten einen Wert in der Spalte **Duplikat bis Element** , die die Nachricht als Duplikat identifiziert. Der Wert in der Spalte **Duplikat in Element** enthält die Element Identität der Nachricht, die exportiert wurde. Weitere Informationen finden Sie unter [Datendeduplizierung in eDiscovery-Suchergebnissen](de-duplication-in-ediscovery-search-results.md).
        
      Bei Dokumenten aus SharePoint-und OneDrive für Unternehmen-Websites enthält das Ergebnisprotokoll Informationen zu den einzelnen Dokumenten, einschließlich:
        
      - Die URL für das Dokument.
        
      - Die URL für die Websitesammlung, in der sich das Dokument befindet.
        
      - Das Datum, an dem das Dokument zuletzt geändert wurde.
        
      - Der Name des Dokuments (der sich in der Spalte Betreff im Ergebnisprotokoll befindet).
    
  - Nicht **indizierte Elemente** Ein Excel-Dokument, das Informationen zu teilweise indizierten Elementen enthält, die in den Suchergebnissen enthalten wären. Wenn Sie beim Generieren des Berichts "Suchergebnisse" nicht teilweise indizierte Elemente einschließen, wird dieser Bericht weiterhin heruntergeladen, wird jedoch leer sein. 
    
  - **Fehler und Warnungen** Enthält Fehler und Warnungen für Dateien, die beim Export aufgetreten sind. In der Spalte Fehler Details finden Sie Informationen zu den einzelnen Fehlern oder Warnungen. 
    
  - **Übersprungene Elemente** Wenn Sie Suchergebnisse aus SharePoint und OneDrive für Unternehmen Websites exportieren, enthält der Export normalerweise einen übersprungenen Element Bericht (SkippedItems. CSV). Die in diesem Bericht zitierten Elemente sind in der Regelelemente, die nicht heruntergeladen werden, beispielsweise ein Ordner oder eine Dokumentenmappe. Das Exportieren dieser Elementtypen ist nicht beabsichtigt. Bei anderen Elementen, die übersprungen wurden, zeigen das Feld Fehlertyp und Fehler Details im Bericht übersprungene Elemente den Grund an, warum das Element übersprungen und nicht mit den anderen Suchergebnissen heruntergeladen wurde. 
    
  - **Ablaufverfolgungsprotokoll** Enthält detaillierte Protokollierungsinformationen zum Exportprozess und kann bei der Ermittlung von Problemen beim Export hilfreich sein. 
    
    > [!NOTE]
    > Sie können diese Dokumente einfach exportieren, ohne die tatsächlichen Suchergebnisse exportieren zu müssen. Weitere Informationen finden Sie unter [Exportieren eines Inhalts Suchberichts](export-a-content-search-report.md). 
  
 ### <a name="exporting-partially-indexed-items"></a>Exportieren von teilweise indizierten Elementen
  
- Wenn Sie Postfachelemente aus einer Inhaltssuche exportieren, die alle Postfachelemente in den Suchergebnissen zurückgibt (da keine Stichwörter in der Suchabfrage enthalten sind), werden teilweise indizierte Elemente nicht in die PST-Datei kopiert, die die nicht indizierten Elemente enthält. Dies liegt daran, dass alle Elemente, einschließlich der teilweise indizierten Elemente, automatisch in die regulären Suchergebnisse eingeschlossen werden. Dies bedeutet, dass teilweise indizierte Elemente in einer PST-Datei (oder als einzelne Nachrichten) enthalten sein werden, die die anderen indizierten Elemente enthält.
    
    Wenn Sie sowohl die indizierten als auch teilweise indizierten Elemente exportieren oder nur die indizierten Elemente aus einer Inhaltssuche exportieren, die alle Elemente zurückgibt, wird die gleiche Anzahl von Elementen heruntergeladen. Dies geschieht auch dann, wenn die geschätzten Suchergebnisse für die Inhaltssuche (angezeigt in den Suchstatistiken im Security & Compliance Center) weiterhin eine separate Schätzung für die Anzahl der teilweise indizierten Elemente enthalten. Angenommen, die Schätzung für eine Suche, die alle Elemente (keine Stichwörter in der Suchabfrage) enthält, zeigt, dass 1.000 Elemente gefunden wurden und 200 teilweise indizierte Elemente ebenfalls gefunden wurden. In diesem Fall enthalten die 1.000-Elemente die teilweise indizierten Elemente, da die Suche alle Elemente zurückgibt. Mit anderen Worten: Es gibt 1.000 Gesamtelemente, die von der Suche zurückgegeben werden, und nicht 1.200 Elemente (wie Sie möglicherweise erwarten). Wenn Sie die Ergebnisse dieser Suche exportieren und indizierte und teilweise indizierte Elemente exportieren (oder nur teilweise indizierte Elemente exportieren), werden 1.000-Elemente heruntergeladen. Das liegt daran, dass teilweise indizierte Elemente in den regulären (indizierten) Ergebnissen enthalten sind, wenn Sie eine leere Suchabfrage verwenden, um alle Elemente zurückzugeben. Wenn Sie in diesem Beispiel nur teilweise indizierte Elemente exportieren, werden nur die 200 nicht indizierten Elemente heruntergeladen.
    
    Beachten Sie auch, dass im vorherigen Beispiel (wenn Sie indizierte und teilweise indizierte Elemente exportieren oder nur indizierte Elemente exportieren) der in den exportierten Suchergebnissen enthaltene **Export Zusammenfassungs** Bericht 1.000 Elemente mit den geschätzten Elementen und 1.000 heruntergeladenen Elementen aus den zuvor beschriebenen Gründen auflisten würde. 
    
- Wenn es sich bei der Suche, aus der Sie Ergebnisse exportieren, um die Suche nach bestimmten Inhaltsspeicherorten oder allen Inhaltsspeicherorten in Ihrer Organisation handelt, werden nur die Teilelemente aus Inhaltsspeicherorten exportiert, die Elemente enthalten, die mit den Suchkriterien übereinstimmen. Wenn also keine Suchergebnisse in einem Postfach oder einer Website gefunden werden, werden alle teilweise indizierten Elemente in diesem Postfach oder der Website nicht exportiert. Der Grund hierfür ist, dass das Exportieren von teilweise indizierten Elementen aus vielen Orten in der Organisation die Wahrscheinlichkeit von Exportfehlern erhöht und die Zeit für den Export und den Download der Suchergebnisse erhöht.
    
    Wenn Sie teilweise indizierte Elemente aus allen Inhaltsspeicherorten für eine Suche exportieren möchten, konfigurieren Sie die Suche so, dass alle Elemente zurückgegeben werden (indem Sie Stichwörter aus der Suchabfrage entfernen), und exportieren Sie dann nur teilweise indizierte Elemente, wenn Sie die Suchergebnisse exportieren.
    
    ![Verwenden der dritten Exportoption zum Exportieren von nur nicht indizierten Elementen](../media/5d7be338-a0e5-425f-8ba5-92769c24bf75.png)
  
- Beim Exportieren von Suchergebnissen aus SharePoint-oder OneDrive für Unternehmen-Websites hängt die Möglichkeit zum Exportieren von nicht indizierten Elementen auch von der ausgewählten Exportoption ab und davon, ob eine gesuchte Website ein indiziertes Element enthält, das den Suchkriterien entspricht. Wenn Sie beispielsweise bestimmte SharePoint-oder OneDrive für Unternehmen-Websites durchsuchen und keine Suchergebnisse gefunden werden, werden keine nicht indizierten Elemente dieser Websites exportiert, wenn Sie die zweite Exportoption zum Exportieren von indizierten und nicht indizierten Elementen auswählen. Wenn ein indiziertes Element von einer Website mit den Suchkriterien übereinstimmt, werden alle nicht indizierten Elemente dieser Website beim Exportieren von indizierten und nicht indizierten Elementen exportiert. In der folgenden Abbildung werden die Exportoptionen beschrieben, basierend darauf, ob eine Website ein indiziertes Element enthält, das den Suchkriterien entspricht.
    
    ![Wählen Sie die Option Export aus, je nachdem, ob eine Website ein indiziertes Element enthält, das den Suchkriterien entspricht.](../media/94f78786-c6bb-42fb-96b3-7ea3998bcd39.png)

    
    a. Nur indizierte Elemente, die den Suchkriterien entsprechen, werden exportiert. Es werden keine teilweise indizierten Elemente exportiert.
    
    b. Wenn keine indizierten Elemente von einer Website mit den Suchkriterien übereinstimmen, werden teilweise indizierte Elemente von dieser Website nicht exportiert. Wenn indizierte Elemente von einer Website in den Suchergebnissen zurückgegeben werden, werden die teilweise indizierten Elemente von dieser Website exportiert. Mit anderen Worten: nur die teilweise indizierten Elemente von Websites, die Elemente enthalten, die den Suchkriterien entsprechen, werden exportiert.
    
    c. Alle teilweise indizierten Elemente aus allen Websites in der Suche werden exportiert, unabhängig davon, ob eine Websiteelemente enthält, die den Suchkriterien entsprechen.
    
    Wenn Sie teilweise indizierte Elemente exportieren, werden teilweise indizierte Postfachelemente in eine separate PST-Datei exportiert, unabhängig von der Option, die Sie unter **Exchange-Export Inhalt als exportieren**auswählen.

- Wenn teilweise indizierte Elemente in den Suchergebnissen zurückgegeben werden (da andere Eigenschaften von teilweise indizierten Elementen mit den Suchkriterien übereinstimmen), werden diese teilweise indizierten mit den regulären Suchergebnissen exportiert. Wenn Sie also sowohl indizierte Elemente als auch teilweise indizierte Elemente exportieren (indem Sie **alle Elemente auswählen, einschließlich derer, die nicht erkanntes Format aufweisen, verschlüsselt sind oder aus anderen Gründen nicht indiziert** wurden), werden die teilweise indizierten Elemente, die mit den regulären Ergebnissen exportiert werden, im Bericht results. CSV aufgeführt. Sie werden nicht im Bericht nicht indizierte Elemente. CSV aufgeführt.
    
 ### <a name="exporting-individual-messages-or-pst-files"></a>Exportieren einzelner Nachrichten oder PST-Dateien
  
- Wenn der Dateipfadname einer Nachricht den maximalen Zeichen Grenzwert für Windows überschreitet, wird der Dateiname abgeschnitten. Der ursprüngliche Dateipfadname wird jedoch im Manifest und in ResultsLog aufgeführt.
    
- Wie bereits erläutert, werden e-Mail-Suchergebnisse in einen Ordner im Dateisystem exportiert. Der Ordnerpfad für einzelne Nachrichten würde den Ordnerpfad im Postfach des Benutzers replizieren. Bei einer Suche mit dem Namen "ContosoCase101" würde beispielsweise Nachrichten im Posteingang eines Benutzers im Ordnerpfad `~ContosoCase101\\<date of export\Exchange\user@contoso.com (Primary)\Top of Information Store\Inbox`gespeichert. 
    
- Wenn Sie e-Mail-Nachrichten in einer PST-Datei exportieren, die alle Nachrichten in einem einzelnen Ordner enthält, werden der Ordner " **Gelöschte Elemente** " und der Ordner " **Suchordner** " auf der obersten Ebene des PST-Ordners aufgeführt. Diese Ordner sind leer. 
  
 ### <a name="decrypting-rms-encrypted-messages"></a>Entschlüsseln von RMS-verschlüsselten Nachrichten
  
- Wie bereits erläutert, müssen Sie die Suchergebnisse als einzelne Nachrichten exportieren, um RMS-verschlüsselte Nachrichten beim Exportieren zu entschlüsseln. Wenn Sie Suchergebnisse in eine PST-Datei exportieren, bleiben RMS-verschlüsselte Nachrichten verschlüsselt.
    
- Das RMS-Entschlüsselungs Feature in der Inhaltssuche entschlüsseln Nachrichten, die beim Exportieren von Suchergebnissen mit Office 365 Nachrichtenverschlüsselung (OM) verschlüsselt wurden, nicht. Wenn jedoch eine mit OM verschlüsselte Nachricht von einem Benutzer in Ihrer Organisation gesendet wird, wird die Kopie der Nachricht im gesendeten Ordner des Benutzers nicht verschlüsselt und kann nach dem Export angezeigt werden. Wenn jedoch mit OM verschlüsselte Nachrichten von Benutzern in Ihrer Organisation empfangen werden, werden Sie nach dem Export nicht entschlüsselt. Weitere Informationen zu OM finden Sie unter [Office 365 Nachrichtenverschlüsselung](https://go.microsoft.com/fwlink/p/?linkid=844966).
    
- Entschlüsselte Nachrichten werden im **ResultsLog** -Bericht identifiziert. Dieser Bericht enthält eine Spalte mit dem Namen **Decode Status**, und der Wert **decodiert** in dieser Spalte identifiziert die Nachrichten, die entschlüsselt wurden. 
    
- Derzeit umfasst diese Entschlüsselungsfunktion keine verschlüsselten Inhalte aus SharePoint und OneDrive für Unternehmen Websites. Nur RMS-verschlüsselte e-Mail-Nachrichten werden entschlüsselt, wenn Sie Sie exportieren.
    
- Wenn eine RMS-verschlüsselte e-Mail-Nachricht eine Anlage (beispielsweise ein Dokument oder eine andere e-Mail-Nachricht) enthält, die ebenfalls verschlüsselt ist, wird nur die e-Mail-Nachricht der obersten Ebene entschlüsselt.
    
- Sie können keine Vorschau einer RMS-verschlüsselten e-Mail-Nachricht anzeigen. Um eine verschlüsselte Nachricht anzuzeigen, müssen Sie Sie exportieren.
    
- Wenn Sie verhindern müssen, dass eine Person RMS-verschlüsselte Nachrichten entschlüsselt, müssen Sie eine benutzerdefinierte Rollengruppe erstellen (durch Kopieren der integrierten eDiscovery-Manager-Rollengruppe) und dann die Verwaltungsrolle "RMS Decrypt" aus der benutzerdefinierten Rollengruppe entfernen. Fügen Sie dann die Person hinzu, die Nachrichten nicht als Mitglied der benutzerdefinierten Rollengruppe entschlüsseln soll.
  
 ### <a name="filenames-of-exported-items"></a>Dateinamen von exportierten Elementen
  
- Für den vollständigen Pfadnamen für e-Mail-Nachrichten und Website Dokumente, die auf Ihren lokalen Computer exportiert werden, gibt es eine Grenze von 260 Zeichen (durch das Betriebssystem auferlegt). Der vollständige Pfadname für exportierte Elemente enthält den ursprünglichen Speicherort des Elements und den Speicherort des Ordners auf dem lokalen Computer, in den die Suchergebnisse heruntergeladen werden. Wenn Sie beispielsweise angeben, dass die Suchergebnisse `C:\Users\Admin\Desktop\SearchResults` im eDiscovery-Export Tool heruntergeladen werden `C:\Users\Admin\Desktop\SearchResults\ContentSearch1\03.15.2017-1242PM\Exchange\sarad@contoso.com (Primary)\Top of Information Store\Inbox\Insider trading investigation.msg`sollen, lautet der vollständige Pfadname für ein heruntergeladenes e-Mail-Element.
    
    Wenn die 260-Zeichen Grenze überschritten wird, wird der vollständige Pfadname für ein Element abgeschnitten.
    
  - Wenn der vollständige Pfadname länger als 260 Zeichen ist, wird der Dateiname verkürzt, um unter den Grenzwert zu gelangen. Beachten Sie, dass der gekürzte Dateiname (mit Ausnahme der Dateierweiterung) nicht weniger als 8 Zeichen beträgt.
    
  - Wenn der vollständige Pfadname nach der Kürzung des Datei namens noch zu lang ist, wird das Element von seinem aktuellen Speicherort in den übergeordneten Ordner verschoben. Wenn der Pfadname immer noch zu lang ist, wird der Prozess wiederholt: kürzen Sie den Dateinamen, und wenn nötig, wieder in den übergeordneten Ordner zu gelangen. Dieser Vorgang wird wiederholt, bis der vollständige Pfadname unter dem Grenzwert von 260 Zeichen liegt.
    
  - Wenn bereits ein gekürzter vollständiger Pfadname vorhanden ist, wird am Ende des Datei namens eine Versionsnummer hinzugefügt. Beispiel: `statusmessage(2).msg`.
    
    Um dieses Problem zu vermeiden, sollten Sie die Suchergebnisse an einen Speicherort mit einem kurzen Pfadnamen herunterladen. beispielsweise `C:\Results` würde das Herunterladen von Suchergebnissen in einen Ordner mit dem Namen weniger Zeichen zu den Pfadnamen von exportierten Elementen hinzufügen, `C:\Users\Admin\Desktop\Results`als diese in einen Ordner mit dem Namen herunterzuladen.
    
- Wenn Sie Website Dokumente exportieren, ist es auch möglich, dass der ursprüngliche Dateiname eines Dokuments geändert wird. Dies geschieht speziell für Dokumente, die aus einer SharePoint-oder OneDrive für Unternehmen-Website gelöscht wurden, die in den Haltestatus versetzt wurde. Nachdem ein Dokument auf einer Warteschleife gelöscht wurde, wird das gelöschte Dokument automatisch in die Aufbewahrungs Archiv-Bibliothek für die Website verschoben (das erstellt wurde, als die Website gespeichert wurde). Wenn das gelöschte Dokument in die Aufbewahrungs Archiv-Bibliothek verschoben wird, wird eine zufällig generierte und eindeutige ID an den ursprünglichen Dateinamen des Dokuments angehängt. Wenn beispielsweise der Dateiname eines Dokuments lautet `FY2017Budget.xlsx` und dieses Dokument später gelöscht und in die Aufbewahrungs Archiv-Bibliothek verschoben wird, wird der Dateiname des Dokuments, das in die Aufbewahrungs Archiv-Bibliothek verschoben wird, in `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx`etwa so geändert. Wenn ein Dokument in der Aufbewahrungs Archiv-Bibliothek mit der Abfrage einer Inhaltssuche übereinstimmt und Sie die Ergebnisse dieser Suche exportieren, hat die exportierte Datei den geänderten Dateinamen; in diesem Beispiel wäre der Dateiname des exportierten Dokuments `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx`.
    
    Wenn ein Dokument auf einer Website, das in der Warteschleife gespeichert ist, geändert wird (und die Versionsverwaltung für die Dokumentbibliothek in der Website aktiviert wurde), wird automatisch eine Kopie der Datei in der Aufbewahrungsspeicher Bibliothek erstellt. In diesem Fall wird auch eine zufällig generierte und eindeutige ID an den Dateinamen des Dokuments angehängt, das in die Aufbewahrungs Bibliothek kopiert wird.
    
    Der Grund, warum filenames von Dokumenten, die in die Aufbewahrungs Archiv Bibliothek verschoben oder kopiert werden, darin besteht, widersprüchliche Dateinamen zu verhindern. Weitere Informationen zum Platzieren eines Haltestatus für Websites und zur Aufbewahrungsspeicher Bibliothek finden Sie unter [Overview of in-Place Hold in SharePoint Server 2016](https://support.office.com/article/5e400d68-cd51-444a-8fe6-e4df1d20aa95).
    
 ### <a name="miscellaneous"></a>Sonstiges
  
- Alle Suchergebnisse und die Export Berichte sind in einem Ordner mit dem gleichen Namen wie die Inhaltssuche enthalten. Die E-Mail-Nachrichten, die exportiert wurden, befinden sich in einem Ordner mit dem Namen **Exchange**. Dokumente befinden sich in einem Ordner mit dem Namen **SharePoint**. 
    
- Die Dateisystemmetadaten für Dokumente in SharePoint und OneDrive für Unternehmen Websites werden beibehalten, wenn Dokumente auf Ihren lokalen Computer exportiert werden. Das bedeutet, dass Dokumenteigenschaften, wie erstellt und Datum der letzten Änderung, beim Exportieren von Dokumenten nicht geändert werden.

- Wenn Ihre Suchergebnisse ein Listenelement aus SharePoint enthalten, das mit der Suchabfrage übereinstimmt, werden alle Zeilen in der Liste zusätzlich zu dem Element, das mit der Suchabfrage übereinstimmt, exportiert. Dies umfasst alle Anlagen in der Liste. Der Grund liegt darin, einen Kontext für Listenelemente bereitzustellen, die in den Suchergebnissen zurückgegeben werden. Beachten Sie außerdem, dass die Anzahl der exportierten Elemente durch die zusätzlichen Listenelemente und Anlagen möglicherweise von der ursprünglichen Schätzung der Suchergebnisse abweicht.
