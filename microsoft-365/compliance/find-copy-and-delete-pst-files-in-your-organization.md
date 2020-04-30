---
title: Verwenden des PST-Sammlungs Tools zum Suchen, kopieren und Löschen von PST-Dateien in Ihrer Organisation
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: 7a150c84-049c-4a9c-8c91-22355b35f2a7
description: Verwenden Sie das Microsoft PST-Sammlungs Tool, um das Netzwerk Ihrer Organisation zu durchsuchen, um eine Bestandsaufnahme der PST-Dateien zu erhalten, die in Ihrer Organisation verstreut sind. Nachdem Sie PST-Dateien gefunden haben, können Sie das PST-Sammlungs Tool verwenden, um Sie an einem zentralen Speicherort zu kopieren, damit Sie Sie in Office 365 importieren können.
ms.openlocfilehash: 3d28db482bc3c17570b4cf4a952939c3c221d94b
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "43942198"
---
# <a name="use-the-pst-collection-tool-to-find-copy-and-delete-pst-files-in-your-organization"></a>Verwenden des PST-Sammlungs Tools zum Suchen, kopieren und Löschen von PST-Dateien in Ihrer Organisation

> [!IMPORTANT]
> Das in diesem Artikel beschriebene PST-Sammlungs Tool wird unter keinem Microsoft Standard Support Programm oder-Dienst unterstützt. Das Tool wird bereitgestellt, wie es ohne Gewährleistung jeglicher Art ist. Microsoft schließt weiterhin konkludent, einschließlich, aber nicht beschränkt auf implizite Garantien der Handelsüblichkeit oder Eignung für einen bestimmten Zweck aus. Das gesamte Risiko, das aus der Verwendung oder Leistung des Tools und der Dokumentation erwachsen, bleibt bei Ihnen. In keinem Fall wird Microsoft, seine Autoren oder andere Personen, die an der Erstellung beteiligt sind, die Produktion oder die Bereitstellung des Tools haftet für jegliche Schäden (einschließlich, ohne Einschränkung, Schäden wegen Verlusts geschäftlicher Gewinne, geschäftlicher Unterbrechung, Verlust von Geschäftsdaten oder sonstiger Vermögensschäden), die aus der Verwendung oder Unfähigkeit zur Verwendung des Tools oder der Dokumentation entstehen, selbst wenn Microsoft über die Möglichkeit solcher Schäden informiert wurde.

Sie können das Microsoft PST-Sammlungs Tool verwenden, um das Netzwerk Ihrer Organisation nach PST-Dateien zu durchsuchen. Das Tool hilft Ihnen, einen Bestand an PST-Dateien zu erhalten, die in Ihrer Organisation verstreut sind. Nachdem Sie PST-Dateien gefunden haben, können Sie Sie mit dem PST-Sammlungs Tool an einem zentralen Speicherort kopieren. Wenn Sie PST an einem zentralen Ort haben, können Sie diese in Exchange Online Postfächer (oder ein einzelnes Exchange Online Postfach) importieren, wo Sie dann die umfangreichen Compliance-Features in Office 365 anwenden können. Dazu gehört das Importieren von PST in die Archivpostfächer von Benutzern, das Suchen nach bestimmten Nachrichten in den PST-Dateien, die Sie mithilfe von eDiscovery-Suchwerkzeugen importiert haben, das Aufbewahren von Nachrichten mithilfe von eDiscovery-Haltebereichen und Aufbewahrungsrichtlinien sowie die Verwaltung des Lebenszyklus dieser Nachrichten mithilfe der Features für die Messaging-Datensatzverwaltung in Exchange Online. Wenn Sie sicher sind, dass die gesammelten PST-Dateien erfolgreich in Office 365 importiert wurden, können Sie Sie mithilfe des Tools von Ihrem ursprünglichen Speicherort im Netzwerk löschen. 
  
Eine andere Möglichkeit, die Sie mit dem PST-Sammlungs Tool tun können, ist, dass Benutzer keine neuen PST-Dateien erstellen und die vorhandenen PST-Dateien ändern, die Sie in Ihrem Netzwerk finden. Diese "blockieren"-Funktionen ermöglichen es Ihnen, eine bekannte Gruppe von PST-Dateien in Microsoft 365 zu finden, zu sammeln und zu importieren und die zukünftige Verbreitung von PST-Dateien in Ihrer Organisation zu verhindern. 
  
## <a name="how-the-pst-collection-tool-works"></a>Funktionsweise des PST-Sammlungs Tools

Hier finden Sie eine kurze Übersicht über den Prozess der Verwendung des PST-Sammlungs Tools zum Suchen, Steuern, sammeln und Löschen von PST-Dateien in Ihrer Organisation.
  
![Übersicht über den Prozess des PST-Sammlungs Tools](../media/67a29f27-f83c-4f0a-9df4-7ed92d3086fe.png)
  
1. **[Schritt 1: Suchen von PST-Dateien in Ihrem Netzwerk](#step-1-find-pst-files-on-your-network)** – Wenn Sie das Tool zum Auffinden von PST-Dateien ausführen, geben Sie einen Speicherort an, beispielsweise eine Organisationseinheit, die Active Directory-Objekte für Client-und Server Computer enthält. Sie können auch bestimmte Computer oder Netzwerkdateifreigaben durchsuchen. Wenn Sie das Tool ausführen, wird ein "Lightweight"-Sammlungs-Agent auf den Zielcomputern installiert. Dieser Agent durchsucht den Zielcomputer nach PST-Dateien und sendet dann Informationen zu jeder gefundenen PST-Datei zurück an das PST-Sammlungs Tool. Das Tool erstellt Protokolldateien, die Informationen zu den PST-Dateien enthalten, die an den angegebenen Speicherorten gefunden wurden. Diese Dateien werden verwendet, wenn Sie das Tool in späteren Schritten ausführen. 
    
2. **[(Optional) Schritt 2: Steuern des Zugriffs auf PST-Dateien](#optional-step-2-control-access-to-pst-files)** -das Tool erstellt ein Gruppenrichtlinienobjekt (Group Policy Object, GPO) mit Einstellungen, die verhindern, dass Benutzer PST-Dateien erstellen oder ändern. Dieses GPO wird auf alle Benutzer in Ihrer Domäne angewendet. Dieser optionale Schritt hilft Ihnen, die PST-Dateien, die in Schritt 1 gefunden wurden, zu sperren, damit Sie Sie erfassen, importieren und löschen können, ohne dass neue PST-Dateien erstellt oder die vorhandenen PST-Dateien geändert wurden. 
    
3. **[Schritt 3: Kopieren der PST-Dateien an einen Sammel Speicherort](#step-3-copy-the-pst-files-to-a-collection-location)** – damit können Sie die PST-Dateien an einem Speicherort sammeln, sodass Sie Sie mithilfe des Office 365-Import Diensts in Schritt 4 in Exchange Online Postfächer importieren können. Wenn Sie das Tool im Modus "Collect" ausführen, kopiert jeder Sammlungs-Agent die PST-Dateien vom Zielcomputer, auf dem der Agent installiert ist, an den Speicherort der Sammlung. 
    
4. **[Schritt 4: Importieren der PST-Dateien in Office 365](#step-4-import-the-pst-files-to-office-365)** – nachdem Sie die PST-Dateien an einen Speicherort kopiert haben, können Sie Sie in Exchange Online Postfächer importieren. 
    
5. **[Schritt 5: Löschen der in Ihrem Netzwerk gefundenen PST](#step-5-delete-the-pst-files-found-on-your-network)** -Dateien – nachdem die gefundenen und gesammelten PST-Dateien in Office 365 in Exchange Online Postfächer importiert wurden, können Sie das PST-Sammlungs Tool verwenden, um die PST-Dateien von den ursprünglichen Speicherorten zu löschen, an denen Sie in Schritt 1 gefunden wurden. 

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Führen Sie die folgenden Schritte aus, um das PST-Sammlungs Tool auf Ihren lokalen Computer herunterzuladen. 
    
    1. [Laden Sie das PST-Sammlungs Tool herunter](https://aka.ms/pstcollectiontool).
    
    2. **Klicken Sie** \> im Popupfenster auf Save **As** speichern unter, um die Datei PSTCollectionTool. zip in einem Ordner auf Ihrem lokalen Computer zu speichern. 
    
    3. Extrahieren Sie die Datei PSTCollectionTool. zip in einen Ordner auf Ihrem lokalen Computer; der Standardordnername lautet PSTCollectionTool.
    
- Zum Ausführen des PST-Sammlungs Tools in einem beliebigen Modus (suchen, blockieren, kopieren oder löschen) müssen Sie Mitglied der Gruppe Domänenadministratoren in Ihrer Active Directory Domäne sein. 

## <a name="step-1-find-pst-files-on-your-network"></a>Schritt 1: Suchen von PST-Dateien in Ihrem Netzwerk

Der erste Schritt besteht darin, das PST-Sammlungs Tool auszuführen, um PST-Dateien in Ihrer Organisation zu finden. Sie können das Tool verwenden, um die folgenden Arten von Speicherorten zu durchsuchen. 
  
- Organisationseinheiten (Organizational Units, OUs) in einer lokalen Active Directory Domäne. Das Tool durchsucht alle Computer, die in der angegebenen Organisationseinheit enthalten sind. 
    
- Client-und Server Computer. Das Tool sucht die angegebenen Computer. 
    
- Netzwerkdateifreigaben. Das Tool durchsucht die angegebenen Netzwerkdateifreigaben. 
    
Beispiele für die Syntax, `Locations` die für jeden dieser Standorttypen verwendet werden soll, finden Sie in der Beschreibung des Parameters in der Tabelle im folgenden Verfahren. 
  
> [!IMPORTANT]
> Sie müssen das PST-Sammlungs Tool im Suchmodus ausführen, bevor Sie andere Aktionen wie blockieren, sammeln oder Löschen von PST-Dateien ausführen können. 
  
1. Öffnen Sie auf dem lokalen Computer eine Eingabeaufforderung (als Administrator ausführen).
    
2. Wechseln Sie zum Ordner PSTCollectionTool (oder dem Ordner, in den Sie die PSTCollectionTool. zip-Datei extrahiert haben).
    
3. Wechseln Sie zum Verzeichnis DataCollectorMaster.
    
4. Führen Sie den folgenden Befehl aus, um PST-Dateien an einem angegebenen Speicherort zu finden.
    
    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Find -JobName <Name> -Locations <Locations to search for PSTs> -LogLocation <Location to store log files> -ConfigurationLocation <Location to store configuration files>
    ```

    In der folgenden Tabelle werden die Parameter und die erforderlichen Werte beschrieben, wenn Sie den Befehl DataCollectorMaster. exe ausführen, um PST-Dateien zu finden. 
    
    |Parameter * * * *|****Beschreibung****|Beispiele * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |Gibt den Typ der zu suchenden Daten an. Derzeit können Sie das PST-Sammlungs Tool verwenden, um nach PST-Dateien zu suchen.  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |Gibt den Typ der Operation an, die vom Tool ausgeführt wird. Verwenden Sie den `Find` Wert, um PST-Dateien an den angegebenen Speicherorten zu finden. Beachten Sie, dass das Tool Informationen zu PST-Dateien finden und abrufen kann, die in Outlook-und PST-Dateien geöffnet sind, die mit Outlook-Profilen verbunden sind.  <br/> | `-Mode Find` <br/> |
    | `JobName` <br/> |Gibt den Namen des PST-Sammlungs Auftrags an. Sie werden denselben Auftragsnamen verwenden, wenn Sie das PST-Sammlungs Tool ausführen, um die PST-Dateien zu blockieren, zu erfassen und zu löschen, die beim Ausführen des Tools zum Auffinden von PST-Dateien gefunden werden. Der Auftragsname wird auch den Namen der Protokoll-und Konfigurationsdatei hinzugefügt.  <br/> | `-JobName PstSearch1` <br/> |
    | `Locations` <br/> | Gibt einen oder mehrere Speicherorte für die Suche nach PST-Dateien an. Wenn Sie mehrere Standorte angeben, verwenden Sie ein Semikolon (;) zum Trennen einzelner Standorte. Stellen Sie sicher, dass Sie die einzelnen Werte dieses Parameters mit doppelten Anführungszeichen ("") umgeben.  <br/><br/>   Hier ist das erforderliche Identitätswert Format für die Typen von Speicherorten, die Sie durchsuchen können.  <br/><br/>        **OUs** – verwenden Sie den Distinguished Name (DN), um OUs zu identifizieren. Zum Beispiel:`"OU=NorthAmerica,OU=NWRegion,OU=ITServices,DC=contoso,DC=com"` <br/> > [!IMPORTANT]> Sie können den integrierten Computer Container nicht angeben (beispielsweise CN = Computers, DC = contoso, DC = com), da es sich nicht um eine Organisationseinheit handelt.<br/> <br/> **Computer** – verwenden Sie den DN oder den vollqualifizierten Domänennamen (FQDN), um Client-und Server Computer in Ihrem Netzwerk zu identifizieren. Zum Beispiel:  <br/>  DN`"CN=FILESERVER01,CN=Computers,DC=contoso,DC=com"` <br/>  Oder:  <br/>  FQDN`"FILESERVER01.contoso.com"` <br/><br/>  **Netzwerkdateifreigaben** : Verwenden Sie einen UNC-Namen, um Netzwerkdateifreigaben zu identifizieren. Zum Beispiel`"\\FILESERVER02\Users"` <br/> | `-Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com"` <br/> |
    | `LogLocation` <br/> |Gibt den Ordner an, in den die Protokolldateien kopiert werden. Wenn der Ordner nicht vorhanden ist, wird er erstellt, wenn Sie das Tool ausführen.  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ConfigurationLocation` <br/> |Gibt den Ordner an, in den die XML-Konfigurationsdatei kopiert wird. Diese Datei enthält Informationen zu jeder PST-Datei, die beim Ausführen des Tools gefunden wird. Diese Datei wird verwendet, wenn Sie das Tool in Schritt 3 ausführen, um die gefundenen PST-Dateien zu kopieren.  <br/> | `-ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"` <br/> |
    | `ExcludedLocations` <br/> |Dieser optionale Parameter gibt Speicherorte an, die während eines Suchvorgangs übersprungen werden sollen. Sie können bestimmte OUs, Computer und Netzwerkdateifreigaben ausschließen. Sie können beispielsweise Computer ausschließen, die als SQL Server konfiguriert sind (oder andere Arten von Anwendungsservern), auf die Benutzer keinen Zugriff haben. Wenn Sie mehrere auszuschließende Orte angeben, verwenden Sie ein Semikolon (;) zum Trennen einzelner Standorte. Stellen Sie sicher, dass Sie die einzelnen Werte dieses Parameters mit doppelten Anführungszeichen ("") umgeben.  <br/> | `-ExcludedLocations "SQLSERVER01.contoso.com"` <br/> |
    | `ForceRestart` <br/> |Mit diesem optionalen Switch können Sie das Tool im Find-Modus für einen vorhandenen PST-Sammlungsauftrag ausführen. Wenn Sie den `ForceRestart` Switch verwenden, werden die Ergebnisse aus dem vorherigen Suchvorgang für den Auftrag verworfen, und das Tool überprüft die angegebenen Speicherorte erneut und erstellt neue Protokoll-und Konfigurationsdateien.  <br/> | `-ForceRestart` <br/> |
   
    Im folgenden finden Sie ein Beispiel für die Syntax für den DataCollectorMaster. exe-Befehl unter Verwendung der tatsächlichen Werte für jeden Parameter:
    
    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Find -JobName PstSearch1 -Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com" -LogLocation "c:\users\admin\desktop\PSTCollection" -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"
    ```

    Nachdem Sie den Befehl ausgeführt haben, werden detaillierte Statusmeldungen angezeigt, die den Fortschritt der Suche nach PST-Dateien an den angegebenen Speicherorten anzeigen. Nach einer Weile zeigt eine abschließende Statusmeldung die Gesamtzahl der gefundenen PST-Dateien an, ob der Auftrag abgeschlossen wurde und ob Fehler aufgetreten sind. Die gleichen Statusmeldungen werden in die Log-Datei kopiert.
    
### <a name="results-of-running-datacollectormasterexe-in-the-find-mode"></a>Ergebnisse der Ausführung von DataCollectorMaster. exe im Find-Modus

Nachdem Sie das PST-Sammlungs Tool im Suchmodus erfolgreich ausgeführt haben, werden die folgenden Dateien erstellt und in den durch die `LogLocation` und `ConfigurationLocation` -Parameter angegebenen Ordnern gespeichert. 
  
- **\>_Find_Jobname Find\<DateTimeStamp\>. log-die Protokolldatei enthält die Statusmeldungen, \<** die angezeigt wurden. Diese Datei wird in dem durch den `LogLocation` -Parameter angegebenen Ordner erstellt. 
    
- **\>_Find_Jobname Find\<DateTimeStamp\>. CSV – die CSV-Datei enthält eine Zeile für jede gefundene \<** PST-Datei. Die Informationen zu den einzelnen PST-Dateien umfassen den Computer, auf dem die PST-Datei gefunden wurde, den vollständigen Dateipfad der PST-Datei, den Besitzer der PST-Datei und die Größe (in Kilobyte, KBS) der PST-Datei. Diese Datei wird in dem durch den `LogLocation` -Parameter angegebenen Ordner erstellt. 
    
    > [!TIP]
    > Verwenden Sie das AutoSum-Tool in Excel, um die Gesamtgröße (in KB) aller PST-Dateien zu berechnen, die in der CSV-Datei aufgeführt sind. Anschließend können Sie einen Konvertierungs Rechner verwenden, um die Gesamtgröße in Megabyte (MB) oder Gigabyte (GB) zu konvertieren. 
  
- **\>_Find_Jobname Find\<DateTimeStamp\>. XML-die XML-Datei enthält Informationen zu den Parameterwerten, die verwendet werden, wenn Sie das Tool im Suchmodus \<** ausgeführt haben. Diese Datei enthält auch Informationen zu jeder PST-Datei, die gefunden wurde. Die Daten in dieser Datei werden verwendet, wenn Sie das Tool erneut ausführen, um denselben Auftrag zum blockieren, erfassen oder Löschen der gefundenen PST-Dateien auszuführen. Diese Datei wird in dem durch den `ConfigurationLocation` -Parameter angegebenen Ordner erstellt. 
    
    > [!IMPORTANT]
    > Diese Datei nicht umbenennen, ändern oder bewegen. Sie wird vom PST-Sammlungs Tool verwendet, wenn Sie das Tool im Block-, Kopier-oder Löschmodus für denselben Auftrag erneut ausführen. 

## <a name="optional-step-2-control-access-to-pst-files"></a>Optional Schritt 2: Steuern des Zugriffs auf PST-Dateien

In diesem optionalen Schritt können Sie die PST-Dateien, die in Schritt 1 gefunden wurden, "Sperren", sodass Sie eine bekannte Gruppe von PST-Dateien in Office 365 erfassen und importieren können. Wenn Sie das PST-Sammlungs Tool im Block Modus ausführen, geschieht Folgendes: 
  
- Das Tool erstellt ein Gruppenrichtlinienobjekt (GPO) namens *PST Usage Controls* . Dieses GPO ist mit Ihrer Domäne verknüpft und gilt für alle authentifizierten Benutzer in Ihrer Organisation. 
    
- Das GPO für PST-Verwendungs Steuerelemente erstellt Registrierungseinstellungen auf Computern in Ihrer Organisation. Je nach verwendetem Parameter können Sie eine Registrierungseinstellung erstellen, um zu verhindern, dass Benutzer neue PST-Dateien erstellen, und eine Registrierungseinstellung, die verhindert, dass Benutzer vorhandene PST-Dateien ändern.
    
> [!NOTE]
> Wenn die Steuerung des Zugriffs auf PST-Dateien zu störend für Ihre Organisation ist, können Sie diesen Schritt überspringen und Schritt 3 ausführen, um PST-Dateien an einen zentralen Speicherort zu kopieren. Anschließend können Sie Schritt 1 für denselben Auftrag (mithilfe des `ForceRestart` Parameters) wiederholen, um zusätzliche PST-Dateien zu finden, die nach dem Kopieren von PST-Dateien an den Speicherort der Sammlung erstellt wurden. Wenn neue PST-Dateien gefunden werden, können Sie Sie an den Speicherort der Sammlung kopieren. Wenn Sie den- `ForceRestart` Parameter verwenden, wenn Sie das Tool im Suchmodus erneut ausführen, werden die Ergebnisse aus dem vorherigen Suchvorgang für einen Auftrag verworfen, und das Tool überprüft die angegebenen Speicherorte erneut. 

So blockieren Sie den Zugriff auf PST-Dateien:

1. Öffnen Sie auf dem lokalen Computer eine Eingabeaufforderung (als Administrator ausführen).
    
2. Wechseln Sie zu dem Verzeichnis, in das Sie das PST-Sammlungs Tool heruntergeladen haben.
    
3. Führen Sie den folgenden Befehl aus, um den Zugriff auf die in Schritt 1 gefundenen PST-Dateien zu blockieren.

    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Block -JobName <Name of job from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -BlockChangesToFiles -BlockNewFiles
    ```

    In der folgenden Tabelle werden die Parameter und die erforderlichen Werte beschrieben, wenn Sie den Befehl DataCollectorMaster. exe ausführen, um das Erstellen und Ändern von PST-Dateien zu blockieren. 
    
    |Parameter * * * *|****Beschreibung****|Beispiele * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |Gibt den Typ der zu suchenden Daten an. Derzeit können Sie das PST-Sammlungs Tool verwenden, um nach PST-Dateien zu suchen.  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |Gibt den Typ der Operation an, die vom Tool ausgeführt wird. Verwenden Sie den `Block` -Wert, um zu verhindern, dass Benutzer neue PST-Dateien erstellen und Änderungen an vorhandenen PST-Dateien vornehmen.  <br/> | `-Mode Block` <br/> |
    | `JobName` <br/> |Gibt den Namen eines vorhandenen PST-Sammlungs Auftrags an. Sie müssen den gleichen Auftragsnamen verwenden, den Sie beim Ausführen des Tools im Find-Modus in Schritt 1 verwendet haben. Dieser Auftragsname wird auch dem Namen der Protokolldatei hinzugefügt, die erstellt wird, wenn Sie das Tool im Block Modus ausführen.  <br/> | `-JobName PstSearch1` <br/> |
    | `ConfigurationLocation` <br/> |Gibt an, dass der Ordner die XML-Konfigurationsdatei enthält, die erstellt wurde, als Sie das Tool im Find-Modus ausgeführt haben. Verwenden Sie den gleichen Wert, den Sie in Schritt 1 für diesen Parameter verwendet haben.  <br/> | `-ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration"` <br/> |
    | `LogLocation` <br/> |Gibt den Ordner an, in den die Protokolldatei für den Block Vorgang kopiert wird. Dieser Parameter ist optional. Wenn Sie es nicht einschließen, wird die Protokolldatei in den Ordner kopiert, in den Sie das PST-Sammlungs Tool heruntergeladen haben. Verwenden Sie den gleichen Protokollspeicherort, den Sie beim Ausführen des Tools im Suchmodus in Schritt 1 verwendet haben, sodass alle Protokolldateien im gleichen Ordner gespeichert werden.  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `BlockChangesToFiles` <br/> |Verwenden Sie diese Option, um zu verhindern, dass Benutzer eine PST-Datei ändern. Wenn Sie diese Option verwenden, wird der folgende Registrierungseintrag erstellt: `HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\<version>\Outlook\PST\PstDisableGrow` und der Datenwert wird auf 1 festgelegt. Diese Registrierungseinstellung wird auf den Computern in Ihrer Organisation durch das GPO erstellt, das erstellt wird, wenn Sie das PST-Sammlungs Tool im Block Modus ausführen.  <br/> | `-BlockChangesToFiles` <br/> |
    | `BlockNewFiles` <br/> |Verwenden Sie diese Option, um zu verhindern, dass Benutzer neue PST-Dateien erstellen, PST-Dateien in Outlook öffnen und importieren und PST-Dateien aus Outlook exportieren. Wenn Sie diese Option verwenden, wird der folgende Registrierungseintrag erstellt: `HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\<version>\Outlook\DisablePst` und der Datenwert wird auf 1 festgelegt. Diese Registrierungseinstellung wird auf den Computern in Ihrer Organisation durch das GPO erstellt, das erstellt wird, wenn Sie das PST-Sammlungs Tool im Block Modus ausführen.  <br/> | `-BlockNewFiles` <br/> |
   
    Im folgenden finden Sie ein Beispiel für die Syntax für den DataCollectorMaster. exe-Befehl unter Verwendung der tatsächlichen Werte für jeden Parameter:

    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Block -JobName PstSearch1 -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -LogLocation "c:\users\admin\desktop\PSTCollection" -BlockChangesToFiles -BlockNewFiles
    ```

    Sie werden aufgefordert, zu bestätigen, dass Sie neue PST-Dateien oder Änderungen an vorhandenen PST-Dateien blockieren möchten. Nachdem Sie bestätigt haben, dass der Vorgang fortgesetzt werden soll und der Befehl erfolgreich ausgeführt wird, wird eine Meldung angezeigt, die besagt, dass ein neues GPO mit dem Namen "PST-Verwendungs Steuerelemente" erstellt wurde.
    
## <a name="step-3-copy-the-pst-files-to-a-collection-location"></a>Schritt 3: Kopieren der PST-Dateien an einen Speicherort der Sammlung

Der nächste Schritt besteht darin, die PST-Dateien zu kopieren, die beim Ausführen des PST-Sammlungs Tools im Find-Modus gefunden wurden. Auf diese Weise können Sie die PST-Dateien an einem Speicherort sammeln, sodass Sie Sie später in Office 365 importieren können. Bevor Sie die PST-Dateien an den Speicherort der Sammlung kopieren, sollten Sie die Gesamtmenge des erforderlichen Speicherplatzes ermitteln. Hierzu können Sie die in Schritt 1 erstellte CSV-Datei verwenden, um die Gesamtgröße aller PST-Dateien zu berechnen.
  
> [!NOTE]
> Nachdem Sie die PST-Dateien in Microsoft 365 importiert und von Ihrem ursprünglichen Speicherort gelöscht haben, können Sie Sie möglicherweise aus dem Speicherort der Sammlung löschen, in den Sie Sie in diesem Schritt kopiert haben. 
  
1. Öffnen Sie auf dem lokalen Computer eine Eingabeaufforderung (als Administrator ausführen).
    
2. Wechseln Sie zu dem Verzeichnis, in das Sie das PST-Sammlungs Tool heruntergeladen haben.
    
3. Führen Sie den folgenden Befehl aus, um die PST-Dateien an einen angegebenen Speicherort zu kopieren.
    
    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Collect -JobName <Name of job from Step 1> -Locations <same locations from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -CopyLocation <Location to copy PST files to>
    ```

    In der folgenden Tabelle werden die Parameter und die erforderlichen Werte beschrieben, wenn Sie den Befehl DataCollectorMaster. exe ausführen, um PST-Dateien zu kopieren. 
    
    |Parameter * * * *|****Beschreibung****|Beispiele * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |Gibt den Typ der zu suchenden Daten an. Derzeit können Sie das PST-Sammlungs Tool verwenden, um nach PST-Dateien zu suchen.  <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |Gibt den Typ der Operation an, die vom Tool ausgeführt wird. Verwenden Sie den `Collect` Wert, um die PST-Dateien zu kopieren, die beim Ausführen des Tools im Find-Modus gefunden wurden. Beachten Sie, dass das Tool PST-Dateien kopieren kann, die in Outlook geöffnet sind, und PST-Dateien kopieren, die mit Outlook-Profilen verbunden sind.  <br/> | `-Mode Collect` <br/> |
    | `JobName` <br/> |Gibt den Namen eines vorhandenen PST-Sammlungs Auftrags an. Sie müssen den gleichen Auftragsnamen verwenden, den Sie beim Ausführen des Tools im Find-Modus in Schritt 1 verwendet haben. Dieser Auftragsname wird auch dem Namen der Protokolldatei hinzugefügt, die erstellt wird, wenn Sie das Tool im Sammelmodus ausführen.  <br/> | `-JobName PstSearch1` <br/> |
    | `Locations` <br/> |Verwenden Sie den gleichen Wert, den Sie für `Locations` den Parameter in Schritt 1 verwendet haben. Sie haben diesen Parameter beim Ausführen des Tools im Sammelmodus hinzugefügt, wenn Sie das Tool erneut ausführen möchten, um die PST-Dateien aus dem Quellspeicherort in Schritt 5 zu löschen.  <br/> | `-Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com"; "CN=FILESERVER02,CN=Computers,DC=contoso,DC=com"` <br/> |
    | `ConfigurationLocation` <br/> |Gibt den Ordner an, der die XML-Konfigurationsdatei enthält, die erstellt wurde, als Sie das Tool im Find-Modus ausgeführt haben. Verwenden Sie den gleichen Wert, den Sie in Schritt 1 für diesen Parameter verwendet haben.  <br/> | `-ConfigurationLocation "c:\users\admin\desktop \PSTCollection\Configuration"` <br/> |
    | `CopyLocation` <br/> |Gibt den Speicherort der Auflistung an, in die Sie die PST-Dateien kopieren möchten. Sie können Dateien auf einen Dateiserver, eine Netzwerkdateifreigabe oder eine Festplatte kopieren. Der Speicherort muss vorhanden sein, bevor Sie das Tool im Sammelmodus ausführen. Das Tool erstellt den Speicherort nicht und gibt einen Fehler zurück, der besagt, dass er nicht vorhanden ist.  <br/> Außerdem müssen Sie Berechtigungen für den durch diesen Parameter angegebenen Speicherort für die Auflistung schreiben.  <br/> | `-CopyLocation "\\FILESERVER03\PSTs"` <br/> |
    | `LogLocation` <br/> |Gibt den Ordner an, in den die Protokolldatei für den Sammelmodus kopiert wird. Dieser Parameter ist optional. Wenn Sie es nicht einschließen, wird die Protokolldatei in den Ordner kopiert, in den Sie das PST-Sammlungs Tool heruntergeladen haben. Verwenden Sie den gleichen Protokollspeicherort, den Sie beim Ausführen des Tools im Suchmodus in Schritt 1 verwendet haben, sodass alle Protokolldateien im gleichen Ordner gespeichert werden.  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ForceRestart` <br/> |Mit diesem optionalen Switch können Sie das Tool im Sammlungsmodus für einen vorhandenen PST-Sammlungsauftrag erneut ausführen. Wenn Sie das Tool zuvor im Sammelmodus ausgeführt haben, das Tool dann jedoch erneut im Suchmodus mit dem `ForceRestart` Switch ausgeführt haben, um Speicherorte für PST-Dateien erneut zu überprüfen, können Sie diese Option verwenden, um das Tool im Sammlungsmodus erneut auszuführen und die PST-Dateien erneut zu kopieren, die beim erneuten Scannen der Speicherorte gefunden wurden. Bei Verwendung des `ForceRestart` Schalters im Sammlungsmodus ignoriert das Tool alle vorherigen Auflistungs Vorgänge und versucht, die PST-Dateien von Grund auf neu zu kopieren.  <br/> | `-ForceRestart` <br/> |
   
    Im folgenden finden Sie ein Beispiel für die Syntax für das Tool DataCollectorMaster. exe unter Verwendung der tatsächlichen Werte für die einzelnen Parameter:
    
    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Collect -JobName PstSearch1 -Locations "CN=FILESERVER01,CN=Computers,DC=contoso,DC=com";"CN=FILESERVER02,CN=Computers,DC=contoso,DC=com" -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -CopyLocation "\\FILESERVER03\PSTs" -LogLocation "c:\users\admin\desktop\PSTCollection"
    ```

    Nachdem Sie den Befehl ausgeführt haben, werden detaillierte Statusmeldungen angezeigt, die den Fortschritt des Sammelns von PST-Dateien anzeigen, die in Schritt 1 gefunden wurden. Nach einer Weile zeigt eine abschließende Statusmeldung an, ob Fehler aufgetreten sind und der Speicherort, an den das Protokoll kopiert wird. Die gleichen Statusmeldungen werden in die Log-Datei kopiert.
    
### <a name="results-of-running-datacollectormasterexe-in-the-collect-mode"></a>Ergebnisse der Ausführung von DataCollectorMaster. exe im Sammelmodus

Nachdem Sie DataCollectorMaster. exe erfolgreich im Sammelmodus ausgeführt haben, werden die folgenden Dateien erstellt und in den durch die `LogLocation` und- `ConfigurationLocation` Parameter angegebenen Ordnern gespeichert. 
  
- **Jobname\>\>von DateTimeStamp. log – die Protokolldatei enthält die Statusmeldungen, die angezeigt wurden._Collect_ \<\<** Diese Datei wird in dem durch den `LogLocation` -Parameter angegebenen Ordner erstellt. 
    
- **\>_Collect_Jobname Collect\<DateTimeStamp\>. XML – die XML-Datei enthält nur Informationen zu den Parameterwerten, die verwendet wurden, wenn das Tool im Sammel \<** Modus ausgeführt wurde. Die Daten in dieser Datei werden verwendet, wenn Sie das Tool DataCollectorMaster. exe erneut ausführen, um PST-Dateien zu löschen. siehe [Schritt 5](#step-5-delete-the-pst-files-found-on-your-network).
    

## <a name="step-4-import-the-pst-files-to-office-365"></a>Schritt 4: Importieren der PST-Dateien in Office 365

Nachdem Sie die in Schritt 1 gefundenen PST-Dateien gesammelt haben, besteht der nächste Schritt darin, Sie in Office 365 in Postfächer zu importieren. Im Rahmen des Importvorgangs müssen Sie eine CSV-Zuordnungsdatei erstellen, die eine Zeile jeder PST-Datei enthält, die Sie importieren möchten. Die Informationen in jeder Zeile geben den Namen der PST-Datei, die e-Mail-Adresse des Benutzers und die Angabe, ob die PST-Datei in das primäre oder Archivpostfach des Benutzers importiert werden soll. Verwenden Sie die Informationen in **der\>Jobname_Find_\<DateTimeStamp. CSV** -Datei (erstellt in Schritt) 1, um Sie beim Erstellen der CSV-Zuordnungsdatei zu unterstützen. 
  
Eine Schritt-für-Schritt-Anleitung zum Importieren von PST-Dateien in Office 365 finden Sie in einem der folgenden Themen:
  
- [Verwenden des Netzwerkuploads zum Importieren von PST-Dateien in Office 365](use-network-upload-to-import-pst-files.md)
    
- [Verwenden des Laufwerkversands zum Importieren von PST-Dateien in Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)
    

## <a name="step-5-delete-the-pst-files-found-on-your-network"></a>Schritt 5: Löschen der in Ihrem Netzwerk gefundenen PST-Dateien

Nachdem die gefundenen und gesammelten PST-Dateien in Office 365 in Exchange Online Postfächer importiert wurden, können Sie das PST-Sammlungs Tool verwenden, um die PST-Dateien aus den ursprünglichen Quellspeicherorten zu löschen, an denen Sie in Schritt 1 gefunden wurden. 
  
1. Öffnen Sie auf dem lokalen Computer eine Eingabeaufforderung (als Administrator ausführen).
    
2. Wechseln Sie zu dem Verzeichnis, in das Sie das PST-Sammlungs Tool heruntergeladen haben.
    
3. Führen Sie den folgenden Befehl aus, um die PST-Dateien zu löschen.

    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Delete -JobName <Name of job from Step 1> -ConfigurationLocation <Location of configuration files from Step 1> -CopyLocation <Location to copy PST files to>
    ```

    In der folgenden Tabelle werden die Parameter und die erforderlichen Werte beschrieben, wenn Sie den Befehl DataCollectorMaster. exe ausführen, um PST-Dateien zu löschen. 
    
    |Parameter * * * *|****Beschreibung****|Beispiele * * * *|
    |:-----|:-----|:-----|
    | `DataSource` <br/> |Gibt den Typ der zu suchenden Daten an. Derzeit können Sie das PST-Sammlungs Tool verwenden, um nach PST-Dateien zu suchen. ![um](../media/b078d05c-3aee-4b9f-8805-6a8a9d8970ee.png)           <br/> | `-DataSource Pst` <br/> |
    | `Mode` <br/> |Gibt den Typ der Operation an, die vom Tool ausgeführt wird. Verwenden Sie den `Delete` -Wert, um die PST-Dateien zu löschen, die gefunden wurden, als Sie das Tool im Find-Modus ausgeführt haben.  <br/> | `-Mode Delete` <br/> |
    | `JobName` <br/> |Gibt den Namen eines vorhandenen PST-Sammlungs Auftrags an. Sie müssen den gleichen Auftragsnamen verwenden, den Sie beim Ausführen des Tools im Such Modus und im Sammelmodus in Schritt 1 und Schritt 3 verwendet haben. Dieser Auftragsname wird auch dem Namen der Protokolldatei hinzugefügt, die erstellt wird, wenn Sie das Tool im Löschmodus ausführen.  <br/> | `-JobName PstSearch1` <br/> |
    | `ConfigurationLocation` <br/> |Gibt den Ordner an, der die XML-Konfigurationsdatei enthält, die erstellt wurde, als Sie das Tool im Sammelmodus ausgeführt haben. Verwenden Sie den gleichen Wert, den Sie in Schritt 3 für diesen Parameter verwendet haben.  <br/> | `-ConfigurationLocation "c:\users\admin\ desktop\PSTCollection\Configuration"` <br/> |
    | `LogLocation` <br/> |Gibt den Ordner an, in den die Protokolldatei für den Löschmodus kopiert wird. Dieser Parameter ist optional. Wenn Sie es nicht einschließen, wird die Protokolldatei in den Ordner kopiert, in den Sie das PST-Sammlungs Tool heruntergeladen haben. Verwenden Sie den gleichen Protokollspeicherort, den Sie beim Ausführen des Tools in den Modi "suchen" und "sammeln" in Schritt 1 und Schritt 3 verwendet haben, damit alle Protokolldateien im gleichen Ordner gespeichert werden.  <br/> | `-LogLocation "c:\users\admin\desktop\PSTCollection"` <br/> |
    | `ForceRestart` <br/> |Mit diesem optionalen Switch können Sie das Tool im Löschmodus für einen vorhandenen PST-Sammlungsauftrag erneut ausführen. Wenn Sie das Tool zuvor im Löschmodus ausgeführt haben, das Tool dann jedoch erneut im Suchmodus mit dem `ForceRestart` Switch ausgeführt haben, um Speicherorte für PST-Dateien erneut zu überprüfen, können Sie diese Option verwenden, um das Tool im Löschmodus erneut auszuführen und die PST-Dateien zu löschen, die beim erneuten Scannen der Speicherorte gefunden wurden. Bei Verwendung des `ForceRestart` Schalters im Löschmodus ignoriert das Tool alle vorherigen Löschvorgänge und versucht erneut, die PST-Dateien zu löschen.  <br/> | `-ForceRestart` <br/> 

    Im folgenden finden Sie ein Beispiel für die Syntax für das Tool DataCollectorMaster. exe unter Verwendung der tatsächlichen Werte für die einzelnen Parameter:
    
    ```powershell
    DataCollectorMaster.exe -DataSource Pst -Mode Delete -JobName PstSearch1 -ConfigurationLocation "c:\users\admin\desktop\PSTCollection\Configuration" -LogLocation "c:\users\admin\desktop\PSTCollection"
    ```

    Nachdem Sie den Befehl ausgeführt haben, werden detaillierte Statusmeldungen angezeigt, die den Fortschritt des Löschens der PST-Dateien anzeigen, die in Schritt 1 gefunden und in Schritt 3 gesammelt wurden. Nach einer Weile zeigt eine abschließende Statusmeldung an, ob Fehler aufgetreten sind und der Speicherort, an den das Protokoll kopiert wird. Die gleichen Statusmeldungen werden in die Log-Datei kopiert.
    
### <a name="results-of-running-datacollectormasterexe-in-the-delete-mode"></a>Ergebnisse der Ausführung von DataCollectorMaster. exe im Löschmodus

Nachdem Sie DataCollectorMaster. exe erfolgreich im Löschmodus ausgeführt haben, werden die folgenden Dateien erstellt und in dem durch die `LogLocation` -und- `ConfigurationLocation` Parameter angegebenen Ordner gespeichert. 
  
- **\>_Delete_Jobname DELETE\<DateTimeStamp\>. log – die Protokolldatei enthält die Statusmeldungen, \<** die angezeigt wurden. Diese Datei wird in dem durch den `LogLocation` -Parameter angegebenen Ordner erstellt. 
    
- **\>_Delete_Jobname DELETE\<DateTimeStamp\>. XML – die XML-Datei enthält nur Informationen zu den Parameterwerten, die verwendet wurden, wenn das Tool im Lösch \<** Modus ausgeführt wurde. Außerdem werden der Name und der Dateipfad jeder gelöschten PST-Datei aufgelistet. Diese Datei wird in dem durch den `ConfigurationLocation` -Parameter angegebenen Ordner erstellt. 
