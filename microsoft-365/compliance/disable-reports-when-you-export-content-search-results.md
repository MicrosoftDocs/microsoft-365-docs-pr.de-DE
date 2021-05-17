---
title: Deaktivieren von Berichten beim Exportieren von Inhaltssuchergebnissen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
ms.custom:
- seo-marvel-apr2020
description: Bearbeiten Sie Windows Registrierung auf Ihrem lokalen Computer, um Berichte zu deaktivieren, wenn Sie die Ergebnisse einer Inhaltssuche aus dem Security & Compliance Center exportieren.
ms.openlocfilehash: 0eaf9c9d1f70e03481b00d38d2e487709329c4cd
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817854"
---
# <a name="disable-reports-when-you-export-content-search-results"></a>Deaktivieren von Berichten beim Exportieren von Inhaltssuchergebnissen

Wenn Sie das eDiscovery-Export-Tool zum Exportieren der Ergebnisse einer Inhaltssuche im Security & Compliance Center verwenden, erstellt und exportiert das Tool automatisch zwei Berichte, die zusätzliche Informationen zu den exportierten Inhalten enthalten. Diese Berichte sind die Results.csv und die Manifest.xml -Datei (ausführliche Beschreibungen dieser Berichte finden Sie im Abschnitt Häufig gestellte Fragen zum Deaktivieren von Exportberichten in diesem Thema). [](#frequently-asked-questions-about-disabling-export-reports) Da diese Dateien sehr groß sein können, können Sie die Downloadzeit beschleunigen und Speicherplatz sparen, indem Sie verhindern, dass diese Dateien exportiert werden. Sie können dies tun, indem Sie Windows Registrierung auf dem Computer ändern, den Sie zum Exportieren der Suchergebnisse verwenden. Wenn Sie die Berichte zu einem späteren Zeitpunkt hinzufügen möchten, können Sie die Registrierungseinstellung bearbeiten. 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a>Erstellen von Registrierungseinstellungen zum Deaktivieren der Exportberichte

Führen Sie das folgende Verfahren auf dem Computer aus, mit dem Sie die Ergebnisse einer Inhaltssuche exportieren.
  
1. Schließen Sie das eDiscovery-Export-Tool, wenn es geöffnet ist.
    
2. Führen Sie einen oder beide der folgenden Schritte aus, je nachdem, welchen Exportbericht Sie deaktivieren möchten.
    
    - **Results.csv**
    
      Speichern Sie den folgenden Text in Windows Registrierungsdatei, indem Sie das Dateinamensuffix .reg verwenden. Beispielsweise DisableResultsCsv.reg.
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - **Manifest.xml**
    
      Speichern Sie den folgenden Text in Windows Registrierungsdatei, indem Sie das Dateinamensuffix .reg verwenden. Beispielsweise DisableManifestXml.reg.
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. Klicken Windows Explorer auf oder doppelklicken Sie auf die .reg-Datei, die Sie in den vorherigen Schritten erstellt haben.
    
4. Klicken Sie im Fenster Benutzerzugriffssteuerung auf **Ja,** damit der Registrierungs-Editor die Änderung vornehmen kann. 
    
5. Wenn Sie zum Fortfahren aufgefordert werden, klicken Sie auf **Ja**.
    
    Der Registrierungs-Editor zeigt eine Meldung an, dass die Einstellung erfolgreich zur Registrierung hinzugefügt wurde.
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a>Bearbeiten von Registrierungseinstellungen zum erneuten Aktivieren der Exportberichte

Wenn Sie die Results.csv- und Manifest.xml-Berichte durch Erstellen der .reg-Dateien im vorherigen Verfahren deaktiviert haben, können Sie diese Dateien bearbeiten, um einen Bericht erneut zu aktivieren, sodass er mit den Suchergebnissen exportiert wird. Führen Sie erneut das folgende Verfahren auf dem Computer aus, mit dem Sie die Ergebnisse einer Inhaltssuche exportieren.
  
1. Schließen Sie das eDiscovery-Export-Tool, wenn es geöffnet ist.
    
2. Bearbeiten Sie eine oder beide der .reg-Bearbeitungsdateien, die Sie im vorherigen Verfahren erstellt haben.
    
    - **Results.csv**
    
        Öffnen Sie die Datei DisableResultsCsv.reg in Editor, ändern Sie den Wert in , und speichern Sie `False` `True` die Datei. Wenn Sie die Datei beispielsweise bearbeitet haben, sieht sie wie die folgende aus:
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - **Manifest.xml**
    
        Öffnen Sie die Datei DisableManifestXml.reg in Editor, ändern Sie den Wert in , und speichern Sie `False` `True` die Datei. Wenn Sie die Datei beispielsweise bearbeitet haben, sieht sie wie die folgende aus:
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. Klicken Windows Explorer auf eine REG-Datei, die Sie im vorherigen Schritt bearbeitet haben, oder doppelklicken Sie auf diese.
    
4. Klicken Sie im Fenster Benutzerzugriffssteuerung auf **Ja,** damit der Registrierungs-Editor die Änderung vornehmen kann. 
    
5. Wenn Sie zum Fortfahren aufgefordert werden, klicken Sie auf **Ja**.
    
    Der Registrierungs-Editor zeigt eine Meldung an, dass die Einstellung erfolgreich zur Registrierung hinzugefügt wurde.
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a>Häufig gestellte Fragen zum Deaktivieren von Exportberichten

 **Was sind die Results.csv und Manifest.xml Berichte?**
  
Die Results.csv und Manifest.xml enthalten zusätzliche Informationen zu den exportierten Inhalten.
  
- **Results.csv** Ein Excel, das Informationen zu jedem Element enthält, das als Suchergebnis heruntergeladen wird. Für E-Mails enthält das Ergebnisprotokoll Informationen zu jeder Nachricht, einschließlich: 
    
  - Der Speicherort der Nachricht im Quellpostfach (einschließlich der Angabe, ob die Nachricht sich im primären oder im Archivpostfach befindet).
    
  - Das Datum, an dem die Nachricht gesendet oder empfangen wurde.
    
  - Die Betreffzeile der Nachricht.
    
  - Absender und Empfänger der Nachricht.
    
  - Gibt an, ob es sich bei der Nachricht um eine doppelte Nachricht handelt, wenn Sie die Deduplizierung beim Exportieren der Suchergebnisse aktiviert haben. Doppelte Nachrichten haben einen Wert in der Spalte **Parent ItemId,** der die Nachricht als Duplikat identifiziert. Der Wert in der **Spalte Parent ItemId** ist identisch mit dem Wert in der **Spalte Item DocumentId** der Nachricht, die exportiert wurde. 
    
    Für Dokumente von SharePoint und OneDrive for Business enthält das Ergebnisprotokoll Informationen zu jedem Dokument, einschließlich:
    
  - Die URL für das Dokument.
    
  - Die URL für die Websitesammlung, in der sich das Dokument befindet.
    
  - Das Datum, an dem das Dokument zuletzt geändert wurde.
    
  - Der Name des Dokuments (das sich in der Spalte Betreff im Ergebnisprotokoll befindet).
    
- **Manifest.xml** Eine Manifestdatei (im XML-Format), die Informationen zu jedem Element enthält, das in den Suchergebnissen enthalten ist. Die Informationen in diesem Bericht sind mit dem bericht Results.csv identisch, haben jedoch das format, das durch das elektronische Ermittlungsreferenzmodell (Electronic Discovery Reference Model, EDRM) angegeben wird. Weitere Informationen zu EDRM finden Sie unter [https://www.edrm.net](https://www.edrm.net) .
    
 **Wann sollte ich das Exportieren dieser Berichte deaktivieren?**
  
Dies hängt von Ihren spezifischen Anforderungen ab. Viele Organisationen benötigen keine zusätzlichen Informationen zu Suchergebnissen und benötigen diese Berichte nicht.
  
 **Auf welchem Computer muss ich dies tun?**
  
 Sie müssen die Registrierungseinstellung auf jedem lokalen Computer ändern, auf dem Sie das eDiscovery-Export-Tool ausführen. 
  
 **Muss ich den Computer neu starten, nachdem ich diese Einstellung geändert habe?**
  
Nein, Sie müssen den Computer nicht neu starten. Wenn das eDiscovery-Exporttool jedoch ausgeführt wird, müssen Sie es schließen und es neu starten, nachdem Sie die Registrierungseinstellung geändert haben.
  
 **Wird ein vorhandener Registrierungsschlüssel bearbeitet oder wird ein neuer Schlüssel erstellt?**
  
Beim ersten Ausführen der .reg-Datei, die Sie im Verfahren in diesem Thema erstellt haben, wird ein neuer Registrierungsschlüssel erstellt. Anschließend wird die Einstellung jedes Mal bearbeitet, wenn Sie die .reg-Bearbeitungsdatei ändern und erneut ausführen.
