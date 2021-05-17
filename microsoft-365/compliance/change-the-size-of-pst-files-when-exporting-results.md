---
title: Ändern der Größe von PST-Dateien beim Exportieren von eDiscovery-Suchergebnissen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: Sie können die Standardgröße von PST-Dateien ändern, die auf Ihren Computer heruntergeladen werden, wenn Sie eDiscovery-Suchergebnisse exportieren.
ms.openlocfilehash: eb5fcce037ff5e3444b42c996b4a32d818edd29d
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "43942918"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a>Ändern der Größe von PST-Dateien beim Exportieren von eDiscovery-Suchergebnissen

Wenn Sie das eDiscovery-Export-Tool verwenden, um die E-Mail-Ergebnisse einer eDiscovery-Suche aus den verschiedenen Microsoft eDiscovery-Tools zu exportieren, beträgt die Standardgröße einer PST-Datei, die exportiert werden kann, 10 GB. Wenn Sie diese Standardgröße ändern möchten, können Sie die Windows registrierung auf dem Computer bearbeiten, den Sie zum Exportieren der Suchergebnisse verwenden. Ein Grund dafür ist, dass eine PST-Datei auf Wechselmedien, z. B. eine DVD, eine CD oder ein USB-Laufwerk, passen kann. 
  
> [!NOTE]
> Das eDiscovery-Exporttool wird zum Exportieren der Suchergebnisse verwendet, wenn das Tool für die Inhaltssuche im Security & Compliance Center, In-Place eDiscovery in Exchange Online und im eDiscovery Center in SharePoint Online verwendet wird.
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a>Erstellen einer Registrierungseinstellung zum Ändern der Größe von PST-Dateien beim Exportieren von eDiscovery-Suchergebnissen

Führen Sie das folgende Verfahren auf dem Computer aus, mit dem Sie die Ergebnisse einer eDiscovery-Suche exportieren.
  
1. Schließen Sie das eDiscovery-Export-Tool, wenn es geöffnet ist. 
    
2. Speichern Sie den folgenden Text mithilfe eines Dateinamensuffixs von .reg in einer Window-Registrierungsdatei. Beispiel: PstExportSize.reg. 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    Im obigen Beispiel wird der Wert auf  `PstSizeLimitInBytes` 1.073.741.824 Byte oder ca. 1 GB festgelegt. Hier sind einige andere Beispielwerte für die  `PstSizeLimitInBytes` Einstellung. 
    
    |**Größe in GB (ca.)**|**Größe in Bytes**|
    |:-----|:-----|
    |0,7 GB (700 MB)  <br/> |751619277  <br/> |
    |2 GB  <br/> |2147483648  <br/> |
    |4 GB  <br/> |4294967296  <br/> |
    |8 GB  <br/> |8589934592  <br/> |
   
3. Ändern Sie den Wert in die gewünschte maximale Größe einer PST-Datei, wenn Sie Suchergebnisse exportieren, und speichern `PstSizeLimitInBytes` Sie die Datei. 
    
4. Klicken Windows Explorer auf oder doppelklicken Sie auf die .reg-Datei, die Sie in den vorherigen Schritten erstellt haben.
    
5. Klicken Sie im Fenster Benutzerzugriffssteuerung auf **Ja,** damit der Registrierungs-Editor die Änderung vornehmen kann. 
    
6. Wenn Sie zum Fortfahren aufgefordert werden, klicken Sie auf **Ja**.
    
    Der Registrierungs-Editor zeigt eine Meldung an, dass die Einstellung erfolgreich zur Registrierung hinzugefügt wurde.
    
7. Sie können die Schritte 3 bis 6 wiederholen, um den Wert für die  `PstSizeLimitInBytes` Registrierungseinstellung zu ändern. 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a>Häufig gestellte Fragen zum Ändern der Standardgröße von PST-Dateien beim Exportieren von eDiscovery-Suchergebnissen

 **Warum ist die Standardgröße 10 GB?**
  
Die Standardgröße von 10 GB basierte auf Kundenfeedback. 10 GB ist eine gute Balance zwischen der optimalen Menge an Inhalten in einem einzelnen PST und einer minimalen Wahrscheinlichkeit von Dateibeschädigung.
  
 **Soll ich die Standardgröße von PST-Dateien erhöhen oder verringern?**
  
Kunden neigen dazu, die Größenbeschränkung zu verringern, sodass die Suchergebnisse auf Wechselmedien passen, die sie physisch an andere Standorte in ihrer Organisation versenden können. Es wird nicht empfohlen, die Standardgröße zu erhöhen, da bei PST-Dateien, die größer als 10 GB sind, möglicherweise Beschädigungsprobleme auftreten.
  
 **Auf welchem Computer muss ich dies tun?**
  
Sie müssen die Registrierungseinstellung auf jedem lokalen Computer ändern, auf dem Sie das eDiscovery-Exporttool ausführen.
  
 **Muss ich den Computer neu starten, nachdem ich diese Einstellung geändert habe?**
  
Nein, Sie müssen den Computer nicht neu starten. Wenn das eDiscovery-Export-Tool jedoch ausgeführt wird, müssen Sie es schließen und neu starten, nachdem Sie diese Einstellung geändert haben.
  
 **Wird ein vorhandener Registrierungsschlüssel bearbeitet oder wird ein neuer Schlüssel erstellt?**
  
Beim ersten Ausführen der in diesem Verfahren erstellten REG-Datei wird ein neuer Registrierungsschlüssel erstellt. Anschließend wird die Einstellung jedes Mal bearbeitet, wenn Sie die .reg-Bearbeitungsdatei ändern und erneut ausführen.
