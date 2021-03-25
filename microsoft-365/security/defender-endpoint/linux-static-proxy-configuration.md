---
title: Statische Proxyermittlung von Microsoft Defender ATP für Linux
ms.reviewer: ''
description: Beschreibt, wie Sie Microsoft Defender ATP für die statische Proxyermittlung konfigurieren.
keywords: microsoft, defender, atp, linux, installation, proxy
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
ms.openlocfilehash: 461c728f6b61aa407d76e3674ba3339027c21a25
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187457"
---
# <a name="configure-microsoft-defender-for-endpoint-for-linux-for-static-proxy-discovery"></a><span data-ttu-id="4e354-104">Konfigurieren von Microsoft Defender for Endpoint für Linux für die statische Proxyermittlung</span><span class="sxs-lookup"><span data-stu-id="4e354-104">Configure Microsoft Defender for Endpoint for Linux for static proxy discovery</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4e354-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="4e354-105">**Applies to:**</span></span>
- [<span data-ttu-id="4e354-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="4e354-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4e354-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4e354-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4e354-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="4e354-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4e354-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="4e354-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="4e354-110">Microsoft Defender ATP kann einen Proxyserver mithilfe der ```HTTPS_PROXY``` Umgebungsvariablen ermitteln.</span><span class="sxs-lookup"><span data-stu-id="4e354-110">Microsoft Defender ATP can discover a proxy server using the ```HTTPS_PROXY``` environment variable.</span></span> <span data-ttu-id="4e354-111">Diese Einstellung muss sowohl **bei** der Installation als auch nach der Installation des Produkts konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="4e354-111">This setting must be configured **both** at installation time and after the product has been installed.</span></span>

## <a name="installation-time-configuration"></a><span data-ttu-id="4e354-112">Konfiguration der Installationszeit</span><span class="sxs-lookup"><span data-stu-id="4e354-112">Installation time configuration</span></span>

<span data-ttu-id="4e354-113">Während der Installation muss ```HTTPS_PROXY``` die Umgebungsvariable an den Paket-Manager übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="4e354-113">During installation, the ```HTTPS_PROXY``` environment variable must be passed to the package manager.</span></span> <span data-ttu-id="4e354-114">Der Paket-Manager kann diese Variable auf eine der folgenden Arten lesen:</span><span class="sxs-lookup"><span data-stu-id="4e354-114">The package manager can read this variable in any of the following ways:</span></span>

- <span data-ttu-id="4e354-115">Die ```HTTPS_PROXY``` Variable wird in der folgenden Zeile ```/etc/environment``` definiert:</span><span class="sxs-lookup"><span data-stu-id="4e354-115">The ```HTTPS_PROXY``` variable is defined in ```/etc/environment``` with the following line:</span></span>

    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

- <span data-ttu-id="4e354-116">Die `HTTPS_PROXY` Variable wird in der globalen Konfiguration des Paket-Managers definiert.</span><span class="sxs-lookup"><span data-stu-id="4e354-116">The `HTTPS_PROXY` variable is defined in the package manager global configuration.</span></span> <span data-ttu-id="4e354-117">In Ubuntu 18.04 können Sie beispielsweise die folgende Zeile `/etc/apt/apt.conf.d/proxy.conf` hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="4e354-117">For example, in Ubuntu 18.04, you can add the following line to `/etc/apt/apt.conf.d/proxy.conf`:</span></span>
  
    ```bash
    Acquire::https::Proxy "http://proxy.server:port/";
    ```

    > [!CAUTION]
    > <span data-ttu-id="4e354-118">Beachten Sie, dass über zwei Methoden den Proxy definieren können, der für andere Anwendungen auf Ihrem System verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4e354-118">Note that above two methods could define the proxy to use for other applications on your system.</span></span> <span data-ttu-id="4e354-119">Verwenden Sie diese Methode mit Vorsicht oder nur, wenn dies eine allgemein globale Konfiguration sein soll.</span><span class="sxs-lookup"><span data-stu-id="4e354-119">Use this method with caution, or only if this is meant to be a generally global configuration.</span></span>
  
- <span data-ttu-id="4e354-120">Die Variable wird für die Installations- oder `HTTPS_PROXY` Deinstallationsbefehle vorab verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e354-120">The `HTTPS_PROXY` variable is prepended to the installation or uninstallation commands.</span></span> <span data-ttu-id="4e354-121">Verwenden Sie beispielsweise den APT-Paket-Manager, um die Variable beim Installieren von Microsoft Defender for Endpoint wie folgt voran zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="4e354-121">For example, with the APT package manager, prepend the variable as follows when installing Microsoft Defender for Endpoint:</span></span> 

    ```bash  
    HTTPS_PROXY="http://proxy.server:port/" apt install mdatp
    ```

    > [!NOTE]
    > <span data-ttu-id="4e354-122">Fügen Sie nicht sudo zwischen der Umgebungsvariablendefinition und apt hinzu, andernfalls wird die Variable nicht verbreitet.</span><span class="sxs-lookup"><span data-stu-id="4e354-122">Do not add sudo between the environment variable definition and apt, otherwise the variable will not be propagated.</span></span>

<span data-ttu-id="4e354-123">Die `HTTPS_PROXY` Umgebungsvariable kann auch während der Deinstallation definiert werden.</span><span class="sxs-lookup"><span data-stu-id="4e354-123">The `HTTPS_PROXY` environment variable may similarly be defined during uninstallation.</span></span>

<span data-ttu-id="4e354-124">Beachten Sie, dass die Installation und Deinstallation nicht unbedingt fehlschlagen, wenn ein Proxy erforderlich, aber nicht konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="4e354-124">Note that installation and uninstallation will not necessarily fail if a proxy is required but not configured.</span></span> <span data-ttu-id="4e354-125">Telemetrie wird jedoch nicht übermittelt, und der Vorgang kann aufgrund von Netzwerktimeouts viel länger dauern.</span><span class="sxs-lookup"><span data-stu-id="4e354-125">However, telemetry will not be submitted, and the operation could take much longer due to network timeouts.</span></span>

## <a name="post-installation-configuration"></a><span data-ttu-id="4e354-126">Konfiguration nach der Installation</span><span class="sxs-lookup"><span data-stu-id="4e354-126">Post installation configuration</span></span>
  
<span data-ttu-id="4e354-127">Nach der Installation muss `HTTPS_PROXY` die Umgebungsvariable in der Defender for Endpoint-Dienstdatei definiert werden.</span><span class="sxs-lookup"><span data-stu-id="4e354-127">After installation, the `HTTPS_PROXY` environment variable must be defined in the Defender for Endpoint service file.</span></span> <span data-ttu-id="4e354-128">Öffnen Sie dazu `/lib/systemd/system/mdatp.service` in einem Texteditor, während Sie als Stammbenutzer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4e354-128">To do this, open `/lib/systemd/system/mdatp.service` in a text editor while running as the root user.</span></span> <span data-ttu-id="4e354-129">Anschließend können Sie die Variable auf zwei Arten an den Dienst weitervermehren:</span><span class="sxs-lookup"><span data-stu-id="4e354-129">You can then propagate the variable to the service in one of two ways:</span></span>

- <span data-ttu-id="4e354-130">Legen Sie die Auskommentierung der Zeile `#Environment="HTTPS_PROXY=http://address:port"` auf, und geben Sie Ihre statische Proxyadresse an.</span><span class="sxs-lookup"><span data-stu-id="4e354-130">Uncomment the line `#Environment="HTTPS_PROXY=http://address:port"` and specify your static proxy address.</span></span>

- <span data-ttu-id="4e354-131">Fügen Sie eine Zeile `EnvironmentFile=/path/to/env/file` hinzu.</span><span class="sxs-lookup"><span data-stu-id="4e354-131">Add a line `EnvironmentFile=/path/to/env/file`.</span></span> <span data-ttu-id="4e354-132">Dieser Pfad kann auf eine oder eine benutzerdefinierte Datei verweisen, die `/etc/environment` die folgende Zeile hinzufügen muss:</span><span class="sxs-lookup"><span data-stu-id="4e354-132">This path can point to `/etc/environment` or a custom file, either of which needs to add the following line:</span></span>
  
    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

<span data-ttu-id="4e354-133">Nachdem Sie die `mdatp.service` Datei geändert haben, speichern und schließen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="4e354-133">After modifying the `mdatp.service` file, save and close it.</span></span> <span data-ttu-id="4e354-134">Starten Sie den Dienst neu, damit die Änderungen angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="4e354-134">Restart the service so the changes can be applied.</span></span> <span data-ttu-id="4e354-135">In Ubuntu umfasst dies zwei Befehle:</span><span class="sxs-lookup"><span data-stu-id="4e354-135">In Ubuntu, this involves two commands:</span></span>  

```bash
systemctl daemon-reload; systemctl restart mdatp
```
