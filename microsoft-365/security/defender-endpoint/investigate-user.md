---
title: Untersuchen eines Benutzerkontos in Microsoft Defender for Endpoint
description: Untersuchen Sie während einer Untersuchung ein Benutzerkonto auf potenzielle gefährdete Anmeldeinformationen oder Pivot für das zugeordnete Benutzerkonto.
keywords: investigate, account, user, user entity, alert, microsoft defender atp
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 672867d107d005004201caab7d6497ceb048ac97
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587707"
---
# <a name="investigate-a-user-account-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="a7874-104">Untersuchen eines Benutzerkontos in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a7874-104">Investigate a user account in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a7874-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a7874-105">**Applies to:**</span></span>
- [<span data-ttu-id="a7874-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="a7874-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a7874-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a7874-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="a7874-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="a7874-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a7874-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="a7874-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatgeuser-abovefoldlink)

## <a name="investigate-user-account-entities"></a><span data-ttu-id="a7874-110">Untersuchen von Benutzerkontenentitäten</span><span class="sxs-lookup"><span data-stu-id="a7874-110">Investigate user account entities</span></span>

<span data-ttu-id="a7874-111">Identifizieren Sie Benutzerkonten mit den aktivsten Warnungen (im Dashboard als "Gefährdete Benutzer" angezeigt), und untersuchen Sie Fälle potenzieller gefährdeter Anmeldeinformationen, oder verwenden Sie das zugehörige Benutzerkonto, wenn Sie eine Warnung oder ein Gerät untersuchen, um eine mögliche quere Bewegung zwischen Geräten mit diesem Benutzerkonto zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="a7874-111">Identify user accounts with the most active alerts (displayed on dashboard as "Users at risk") and investigate cases of potential compromised credentials, or pivot on the associated user account when investigating an alert or device to identify possible lateral movement between devices with that user account.</span></span>

<span data-ttu-id="a7874-112">Informationen zum Benutzerkonto finden Sie in den folgenden Ansichten:</span><span class="sxs-lookup"><span data-stu-id="a7874-112">You can find user account information in the following views:</span></span>

- <span data-ttu-id="a7874-113">Dashboard</span><span class="sxs-lookup"><span data-stu-id="a7874-113">Dashboard</span></span>
- <span data-ttu-id="a7874-114">Warnungswarteschlange</span><span class="sxs-lookup"><span data-stu-id="a7874-114">Alert queue</span></span>
- <span data-ttu-id="a7874-115">Seite "Gerätedetails"</span><span class="sxs-lookup"><span data-stu-id="a7874-115">Device details page</span></span>

<span data-ttu-id="a7874-116">In diesen Ansichten ist ein klickbarer Benutzerkontolink verfügbar, über den Sie zur Seite mit den Benutzerkontodetails gelangen, auf der weitere Details zum Benutzerkonto angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a7874-116">A clickable user account link is available in these views, that will take you to the user account details page where more details about the user account are shown.</span></span>

<span data-ttu-id="a7874-117">Wenn Sie eine Benutzerkontenentität untersuchen, sehen Sie:</span><span class="sxs-lookup"><span data-stu-id="a7874-117">When you investigate a user account entity, you'll see:</span></span>

- <span data-ttu-id="a7874-118">Benutzerkontodetails, Azure Advanced Threat Protection (Azure ATP)-Warnungen und angemeldete Geräte, Rolle, Anmeldetyp und andere Details</span><span class="sxs-lookup"><span data-stu-id="a7874-118">User account details, Azure Advanced Threat Protection (Azure ATP) alerts, and logged on devices, role, logon type, and other details</span></span>
- <span data-ttu-id="a7874-119">Übersicht über vorfälle und Benutzergeräte</span><span class="sxs-lookup"><span data-stu-id="a7874-119">Overview of the incidents and user's devices</span></span>
- <span data-ttu-id="a7874-120">Warnungen im Zusammenhang mit diesem Benutzer</span><span class="sxs-lookup"><span data-stu-id="a7874-120">Alerts related to this user</span></span>
- <span data-ttu-id="a7874-121">Beobachtet in der Organisation (angemeldete Geräte)</span><span class="sxs-lookup"><span data-stu-id="a7874-121">Observed in organization (devices logged on to)</span></span>

![Abbildung der Seite mit den Details der Benutzerkontenentität](images/atp-user-details-view.png)

### <a name="user-details"></a><span data-ttu-id="a7874-123">Benutzerdetails</span><span class="sxs-lookup"><span data-stu-id="a7874-123">User details</span></span>

<span data-ttu-id="a7874-124">Der  Bereich Benutzerdetails auf der linken Seite enthält Informationen über den Benutzer, z. B. verwandte offene Vorfälle, aktive Warnungen, SAM-Name, SID, Azure ATP-Warnungen, Anzahl der Geräte, bei denen der Benutzer angemeldet ist, wann der Benutzer zuerst und zuletzt gesehen wurde, Rollen- und Anmeldetypen.</span><span class="sxs-lookup"><span data-stu-id="a7874-124">The **User details** pane on left provides information about the user, such as related open incidents, active alerts, SAM name, SID, Azure ATP alerts, number of devices the user is logged on to, when the user was first and last seen, role, and logon types.</span></span> <span data-ttu-id="a7874-125">Je nach den von Ihnen aktivierten Integrationsfeatures werden weitere Details zu sehen sein.</span><span class="sxs-lookup"><span data-stu-id="a7874-125">Depending on the integration features you've enabled, you'll see other details.</span></span> <span data-ttu-id="a7874-126">Wenn Sie beispielsweise die Skype for Business-Integration aktivieren, können Sie den Benutzer über das Portal kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="a7874-126">For example, if you enable the Skype for business integration, you'll be able to contact the user from the portal.</span></span> <span data-ttu-id="a7874-127">Der **Abschnitt Azure ATP-Warnungen** enthält einen Link, über den Sie zur Azure ATP-Seite gelangen, wenn Sie das Azure ATP-Feature aktiviert haben und es Warnungen im Zusammenhang mit dem Benutzer gibt.</span><span class="sxs-lookup"><span data-stu-id="a7874-127">The **Azure ATP alerts** section contains a link that will take you to the Azure ATP page, if you have enabled the Azure ATP feature, and there are alerts related to the user.</span></span> <span data-ttu-id="a7874-128">Die Azure ATP-Seite enthält weitere Informationen zu den Warnungen.</span><span class="sxs-lookup"><span data-stu-id="a7874-128">The Azure ATP page will provide more information about the alerts.</span></span>

>[!NOTE]
><span data-ttu-id="a7874-129">Sie müssen die Integration in Azure ATP und Defender for Endpoint aktivieren, um dieses Feature verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="a7874-129">You'll need to enable the integration on both Azure ATP and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="a7874-130">In Defender for Endpoint können Sie dieses Feature in erweiterten Features aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a7874-130">In Defender for Endpoint, you can enable this feature in advanced features.</span></span> <span data-ttu-id="a7874-131">Weitere Informationen zum Aktivieren erweiterter Features finden Sie unter [Turn on advanced features](advanced-features.md).</span><span class="sxs-lookup"><span data-stu-id="a7874-131">For more information on how to enable advanced features, see [Turn on advanced features](advanced-features.md).</span></span>

<span data-ttu-id="a7874-132">Die Registerkarten Übersicht, Warnungen und Beobachtet in der Organisation sind unterschiedliche Registerkarten, die verschiedene Attribute zum Benutzerkonto anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a7874-132">The Overview, Alerts, and Observed in organization are different tabs that display various attributes about the user account.</span></span>

### <a name="overview"></a><span data-ttu-id="a7874-133">Übersicht</span><span class="sxs-lookup"><span data-stu-id="a7874-133">Overview</span></span>

<span data-ttu-id="a7874-134">Auf **der** Registerkarte Übersicht werden die Details zu Vorfällen und eine Liste der Geräte angezeigt, bei der sich der Benutzer angemeldet hat.</span><span class="sxs-lookup"><span data-stu-id="a7874-134">The **Overview** tab shows the incidents details and a list of the devices that the user has logged on to.</span></span> <span data-ttu-id="a7874-135">Sie können diese erweitern, um Details der Anmeldeereignisse für jedes Gerät anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a7874-135">You can expand these to see details of the log-on events for each device.</span></span>

### <a name="alerts"></a><span data-ttu-id="a7874-136">Warnungen</span><span class="sxs-lookup"><span data-stu-id="a7874-136">Alerts</span></span>

<span data-ttu-id="a7874-137">Die **Registerkarte Warnungen** enthält eine Liste der Warnungen, die dem Benutzerkonto zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="a7874-137">The **Alerts** tab provides a list of alerts that are associated with the user account.</span></span> <span data-ttu-id="a7874-138">Diese Liste ist eine gefilterte Ansicht der Warnungswarteschlange [und](alerts-queue.md)zeigt Warnungen an, bei denen der Benutzerkontext das ausgewählte Benutzerkonto ist, das Datum, an dem die letzte Aktivität erkannt wurde, eine kurze Beschreibung der Warnung, das gerät, das der Warnung zugeordnet ist, den Schweregrad der Warnung, den Status der Warnung in der Warteschleife und wem die Warnung zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="a7874-138">This list is a filtered view of the [Alert queue](alerts-queue.md), and shows alerts where the user context is the selected user account, the date when the last activity was detected, a short description of the alert, the device associated with the alert, the alert's severity, the alert's status in the queue, and who is assigned the alert.</span></span>

### <a name="observed-in-organization"></a><span data-ttu-id="a7874-139">Beobachtet in der Organisation</span><span class="sxs-lookup"><span data-stu-id="a7874-139">Observed in organization</span></span>

<span data-ttu-id="a7874-140">Auf der Registerkarte **Beobachtet in** der Organisation können Sie einen Datumsbereich angeben, um eine Liste der Geräte zu sehen, auf denen dieser Benutzer angemeldet war, das häufigste und am wenigsten häufig angemeldete Benutzerkonto für jedes dieser Geräte und die Gesamtzahl der beobachteten Benutzer auf jedem Gerät.</span><span class="sxs-lookup"><span data-stu-id="a7874-140">The **Observed in organization** tab allows you to specify a date range to see a list of devices where this user was observed logged on to, the most frequent and least frequent logged on user account for each of these devices, and total observed users on each device.</span></span>

<span data-ttu-id="a7874-141">Durch Auswählen eines Elements in der Tabelle Beobachtet in der Organisation wird das Element erweitert, und es werden weitere Details zum Gerät angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a7874-141">Selecting an item on the Observed in organization table will expand the item, revealing more details about the device.</span></span> <span data-ttu-id="a7874-142">Wenn Sie direkt einen Link innerhalb eines Elements auswählen, gelangen Sie zur entsprechenden Seite.</span><span class="sxs-lookup"><span data-stu-id="a7874-142">Directly selecting a link within an item will send you to the corresponding page.</span></span>

## <a name="search-for-specific-user-accounts"></a><span data-ttu-id="a7874-143">Suchen nach bestimmten Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="a7874-143">Search for specific user accounts</span></span>

1. <span data-ttu-id="a7874-144">Wählen **Sie im** Dropdownmenü **Suchleiste** Die Option Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="a7874-144">Select **User** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="a7874-145">Geben Sie das Benutzerkonto in das Feld **Suchen** ein.</span><span class="sxs-lookup"><span data-stu-id="a7874-145">Enter the user account in the **Search** field.</span></span>
3. <span data-ttu-id="a7874-146">Klicken Sie auf das Suchsymbol, oder drücken Sie die **EINGABETASTE.**</span><span class="sxs-lookup"><span data-stu-id="a7874-146">Click the search icon or press **Enter**.</span></span>

<span data-ttu-id="a7874-147">Eine Liste der Benutzer, die mit dem Abfragetext übereinstimmen, wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a7874-147">A list of users matching the query text is displayed.</span></span> <span data-ttu-id="a7874-148">Sie sehen die Domäne und den Namen des Benutzerkontos, wenn das Benutzerkonto zuletzt gesehen wurde, und die Gesamtzahl der Geräte, auf denen es in den letzten 30 Tagen angemeldet war.</span><span class="sxs-lookup"><span data-stu-id="a7874-148">You'll see the user account's domain and name, when the user account was last seen, and the total number of devices it was observed logged on to in the last 30 days.</span></span>

<span data-ttu-id="a7874-149">Sie können die Ergebnisse nach den folgenden Zeiträumen filtern:</span><span class="sxs-lookup"><span data-stu-id="a7874-149">You can filter the results by the following time periods:</span></span>

- <span data-ttu-id="a7874-150">1 Tag</span><span class="sxs-lookup"><span data-stu-id="a7874-150">1 day</span></span>
- <span data-ttu-id="a7874-151">3 Tage</span><span class="sxs-lookup"><span data-stu-id="a7874-151">3 days</span></span>
- <span data-ttu-id="a7874-152">7 Tage</span><span class="sxs-lookup"><span data-stu-id="a7874-152">7 days</span></span>
- <span data-ttu-id="a7874-153">30 Tage</span><span class="sxs-lookup"><span data-stu-id="a7874-153">30 days</span></span>
- <span data-ttu-id="a7874-154">6 Monate</span><span class="sxs-lookup"><span data-stu-id="a7874-154">6 months</span></span>

## <a name="related-topics"></a><span data-ttu-id="a7874-155">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a7874-155">Related topics</span></span>

- [<span data-ttu-id="a7874-156">Anzeigen und Organisieren der Microsoft Defender for Endpoint Alerts-Warteschlange</span><span class="sxs-lookup"><span data-stu-id="a7874-156">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="a7874-157">Verwalten von Microsoft Defender for Endpoint-Warnungen</span><span class="sxs-lookup"><span data-stu-id="a7874-157">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="a7874-158">Untersuchen von Microsoft Defender for Endpoint-Warnungen</span><span class="sxs-lookup"><span data-stu-id="a7874-158">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="a7874-159">Untersuchen einer Datei, die einer Defender for Endpoint-Warnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="a7874-159">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="a7874-160">Untersuchen von Geräten in der Liste "Defender for Endpoint Devices"</span><span class="sxs-lookup"><span data-stu-id="a7874-160">Investigate devices in the Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="a7874-161">Untersuchen einer einer Defender for Endpoint-Warnung zugeordneten IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="a7874-161">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="a7874-162">Untersuchen einer Domäne, die einer Defender for Endpoint-Warnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="a7874-162">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
