---
title: Höhere Downloadgeschwindigkeit beim Exportieren von eDiscovery-Suchergebnissen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: c4c8f689-9d52-4e80-ae4b-1411ee9efc43
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie die Windows-Registrierung so konfigurieren, dass der Datendurchsatz beim Herunterladen von Suchergebnissen und Daten erhöht wird.
ms.openlocfilehash: a68a616d2dced4a3dd70580e1b258c95a0b5e39e
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817674"
---
# <a name="increase-the-download-speed-when-exporting-ediscovery-search-results"></a><span data-ttu-id="5d056-103">Höhere Downloadgeschwindigkeit beim Exportieren von eDiscovery-Suchergebnissen</span><span class="sxs-lookup"><span data-stu-id="5d056-103">Increase the download speed when exporting eDiscovery search results</span></span>

<span data-ttu-id="5d056-104">Wenn Sie das eDiscovery-Export Tool zum Herunterladen der Ergebnisse einer Inhaltssuche im Security & Compliance Center oder zum Herunterladen von Daten von Advanced eDiscovery verwenden, startet das Tool eine bestimmte Anzahl gleichzeitiger Exportvorgänge, um die Daten auf den lokalen Computer herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="5d056-104">When you use the eDiscovery Export tool to download the results of a Content Search in the Security & Compliance Center or download data from Advanced eDiscovery, the tool starts a certain number of concurrent export operations to download the data to your local computer.</span></span> <span data-ttu-id="5d056-105">Standardmäßig ist die Anzahl gleichzeitiger Vorgänge auf das 8-fache der Anzahl der Kerne des Computers festgelegt, den Sie zum Herunterladen der Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="5d056-105">By default, the number of concurrent operations is set to 8 times the number of cores in the computer you're using to download the data.</span></span> <span data-ttu-id="5d056-106">Wenn Sie beispielsweise über einen Dual-Core-Computer verfügen (d. h. zwei zentrale Verarbeitungseinheiten auf einem Chip), beträgt die Standardanzahl gleichzeitiger Exportvorgänge 16.</span><span class="sxs-lookup"><span data-stu-id="5d056-106">For example, if you have a dual core computer (meaning two central processing units on one chip), the default number of concurrent export operations is 16.</span></span> <span data-ttu-id="5d056-107">Um den Durchsatz der Datenübertragung zu erhöhen und den Downloadvorgang zu beschleunigen, können Sie die Anzahl gleichzeitiger Vorgänge erhöhen, indem Sie eine Windows-Registrierungseinstellung auf dem Computer konfigurieren, mit dem Sie die Suchergebnisse herunterladen.</span><span class="sxs-lookup"><span data-stu-id="5d056-107">To increase the data transfer throughput and speed-up the download process, you can increase the number of concurrent operations by configuring a Windows Registry setting on the computer that you use to download the search results.</span></span> <span data-ttu-id="5d056-108">Um den Downloadprozess zu beschleunigen, sollten Sie mit einer Einstellung von 24 gleichzeitigen Vorgängen beginnen.</span><span class="sxs-lookup"><span data-stu-id="5d056-108">To speed-up the download process, we recommend that you start with a setting of 24 concurrent operations.</span></span>
  
<span data-ttu-id="5d056-109">Wenn Sie Suchergebnisse über ein Netzwerk mit niedriger Bandbreite herunterladen, wirkt sich die Erhöhung dieser Einstellung möglicherweise negativ aus.</span><span class="sxs-lookup"><span data-stu-id="5d056-109">If you download search results over a low-bandwidth network, increasing this setting might have a negative impact.</span></span> <span data-ttu-id="5d056-110">Alternativ können Sie die Einstellung möglicherweise auf mehr als 24 gleichzeitige Vorgänge in einem Netzwerk mit hoher Bandbreite vergrössern (die maximale Anzahl gleichzeitiger Vorgänge ist 48).</span><span class="sxs-lookup"><span data-stu-id="5d056-110">Alternatively, you might be able to increase the setting to more than 24 concurrent operations in a high-bandwidth network (the maximum number of concurrent operations is 48).</span></span> <span data-ttu-id="5d056-111">Nachdem Sie diese Registrierungseinstellung konfiguriert haben, müssen Sie Sie möglicherweise ändern, um die optimale Anzahl gleichzeitiger Vorgänge für Ihre Umgebung zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="5d056-111">After you configure this registry setting, you might have to change it to find the optimal number of concurrent operations for your environment.</span></span>
  
## <a name="create-a-registry-setting-to-change-the-number-of-concurrent-operations-when-exporting-data"></a><span data-ttu-id="5d056-112">Erstellen einer Registrierungseinstellung zum Ändern der Anzahl gleichzeitiger Vorgänge beim Exportieren von Daten</span><span class="sxs-lookup"><span data-stu-id="5d056-112">Create a registry setting to change the number of concurrent operations when exporting data</span></span>

<span data-ttu-id="5d056-113">Führen Sie das folgende Verfahren auf dem Computer aus, den Sie zum Herunterladen von Suchergebnissen aus dem Security & Compliance Center oder von Daten aus Advanced eDiscovery verwenden.</span><span class="sxs-lookup"><span data-stu-id="5d056-113">Perform the following procedure on the computer that you'll use to download search results from the Security & Compliance Center or data from Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="5d056-114">Schließen Sie das eDiscovery-Export Tool, wenn es geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="5d056-114">Close the eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="5d056-115">Speichern Sie den folgenden Text in einer Fenster Registrierungsdatei unter Verwendung eines filename-Suffixes von. reg; Beispiel: ConcurrentOperations. reg.</span><span class="sxs-lookup"><span data-stu-id="5d056-115">Save the following text to a Window registry file by using a filename suffix of .reg; for example, ConcurrentOperations.reg.</span></span> 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "DownloadConcurrency"="24"
    ```

    <span data-ttu-id="5d056-116">Wie bereits erläutert, wird empfohlen, mit 24 gleichzeitigen Vorgängen zu beginnen und diese Einstellung entsprechend zu ändern.</span><span class="sxs-lookup"><span data-stu-id="5d056-116">As previous explained, we recommend that you start with 24 concurrent operations, and then change this setting as appropriate.</span></span>
    
3. <span data-ttu-id="5d056-117">Klicken oder Doppelklicken Sie in Windows-Explorer auf die reg-Datei, die Sie im vorherigen Schritt erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="5d056-117">In Windows Explorer, click or double-click the .reg file that you created in the previous step.</span></span>
    
4. <span data-ttu-id="5d056-118">Klicken Sie im Fenster Benutzerzugriffssteuerung auf **Ja** , damit der Registrierungs-Editor die Änderung vornehmen kann.</span><span class="sxs-lookup"><span data-stu-id="5d056-118">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="5d056-119">Wenn Sie aufgefordert werden, den Vorgang fortzusetzen, klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="5d056-119">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="5d056-120">Der Registrierungs-Editor zeigt eine Meldung an, die besagt, dass die Einstellung der Registrierung erfolgreich hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="5d056-120">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
6. <span data-ttu-id="5d056-121">Sie können die Schritte 2-5 wiederholen, um den Wert für die `DownloadConcurrency` Registrierungseinstellung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="5d056-121">You can repeat steps 2 - 5 to change the value for the  `DownloadConcurrency` registry setting.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="5d056-122">Nachdem Sie die Registrierungseinstellung erstellt oder geändert `DownloadConcurrency` haben, müssen Sie einen neuen Exportauftrag erstellen oder einen vorhandenen Exportauftrag für die Suchergebnisse oder Daten neu starten, die Sie herunterladen möchten.</span><span class="sxs-lookup"><span data-stu-id="5d056-122">After you create or change the  `DownloadConcurrency` registry setting, be sure to create a new export job or restart an existing export job for the search results or data that you want to download.</span></span> <span data-ttu-id="5d056-123">Weitere Informationen finden Sie im Abschnitt [Weitere Informationen](#more-information) .</span><span class="sxs-lookup"><span data-stu-id="5d056-123">See the [More information](#more-information) section for more details.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="5d056-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5d056-124">More information</span></span>

- <span data-ttu-id="5d056-125">Ein neuer Registrierungsschlüssel wird erstellt, wenn Sie die reg-Datei zum ersten Mal ausführen, die Sie in diesem Verfahren erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="5d056-125">A new registry key is created the first time you run the .reg file that you created in this procedure.</span></span> <span data-ttu-id="5d056-126">Anschließend `DownloadConcurrency` wird die Registrierungseinstellung jedes Mal bearbeitet, wenn Sie die reg-Bearbeitungs Datei ändern und erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="5d056-126">Then the  `DownloadConcurrency` registry setting is edited each time you change and re-run the .reg edit file.</span></span> 
    
- <span data-ttu-id="5d056-127">Das eDiscovery-Export Tool verwendet das [Azure AzCopy-Dienstprogramm](https://go.microsoft.com/fwlink/?linkid=849949) zum Herunterladen von Such Daten aus dem Security & Compliance Center oder von Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="5d056-127">The eDiscovery Export tool uses the [Azure AzCopy utility](https://go.microsoft.com/fwlink/?linkid=849949) to download search data from the Security & Compliance Center or from Advanced eDiscovery.</span></span> <span data-ttu-id="5d056-128">Das Konfigurieren der `DownloadConcurrency` Registrierungseinstellung ähnelt dem Verwenden des **/NC** -Parameters bei der Ausführung des AzCopy-Dienstprogramms.</span><span class="sxs-lookup"><span data-stu-id="5d056-128">Configuring the  `DownloadConcurrency` registry setting is similar to using the **/NC** parameter when running the AzCopy utility.</span></span> <span data-ttu-id="5d056-129">Daher hätte die Registrierungseinstellung von `"DownloadConcurrency=24"` denselben Effekt wie die Verwendung des Parameters value von `/NC:24` mit dem AzCopy-Dienstprogramm.</span><span class="sxs-lookup"><span data-stu-id="5d056-129">So the registry setting of  `"DownloadConcurrency=24"` would have the same effect as using the parameter value of  `/NC:24` with the AzCopy utility.</span></span> 
    
- <span data-ttu-id="5d056-130">Wenn Sie einen Export Download beenden, der derzeit ausgeführt wird, und ihn dann neu starten (indem Sie versuchen, die Suchergebnisse erneut herunterzuladen), versucht das eDiscovery-Export Tool, den gleichen Download fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="5d056-130">If you stop an export download that's currently in progress and then restart it (by trying to download the search results again), the eDiscovery Export tool will attempt to resume the same download.</span></span> <span data-ttu-id="5d056-131">Wenn Sie also einen Download starten, ihn beenden und dann die `DownloadConcurrency` Registrierungseinstellung ändern, schlägt der Download möglicherweise fehl, wenn Sie ihn neu starten (indem Sie auf **exportierte Ergebnisse herunterladen**klicken).</span><span class="sxs-lookup"><span data-stu-id="5d056-131">So, if you start a download, stop it, and then change the  `DownloadConcurrency` registry setting, the download will probably fail if you restart it (by clicking **Download exported results**).</span></span> <span data-ttu-id="5d056-132">Dies liegt daran, dass das Export Tool versucht, den vorherigen Download mithilfe von Einstellungen fortzusetzen, die nicht gültig sind, da Sie die Registrierungseinstellung geändert haben.</span><span class="sxs-lookup"><span data-stu-id="5d056-132">This is because the export tool will attempt to resume the previous download using settings that aren't valid because you changed the registry setting.</span></span>
    
    <span data-ttu-id="5d056-133">Nachdem Sie die `DownloadConcurrency` Registrierungseinstellung geändert haben, müssen Sie daher den Exportauftrag (durch Klicken auf **Export neu starten**) im Security & Compliance Center neu starten.</span><span class="sxs-lookup"><span data-stu-id="5d056-133">Therefore, after you change the  `DownloadConcurrency` registry setting, be sure to restart the export job (by clicking **Restart export**) in the Security & Compliance Center.</span></span> <span data-ttu-id="5d056-134">Anschließend können Sie die exportierten Ergebnisse herunterladen.</span><span class="sxs-lookup"><span data-stu-id="5d056-134">Then you can download the exported results.</span></span> <span data-ttu-id="5d056-135">Weitere Informationen zum Exportieren von Suchergebnissen und Daten finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="5d056-135">For more information about exporting search results and data, see:</span></span>
    
  - [<span data-ttu-id="5d056-136">Exportieren von Inhaltssuchergebnissen </span><span class="sxs-lookup"><span data-stu-id="5d056-136">Export Content Search results</span></span>](export-search-results.md)
    
  - [<span data-ttu-id="5d056-137">Exportieren von Ergebnissen in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="5d056-137">Export results in Advanced eDiscovery</span></span>](export-results-in-advanced-ediscovery.md)
    
