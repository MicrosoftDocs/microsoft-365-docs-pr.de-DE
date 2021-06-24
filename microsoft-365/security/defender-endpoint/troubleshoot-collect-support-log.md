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
# <a name="collect-support-logs-in-microsoft-defender-for-endpoint-using-live-response"></a><span data-ttu-id="2daa4-104">Sammeln von Supportprotokollen in Microsoft Defender für Endpunkt mithilfe der Liveantwort</span><span class="sxs-lookup"><span data-stu-id="2daa4-104">Collect support logs in Microsoft Defender for Endpoint using live response</span></span> 


<span data-ttu-id="2daa4-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2daa4-105">**Applies to:**</span></span>
- [<span data-ttu-id="2daa4-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="2daa4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2daa4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2daa4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2daa4-108">Möchten Sie Defender für Endpunkt erfahren?</span><span class="sxs-lookup"><span data-stu-id="2daa4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2daa4-109">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="2daa4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="2daa4-110">Wenn Sie sich an den Support wenden, werden Sie möglicherweise aufgefordert, das Ausgabepaket des Microsoft Defender für Endpoint Client Analyzer-Tools bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="2daa4-110">When contacting support, you may be asked to provide the output package of the Microsoft Defender for Endpoint Client Analyzer tool.</span></span>

<span data-ttu-id="2daa4-111">Dieses Thema enthält Anweisungen zum Ausführen des Tools über Live Response.</span><span class="sxs-lookup"><span data-stu-id="2daa4-111">This topic provides instructions on how to run the tool via Live Response.</span></span>

1. <span data-ttu-id="2daa4-112">Herunterladen des entsprechenden Skripts</span><span class="sxs-lookup"><span data-stu-id="2daa4-112">Download the appropriate script</span></span>
    * <span data-ttu-id="2daa4-113">Microsoft Defender für Endpunkt-Clientsensor protokolliert nur: [LiveAnalyzer.ps1 Skript.](https://aka.ms/MDELiveAnalyzer)</span><span class="sxs-lookup"><span data-stu-id="2daa4-113">Microsoft Defender for Endpoint client sensor logs only: [LiveAnalyzer.ps1 script](https://aka.ms/MDELiveAnalyzer).</span></span>
      - <span data-ttu-id="2daa4-114">Ungefähre Größe des Ergebnispakets: ca. 100 KB</span><span class="sxs-lookup"><span data-stu-id="2daa4-114">Result package approximate size: ~100Kb</span></span> 
    *  <span data-ttu-id="2daa4-115">Microsoft Defender für Endpunkt-Clientsensor und Antivirusprotokolle: [LiveAnalyzer+MDAV.ps1 Skript.](https://aka.ms/MDELiveAnalyzerAV)</span><span class="sxs-lookup"><span data-stu-id="2daa4-115">Microsoft Defender for Endpoint client sensor and Antivirus logs: [LiveAnalyzer+MDAV.ps1 script](https://aka.ms/MDELiveAnalyzerAV).</span></span>
       - <span data-ttu-id="2daa4-116">Ungefähre Größe des Ergebnispakets: ~10 Mb</span><span class="sxs-lookup"><span data-stu-id="2daa4-116">Result package approximate size: ~10Mb</span></span> 
 
2.  <span data-ttu-id="2daa4-117">Initiieren Sie eine [Live-Antwortsitzung](live-response.md#initiate-a-live-response-session-on-a-device) auf dem Computer, den Sie untersuchen müssen.</span><span class="sxs-lookup"><span data-stu-id="2daa4-117">Initiate a [Live Response session](live-response.md#initiate-a-live-response-session-on-a-device) on the machine you need to investigate.</span></span>

3.  <span data-ttu-id="2daa4-118">Wählen Sie **Hochladen Datei aus, die in der Bibliothek angezeigt werden soll.**</span><span class="sxs-lookup"><span data-stu-id="2daa4-118">Select **Upload file to library**.</span></span>

    ![Abbildung der Uploaddatei](images/upload-file.png)

4. <span data-ttu-id="2daa4-120">Wählen Sie **"Datei auswählen"** aus.</span><span class="sxs-lookup"><span data-stu-id="2daa4-120">Select **Choose file**.</span></span>

    ![Abbildung der Schaltfläche "Datei auswählen1"](images/choose-file.png)

5. <span data-ttu-id="2daa4-122">Wählen Sie die heruntergeladene Datei mit dem Namen MDELiveAnalyzer.ps1 aus, und klicken Sie dann auf **"Bestätigen".**</span><span class="sxs-lookup"><span data-stu-id="2daa4-122">Select the downloaded file named MDELiveAnalyzer.ps1 and then click on **Confirm**</span></span>


   ![Abbildung der Schaltfläche "Datei auswählen"2](images/analyzer-file.png)


6. <span data-ttu-id="2daa4-124">Verwenden Sie während der LiveResponse-Sitzung die folgenden Befehle, um den Analyzer auszuführen und die Ergebnisdatei zu erfassen:</span><span class="sxs-lookup"><span data-stu-id="2daa4-124">While still in the LiveResponse session, use the commands below to run the analyzer and collect the result file:</span></span>

    ```console
    Run MDELiveAnalyzer.ps1
    GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip"
    ```

    <span data-ttu-id="2daa4-125">[![Abbildung von Befehlen ](images/analyzer-commands.png)](images/analyzer-commands.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="2daa4-125">[ ![Image of commands](images/analyzer-commands.png) ](images/analyzer-commands.png#lightbox)</span></span>


>[!NOTE]
> - <span data-ttu-id="2daa4-126">Die neueste Vorschauversion von MDEClientAnalyzer kann hier heruntergeladen werden: [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer) .</span><span class="sxs-lookup"><span data-stu-id="2daa4-126">The latest preview version of MDEClientAnalyzer can be downloaded here: [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer).</span></span>
> 
> - <span data-ttu-id="2daa4-127">Das LiveAnalyzer-Skript lädt das Problembehandlungspaket auf den Zielcomputer von: https://mdatpclientanalyzer.blob.core.windows.net .</span><span class="sxs-lookup"><span data-stu-id="2daa4-127">The LiveAnalyzer script downloads the troubleshooting package on the destination machine from: https://mdatpclientanalyzer.blob.core.windows.net.</span></span>
> 
>   <span data-ttu-id="2daa4-128">Wenn Sie nicht zulassen können, dass der Computer die oben genannte URL erreicht, laden Sie MDEClientAnalyzerPreview.zip Datei in die Bibliothek hoch, bevor Sie das LiveAnalyzer-Skript ausführen:</span><span class="sxs-lookup"><span data-stu-id="2daa4-128">If you cannot allow the machine to reach the above URL, then upload MDEClientAnalyzerPreview.zip file to the library before running the LiveAnalyzer script:</span></span>
>
>   ```console
>   PutFile MDEClientAnalyzerPreview.zip -overwrite
>   Run MDELiveAnalyzer.ps1
>   GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip" 
>   ```
> 
> - <span data-ttu-id="2daa4-129">Weitere Informationen zum lokalen Sammeln von Daten auf einem Computer für den Fall, dass der Computer nicht mit Microsoft Defender für Endpunkt-Clouddiensten kommuniziert oder nicht wie erwartet im Microsoft Defender für Endpunkt-Portal angezeigt wird, finden Sie unter Überprüfen der [Clientkonnektivität mit Microsoft Defender für Endpunkt-Dienst-URLs.](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</span><span class="sxs-lookup"><span data-stu-id="2daa4-129">For more information on gathering data locally on a machine in case the machine isn't communicating with Microsoft Defender for Endpoint cloud services, or does not appear in Microsoft Defender for Endpoint portal as expected, see [Verify client connectivity to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls).</span></span>
