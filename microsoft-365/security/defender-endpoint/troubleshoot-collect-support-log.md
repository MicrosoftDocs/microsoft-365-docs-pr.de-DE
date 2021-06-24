---
title: Sammeln von Supportprotokollen in Microsoft Defender für Endpunkte mithilfe der Liveantwort
description: Erfahren Sie, wie Sie Protokolle mithilfe von Liveantworten sammeln, um Probleme mit Microsoft Defender für Endpunkte zu beheben.
keywords: support, log, collect, troubleshoot, live response, liveanalyzer, analyzer, live, response
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 0e7634177e58b558381fdc230533b55cade9dc13
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108511"
---
# <a name="collect-support-logs-in-microsoft-defender-for-endpoint-using-live-response"></a>Sammeln von Supportprotokollen in Microsoft Defender für Endpunkt mithilfe der Liveantwort 


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender für Endpunkt erfahren? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


Wenn Sie sich an den Support wenden, werden Sie möglicherweise aufgefordert, das Ausgabepaket des Microsoft Defender für Endpoint Client Analyzer-Tools bereitzustellen.

Dieses Thema enthält Anweisungen zum Ausführen des Tools über Live Response.

1. Herunterladen des entsprechenden Skripts
    * Microsoft Defender für Endpunkt-Clientsensor protokolliert nur: [LiveAnalyzer.ps1 Skript.](https://aka.ms/MDELiveAnalyzer)
      - Ungefähre Größe des Ergebnispakets: ca. 100 KB 
    *  Microsoft Defender für Endpunkt-Clientsensor und Antivirusprotokolle: [LiveAnalyzer+MDAV.ps1 Skript.](https://aka.ms/MDELiveAnalyzerAV)
       - Ungefähre Größe des Ergebnispakets: ~10 Mb 
 
2.  Initiieren Sie eine [Live-Antwortsitzung](live-response.md#initiate-a-live-response-session-on-a-device) auf dem Computer, den Sie untersuchen müssen.

3.  Wählen Sie **Hochladen Datei aus, die in der Bibliothek angezeigt werden soll.**

    ![Abbildung der Uploaddatei](images/upload-file.png)

4. Wählen Sie **"Datei auswählen"** aus.

    ![Abbildung der Schaltfläche "Datei auswählen1"](images/choose-file.png)

5. Wählen Sie die heruntergeladene Datei mit dem Namen MDELiveAnalyzer.ps1 aus, und klicken Sie dann auf **"Bestätigen".**


   ![Abbildung der Schaltfläche "Datei auswählen"2](images/analyzer-file.png)


6. Verwenden Sie während der LiveResponse-Sitzung die folgenden Befehle, um den Analyzer auszuführen und die Ergebnisdatei zu erfassen:

    ```console
    Run MDELiveAnalyzer.ps1
    GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip"
    ```

    [![Abbildung von Befehlen ](images/analyzer-commands.png)](images/analyzer-commands.png#lightbox)


>[!NOTE]
> - Die neueste Vorschauversion von MDEClientAnalyzer kann hier heruntergeladen werden: [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer) .
> 
> - Das LiveAnalyzer-Skript lädt das Problembehandlungspaket auf den Zielcomputer von: https://mdatpclientanalyzer.blob.core.windows.net .
> 
>   Wenn Sie nicht zulassen können, dass der Computer die oben genannte URL erreicht, laden Sie MDEClientAnalyzerPreview.zip Datei in die Bibliothek hoch, bevor Sie das LiveAnalyzer-Skript ausführen:
>
>   ```console
>   PutFile MDEClientAnalyzerPreview.zip -overwrite
>   Run MDELiveAnalyzer.ps1
>   GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip" 
>   ```
> 
> - Weitere Informationen zum lokalen Sammeln von Daten auf einem Computer für den Fall, dass der Computer nicht mit Microsoft Defender für Endpunkt-Clouddiensten kommuniziert oder nicht wie erwartet im Microsoft Defender für Endpunkt-Portal angezeigt wird, finden Sie unter Überprüfen der [Clientkonnektivität mit Microsoft Defender für Endpunkt-Dienst-URLs.](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)
