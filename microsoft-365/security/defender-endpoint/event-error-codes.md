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
# <a name="review-events-and-errors-using-event-viewer"></a><span data-ttu-id="0c487-104">Überprüfen von Ereignissen und Fehlern mithilfe der Ereignisanzeige</span><span class="sxs-lookup"><span data-stu-id="0c487-104">Review events and errors using Event Viewer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0c487-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0c487-105">**Applies to:**</span></span>
- <span data-ttu-id="0c487-106">Ereignisanzeige</span><span class="sxs-lookup"><span data-stu-id="0c487-106">Event Viewer</span></span>
- [<span data-ttu-id="0c487-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0c487-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="0c487-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0c487-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="0c487-109">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="0c487-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0c487-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="0c487-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="0c487-111">Sie können Ereignis-IDs in der [Ereignisanzeige auf](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) einzelnen Geräten überprüfen.</span><span class="sxs-lookup"><span data-stu-id="0c487-111">You can review event IDs in the [Event Viewer](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) on individual devices.</span></span>

<span data-ttu-id="0c487-112">Wenn Geräte beispielsweise nicht in der Liste Geräte angezeigt **werden,** müssen Sie möglicherweise nach Ereignis-IDs auf den Geräten suchen.</span><span class="sxs-lookup"><span data-stu-id="0c487-112">For example, if devices aren't appearing in the **Devices list**, you might need to look for event IDs on the devices.</span></span> <span data-ttu-id="0c487-113">Anschließend können Sie diese Tabelle verwenden, um weitere Schritte zur Problembehandlung zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="0c487-113">You can then use this table to determine further troubleshooting steps.</span></span>

<span data-ttu-id="0c487-114">**Öffnen Sie die Ereignisanzeige, und suchen Sie das Microsoft Defender for Endpoint-Dienstereignisprotokoll:**</span><span class="sxs-lookup"><span data-stu-id="0c487-114">**Open Event Viewer and find the Microsoft Defender for Endpoint service event log:**</span></span>

1. <span data-ttu-id="0c487-115">Klicken **Sie im** Menü Windows auf Start, geben Sie **Ereignisanzeige ein,** und drücken Sie die **EINGABETASTE.**</span><span class="sxs-lookup"><span data-stu-id="0c487-115">Click **Start** on the Windows menu, type **Event Viewer**, and press **Enter**.</span></span>

2. <span data-ttu-id="0c487-116">Führen Sie in der Protokollliste unter **Protokollzusammenfassung** einen Bildlauf durch, bis **Microsoft-Windows-SENSE/Operational angezeigt wird.**</span><span class="sxs-lookup"><span data-stu-id="0c487-116">In the log list, under **Log Summary**, scroll until you see **Microsoft-Windows-SENSE/Operational**.</span></span> <span data-ttu-id="0c487-117">Doppelklicken Sie auf das Element, um das Protokoll zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0c487-117">Double-click the item to open the log.</span></span>

   <span data-ttu-id="0c487-118">a.</span><span class="sxs-lookup"><span data-stu-id="0c487-118">a.</span></span>  <span data-ttu-id="0c487-119">Sie können auch auf das Protokoll zugreifen, indem Sie **Anwendungen und Dienstprotokolle** Microsoft Windows SENSE erweitern  >    >    >   und auf **Betriebs klicken.**</span><span class="sxs-lookup"><span data-stu-id="0c487-119">You can also access the log by expanding **Applications and Services Logs** > **Microsoft** > **Windows** > **SENSE** and click on **Operational**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0c487-120">SENSE ist der interne Name, der verwendet wird, um auf den Verhaltenssensor zu verweisen, der Microsoft Defender for Endpoint unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0c487-120">SENSE is the internal name used to refer to the behavioral sensor that powers Microsoft Defender for Endpoint.</span></span>

3. <span data-ttu-id="0c487-121">Vom Dienst aufgezeichnete Ereignisse werden im Protokoll angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0c487-121">Events recorded by the service will appear in the log.</span></span> <span data-ttu-id="0c487-122">Eine Liste der vom Dienst aufgezeichneten Ereignisse finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="0c487-122">See the following table for a list of events recorded by the service.</span></span>

<table>
<tbody style="vertical-align:top;">
<tr>
<th><span data-ttu-id="0c487-123">Ereigniskennung</span><span class="sxs-lookup"><span data-stu-id="0c487-123">Event ID</span></span></th>
<th><span data-ttu-id="0c487-124">Message</span><span class="sxs-lookup"><span data-stu-id="0c487-124">Message</span></span></th>
<th><span data-ttu-id="0c487-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0c487-125">Description</span></span></th>
<th><span data-ttu-id="0c487-126">Aktion</span><span class="sxs-lookup"><span data-stu-id="0c487-126">Action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="0c487-127">1</span><span class="sxs-lookup"><span data-stu-id="0c487-127">1</span></span></td>
<td><span data-ttu-id="0c487-128">Microsoft Defender for Endpoint Service gestartet (Version <code>variable</code> ).</span><span class="sxs-lookup"><span data-stu-id="0c487-128">Microsoft Defender for Endpoint service started (Version <code>variable</code>).</span></span></td>
<td><span data-ttu-id="0c487-129">Tritt während des Systemstarts, heruntergefahren und während des Onboardings auf.</span><span class="sxs-lookup"><span data-stu-id="0c487-129">Occurs during system startup, shut down, and during onboarding.</span></span></td>
<td><span data-ttu-id="0c487-130">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-130">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-131">2</span><span class="sxs-lookup"><span data-stu-id="0c487-131">2</span></span></td>
<td><span data-ttu-id="0c487-132">Herunterfahren des Microsoft Defender for Endpoint-Diensts.</span><span class="sxs-lookup"><span data-stu-id="0c487-132">Microsoft Defender for Endpoint service shutdown.</span></span></td>
<td><span data-ttu-id="0c487-133">Tritt auf, wenn das Gerät heruntergefahren oder offboarded wird.</span><span class="sxs-lookup"><span data-stu-id="0c487-133">Occurs when the device is shut down or offboarded.</span></span></td>
<td><span data-ttu-id="0c487-134">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-134">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-135">3</span><span class="sxs-lookup"><span data-stu-id="0c487-135">3</span></span></td>
<td><span data-ttu-id="0c487-136">Der Microsoft Defender for Endpoint-Dienst konnte nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="0c487-136">Microsoft Defender for Endpoint service failed to start.</span></span> <span data-ttu-id="0c487-137">Fehlercode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="0c487-137">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="0c487-138">Der Dienst wurde nicht gestartet.</span><span class="sxs-lookup"><span data-stu-id="0c487-138">Service didn't start.</span></span></td>
<td><span data-ttu-id="0c487-139">Überprüfen Sie andere Nachrichten, um mögliche Ursachen und Schritte zur Problembehandlung zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="0c487-139">Review other messages to determine possible cause and troubleshooting steps.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-140">4 </span><span class="sxs-lookup"><span data-stu-id="0c487-140">4</span></span></td>
<td><span data-ttu-id="0c487-141">Der Microsoft Defender for Endpoint-Dienst hat den Server unter <code>variable</code> kontaktiert.</span><span class="sxs-lookup"><span data-stu-id="0c487-141">Microsoft Defender for Endpoint service contacted the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="0c487-142">Variable = URL der Defender for Endpoint-Verarbeitungsserver.</span><span class="sxs-lookup"><span data-stu-id="0c487-142">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="0c487-143">Diese URL ist mit der In der Firewall- oder Netzwerkaktivität übereinstimmend.</span><span class="sxs-lookup"><span data-stu-id="0c487-143">This URL will match that seen in the Firewall or network activity.</span></span></td>
<td><span data-ttu-id="0c487-144">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-144">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-145">5 </span><span class="sxs-lookup"><span data-stu-id="0c487-145">5</span></span></td>
<td><span data-ttu-id="0c487-146">Microsoft Defender for Endpoint-Dienst konnte keine Verbindung mit dem Server unter <code>variable</code> herstellen.</span><span class="sxs-lookup"><span data-stu-id="0c487-146">Microsoft Defender for Endpoint service failed to connect to the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="0c487-147">Variable = URL der Defender for Endpoint-Verarbeitungsserver.</span><span class="sxs-lookup"><span data-stu-id="0c487-147">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="0c487-148">Der Dienst konnte die externen Verarbeitungsserver unter dieser URL nicht kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="0c487-148">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="0c487-149">Überprüfen Sie die Verbindung zur URL.</span><span class="sxs-lookup"><span data-stu-id="0c487-149">Check the connection to the URL.</span></span> <span data-ttu-id="0c487-150">Weitere Informationen finden Sie unter <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and internet connectivity</a>.</span><span class="sxs-lookup"><span data-stu-id="0c487-150">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-151">6 </span><span class="sxs-lookup"><span data-stu-id="0c487-151">6</span></span></td>
<td><span data-ttu-id="0c487-152">Der Microsoft Defender for Endpoint-Dienst ist nicht onboarded, und es wurden keine Onboardingparameter gefunden.</span><span class="sxs-lookup"><span data-stu-id="0c487-152">Microsoft Defender for Endpoint service is not onboarded and no onboarding parameters were found.</span></span></td>
<td><span data-ttu-id="0c487-153">Das Gerät wurde nicht ordnungsgemäß onboardiert und meldet nicht an das Portal.</span><span class="sxs-lookup"><span data-stu-id="0c487-153">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="0c487-154">Das Onboarding muss vor dem Starten des Diensts ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0c487-154">Onboarding must be run before starting the service.</span></span><br>
<span data-ttu-id="0c487-155">Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="0c487-155">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="0c487-156">Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0c487-156">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="0c487-157">Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></span><span class="sxs-lookup"><span data-stu-id="0c487-157">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-158">7 </span><span class="sxs-lookup"><span data-stu-id="0c487-158">7</span></span></td>
<td><span data-ttu-id="0c487-159">Der Microsoft Defender for Endpoint-Dienst konnte die Onboardingparameter nicht lesen.</span><span class="sxs-lookup"><span data-stu-id="0c487-159">Microsoft Defender for Endpoint service failed to read the onboarding parameters.</span></span> <span data-ttu-id="0c487-160">Fehler: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="0c487-160">Failure: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="0c487-161">Variable = detaillierte Fehlerbeschreibung.</span><span class="sxs-lookup"><span data-stu-id="0c487-161">Variable = detailed error description.</span></span> <span data-ttu-id="0c487-162">Das Gerät wurde nicht ordnungsgemäß onboardiert und meldet nicht an das Portal.</span><span class="sxs-lookup"><span data-stu-id="0c487-162">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="0c487-163">Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="0c487-163">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="0c487-164">Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0c487-164">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="0c487-165">Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></span><span class="sxs-lookup"><span data-stu-id="0c487-165">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-166">8 </span><span class="sxs-lookup"><span data-stu-id="0c487-166">8</span></span></td>
<td><span data-ttu-id="0c487-167">Der Microsoft Defender for Endpoint-Dienst konnte seine Konfiguration nicht bereinigen.</span><span class="sxs-lookup"><span data-stu-id="0c487-167">Microsoft Defender for Endpoint service failed to clean its configuration.</span></span> <span data-ttu-id="0c487-168">Fehlercode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="0c487-168">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="0c487-169"><b>Während des Onboardings:</b> Fehler beim Bereinigen der Konfiguration während des Onboardings durch den Dienst.</span><span class="sxs-lookup"><span data-stu-id="0c487-169"><b>During onboarding:</b> The service failed to clean its configuration during the onboarding.</span></span> <span data-ttu-id="0c487-170">Der Onboardingprozess wird fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="0c487-170">The onboarding process continues.</span></span> <br><br> <span data-ttu-id="0c487-171"><b>Während des Offboardings:</b> Der Dienst konnte seine Konfiguration während des Offboardings nicht bereinigen.</span><span class="sxs-lookup"><span data-stu-id="0c487-171"><b>During offboarding:</b> The service failed to clean its configuration during the offboarding.</span></span> <span data-ttu-id="0c487-172">Der Offboardingvorgang wurde abgeschlossen, der Dienst wird jedoch weiterhin ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0c487-172">The offboarding process finished but the service keeps running.</span></span>
 </td>
<td><span data-ttu-id="0c487-173"><b>Onboarding:</b> Keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-173"><b>Onboarding:</b> No action required.</span></span> <br><br> <span data-ttu-id="0c487-174"><b>Offboarding:</b> Starten Sie das System neu.</span><span class="sxs-lookup"><span data-stu-id="0c487-174"><b>Offboarding:</b> Reboot the system.</span></span><br>
<span data-ttu-id="0c487-175">Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></span><span class="sxs-lookup"><span data-stu-id="0c487-175">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-176">9 </span><span class="sxs-lookup"><span data-stu-id="0c487-176">9</span></span></td>
<td><span data-ttu-id="0c487-177">Der Microsoft Defender for Endpoint-Dienst konnte seinen Starttyp nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="0c487-177">Microsoft Defender for Endpoint service failed to change its start type.</span></span> <span data-ttu-id="0c487-178">Fehlercode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="0c487-178">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="0c487-179"><b>Während des Onboardings:</b> Das Gerät wurde nicht ordnungsgemäß onboardiert und meldet nicht an das Portal.</span><span class="sxs-lookup"><span data-stu-id="0c487-179"><b>During onboarding:</b> The device didn't onboard correctly and won't be reporting to the portal.</span></span> <br><br><span data-ttu-id="0c487-180"><b>Während des Offboardings:</b> Fehler beim Ändern des Dienststarttyps.</span><span class="sxs-lookup"><span data-stu-id="0c487-180"><b>During offboarding:</b> Failed to change the service start type.</span></span> <span data-ttu-id="0c487-181">Der Offboardingprozess wird fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="0c487-181">The offboarding process continues.</span></span> </td>
<td><span data-ttu-id="0c487-182">Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="0c487-182">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="0c487-183">Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0c487-183">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="0c487-184">Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></span><span class="sxs-lookup"><span data-stu-id="0c487-184">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-185">10  </span><span class="sxs-lookup"><span data-stu-id="0c487-185">10</span></span></td>
<td><span data-ttu-id="0c487-186">Der Microsoft Defender for Endpoint-Dienst konnte die Onboardinginformationen nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="0c487-186">Microsoft Defender for Endpoint service failed to persist the onboarding information.</span></span> <span data-ttu-id="0c487-187">Fehlercode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="0c487-187">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="0c487-188">Das Gerät wurde nicht ordnungsgemäß onboardiert und meldet nicht an das Portal.</span><span class="sxs-lookup"><span data-stu-id="0c487-188">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="0c487-189">Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="0c487-189">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="0c487-190">Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0c487-190">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="0c487-191">Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></span><span class="sxs-lookup"><span data-stu-id="0c487-191">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-192">11</span><span class="sxs-lookup"><span data-stu-id="0c487-192">11</span></span></td>
<td><span data-ttu-id="0c487-193">Onboarding oder erneutes Onboarding des Defender for Endpoint-Diensts abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="0c487-193">Onboarding or re-onboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="0c487-194">Das Gerät wurde ordnungsgemäß onboardiert.</span><span class="sxs-lookup"><span data-stu-id="0c487-194">The device onboarded correctly.</span></span></td>
<td><span data-ttu-id="0c487-195">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-195">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="0c487-196">Es kann mehrere Stunden dauern, bis das Gerät im Portal angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0c487-196">It may take several hours for the device to appear in the portal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-197">12 </span><span class="sxs-lookup"><span data-stu-id="0c487-197">12</span></span></td>
<td><span data-ttu-id="0c487-198">Microsoft Defender for Endpoint konnte die Standardkonfiguration nicht anwenden.</span><span class="sxs-lookup"><span data-stu-id="0c487-198">Microsoft Defender for Endpoint failed to apply the default configuration.</span></span></td>
<td><span data-ttu-id="0c487-199">Der Dienst konnte die Standardkonfiguration nicht anwenden.</span><span class="sxs-lookup"><span data-stu-id="0c487-199">Service was unable to apply the default configuration.</span></span></td>
<td><span data-ttu-id="0c487-200">Dieser Fehler sollte nach kurzer Zeit behoben werden.</span><span class="sxs-lookup"><span data-stu-id="0c487-200">This error should resolve after a short period of time.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-201">13</span><span class="sxs-lookup"><span data-stu-id="0c487-201">13</span></span></td>
<td><span data-ttu-id="0c487-202">Microsoft Defender for Endpoint-Geräte-ID berechnet: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="0c487-202">Microsoft Defender for Endpoint device ID calculated: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="0c487-203">Normaler Betriebsprozess.</span><span class="sxs-lookup"><span data-stu-id="0c487-203">Normal operating process.</span></span></td>
<td><span data-ttu-id="0c487-204">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-204">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-205">15 </span><span class="sxs-lookup"><span data-stu-id="0c487-205">15</span></span></td>
<td><span data-ttu-id="0c487-206">Microsoft Defender for Endpoint kann den Befehlskanal nicht mit DER URL starten: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="0c487-206">Microsoft Defender for Endpoint cannot start command channel with URL: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="0c487-207">Variable = URL der Defender for Endpoint-Verarbeitungsserver.</span><span class="sxs-lookup"><span data-stu-id="0c487-207">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="0c487-208">Der Dienst konnte die externen Verarbeitungsserver unter dieser URL nicht kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="0c487-208">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="0c487-209">Überprüfen Sie die Verbindung zur URL.</span><span class="sxs-lookup"><span data-stu-id="0c487-209">Check the connection to the URL.</span></span> <span data-ttu-id="0c487-210">Weitere Informationen finden Sie unter <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and internet connectivity</a>.</span><span class="sxs-lookup"><span data-stu-id="0c487-210">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-211">17 </span><span class="sxs-lookup"><span data-stu-id="0c487-211">17</span></span></td>
<td><span data-ttu-id="0c487-212">Der Microsoft Defender for Endpoint-Dienst konnte den Speicherort des Diensts für verbundene Benutzererfahrungen und Telemetrie nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="0c487-212">Microsoft Defender for Endpoint service failed to change the Connected User Experiences and Telemetry service location.</span></span> <span data-ttu-id="0c487-213">Fehlercode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="0c487-213">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="0c487-214">Beim Windows-Telemetriedienst ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0c487-214">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="0c487-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Stellen Sie sicher, dass der Diagnosedatendienst aktiviert ist.</a></span><span class="sxs-lookup"><span data-stu-id="0c487-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="0c487-216">Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="0c487-216">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="0c487-217">Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0c487-217">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="0c487-218">Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></span><span class="sxs-lookup"><span data-stu-id="0c487-218">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-219">18 </span><span class="sxs-lookup"><span data-stu-id="0c487-219">18</span></span></td>
<td><span data-ttu-id="0c487-220">OOBE (Windows Welcome) ist abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="0c487-220">OOBE (Windows Welcome) is completed.</span></span></td>
<td><span data-ttu-id="0c487-221">Der Dienst wird erst gestartet, nachdem alle Windows-Updates installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="0c487-221">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="0c487-222">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-222">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-223">19</span><span class="sxs-lookup"><span data-stu-id="0c487-223">19</span></span></td>
<td><span data-ttu-id="0c487-224">OOBE (Windows Welcome) wurde noch nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="0c487-224">OOBE (Windows Welcome) has not yet completed.</span></span></td>
<td><span data-ttu-id="0c487-225">Der Dienst wird erst gestartet, nachdem alle Windows-Updates installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="0c487-225">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="0c487-226">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-226">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="0c487-227">Wenn dieser Fehler nach einem Systemneustart weiterhin auftritt, stellen Sie sicher, dass alle Windows-Updates vollständig installiert sind.</span><span class="sxs-lookup"><span data-stu-id="0c487-227">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-228">20</span><span class="sxs-lookup"><span data-stu-id="0c487-228">20</span></span></td>
<td><span data-ttu-id="0c487-229">Kann nicht warten, bis OOBE (Windows Welcome) abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="0c487-229">Cannot wait for OOBE (Windows Welcome) to complete.</span></span> <span data-ttu-id="0c487-230">Fehlercode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="0c487-230">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="0c487-231">Interner Fehler.</span><span class="sxs-lookup"><span data-stu-id="0c487-231">Internal error.</span></span></td>
<td><span data-ttu-id="0c487-232">Wenn dieser Fehler nach einem Systemneustart weiterhin auftritt, stellen Sie sicher, dass alle Windows-Updates vollständig installiert sind.</span><span class="sxs-lookup"><span data-stu-id="0c487-232">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-233">25</span><span class="sxs-lookup"><span data-stu-id="0c487-233">25</span></span></td>
<td><span data-ttu-id="0c487-234">Der Microsoft Defender for Endpoint-Dienst konnte den Integritätsstatus in der Registrierung nicht zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="0c487-234">Microsoft Defender for Endpoint service failed to reset health status in the registry.</span></span> <span data-ttu-id="0c487-235">Fehlercode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="0c487-235">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="0c487-236">Das Gerät wurde nicht ordnungsgemäß onboardiert.</span><span class="sxs-lookup"><span data-stu-id="0c487-236">The device didn't onboard correctly.</span></span>
<span data-ttu-id="0c487-237">Er wird dem Portal gemeldet, der Dienst wird jedoch möglicherweise nicht in SCCM oder der Registrierung registriert angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0c487-237">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="0c487-238">Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="0c487-238">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="0c487-239">Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0c487-239">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="0c487-240">Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></span><span class="sxs-lookup"><span data-stu-id="0c487-240">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-241">26</span><span class="sxs-lookup"><span data-stu-id="0c487-241">26</span></span></td>
<td><span data-ttu-id="0c487-242">Der Microsoft Defender for Endpoint-Dienst konnte den Onboardingstatus in der Registrierung nicht festlegen.</span><span class="sxs-lookup"><span data-stu-id="0c487-242">Microsoft Defender for Endpoint service failed to set the onboarding status in the registry.</span></span> <span data-ttu-id="0c487-243">Fehlercode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="0c487-243">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="0c487-244">Das Gerät wurde nicht ordnungsgemäß onboardiert.</span><span class="sxs-lookup"><span data-stu-id="0c487-244">The device didn't onboard correctly.</span></span><br>
<span data-ttu-id="0c487-245">Er wird dem Portal gemeldet, der Dienst wird jedoch möglicherweise nicht in SCCM oder der Registrierung registriert angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0c487-245">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="0c487-246">Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="0c487-246">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="0c487-247">Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0c487-247">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="0c487-248">Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></span><span class="sxs-lookup"><span data-stu-id="0c487-248">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-249">27</span><span class="sxs-lookup"><span data-stu-id="0c487-249">27</span></span></td>
<td><span data-ttu-id="0c487-250">Der Microsoft Defender for Endpoint-Dienst konnte den SENSE-bewussten Modus in Microsoft Defender Antivirus nicht aktivieren.</span><span class="sxs-lookup"><span data-stu-id="0c487-250">Microsoft Defender for Endpoint service failed to enable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="0c487-251">Fehler beim Onboardingprozess.</span><span class="sxs-lookup"><span data-stu-id="0c487-251">Onboarding process failed.</span></span> <span data-ttu-id="0c487-252">Fehlercode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="0c487-252">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="0c487-253">Normalerweise wird Microsoft Defender Antivirus in einen speziellen passiven Zustand ein, wenn ein anderes Antischasoftwareprodukt in Echtzeit ordnungsgemäß auf dem Gerät ausgeführt wird und das Gerät an Defender for Endpoint meldet.</span><span class="sxs-lookup"><span data-stu-id="0c487-253">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="0c487-254">Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="0c487-254">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="0c487-255">Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0c487-255">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="0c487-256">Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></span><span class="sxs-lookup"><span data-stu-id="0c487-256">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span><br>
<span data-ttu-id="0c487-257">Stellen Sie sicher, dass der Antischalwareschutz in Echtzeit ordnungsgemäß ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0c487-257">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-258">28</span><span class="sxs-lookup"><span data-stu-id="0c487-258">28</span></span></td>
<td><span data-ttu-id="0c487-259">Fehler bei der Registrierung des Microsoft Defender for Endpoint Connected User Experiences and Telemetry Service.</span><span class="sxs-lookup"><span data-stu-id="0c487-259">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration failed.</span></span> <span data-ttu-id="0c487-260">Fehlercode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="0c487-260">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="0c487-261">Beim Windows-Telemetriedienst ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0c487-261">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="0c487-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Stellen Sie sicher, dass der Diagnosedatendienst aktiviert ist.</a></span><span class="sxs-lookup"><span data-stu-id="0c487-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="0c487-263">Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="0c487-263">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="0c487-264">Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0c487-264">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="0c487-265">Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></span><span class="sxs-lookup"><span data-stu-id="0c487-265">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-266">29</span><span class="sxs-lookup"><span data-stu-id="0c487-266">29</span></span></td>
<td><span data-ttu-id="0c487-267">Fehler beim Lesen der offboarding-Parameter.</span><span class="sxs-lookup"><span data-stu-id="0c487-267">Failed to read the offboarding parameters.</span></span> <span data-ttu-id="0c487-268">Fehlertyp: %1, Fehlercode: %2, Beschreibung: %3</span><span class="sxs-lookup"><span data-stu-id="0c487-268">Error type: %1, Error code: %2, Description: %3</span></span> </td>
<td><span data-ttu-id="0c487-269">Dieses Ereignis tritt auf, wenn das System&#39;offboarding-Parameter nicht lesen kann.</span><span class="sxs-lookup"><span data-stu-id="0c487-269">This event occurs when the system can&#39;t read the offboarding parameters.</span></span></td>
<td><span data-ttu-id="0c487-270">Stellen Sie sicher, dass das Gerät über Internetzugriff verfügt, und führen Sie dann den gesamten Offboardingvorgang erneut aus.</span><span class="sxs-lookup"><span data-stu-id="0c487-270">Ensure the device has Internet access, then run the entire offboarding process again.</span></span> <span data-ttu-id="0c487-271">Stellen Sie sicher, dass das offboarding-Paket nicht abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="0c487-271">Ensure the offboarding package hasn't expired.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-272">30</span><span class="sxs-lookup"><span data-stu-id="0c487-272">30</span></span></td>
<td><span data-ttu-id="0c487-273">Der Microsoft Defender for Endpoint-Dienst konnte den SENSE-benachrichtigungsmodus in Microsoft Defender Antivirus nicht deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="0c487-273">Microsoft Defender for Endpoint service failed to disable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="0c487-274">Fehlercode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="0c487-274">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="0c487-275">Normalerweise wird Microsoft Defender Antivirus in einen speziellen passiven Zustand ein, wenn ein anderes Antischasoftwareprodukt in Echtzeit ordnungsgemäß auf dem Gerät ausgeführt wird und das Gerät an Defender for Endpoint meldet.</span><span class="sxs-lookup"><span data-stu-id="0c487-275">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="0c487-276">Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="0c487-276">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="0c487-277">Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0c487-277">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="0c487-278">Siehe <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboarding von Windows 10-Geräten</a></span><span class="sxs-lookup"><span data-stu-id="0c487-278">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a></span></span><br>
<span data-ttu-id="0c487-279">Stellen Sie sicher, dass der Antischalwareschutz in Echtzeit ordnungsgemäß ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0c487-279">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-280">31</span><span class="sxs-lookup"><span data-stu-id="0c487-280">31</span></span></td>
<td><span data-ttu-id="0c487-281">Die Registrierung des Microsoft Defender for Endpoint Connected User Experiences and Telemetry Service ist fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="0c487-281">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service unregistration failed.</span></span> <span data-ttu-id="0c487-282">Fehlercode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="0c487-282">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="0c487-283">Beim Onboarding ist beim Windows-Telemetriedienst ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0c487-283">An error occurred with the Windows telemetry service during onboarding.</span></span> <span data-ttu-id="0c487-284">Der Offboardingprozess wird fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="0c487-284">The offboarding process continues.</span></span></td>
<td><span data-ttu-id="0c487-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Überprüfen Sie mit dem Windows-Telemetriedienst auf Fehler.</a></span><span class="sxs-lookup"><span data-stu-id="0c487-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Check for errors with the Windows telemetry service</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-286">32</span><span class="sxs-lookup"><span data-stu-id="0c487-286">32</span></span></td>
<td><span data-ttu-id="0c487-287">Der Microsoft Defender for Endpoint-Dienst konnte nicht anfordern, dass er sich nach dem Offboardingvorgang selbst beendet.</span><span class="sxs-lookup"><span data-stu-id="0c487-287">Microsoft Defender for Endpoint service failed to request to stop itself after offboarding process.</span></span> <span data-ttu-id="0c487-288">Fehlercode: %1</span><span class="sxs-lookup"><span data-stu-id="0c487-288">Failure code: %1</span></span></td>
<td><span data-ttu-id="0c487-289">Beim Offboarding ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0c487-289">An error occurred during offboarding.</span></span></td>
<td><span data-ttu-id="0c487-290">Starten Sie das Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="0c487-290">Reboot the device.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-291">33</span><span class="sxs-lookup"><span data-stu-id="0c487-291">33</span></span></td>
<td><span data-ttu-id="0c487-292">Microsoft Defender for Endpoint-Dienst konnte die SENSE-GUID nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="0c487-292">Microsoft Defender for Endpoint service failed to persist SENSE GUID.</span></span> <span data-ttu-id="0c487-293">Fehlercode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="0c487-293">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="0c487-294">Ein eindeutiger Bezeichner wird verwendet, um jedes Gerät zu repräsentieren, das an das Portal meldet.</span><span class="sxs-lookup"><span data-stu-id="0c487-294">A unique identifier is used to represent each device that is reporting to the portal.</span></span><br>
<span data-ttu-id="0c487-295">Wenn der Bezeichner nicht beibehalten wird, wird das gleiche Gerät möglicherweise zweimal im Portal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0c487-295">If the identifier doesn't persist, the same device might appear twice in the portal.</span></span></td>
<td><span data-ttu-id="0c487-296">Überprüfen Sie die Registrierungsberechtigungen auf dem Gerät, um sicherzustellen, dass der Dienst die Registrierung aktualisieren kann.</span><span class="sxs-lookup"><span data-stu-id="0c487-296">Check registry permissions on the device to ensure the service can update the registry.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-297">34</span><span class="sxs-lookup"><span data-stu-id="0c487-297">34</span></span></td>
<td><span data-ttu-id="0c487-298">Der Microsoft Defender for Endpoint-Dienst konnte sich nicht selbst als Abhängigkeit vom Dienst für verbundene Benutzererfahrungen und Telemetrie hinzufügen, wodurch der Onboardingprozess fehlschlagen konnte.</span><span class="sxs-lookup"><span data-stu-id="0c487-298">Microsoft Defender for Endpoint service failed to add itself as a dependency on the Connected User Experiences and Telemetry service, causing onboarding process to fail.</span></span> <span data-ttu-id="0c487-299">Fehlercode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="0c487-299">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="0c487-300">Beim Windows-Telemetriedienst ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0c487-300">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="0c487-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Stellen Sie sicher, dass der Diagnosedatendienst aktiviert ist.</a></span><span class="sxs-lookup"><span data-stu-id="0c487-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="0c487-302">Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="0c487-302">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="0c487-303">Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0c487-303">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="0c487-304">Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></span><span class="sxs-lookup"><span data-stu-id="0c487-304">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-305">35</span><span class="sxs-lookup"><span data-stu-id="0c487-305">35</span></span></td>
<td><span data-ttu-id="0c487-306">Der Microsoft Defender for Endpoint-Dienst konnte sich nicht selbst als Abhängigkeit vom Dienst für verbundene Benutzererfahrungen und Telemetrie entfernen.</span><span class="sxs-lookup"><span data-stu-id="0c487-306">Microsoft Defender for Endpoint service failed to remove itself as a dependency on the Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="0c487-307">Fehlercode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="0c487-307">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="0c487-308">Beim Offboarding ist beim Windows-Telemetriedienst ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0c487-308">An error occurred with the Windows telemetry service during offboarding.</span></span> <span data-ttu-id="0c487-309">Der Offboardingprozess wird fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="0c487-309">The offboarding process continues.</span></span>
</td>
<td><span data-ttu-id="0c487-310">Überprüfen Sie beim Windows-Diagnosedatendienst auf Fehler.</span><span class="sxs-lookup"><span data-stu-id="0c487-310">Check for errors with the Windows diagnostic data service.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-311">36</span><span class="sxs-lookup"><span data-stu-id="0c487-311">36</span></span></td>
<td><span data-ttu-id="0c487-312">Die Registrierung des Microsoft Defender for Endpoint Connected User Experiences and Telemetry Service ist erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="0c487-312">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration succeeded.</span></span> <span data-ttu-id="0c487-313">Fertigstellungscode: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="0c487-313">Completion code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="0c487-314">Die Registrierung von Defender for Endpoint beim Dienst für verbundene Benutzererfahrungen und Telemetrie wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="0c487-314">Registering Defender for Endpoint with the Connected User Experiences and Telemetry service completed successfully.</span></span></td>
<td><span data-ttu-id="0c487-315">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-315">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-316">37</span><span class="sxs-lookup"><span data-stu-id="0c487-316">37</span></span></td>
<td><span data-ttu-id="0c487-317">Microsoft Defender for Endpoint A module is about to exceed its quota.</span><span class="sxs-lookup"><span data-stu-id="0c487-317">Microsoft Defender for Endpoint A module is about to exceed its quota.</span></span> <span data-ttu-id="0c487-318">Modul: %1, Kontingent: {%2} {%3}, Prozentsatz der Kontingentauslastung: %4.</span><span class="sxs-lookup"><span data-stu-id="0c487-318">Module: %1, Quota: {%2} {%3}, Percentage of quota utilization: %4.</span></span></td>
<td><span data-ttu-id="0c487-319">Das gerät hat fast das zugewiesene Kontingent des aktuellen 24-Stunden-Fensters verwendet.</span><span class="sxs-lookup"><span data-stu-id="0c487-319">The device has almost used its allocated quota of the current 24-hour window.</span></span> <span data-ttu-id="0c487-320">Es wird gedrosselt.</span><span class="sxs-lookup"><span data-stu-id="0c487-320">It’s about to be throttled.</span></span></td>
<td><span data-ttu-id="0c487-321">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-321">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-322">38</span><span class="sxs-lookup"><span data-stu-id="0c487-322">38</span></span></td>
<td><span data-ttu-id="0c487-323">Die Netzwerkverbindung wird als niedrig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="0c487-323">Network connection is identified as low.</span></span> <span data-ttu-id="0c487-324">Microsoft Defender for Endpoint kontaktiert den Server alle %1 Minuten.</span><span class="sxs-lookup"><span data-stu-id="0c487-324">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="0c487-325">Gemessene Verbindung: %2, Internet verfügbar: %3, kostenloses Netzwerk verfügbar: %4.</span><span class="sxs-lookup"><span data-stu-id="0c487-325">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="0c487-326">Das Gerät verwendet ein gemessenes/kostenpflichtiges Netzwerk und kontaktiert den Server seltener.</span><span class="sxs-lookup"><span data-stu-id="0c487-326">The device is using a metered/paid network and will be contacting the server less frequently.</span></span></td>
<td><span data-ttu-id="0c487-327">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-327">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-328">39</span><span class="sxs-lookup"><span data-stu-id="0c487-328">39</span></span></td>
<td><span data-ttu-id="0c487-329">Die Netzwerkverbindung wird als normal identifiziert.</span><span class="sxs-lookup"><span data-stu-id="0c487-329">Network connection is identified as normal.</span></span> <span data-ttu-id="0c487-330">Microsoft Defender for Endpoint kontaktiert den Server alle %1 Minuten.</span><span class="sxs-lookup"><span data-stu-id="0c487-330">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="0c487-331">Gemessene Verbindung: %2, Internet verfügbar: %3, kostenloses Netzwerk verfügbar: %4.</span><span class="sxs-lookup"><span data-stu-id="0c487-331">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="0c487-332">Das Gerät verwendet keine meterierte/kostenpflichtige Verbindung und kontaktiert den Server wie gewohnt.</span><span class="sxs-lookup"><span data-stu-id="0c487-332">The device isn't using a metered/paid connection and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="0c487-333">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-333">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-334">40</span><span class="sxs-lookup"><span data-stu-id="0c487-334">40</span></span></td>
<td><span data-ttu-id="0c487-335">Der Akkuzustand wird als niedrig gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="0c487-335">Battery state is identified as low.</span></span> <span data-ttu-id="0c487-336">Microsoft Defender for Endpoint kontaktiert den Server alle %1 Minuten.</span><span class="sxs-lookup"><span data-stu-id="0c487-336">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="0c487-337">Akkuzustand: %2.</span><span class="sxs-lookup"><span data-stu-id="0c487-337">Battery state: %2.</span></span></td>
<td><span data-ttu-id="0c487-338">Das Gerät hat einen niedrigen Akkustand und kontaktiert den Server seltener.</span><span class="sxs-lookup"><span data-stu-id="0c487-338">The device has low battery level and will contact the server less frequently.</span></span></td>
<td><span data-ttu-id="0c487-339">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-339">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-340">41</span><span class="sxs-lookup"><span data-stu-id="0c487-340">41</span></span></td>
<td><span data-ttu-id="0c487-341">Der Akkuzustand wird als normal identifiziert.</span><span class="sxs-lookup"><span data-stu-id="0c487-341">Battery state is identified as normal.</span></span> <span data-ttu-id="0c487-342">Microsoft Defender for Endpoint kontaktiert den Server alle %1 Minuten.</span><span class="sxs-lookup"><span data-stu-id="0c487-342">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="0c487-343">Akkuzustand: %2.</span><span class="sxs-lookup"><span data-stu-id="0c487-343">Battery state: %2.</span></span></td>
<td><span data-ttu-id="0c487-344">Das Gerät hat keinen niedrigen Akkustand und kontaktiert den Server wie gewohnt.</span><span class="sxs-lookup"><span data-stu-id="0c487-344">The device doesn’t have low battery level and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="0c487-345">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-345">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-346">42</span><span class="sxs-lookup"><span data-stu-id="0c487-346">42</span></span></td>
<td><span data-ttu-id="0c487-347">Microsoft Defender for Endpoint-Komponente konnte keine Aktion ausführen.</span><span class="sxs-lookup"><span data-stu-id="0c487-347">Microsoft Defender for Endpoint component failed to perform action.</span></span> <span data-ttu-id="0c487-348">Komponente: %1, Aktion: %2, Ausnahmetyp: %3, Ausnahmemeldung: %4</span><span class="sxs-lookup"><span data-stu-id="0c487-348">Component: %1, Action: %2, Exception Type: %3, Exception message: %4</span></span></td>
<td><span data-ttu-id="0c487-349">Interner Fehler.</span><span class="sxs-lookup"><span data-stu-id="0c487-349">Internal error.</span></span> <span data-ttu-id="0c487-350">Der Dienst konnte nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="0c487-350">The service failed to start.</span></span></td>
<td><span data-ttu-id="0c487-351">Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="0c487-351">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-352">43</span><span class="sxs-lookup"><span data-stu-id="0c487-352">43</span></span></td>
<td><span data-ttu-id="0c487-353">Microsoft Defender for Endpoint-Komponente konnte keine Aktion ausführen.</span><span class="sxs-lookup"><span data-stu-id="0c487-353">Microsoft Defender for Endpoint component failed to perform action.</span></span> <span data-ttu-id="0c487-354">Komponente: %1, Aktion: %2, Ausnahmetyp: %3, Ausnahmefehler: %4, Ausnahmemeldung: %5</span><span class="sxs-lookup"><span data-stu-id="0c487-354">Component: %1, Action: %2, Exception Type: %3, Exception Error: %4, Exception message: %5</span></span></td>
<td><span data-ttu-id="0c487-355">Interner Fehler.</span><span class="sxs-lookup"><span data-stu-id="0c487-355">Internal error.</span></span> <span data-ttu-id="0c487-356">Der Dienst konnte nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="0c487-356">The service failed to start.</span></span></td>
<td><span data-ttu-id="0c487-357">Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="0c487-357">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-358">44</span><span class="sxs-lookup"><span data-stu-id="0c487-358">44</span></span></td>
<td><span data-ttu-id="0c487-359">Offboarding des Defender for Endpoint-Diensts abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="0c487-359">Offboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="0c487-360">Der Dienst wurde offboarded.</span><span class="sxs-lookup"><span data-stu-id="0c487-360">The service was offboarded.</span></span></td>
<td><span data-ttu-id="0c487-361">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-361">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-362">45</span><span class="sxs-lookup"><span data-stu-id="0c487-362">45</span></span></td>
<td><span data-ttu-id="0c487-363">Fehler beim Registrieren und Starten der Ereignisverfolgungssitzung [%1].</span><span class="sxs-lookup"><span data-stu-id="0c487-363">Failed to register and to start the event trace session [%1].</span></span> <span data-ttu-id="0c487-364">Fehlercode: %2</span><span class="sxs-lookup"><span data-stu-id="0c487-364">Error code: %2</span></span></td>
<td><span data-ttu-id="0c487-365">Beim Starten des Diensts beim Erstellen einer ETW-Sitzung ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0c487-365">An error occurred on service startup while creating ETW session.</span></span> <span data-ttu-id="0c487-366">Dies führte zu einem Fehler beim Starten des Diensts.</span><span class="sxs-lookup"><span data-stu-id="0c487-366">This caused service start-up failure.</span></span></td>
<td><span data-ttu-id="0c487-367">Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="0c487-367">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-368">46</span><span class="sxs-lookup"><span data-stu-id="0c487-368">46</span></span></td>
<td><span data-ttu-id="0c487-369">Fehler beim Registrieren und Starten der Ereignisverfolgungssitzung [%1] aufgrund fehlender Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="0c487-369">Failed to register and start the event trace session [%1] due to lack of resources.</span></span> <span data-ttu-id="0c487-370">Fehlercode: %2.</span><span class="sxs-lookup"><span data-stu-id="0c487-370">Error code: %2.</span></span> <span data-ttu-id="0c487-371">Dies liegt wahrscheinlich daran, dass zu viele aktive Ereignisverfolgungssitzungen sind.</span><span class="sxs-lookup"><span data-stu-id="0c487-371">This is most likely because there are too many active event trace sessions.</span></span> <span data-ttu-id="0c487-372">Der Dienst wird in 1 Minute erneut versuchen.</span><span class="sxs-lookup"><span data-stu-id="0c487-372">The service will retry in 1 minute.</span></span></td>
<td><span data-ttu-id="0c487-373">Fehler beim Starten des Diensts beim Erstellen einer ETW-Sitzung aufgrund fehlender Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="0c487-373">An error occurred on service startup while creating ETW session due to lack of resources.</span></span> <span data-ttu-id="0c487-374">Der Dienst wurde gestartet und wird ausgeführt, es wird jedoch erst ein Sensorereignis berichtet, wenn die ETW-Sitzung gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="0c487-374">The service started and is running, but won't report any sensor event until the ETW session is started.</span></span></td>
<td><span data-ttu-id="0c487-375">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-375">Normal operating notification; no action required.</span></span> <span data-ttu-id="0c487-376">Der Dienst versucht, die Sitzung jede Minute zu starten.</span><span class="sxs-lookup"><span data-stu-id="0c487-376">The service will try to start the session every minute.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-377">47</span><span class="sxs-lookup"><span data-stu-id="0c487-377">47</span></span></td>
<td><span data-ttu-id="0c487-378">Die Ereignisverfolgungssitzung wurde erfolgreich registriert und gestartet – nach vorherigen fehlgeschlagenen Versuchen wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="0c487-378">Successfully registered and started the event trace session - recovered after previous failed attempts.</span></span></td>
<td><span data-ttu-id="0c487-379">Dieses Ereignis folgt dem vorherigen Ereignis nach dem erfolgreichen Starten der ETW-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="0c487-379">This event follows the previous event after successfully starting of the ETW session.</span></span></td>
<td><span data-ttu-id="0c487-380">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-380">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0c487-381">48</span><span class="sxs-lookup"><span data-stu-id="0c487-381">48</span></span></td>
<td><span data-ttu-id="0c487-382">Fehler beim Hinzufügen eines Anbieters [%1] zur Ereignisverfolgungssitzung [%2].</span><span class="sxs-lookup"><span data-stu-id="0c487-382">Failed to add a provider [%1] to event trace session [%2].</span></span> <span data-ttu-id="0c487-383">Fehlercode: %3.</span><span class="sxs-lookup"><span data-stu-id="0c487-383">Error code: %3.</span></span> <span data-ttu-id="0c487-384">Dies bedeutet, dass Ereignisse von diesem Anbieter nicht gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="0c487-384">This means that events from this provider will not be reported.</span></span></td>
<td><span data-ttu-id="0c487-385">Fehler beim Hinzufügen eines Anbieters zur ETW-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="0c487-385">Failed to add a provider to ETW session.</span></span> <span data-ttu-id="0c487-386">Aus diesem Grund werden die Anbieterereignisse nicht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="0c487-386">As a result, the provider events aren’t reported.</span></span></td>
<td><span data-ttu-id="0c487-387">Überprüfen Sie den Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="0c487-387">Check the error code.</span></span> <span data-ttu-id="0c487-388">Wenn der Fehler weiterhin auftritt, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="0c487-388">If the error persists contact Support.</span></span></td>
</tr>
</tr>
<tr>
   <td><span data-ttu-id="0c487-389">49</span><span class="sxs-lookup"><span data-stu-id="0c487-389">49</span></span></td>
   <td><span data-ttu-id="0c487-390">Ungültiger Cloudkonfigurationsbefehl empfangen und ignoriert.</span><span class="sxs-lookup"><span data-stu-id="0c487-390">Invalid cloud configuration command received and ignored.</span></span> <span data-ttu-id="0c487-391">Version: %1, Status: %2, Fehlercode: %3, Meldung: %4</span><span class="sxs-lookup"><span data-stu-id="0c487-391">Version: %1, status: %2, error code: %3, message: %4</span></span></td>
   <td><span data-ttu-id="0c487-392">Vom Clouddienst wurde eine ungültige Konfigurationsdatei empfangen, die ignoriert wurde.</span><span class="sxs-lookup"><span data-stu-id="0c487-392">Received an invalid configuration file from the cloud service that was ignored.</span></span></td>
   <td><span data-ttu-id="0c487-393">Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="0c487-393">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-394">50</span><span class="sxs-lookup"><span data-stu-id="0c487-394">50</span></span></td>
   <td><span data-ttu-id="0c487-395">Neue Cloudkonfiguration wurde erfolgreich angewendet.</span><span class="sxs-lookup"><span data-stu-id="0c487-395">New cloud configuration applied successfully.</span></span> <span data-ttu-id="0c487-396">Version: %1.</span><span class="sxs-lookup"><span data-stu-id="0c487-396">Version: %1.</span></span></td>
   <td><span data-ttu-id="0c487-397">Eine neue Konfiguration wurde erfolgreich vom Clouddienst angewendet.</span><span class="sxs-lookup"><span data-stu-id="0c487-397">Successfully applied a new configuration from the cloud service.</span></span></td>
   <td><span data-ttu-id="0c487-398">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-398">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-399">51</span><span class="sxs-lookup"><span data-stu-id="0c487-399">51</span></span></td>
   <td><span data-ttu-id="0c487-400">Neue Cloudkonfiguration konnte nicht angewendet werden, Version: %1.</span><span class="sxs-lookup"><span data-stu-id="0c487-400">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="0c487-401">Die letzte bekannte gute Konfiguration, Version %2, wurde erfolgreich angewendet.</span><span class="sxs-lookup"><span data-stu-id="0c487-401">Successfully applied the last known good configuration, version %2.</span></span></td>
   <td><span data-ttu-id="0c487-402">Vom Clouddienst wurde eine ungültige Konfigurationsdatei empfangen.</span><span class="sxs-lookup"><span data-stu-id="0c487-402">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="0c487-403">Die letzte bekannte gute Konfiguration wurde erfolgreich angewendet.</span><span class="sxs-lookup"><span data-stu-id="0c487-403">Last known good configuration was applied successfully.</span></span></td>
   <td><span data-ttu-id="0c487-404">Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="0c487-404">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-405">52</span><span class="sxs-lookup"><span data-stu-id="0c487-405">52</span></span></td>
   <td><span data-ttu-id="0c487-406">Neue Cloudkonfiguration konnte nicht angewendet werden, Version: %1.</span><span class="sxs-lookup"><span data-stu-id="0c487-406">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="0c487-407">Außerdem konnte die letzte bekannte gute Konfiguration, Version %2, nicht angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="0c487-407">Also failed to apply last known good configuration, version %2.</span></span> <span data-ttu-id="0c487-408">Die Standardkonfiguration wurde erfolgreich angewendet.</span><span class="sxs-lookup"><span data-stu-id="0c487-408">Successfully applied the default configuration.</span></span></td>
   <td><span data-ttu-id="0c487-409">Vom Clouddienst wurde eine ungültige Konfigurationsdatei empfangen.</span><span class="sxs-lookup"><span data-stu-id="0c487-409">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="0c487-410">Fehler beim Anwenden der letzten als gut bekannten Konfiguration – und die Standardkonfiguration wurde angewendet.</span><span class="sxs-lookup"><span data-stu-id="0c487-410">Failed to apply the last known good configuration - and the default configuration was applied.</span></span></td>
   <td><span data-ttu-id="0c487-411">Der Dienst versucht, innerhalb von 5 Minuten eine neue Konfigurationsdatei herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="0c487-411">The service will attempt to download a new configuration file within 5 minutes.</span></span> <span data-ttu-id="0c487-412">Wenn das Ereignis nicht #50 , wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="0c487-412">If you don't see event #50 - contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-413">53</span><span class="sxs-lookup"><span data-stu-id="0c487-413">53</span></span></td>
   <td><span data-ttu-id="0c487-414">Cloudkonfiguration, die aus dem beständigen Speicher geladen wird, Version: %1.</span><span class="sxs-lookup"><span data-stu-id="0c487-414">Cloud configuration loaded from persistent storage, version: %1.</span></span></td>
   <td><span data-ttu-id="0c487-415">Die Konfiguration wurde beim Starten des Diensts aus dem beständigen Speicher geladen.</span><span class="sxs-lookup"><span data-stu-id="0c487-415">The configuration was loaded from persistent storage on service startup.</span></span></td>
   <td><span data-ttu-id="0c487-416">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-416">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-417">55</span><span class="sxs-lookup"><span data-stu-id="0c487-417">55</span></span></td>
   <td><span data-ttu-id="0c487-418">Fehler beim Erstellen des Secure ETW-Autologgers.</span><span class="sxs-lookup"><span data-stu-id="0c487-418">Failed to create the Secure ETW autologger.</span></span> <span data-ttu-id="0c487-419">Fehlercode: %1</span><span class="sxs-lookup"><span data-stu-id="0c487-419">Failure code: %1</span></span></td>
   <td><span data-ttu-id="0c487-420">Fehler beim Erstellen des sicheren ETW-Loggers.</span><span class="sxs-lookup"><span data-stu-id="0c487-420">Failed to create the secure ETW logger.</span></span></td>
   <td><span data-ttu-id="0c487-421">Starten Sie das Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="0c487-421">Reboot the device.</span></span> <span data-ttu-id="0c487-422">Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="0c487-422">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-423">56</span><span class="sxs-lookup"><span data-stu-id="0c487-423">56</span></span></td>
   <td><span data-ttu-id="0c487-424">Fehler beim Entfernen des Secure ETW-Autologgers.</span><span class="sxs-lookup"><span data-stu-id="0c487-424">Failed to remove the Secure ETW autologger.</span></span> <span data-ttu-id="0c487-425">Fehlercode: %1</span><span class="sxs-lookup"><span data-stu-id="0c487-425">Failure code: %1</span></span></td>
   <td><span data-ttu-id="0c487-426">Fehler beim Entfernen der sicheren ETW-Sitzung beim Offboarding.</span><span class="sxs-lookup"><span data-stu-id="0c487-426">Failed to remove the secure ETW session on offboarding.</span></span></td>
   <td><span data-ttu-id="0c487-427">Wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="0c487-427">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-428">57</span><span class="sxs-lookup"><span data-stu-id="0c487-428">57</span></span></td>
   <td><span data-ttu-id="0c487-429">Erfassen einer Momentaufnahme des Computers zur Problembehandlung.</span><span class="sxs-lookup"><span data-stu-id="0c487-429">Capturing a snapshot of the machine for troubleshooting purposes.</span></span></td>
   <td><span data-ttu-id="0c487-430">Ein Untersuchungspaket, das auch als Forensikpaket bezeichnet wird, wird gesammelt.</span><span class="sxs-lookup"><span data-stu-id="0c487-430">An investigation package, also known as forensics package, is being collected.</span></span></td>
   <td><span data-ttu-id="0c487-431">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-431">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-432">59</span><span class="sxs-lookup"><span data-stu-id="0c487-432">59</span></span></td>
   <td><span data-ttu-id="0c487-433">Startbefehl: %1</span><span class="sxs-lookup"><span data-stu-id="0c487-433">Starting command: %1</span></span></td>
   <td><span data-ttu-id="0c487-434">Starten der Ausführung des Antwortbefehls.</span><span class="sxs-lookup"><span data-stu-id="0c487-434">Starting response command execution.</span></span></td>
   <td><span data-ttu-id="0c487-435">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-435">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-436">60</span><span class="sxs-lookup"><span data-stu-id="0c487-436">60</span></span></td>
   <td><span data-ttu-id="0c487-437">Befehl "%1" konnte nicht ausgeführt werden, Fehler: %2.</span><span class="sxs-lookup"><span data-stu-id="0c487-437">Failed to run command %1, error: %2.</span></span></td>
   <td><span data-ttu-id="0c487-438">Antwortbefehl konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0c487-438">Failed to execute response command.</span></span></td>
   <td><span data-ttu-id="0c487-439">Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="0c487-439">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-440">61</span><span class="sxs-lookup"><span data-stu-id="0c487-440">61</span></span></td>
   <td><span data-ttu-id="0c487-441">Parameter des Datensammlungsbefehls sind ungültig: SasUri: %1, compressionLevel: %2.</span><span class="sxs-lookup"><span data-stu-id="0c487-441">Data collection command parameters are invalid: SasUri: %1, compressionLevel: %2.</span></span></td>
   <td><span data-ttu-id="0c487-442">Fehler beim Lesen oder Analysieren der Datensammlungsbefehlsargumente (ungültige Argumente).</span><span class="sxs-lookup"><span data-stu-id="0c487-442">Failed to read or parse the data collection command arguments (invalid arguments).</span></span></td>
   <td><span data-ttu-id="0c487-443">Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="0c487-443">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-444">62</span><span class="sxs-lookup"><span data-stu-id="0c487-444">62</span></span></td>
   <td><span data-ttu-id="0c487-445">Fehler beim Starten des Diensts für verbundene Benutzererfahrungen und Telemetrie.</span><span class="sxs-lookup"><span data-stu-id="0c487-445">Failed to start Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="0c487-446">Fehlercode: %1</span><span class="sxs-lookup"><span data-stu-id="0c487-446">Failure code: %1</span></span></td>
   <td><span data-ttu-id="0c487-447">Der Dienst für verbundene Benutzererfahrungen und Telemetrie (Diagtrack) konnte nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="0c487-447">Connected User Experiences and Telemetry (diagtrack) service failed to start.</span></span> <span data-ttu-id="0c487-448">Telemetriedaten von Nicht-Microsoft Defender for Endpoint werden nicht von diesem Computer gesendet.</span><span class="sxs-lookup"><span data-stu-id="0c487-448">Non-Microsoft Defender for Endpoint telemetry won't be sent from this machine.</span></span></td>
   <td><span data-ttu-id="0c487-449">Weitere Hinweise zur Problembehandlung finden Sie im Ereignisprotokoll: Microsoft-Windows-UniversalTelemetryClient/Operational.</span><span class="sxs-lookup"><span data-stu-id="0c487-449">Look for more troubleshooting hints in the event log: Microsoft-Windows-UniversalTelemetryClient/Operational.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-450">63</span><span class="sxs-lookup"><span data-stu-id="0c487-450">63</span></span></td>
   <td><span data-ttu-id="0c487-451">Aktualisieren des Starttyps des externen Diensts.</span><span class="sxs-lookup"><span data-stu-id="0c487-451">Updating the start type of external service.</span></span> <span data-ttu-id="0c487-452">Name: %1, tatsächlicher Starttyp: %2, erwarteter Starttyp: %3, Exitcode: %4</span><span class="sxs-lookup"><span data-stu-id="0c487-452">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="0c487-453">Der Starttyp des externen Diensts wurde aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="0c487-453">Updated start type of the external service.</span></span></td>
   <td><span data-ttu-id="0c487-454">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-454">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-455">64</span><span class="sxs-lookup"><span data-stu-id="0c487-455">64</span></span></td>
   <td><span data-ttu-id="0c487-456">Starten des beendeten externen Diensts.</span><span class="sxs-lookup"><span data-stu-id="0c487-456">Starting stopped external service.</span></span> <span data-ttu-id="0c487-457">Name: %1, Exitcode: %2</span><span class="sxs-lookup"><span data-stu-id="0c487-457">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="0c487-458">Starten eines externen Diensts.</span><span class="sxs-lookup"><span data-stu-id="0c487-458">Starting an external service.</span></span></td>
   <td><span data-ttu-id="0c487-459">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-459">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-460">65</span><span class="sxs-lookup"><span data-stu-id="0c487-460">65</span></span></td>
   <td><span data-ttu-id="0c487-461">Microsoft Security Events Component Minifilter-Treiber konnte nicht geladen werden.</span><span class="sxs-lookup"><span data-stu-id="0c487-461">Failed to load Microsoft Security Events Component Minifilter driver.</span></span> <span data-ttu-id="0c487-462">Fehlercode: %1</span><span class="sxs-lookup"><span data-stu-id="0c487-462">Failure code: %1</span></span></td>
   <td><span data-ttu-id="0c487-463">Fehler beim Laden MsSecFlt.sys Dateisystem-Minifilters.</span><span class="sxs-lookup"><span data-stu-id="0c487-463">Failed to load MsSecFlt.sys filesystem minifilter.</span></span></td>
   <td><span data-ttu-id="0c487-464">Starten Sie das Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="0c487-464">Reboot the device.</span></span> <span data-ttu-id="0c487-465">Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="0c487-465">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-466">66</span><span class="sxs-lookup"><span data-stu-id="0c487-466">66</span></span></td>
   <td><span data-ttu-id="0c487-467">Richtlinienupdate: Latenzmodus – %1</span><span class="sxs-lookup"><span data-stu-id="0c487-467">Policy update: Latency mode - %1</span></span></td>
   <td><span data-ttu-id="0c487-468">Die C&C-Verbindungshäufigkeitsrichtlinie wurde aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="0c487-468">The C&C connection frequency policy was updated.</span></span></td>
   <td><span data-ttu-id="0c487-469">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-469">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-470">68</span><span class="sxs-lookup"><span data-stu-id="0c487-470">68</span></span></td>
   <td><span data-ttu-id="0c487-471">Der Starttyp des Diensts ist unerwartet.</span><span class="sxs-lookup"><span data-stu-id="0c487-471">The start type of the service is unexpected.</span></span> <span data-ttu-id="0c487-472">Dienstname: %1, tatsächlicher Starttyp: %2, erwarteter Starttyp: %3</span><span class="sxs-lookup"><span data-stu-id="0c487-472">Service name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="0c487-473">Unerwarteter Starttyp des externen Diensts.</span><span class="sxs-lookup"><span data-stu-id="0c487-473">Unexpected external service start type.</span></span></td>
   <td><span data-ttu-id="0c487-474">Fix the external service start type.</span><span class="sxs-lookup"><span data-stu-id="0c487-474">Fix the external service start type.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-475">69</span><span class="sxs-lookup"><span data-stu-id="0c487-475">69</span></span></td>
   <td><span data-ttu-id="0c487-476">Der Dienst wird beendet.</span><span class="sxs-lookup"><span data-stu-id="0c487-476">The service is stopped.</span></span> <span data-ttu-id="0c487-477">Dienstname: %1</span><span class="sxs-lookup"><span data-stu-id="0c487-477">Service name: %1</span></span></td>
   <td><span data-ttu-id="0c487-478">Der externe Dienst wird beendet.</span><span class="sxs-lookup"><span data-stu-id="0c487-478">The external service is stopped.</span></span></td>
   <td><span data-ttu-id="0c487-479">Starten Sie den externen Dienst.</span><span class="sxs-lookup"><span data-stu-id="0c487-479">Start the external service.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-480">70</span><span class="sxs-lookup"><span data-stu-id="0c487-480">70</span></span></td>
   <td><span data-ttu-id="0c487-481">Richtlinienupdate: Beispielsammlung zulassen – %1</span><span class="sxs-lookup"><span data-stu-id="0c487-481">Policy update: Allow sample collection - %1</span></span></td>
   <td><span data-ttu-id="0c487-482">Die Beispielsammlungsrichtlinie wurde aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="0c487-482">The sample collection policy was updated.</span></span></td>
   <td><span data-ttu-id="0c487-483">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-483">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-484">71</span><span class="sxs-lookup"><span data-stu-id="0c487-484">71</span></span></td>
   <td><span data-ttu-id="0c487-485">Befehl konnte erfolgreich ausgeführt werden: %1</span><span class="sxs-lookup"><span data-stu-id="0c487-485">Succeeded to run command: %1</span></span></td>
   <td><span data-ttu-id="0c487-486">Der Befehl wurde erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0c487-486">The command was executed successfully.</span></span></td>
   <td><span data-ttu-id="0c487-487">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-487">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-488">72</span><span class="sxs-lookup"><span data-stu-id="0c487-488">72</span></span></td>
   <td><span data-ttu-id="0c487-489">Es wurde versucht, den ersten vollständigen Computerprofilbericht zu senden.</span><span class="sxs-lookup"><span data-stu-id="0c487-489">Tried to send first full machine profile report.</span></span> <span data-ttu-id="0c487-490">Ergebniscode: %1</span><span class="sxs-lookup"><span data-stu-id="0c487-490">Result code: %1</span></span></td>
   <td><span data-ttu-id="0c487-491">Nur Information.</span><span class="sxs-lookup"><span data-stu-id="0c487-491">Informational only.</span></span></td>
   <td><span data-ttu-id="0c487-492">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-492">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-493">73</span><span class="sxs-lookup"><span data-stu-id="0c487-493">73</span></span></td>
   <td><span data-ttu-id="0c487-494">Sinn beim Starten der Plattform: %1</span><span class="sxs-lookup"><span data-stu-id="0c487-494">Sense starting for platform: %1</span></span></td>
   <td><span data-ttu-id="0c487-495">Nur Information.</span><span class="sxs-lookup"><span data-stu-id="0c487-495">Informational only.</span></span></td>
   <td><span data-ttu-id="0c487-496">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-496">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-497">74</span><span class="sxs-lookup"><span data-stu-id="0c487-497">74</span></span></td>
   <td><span data-ttu-id="0c487-498">Das Gerätetag in der Registrierung überschreitet die Längenbeschränkung.</span><span class="sxs-lookup"><span data-stu-id="0c487-498">Device tag in registry exceeds length limit.</span></span> <span data-ttu-id="0c487-499">Tagname: %2.</span><span class="sxs-lookup"><span data-stu-id="0c487-499">Tag name: %2.</span></span> <span data-ttu-id="0c487-500">Längenbeschränkung: %1.</span><span class="sxs-lookup"><span data-stu-id="0c487-500">Length limit: %1.</span></span></td>
   <td><span data-ttu-id="0c487-501">Das Gerätetag überschreitet den Längengrenzwert.</span><span class="sxs-lookup"><span data-stu-id="0c487-501">The device tag exceeds the length limit.</span></span></td>
   <td><span data-ttu-id="0c487-502">Verwenden Sie ein kürzeres Gerätetag.</span><span class="sxs-lookup"><span data-stu-id="0c487-502">Use a shorter device tag.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-503">81</span><span class="sxs-lookup"><span data-stu-id="0c487-503">81</span></span></td>
   <td><span data-ttu-id="0c487-504">Fehler beim Erstellen des AutomatischenLoggers von Microsoft Defender for Endpoint ETW.</span><span class="sxs-lookup"><span data-stu-id="0c487-504">Failed to create Microsoft Defender for Endpoint ETW autologger.</span></span> <span data-ttu-id="0c487-505">Fehlercode: %1</span><span class="sxs-lookup"><span data-stu-id="0c487-505">Failure code: %1</span></span></td>
   <td><span data-ttu-id="0c487-506">Fehler beim Erstellen der ETW-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="0c487-506">Failed to create the ETW session.</span></span></td>
   <td><span data-ttu-id="0c487-507">Starten Sie das Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="0c487-507">Reboot the device.</span></span> <span data-ttu-id="0c487-508">Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="0c487-508">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-509">82</span><span class="sxs-lookup"><span data-stu-id="0c487-509">82</span></span></td>
   <td><span data-ttu-id="0c487-510">Fehler beim Entfernen des Autologgers von Microsoft Defender for Endpoint ETW.</span><span class="sxs-lookup"><span data-stu-id="0c487-510">Failed to remove Microsoft Defender for Endpoint ETW autologger.</span></span> <span data-ttu-id="0c487-511">Fehlercode: %1</span><span class="sxs-lookup"><span data-stu-id="0c487-511">Failure code: %1</span></span></td>
   <td><span data-ttu-id="0c487-512">Fehler beim Löschen der ETW-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="0c487-512">Failed to delete the ETW session.</span></span></td>
   <td><span data-ttu-id="0c487-513">Wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="0c487-513">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-514">84</span><span class="sxs-lookup"><span data-stu-id="0c487-514">84</span></span></td>
   <td><span data-ttu-id="0c487-515">Festlegen Windows Defender Antivirus-Ausführungsmodus.</span><span class="sxs-lookup"><span data-stu-id="0c487-515">Set Windows Defender Antivirus running mode.</span></span> <span data-ttu-id="0c487-516">Erzwingen des passiven Modus: %1, Ergebniscode: %2.</span><span class="sxs-lookup"><span data-stu-id="0c487-516">Force passive mode: %1, result code: %2.</span></span></td>
   <td><span data-ttu-id="0c487-517">Festlegen des laufenden Defender-Modus (aktiv oder passiv).</span><span class="sxs-lookup"><span data-stu-id="0c487-517">Set defender running mode (active or passive).</span></span></td>
   <td><span data-ttu-id="0c487-518">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-518">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-519">85</span><span class="sxs-lookup"><span data-stu-id="0c487-519">85</span></span></td>
   <td><span data-ttu-id="0c487-520">Fehler beim Auslösen der ausführbaren Datei "Microsoft Defender for Endpoint".</span><span class="sxs-lookup"><span data-stu-id="0c487-520">Failed to trigger Microsoft Defender for Endpoint executable.</span></span> <span data-ttu-id="0c487-521">Fehlercode: %1</span><span class="sxs-lookup"><span data-stu-id="0c487-521">Failure code: %1</span></span></td>
   <td><span data-ttu-id="0c487-522">Fehler beim Ausführen der ausführbaren SenseIR-Datei.</span><span class="sxs-lookup"><span data-stu-id="0c487-522">Starring SenseIR executable failed.</span></span></td>
   <td><span data-ttu-id="0c487-523">Starten Sie das Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="0c487-523">Reboot the device.</span></span> <span data-ttu-id="0c487-524">Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="0c487-524">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-525">86</span><span class="sxs-lookup"><span data-stu-id="0c487-525">86</span></span></td>
   <td><span data-ttu-id="0c487-526">Beim erneuten Starten wurde der externe Dienst beendet, der eingerichtet werden sollte.</span><span class="sxs-lookup"><span data-stu-id="0c487-526">Starting again stopped external service that should be up.</span></span> <span data-ttu-id="0c487-527">Name: %1, Exitcode: %2</span><span class="sxs-lookup"><span data-stu-id="0c487-527">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="0c487-528">Starten Sie den externen Dienst erneut.</span><span class="sxs-lookup"><span data-stu-id="0c487-528">Starting the external service again.</span></span></td>
   <td><span data-ttu-id="0c487-529">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-529">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-530">87</span><span class="sxs-lookup"><span data-stu-id="0c487-530">87</span></span></td>
   <td><span data-ttu-id="0c487-531">Der externe Dienst kann nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="0c487-531">Cannot start the external service.</span></span> <span data-ttu-id="0c487-532">Name: %1</span><span class="sxs-lookup"><span data-stu-id="0c487-532">Name: %1</span></span></td>
   <td><span data-ttu-id="0c487-533">Fehler beim Starten des externen Diensts.</span><span class="sxs-lookup"><span data-stu-id="0c487-533">Failed to start the external service.</span></span></td>
   <td><span data-ttu-id="0c487-534">Wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="0c487-534">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-535">88</span><span class="sxs-lookup"><span data-stu-id="0c487-535">88</span></span></td>
   <td><span data-ttu-id="0c487-536">Aktualisieren des Starttyps des externen Diensts erneut.</span><span class="sxs-lookup"><span data-stu-id="0c487-536">Updating the start type of external service again.</span></span> <span data-ttu-id="0c487-537">Name: %1, tatsächlicher Starttyp: %2, erwarteter Starttyp: %3, Exitcode: %4</span><span class="sxs-lookup"><span data-stu-id="0c487-537">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="0c487-538">Der Starttyp des externen Diensts wurde aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="0c487-538">Updated the start type of the external service.</span></span></td>
   <td><span data-ttu-id="0c487-539">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-539">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-540">89</span><span class="sxs-lookup"><span data-stu-id="0c487-540">89</span></span></td>
   <td><span data-ttu-id="0c487-541">Der Starttyp des externen Diensts kann nicht aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="0c487-541">Cannot update the start type of external service.</span></span> <span data-ttu-id="0c487-542">Name: %1, tatsächlicher Starttyp: %2, erwarteter Starttyp: %3</span><span class="sxs-lookup"><span data-stu-id="0c487-542">Name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="0c487-543">Der Starttyp des externen Diensts kann nicht aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="0c487-543">Can't update the start type of the external service.</span></span></td>
   <td><span data-ttu-id="0c487-544">Wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="0c487-544">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-545">90</span><span class="sxs-lookup"><span data-stu-id="0c487-545">90</span></span></td>
   <td><span data-ttu-id="0c487-546">Fehler beim Konfigurieren des System Guard-Laufzeitmonitors für die Verbindung mit dem Clouddienst in der geografischen Region "%1".</span><span class="sxs-lookup"><span data-stu-id="0c487-546">Failed to configure System Guard Runtime Monitor to connect to cloud service in geo-region %1.</span></span> <span data-ttu-id="0c487-547">Fehlercode: %2</span><span class="sxs-lookup"><span data-stu-id="0c487-547">Failure code: %2</span></span></td>
   <td><span data-ttu-id="0c487-548">System Guard Runtime Monitor sendet keine Nachweisdaten an den Clouddienst.</span><span class="sxs-lookup"><span data-stu-id="0c487-548">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="0c487-549">Überprüfen Sie die Berechtigungen im Registerpfad: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span><span class="sxs-lookup"><span data-stu-id="0c487-549">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="0c487-550">Wenn keine Probleme auftreten, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="0c487-550">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-551">91</span><span class="sxs-lookup"><span data-stu-id="0c487-551">91</span></span></td>
   <td><span data-ttu-id="0c487-552">Fehler beim Entfernen von Informationen zur geografischen Region des System Guard-Runtime-Monitors.</span><span class="sxs-lookup"><span data-stu-id="0c487-552">Failed to remove System Guard Runtime Monitor geo-region information.</span></span> <span data-ttu-id="0c487-553">Fehlercode: %1</span><span class="sxs-lookup"><span data-stu-id="0c487-553">Failure code: %1</span></span></td>
   <td><span data-ttu-id="0c487-554">System Guard Runtime Monitor sendet keine Nachweisdaten an den Clouddienst.</span><span class="sxs-lookup"><span data-stu-id="0c487-554">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="0c487-555">Überprüfen Sie die Berechtigungen im Registerpfad: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span><span class="sxs-lookup"><span data-stu-id="0c487-555">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="0c487-556">Wenn keine Probleme auftreten, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="0c487-556">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-557">92</span><span class="sxs-lookup"><span data-stu-id="0c487-557">92</span></span></td>
   <td><span data-ttu-id="0c487-558">Beenden des Sendens des Cyberdatenkontingents des Sensors, da das Datenkontingent überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="0c487-558">Stopping sending sensor cyber data quota because data quota is exceeded.</span></span> <span data-ttu-id="0c487-559">Wird das Senden fortgesetzt, sobald der Kontingentzeitraum vergeht.</span><span class="sxs-lookup"><span data-stu-id="0c487-559">Will resume sending once quota period passes.</span></span> <span data-ttu-id="0c487-560">Zustandsmaske: %1</span><span class="sxs-lookup"><span data-stu-id="0c487-560">State Mask: %1</span></span></td>
   <td><span data-ttu-id="0c487-561">Drosselungsgrenzwert überschreiten.</span><span class="sxs-lookup"><span data-stu-id="0c487-561">Exceed throttling limit.</span></span></td>
   <td><span data-ttu-id="0c487-562">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-562">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-563">93</span><span class="sxs-lookup"><span data-stu-id="0c487-563">93</span></span></td>
   <td><span data-ttu-id="0c487-564">Fortsetzen des Sendens von Sensor-Cyberdaten.</span><span class="sxs-lookup"><span data-stu-id="0c487-564">Resuming sending sensor cyber data.</span></span> <span data-ttu-id="0c487-565">Zustandsmaske: %1</span><span class="sxs-lookup"><span data-stu-id="0c487-565">State Mask: %1</span></span></td>
   <td><span data-ttu-id="0c487-566">Fortsetzen der Cyberdatenübermittlung.</span><span class="sxs-lookup"><span data-stu-id="0c487-566">Resume cyber data submission.</span></span></td>
   <td><span data-ttu-id="0c487-567">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-567">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-568">94</span><span class="sxs-lookup"><span data-stu-id="0c487-568">94</span></span></td>
   <td><span data-ttu-id="0c487-569">Die ausführbare Datei "Microsoft Defender for Endpoint" wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="0c487-569">Microsoft Defender for Endpoint executable has started</span></span></td>
   <td><span data-ttu-id="0c487-570">Die ausführbare Datei SenseCE wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="0c487-570">The SenseCE executable has started.</span></span></td>
   <td><span data-ttu-id="0c487-571">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-571">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-572">95</span><span class="sxs-lookup"><span data-stu-id="0c487-572">95</span></span></td>
   <td><span data-ttu-id="0c487-573">Die ausführbare Datei "Microsoft Defender for Endpoint" wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="0c487-573">Microsoft Defender for Endpoint executable has ended</span></span></td>
   <td><span data-ttu-id="0c487-574">Die ausführbare Datei SenseCE wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="0c487-574">The SenseCE executable has ended.</span></span></td>
   <td><span data-ttu-id="0c487-575">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-575">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-576">96</span><span class="sxs-lookup"><span data-stu-id="0c487-576">96</span></span></td>
   <td><span data-ttu-id="0c487-577">Microsoft Defender for Endpoint Init hat aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="0c487-577">Microsoft Defender for Endpoint Init has called.</span></span> <span data-ttu-id="0c487-578">Ergebniscode: %2</span><span class="sxs-lookup"><span data-stu-id="0c487-578">Result code: %2</span></span></td>
   <td><span data-ttu-id="0c487-579">Die ausführbare SenseCE-Datei hat die MCE-Initialisierung aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="0c487-579">The SenseCE executable has called MCE initialization.</span></span></td>
   <td><span data-ttu-id="0c487-580">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-580">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-581">97</span><span class="sxs-lookup"><span data-stu-id="0c487-581">97</span></span></td>
   <td><span data-ttu-id="0c487-582">Es gibt Konnektivitätsprobleme mit der Cloud für das DLP-Szenario</span><span class="sxs-lookup"><span data-stu-id="0c487-582">There are connectivity issues to the Cloud for the DLP scenario</span></span></td>
   <td><span data-ttu-id="0c487-583">Es gibt Netzwerkkonnektivitätsprobleme, die sich auf den DLP-Klassifizierungsfluss auswirken.</span><span class="sxs-lookup"><span data-stu-id="0c487-583">There are network connectivity issues that affect the DLP classification flow.</span></span></td>
   <td><span data-ttu-id="0c487-584">Überprüfen Sie die Netzwerkkonnektivität.</span><span class="sxs-lookup"><span data-stu-id="0c487-584">Check the network connectivity.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-585">98</span><span class="sxs-lookup"><span data-stu-id="0c487-585">98</span></span></td>
   <td><span data-ttu-id="0c487-586">Die Konnektivität mit der Cloud für das DLP-Szenario wurde wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="0c487-586">The connectivity to the Cloud for the DLP scenario has been restored</span></span></td>
   <td><span data-ttu-id="0c487-587">Die Verbindung mit dem Netzwerk wurde wiederhergestellt, und der DLP-Klassifizierungsfluss kann fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="0c487-587">The connectivity to the network was restored and the DLP classification flow can continue.</span></span></td>
   <td><span data-ttu-id="0c487-588">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-588">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-589">99</span><span class="sxs-lookup"><span data-stu-id="0c487-589">99</span></span></td>
   <td><span data-ttu-id="0c487-590">Bei der Kommunikation mit dem Server ist der folgende Fehler aufgetreten: (%1).</span><span class="sxs-lookup"><span data-stu-id="0c487-590">Sense has encountered the following error while communicating with server: (%1).</span></span> <span data-ttu-id="0c487-591">Ergebnis: (%2)</span><span class="sxs-lookup"><span data-stu-id="0c487-591">Result: (%2)</span></span></td>
   <td><span data-ttu-id="0c487-592">Ein Kommunikationsfehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0c487-592">A communication error occurred.</span></span></td>
   <td><span data-ttu-id="0c487-593">Überprüfen Sie die folgenden Ereignisse im Ereignisprotokoll auf weitere Details.</span><span class="sxs-lookup"><span data-stu-id="0c487-593">Check the following events in the event log for further details.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-594">100</span><span class="sxs-lookup"><span data-stu-id="0c487-594">100</span></span></td>
   <td><span data-ttu-id="0c487-595">Die ausführbare Microsoft Defender for Endpoint-Datei konnte nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="0c487-595">Microsoft Defender for Endpoint executable failed to start.</span></span> <span data-ttu-id="0c487-596">Fehlercode: %1</span><span class="sxs-lookup"><span data-stu-id="0c487-596">Failure code: %1</span></span></td>
   <td><span data-ttu-id="0c487-597">Die ausführbare Datei SenseCE konnte nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="0c487-597">The SenseCE executable has failed to start.</span></span></td>
   <td><span data-ttu-id="0c487-598">Starten Sie das Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="0c487-598">Reboot the device.</span></span> <span data-ttu-id="0c487-599">Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="0c487-599">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-600">102</span><span class="sxs-lookup"><span data-stu-id="0c487-600">102</span></span></td>
   <td><span data-ttu-id="0c487-601">Microsoft Defender for Endpoint Network Detection and Response executable has started</span><span class="sxs-lookup"><span data-stu-id="0c487-601">Microsoft Defender for Endpoint Network Detection and Response executable has started</span></span></td>
   <td><span data-ttu-id="0c487-602">Die ausführbare Datei SenseNdr wurde gestartet.</span><span class="sxs-lookup"><span data-stu-id="0c487-602">The SenseNdr executable has started.</span></span></td>
   <td><span data-ttu-id="0c487-603">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-603">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="0c487-604">103</span><span class="sxs-lookup"><span data-stu-id="0c487-604">103</span></span></td>
   <td><span data-ttu-id="0c487-605">Microsoft Defender for Endpoint Network Detection and Response executable has ended</span><span class="sxs-lookup"><span data-stu-id="0c487-605">Microsoft Defender for Endpoint Network Detection and Response executable has ended</span></span></td>
   <td><span data-ttu-id="0c487-606">Die ausführbare Datei SenseNdr wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="0c487-606">The SenseNdr executable has ended.</span></span></td>
   <td><span data-ttu-id="0c487-607">Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c487-607">Normal operating notification; no action required.</span></span></td>
</tr>
</tbody>
</table>

><span data-ttu-id="0c487-608">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="0c487-608">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0c487-609">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="0c487-609">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="0c487-610">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="0c487-610">Related topics</span></span>
- [<span data-ttu-id="0c487-611">Onboarding von Windows 10-Geräten</span><span class="sxs-lookup"><span data-stu-id="0c487-611">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="0c487-612">Konfigurieren von Geräteproxy- und Internetverbindungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="0c487-612">Configure device proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="0c487-613">Problembehandlung von Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0c487-613">Troubleshoot Microsoft Defender for Endpoint</span></span>](troubleshoot-onboarding.md)
