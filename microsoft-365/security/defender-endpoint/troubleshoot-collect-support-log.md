---
title: Sammeln von Supportprotokollen in Microsoft Defender for Endpoints mithilfe von Liveantworten
description: Informationen zum Sammeln von Protokollen mithilfe von Liveantworten zur Problembehandlung von Microsoft Defender for Endpoints-Problemen
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
ms.openlocfilehash: 8b7fe8f0973cabfb5f5268be28ac606dfc4c6387
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51183717"
---
# <a name="collect-support-logs-in-microsoft-defender-for-endpoint-using-live-response"></a>Sammeln von Supportprotokollen in Microsoft Defender for Endpoint mithilfe von Liveantworten 


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


Wenn Sie sich an den Support wenden, werden Sie möglicherweise aufgefordert, das Ausgabepaket des Microsoft Defender for Endpoint Client Analyzer-Tools zur Verfügung zu stellen.

Dieses Thema enthält Anweisungen zum Ausführen des Tools über Live Response.

1. Laden Sie das entsprechende Skript herunter
    * Microsoft Defender for Endpoint-Clientsensorprotokolle: [LiveAnalyzer.ps1 Skript .](https://aka.ms/MDELiveAnalyzer)
      - Ungefähre Größe des Ergebnispakets: ~100Kb 
    *  Microsoft Defender for Endpoint-Clientsensor- und Antivirusprotokolle: [LiveAnalyzer+MDAV.ps1 Skript.](https://aka.ms/MDELiveAnalyzerAV)
       - Ungefähre Größe des Ergebnispakets: ~10 Mb 
 
2.  Initiieren Sie [eine Live-Reaktionssitzung](live-response.md#initiate-a-live-response-session-on-a-device) auf dem Computer, den Sie untersuchen müssen.

3.  Wählen **Sie Datei in Bibliothek hochladen aus.**

    ![Bild der Uploaddatei](images/upload-file.png)

4. Wählen **Sie Datei auswählen aus.**

    ![Abbildung der Auswahldateischaltfläche1](images/choose-file.png)

5. Wählen Sie die heruntergeladene Datei namens MDELiveAnalyzer.ps1 aus, und klicken Sie dann auf **Bestätigen.**


   ![Abbildung der Auswahldateischaltfläche2](images/analyzer-file.png)


6. Verwenden Sie während der LiveResponse-Sitzung die folgenden Befehle, um die Analyse auszuführen und die Ergebnisdatei zu erfassen:

    ```console
    Run MDELiveAnalyzer.ps1
    GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip" -auto
    ```

    ![Abbildung von Befehlen](images/analyzer-commands.png)


>[!NOTE]
> - Die neueste Vorschauversion von MDEClientAnalyzer finden Sie hier: [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer) .
> 
> - Das LiveAnalyzer-Skript lädt das Problembehandlungspaket auf dem Zielcomputer von: https://mdatpclientanalyzer.blob.core.windows.net herunter.
> 
>   Wenn Sie dem Computer nicht erlauben können, die oben aufgeführte URL zu erreichen, laden MDEClientAnalyzerPreview.zip in die Bibliothek hoch, bevor Sie das LiveAnalyzer-Skript ausführen:
>
>   ```console
>   PutFile MDEClientAnalyzerPreview.zip -overwrite
>   Run MDELiveAnalyzer.ps1
>   GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip" -auto
>   ```
> 
> - Weitere Informationen zum lokalen Sammeln von Daten auf einem Computer, falls der Computer nicht mit Microsoft Defender for Endpoint-Clouddiensten kommuniziert oder nicht wie erwartet im Microsoft Defender for Endpoint-Portal angezeigt wird, finden Sie unter [Verify client connectivity to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-atp-service-urls).
