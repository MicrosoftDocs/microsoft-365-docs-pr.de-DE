---
title: Behandeln von Problemen mit der Cloudverbindung für Microsoft Defender for Endpoint unter macOS
description: In diesem Thema wird beschrieben, wie Sie Probleme mit der Cloudverbindung für Microsoft Defender for Endpoint unter macOS behandeln.
keywords: microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: fbe9d0006a2f1779e1bad60dc283a5a40429dbdd
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51750016"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="ee94b-104">Behandeln von Problemen mit der Cloudverbindung für Microsoft Defender for Endpoint unter macOS</span><span class="sxs-lookup"><span data-stu-id="ee94b-104">Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ee94b-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="ee94b-105">**Applies to:**</span></span>
- [<span data-ttu-id="ee94b-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="ee94b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ee94b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ee94b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="ee94b-108">**Plattform** macOS</span><span class="sxs-lookup"><span data-stu-id="ee94b-108">**Platform** macOS</span></span>

<span data-ttu-id="ee94b-109">In diesem Thema wird beschrieben, wie Sie Probleme mit der Cloudkonnektivität für Microsoft Defender for Endpoint unter macOS behandeln.</span><span class="sxs-lookup"><span data-stu-id="ee94b-109">This topic describes how to Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on macOS.</span></span>

## <a name="run-the-connectivity-test"></a><span data-ttu-id="ee94b-110">Ausführen des Konnektivitätstests</span><span class="sxs-lookup"><span data-stu-id="ee94b-110">Run the connectivity test</span></span>
<span data-ttu-id="ee94b-111">Um zu testen, ob Defender for Endpoint auf Dem Mac mit den aktuellen Netzwerkeinstellungen mit der Cloud kommunizieren kann, führen Sie einen Verbindungstest über die Befehlszeile aus:</span><span class="sxs-lookup"><span data-stu-id="ee94b-111">To test if Defender for Endpoint on Mac can communicate to the cloud with the current network settings, run a connectivity test from the command line:</span></span>

```Bash
mdatp connectivity test
```

<span data-ttu-id="ee94b-112">Erwartete Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="ee94b-112">expected output:</span></span>
```Bash
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

<span data-ttu-id="ee94b-113">Wenn der [Konnektivitätstest](microsoft-defender-endpoint-mac.md#network-connections) fehlschlägt, überprüfen Sie, ob das Gerät über Internetzugriff verfügt und ob einer der vom Produkt benötigten Endpunkte von einem Proxy oder einer Firewall blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="ee94b-113">If the connectivity test fails, check if the device has Internet access and if [any of the endpoints required by the product](microsoft-defender-endpoint-mac.md#network-connections) are blocked by a proxy or firewall.</span></span>

<span data-ttu-id="ee94b-114">Fehler mit dem Lockenfehler 35 oder 60 deuten auf die Ablehnung des Anheftens von Zertifikaten hin, was auf ein potenzielles Problem bei der SSL- oder HTTPS-Überprüfung hinweist.</span><span class="sxs-lookup"><span data-stu-id="ee94b-114">Failures with curl error 35 or 60 indicate certificate pinning rejection, which indicates a potential issue with SSL or HTTPS inspection.</span></span> <span data-ttu-id="ee94b-115">Weitere Informationen finden Sie unter Anweisungen zur KONFIGURATION der SSL-Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="ee94b-115">See instructions below regarding SSL inspection configuration.</span></span>

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-proxy-autoconfig-pac-or-with-web-proxy-autodiscovery-protocol-wpad"></a><span data-ttu-id="ee94b-116">Problembehandlung bei Umgebungen ohne Proxy oder mit Proxy autoconfig (PAC) oder mit Web Proxy AutoDiscovery Protocol (WPAD)</span><span class="sxs-lookup"><span data-stu-id="ee94b-116">Troubleshooting steps for environments without proxy or with Proxy autoconfig (PAC) or with Web Proxy Autodiscovery Protocol (WPAD)</span></span>
<span data-ttu-id="ee94b-117">Verwenden Sie das folgende Verfahren, um zu testen, ob eine Verbindung in einer Umgebung ohne Proxy oder mit Proxy autoconfig (PAC) oder mit Web Proxy AutoDiscovery Protocol (WPAD) nicht blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="ee94b-117">Use the following procedure to test that a connection is not blocked in an environment without a proxy or with Proxy autoconfig (PAC) or with Web Proxy Autodiscovery Protocol (WPAD).</span></span>

<span data-ttu-id="ee94b-118">Wenn ein Proxy oder eine Firewall anonymen Datenverkehr blockiert, stellen Sie sicher, dass anonymer Datenverkehr in den zuvor aufgeführten URLs zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="ee94b-118">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span>

> [!WARNING]
> <span data-ttu-id="ee94b-119">Authentifizierte Proxys werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ee94b-119">Authenticated proxies are not supported.</span></span> <span data-ttu-id="ee94b-120">Stellen Sie sicher, dass nur PAC, WPAD oder ein statischer Proxy verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ee94b-120">Ensure that only PAC, WPAD, or a static proxy is being used.</span></span> <span data-ttu-id="ee94b-121">Ssl-Überprüfung und Abfangen von Proxys werden aus Sicherheitsgründen ebenfalls nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ee94b-121">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="ee94b-122">Konfigurieren Sie eine Ausnahme für die SSL-Überprüfung und Ihren Proxyserver, um Daten von Microsoft Defender for Endpoint auf macOS direkt an die relevanten URLs ohne Abfangen zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="ee94b-122">Configure an exception for SSL inspection and your proxy server to directly pass through data from Microsoft Defender for Endpoint on macOS to the relevant URLs without interception.</span></span> <span data-ttu-id="ee94b-123">Wenn Sie Ihr Abfangzertifikat zum globalen Speicher hinzufügen, ist das Abfangen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="ee94b-123">Adding your interception certificate to the global store will not allow for interception.</span></span>
<span data-ttu-id="ee94b-124">So testen Sie, ob eine Verbindung nicht blockiert ist: In einem Browser wie Microsoft Edge für Mac oder Safari öffnen https://x.cp.wd.microsoft.com/api/report und https://cdn.x.cp.wd.microsoft.com/ping .</span><span class="sxs-lookup"><span data-stu-id="ee94b-124">To test that a connection is not blocked: In a browser such as Microsoft Edge for Mac or Safari open https://x.cp.wd.microsoft.com/api/report and https://cdn.x.cp.wd.microsoft.com/ping.</span></span>

<span data-ttu-id="ee94b-125">Führen Sie optional im Terminal den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="ee94b-125">Optionally, in Terminal, run the following command:</span></span>

```Bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping' 
```

<span data-ttu-id="ee94b-126">Die Ausgabe dieses Befehls sollte wie die folgenden sein:</span><span class="sxs-lookup"><span data-stu-id="ee94b-126">The output from this command should be similar to:</span></span>
```bash
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```
