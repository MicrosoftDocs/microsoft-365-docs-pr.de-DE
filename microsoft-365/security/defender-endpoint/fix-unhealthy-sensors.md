---
title: Beheben fehlerhafter Sensoren in Microsoft Defender for Endpoint
description: Beheben Sie Gerätesensoren, die als falsch konfiguriert oder inaktiv melden, sodass der Dienst Daten vom Gerät empfängt.
keywords: falsch konfiguriert, inaktiv, Sensor fix, Sensorintegte, keine Sensordaten, Sensordaten, beeinträchtigte Kommunikation, Kommunikation
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
ms.topic: article
ms.date: 11/06/2020
ms.technology: mde
ms.openlocfilehash: a24dc4ef23d32b19de9d2871b7d87aae90d05828
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065696"
---
# <a name="fix-unhealthy-sensors-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="34252-104">Beheben fehlerhafter Sensoren in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="34252-104">Fix unhealthy sensors in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="34252-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="34252-105">**Applies to:**</span></span>
- [<span data-ttu-id="34252-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="34252-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="34252-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="34252-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="34252-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="34252-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="34252-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="34252-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-fixsensor-abovefoldlink)

<span data-ttu-id="34252-110">Geräte, die als falsch konfiguriert oder inaktiv kategorisiert sind, können aufgrund unterschiedlicher Ursachen gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="34252-110">Devices that are categorized as misconfigured or inactive can be flagged due to varying causes.</span></span> <span data-ttu-id="34252-111">Dieser Abschnitt enthält einige Erläuterungen dazu, was dazu führte, dass ein Gerät als inaktiv oder falsch konfiguriert kategorisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="34252-111">This section provides some explanations as to what might have caused a device to be categorized as inactive or misconfigured.</span></span>

## <a name="inactive-devices"></a><span data-ttu-id="34252-112">Inaktive Geräte</span><span class="sxs-lookup"><span data-stu-id="34252-112">Inactive devices</span></span>

<span data-ttu-id="34252-113">Ein inaktives Gerät wird aufgrund eines Problems nicht unbedingt gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="34252-113">An inactive device is not necessarily flagged due to an issue.</span></span> <span data-ttu-id="34252-114">Die folgenden Aktionen auf einem Gerät können dazu führen, dass ein Gerät als inaktiv kategorisiert wird:</span><span class="sxs-lookup"><span data-stu-id="34252-114">The following actions taken on a device can cause a device to be categorized as inactive:</span></span>

### <a name="device-is-not-in-use"></a><span data-ttu-id="34252-115">Gerät wird nicht verwendet</span><span class="sxs-lookup"><span data-stu-id="34252-115">Device is not in use</span></span>

<span data-ttu-id="34252-116">Wenn das Gerät aus irgendeinem Grund seit mehr als sieben Tagen nicht verwendet wird, bleibt es im Portal im Status "Inaktiv".</span><span class="sxs-lookup"><span data-stu-id="34252-116">If the device has not been in use for more than seven days for any reason, it will remain in an ‘Inactive’ status in the portal.</span></span>

### <a name="device-was-reinstalled-or-renamed"></a><span data-ttu-id="34252-117">Gerät wurde neu installiert oder umbenannt</span><span class="sxs-lookup"><span data-stu-id="34252-117">Device was reinstalled or renamed</span></span>
<span data-ttu-id="34252-118">Ein neu installiertes oder umbenanntes Gerät generiert eine neue Geräteentität im Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="34252-118">A reinstalled or renamed device will generate a new device entity in Microsoft Defender Security Center.</span></span> <span data-ttu-id="34252-119">Die vorherige Geräteentität bleibt im Portal mit dem Status "Inaktiv" erhalten.</span><span class="sxs-lookup"><span data-stu-id="34252-119">The previous device entity will remain with an ‘Inactive’ status in the portal.</span></span> <span data-ttu-id="34252-120">Wenn Sie ein Gerät neu installiert und das Defender for Endpoint-Paket bereitgestellt haben, suchen Sie nach dem neuen Gerätenamen, um sicherzustellen, dass das Gerät normal meldet.</span><span class="sxs-lookup"><span data-stu-id="34252-120">If you reinstalled a device and deployed the Defender for Endpoint package, search for the new device name to verify that the device is reporting normally.</span></span>

### <a name="device-was-offboarded"></a><span data-ttu-id="34252-121">Gerät wurde offboarded</span><span class="sxs-lookup"><span data-stu-id="34252-121">Device was offboarded</span></span>
<span data-ttu-id="34252-122">Wenn das Gerät offboarded war, wird es weiterhin in der Geräteliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="34252-122">If the device was offboarded, it will still appear in devices list.</span></span> <span data-ttu-id="34252-123">Nach sieben Tagen sollte der Zustand des Gerätestatus in inaktiv geändert werden.</span><span class="sxs-lookup"><span data-stu-id="34252-123">After seven days, the device health state should change to inactive.</span></span>

### <a name="device-is-not-sending-signals"></a><span data-ttu-id="34252-124">Gerät sendet keine Signale</span><span class="sxs-lookup"><span data-stu-id="34252-124">Device is not sending signals</span></span>
<span data-ttu-id="34252-125">Wenn das Gerät aus irgendeinem Grund, einschließlich Bedingungen, die unter die Klassifizierung falsch konfigurierter Geräte fallen, keine Signale mehr als sieben Tage lang an einen der Microsoft Defender for Endpoint-Kanäle sendet, kann ein Gerät als inaktiv betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="34252-125">If the device is not sending any signals for more than seven days to any of the Microsoft Defender for Endpoint channels for any reason including conditions that fall under misconfigured devices classification, a device can be considered inactive.</span></span> 

<span data-ttu-id="34252-126">Erwarten Sie, dass ein Gerät den Status "Aktiv" hat?</span><span class="sxs-lookup"><span data-stu-id="34252-126">Do you expect a device to be in ‘Active’ status?</span></span> <span data-ttu-id="34252-127">[Öffnen Sie ein Supportticket](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561).</span><span class="sxs-lookup"><span data-stu-id="34252-127">[Open a support ticket](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561).</span></span>

## <a name="misconfigured-devices"></a><span data-ttu-id="34252-128">Falsch konfigurierte Geräte</span><span class="sxs-lookup"><span data-stu-id="34252-128">Misconfigured devices</span></span>
<span data-ttu-id="34252-129">Falsch konfigurierte Geräte können weiter wie folgt klassifiziert werden:</span><span class="sxs-lookup"><span data-stu-id="34252-129">Misconfigured devices can further be classified to:</span></span>
- <span data-ttu-id="34252-130">Beeinträchtigte Kommunikation</span><span class="sxs-lookup"><span data-stu-id="34252-130">Impaired communications</span></span>
- <span data-ttu-id="34252-131">Keine Sensordaten</span><span class="sxs-lookup"><span data-stu-id="34252-131">No sensor data</span></span>

### <a name="impaired-communications"></a><span data-ttu-id="34252-132">Beeinträchtigte Kommunikation</span><span class="sxs-lookup"><span data-stu-id="34252-132">Impaired communications</span></span>
<span data-ttu-id="34252-133">Dieser Status gibt an, dass die Kommunikation zwischen dem Gerät und dem Dienst eingeschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="34252-133">This status indicates that there's limited communication between the device and the service.</span></span>

<span data-ttu-id="34252-134">Mit den folgenden vorgeschlagenen Aktionen können Probleme im Zusammenhang mit einem falsch konfigurierten Gerät mit eingeschränkter Kommunikation behoben werden:</span><span class="sxs-lookup"><span data-stu-id="34252-134">The following suggested actions can help fix issues related to a misconfigured device with impaired communications:</span></span>

- [<span data-ttu-id="34252-135">Sicherstellen, dass das Gerät über eine Internetverbindung verfügt</span><span class="sxs-lookup"><span data-stu-id="34252-135">Ensure the device has Internet connection</span></span>](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  <span data-ttu-id="34252-136">Für den Window Defender ATP-Sensor muss Microsoft Windows HTTP (WinHTTP) Sensordaten melden und mit dem Microsoft Defender for Endpoint-Dienst kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="34252-136">The Window Defender ATP sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span>

- [<span data-ttu-id="34252-137">Überprüfen der Clientkonnektivität mit Microsoft Defender for Endpoint-Dienst-URLs</span><span class="sxs-lookup"><span data-stu-id="34252-137">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-atp-service-urls)</br>
  <span data-ttu-id="34252-138">Überprüfen Sie, ob die Proxykonfiguration erfolgreich abgeschlossen wurde, dass WinHTTP den Proxyserver in Ihrer Umgebung ermitteln und kommunizieren kann und dass der Proxyserver Datenverkehr an die URLs des Microsoft Defender for Endpoint-Diensts zulässt.</span><span class="sxs-lookup"><span data-stu-id="34252-138">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Microsoft Defender for Endpoint service URLs.</span></span>

<span data-ttu-id="34252-139">Wenn Sie Korrekturmaßnahmen ergriffen haben und der Gerätestatus weiterhin falsch konfiguriert ist, öffnen [Sie ein Supportticket](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="34252-139">If you took corrective actions and the device status is still misconfigured, [open a support ticket](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).</span></span>

### <a name="no-sensor-data"></a><span data-ttu-id="34252-140">Keine Sensordaten</span><span class="sxs-lookup"><span data-stu-id="34252-140">No sensor data</span></span>
<span data-ttu-id="34252-141">Ein falsch konfiguriertes Gerät mit dem Status "Keine Sensordaten" verfügt über eine Kommunikation mit dem Dienst, kann aber nur Teilsensordaten melden.</span><span class="sxs-lookup"><span data-stu-id="34252-141">A misconfigured device with status ‘No sensor data’ has communication with the service but can only report partial sensor data.</span></span>
<span data-ttu-id="34252-142">Führen Sie diese Aktionen aus, um bekannte Probleme im Zusammenhang mit einem falsch konfigurierten Gerät mit dem Status "Keine Sensordaten" zu beheben:</span><span class="sxs-lookup"><span data-stu-id="34252-142">Follow theses actions to correct known issues related to a misconfigured device with status ‘No sensor data’:</span></span>

- [<span data-ttu-id="34252-143">Sicherstellen, dass das Gerät über eine Internetverbindung verfügt</span><span class="sxs-lookup"><span data-stu-id="34252-143">Ensure the device has Internet connection</span></span>](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  <span data-ttu-id="34252-144">Für den Window Defender ATP-Sensor muss Microsoft Windows HTTP (WinHTTP) Sensordaten melden und mit dem Microsoft Defender for Endpoint-Dienst kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="34252-144">The Window Defender ATP sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span>

- [<span data-ttu-id="34252-145">Überprüfen der Clientkonnektivität mit Microsoft Defender for Endpoint-Dienst-URLs</span><span class="sxs-lookup"><span data-stu-id="34252-145">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-atp-service-urls)</br>
  <span data-ttu-id="34252-146">Überprüfen Sie, ob die Proxykonfiguration erfolgreich abgeschlossen wurde, dass WinHTTP den Proxyserver in Ihrer Umgebung ermitteln und kommunizieren kann und dass der Proxyserver Datenverkehr an die URLs des Microsoft Defender for Endpoint-Diensts zulässt.</span><span class="sxs-lookup"><span data-stu-id="34252-146">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Microsoft Defender for Endpoint service URLs.</span></span>

- [<span data-ttu-id="34252-147">Sicherstellen, dass der Diagnosedatendienst aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="34252-147">Ensure the diagnostic data service is enabled</span></span>](troubleshoot-onboarding.md#ensure-the-diagnostics-service-is-enabled)</br>
<span data-ttu-id="34252-148">Wenn die Geräte nicht ordnungsgemäß melden, müssen Sie möglicherweise überprüfen, ob der Windows 10-Diagnosedatendienst auf den automatischen Start festgelegt ist und auf dem Endpunkt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="34252-148">If the devices aren't reporting correctly, you might need to check that the Windows 10 diagnostic data service is set to automatically start and is running on the endpoint.</span></span>

- [<span data-ttu-id="34252-149">Stellen Sie sicher, dass Microsoft Defender Antivirus nicht von der Richtlinie deaktiviert ist</span><span class="sxs-lookup"><span data-stu-id="34252-149">Ensure that Microsoft Defender Antivirus is not disabled by policy</span></span>](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</br>
<span data-ttu-id="34252-150">Wenn auf Ihren Geräten ein Antischasoftwareclient eines Drittanbieters ausgeführt wird, benötigt der Defender for Endpoint-Agent, dass der Microsoft Defender Antivirus Early Launch Antimalware (ELAM)-Treiber aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="34252-150">If your devices are running a third-party antimalware client, the Defender for Endpoint agent needs the Microsoft Defender Antivirus Early Launch Antimalware (ELAM) driver to be enabled.</span></span>

<span data-ttu-id="34252-151">Wenn Sie Korrekturmaßnahmen ergriffen haben und der Gerätestatus weiterhin falsch konfiguriert ist, öffnen [Sie ein Supportticket](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="34252-151">If you took corrective actions and the device status is still misconfigured, [open a support ticket](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).</span></span>

## <a name="see-also"></a><span data-ttu-id="34252-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34252-152">See also</span></span>
- [<span data-ttu-id="34252-153">Überprüfen des Sensorintestatus in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="34252-153">Check sensor health state in Microsoft Defender for Endpoint</span></span>](check-sensor-status.md)
