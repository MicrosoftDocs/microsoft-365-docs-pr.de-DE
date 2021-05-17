---
title: Überprüfen von Ereignissen und Fehlern mithilfe der Ereignisanzeige
description: Erhalten Sie Beschreibungen und weitere Schritte zur Problembehandlung (falls erforderlich) für alle Ereignisse, die vom Microsoft Defender for Endpoint-Dienst gemeldet wurden.
keywords: Problembehandlung, Ereignisanzeige, Protokollzusammenfassung, Fehlercode, Fehler, Microsoft Defender for Endpoint-Dienst, kann nicht gestartet, unterbrochen, nicht gestartet werden
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
ms.date: 05/21/2018
ms.technology: mde
ms.openlocfilehash: a8b7268e89470a85a34015967b69abb1818fe64f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933841"
---
# <a name="review-events-and-errors-using-event-viewer"></a><span data-ttu-id="abd91-104">Überprüfen von Ereignissen und Fehlern mithilfe der Ereignisanzeige</span><span class="sxs-lookup"><span data-stu-id="abd91-104">Review events and errors using Event Viewer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="abd91-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="abd91-105">**Applies to:**</span></span>
- <span data-ttu-id="abd91-106">Ereignisanzeige</span><span class="sxs-lookup"><span data-stu-id="abd91-106">Event Viewer</span></span>
- [<span data-ttu-id="abd91-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="abd91-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="abd91-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="abd91-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="abd91-109">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="abd91-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="abd91-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="abd91-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="abd91-111">Sie können Ereignis-IDs in der [Ereignisanzeige auf](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) einzelnen Geräten überprüfen.</span><span class="sxs-lookup"><span data-stu-id="abd91-111">You can review event IDs in the [Event Viewer](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) on individual devices.</span></span>

<span data-ttu-id="abd91-112">Wenn Geräte beispielsweise nicht in der Liste Geräte angezeigt **werden,** müssen Sie möglicherweise nach Ereignis-IDs auf den Geräten suchen.</span><span class="sxs-lookup"><span data-stu-id="abd91-112">For example, if devices aren't appearing in the **Devices list**, you might need to look for event IDs on the devices.</span></span> <span data-ttu-id="abd91-113">Anschließend können Sie diese Tabelle verwenden, um weitere Schritte zur Problembehandlung zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="abd91-113">You can then use this table to determine further troubleshooting steps.</span></span>

<span data-ttu-id="abd91-114">**Öffnen Sie die Ereignisanzeige, und suchen Sie das Microsoft Defender for Endpoint-Dienstereignisprotokoll:**</span><span class="sxs-lookup"><span data-stu-id="abd91-114">**Open Event Viewer and find the Microsoft Defender for Endpoint service event log:**</span></span>

1. <span data-ttu-id="abd91-115">Klicken **Sie im** Menü Windows auf Start, geben Sie **Ereignisanzeige ein,** und drücken Sie die **EINGABETASTE.**</span><span class="sxs-lookup"><span data-stu-id="abd91-115">Click **Start** on the Windows menu, type **Event Viewer**, and press **Enter**.</span></span>

2. <span data-ttu-id="abd91-116">Führen Sie in der Protokollliste unter **Protokollzusammenfassung** einen Bildlauf durch, bis **Microsoft-Windows-SENSE/Operational angezeigt wird.**</span><span class="sxs-lookup"><span data-stu-id="abd91-116">In the log list, under **Log Summary**, scroll until you see **Microsoft-Windows-SENSE/Operational**.</span></span> <span data-ttu-id="abd91-117">Doppelklicken Sie auf das Element, um das Protokoll zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="abd91-117">Double-click the item to open the log.</span></span>

   <span data-ttu-id="abd91-118">a.</span><span class="sxs-lookup"><span data-stu-id="abd91-118">a.</span></span>  <span data-ttu-id="abd91-119">Sie können auch auf das Protokoll zugreifen, indem Sie Die Anwendungs- und **Dienstprotokolle** von Microsoft Windows erweitern und  >    >    >   auf **Betriebs.**</span><span class="sxs-lookup"><span data-stu-id="abd91-119">You can also access the log by expanding **Applications and Services Logs** > **Microsoft** > **Windows** > **SENSE** and click on **Operational**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="abd91-120">SENSE ist der interne Name, der verwendet wird, um auf den Verhaltenssensor zu verweisen, der Microsoft Defender for Endpoint unterstützt.</span><span class="sxs-lookup"><span data-stu-id="abd91-120">SENSE is the internal name used to refer to the behavioral sensor that powers Microsoft Defender for Endpoint.</span></span>

3. <span data-ttu-id="abd91-121">Vom Dienst aufgezeichnete Ereignisse werden im Protokoll angezeigt.</span><span class="sxs-lookup"><span data-stu-id="abd91-121">Events recorded by the service will appear in the log.</span></span> <span data-ttu-id="abd91-122">Eine Liste der vom Dienst aufgezeichneten Ereignisse finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="abd91-122">See the following table for a list of events recorded by the service.</span></span>

<table>
<tbody style="vertical-align:top;">
<tr>
<th><span data-ttu-id="abd91-123">Ereigniskennung</span><span class="sxs-lookup"><span data-stu-id="abd91-123">Event ID</span></span></th>
<th><span data-ttu-id="abd91-124">Message</span><span class="sxs-lookup"><span data-stu-id="abd91-124">Message</span></span></th>
<th><span data-ttu-id="abd91-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="abd91-125">Description</span></span></th>
<th><span data-ttu-id="abd91-126">Aktion</span><span class="sxs-lookup"><span data-stu-id="abd91-126">Action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="abd91-127">1</span><span class="sxs-lookup"><span data-stu-id="abd91-127">1</span></span></td>
<td><span data-ttu-id="abd91-128">Microsoft Defender for Endpoint Service gestartet (Version <code>variable</code> ).</span><span class="sxs-lookup"><span data-stu-id="abd91-128">Microsoft Defender for Endpoint service started (Version <code>variable</code>).</span></span></td>
<td><span data-ttu-id="abd91-129">Tritt während des Systemstarts, heruntergefahren und während des Onboardings auf.</span><span class="sxs-lookup"><span data-stu-id="abd91-129">Occurs during system startup, shut down, and during onboarding.</span></span></td>
<td><span data-ttu-id="abd91-130">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-130">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-131">2</span><span class="sxs-lookup"><span data-stu-id="abd91-131">2</span></span></td>
<td><span data-ttu-id="abd91-132">Herunterfahren des Microsoft Defender for Endpoint-Diensts.</span><span class="sxs-lookup"><span data-stu-id="abd91-132">Microsoft Defender for Endpoint service shutdown.</span></span></td>
<td><span data-ttu-id="abd91-133">Tritt auf, wenn das Gerät heruntergefahren oder offboarded wird.</span><span class="sxs-lookup"><span data-stu-id="abd91-133">Occurs when the device is shut down or offboarded.</span></span></td>
<td><span data-ttu-id="abd91-134">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-134">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-135">3</span><span class="sxs-lookup"><span data-stu-id="abd91-135">3</span></span></td>
<td><span data-ttu-id="abd91-136">Der Microsoft Defender for Endpoint-Dienst konnte nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="abd91-136">Microsoft Defender for Endpoint service failed to start.</span></span> <span data-ttu-id="abd91-137">Fehlercode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="abd91-137">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="abd91-138">Der Dienst wurde nicht gestartet.</span><span class="sxs-lookup"><span data-stu-id="abd91-138">Service didn't start.</span></span></td>
<td><span data-ttu-id="abd91-139">Überprüfen Sie andere Nachrichten, um mögliche Ursachen und Schritte zur Problembehandlung zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="abd91-139">Review other messages to determine possible cause and troubleshooting steps.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-140">4 </span><span class="sxs-lookup"><span data-stu-id="abd91-140">4</span></span></td>
<td><span data-ttu-id="abd91-141">Der Microsoft Defender for Endpoint-Dienst hat den Server unter <code>variable</code> kontaktiert.</span><span class="sxs-lookup"><span data-stu-id="abd91-141">Microsoft Defender for Endpoint service contacted the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="abd91-142">Variable = URL der Defender for Endpoint-Verarbeitungsserver.</span><span class="sxs-lookup"><span data-stu-id="abd91-142">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="abd91-143">Diese URL ist mit der In der Firewall- oder Netzwerkaktivität übereinstimmend.</span><span class="sxs-lookup"><span data-stu-id="abd91-143">This URL will match that seen in the Firewall or network activity.</span></span></td>
<td><span data-ttu-id="abd91-144">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-144">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-145">5 </span><span class="sxs-lookup"><span data-stu-id="abd91-145">5</span></span></td>
<td><span data-ttu-id="abd91-146">Microsoft Defender for Endpoint-Dienst konnte keine Verbindung mit dem Server unter <code>variable</code> herstellen.</span><span class="sxs-lookup"><span data-stu-id="abd91-146">Microsoft Defender for Endpoint service failed to connect to the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="abd91-147">Variable = URL der Defender for Endpoint-Verarbeitungsserver.</span><span class="sxs-lookup"><span data-stu-id="abd91-147">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="abd91-148">Der Dienst konnte die externen Verarbeitungsserver unter dieser URL nicht kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="abd91-148">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="abd91-149">Überprüfen Sie die Verbindung zur URL.</span><span class="sxs-lookup"><span data-stu-id="abd91-149">Check the connection to the URL.</span></span> <span data-ttu-id="abd91-150">Weitere Informationen finden Sie unter <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and internet connectivity</a>.</span><span class="sxs-lookup"><span data-stu-id="abd91-150">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-151">6 </span><span class="sxs-lookup"><span data-stu-id="abd91-151">6</span></span></td>
<td><span data-ttu-id="abd91-152">Der Microsoft Defender for Endpoint-Dienst ist nicht onboarded, und es wurden keine Onboardingparameter gefunden.</span><span class="sxs-lookup"><span data-stu-id="abd91-152">Microsoft Defender for Endpoint service is not onboarded and no onboarding parameters were found.</span></span></td>
<td><span data-ttu-id="abd91-153">Das Gerät wurde nicht ordnungsgemäß onboardiert und meldet nicht an das Portal.</span><span class="sxs-lookup"><span data-stu-id="abd91-153">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="abd91-154">Das Onboarding muss vor dem Starten des Diensts ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="abd91-154">Onboarding must be run before starting the service.</span></span><br>
<span data-ttu-id="abd91-155">Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="abd91-155">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="abd91-156">Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="abd91-156">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="abd91-157">Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboard Windows 10 devices</a>.</span><span class="sxs-lookup"><span data-stu-id="abd91-157">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-158">7 </span><span class="sxs-lookup"><span data-stu-id="abd91-158">7</span></span></td>
<td><span data-ttu-id="abd91-159">Der Microsoft Defender for Endpoint-Dienst konnte die Onboardingparameter nicht lesen.</span><span class="sxs-lookup"><span data-stu-id="abd91-159">Microsoft Defender for Endpoint service failed to read the onboarding parameters.</span></span> <span data-ttu-id="abd91-160">Fehler: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="abd91-160">Failure: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="abd91-161">Variable = detaillierte Fehlerbeschreibung.</span><span class="sxs-lookup"><span data-stu-id="abd91-161">Variable = detailed error description.</span></span> <span data-ttu-id="abd91-162">Das Gerät wurde nicht ordnungsgemäß onboardiert und meldet nicht an das Portal.</span><span class="sxs-lookup"><span data-stu-id="abd91-162">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="abd91-163">Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="abd91-163">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="abd91-164">Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="abd91-164">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="abd91-165">Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboard Windows 10 devices</a>.</span><span class="sxs-lookup"><span data-stu-id="abd91-165">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-166">8 </span><span class="sxs-lookup"><span data-stu-id="abd91-166">8</span></span></td>
<td><span data-ttu-id="abd91-167">Der Microsoft Defender for Endpoint-Dienst konnte seine Konfiguration nicht bereinigen.</span><span class="sxs-lookup"><span data-stu-id="abd91-167">Microsoft Defender for Endpoint service failed to clean its configuration.</span></span> <span data-ttu-id="abd91-168">Fehlercode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="abd91-168">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="abd91-169"><b>Während des Onboardings:</b> Fehler beim Bereinigen der Konfiguration während des Onboardings durch den Dienst.</span><span class="sxs-lookup"><span data-stu-id="abd91-169"><b>During onboarding:</b> The service failed to clean its configuration during the onboarding.</span></span> <span data-ttu-id="abd91-170">Der Onboardingprozess wird fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="abd91-170">The onboarding process continues.</span></span> <br><br> <span data-ttu-id="abd91-171"><b>Während des Offboardings:</b> Der Dienst konnte seine Konfiguration während des Offboardings nicht bereinigen.</span><span class="sxs-lookup"><span data-stu-id="abd91-171"><b>During offboarding:</b> The service failed to clean its configuration during the offboarding.</span></span> <span data-ttu-id="abd91-172">Der Offboardingvorgang wurde abgeschlossen, der Dienst wird jedoch weiterhin ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="abd91-172">The offboarding process finished but the service keeps running.</span></span>
 </td>
<td><span data-ttu-id="abd91-173"><b>Onboarding:</b> Keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-173"><b>Onboarding:</b> No action required.</span></span> <br><br> <span data-ttu-id="abd91-174"><b>Offboarding:</b> Starten Sie das System neu.</span><span class="sxs-lookup"><span data-stu-id="abd91-174"><b>Offboarding:</b> Reboot the system.</span></span><br>
<span data-ttu-id="abd91-175">Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboard Windows 10 devices</a>.</span><span class="sxs-lookup"><span data-stu-id="abd91-175">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-176">9 </span><span class="sxs-lookup"><span data-stu-id="abd91-176">9</span></span></td>
<td><span data-ttu-id="abd91-177">Der Microsoft Defender for Endpoint-Dienst konnte seinen Starttyp nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="abd91-177">Microsoft Defender for Endpoint service failed to change its start type.</span></span> <span data-ttu-id="abd91-178">Fehlercode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="abd91-178">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="abd91-179"><b>Während des Onboardings:</b> Das Gerät wurde nicht ordnungsgemäß onboardiert und meldet nicht an das Portal.</span><span class="sxs-lookup"><span data-stu-id="abd91-179"><b>During onboarding:</b> The device didn't onboard correctly and won't be reporting to the portal.</span></span> <br><br><span data-ttu-id="abd91-180"><b>Während des Offboardings:</b> Fehler beim Ändern des Dienststarttyps.</span><span class="sxs-lookup"><span data-stu-id="abd91-180"><b>During offboarding:</b> Failed to change the service start type.</span></span> <span data-ttu-id="abd91-181">Der Offboardingprozess wird fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="abd91-181">The offboarding process continues.</span></span> </td>
<td><span data-ttu-id="abd91-182">Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="abd91-182">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="abd91-183">Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="abd91-183">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="abd91-184">Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboard Windows 10 devices</a>.</span><span class="sxs-lookup"><span data-stu-id="abd91-184">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-185">10</span><span class="sxs-lookup"><span data-stu-id="abd91-185">10</span></span></td>
<td><span data-ttu-id="abd91-186">Der Microsoft Defender for Endpoint-Dienst konnte die Onboardinginformationen nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="abd91-186">Microsoft Defender for Endpoint service failed to persist the onboarding information.</span></span> <span data-ttu-id="abd91-187">Fehlercode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="abd91-187">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="abd91-188">Das Gerät wurde nicht ordnungsgemäß onboardiert und meldet nicht an das Portal.</span><span class="sxs-lookup"><span data-stu-id="abd91-188">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="abd91-189">Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="abd91-189">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="abd91-190">Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="abd91-190">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="abd91-191">Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboard Windows 10 devices</a>.</span><span class="sxs-lookup"><span data-stu-id="abd91-191">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-192">11</span><span class="sxs-lookup"><span data-stu-id="abd91-192">11</span></span></td>
<td><span data-ttu-id="abd91-193">Onboarding oder erneutes Onboarding des Defender for Endpoint-Diensts abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="abd91-193">Onboarding or re-onboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="abd91-194">Das Gerät wurde ordnungsgemäß onboardiert.</span><span class="sxs-lookup"><span data-stu-id="abd91-194">The device onboarded correctly.</span></span></td>
<td><span data-ttu-id="abd91-195">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-195">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="abd91-196">Es kann mehrere Stunden dauern, bis das Gerät im Portal angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="abd91-196">It may take several hours for the device to appear in the portal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-197">12 </span><span class="sxs-lookup"><span data-stu-id="abd91-197">12</span></span></td>
<td><span data-ttu-id="abd91-198">Microsoft Defender for Endpoint konnte die Standardkonfiguration nicht anwenden.</span><span class="sxs-lookup"><span data-stu-id="abd91-198">Microsoft Defender for Endpoint failed to apply the default configuration.</span></span></td>
<td><span data-ttu-id="abd91-199">Der Dienst konnte die Standardkonfiguration nicht anwenden.</span><span class="sxs-lookup"><span data-stu-id="abd91-199">Service was unable to apply the default configuration.</span></span></td>
<td><span data-ttu-id="abd91-200">Dieser Fehler sollte nach kurzer Zeit behoben werden.</span><span class="sxs-lookup"><span data-stu-id="abd91-200">This error should resolve after a short period of time.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-201">13</span><span class="sxs-lookup"><span data-stu-id="abd91-201">13</span></span></td>
<td><span data-ttu-id="abd91-202">Microsoft Defender for Endpoint-Geräte-ID berechnet: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="abd91-202">Microsoft Defender for Endpoint device ID calculated: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="abd91-203">Normaler Betriebsprozess.</span><span class="sxs-lookup"><span data-stu-id="abd91-203">Normal operating process.</span></span></td>
<td><span data-ttu-id="abd91-204">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-204">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-205">15 </span><span class="sxs-lookup"><span data-stu-id="abd91-205">15</span></span></td>
<td><span data-ttu-id="abd91-206">Microsoft Defender for Endpoint kann den Befehlskanal nicht mit DER URL starten: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="abd91-206">Microsoft Defender for Endpoint cannot start command channel with URL: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="abd91-207">Variable = URL der Defender for Endpoint-Verarbeitungsserver.</span><span class="sxs-lookup"><span data-stu-id="abd91-207">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="abd91-208">Der Dienst konnte die externen Verarbeitungsserver unter dieser URL nicht kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="abd91-208">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="abd91-209">Überprüfen Sie die Verbindung zur URL.</span><span class="sxs-lookup"><span data-stu-id="abd91-209">Check the connection to the URL.</span></span> <span data-ttu-id="abd91-210">Weitere Informationen finden Sie unter <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and internet connectivity</a>.</span><span class="sxs-lookup"><span data-stu-id="abd91-210">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-211">17 </span><span class="sxs-lookup"><span data-stu-id="abd91-211">17</span></span></td>
<td><span data-ttu-id="abd91-212">Der Microsoft Defender for Endpoint-Dienst konnte den Speicherort des Diensts für verbundene Benutzererfahrungen und Telemetrie nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="abd91-212">Microsoft Defender for Endpoint service failed to change the Connected User Experiences and Telemetry service location.</span></span> <span data-ttu-id="abd91-213">Fehlercode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="abd91-213">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="abd91-214">Beim Telemetriedienst ist Windows aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="abd91-214">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="abd91-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Stellen Sie sicher, dass der Diagnosedatendienst aktiviert ist.</a></span><span class="sxs-lookup"><span data-stu-id="abd91-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="abd91-216">Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="abd91-216">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="abd91-217">Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="abd91-217">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="abd91-218">Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboard Windows 10 devices</a>.</span><span class="sxs-lookup"><span data-stu-id="abd91-218">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-219">18 </span><span class="sxs-lookup"><span data-stu-id="abd91-219">18</span></span></td>
<td><span data-ttu-id="abd91-220">OOBE (Windows Welcome) ist abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="abd91-220">OOBE (Windows Welcome) is completed.</span></span></td>
<td><span data-ttu-id="abd91-221">Der Dienst wird erst gestartet, nachdem alle Windows installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="abd91-221">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="abd91-222">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-222">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-223">19</span><span class="sxs-lookup"><span data-stu-id="abd91-223">19</span></span></td>
<td><span data-ttu-id="abd91-224">OOBE (Windows Welcome) wurde noch nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="abd91-224">OOBE (Windows Welcome) has not yet completed.</span></span></td>
<td><span data-ttu-id="abd91-225">Der Dienst wird erst gestartet, nachdem alle Windows installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="abd91-225">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="abd91-226">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-226">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="abd91-227">Wenn dieser Fehler nach einem Systemneustart weiterhin auftritt, stellen Sie sicher, dass alle Windows vollständig installiert sind.</span><span class="sxs-lookup"><span data-stu-id="abd91-227">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-228">20</span><span class="sxs-lookup"><span data-stu-id="abd91-228">20</span></span></td>
<td><span data-ttu-id="abd91-229">Kann nicht warten, bis OOBE (Windows) abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="abd91-229">Cannot wait for OOBE (Windows Welcome) to complete.</span></span> <span data-ttu-id="abd91-230">Fehlercode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="abd91-230">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="abd91-231">Interner Fehler.</span><span class="sxs-lookup"><span data-stu-id="abd91-231">Internal error.</span></span></td>
<td><span data-ttu-id="abd91-232">Wenn dieser Fehler nach einem Systemneustart weiterhin auftritt, stellen Sie sicher, dass alle Windows vollständig installiert sind.</span><span class="sxs-lookup"><span data-stu-id="abd91-232">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-233">25</span><span class="sxs-lookup"><span data-stu-id="abd91-233">25</span></span></td>
<td><span data-ttu-id="abd91-234">Der Microsoft Defender for Endpoint-Dienst konnte den Integritätsstatus in der Registrierung nicht zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="abd91-234">Microsoft Defender for Endpoint service failed to reset health status in the registry.</span></span> <span data-ttu-id="abd91-235">Fehlercode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="abd91-235">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="abd91-236">Das Gerät wurde nicht ordnungsgemäß onboardiert.</span><span class="sxs-lookup"><span data-stu-id="abd91-236">The device didn't onboard correctly.</span></span>
<span data-ttu-id="abd91-237">Er wird dem Portal gemeldet, der Dienst wird jedoch möglicherweise nicht in SCCM oder der Registrierung registriert angezeigt.</span><span class="sxs-lookup"><span data-stu-id="abd91-237">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="abd91-238">Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="abd91-238">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="abd91-239">Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="abd91-239">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="abd91-240">Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboard Windows 10 devices</a>.</span><span class="sxs-lookup"><span data-stu-id="abd91-240">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-241">26</span><span class="sxs-lookup"><span data-stu-id="abd91-241">26</span></span></td>
<td><span data-ttu-id="abd91-242">Der Microsoft Defender for Endpoint-Dienst konnte den Onboardingstatus in der Registrierung nicht festlegen.</span><span class="sxs-lookup"><span data-stu-id="abd91-242">Microsoft Defender for Endpoint service failed to set the onboarding status in the registry.</span></span> <span data-ttu-id="abd91-243">Fehlercode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="abd91-243">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="abd91-244">Das Gerät wurde nicht ordnungsgemäß onboardiert.</span><span class="sxs-lookup"><span data-stu-id="abd91-244">The device didn't onboard correctly.</span></span><br>
<span data-ttu-id="abd91-245">Er wird dem Portal gemeldet, der Dienst wird jedoch möglicherweise nicht in SCCM oder der Registrierung registriert angezeigt.</span><span class="sxs-lookup"><span data-stu-id="abd91-245">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="abd91-246">Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="abd91-246">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="abd91-247">Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="abd91-247">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="abd91-248">Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboard Windows 10 devices</a>.</span><span class="sxs-lookup"><span data-stu-id="abd91-248">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-249">27</span><span class="sxs-lookup"><span data-stu-id="abd91-249">27</span></span></td>
<td><span data-ttu-id="abd91-250">Der Microsoft Defender for Endpoint-Dienst konnte den SENSE-bewussten Modus in einem Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="abd91-250">Microsoft Defender for Endpoint service failed to enable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="abd91-251">Fehler beim Onboardingprozess.</span><span class="sxs-lookup"><span data-stu-id="abd91-251">Onboarding process failed.</span></span> <span data-ttu-id="abd91-252">Fehlercode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="abd91-252">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="abd91-253">Normalerweise wird Microsoft Defender Antivirus einen besonderen passiven Zustand erhalten, wenn ein anderes Antischalwareprodukt in Echtzeit ordnungsgemäß auf dem Gerät ausgeführt wird und das Gerät defender for Endpoint meldet.</span><span class="sxs-lookup"><span data-stu-id="abd91-253">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="abd91-254">Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="abd91-254">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="abd91-255">Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="abd91-255">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="abd91-256">Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboard Windows 10 devices</a>.</span><span class="sxs-lookup"><span data-stu-id="abd91-256">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span><br>
<span data-ttu-id="abd91-257">Stellen Sie sicher, dass der Antischalwareschutz in Echtzeit ordnungsgemäß ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="abd91-257">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-258">28</span><span class="sxs-lookup"><span data-stu-id="abd91-258">28</span></span></td>
<td><span data-ttu-id="abd91-259">Fehler bei der Registrierung des Microsoft Defender for Endpoint Connected User Experiences and Telemetry Service.</span><span class="sxs-lookup"><span data-stu-id="abd91-259">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration failed.</span></span> <span data-ttu-id="abd91-260">Fehlercode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="abd91-260">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="abd91-261">Beim Telemetriedienst ist Windows aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="abd91-261">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="abd91-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Stellen Sie sicher, dass der Diagnosedatendienst aktiviert ist.</a></span><span class="sxs-lookup"><span data-stu-id="abd91-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="abd91-263">Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="abd91-263">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="abd91-264">Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="abd91-264">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="abd91-265">Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboard Windows 10 devices</a>.</span><span class="sxs-lookup"><span data-stu-id="abd91-265">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-266">29</span><span class="sxs-lookup"><span data-stu-id="abd91-266">29</span></span></td>
<td><span data-ttu-id="abd91-267">Fehler beim Lesen der offboarding-Parameter.</span><span class="sxs-lookup"><span data-stu-id="abd91-267">Failed to read the offboarding parameters.</span></span> <span data-ttu-id="abd91-268">Fehlertyp: %1, Fehlercode: %2, Beschreibung: %3</span><span class="sxs-lookup"><span data-stu-id="abd91-268">Error type: %1, Error code: %2, Description: %3</span></span> </td>
<td><span data-ttu-id="abd91-269">Dieses Ereignis tritt auf, wenn das System&#39;offboarding-Parameter nicht lesen kann.</span><span class="sxs-lookup"><span data-stu-id="abd91-269">This event occurs when the system can&#39;t read the offboarding parameters.</span></span></td>
<td><span data-ttu-id="abd91-270">Stellen Sie sicher, dass das Gerät über Internetzugriff verfügt, und führen Sie dann den gesamten Offboardingvorgang erneut aus.</span><span class="sxs-lookup"><span data-stu-id="abd91-270">Ensure the device has Internet access, then run the entire offboarding process again.</span></span> <span data-ttu-id="abd91-271">Stellen Sie sicher, dass das offboarding-Paket nicht abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="abd91-271">Ensure the offboarding package hasn't expired.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-272">30</span><span class="sxs-lookup"><span data-stu-id="abd91-272">30</span></span></td>
<td><span data-ttu-id="abd91-273">Der Microsoft Defender for Endpoint-Dienst konnte den SENSE-benachrichtigungsmodus in einem Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="abd91-273">Microsoft Defender for Endpoint service failed to disable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="abd91-274">Fehlercode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="abd91-274">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="abd91-275">Normalerweise wird Microsoft Defender Antivirus einen besonderen passiven Zustand erhalten, wenn ein anderes Antischalwareprodukt in Echtzeit ordnungsgemäß auf dem Gerät ausgeführt wird und das Gerät defender for Endpoint meldet.</span><span class="sxs-lookup"><span data-stu-id="abd91-275">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="abd91-276">Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="abd91-276">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="abd91-277">Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="abd91-277">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="abd91-278">Siehe <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboarding Windows 10 Geräte</a></span><span class="sxs-lookup"><span data-stu-id="abd91-278">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a></span></span><br>
<span data-ttu-id="abd91-279">Stellen Sie sicher, dass der Antischalwareschutz in Echtzeit ordnungsgemäß ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="abd91-279">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-280">31</span><span class="sxs-lookup"><span data-stu-id="abd91-280">31</span></span></td>
<td><span data-ttu-id="abd91-281">Die Registrierung des Microsoft Defender for Endpoint Connected User Experiences and Telemetry Service ist fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="abd91-281">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service unregistration failed.</span></span> <span data-ttu-id="abd91-282">Fehlercode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="abd91-282">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="abd91-283">Beim Onboarding ist beim Windows ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="abd91-283">An error occurred with the Windows telemetry service during onboarding.</span></span> <span data-ttu-id="abd91-284">Der Offboardingprozess wird fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="abd91-284">The offboarding process continues.</span></span></td>
<td><span data-ttu-id="abd91-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Überprüfen Sie mit dem Telemetriedienst Windows Fehler.</a></span><span class="sxs-lookup"><span data-stu-id="abd91-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Check for errors with the Windows telemetry service</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-286">32</span><span class="sxs-lookup"><span data-stu-id="abd91-286">32</span></span></td>
<td><span data-ttu-id="abd91-287">Der Microsoft Defender for Endpoint-Dienst konnte nicht anfordern, dass er sich nach dem Offboardingvorgang selbst beendet.</span><span class="sxs-lookup"><span data-stu-id="abd91-287">Microsoft Defender for Endpoint service failed to request to stop itself after offboarding process.</span></span> <span data-ttu-id="abd91-288">Fehlercode: %1</span><span class="sxs-lookup"><span data-stu-id="abd91-288">Failure code: %1</span></span></td>
<td><span data-ttu-id="abd91-289">Beim Offboarding ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="abd91-289">An error occurred during offboarding.</span></span></td>
<td><span data-ttu-id="abd91-290">Starten Sie das Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="abd91-290">Reboot the device.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-291">33</span><span class="sxs-lookup"><span data-stu-id="abd91-291">33</span></span></td>
<td><span data-ttu-id="abd91-292">Microsoft Defender for Endpoint-Dienst konnte die SENSE-GUID nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="abd91-292">Microsoft Defender for Endpoint service failed to persist SENSE GUID.</span></span> <span data-ttu-id="abd91-293">Fehlercode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="abd91-293">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="abd91-294">Ein eindeutiger Bezeichner wird verwendet, um jedes Gerät zu repräsentieren, das an das Portal meldet.</span><span class="sxs-lookup"><span data-stu-id="abd91-294">A unique identifier is used to represent each device that is reporting to the portal.</span></span><br>
<span data-ttu-id="abd91-295">Wenn der Bezeichner nicht beibehalten wird, wird das gleiche Gerät möglicherweise zweimal im Portal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="abd91-295">If the identifier doesn't persist, the same device might appear twice in the portal.</span></span></td>
<td><span data-ttu-id="abd91-296">Überprüfen Sie die Registrierungsberechtigungen auf dem Gerät, um sicherzustellen, dass der Dienst die Registrierung aktualisieren kann.</span><span class="sxs-lookup"><span data-stu-id="abd91-296">Check registry permissions on the device to ensure the service can update the registry.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-297">34</span><span class="sxs-lookup"><span data-stu-id="abd91-297">34</span></span></td>
<td><span data-ttu-id="abd91-298">Der Microsoft Defender for Endpoint-Dienst konnte sich nicht selbst als Abhängigkeit vom Dienst für verbundene Benutzererfahrungen und Telemetrie hinzufügen, wodurch der Onboardingprozess fehlschlagen konnte.</span><span class="sxs-lookup"><span data-stu-id="abd91-298">Microsoft Defender for Endpoint service failed to add itself as a dependency on the Connected User Experiences and Telemetry service, causing onboarding process to fail.</span></span> <span data-ttu-id="abd91-299">Fehlercode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="abd91-299">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="abd91-300">Beim Telemetriedienst ist Windows aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="abd91-300">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="abd91-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Stellen Sie sicher, dass der Diagnosedatendienst aktiviert ist.</a></span><span class="sxs-lookup"><span data-stu-id="abd91-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="abd91-302">Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="abd91-302">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="abd91-303">Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="abd91-303">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="abd91-304">Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboard Windows 10 devices</a>.</span><span class="sxs-lookup"><span data-stu-id="abd91-304">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-305">35</span><span class="sxs-lookup"><span data-stu-id="abd91-305">35</span></span></td>
<td><span data-ttu-id="abd91-306">Der Microsoft Defender for Endpoint-Dienst konnte sich nicht selbst als Abhängigkeit vom Dienst für verbundene Benutzererfahrungen und Telemetrie entfernen.</span><span class="sxs-lookup"><span data-stu-id="abd91-306">Microsoft Defender for Endpoint service failed to remove itself as a dependency on the Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="abd91-307">Fehlercode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="abd91-307">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="abd91-308">Beim Telemetriedienst Windows während des Offboardings ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="abd91-308">An error occurred with the Windows telemetry service during offboarding.</span></span> <span data-ttu-id="abd91-309">Der Offboardingprozess wird fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="abd91-309">The offboarding process continues.</span></span>
</td>
<td><span data-ttu-id="abd91-310">Überprüfen Sie mit dem Diagnosedatendienst Windows Fehler.</span><span class="sxs-lookup"><span data-stu-id="abd91-310">Check for errors with the Windows diagnostic data service.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-311">36</span><span class="sxs-lookup"><span data-stu-id="abd91-311">36</span></span></td>
<td><span data-ttu-id="abd91-312">Die Registrierung des Microsoft Defender for Endpoint Connected User Experiences and Telemetry Service ist erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="abd91-312">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration succeeded.</span></span> <span data-ttu-id="abd91-313">Fertigstellungscode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="abd91-313">Completion code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="abd91-314">Die Registrierung von Defender for Endpoint beim Dienst für verbundene Benutzererfahrungen und Telemetrie wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="abd91-314">Registering Defender for Endpoint with the Connected User Experiences and Telemetry service completed successfully.</span></span></td>
<td><span data-ttu-id="abd91-315">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-315">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-316">37</span><span class="sxs-lookup"><span data-stu-id="abd91-316">37</span></span></td>
<td><span data-ttu-id="abd91-317">Microsoft Defender for Endpoint A module is about to exceed its quota.</span><span class="sxs-lookup"><span data-stu-id="abd91-317">Microsoft Defender for Endpoint A module is about to exceed its quota.</span></span> <span data-ttu-id="abd91-318">Modul: %1, Kontingent: {%2} {%3}, Prozentsatz der Kontingentauslastung: %4.</span><span class="sxs-lookup"><span data-stu-id="abd91-318">Module: %1, Quota: {%2} {%3}, Percentage of quota utilization: %4.</span></span></td>
<td><span data-ttu-id="abd91-319">Das gerät hat fast das zugewiesene Kontingent des aktuellen 24-Stunden-Fensters verwendet.</span><span class="sxs-lookup"><span data-stu-id="abd91-319">The device has almost used its allocated quota of the current 24-hour window.</span></span> <span data-ttu-id="abd91-320">Es wird gedrosselt.</span><span class="sxs-lookup"><span data-stu-id="abd91-320">It’s about to be throttled.</span></span></td>
<td><span data-ttu-id="abd91-321">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-321">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-322">38</span><span class="sxs-lookup"><span data-stu-id="abd91-322">38</span></span></td>
<td><span data-ttu-id="abd91-323">Die Netzwerkverbindung wird als niedrig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="abd91-323">Network connection is identified as low.</span></span> <span data-ttu-id="abd91-324">Microsoft Defender for Endpoint kontaktiert den Server alle %1 Minuten.</span><span class="sxs-lookup"><span data-stu-id="abd91-324">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="abd91-325">Gemessene Verbindung: %2, Internet verfügbar: %3, kostenloses Netzwerk verfügbar: %4.</span><span class="sxs-lookup"><span data-stu-id="abd91-325">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="abd91-326">Das Gerät verwendet ein gemessenes/kostenpflichtiges Netzwerk und kontaktiert den Server seltener.</span><span class="sxs-lookup"><span data-stu-id="abd91-326">The device is using a metered/paid network and will be contacting the server less frequently.</span></span></td>
<td><span data-ttu-id="abd91-327">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-327">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-328">39</span><span class="sxs-lookup"><span data-stu-id="abd91-328">39</span></span></td>
<td><span data-ttu-id="abd91-329">Die Netzwerkverbindung wird als normal identifiziert.</span><span class="sxs-lookup"><span data-stu-id="abd91-329">Network connection is identified as normal.</span></span> <span data-ttu-id="abd91-330">Microsoft Defender for Endpoint kontaktiert den Server alle %1 Minuten.</span><span class="sxs-lookup"><span data-stu-id="abd91-330">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="abd91-331">Gemessene Verbindung: %2, Internet verfügbar: %3, kostenloses Netzwerk verfügbar: %4.</span><span class="sxs-lookup"><span data-stu-id="abd91-331">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="abd91-332">Das Gerät verwendet keine meterierte/kostenpflichtige Verbindung und kontaktiert den Server wie gewohnt.</span><span class="sxs-lookup"><span data-stu-id="abd91-332">The device isn't using a metered/paid connection and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="abd91-333">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-333">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-334">40</span><span class="sxs-lookup"><span data-stu-id="abd91-334">40</span></span></td>
<td><span data-ttu-id="abd91-335">Der Akkuzustand wird als niedrig gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="abd91-335">Battery state is identified as low.</span></span> <span data-ttu-id="abd91-336">Microsoft Defender for Endpoint kontaktiert den Server alle %1 Minuten.</span><span class="sxs-lookup"><span data-stu-id="abd91-336">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="abd91-337">Akkuzustand: %2.</span><span class="sxs-lookup"><span data-stu-id="abd91-337">Battery state: %2.</span></span></td>
<td><span data-ttu-id="abd91-338">Das Gerät hat einen niedrigen Akkustand und kontaktiert den Server seltener.</span><span class="sxs-lookup"><span data-stu-id="abd91-338">The device has low battery level and will contact the server less frequently.</span></span></td>
<td><span data-ttu-id="abd91-339">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-339">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-340">41</span><span class="sxs-lookup"><span data-stu-id="abd91-340">41</span></span></td>
<td><span data-ttu-id="abd91-341">Der Akkuzustand wird als normal identifiziert.</span><span class="sxs-lookup"><span data-stu-id="abd91-341">Battery state is identified as normal.</span></span> <span data-ttu-id="abd91-342">Microsoft Defender for Endpoint kontaktiert den Server alle %1 Minuten.</span><span class="sxs-lookup"><span data-stu-id="abd91-342">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="abd91-343">Akkuzustand: %2.</span><span class="sxs-lookup"><span data-stu-id="abd91-343">Battery state: %2.</span></span></td>
<td><span data-ttu-id="abd91-344">Das Gerät hat keinen niedrigen Akkustand und kontaktiert den Server wie gewohnt.</span><span class="sxs-lookup"><span data-stu-id="abd91-344">The device doesn’t have low battery level and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="abd91-345">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-345">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-346">42</span><span class="sxs-lookup"><span data-stu-id="abd91-346">42</span></span></td>
<td><span data-ttu-id="abd91-347">Microsoft Defender for Endpoint-Komponente konnte keine Aktion ausführen.</span><span class="sxs-lookup"><span data-stu-id="abd91-347">Microsoft Defender for Endpoint component failed to perform action.</span></span> <span data-ttu-id="abd91-348">Komponente: %1, Aktion: %2, Ausnahmetyp: %3, Ausnahmemeldung: %4</span><span class="sxs-lookup"><span data-stu-id="abd91-348">Component: %1, Action: %2, Exception Type: %3, Exception message: %4</span></span></td>
<td><span data-ttu-id="abd91-349">Interner Fehler.</span><span class="sxs-lookup"><span data-stu-id="abd91-349">Internal error.</span></span> <span data-ttu-id="abd91-350">Der Dienst konnte nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="abd91-350">The service failed to start.</span></span></td>
<td><span data-ttu-id="abd91-351">Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="abd91-351">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-352">43</span><span class="sxs-lookup"><span data-stu-id="abd91-352">43</span></span></td>
<td><span data-ttu-id="abd91-353">Microsoft Defender for Endpoint-Komponente konnte keine Aktion ausführen.</span><span class="sxs-lookup"><span data-stu-id="abd91-353">Microsoft Defender for Endpoint component failed to perform action.</span></span> <span data-ttu-id="abd91-354">Komponente: %1, Aktion: %2, Ausnahmetyp: %3, Ausnahmefehler: %4, Ausnahmemeldung: %5</span><span class="sxs-lookup"><span data-stu-id="abd91-354">Component: %1, Action: %2, Exception Type: %3, Exception Error: %4, Exception message: %5</span></span></td>
<td><span data-ttu-id="abd91-355">Interner Fehler.</span><span class="sxs-lookup"><span data-stu-id="abd91-355">Internal error.</span></span> <span data-ttu-id="abd91-356">Der Dienst konnte nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="abd91-356">The service failed to start.</span></span></td>
<td><span data-ttu-id="abd91-357">Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="abd91-357">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-358">44</span><span class="sxs-lookup"><span data-stu-id="abd91-358">44</span></span></td>
<td><span data-ttu-id="abd91-359">Offboarding des Defender for Endpoint-Diensts abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="abd91-359">Offboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="abd91-360">Der Dienst wurde offboarded.</span><span class="sxs-lookup"><span data-stu-id="abd91-360">The service was offboarded.</span></span></td>
<td><span data-ttu-id="abd91-361">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-361">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-362">45</span><span class="sxs-lookup"><span data-stu-id="abd91-362">45</span></span></td>
<td><span data-ttu-id="abd91-363">Fehler beim Registrieren und Starten der Ereignisverfolgungssitzung [%1].</span><span class="sxs-lookup"><span data-stu-id="abd91-363">Failed to register and to start the event trace session [%1].</span></span> <span data-ttu-id="abd91-364">Fehlercode: %2</span><span class="sxs-lookup"><span data-stu-id="abd91-364">Error code: %2</span></span></td>
<td><span data-ttu-id="abd91-365">Beim Starten des Diensts beim Erstellen einer ETW-Sitzung ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="abd91-365">An error occurred on service startup while creating ETW session.</span></span> <span data-ttu-id="abd91-366">Dies führte zu einem Fehler beim Starten des Diensts.</span><span class="sxs-lookup"><span data-stu-id="abd91-366">This caused service start-up failure.</span></span></td>
<td><span data-ttu-id="abd91-367">Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="abd91-367">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-368">46</span><span class="sxs-lookup"><span data-stu-id="abd91-368">46</span></span></td>
<td><span data-ttu-id="abd91-369">Fehler beim Registrieren und Starten der Ereignisverfolgungssitzung [%1] aufgrund fehlender Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="abd91-369">Failed to register and start the event trace session [%1] due to lack of resources.</span></span> <span data-ttu-id="abd91-370">Fehlercode: %2.</span><span class="sxs-lookup"><span data-stu-id="abd91-370">Error code: %2.</span></span> <span data-ttu-id="abd91-371">Dies liegt wahrscheinlich daran, dass zu viele aktive Ereignisverfolgungssitzungen sind.</span><span class="sxs-lookup"><span data-stu-id="abd91-371">This is most likely because there are too many active event trace sessions.</span></span> <span data-ttu-id="abd91-372">Der Dienst wird in 1 Minute erneut versuchen.</span><span class="sxs-lookup"><span data-stu-id="abd91-372">The service will retry in 1 minute.</span></span></td>
<td><span data-ttu-id="abd91-373">Fehler beim Starten des Diensts beim Erstellen einer ETW-Sitzung aufgrund fehlender Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="abd91-373">An error occurred on service startup while creating ETW session due to lack of resources.</span></span> <span data-ttu-id="abd91-374">Der Dienst wurde gestartet und wird ausgeführt, es wird jedoch erst ein Sensorereignis berichtet, wenn die ETW-Sitzung gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="abd91-374">The service started and is running, but won't report any sensor event until the ETW session is started.</span></span></td>
<td><span data-ttu-id="abd91-375">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-375">Normal operating notification; no action required.</span></span> <span data-ttu-id="abd91-376">Der Dienst versucht, die Sitzung jede Minute zu starten.</span><span class="sxs-lookup"><span data-stu-id="abd91-376">The service will try to start the session every minute.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-377">47</span><span class="sxs-lookup"><span data-stu-id="abd91-377">47</span></span></td>
<td><span data-ttu-id="abd91-378">Die Ereignisverfolgungssitzung wurde erfolgreich registriert und gestartet – nach vorherigen fehlgeschlagenen Versuchen wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="abd91-378">Successfully registered and started the event trace session - recovered after previous failed attempts.</span></span></td>
<td><span data-ttu-id="abd91-379">Dieses Ereignis folgt dem vorherigen Ereignis nach dem erfolgreichen Starten der ETW-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="abd91-379">This event follows the previous event after successfully starting of the ETW session.</span></span></td>
<td><span data-ttu-id="abd91-380">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-380">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="abd91-381">48</span><span class="sxs-lookup"><span data-stu-id="abd91-381">48</span></span></td>
<td><span data-ttu-id="abd91-382">Fehler beim Hinzufügen eines Anbieters [%1] zur Ereignisverfolgungssitzung [%2].</span><span class="sxs-lookup"><span data-stu-id="abd91-382">Failed to add a provider [%1] to event trace session [%2].</span></span> <span data-ttu-id="abd91-383">Fehlercode: %3.</span><span class="sxs-lookup"><span data-stu-id="abd91-383">Error code: %3.</span></span> <span data-ttu-id="abd91-384">Dies bedeutet, dass Ereignisse von diesem Anbieter nicht gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="abd91-384">This means that events from this provider will not be reported.</span></span></td>
<td><span data-ttu-id="abd91-385">Fehler beim Hinzufügen eines Anbieters zur ETW-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="abd91-385">Failed to add a provider to ETW session.</span></span> <span data-ttu-id="abd91-386">Aus diesem Grund werden die Anbieterereignisse nicht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="abd91-386">As a result, the provider events aren’t reported.</span></span></td>
<td><span data-ttu-id="abd91-387">Überprüfen Sie den Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="abd91-387">Check the error code.</span></span> <span data-ttu-id="abd91-388">Wenn der Fehler weiterhin auftritt, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="abd91-388">If the error persists contact Support.</span></span></td>
</tr>
</tr>
<tr>
   <td><span data-ttu-id="abd91-389">49</span><span class="sxs-lookup"><span data-stu-id="abd91-389">49</span></span></td>
   <td><span data-ttu-id="abd91-390">Ungültiger Cloudkonfigurationsbefehl empfangen und ignoriert.</span><span class="sxs-lookup"><span data-stu-id="abd91-390">Invalid cloud configuration command received and ignored.</span></span> <span data-ttu-id="abd91-391">Version: %1, Status: %2, Fehlercode: %3, Meldung: %4</span><span class="sxs-lookup"><span data-stu-id="abd91-391">Version: %1, status: %2, error code: %3, message: %4</span></span></td>
   <td><span data-ttu-id="abd91-392">Vom Clouddienst wurde eine ungültige Konfigurationsdatei empfangen, die ignoriert wurde.</span><span class="sxs-lookup"><span data-stu-id="abd91-392">Received an invalid configuration file from the cloud service that was ignored.</span></span></td>
   <td><span data-ttu-id="abd91-393">Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="abd91-393">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-394">50</span><span class="sxs-lookup"><span data-stu-id="abd91-394">50</span></span></td>
   <td><span data-ttu-id="abd91-395">Neue Cloudkonfiguration wurde erfolgreich angewendet.</span><span class="sxs-lookup"><span data-stu-id="abd91-395">New cloud configuration applied successfully.</span></span> <span data-ttu-id="abd91-396">Version: %1.</span><span class="sxs-lookup"><span data-stu-id="abd91-396">Version: %1.</span></span></td>
   <td><span data-ttu-id="abd91-397">Eine neue Konfiguration wurde erfolgreich vom Clouddienst angewendet.</span><span class="sxs-lookup"><span data-stu-id="abd91-397">Successfully applied a new configuration from the cloud service.</span></span></td>
   <td><span data-ttu-id="abd91-398">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-398">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-399">51</span><span class="sxs-lookup"><span data-stu-id="abd91-399">51</span></span></td>
   <td><span data-ttu-id="abd91-400">Neue Cloudkonfiguration konnte nicht angewendet werden, Version: %1.</span><span class="sxs-lookup"><span data-stu-id="abd91-400">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="abd91-401">Die letzte bekannte gute Konfiguration, Version %2, wurde erfolgreich angewendet.</span><span class="sxs-lookup"><span data-stu-id="abd91-401">Successfully applied the last known good configuration, version %2.</span></span></td>
   <td><span data-ttu-id="abd91-402">Vom Clouddienst wurde eine ungültige Konfigurationsdatei empfangen.</span><span class="sxs-lookup"><span data-stu-id="abd91-402">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="abd91-403">Die letzte bekannte gute Konfiguration wurde erfolgreich angewendet.</span><span class="sxs-lookup"><span data-stu-id="abd91-403">Last known good configuration was applied successfully.</span></span></td>
   <td><span data-ttu-id="abd91-404">Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="abd91-404">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-405">52</span><span class="sxs-lookup"><span data-stu-id="abd91-405">52</span></span></td>
   <td><span data-ttu-id="abd91-406">Neue Cloudkonfiguration konnte nicht angewendet werden, Version: %1.</span><span class="sxs-lookup"><span data-stu-id="abd91-406">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="abd91-407">Außerdem konnte die letzte bekannte gute Konfiguration, Version %2, nicht angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="abd91-407">Also failed to apply last known good configuration, version %2.</span></span> <span data-ttu-id="abd91-408">Die Standardkonfiguration wurde erfolgreich angewendet.</span><span class="sxs-lookup"><span data-stu-id="abd91-408">Successfully applied the default configuration.</span></span></td>
   <td><span data-ttu-id="abd91-409">Vom Clouddienst wurde eine ungültige Konfigurationsdatei empfangen.</span><span class="sxs-lookup"><span data-stu-id="abd91-409">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="abd91-410">Fehler beim Anwenden der letzten als gut bekannten Konfiguration – und die Standardkonfiguration wurde angewendet.</span><span class="sxs-lookup"><span data-stu-id="abd91-410">Failed to apply the last known good configuration - and the default configuration was applied.</span></span></td>
   <td><span data-ttu-id="abd91-411">Der Dienst versucht, innerhalb von 5 Minuten eine neue Konfigurationsdatei herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="abd91-411">The service will attempt to download a new configuration file within 5 minutes.</span></span> <span data-ttu-id="abd91-412">Wenn das Ereignis nicht #50 , wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="abd91-412">If you don't see event #50 - contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-413">53</span><span class="sxs-lookup"><span data-stu-id="abd91-413">53</span></span></td>
   <td><span data-ttu-id="abd91-414">Cloudkonfiguration, die aus dem beständigen Speicher geladen wird, Version: %1.</span><span class="sxs-lookup"><span data-stu-id="abd91-414">Cloud configuration loaded from persistent storage, version: %1.</span></span></td>
   <td><span data-ttu-id="abd91-415">Die Konfiguration wurde beim Starten des Diensts aus dem beständigen Speicher geladen.</span><span class="sxs-lookup"><span data-stu-id="abd91-415">The configuration was loaded from persistent storage on service startup.</span></span></td>
   <td><span data-ttu-id="abd91-416">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-416">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-417">55</span><span class="sxs-lookup"><span data-stu-id="abd91-417">55</span></span></td>
   <td><span data-ttu-id="abd91-418">Fehler beim Erstellen des Secure ETW-Autologgers.</span><span class="sxs-lookup"><span data-stu-id="abd91-418">Failed to create the Secure ETW autologger.</span></span> <span data-ttu-id="abd91-419">Fehlercode: %1</span><span class="sxs-lookup"><span data-stu-id="abd91-419">Failure code: %1</span></span></td>
   <td><span data-ttu-id="abd91-420">Fehler beim Erstellen des sicheren ETW-Loggers.</span><span class="sxs-lookup"><span data-stu-id="abd91-420">Failed to create the secure ETW logger.</span></span></td>
   <td><span data-ttu-id="abd91-421">Starten Sie das Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="abd91-421">Reboot the device.</span></span> <span data-ttu-id="abd91-422">Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="abd91-422">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-423">56</span><span class="sxs-lookup"><span data-stu-id="abd91-423">56</span></span></td>
   <td><span data-ttu-id="abd91-424">Fehler beim Entfernen des Secure ETW-Autologgers.</span><span class="sxs-lookup"><span data-stu-id="abd91-424">Failed to remove the Secure ETW autologger.</span></span> <span data-ttu-id="abd91-425">Fehlercode: %1</span><span class="sxs-lookup"><span data-stu-id="abd91-425">Failure code: %1</span></span></td>
   <td><span data-ttu-id="abd91-426">Fehler beim Entfernen der sicheren ETW-Sitzung beim Offboarding.</span><span class="sxs-lookup"><span data-stu-id="abd91-426">Failed to remove the secure ETW session on offboarding.</span></span></td>
   <td><span data-ttu-id="abd91-427">Wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="abd91-427">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-428">57</span><span class="sxs-lookup"><span data-stu-id="abd91-428">57</span></span></td>
   <td><span data-ttu-id="abd91-429">Erfassen einer Momentaufnahme des Computers zur Problembehandlung.</span><span class="sxs-lookup"><span data-stu-id="abd91-429">Capturing a snapshot of the machine for troubleshooting purposes.</span></span></td>
   <td><span data-ttu-id="abd91-430">Ein Untersuchungspaket, das auch als Forensikpaket bezeichnet wird, wird gesammelt.</span><span class="sxs-lookup"><span data-stu-id="abd91-430">An investigation package, also known as forensics package, is being collected.</span></span></td>
   <td><span data-ttu-id="abd91-431">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-431">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-432">59</span><span class="sxs-lookup"><span data-stu-id="abd91-432">59</span></span></td>
   <td><span data-ttu-id="abd91-433">Startbefehl: %1</span><span class="sxs-lookup"><span data-stu-id="abd91-433">Starting command: %1</span></span></td>
   <td><span data-ttu-id="abd91-434">Starten der Ausführung des Antwortbefehls.</span><span class="sxs-lookup"><span data-stu-id="abd91-434">Starting response command execution.</span></span></td>
   <td><span data-ttu-id="abd91-435">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-435">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-436">60</span><span class="sxs-lookup"><span data-stu-id="abd91-436">60</span></span></td>
   <td><span data-ttu-id="abd91-437">Befehl "%1" konnte nicht ausgeführt werden, Fehler: %2.</span><span class="sxs-lookup"><span data-stu-id="abd91-437">Failed to run command %1, error: %2.</span></span></td>
   <td><span data-ttu-id="abd91-438">Antwortbefehl konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="abd91-438">Failed to execute response command.</span></span></td>
   <td><span data-ttu-id="abd91-439">Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="abd91-439">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-440">61</span><span class="sxs-lookup"><span data-stu-id="abd91-440">61</span></span></td>
   <td><span data-ttu-id="abd91-441">Parameter des Datensammlungsbefehls sind ungültig: SasUri: %1, compressionLevel: %2.</span><span class="sxs-lookup"><span data-stu-id="abd91-441">Data collection command parameters are invalid: SasUri: %1, compressionLevel: %2.</span></span></td>
   <td><span data-ttu-id="abd91-442">Fehler beim Lesen oder Analysieren der Datensammlungsbefehlsargumente (ungültige Argumente).</span><span class="sxs-lookup"><span data-stu-id="abd91-442">Failed to read or parse the data collection command arguments (invalid arguments).</span></span></td>
   <td><span data-ttu-id="abd91-443">Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="abd91-443">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-444">62</span><span class="sxs-lookup"><span data-stu-id="abd91-444">62</span></span></td>
   <td><span data-ttu-id="abd91-445">Fehler beim Starten des Diensts für verbundene Benutzererfahrungen und Telemetrie.</span><span class="sxs-lookup"><span data-stu-id="abd91-445">Failed to start Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="abd91-446">Fehlercode: %1</span><span class="sxs-lookup"><span data-stu-id="abd91-446">Failure code: %1</span></span></td>
   <td><span data-ttu-id="abd91-447">Der Dienst für verbundene Benutzererfahrungen und Telemetrie (Diagtrack) konnte nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="abd91-447">Connected User Experiences and Telemetry (diagtrack) service failed to start.</span></span> <span data-ttu-id="abd91-448">Telemetriedaten von Nicht-Microsoft Defender for Endpoint werden nicht von diesem Computer gesendet.</span><span class="sxs-lookup"><span data-stu-id="abd91-448">Non-Microsoft Defender for Endpoint telemetry won't be sent from this machine.</span></span></td>
   <td><span data-ttu-id="abd91-449">Weitere Hinweise zur Problembehandlung finden Sie im Ereignisprotokoll: Microsoft-Windows-UniversalTelemetryClient/Operational.</span><span class="sxs-lookup"><span data-stu-id="abd91-449">Look for more troubleshooting hints in the event log: Microsoft-Windows-UniversalTelemetryClient/Operational.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-450">63</span><span class="sxs-lookup"><span data-stu-id="abd91-450">63</span></span></td>
   <td><span data-ttu-id="abd91-451">Aktualisieren des Starttyps des externen Diensts.</span><span class="sxs-lookup"><span data-stu-id="abd91-451">Updating the start type of external service.</span></span> <span data-ttu-id="abd91-452">Name: %1, tatsächlicher Starttyp: %2, erwarteter Starttyp: %3, Exitcode: %4</span><span class="sxs-lookup"><span data-stu-id="abd91-452">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="abd91-453">Der Starttyp des externen Diensts wurde aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="abd91-453">Updated start type of the external service.</span></span></td>
   <td><span data-ttu-id="abd91-454">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-454">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-455">64</span><span class="sxs-lookup"><span data-stu-id="abd91-455">64</span></span></td>
   <td><span data-ttu-id="abd91-456">Starten des beendeten externen Diensts.</span><span class="sxs-lookup"><span data-stu-id="abd91-456">Starting stopped external service.</span></span> <span data-ttu-id="abd91-457">Name: %1, Exitcode: %2</span><span class="sxs-lookup"><span data-stu-id="abd91-457">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="abd91-458">Starten eines externen Diensts.</span><span class="sxs-lookup"><span data-stu-id="abd91-458">Starting an external service.</span></span></td>
   <td><span data-ttu-id="abd91-459">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-459">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-460">65</span><span class="sxs-lookup"><span data-stu-id="abd91-460">65</span></span></td>
   <td><span data-ttu-id="abd91-461">Microsoft Security Events Component Minifilter-Treiber konnte nicht geladen werden.</span><span class="sxs-lookup"><span data-stu-id="abd91-461">Failed to load Microsoft Security Events Component Minifilter driver.</span></span> <span data-ttu-id="abd91-462">Fehlercode: %1</span><span class="sxs-lookup"><span data-stu-id="abd91-462">Failure code: %1</span></span></td>
   <td><span data-ttu-id="abd91-463">Fehler beim Laden MsSecFlt.sys Dateisystem-Minifilters.</span><span class="sxs-lookup"><span data-stu-id="abd91-463">Failed to load MsSecFlt.sys filesystem minifilter.</span></span></td>
   <td><span data-ttu-id="abd91-464">Starten Sie das Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="abd91-464">Reboot the device.</span></span> <span data-ttu-id="abd91-465">Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="abd91-465">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-466">66</span><span class="sxs-lookup"><span data-stu-id="abd91-466">66</span></span></td>
   <td><span data-ttu-id="abd91-467">Richtlinienupdate: Latenzmodus – %1</span><span class="sxs-lookup"><span data-stu-id="abd91-467">Policy update: Latency mode - %1</span></span></td>
   <td><span data-ttu-id="abd91-468">Die C&C-Verbindungshäufigkeitsrichtlinie wurde aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="abd91-468">The C&C connection frequency policy was updated.</span></span></td>
   <td><span data-ttu-id="abd91-469">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-469">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-470">68</span><span class="sxs-lookup"><span data-stu-id="abd91-470">68</span></span></td>
   <td><span data-ttu-id="abd91-471">Der Starttyp des Diensts ist unerwartet.</span><span class="sxs-lookup"><span data-stu-id="abd91-471">The start type of the service is unexpected.</span></span> <span data-ttu-id="abd91-472">Dienstname: %1, tatsächlicher Starttyp: %2, erwarteter Starttyp: %3</span><span class="sxs-lookup"><span data-stu-id="abd91-472">Service name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="abd91-473">Unerwarteter Starttyp des externen Diensts.</span><span class="sxs-lookup"><span data-stu-id="abd91-473">Unexpected external service start type.</span></span></td>
   <td><span data-ttu-id="abd91-474">Fix the external service start type.</span><span class="sxs-lookup"><span data-stu-id="abd91-474">Fix the external service start type.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-475">69</span><span class="sxs-lookup"><span data-stu-id="abd91-475">69</span></span></td>
   <td><span data-ttu-id="abd91-476">Der Dienst wird beendet.</span><span class="sxs-lookup"><span data-stu-id="abd91-476">The service is stopped.</span></span> <span data-ttu-id="abd91-477">Dienstname: %1</span><span class="sxs-lookup"><span data-stu-id="abd91-477">Service name: %1</span></span></td>
   <td><span data-ttu-id="abd91-478">Der externe Dienst wird beendet.</span><span class="sxs-lookup"><span data-stu-id="abd91-478">The external service is stopped.</span></span></td>
   <td><span data-ttu-id="abd91-479">Starten Sie den externen Dienst.</span><span class="sxs-lookup"><span data-stu-id="abd91-479">Start the external service.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-480">70</span><span class="sxs-lookup"><span data-stu-id="abd91-480">70</span></span></td>
   <td><span data-ttu-id="abd91-481">Richtlinienupdate: Beispielsammlung zulassen – %1</span><span class="sxs-lookup"><span data-stu-id="abd91-481">Policy update: Allow sample collection - %1</span></span></td>
   <td><span data-ttu-id="abd91-482">Die Beispielsammlungsrichtlinie wurde aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="abd91-482">The sample collection policy was updated.</span></span></td>
   <td><span data-ttu-id="abd91-483">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-483">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-484">71</span><span class="sxs-lookup"><span data-stu-id="abd91-484">71</span></span></td>
   <td><span data-ttu-id="abd91-485">Befehl konnte erfolgreich ausgeführt werden: %1</span><span class="sxs-lookup"><span data-stu-id="abd91-485">Succeeded to run command: %1</span></span></td>
   <td><span data-ttu-id="abd91-486">Der Befehl wurde erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="abd91-486">The command was executed successfully.</span></span></td>
   <td><span data-ttu-id="abd91-487">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-487">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-488">72</span><span class="sxs-lookup"><span data-stu-id="abd91-488">72</span></span></td>
   <td><span data-ttu-id="abd91-489">Es wurde versucht, den ersten vollständigen Computerprofilbericht zu senden.</span><span class="sxs-lookup"><span data-stu-id="abd91-489">Tried to send first full machine profile report.</span></span> <span data-ttu-id="abd91-490">Ergebniscode: %1</span><span class="sxs-lookup"><span data-stu-id="abd91-490">Result code: %1</span></span></td>
   <td><span data-ttu-id="abd91-491">Nur Information.</span><span class="sxs-lookup"><span data-stu-id="abd91-491">Informational only.</span></span></td>
   <td><span data-ttu-id="abd91-492">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-492">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-493">73</span><span class="sxs-lookup"><span data-stu-id="abd91-493">73</span></span></td>
   <td><span data-ttu-id="abd91-494">Sinn beim Starten der Plattform: %1</span><span class="sxs-lookup"><span data-stu-id="abd91-494">Sense starting for platform: %1</span></span></td>
   <td><span data-ttu-id="abd91-495">Nur Information.</span><span class="sxs-lookup"><span data-stu-id="abd91-495">Informational only.</span></span></td>
   <td><span data-ttu-id="abd91-496">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-496">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-497">74</span><span class="sxs-lookup"><span data-stu-id="abd91-497">74</span></span></td>
   <td><span data-ttu-id="abd91-498">Das Gerätetag in der Registrierung überschreitet die Längenbeschränkung.</span><span class="sxs-lookup"><span data-stu-id="abd91-498">Device tag in registry exceeds length limit.</span></span> <span data-ttu-id="abd91-499">Tagname: %2.</span><span class="sxs-lookup"><span data-stu-id="abd91-499">Tag name: %2.</span></span> <span data-ttu-id="abd91-500">Längenbeschränkung: %1.</span><span class="sxs-lookup"><span data-stu-id="abd91-500">Length limit: %1.</span></span></td>
   <td><span data-ttu-id="abd91-501">Das Gerätetag überschreitet den Längengrenzwert.</span><span class="sxs-lookup"><span data-stu-id="abd91-501">The device tag exceeds the length limit.</span></span></td>
   <td><span data-ttu-id="abd91-502">Verwenden Sie ein kürzeres Gerätetag.</span><span class="sxs-lookup"><span data-stu-id="abd91-502">Use a shorter device tag.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-503">81</span><span class="sxs-lookup"><span data-stu-id="abd91-503">81</span></span></td>
   <td><span data-ttu-id="abd91-504">Fehler beim Erstellen des AutomatischenLoggers von Microsoft Defender for Endpoint ETW.</span><span class="sxs-lookup"><span data-stu-id="abd91-504">Failed to create Microsoft Defender for Endpoint ETW autologger.</span></span> <span data-ttu-id="abd91-505">Fehlercode: %1</span><span class="sxs-lookup"><span data-stu-id="abd91-505">Failure code: %1</span></span></td>
   <td><span data-ttu-id="abd91-506">Fehler beim Erstellen der ETW-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="abd91-506">Failed to create the ETW session.</span></span></td>
   <td><span data-ttu-id="abd91-507">Starten Sie das Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="abd91-507">Reboot the device.</span></span> <span data-ttu-id="abd91-508">Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="abd91-508">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-509">82</span><span class="sxs-lookup"><span data-stu-id="abd91-509">82</span></span></td>
   <td><span data-ttu-id="abd91-510">Fehler beim Entfernen des Autologgers von Microsoft Defender for Endpoint ETW.</span><span class="sxs-lookup"><span data-stu-id="abd91-510">Failed to remove Microsoft Defender for Endpoint ETW autologger.</span></span> <span data-ttu-id="abd91-511">Fehlercode: %1</span><span class="sxs-lookup"><span data-stu-id="abd91-511">Failure code: %1</span></span></td>
   <td><span data-ttu-id="abd91-512">Fehler beim Löschen der ETW-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="abd91-512">Failed to delete the ETW session.</span></span></td>
   <td><span data-ttu-id="abd91-513">Wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="abd91-513">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-514">84</span><span class="sxs-lookup"><span data-stu-id="abd91-514">84</span></span></td>
   <td><span data-ttu-id="abd91-515">Legen Sie Windows Defender Antivirus ausführungsmodus ein.</span><span class="sxs-lookup"><span data-stu-id="abd91-515">Set Windows Defender Antivirus running mode.</span></span> <span data-ttu-id="abd91-516">Erzwingen des passiven Modus: %1, Ergebniscode: %2.</span><span class="sxs-lookup"><span data-stu-id="abd91-516">Force passive mode: %1, result code: %2.</span></span></td>
   <td><span data-ttu-id="abd91-517">Festlegen des laufenden Defender-Modus (aktiv oder passiv).</span><span class="sxs-lookup"><span data-stu-id="abd91-517">Set defender running mode (active or passive).</span></span></td>
   <td><span data-ttu-id="abd91-518">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-518">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-519">85</span><span class="sxs-lookup"><span data-stu-id="abd91-519">85</span></span></td>
   <td><span data-ttu-id="abd91-520">Fehler beim Auslösen der ausführbaren Datei "Microsoft Defender for Endpoint".</span><span class="sxs-lookup"><span data-stu-id="abd91-520">Failed to trigger Microsoft Defender for Endpoint executable.</span></span> <span data-ttu-id="abd91-521">Fehlercode: %1</span><span class="sxs-lookup"><span data-stu-id="abd91-521">Failure code: %1</span></span></td>
   <td><span data-ttu-id="abd91-522">Fehler beim Ausführen der ausführbaren SenseIR-Datei.</span><span class="sxs-lookup"><span data-stu-id="abd91-522">Starring SenseIR executable failed.</span></span></td>
   <td><span data-ttu-id="abd91-523">Starten Sie das Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="abd91-523">Reboot the device.</span></span> <span data-ttu-id="abd91-524">Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="abd91-524">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-525">86</span><span class="sxs-lookup"><span data-stu-id="abd91-525">86</span></span></td>
   <td><span data-ttu-id="abd91-526">Beim erneuten Starten wurde der externe Dienst beendet, der eingerichtet werden sollte.</span><span class="sxs-lookup"><span data-stu-id="abd91-526">Starting again stopped external service that should be up.</span></span> <span data-ttu-id="abd91-527">Name: %1, Exitcode: %2</span><span class="sxs-lookup"><span data-stu-id="abd91-527">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="abd91-528">Starten Sie den externen Dienst erneut.</span><span class="sxs-lookup"><span data-stu-id="abd91-528">Starting the external service again.</span></span></td>
   <td><span data-ttu-id="abd91-529">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-529">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-530">87</span><span class="sxs-lookup"><span data-stu-id="abd91-530">87</span></span></td>
   <td><span data-ttu-id="abd91-531">Der externe Dienst kann nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="abd91-531">Cannot start the external service.</span></span> <span data-ttu-id="abd91-532">Name: %1</span><span class="sxs-lookup"><span data-stu-id="abd91-532">Name: %1</span></span></td>
   <td><span data-ttu-id="abd91-533">Fehler beim Starten des externen Diensts.</span><span class="sxs-lookup"><span data-stu-id="abd91-533">Failed to start the external service.</span></span></td>
   <td><span data-ttu-id="abd91-534">Wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="abd91-534">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-535">88</span><span class="sxs-lookup"><span data-stu-id="abd91-535">88</span></span></td>
   <td><span data-ttu-id="abd91-536">Aktualisieren des Starttyps des externen Diensts erneut.</span><span class="sxs-lookup"><span data-stu-id="abd91-536">Updating the start type of external service again.</span></span> <span data-ttu-id="abd91-537">Name: %1, tatsächlicher Starttyp: %2, erwarteter Starttyp: %3, Exitcode: %4</span><span class="sxs-lookup"><span data-stu-id="abd91-537">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="abd91-538">Der Starttyp des externen Diensts wurde aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="abd91-538">Updated the start type of the external service.</span></span></td>
   <td><span data-ttu-id="abd91-539">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-539">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-540">89</span><span class="sxs-lookup"><span data-stu-id="abd91-540">89</span></span></td>
   <td><span data-ttu-id="abd91-541">Der Starttyp des externen Diensts kann nicht aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="abd91-541">Cannot update the start type of external service.</span></span> <span data-ttu-id="abd91-542">Name: %1, tatsächlicher Starttyp: %2, erwarteter Starttyp: %3</span><span class="sxs-lookup"><span data-stu-id="abd91-542">Name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="abd91-543">Der Starttyp des externen Diensts kann nicht aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="abd91-543">Can't update the start type of the external service.</span></span></td>
   <td><span data-ttu-id="abd91-544">Wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="abd91-544">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-545">90</span><span class="sxs-lookup"><span data-stu-id="abd91-545">90</span></span></td>
   <td><span data-ttu-id="abd91-546">Fehler beim Konfigurieren des System Guard-Laufzeitmonitors für die Verbindung mit dem Clouddienst in der geografischen Region "%1".</span><span class="sxs-lookup"><span data-stu-id="abd91-546">Failed to configure System Guard Runtime Monitor to connect to cloud service in geo-region %1.</span></span> <span data-ttu-id="abd91-547">Fehlercode: %2</span><span class="sxs-lookup"><span data-stu-id="abd91-547">Failure code: %2</span></span></td>
   <td><span data-ttu-id="abd91-548">System Guard Runtime Monitor sendet keine Nachweisdaten an den Clouddienst.</span><span class="sxs-lookup"><span data-stu-id="abd91-548">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="abd91-549">Überprüfen Sie die Berechtigungen im Registerpfad: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span><span class="sxs-lookup"><span data-stu-id="abd91-549">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="abd91-550">Wenn keine Probleme auftreten, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="abd91-550">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-551">91</span><span class="sxs-lookup"><span data-stu-id="abd91-551">91</span></span></td>
   <td><span data-ttu-id="abd91-552">Fehler beim Entfernen von Informationen zur geografischen Region des System Guard-Runtime-Monitors.</span><span class="sxs-lookup"><span data-stu-id="abd91-552">Failed to remove System Guard Runtime Monitor geo-region information.</span></span> <span data-ttu-id="abd91-553">Fehlercode: %1</span><span class="sxs-lookup"><span data-stu-id="abd91-553">Failure code: %1</span></span></td>
   <td><span data-ttu-id="abd91-554">System Guard Runtime Monitor sendet keine Nachweisdaten an den Clouddienst.</span><span class="sxs-lookup"><span data-stu-id="abd91-554">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="abd91-555">Überprüfen Sie die Berechtigungen im Registerpfad: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span><span class="sxs-lookup"><span data-stu-id="abd91-555">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="abd91-556">Wenn keine Probleme auftreten, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="abd91-556">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-557">92</span><span class="sxs-lookup"><span data-stu-id="abd91-557">92</span></span></td>
   <td><span data-ttu-id="abd91-558">Beenden des Sendens des Cyberdatenkontingents des Sensors, da das Datenkontingent überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="abd91-558">Stopping sending sensor cyber data quota because data quota is exceeded.</span></span> <span data-ttu-id="abd91-559">Wird das Senden fortgesetzt, sobald der Kontingentzeitraum vergeht.</span><span class="sxs-lookup"><span data-stu-id="abd91-559">Will resume sending once quota period passes.</span></span> <span data-ttu-id="abd91-560">Zustandsmaske: %1</span><span class="sxs-lookup"><span data-stu-id="abd91-560">State Mask: %1</span></span></td>
   <td><span data-ttu-id="abd91-561">Drosselungsgrenzwert überschreiten.</span><span class="sxs-lookup"><span data-stu-id="abd91-561">Exceed throttling limit.</span></span></td>
   <td><span data-ttu-id="abd91-562">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-562">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-563">93</span><span class="sxs-lookup"><span data-stu-id="abd91-563">93</span></span></td>
   <td><span data-ttu-id="abd91-564">Fortsetzen des Sendens von Sensor-Cyberdaten.</span><span class="sxs-lookup"><span data-stu-id="abd91-564">Resuming sending sensor cyber data.</span></span> <span data-ttu-id="abd91-565">Zustandsmaske: %1</span><span class="sxs-lookup"><span data-stu-id="abd91-565">State Mask: %1</span></span></td>
   <td><span data-ttu-id="abd91-566">Fortsetzen der Cyberdatenübermittlung.</span><span class="sxs-lookup"><span data-stu-id="abd91-566">Resume cyber data submission.</span></span></td>
   <td><span data-ttu-id="abd91-567">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-567">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-568">94</span><span class="sxs-lookup"><span data-stu-id="abd91-568">94</span></span></td>
   <td><span data-ttu-id="abd91-569">Die ausführbare Datei "Microsoft Defender for Endpoint" wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="abd91-569">Microsoft Defender for Endpoint executable has started</span></span></td>
   <td><span data-ttu-id="abd91-570">Die ausführbare Datei SenseCE wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="abd91-570">The SenseCE executable has started.</span></span></td>
   <td><span data-ttu-id="abd91-571">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-571">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-572">95</span><span class="sxs-lookup"><span data-stu-id="abd91-572">95</span></span></td>
   <td><span data-ttu-id="abd91-573">Die ausführbare Datei "Microsoft Defender for Endpoint" wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="abd91-573">Microsoft Defender for Endpoint executable has ended</span></span></td>
   <td><span data-ttu-id="abd91-574">Die ausführbare Datei SenseCE wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="abd91-574">The SenseCE executable has ended.</span></span></td>
   <td><span data-ttu-id="abd91-575">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-575">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-576">96</span><span class="sxs-lookup"><span data-stu-id="abd91-576">96</span></span></td>
   <td><span data-ttu-id="abd91-577">Microsoft Defender for Endpoint Init hat aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="abd91-577">Microsoft Defender for Endpoint Init has called.</span></span> <span data-ttu-id="abd91-578">Ergebniscode: %2</span><span class="sxs-lookup"><span data-stu-id="abd91-578">Result code: %2</span></span></td>
   <td><span data-ttu-id="abd91-579">Die ausführbare SenseCE-Datei hat die MCE-Initialisierung aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="abd91-579">The SenseCE executable has called MCE initialization.</span></span></td>
   <td><span data-ttu-id="abd91-580">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-580">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-581">97</span><span class="sxs-lookup"><span data-stu-id="abd91-581">97</span></span></td>
   <td><span data-ttu-id="abd91-582">Es gibt Konnektivitätsprobleme mit der Cloud für das DLP-Szenario</span><span class="sxs-lookup"><span data-stu-id="abd91-582">There are connectivity issues to the Cloud for the DLP scenario</span></span></td>
   <td><span data-ttu-id="abd91-583">Es gibt Netzwerkkonnektivitätsprobleme, die sich auf den DLP-Klassifizierungsfluss auswirken.</span><span class="sxs-lookup"><span data-stu-id="abd91-583">There are network connectivity issues that affect the DLP classification flow.</span></span></td>
   <td><span data-ttu-id="abd91-584">Überprüfen Sie die Netzwerkkonnektivität.</span><span class="sxs-lookup"><span data-stu-id="abd91-584">Check the network connectivity.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-585">98</span><span class="sxs-lookup"><span data-stu-id="abd91-585">98</span></span></td>
   <td><span data-ttu-id="abd91-586">Die Konnektivität mit der Cloud für das DLP-Szenario wurde wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="abd91-586">The connectivity to the Cloud for the DLP scenario has been restored</span></span></td>
   <td><span data-ttu-id="abd91-587">Die Verbindung mit dem Netzwerk wurde wiederhergestellt, und der DLP-Klassifizierungsfluss kann fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="abd91-587">The connectivity to the network was restored and the DLP classification flow can continue.</span></span></td>
   <td><span data-ttu-id="abd91-588">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-588">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-589">99</span><span class="sxs-lookup"><span data-stu-id="abd91-589">99</span></span></td>
   <td><span data-ttu-id="abd91-590">Bei der Kommunikation mit dem Server ist der folgende Fehler aufgetreten: (%1).</span><span class="sxs-lookup"><span data-stu-id="abd91-590">Sense has encountered the following error while communicating with server: (%1).</span></span> <span data-ttu-id="abd91-591">Ergebnis: (%2)</span><span class="sxs-lookup"><span data-stu-id="abd91-591">Result: (%2)</span></span></td>
   <td><span data-ttu-id="abd91-592">Ein Kommunikationsfehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="abd91-592">A communication error occurred.</span></span></td>
   <td><span data-ttu-id="abd91-593">Überprüfen Sie die folgenden Ereignisse im Ereignisprotokoll auf weitere Details.</span><span class="sxs-lookup"><span data-stu-id="abd91-593">Check the following events in the event log for further details.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-594">100</span><span class="sxs-lookup"><span data-stu-id="abd91-594">100</span></span></td>
   <td><span data-ttu-id="abd91-595">Die ausführbare Microsoft Defender for Endpoint-Datei konnte nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="abd91-595">Microsoft Defender for Endpoint executable failed to start.</span></span> <span data-ttu-id="abd91-596">Fehlercode: %1</span><span class="sxs-lookup"><span data-stu-id="abd91-596">Failure code: %1</span></span></td>
   <td><span data-ttu-id="abd91-597">Die ausführbare Datei SenseCE konnte nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="abd91-597">The SenseCE executable has failed to start.</span></span></td>
   <td><span data-ttu-id="abd91-598">Starten Sie das Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="abd91-598">Reboot the device.</span></span> <span data-ttu-id="abd91-599">Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="abd91-599">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-600">102</span><span class="sxs-lookup"><span data-stu-id="abd91-600">102</span></span></td>
   <td><span data-ttu-id="abd91-601">Microsoft Defender for Endpoint Network Detection and Response executable has started</span><span class="sxs-lookup"><span data-stu-id="abd91-601">Microsoft Defender for Endpoint Network Detection and Response executable has started</span></span></td>
   <td><span data-ttu-id="abd91-602">Die ausführbare Datei SenseNdr wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="abd91-602">The SenseNdr executable has started.</span></span></td>
   <td><span data-ttu-id="abd91-603">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-603">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="abd91-604">103</span><span class="sxs-lookup"><span data-stu-id="abd91-604">103</span></span></td>
   <td><span data-ttu-id="abd91-605">Microsoft Defender for Endpoint Network Detection and Response executable has ended</span><span class="sxs-lookup"><span data-stu-id="abd91-605">Microsoft Defender for Endpoint Network Detection and Response executable has ended</span></span></td>
   <td><span data-ttu-id="abd91-606">Die ausführbare Datei SenseNdr wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="abd91-606">The SenseNdr executable has ended.</span></span></td>
   <td><span data-ttu-id="abd91-607">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="abd91-607">Normal operating notification; no action required.</span></span></td>
</tr>
</tbody>
</table>

><span data-ttu-id="abd91-608">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="abd91-608">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="abd91-609">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="abd91-609">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="abd91-610">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="abd91-610">Related topics</span></span>
- [<span data-ttu-id="abd91-611">Onboarding von Windows 10-Geräten</span><span class="sxs-lookup"><span data-stu-id="abd91-611">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="abd91-612">Konfigurieren von Geräteproxy- und Internetverbindungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="abd91-612">Configure device proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="abd91-613">Problembehandlung von Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="abd91-613">Troubleshoot Microsoft Defender for Endpoint</span></span>](troubleshoot-onboarding.md)
