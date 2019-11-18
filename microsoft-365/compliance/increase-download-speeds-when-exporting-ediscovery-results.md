---
title: Höhere Downloadgeschwindigkeit beim Exportieren von eDiscovery-Suchergebnissen aus Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: c4c8f689-9d52-4e80-ae4b-1411ee9efc43
description: 'In diesem Artikel erfahren Sie, wie Sie die Windows-Registrierung so konfigurieren, dass der Datendurchsatz beim Herunterladen von Suchergebnissen und Such Daten aus dem Security #a0 Compliance Center und Advanced eDiscovery in Office 365 erhöht wird.'
ms.openlocfilehash: f74d164250f9d5b9b8315fe2651d3374457451ed
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "38686237"
---
# <a name="increase-the-download-speed-when-exporting-ediscovery-search-results-from-office-365"></a>Höhere Downloadgeschwindigkeit beim Exportieren von eDiscovery-Suchergebnissen aus Office 365

Wenn Sie das Office 365 eDiscovery-Export Tool zum Herunterladen der Ergebnisse einer Inhaltssuche im Security #a0 Compliance Center oder zum Herunterladen von Daten aus Office 365 Advanced eDiscovery verwenden, startet das Tool eine bestimmte Anzahl gleichzeitiger Exportvorgänge, um die Daten auf den lokalen Computer herunterzuladen. Standardmäßig ist die Anzahl gleichzeitiger Vorgänge auf das 8-fache der Anzahl der Kerne des Computers festgelegt, den Sie zum Herunterladen der Daten verwenden. Wenn Sie beispielsweise über einen Dual-Core-Computer verfügen (d. h. zwei zentrale Verarbeitungseinheiten auf einem Chip), beträgt die Standardanzahl gleichzeitiger Exportvorgänge 16. Um den Durchsatz der Datenübertragung zu erhöhen und den Downloadvorgang zu beschleunigen, können Sie die Anzahl gleichzeitiger Vorgänge erhöhen, indem Sie eine Windows-Registrierungseinstellung auf dem Computer konfigurieren, mit dem Sie die Suchergebnisse herunterladen. Um den Downloadprozess zu beschleunigen, sollten Sie mit einer Einstellung von 24 gleichzeitigen Vorgängen beginnen.
  
Wenn Sie Suchergebnisse über ein Netzwerk mit niedriger Bandbreite herunterladen, wirkt sich die Erhöhung dieser Einstellung möglicherweise negativ aus. Alternativ können Sie die Einstellung möglicherweise auf mehr als 24 gleichzeitige Vorgänge in einem Netzwerk mit hoher Bandbreite vergrössern (die maximale Anzahl gleichzeitiger Vorgänge ist 48). Nachdem Sie diese Registrierungseinstellung konfiguriert haben, müssen Sie Sie möglicherweise ändern, um die optimale Anzahl gleichzeitiger Vorgänge für Ihre Umgebung zu ermitteln.
  
## <a name="create-a-registry-setting-to-change-the-number-of-concurrent-operations-when-exporting-data"></a>Erstellen einer Registrierungseinstellung zum Ändern der Anzahl gleichzeitiger Vorgänge beim Exportieren von Daten

Führen Sie das folgende Verfahren auf dem Computer aus, den Sie zum Herunterladen von Suchergebnissen aus dem Security #a0 Compliance Center oder von Daten aus Advanced eDiscovery verwenden.
  
1. Schließen Sie das Office 365 eDiscovery-Export Tool, wenn es geöffnet ist. 
    
2. Speichern Sie den folgenden Text in einer Fenster Registrierungsdatei unter Verwendung eines filename-Suffixes von. reg; Beispiel: ConcurrentOperations. reg. 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "DownloadConcurrency"="24"
    ```

    Wie bereits erläutert, wird empfohlen, mit 24 gleichzeitigen Vorgängen zu beginnen und diese Einstellung entsprechend zu ändern.
    
3. Klicken oder Doppelklicken Sie in Windows-Explorer auf die reg-Datei, die Sie im vorherigen Schritt erstellt haben.
    
4. Klicken Sie im Fenster Benutzerzugriffssteuerung auf **Ja** , damit der Registrierungs-Editor die Änderung vornehmen kann. 
    
5. Wenn Sie aufgefordert werden, den Vorgang fortzusetzen, klicken Sie auf **Ja**.
    
    Der Registrierungs-Editor zeigt eine Meldung an, die besagt, dass die Einstellung der Registrierung erfolgreich hinzugefügt wurde.
    
6. Sie können die Schritte 2-5 wiederholen, um den Wert `DownloadConcurrency` für die Registrierungseinstellung zu ändern. 
    
    > [!IMPORTANT]
    > Nachdem Sie die `DownloadConcurrency` Registrierungseinstellung erstellt oder geändert haben, müssen Sie einen neuen Exportauftrag erstellen oder einen vorhandenen Exportauftrag für die Suchergebnisse oder Daten neu starten, die Sie herunterladen möchten. Weitere Informationen finden Sie im Abschnitt [Weitere Informationen](#more-information) . 
  
## <a name="more-information"></a>Weitere Informationen

- Ein neuer Registrierungsschlüssel wird erstellt, wenn Sie die reg-Datei zum ersten Mal ausführen, die Sie in diesem Verfahren erstellt haben. Anschließend wird `DownloadConcurrency` die Registrierungseinstellung jedes Mal bearbeitet, wenn Sie die reg-Bearbeitungs Datei ändern und erneut ausführen. 
    
- Das Office 365 eDiscovery-Export Tool verwendet das [Azure AzCopy-Dienstprogramm](https://go.microsoft.com/fwlink/?linkid=849949) zum Herunterladen von Such Daten aus dem Security #a0 Compliance Center oder von Advanced eDiscovery. Das konfigurieren `DownloadConcurrency` der Registrierungseinstellung ähnelt dem Verwenden des **/NC** -Parameters bei der Ausführung des AzCopy-Dienstprogramms. Daher hätte die Registrierungseinstellung `"DownloadConcurrency=24"` von denselben Effekt wie die Verwendung des Parameters value `/NC:24` von mit dem AzCopy-Dienstprogramm. 
    
- Wenn Sie einen Export Download beenden, der derzeit ausgeführt wird, und ihn dann neu starten (indem Sie versuchen, die Suchergebnisse erneut herunterzuladen), versucht das Office 365 eDiscovery-Export Tool, den gleichen Download fortzusetzen. Wenn Sie also einen Download starten, ihn beenden und dann die `DownloadConcurrency` Registrierungseinstellung ändern, schlägt der Download möglicherweise fehl, wenn Sie ihn neu starten (indem Sie auf **exportierte Ergebnisse herunterladen**klicken). Dies liegt daran, dass das Export Tool versucht, den vorherigen Download mithilfe von Einstellungen fortzusetzen, die nicht gültig sind, da Sie die Registrierungseinstellung geändert haben.
    
    Nachdem Sie die `DownloadConcurrency` Registrierungseinstellung geändert haben, müssen Sie daher den Exportauftrag (durch Klicken auf **Export neu starten**) im Security #a0 Compliance Center neu starten. Anschließend können Sie die exportierten Ergebnisse herunterladen. Weitere Informationen zum Exportieren von Suchergebnissen und Daten finden Sie unter:
    
  - [Exportieren von Inhaltssuchergebnissen ](export-search-results.md)
    
  - [Exportieren von Ergebnissen in Office 365 Advanced eDiscovery](export-results-in-advanced-ediscovery.md)
    
