---
title: Microsoft Defender für Endpoint auf Dem Mac
ms.reviewer: ''
description: Erfahren Sie, wie Sie Microsoft Defender for Endpoint auf Mac installieren, konfigurieren, aktualisieren und verwenden.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamf, macos, big sur, catalina, mojave, mde for mac
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
ms.openlocfilehash: 365fed8b5f7c7fc617ea068e324da541f7f1b187
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52301776"
---
# <a name="microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="be6af-104">Microsoft Defender für Endpoint auf Dem Mac</span><span class="sxs-lookup"><span data-stu-id="be6af-104">Microsoft Defender for Endpoint on Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="be6af-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="be6af-105">**Applies to:**</span></span>
- [<span data-ttu-id="be6af-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="be6af-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="be6af-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="be6af-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="be6af-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="be6af-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="be6af-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="be6af-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="be6af-110">In diesem Thema wird beschrieben, wie Sie Defender for Endpoint auf Dem Mac installieren, konfigurieren, aktualisieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="be6af-110">This topic describes how to install, configure, update, and use Defender for Endpoint on Mac.</span></span>

> [!CAUTION]
> <span data-ttu-id="be6af-111">Das Ausführen anderer Endpunktschutzprodukte von Drittanbietern zusammen mit Microsoft Defender for Endpoint auf Mac führt wahrscheinlich zu Leistungsproblemen und unvorhersehbaren Nebenwirkungen.</span><span class="sxs-lookup"><span data-stu-id="be6af-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint on Mac is likely to lead to performance problems and unpredictable side effects.</span></span> <span data-ttu-id="be6af-112">Wenn in Ihrer Umgebung kein Microsoft-Endpunktschutz eine absolute Anforderung ist, können Sie die Funktionen von Defender for Endpoint auf Mac EDR weiterhin nutzen, nachdem Sie die Antivirenfunktionen für die Ausführung im passiven Modus konfiguriert [haben.](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="be6af-112">If non-Microsoft endpoint protection is an absolute requirement in your environment, you can still safely take advantage of Defender for Endpoint on Mac EDR functionality after configuring the antivirus functionality to run in [Passive mode](mac-preferences.md#enable--disable-passive-mode).</span></span>

## <a name="whats-new-in-the-latest-release"></a><span data-ttu-id="be6af-113">Neuigkeiten in der neuesten Version</span><span class="sxs-lookup"><span data-stu-id="be6af-113">What’s new in the latest release</span></span>

[<span data-ttu-id="be6af-114">Neuigkeiten in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="be6af-114">What's new in Microsoft Defender for Endpoint</span></span>](whats-new-in-microsoft-defender-atp.md)

[<span data-ttu-id="be6af-115">Neues in Microsoft Defender for Endpoint auf Mac</span><span class="sxs-lookup"><span data-stu-id="be6af-115">What's new in Microsoft Defender for Endpoint on Mac</span></span>](mac-whatsnew.md)

> [!TIP]
> <span data-ttu-id="be6af-116">Wenn Sie Feedback haben, das Sie freigeben möchten, übermitteln Sie es, indem Sie Microsoft Defender for Endpoint auf Dem Mac auf Ihrem Gerät öffnen und navigieren, um Feedback zu  >  senden.</span><span class="sxs-lookup"><span data-stu-id="be6af-116">If you have any feedback that you would like to share, submit it by opening Microsoft Defender for Endpoint on Mac on your device and navigating to **Help** > **Send feedback**.</span></span>

<span data-ttu-id="be6af-117">Um die neuesten Features, einschließlich Vorschaufunktionen (z. B. EDR für Ihre Mac-Geräte), zu erhalten, konfigurieren Sie Ihr macOS-Gerät, auf dem Microsoft Defender for Endpoint ausgeführt wird, als "Insider"-Gerät.</span><span class="sxs-lookup"><span data-stu-id="be6af-117">To get the latest features, including preview capabilities (such as endpoint detection and response for your Mac devices), configure your macOS device running Microsoft Defender for Endpoint to be an "Insider" device.</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="be6af-118">Installieren von Microsoft Defender for Endpoint auf Dem Mac</span><span class="sxs-lookup"><span data-stu-id="be6af-118">How to install Microsoft Defender for Endpoint on Mac</span></span>

### <a name="prerequisites"></a><span data-ttu-id="be6af-119">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="be6af-119">Prerequisites</span></span>

- <span data-ttu-id="be6af-120">Ein Defender for Endpoint-Abonnement und Zugriff auf das Microsoft Defender Security Center Portal</span><span class="sxs-lookup"><span data-stu-id="be6af-120">A Defender for Endpoint subscription and access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="be6af-121">Erfahrung auf Anfängerebene in macOS- und BASH-Skripting</span><span class="sxs-lookup"><span data-stu-id="be6af-121">Beginner-level experience in macOS and BASH scripting</span></span>
- <span data-ttu-id="be6af-122">Administratorrechte auf dem Gerät (bei manueller Bereitstellung)</span><span class="sxs-lookup"><span data-stu-id="be6af-122">Administrative privileges on the device (in case of manual deployment)</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="be6af-123">Installationsanweisungen</span><span class="sxs-lookup"><span data-stu-id="be6af-123">Installation instructions</span></span>

<span data-ttu-id="be6af-124">Es gibt mehrere Methoden und Bereitstellungstools, die Sie zum Installieren und Konfigurieren von Defender for Endpoint auf Dem Mac verwenden können.</span><span class="sxs-lookup"><span data-stu-id="be6af-124">There are several methods and deployment tools that you can use to install and configure Defender for Endpoint on Mac.</span></span>

- <span data-ttu-id="be6af-125">Verwaltungstools von Drittanbietern:</span><span class="sxs-lookup"><span data-stu-id="be6af-125">Third-party management tools:</span></span>
    - [<span data-ttu-id="be6af-126">Microsoft-Intune-basierte Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="be6af-126">Microsoft Intune-based deployment</span></span>](mac-install-with-intune.md)
    - [<span data-ttu-id="be6af-127">JAMF-basierte Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="be6af-127">JAMF-based deployment</span></span>](mac-install-with-jamf.md)
    - [<span data-ttu-id="be6af-128">Andere MDM-Produkte</span><span class="sxs-lookup"><span data-stu-id="be6af-128">Other MDM products</span></span>](mac-install-with-other-mdm.md)

- <span data-ttu-id="be6af-129">Befehlszeilentool:</span><span class="sxs-lookup"><span data-stu-id="be6af-129">Command-line tool:</span></span>
    - [<span data-ttu-id="be6af-130">Manuelle Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="be6af-130">Manual deployment</span></span>](mac-install-manually.md)

### <a name="system-requirements"></a><span data-ttu-id="be6af-131">Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="be6af-131">System requirements</span></span>

<span data-ttu-id="be6af-132">Die drei neuesten Hauptversionen von macOS werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="be6af-132">The three most recent major releases of macOS are supported.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="be6af-133">Unter macOS 11 (Big Sur) erfordert Microsoft Defender for Endpoint zusätzliche Konfigurationsprofile.</span><span class="sxs-lookup"><span data-stu-id="be6af-133">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="be6af-134">Wenn Sie ein vorhandenes Kunden-Upgrade von früheren Versionen von macOS sind, stellen Sie sicher, dass Sie die zusätzlichen Konfigurationsprofile bereitstellen, die unter Neue Konfigurationsprofile für [macOS Catalina](mac-sysext-policies.md)und neuere Versionen von macOS aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="be6af-134">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [New configuration profiles for macOS Catalina and newer versions of macOS](mac-sysext-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="be6af-135">Die Unterstützung für macOS 10.13 (High Sierra) wurde ab dem 15. Februar 2021 eingestellt.</span><span class="sxs-lookup"><span data-stu-id="be6af-135">Support for macOS 10.13 (High Sierra) has been discontinued as of February 15th, 2021.</span></span>

- <span data-ttu-id="be6af-136">11 (Big Sur), 10.15 (Catalina), 10.14 (Mojave)</span><span class="sxs-lookup"><span data-stu-id="be6af-136">11 (Big Sur), 10.15 (Catalina), 10.14 (Mojave)</span></span>
- <span data-ttu-id="be6af-137">Speicherplatz: 1 GB</span><span class="sxs-lookup"><span data-stu-id="be6af-137">Disk space: 1GB</span></span>

<span data-ttu-id="be6af-138">Betaversionen von macOS werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="be6af-138">Beta versions of macOS are not supported.</span></span>

<span data-ttu-id="be6af-139">MacOS-Geräte mit M1-Prozessoren werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="be6af-139">macOS devices with M1 processors are not supported.</span></span>

<span data-ttu-id="be6af-140">Nachdem Sie den Dienst aktiviert haben, müssen Sie möglicherweise Ihr Netzwerk oder ihre Firewall so konfigurieren, dass ausgehende Verbindungen zwischen dem Dienst und Ihren Endpunkten zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="be6af-140">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="be6af-141">Lizenzierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="be6af-141">Licensing requirements</span></span>

<span data-ttu-id="be6af-142">Microsoft Defender für Endpoint auf Mac erfordert eines der folgenden Microsoft Volumenlizenzangebote:</span><span class="sxs-lookup"><span data-stu-id="be6af-142">Microsoft Defender for Endpoint on Mac requires one of the following Microsoft Volume Licensing offers:</span></span>

- <span data-ttu-id="be6af-143">Microsoft 365 E5 (M365 E5)</span><span class="sxs-lookup"><span data-stu-id="be6af-143">Microsoft 365 E5 (M365 E5)</span></span>
- <span data-ttu-id="be6af-144">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="be6af-144">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="be6af-145">Microsoft 365 A5 (M365 A5)</span><span class="sxs-lookup"><span data-stu-id="be6af-145">Microsoft 365 A5 (M365 A5)</span></span>
- <span data-ttu-id="be6af-146">Windows 10 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="be6af-146">Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="be6af-147">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="be6af-147">Microsoft Defender for Endpoint</span></span>

> [!NOTE]
> <span data-ttu-id="be6af-148">Berechtigte lizenzierte Benutzer können Microsoft Defender for Endpoint auf bis zu fünf gleichzeitigen Geräten verwenden.</span><span class="sxs-lookup"><span data-stu-id="be6af-148">Eligible licensed users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span>
> <span data-ttu-id="be6af-149">Microsoft Defender for Endpoint steht auch bei einem Cloud Solution Provider (CSP) zum Kauf zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="be6af-149">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span> <span data-ttu-id="be6af-150">Wenn sie über einen CSP erworben werden, sind keine Microsoft Volumenlizenzangebote aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="be6af-150">When purchased via a CSP, it does not require Microsoft Volume Licensing offers listed.</span></span>

### <a name="network-connections"></a><span data-ttu-id="be6af-151">Netzwerkverbindungen</span><span class="sxs-lookup"><span data-stu-id="be6af-151">Network connections</span></span>

<span data-ttu-id="be6af-152">In der folgenden herunterladbaren Kalkulationstabelle sind die Dienste und die zugehörigen URLs aufgeführt, mit deren Netzwerk eine Verbindung herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="be6af-152">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="be6af-153">Sie sollten sicherstellen, dass es keine Firewall- oder Netzwerkfilterregeln gibt, die den  Zugriff auf diese URLs verweigern würden, oder Sie müssen möglicherweise eine speziell für sie zulässige Regel erstellen.</span><span class="sxs-lookup"><span data-stu-id="be6af-153">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>



|<span data-ttu-id="be6af-154">**Tabellenkalkulation der Domänenliste**</span><span class="sxs-lookup"><span data-stu-id="be6af-154">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="be6af-155">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="be6af-155">**Description**</span></span>|
|:-----|:-----|
|![Thumb image for Microsoft Defender for Endpoint URLs spreadsheet](images/mdatp-urls.png)<br/>  | <span data-ttu-id="be6af-157">Tabellenkalkulation bestimmter DNS-Einträge für Dienststandorte, geografische Standorte und Betriebssysteme.</span><span class="sxs-lookup"><span data-stu-id="be6af-157">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br><span data-ttu-id="be6af-158">Laden Sie die Kalkulationstabelle [ hier herunter:mdatp-urls.xlsx](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx).</span><span class="sxs-lookup"><span data-stu-id="be6af-158">Download the spreadsheet here: [mdatp-urls.xlsx](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx).</span></span>

<span data-ttu-id="be6af-159">Microsoft Defender for Endpoint kann einen Proxyserver mithilfe der folgenden Ermittlungsmethoden ermitteln:</span><span class="sxs-lookup"><span data-stu-id="be6af-159">Microsoft Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="be6af-160">Proxy autoconfig (PAC)</span><span class="sxs-lookup"><span data-stu-id="be6af-160">Proxy autoconfig (PAC)</span></span>
- <span data-ttu-id="be6af-161">Webproxy-AutoErmittlungsprotokoll (WPAD)</span><span class="sxs-lookup"><span data-stu-id="be6af-161">Web Proxy Autodiscovery Protocol (WPAD)</span></span>
- <span data-ttu-id="be6af-162">Manuelle Konfiguration statischer Proxys</span><span class="sxs-lookup"><span data-stu-id="be6af-162">Manual static proxy configuration</span></span>

<span data-ttu-id="be6af-163">Wenn ein Proxy oder eine Firewall anonymen Datenverkehr blockiert, stellen Sie sicher, dass anonymer Datenverkehr in den zuvor aufgeführten URLs zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="be6af-163">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span>

> [!WARNING]
> <span data-ttu-id="be6af-164">Authentifizierte Proxys werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="be6af-164">Authenticated proxies are not supported.</span></span> <span data-ttu-id="be6af-165">Stellen Sie sicher, dass nur PAC, WPAD oder ein statischer Proxy verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="be6af-165">Ensure that only PAC, WPAD, or a static proxy is being used.</span></span>
>
> <span data-ttu-id="be6af-166">Ssl-Überprüfung und Abfangen von Proxys werden aus Sicherheitsgründen ebenfalls nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="be6af-166">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="be6af-167">Konfigurieren Sie eine Ausnahme für die SSL-Überprüfung und Ihren Proxyserver, um Daten von Microsoft Defender for Endpoint auf macOS direkt an die relevanten URLs ohne Abfangen zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="be6af-167">Configure an exception for SSL inspection and your proxy server to directly pass through data from Microsoft Defender for Endpoint on macOS to the relevant URLs without interception.</span></span> <span data-ttu-id="be6af-168">Wenn Sie Ihr Abfangzertifikat zum globalen Speicher hinzufügen, ist das Abfangen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="be6af-168">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="be6af-169">Öffnen Sie und in einem Browser, um zu testen, ob eine Verbindung [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) nicht blockiert ist.</span><span class="sxs-lookup"><span data-stu-id="be6af-169">To test that a connection is not blocked, open [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) and [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) in a browser.</span></span>

<span data-ttu-id="be6af-170">Wenn Sie die Befehlszeile bevorzugen, können Sie die Verbindung auch überprüfen, indem Sie den folgenden Befehl im Terminal ausführen:</span><span class="sxs-lookup"><span data-stu-id="be6af-170">If you prefer the command line, you can also check the connection by running the following command in Terminal:</span></span>

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="be6af-171">Die Ausgabe dieses Befehls sollte der folgenden ähneln:</span><span class="sxs-lookup"><span data-stu-id="be6af-171">The output from this command should be similar to the following:</span></span>

 `OK https://x.cp.wd.microsoft.com/api/report`

 `OK https://cdn.x.cp.wd.microsoft.com/ping`

> [!CAUTION]
> <span data-ttu-id="be6af-172">Es wird empfohlen, den [Systemintegritätsschutz (System Integrity Protection,](https://support.apple.com/en-us/HT204899) SIP) auf Clientgeräten aktiviert zu lassen.</span><span class="sxs-lookup"><span data-stu-id="be6af-172">We recommend that you keep [System Integrity Protection](https://support.apple.com/en-us/HT204899) (SIP) enabled on client devices.</span></span> <span data-ttu-id="be6af-173">SIP ist ein integriertes macOS-Sicherheitsfeature, das Fälschungen auf niedriger Ebene am Betriebssystem verhindert und standardmäßig aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="be6af-173">SIP is a built-in macOS security feature that prevents low-level tampering with the OS, and is enabled by default.</span></span>

<span data-ttu-id="be6af-174">Sobald Microsoft Defender for Endpoint installiert ist, kann die Konnektivität überprüft werden, indem der folgende Befehl im Terminal ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="be6af-174">Once Microsoft Defender for Endpoint is installed, connectivity can be validated by running the following command in Terminal:</span></span>
```bash
mdatp connectivity test
```

## <a name="how-to-update-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="be6af-175">Aktualisieren von Microsoft Defender for Endpoint auf Dem Mac</span><span class="sxs-lookup"><span data-stu-id="be6af-175">How to update Microsoft Defender for Endpoint on Mac</span></span>

<span data-ttu-id="be6af-176">Microsoft veröffentlicht regelmäßig Softwareupdates, um leistung, Sicherheit und neue Features zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="be6af-176">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="be6af-177">Zum Aktualisieren von Microsoft Defender for Endpoint auf Mac wird ein Programm namens Microsoft AutoUpdate (MAU) verwendet.</span><span class="sxs-lookup"><span data-stu-id="be6af-177">To update Microsoft Defender for Endpoint on Mac, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="be6af-178">Weitere Informationen finden Sie unter [Deploy updates for Microsoft Defender for Endpoint on Mac](mac-updates.md).</span><span class="sxs-lookup"><span data-stu-id="be6af-178">To learn more, see [Deploy updates for Microsoft Defender for Endpoint on Mac](mac-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="be6af-179">Konfigurieren von Microsoft Defender for Endpoint auf Dem Mac</span><span class="sxs-lookup"><span data-stu-id="be6af-179">How to configure Microsoft Defender for Endpoint on Mac</span></span>

<span data-ttu-id="be6af-180">Anleitungen zum Konfigurieren des Produkts in Unternehmensumgebungen finden Sie unter [Set preferences for Microsoft Defender for Endpoint on Mac](mac-preferences.md).</span><span class="sxs-lookup"><span data-stu-id="be6af-180">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint on Mac](mac-preferences.md).</span></span>

## <a name="macos-kernel-and-system-extensions"></a><span data-ttu-id="be6af-181">macOS-Kernel und Systemerweiterungen</span><span class="sxs-lookup"><span data-stu-id="be6af-181">macOS kernel and system extensions</span></span>

<span data-ttu-id="be6af-182">In Übereinstimmung mit der macOS-Weiterentwicklung bereiten wir ein Microsoft Defender for Endpoint on Mac-Update vor, das Systemerweiterungen anstelle von Kernelerweiterungen nutzt.</span><span class="sxs-lookup"><span data-stu-id="be6af-182">In alignment with macOS evolution, we are preparing a Microsoft Defender for Endpoint on Mac update that leverages system extensions instead of kernel extensions.</span></span> <span data-ttu-id="be6af-183">Relevante Details finden Sie unter [What's new in Microsoft Defender for Endpoint on Mac](mac-whatsnew.md).</span><span class="sxs-lookup"><span data-stu-id="be6af-183">For relevant details, see [What's new in Microsoft Defender for Endpoint on Mac](mac-whatsnew.md).</span></span>

## <a name="resources"></a><span data-ttu-id="be6af-184">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="be6af-184">Resources</span></span>

- <span data-ttu-id="be6af-185">Weitere Informationen zum Protokollieren, Deinstallieren oder anderen Themen finden Sie unter [Ressourcen für Microsoft Defender for Endpoint auf Mac](mac-resources.md).</span><span class="sxs-lookup"><span data-stu-id="be6af-185">For more information about logging, uninstalling, or other topics, see [Resources for Microsoft Defender for Endpoint on Mac](mac-resources.md).</span></span>

- <span data-ttu-id="be6af-186">[Datenschutz für Microsoft Defender for Endpoint auf Mac](mac-privacy.md).</span><span class="sxs-lookup"><span data-stu-id="be6af-186">[Privacy for Microsoft Defender for Endpoint on Mac](mac-privacy.md).</span></span>
