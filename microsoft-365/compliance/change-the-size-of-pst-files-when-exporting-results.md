---
title: Ändern der Größe von PST-Dateien beim Exportieren von eDiscovery-Suchergebnissen
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: Sie können die Standardgröße von PST-Dateien ändern, die beim Exportieren von eDiscovery-Suchergebnissen auf Ihren Computer heruntergeladen werden.
ms.openlocfilehash: 3a302164a1de6d383e2e120dd7a849e692e622eb
ms.sourcegitcommit: e386037c9cc335c86896dc153344850735afbccd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/27/2019
ms.locfileid: "39634002"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a>Ändern der Größe von PST-Dateien beim Exportieren von eDiscovery-Suchergebnissen

Wenn Sie das e-Mail-Ergebnis einer eDiscovery-Suche mithilfe des Office 365 eDiscovery-Exporttools aus den verschiedenen Microsoft eDiscovery-Tools exportieren, beträgt die Standardgröße einer PST-Datei, die exportiert werden kann, 10 GB. Wenn Sie diese Standardgröße ändern möchten, können Sie die Windows-Registrierung auf dem Computer bearbeiten, mit dem Sie die Suchergebnisse exportieren. Ein Grund hierfür ist, dass eine PST-Datei auf Wechselmedien, einer solchen DVD, einer CD oder einem USB-Laufwerk angepasst werden kann. 
  
> [!NOTE]
> Das Office 365 eDiscovery-Export Tool wird verwendet, um die Suchergebnisse zu exportieren, wenn Sie das Tool für die Inhaltssuche im Security and Compliance Center, in-Place eDiscovery in Exchange Online und im eDiscovery Center in SharePoint Online verwenden.
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a>Erstellen einer Registrierungseinstellung zum Ändern der Größe von PST-Dateien beim Exportieren von eDiscovery-Suchergebnissen

Führen Sie das folgende Verfahren auf dem Computer aus, mit dem Sie die Ergebnisse einer eDiscovery-Suche exportieren.
  
1. Schließen Sie das Office 365 eDiscovery-Export Tool, wenn es geöffnet ist. 
    
2. Speichern Sie den folgenden Text in einer Fenster Registrierungsdatei unter Verwendung eines filename-Suffixes von. reg; Beispiel: PstExportSize. reg. 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    Im obigen Beispiel ist der `PstSizeLimitInBytes` Wert auf 1.073.741.824 Byte oder ungefähr 1 GB festgelegt. Hier sind einige weitere Beispielwerte für die `PstSizeLimitInBytes` Einstellung. 
    
    |**Größe in GB (ca.)**|**Größe in Bytes**|
    |:-----|:-----|
    |0,7 GB (700 MB)  <br/> |751619277  <br/> |
    |2 GB  <br/> |2147483648  <br/> |
    |4 GB  <br/> |4294967296  <br/> |
    |8 GB  <br/> |8589934592  <br/> |
   
3. Ändern Sie `PstSizeLimitInBytes` den Wert in die gewünschte maximale Größe einer PST-Datei, wenn Sie Suchergebnisse exportieren, und speichern Sie dann die Datei. 
    
4. Klicken oder Doppelklicken Sie in Windows-Explorer auf die reg-Datei, die Sie in den vorherigen Schritten erstellt haben.
    
5. Klicken Sie im Fenster Benutzerzugriffssteuerung auf **Ja** , damit der Registrierungs-Editor die Änderung vornehmen kann. 
    
6. Wenn Sie aufgefordert werden, den Vorgang fortzusetzen, klicken Sie auf **Ja**.
    
    Der Registrierungs-Editor zeigt eine Meldung an, die besagt, dass die Einstellung der Registrierung erfolgreich hinzugefügt wurde.
    
7. Sie können die Schritte 3-6 wiederholen, um den Wert `PstSizeLimitInBytes` für die Registrierungseinstellung zu ändern. 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a>Häufig gestellte Fragen zum Ändern der Standardgröße von PST-Dateien beim Exportieren von eDiscovery-Suchergebnissen

 **Warum ist die Standardgröße 10 GB?**
  
Die Standardgröße von 10 GB basierte auf dem Kundenfeedback; 10 GB ist ein gutes Gleichgewichtzwischen der optimalen Menge an Inhalten in einer einzelnen PST-Datei und einer minimalen Wahrscheinlichkeit von Beschädigung von Dateien.
  
 **Sollte ich die Standardgröße von PST-Dateien vergrößern oder verkleinern?**
  
Kunden neigen dazu, die Größenbeschränkung so zu verringern, dass die Suchergebnisse auf Wechseldatenträgern angepasst werden, die Sie physisch an andere Standorte in Ihrer Organisation versenden können. Es wird nicht empfohlen, dass Sie die Standardgröße vergrößern, da PST-Dateien mit mehr als 10 GB möglicherweise zu Problemen mit der Beschädigung kommen.
  
 **Auf welchem Computer muss ich diese Funktion ausführen?**
  
Sie müssen die Registrierungseinstellung auf einem lokalen Computer ändern, auf dem Sie das Office 365 eDiscovery-Export Tool ausführen.
  
 **Muss ich den Computer neu starten, nachdem ich diese Einstellung geändert habe?**
  
Nein, Sie müssen den Computer nicht neu starten. Wenn das Office 365 eDiscovery-Export Tool jedoch aktiv ist, müssen Sie es schließen und neu starten, nachdem Sie diese Einstellung geändert haben.
  
 **Wird ein vorhandener Registrierungsschlüssel bearbeitet oder wird ein neuer Schlüssel erstellt?**
  
Ein neuer Registrierungsschlüssel wird erstellt, wenn Sie die reg-Datei zum ersten Mal ausführen, die Sie in diesem Verfahren erstellt haben. Anschließend wird die Einstellung jedes Mal bearbeitet, wenn Sie die reg-Bearbeitungs Datei ändern und erneut ausführen.
