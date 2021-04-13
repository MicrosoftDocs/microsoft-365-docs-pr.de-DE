---
title: Behandeln von Problemen mit der Kernelerweiterung in Microsoft Defender for Endpoint unter macOS
description: Behandeln von Problemen mit kernelerweiterungsbezogenen Problemen in Microsoft Defender for Endpoint unter macOS.
keywords: microsoft, defender, atp, mac, kernel, extension
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 32a4819f7a607c69b4dbf45b3284b2f4ea66ffc4
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689653"
---
# <a name="troubleshoot-kernel-extension-issues-in-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="9e9c9-104">Behandeln von Problemen mit der Kernelerweiterung in Microsoft Defender for Endpoint unter macOS</span><span class="sxs-lookup"><span data-stu-id="9e9c9-104">Troubleshoot kernel extension issues in Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9e9c9-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="9e9c9-105">**Applies to:**</span></span>

- [<span data-ttu-id="9e9c9-106">Microsoft Defender for Endpoint unter macOS</span><span class="sxs-lookup"><span data-stu-id="9e9c9-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="9e9c9-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9e9c9-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9e9c9-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e9c9-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9e9c9-109">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="9e9c9-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9e9c9-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="9e9c9-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="9e9c9-111">Dieser Artikel enthält Informationen zum Behandeln von Problemen mit der Kernelerweiterung, die als Teil von Microsoft Defender for Endpoint unter macOS installiert ist.</span><span class="sxs-lookup"><span data-stu-id="9e9c9-111">This article provides information on how to troubleshoot issues with the kernel extension that is installed as part of Microsoft Defender for Endpoint on macOS.</span></span>

<span data-ttu-id="9e9c9-112">Ab macOS High Sierra (10.13) muss macOS alle Kernelerweiterungen explizit genehmigt werden, bevor sie auf dem Gerät ausgeführt werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="9e9c9-112">Starting with macOS High Sierra (10.13), macOS requires all kernel extensions to be explicitly approved before they're allowed to run on the device.</span></span>

<span data-ttu-id="9e9c9-113">Wenn Sie die Kernelerweiterung während der Bereitstellung/Installation von Microsoft Defender for Endpoint auf macOS nicht genehmigt haben, zeigt die Anwendung ein Banner an, in dem Sie aufgefordert werden, sie zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="9e9c9-113">If you didn't approve the kernel extension during the deployment/installation of Microsoft Defender for Endpoint on macOS, the application displays a banner prompting you to enable it:</span></span>

   ![Deaktivierter Screenshot von RTP](images/mdatp-32-main-app-fix.png)

<span data-ttu-id="9e9c9-115">Sie können auch ```mdatp health``` ausführen.</span><span class="sxs-lookup"><span data-stu-id="9e9c9-115">You can also run ```mdatp health```.</span></span> <span data-ttu-id="9e9c9-116">Es wird berichtet, ob der Echtzeitschutz aktiviert ist, aber nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="9e9c9-116">It reports if real-time protection is enabled but not available.</span></span> <span data-ttu-id="9e9c9-117">Dies bedeutet, dass die Kernelerweiterung nicht für die Ausführung auf Ihrem Gerät genehmigt wurde.</span><span class="sxs-lookup"><span data-stu-id="9e9c9-117">This indicates that the kernel extension isn't approved to run on your device.</span></span>

```bash
mdatp health
```
```Output
...
real_time_protection_enabled                : false
real_time_protection_available              : true
...
```

<span data-ttu-id="9e9c9-118">In den folgenden Abschnitten finden Sie Anleitungen zur Behandlung dieses Problems, abhängig von der Methode, die Sie zum Bereitstellen von Microsoft Defender for Endpoint auf macOS verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="9e9c9-118">The following sections provide guidance on how to address this issue, depending on the method that you used to deploy Microsoft Defender for Endpoint on macOS.</span></span>

## <a name="managed-deployment"></a><span data-ttu-id="9e9c9-119">Verwaltete Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="9e9c9-119">Managed deployment</span></span>

<span data-ttu-id="9e9c9-120">Weitere Informationen finden Sie in den Anweisungen zum Verwaltungstool, das Sie zum Bereitstellen des Produkts verwendet haben:</span><span class="sxs-lookup"><span data-stu-id="9e9c9-120">See the instructions corresponding to the management tool that you used to deploy the product:</span></span>

- [<span data-ttu-id="9e9c9-121">JAMF-basierte Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="9e9c9-121">JAMF-based deployment</span></span>](mac-install-with-jamf.md)
- [<span data-ttu-id="9e9c9-122">Microsoft-Intune-basierte Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="9e9c9-122">Microsoft Intune-based deployment</span></span>](mac-install-with-intune.md#create-system-configuration-profiles)

## <a name="manual-deployment"></a><span data-ttu-id="9e9c9-123">Manuelle Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="9e9c9-123">Manual deployment</span></span>

<span data-ttu-id="9e9c9-124">Wenn seit der Installation des Produkts weniger als 30 Minuten vergangen sind, navigieren Sie zu **Systemeinstellungen** Sicherheit & Datenschutz , wo Sie Systemsoftware von  >  Entwicklern  "Microsoft Corporation" zulassen müssen.</span><span class="sxs-lookup"><span data-stu-id="9e9c9-124">If less than 30 minutes have passed since the product was installed, navigate to **System Preferences** > **Security & Privacy**, where you have to **Allow** system software from developers "Microsoft Corporation".</span></span>

<span data-ttu-id="9e9c9-125">Wenn diese Aufforderung nicht angezeigt wird, bedeutet dies, dass 30 oder mehr Minuten vergangen sind und die Kernelerweiterung weiterhin nicht genehmigt wurde, um auf Ihrem Gerät ausgeführt zu werden:</span><span class="sxs-lookup"><span data-stu-id="9e9c9-125">If you don't see this prompt, it means that 30 or more minutes have passed, and the kernel extension still not been approved to run on your device:</span></span>

![Sicherheits- und Datenschutzfenster nach ablaufend abgelaufener Eingabeaufforderung](images/mdatp-33-securityprivacysettings-noprompt.png)

<span data-ttu-id="9e9c9-127">In diesem Fall müssen Sie die folgenden Schritte ausführen, um den Genehmigungsfluss erneut auszulösen.</span><span class="sxs-lookup"><span data-stu-id="9e9c9-127">In this case, you need to perform the following steps to trigger the approval flow again.</span></span>

1. <span data-ttu-id="9e9c9-128">Versuchen Sie im Terminal, den Treiber zu installieren.</span><span class="sxs-lookup"><span data-stu-id="9e9c9-128">In Terminal, attempt to install the driver.</span></span> <span data-ttu-id="9e9c9-129">Beim folgenden Vorgang wird ein Fehler ausgeführt, da die Kernelerweiterung nicht für die Ausführung auf dem Gerät genehmigt wurde.</span><span class="sxs-lookup"><span data-stu-id="9e9c9-129">The following operation will fail, because the kernel extension wasn't approved to run on the device.</span></span> <span data-ttu-id="9e9c9-130">Der Genehmigungsfluss wird jedoch erneut ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="9e9c9-130">However, it will trigger the approval flow again.</span></span>

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```
    
    ```Output
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Diagnostics for /Library/Extensions/wdavkext.kext:
    ```

2. <span data-ttu-id="9e9c9-131">Öffnen **Sie Systemeinstellungen**  >  **Sicherheit & Datenschutz im** Menü.</span><span class="sxs-lookup"><span data-stu-id="9e9c9-131">Open **System Preferences** > **Security & Privacy** from the menu.</span></span> <span data-ttu-id="9e9c9-132">(Schließen Sie es zuerst, wenn es geöffnet ist.)</span><span class="sxs-lookup"><span data-stu-id="9e9c9-132">(Close it first, if it's opened.)</span></span>

3. <span data-ttu-id="9e9c9-133">**Zulassen** von Systemsoftware von Entwicklern "Microsoft Corporation"</span><span class="sxs-lookup"><span data-stu-id="9e9c9-133">**Allow** system software from developers "Microsoft Corporation"</span></span>

4. <span data-ttu-id="9e9c9-134">Installieren Sie im Terminal den Treiber erneut.</span><span class="sxs-lookup"><span data-stu-id="9e9c9-134">In Terminal, install the driver again.</span></span> <span data-ttu-id="9e9c9-135">Dieses Mal wird der Vorgang erfolgreich sein:</span><span class="sxs-lookup"><span data-stu-id="9e9c9-135">This time the operation will succeed:</span></span>

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```

    <span data-ttu-id="9e9c9-136">Das Banner sollte aus der Defender-Anwendung verschwinden und nun melden, dass der Echtzeitschutz aktiviert und ```mdatp health``` verfügbar ist:</span><span class="sxs-lookup"><span data-stu-id="9e9c9-136">The banner should disappear from the Defender application, and ```mdatp health``` should now report that real-time protection is both enabled and available:</span></span>

    ```bash
    mdatp health
    ```

    ```Output
    ...
    real_time_protection_enabled                : true
    real_time_protection_available              : true
    ...
    ```
