---
title: Behandeln von Problemen mit der Cloudverbindung für Microsoft Defender ATP für Linux
ms.reviewer: ''
description: Behandeln von Problemen mit der Cloudverbindung für Microsoft Defender ATP für Linux
keywords: microsoft, defender, atp, linux, cloud, connectivity, communication
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
ms.openlocfilehash: 77ab7bbbb156165f26538cf3d14eae1e5e76d92c
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587539"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="c99c7-104">Behandeln von Problemen mit der Cloudverbindung für Microsoft Defender for Endpoint für Linux</span><span class="sxs-lookup"><span data-stu-id="c99c7-104">Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c99c7-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c99c7-105">**Applies to:**</span></span>
- [<span data-ttu-id="c99c7-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="c99c7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c99c7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c99c7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c99c7-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="c99c7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c99c7-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="c99c7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="run-the-connectivity-test"></a><span data-ttu-id="c99c7-110">Ausführen des Konnektivitätstests</span><span class="sxs-lookup"><span data-stu-id="c99c7-110">Run the connectivity test</span></span>

<span data-ttu-id="c99c7-111">Um zu testen, ob Defender for Endpoint für Linux mit den aktuellen Netzwerkeinstellungen mit der Cloud kommunizieren kann, führen Sie einen Verbindungstest über die Befehlszeile aus:</span><span class="sxs-lookup"><span data-stu-id="c99c7-111">To test if Defender for Endpoint for Linux can communicate to the cloud with the current network settings, run a connectivity test from the command line:</span></span>

```bash
mdatp connectivity test
```

<span data-ttu-id="c99c7-112">Erwartete Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="c99c7-112">expected output:</span></span>

```output
Testing connection with https://cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://eu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://wu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://x.cp.wd.microsoft.com/api/report ... [OK]
Testing connection with https://winatp-gw-cus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-eus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-weu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-neu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-ukw.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-uks.microsoft.com/test ... [OK]
Testing connection with https://eu-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://us-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://uk-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://v20.events.data.microsoft.com/ping ... [OK]
```

<span data-ttu-id="c99c7-113">Wenn der [Konnektivitätstest](microsoft-defender-endpoint-linux.md#network-connections) fehlschlägt, überprüfen Sie, ob das Gerät über Internetzugriff verfügt und ob einer der vom Produkt benötigten Endpunkte von einem Proxy oder einer Firewall blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="c99c7-113">If the connectivity test fails, check if the device has Internet access and if [any of the endpoints required by the product](microsoft-defender-endpoint-linux.md#network-connections) are blocked by a proxy or firewall.</span></span>

<span data-ttu-id="c99c7-114">Fehler mit dem Lockenfehler 35 oder 60 geben die Ablehnung des Anheftens des Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="c99c7-114">Failures with curl error 35 or 60, indicate certificate pinning rejection.</span></span> <span data-ttu-id="c99c7-115">Überprüfen Sie, ob die Verbindung unter SSL- oder HTTPS-Prüfung steht.</span><span class="sxs-lookup"><span data-stu-id="c99c7-115">Please check if the connection is under SSL or HTTPS inspection.</span></span> <span data-ttu-id="c99c7-116">Wenn ja, fügen Sie Microsoft Defender for Endpoint der Liste der zulässigen Daten hinzu.</span><span class="sxs-lookup"><span data-stu-id="c99c7-116">If so, add Microsoft Defender for Endpoint to the allow list.</span></span>

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-transparent-proxy"></a><span data-ttu-id="c99c7-117">Problembehandlung bei Umgebungen ohne Proxy oder mit transparentem Proxy</span><span class="sxs-lookup"><span data-stu-id="c99c7-117">Troubleshooting steps for environments without proxy or with transparent proxy</span></span>

<span data-ttu-id="c99c7-118">Führen Sie den folgenden Befehl im Terminal aus, um zu testen, ob eine Verbindung in einer Umgebung ohne Proxy oder mit einem transparenten Proxy nicht blockiert ist:</span><span class="sxs-lookup"><span data-stu-id="c99c7-118">To test that a connection is not blocked in an environment without a proxy or with a transparent proxy, run the following command in the terminal:</span></span>

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="c99c7-119">Die Ausgabe dieses Befehls sollte wie die folgenden sein:</span><span class="sxs-lookup"><span data-stu-id="c99c7-119">The output from this command should be similar to:</span></span>

```Output
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```

## <a name="troubleshooting-steps-for-environments-with-static-proxy"></a><span data-ttu-id="c99c7-120">Problembehandlung bei Umgebungen mit statischem Proxy</span><span class="sxs-lookup"><span data-stu-id="c99c7-120">Troubleshooting steps for environments with static proxy</span></span>

> [!WARNING]
> <span data-ttu-id="c99c7-121">PAC-, WPAD- und authentifizierte Proxys werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c99c7-121">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="c99c7-122">Stellen Sie sicher, dass nur ein statischer oder transparenter Proxy verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c99c7-122">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="c99c7-123">Ssl-Überprüfung und Abfangen von Proxys werden aus Sicherheitsgründen ebenfalls nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c99c7-123">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="c99c7-124">Konfigurieren Sie eine Ausnahme für die SSL-Überprüfung und Ihren Proxyserver, um Daten von Defender for Endpoint für Linux direkt an die relevanten URLs ohne Abfangen zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="c99c7-124">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint for Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="c99c7-125">Wenn Sie Ihr Abfangzertifikat zum globalen Speicher hinzufügen, ist das Abfangen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="c99c7-125">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="c99c7-126">Wenn ein statischer Proxy erforderlich ist, fügen Sie dem obigen Befehl einen Proxyparameter hinzu, der der Proxyadresse und dem Port `proxy_address:port` entspricht:</span><span class="sxs-lookup"><span data-stu-id="c99c7-126">If a static proxy is required, add a proxy parameter to the above command, where `proxy_address:port` correspond to the proxy address and port:</span></span>

```bash
curl -x http://proxy_address:port -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="c99c7-127">Stellen Sie sicher, dass Sie dieselbe Proxyadresse und denselben Port wie in der Datei `/lib/system/system/mdatp.service` konfiguriert verwenden.</span><span class="sxs-lookup"><span data-stu-id="c99c7-127">Ensure that you use the same proxy address and port as configured in the `/lib/system/system/mdatp.service` file.</span></span> <span data-ttu-id="c99c7-128">Überprüfen Sie die Proxykonfiguration, wenn fehler aus den obigen Befehlen auftreten.</span><span class="sxs-lookup"><span data-stu-id="c99c7-128">Check your proxy configuration if there are errors from the above commands.</span></span>

> [!WARNING]
> <span data-ttu-id="c99c7-129">Der statische Proxy kann nicht über eine systemweite `HTTPS_PROXY` Umgebungsvariable konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="c99c7-129">The static proxy cannot be configured through a system-wide `HTTPS_PROXY` environment variable.</span></span> <span data-ttu-id="c99c7-130">Stellen Sie stattdessen sicher, `HTTPS_PROXY` dass dies ordnungsgemäß in der Datei festgelegt `/lib/system/system/mdatp.service` ist.</span><span class="sxs-lookup"><span data-stu-id="c99c7-130">Instead, ensure that `HTTPS_PROXY` is properly set in the `/lib/system/system/mdatp.service` file.</span></span>

<span data-ttu-id="c99c7-131">Um einen statischen Proxy verwenden zu können, `mdatp.service` muss die Datei geändert werden.</span><span class="sxs-lookup"><span data-stu-id="c99c7-131">To use a static proxy, the `mdatp.service` file must be modified.</span></span> <span data-ttu-id="c99c7-132">Stellen Sie sicher, dass `#` der Vorschub entfernt wird, um die Auskommentierung der folgenden Zeile aus zu `/lib/systemd/system/mdatp.service` entfernen:</span><span class="sxs-lookup"><span data-stu-id="c99c7-132">Ensure the leading `#` is removed to uncomment the following line from `/lib/systemd/system/mdatp.service`:</span></span>

```bash
#Environment="HTTPS_PROXY=http://address:port"
```

<span data-ttu-id="c99c7-133">Stellen Sie außerdem sicher, dass die richtige statische Proxyadresse ausgefüllt wird, um zu `address:port` ersetzen.</span><span class="sxs-lookup"><span data-stu-id="c99c7-133">Also ensure that the correct static proxy address is filled in to replace `address:port`.</span></span>

<span data-ttu-id="c99c7-134">Wenn diese Datei richtig ist, führen Sie den folgenden Befehl im Terminal aus, um Defender for Endpoint für Linux neu zu laden und die Einstellung weiterzuververmehren:</span><span class="sxs-lookup"><span data-stu-id="c99c7-134">If this file is correct, try running the following command in the terminal to reload Defender for Endpoint for Linux and propagate the setting:</span></span>

```bash
sudo systemctl daemon-reload; sudo systemctl restart mdatp
```

<span data-ttu-id="c99c7-135">Versuchen Sie nach erfolgreichem Erfolg einen weiteren Konnektivitätstest über die Befehlszeile:</span><span class="sxs-lookup"><span data-stu-id="c99c7-135">Upon success, attempt another connectivity test from the command line:</span></span>

```bash
mdatp connectivity test
```

<span data-ttu-id="c99c7-136">Wenn das Problem weiterhin besteht, wenden Sie sich an den Kundensupport.</span><span class="sxs-lookup"><span data-stu-id="c99c7-136">If the problem persists, contact customer support.</span></span>

## <a name="resources"></a><span data-ttu-id="c99c7-137">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="c99c7-137">Resources</span></span>

- <span data-ttu-id="c99c7-138">Weitere Informationen zum Konfigurieren des Produkts für die Verwendung eines statischen Proxys finden Sie unter [Configure Microsoft Defender for Endpoint for static proxy discovery](linux-static-proxy-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="c99c7-138">For more information about how to configure the product to use a static proxy, see [Configure Microsoft Defender for Endpoint for static proxy discovery](linux-static-proxy-configuration.md).</span></span>
