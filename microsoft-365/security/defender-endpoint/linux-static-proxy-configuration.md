---
title: Microsoft Defender für Endpunkt unter Linux – Ermittlung statischer Proxys
ms.reviewer: ''
description: Beschreibt, wie Microsoft Defender für Endpunkt unter Linux für statische Proxyermittlung konfiguriert wird.
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, Linux, Installation, Proxy
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5a8e1cbda5f4361532c7fac0892be7ffe72f64ca
ms.sourcegitcommit: 8b79d276f71f22bcaeb150e78e35101cb1ae0375
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53114731"
---
# <a name="configure-microsoft-defender-for-endpoint-on-linux-for-static-proxy-discovery"></a><span data-ttu-id="79f91-104">Konfigurieren von Microsoft Defender für Endpunkt unter Linux für die Ermittlung statischer Proxys</span><span class="sxs-lookup"><span data-stu-id="79f91-104">Configure Microsoft Defender for Endpoint on Linux for static proxy discovery</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="79f91-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="79f91-105">**Applies to:**</span></span>
- [<span data-ttu-id="79f91-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="79f91-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="79f91-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="79f91-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="79f91-108">Möchten Sie Defender für Endpunkt erfahren?</span><span class="sxs-lookup"><span data-stu-id="79f91-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="79f91-109">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="79f91-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="79f91-110">Microsoft Defender für Endpunkt kann einen Proxyserver mithilfe der `HTTPS_PROXY` Umgebungsvariablen ermitteln.</span><span class="sxs-lookup"><span data-stu-id="79f91-110">Microsoft Defender for Endpoint can discover a proxy server using the `HTTPS_PROXY` environment variable.</span></span> <span data-ttu-id="79f91-111">Diese Einstellung muss **sowohl** zur Installationszeit als auch nach der Installation des Produkts konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="79f91-111">This setting must be configured **both** at installation time and after the product has been installed.</span></span>

## <a name="installation-time-configuration"></a><span data-ttu-id="79f91-112">Konfiguration der Installationszeit</span><span class="sxs-lookup"><span data-stu-id="79f91-112">Installation time configuration</span></span>

<span data-ttu-id="79f91-113">Während der Installation muss die `HTTPS_PROXY` Umgebungsvariable an den Paket-Manager übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="79f91-113">During installation, the `HTTPS_PROXY` environment variable must be passed to the package manager.</span></span> <span data-ttu-id="79f91-114">Der Paket-Manager kann diese Variable auf eine der folgenden Arten lesen:</span><span class="sxs-lookup"><span data-stu-id="79f91-114">The package manager can read this variable in any of the following ways:</span></span>

- <span data-ttu-id="79f91-115">Die `HTTPS_PROXY` Variable wird in der folgenden Zeile `/etc/environment` definiert:</span><span class="sxs-lookup"><span data-stu-id="79f91-115">The `HTTPS_PROXY` variable is defined in `/etc/environment` with the following line:</span></span>

  ```bash
  HTTPS_PROXY="http://proxy.server:port/"
  ```

- <span data-ttu-id="79f91-116">Die `HTTPS_PROXY` Variable wird in der globalen Paket-Manager-Konfiguration definiert.</span><span class="sxs-lookup"><span data-stu-id="79f91-116">The `HTTPS_PROXY` variable is defined in the package manager global configuration.</span></span> <span data-ttu-id="79f91-117">In Ubuntu 18.04 können Sie beispielsweise die folgende Zeile hinzufügen `/etc/apt/apt.conf.d/proxy.conf` zu:</span><span class="sxs-lookup"><span data-stu-id="79f91-117">For example, in Ubuntu 18.04, you can add the following line to `/etc/apt/apt.conf.d/proxy.conf`:</span></span>
  
  ```bash
  Acquire::https::Proxy "http://proxy.server:port/";
  ```

  > [!CAUTION]
  > <span data-ttu-id="79f91-118">Beachten Sie, dass oben zwei Methoden den Proxy definieren können, der für andere Anwendungen auf Ihrem System verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="79f91-118">Note that above two methods could define the proxy to use for other applications on your system.</span></span> <span data-ttu-id="79f91-119">Verwenden Sie diese Methode mit Vorsicht oder nur, wenn dies eine allgemeine globale Konfiguration sein soll.</span><span class="sxs-lookup"><span data-stu-id="79f91-119">Use this method with caution, or only if this is meant to be a generally global configuration.</span></span>
  
- <span data-ttu-id="79f91-120">Die `HTTPS_PROXY` Variable wird den Installations- oder Deinstallationsbefehlen vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="79f91-120">The `HTTPS_PROXY` variable is prepended to the installation or uninstallation commands.</span></span> <span data-ttu-id="79f91-121">Stellen Sie beispielsweise mit dem APT-Paket-Manager die Variable bei der Installation von Microsoft Defender für Endpunkt wie folgt voran:</span><span class="sxs-lookup"><span data-stu-id="79f91-121">For example, with the APT package manager, prepend the variable as follows when installing Microsoft Defender for Endpoint:</span></span> 

  ```bash  
  HTTPS_PROXY="http://proxy.server:port/" apt install mdatp
  ```

  > [!NOTE]
  > <span data-ttu-id="79f91-122">Fügen Sie kein Sudo zwischen der Umgebungsvariablendefinition und apt hinzu, andernfalls wird die Variable nicht weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="79f91-122">Do not add sudo between the environment variable definition and apt, otherwise the variable will not be propagated.</span></span>

<span data-ttu-id="79f91-123">Die `HTTPS_PROXY` Umgebungsvariable kann während der Deinstallation auf ähnliche Weise definiert werden.</span><span class="sxs-lookup"><span data-stu-id="79f91-123">The `HTTPS_PROXY` environment variable may similarly be defined during uninstallation.</span></span>

<span data-ttu-id="79f91-124">Beachten Sie, dass installation and uninstallation not necessarily fail if a proxy is required but not configured.</span><span class="sxs-lookup"><span data-stu-id="79f91-124">Note that installation and uninstallation will not necessarily fail if a proxy is required but not configured.</span></span> <span data-ttu-id="79f91-125">Telemetriedaten werden jedoch nicht übermittelt, und der Vorgang kann aufgrund von Netzwerktimeouts viel länger dauern.</span><span class="sxs-lookup"><span data-stu-id="79f91-125">However, telemetry will not be submitted, and the operation could take much longer due to network timeouts.</span></span>

## <a name="post-installation-configuration"></a><span data-ttu-id="79f91-126">Konfiguration nach der Installation</span><span class="sxs-lookup"><span data-stu-id="79f91-126">Post installation configuration</span></span>
  
<span data-ttu-id="79f91-127">Nach der Installation muss die `HTTPS_PROXY` Umgebungsvariable in der Defender für Endpunkt-Dienstdatei definiert werden.</span><span class="sxs-lookup"><span data-stu-id="79f91-127">After installation, the `HTTPS_PROXY` environment variable must be defined in the Defender for Endpoint service file.</span></span> <span data-ttu-id="79f91-128">Öffnen Sie dazu `/lib/systemd/system/mdatp.service` in einem Text-Editor, während Sie als Stammbenutzer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="79f91-128">To do this, open `/lib/systemd/system/mdatp.service` in a text editor while running as the root user.</span></span> <span data-ttu-id="79f91-129">Anschließend können Sie die Variable auf eine von zwei Arten an den Dienst überweisen:</span><span class="sxs-lookup"><span data-stu-id="79f91-129">You can then propagate the variable to the service in one of two ways:</span></span>

> [!NOTE]
> <span data-ttu-id="79f91-130">On CentOS or RedHat Linux distributions the location of the Endpoint service file is `/usr/lib/systemd/system/mdatp.service` .</span><span class="sxs-lookup"><span data-stu-id="79f91-130">On CentOS or RedHat Linux distributions the location of the Endpoint service file is `/usr/lib/systemd/system/mdatp.service`.</span></span>

- <span data-ttu-id="79f91-131">Kommentieren Sie die Zeile `#Environment="HTTPS_PROXY=http://address:port"` aus, und geben Sie Ihre statische Proxyadresse an.</span><span class="sxs-lookup"><span data-stu-id="79f91-131">Uncomment the line `#Environment="HTTPS_PROXY=http://address:port"` and specify your static proxy address.</span></span>

- <span data-ttu-id="79f91-132">Fügen Sie eine Zeile `EnvironmentFile=/path/to/env/file` hinzu.</span><span class="sxs-lookup"><span data-stu-id="79f91-132">Add a line `EnvironmentFile=/path/to/env/file`.</span></span> <span data-ttu-id="79f91-133">Dieser Pfad kann auf `/etc/environment` eine oder eine benutzerdefinierte Datei verweisen, von der eine die folgende Zeile hinzufügen muss:</span><span class="sxs-lookup"><span data-stu-id="79f91-133">This path can point to `/etc/environment` or a custom file, either of which needs to add the following line:</span></span>
  
  ```bash
  HTTPS_PROXY="http://proxy.server:port/"
  ```

<span data-ttu-id="79f91-134">Speichern und schließen Sie die Datei, nachdem Sie die Datei geändert `mdatp.service` haben.</span><span class="sxs-lookup"><span data-stu-id="79f91-134">After modifying the `mdatp.service` file, save and close it.</span></span> <span data-ttu-id="79f91-135">Starten Sie den Dienst neu, damit die Änderungen übernommen werden können.</span><span class="sxs-lookup"><span data-stu-id="79f91-135">Restart the service so the changes can be applied.</span></span> <span data-ttu-id="79f91-136">In Ubuntu umfasst dies zwei Befehle:</span><span class="sxs-lookup"><span data-stu-id="79f91-136">In Ubuntu, this involves two commands:</span></span>  

```bash
systemctl daemon-reload; systemctl restart mdatp
```
