---
title: Microsoft Defender ATP für Mac
ms.reviewer: ''
description: Erfahren Sie, wie Sie Microsoft Defender for Endpoint für Mac installieren, konfigurieren, aktualisieren und verwenden.
keywords: microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 6af8a6e0e23201f3c5861cb6a28b2bffa0f04ea4
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186437"
---
# <a name="microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="cb761-104">Microsoft Defender für Endpoint für Mac</span><span class="sxs-lookup"><span data-stu-id="cb761-104">Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cb761-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="cb761-105">**Applies to:**</span></span>
- [<span data-ttu-id="cb761-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="cb761-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cb761-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cb761-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="cb761-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="cb761-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cb761-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="cb761-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="cb761-110">In diesem Thema wird beschrieben, wie Sie Defender for Endpoint für Mac installieren, konfigurieren, aktualisieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="cb761-110">This topic describes how to install, configure, update, and use Defender for Endpoint for Mac.</span></span>

> [!CAUTION]
> <span data-ttu-id="cb761-111">Das Ausführen anderer Endpunktschutzprodukte von Drittanbietern zusammen mit Defender for Endpoint für Mac führt wahrscheinlich zu Leistungsproblemen und unvorhersehbaren Nebenwirkungen.</span><span class="sxs-lookup"><span data-stu-id="cb761-111">Running other third-party endpoint protection products alongside Defender for Endpoint for Mac is likely to lead to performance problems and unpredictable side effects.</span></span> <span data-ttu-id="cb761-112">Wenn in Ihrer Umgebung kein Microsoft-Endpunktschutz eine absolute Anforderung ist, können Sie weiterhin die MDATP für Mac EDR-Funktionalität nutzen, nachdem Sie die MDATP für Mac-Antivirenfunktionen für die Ausführung im passiven Modus konfiguriert [haben.](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="cb761-112">If non-Microsoft endpoint protection is an absolute requirement in your environment, you can still safely take advantage of MDATP for Mac EDR functionality after configuring MDATP for Mac antivirus functionality to run in [Passive mode](mac-preferences.md#enable--disable-passive-mode).</span></span>

## <a name="whats-new-in-the-latest-release"></a><span data-ttu-id="cb761-113">Neuigkeiten in der neuesten Version</span><span class="sxs-lookup"><span data-stu-id="cb761-113">What’s new in the latest release</span></span>

[<span data-ttu-id="cb761-114">Neues in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="cb761-114">What's new in Microsoft Defender for Endpoint</span></span>](whats-new-in-microsoft-defender-atp.md)

[<span data-ttu-id="cb761-115">Neues in Microsoft Defender for Endpoint für Mac</span><span class="sxs-lookup"><span data-stu-id="cb761-115">What's new in Microsoft Defender for Endpoint for Mac</span></span>](mac-whatsnew.md)

> [!TIP]
> <span data-ttu-id="cb761-116">Wenn Sie Feedback haben, das Sie freigeben möchten, übermitteln Sie es, indem Sie Microsoft Defender for Endpoint für Mac auf Ihrem Gerät öffnen und zu Hilfe senden feedback  >  **navigieren.**</span><span class="sxs-lookup"><span data-stu-id="cb761-116">If you have any feedback that you would like to share, submit it by opening Microsoft Defender for Endpoint for Mac on your device and navigating to **Help** > **Send feedback**.</span></span>

<span data-ttu-id="cb761-117">Um die neuesten Features, einschließlich Vorschaufunktionen (z. B. Endpunkterkennung und -antwort für Ihre Mac-Geräte), zu erhalten, konfigurieren Sie Ihr macOS-Gerät, auf dem Microsoft Defender for Endpoint ausgeführt wird, als "Insider"-Gerät.</span><span class="sxs-lookup"><span data-stu-id="cb761-117">To get the latest features, including preview capabilities (such as endpoint detection and response for your Mac devices), configure your macOS device running Microsoft Defender for Endpoint to be an "Insider" device.</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="cb761-118">Installieren von Microsoft Defender for Endpoint für Mac</span><span class="sxs-lookup"><span data-stu-id="cb761-118">How to install Microsoft Defender for Endpoint for Mac</span></span>

### <a name="prerequisites"></a><span data-ttu-id="cb761-119">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="cb761-119">Prerequisites</span></span>

- <span data-ttu-id="cb761-120">Ein Defender for Endpoint-Abonnement und Zugriff auf das Microsoft Defender Security Center-Portal</span><span class="sxs-lookup"><span data-stu-id="cb761-120">A Defender for Endpoint subscription and access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="cb761-121">Erfahrung auf Anfängerebene in macOS- und BASH-Skripting</span><span class="sxs-lookup"><span data-stu-id="cb761-121">Beginner-level experience in macOS and BASH scripting</span></span>
- <span data-ttu-id="cb761-122">Administratorrechte auf dem Gerät (bei manueller Bereitstellung)</span><span class="sxs-lookup"><span data-stu-id="cb761-122">Administrative privileges on the device (in case of manual deployment)</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="cb761-123">Installationsanweisungen</span><span class="sxs-lookup"><span data-stu-id="cb761-123">Installation instructions</span></span>

<span data-ttu-id="cb761-124">Es gibt mehrere Methoden und Bereitstellungstools, die Sie zum Installieren und Konfigurieren von Defender for Endpoint für Mac verwenden können.</span><span class="sxs-lookup"><span data-stu-id="cb761-124">There are several methods and deployment tools that you can use to install and configure Defender for Endpoint for Mac.</span></span>

- <span data-ttu-id="cb761-125">Verwaltungstools von Drittanbietern:</span><span class="sxs-lookup"><span data-stu-id="cb761-125">Third-party management tools:</span></span>
    - [<span data-ttu-id="cb761-126">Microsoft Intune-basierte Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="cb761-126">Microsoft Intune-based deployment</span></span>](mac-install-with-intune.md)
    - [<span data-ttu-id="cb761-127">JAMF-basierte Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="cb761-127">JAMF-based deployment</span></span>](mac-install-with-jamf.md)
    - [<span data-ttu-id="cb761-128">Andere MDM-Produkte</span><span class="sxs-lookup"><span data-stu-id="cb761-128">Other MDM products</span></span>](mac-install-with-other-mdm.md)

- <span data-ttu-id="cb761-129">Befehlszeilentool:</span><span class="sxs-lookup"><span data-stu-id="cb761-129">Command-line tool:</span></span>
    - [<span data-ttu-id="cb761-130">Manuelle Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="cb761-130">Manual deployment</span></span>](mac-install-manually.md)

### <a name="system-requirements"></a><span data-ttu-id="cb761-131">Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="cb761-131">System requirements</span></span>

<span data-ttu-id="cb761-132">Die drei neuesten Hauptversionen von macOS werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cb761-132">The three most recent major releases of macOS are supported.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb761-133">Unter macOS 11 (Big Sur) erfordert Microsoft Defender for Endpoint zusätzliche Konfigurationsprofile.</span><span class="sxs-lookup"><span data-stu-id="cb761-133">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="cb761-134">Wenn Sie ein vorhandenes Kunden-Upgrade von früheren Versionen von macOS sind, stellen Sie sicher, dass Sie die zusätzlichen Konfigurationsprofile bereitstellen, die unter Neue Konfigurationsprofile für [macOS Catalina](mac-sysext-policies.md)und neuere Versionen von macOS aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="cb761-134">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [New configuration profiles for macOS Catalina and newer versions of macOS](mac-sysext-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb761-135">Die Unterstützung für macOS 10.13 (High Sierra) wird am 15. Februar 2021 eingestellt.</span><span class="sxs-lookup"><span data-stu-id="cb761-135">Support for macOS 10.13 (High Sierra) will be discontinued on February 15th, 2021.</span></span>

- <span data-ttu-id="cb761-136">11 (Big Sur), 10,15 (Catalina), 10,14 (Mojave), 10,13 (High Sierra)</span><span class="sxs-lookup"><span data-stu-id="cb761-136">11 (Big Sur), 10.15 (Catalina), 10.14 (Mojave), 10.13 (High Sierra)</span></span>
- <span data-ttu-id="cb761-137">Speicherplatz: 1 GB</span><span class="sxs-lookup"><span data-stu-id="cb761-137">Disk space: 1GB</span></span>

<span data-ttu-id="cb761-138">Betaversionen von macOS werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cb761-138">Beta versions of macOS are not supported.</span></span>

<span data-ttu-id="cb761-139">Nachdem Sie den Dienst aktiviert haben, müssen Sie möglicherweise Ihr Netzwerk oder ihre Firewall so konfigurieren, dass ausgehende Verbindungen zwischen dem Dienst und Ihren Endpunkten zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="cb761-139">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="cb761-140">Lizenzierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="cb761-140">Licensing requirements</span></span>

<span data-ttu-id="cb761-141">Microsoft Defender für Endpoint für Mac erfordert eines der folgenden Microsoft Volumenlizenzangebote:</span><span class="sxs-lookup"><span data-stu-id="cb761-141">Microsoft Defender for Endpoint for Mac requires one of the following Microsoft Volume Licensing offers:</span></span>

- <span data-ttu-id="cb761-142">Microsoft 365 E5 (M365 E5)</span><span class="sxs-lookup"><span data-stu-id="cb761-142">Microsoft 365 E5 (M365 E5)</span></span>
- <span data-ttu-id="cb761-143">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="cb761-143">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="cb761-144">Microsoft 365 A5 (M365 A5)</span><span class="sxs-lookup"><span data-stu-id="cb761-144">Microsoft 365 A5 (M365 A5)</span></span>

> [!NOTE]
> <span data-ttu-id="cb761-145">Berechtigte lizenzierte Benutzer können Microsoft Defender for Endpoint auf bis zu fünf gleichzeitigen Geräten verwenden.</span><span class="sxs-lookup"><span data-stu-id="cb761-145">Eligible licensed users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span>
> <span data-ttu-id="cb761-146">Microsoft Defender for Endpoint steht auch bei einem Cloud Solution Provider (CSP) zum Kauf zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="cb761-146">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span> <span data-ttu-id="cb761-147">Wenn sie über einen CSP erworben werden, sind keine Microsoft Volumenlizenzangebote aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="cb761-147">When purchased via a CSP, it does not require Microsoft Volume Licensing offers listed.</span></span>

### <a name="network-connections"></a><span data-ttu-id="cb761-148">Netzwerkverbindungen</span><span class="sxs-lookup"><span data-stu-id="cb761-148">Network connections</span></span>

<span data-ttu-id="cb761-149">In der folgenden herunterladbaren Kalkulationstabelle sind die Dienste und die zugehörigen URLs aufgeführt, mit deren Netzwerk eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="cb761-149">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="cb761-150">Sie sollten sicherstellen, dass es keine Firewall- oder Netzwerkfilterregeln gibt, die den  Zugriff auf diese URLs verweigern würden, oder Sie müssen möglicherweise eine speziell für sie zulässige Regel erstellen.</span><span class="sxs-lookup"><span data-stu-id="cb761-150">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>



|<span data-ttu-id="cb761-151">**Tabellenkalkulation der Domänenliste**</span><span class="sxs-lookup"><span data-stu-id="cb761-151">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="cb761-152">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="cb761-152">**Description**</span></span>|
|:-----|:-----|
|![Thumb image for Microsoft Defender for Endpoint URLs spreadsheet](images/mdatp-urls.png)<br/>  | <span data-ttu-id="cb761-154">Tabellenkalkulation bestimmter DNS-Einträge für Dienststandorte, geografische Standorte und Betriebssysteme.</span><span class="sxs-lookup"><span data-stu-id="cb761-154">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br><span data-ttu-id="cb761-155">Laden Sie die Kalkulationstabelle [ hier herunter:mdatp-urls.xlsx](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx).</span><span class="sxs-lookup"><span data-stu-id="cb761-155">Download the spreadsheet here: [mdatp-urls.xlsx](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx).</span></span>

<span data-ttu-id="cb761-156">Microsoft Defender for Endpoint kann einen Proxyserver mithilfe der folgenden Ermittlungsmethoden ermitteln:</span><span class="sxs-lookup"><span data-stu-id="cb761-156">Microsoft Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="cb761-157">Proxy autoconfig (PAC)</span><span class="sxs-lookup"><span data-stu-id="cb761-157">Proxy autoconfig (PAC)</span></span>
- <span data-ttu-id="cb761-158">Webproxy-AutoErmittlungsprotokoll (WPAD)</span><span class="sxs-lookup"><span data-stu-id="cb761-158">Web Proxy Autodiscovery Protocol (WPAD)</span></span>
- <span data-ttu-id="cb761-159">Manuelle Konfiguration statischer Proxys</span><span class="sxs-lookup"><span data-stu-id="cb761-159">Manual static proxy configuration</span></span>

<span data-ttu-id="cb761-160">Wenn ein Proxy oder eine Firewall anonymen Datenverkehr blockiert, stellen Sie sicher, dass anonymer Datenverkehr in den zuvor aufgeführten URLs zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="cb761-160">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span>

> [!WARNING]
> <span data-ttu-id="cb761-161">Authentifizierte Proxys werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cb761-161">Authenticated proxies are not supported.</span></span> <span data-ttu-id="cb761-162">Stellen Sie sicher, dass nur PAC, WPAD oder ein statischer Proxy verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cb761-162">Ensure that only PAC, WPAD, or a static proxy is being used.</span></span>
>
> <span data-ttu-id="cb761-163">Ssl-Überprüfung und Abfangen von Proxys werden aus Sicherheitsgründen ebenfalls nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cb761-163">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="cb761-164">Konfigurieren Sie eine Ausnahme für die SSL-Überprüfung und Ihren Proxyserver, um Daten von Microsoft Defender for Endpoint für Mac direkt an die relevanten URLs ohne Abfangen zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="cb761-164">Configure an exception for SSL inspection and your proxy server to directly pass through data from Microsoft Defender for Endpoint for Mac to the relevant URLs without interception.</span></span> <span data-ttu-id="cb761-165">Wenn Sie Ihr Abfangzertifikat zum globalen Speicher hinzufügen, ist das Abfangen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="cb761-165">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="cb761-166">Öffnen Sie und in einem Browser, um zu testen, ob eine Verbindung [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) nicht blockiert ist.</span><span class="sxs-lookup"><span data-stu-id="cb761-166">To test that a connection is not blocked, open [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) and [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) in a browser.</span></span>

<span data-ttu-id="cb761-167">Wenn Sie die Befehlszeile bevorzugen, können Sie die Verbindung auch überprüfen, indem Sie den folgenden Befehl im Terminal ausführen:</span><span class="sxs-lookup"><span data-stu-id="cb761-167">If you prefer the command line, you can also check the connection by running the following command in Terminal:</span></span>

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="cb761-168">Die Ausgabe dieses Befehls sollte der folgenden ähneln:</span><span class="sxs-lookup"><span data-stu-id="cb761-168">The output from this command should be similar to the following:</span></span>

 `OK https://x.cp.wd.microsoft.com/api/report`

 `OK https://cdn.x.cp.wd.microsoft.com/ping`

> [!CAUTION]
> <span data-ttu-id="cb761-169">Es wird empfohlen, den [Systemintegritätsschutz (System Integrity Protection,](https://support.apple.com/en-us/HT204899) SIP) auf Clientgeräten aktiviert zu lassen.</span><span class="sxs-lookup"><span data-stu-id="cb761-169">We recommend that you keep [System Integrity Protection](https://support.apple.com/en-us/HT204899) (SIP) enabled on client devices.</span></span> <span data-ttu-id="cb761-170">SIP ist ein integriertes macOS-Sicherheitsfeature, das Fälschungen auf niedriger Ebene am Betriebssystem verhindert und standardmäßig aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="cb761-170">SIP is a built-in macOS security feature that prevents low-level tampering with the OS, and is enabled by default.</span></span>

<span data-ttu-id="cb761-171">Sobald Microsoft Defender for Endpoint installiert ist, kann die Konnektivität überprüft werden, indem der folgende Befehl im Terminal ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="cb761-171">Once Microsoft Defender for Endpoint is installed, connectivity can be validated by running the following command in Terminal:</span></span>
```bash
mdatp connectivity test
```

## <a name="how-to-update-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="cb761-172">Aktualisieren von Microsoft Defender for Endpoint für Mac</span><span class="sxs-lookup"><span data-stu-id="cb761-172">How to update Microsoft Defender for Endpoint for Mac</span></span>

<span data-ttu-id="cb761-173">Microsoft veröffentlicht regelmäßig Softwareupdates, um leistung, Sicherheit und neue Features zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="cb761-173">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="cb761-174">Zum Aktualisieren von Microsoft Defender für Endpoint für Mac wird ein Programm namens Microsoft AutoUpdate (MAU) verwendet.</span><span class="sxs-lookup"><span data-stu-id="cb761-174">To update Microsoft Defender for Endpoint for Mac, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="cb761-175">Weitere Informationen finden Sie unter [Deploy updates for Microsoft Defender for Endpoint for Mac](mac-updates.md).</span><span class="sxs-lookup"><span data-stu-id="cb761-175">To learn more, see [Deploy updates for Microsoft Defender for Endpoint for Mac](mac-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="cb761-176">Konfigurieren von Microsoft Defender for Endpoint für Mac</span><span class="sxs-lookup"><span data-stu-id="cb761-176">How to configure Microsoft Defender for Endpoint for Mac</span></span>

<span data-ttu-id="cb761-177">Anleitungen zum Konfigurieren des Produkts in Unternehmensumgebungen finden Sie unter [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md).</span><span class="sxs-lookup"><span data-stu-id="cb761-177">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md).</span></span>

## <a name="macos-kernel-and-system-extensions"></a><span data-ttu-id="cb761-178">macOS-Kernel und Systemerweiterungen</span><span class="sxs-lookup"><span data-stu-id="cb761-178">macOS kernel and system extensions</span></span>

<span data-ttu-id="cb761-179">In Übereinstimmung mit der macOS-Weiterentwicklung bereiten wir ein Microsoft Defender for Endpoint für Mac-Update vor, das Systemerweiterungen anstelle von Kernelerweiterungen nutzt.</span><span class="sxs-lookup"><span data-stu-id="cb761-179">In alignment with macOS evolution, we are preparing a Microsoft Defender for Endpoint for Mac update that leverages system extensions instead of kernel extensions.</span></span> <span data-ttu-id="cb761-180">Relevante Details finden Sie unter [What's new in Microsoft Defender for Endpoint for Mac](mac-whatsnew.md).</span><span class="sxs-lookup"><span data-stu-id="cb761-180">For relevant details, see [What's new in Microsoft Defender for Endpoint for Mac](mac-whatsnew.md).</span></span>

## <a name="resources"></a><span data-ttu-id="cb761-181">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="cb761-181">Resources</span></span>

- <span data-ttu-id="cb761-182">Weitere Informationen zum Protokollieren, Deinstallieren oder anderen Themen finden Sie unter [Resources for Microsoft Defender for Endpoint for Mac](mac-resources.md).</span><span class="sxs-lookup"><span data-stu-id="cb761-182">For more information about logging, uninstalling, or other topics, see [Resources for Microsoft Defender for Endpoint for Mac](mac-resources.md).</span></span>

- <span data-ttu-id="cb761-183">[Datenschutz für Microsoft Defender for Endpoint für Mac](mac-privacy.md).</span><span class="sxs-lookup"><span data-stu-id="cb761-183">[Privacy for Microsoft Defender for Endpoint for Mac](mac-privacy.md).</span></span>
