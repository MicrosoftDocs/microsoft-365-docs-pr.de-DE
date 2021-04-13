---
title: Überprüfen der Integrität des Microsoft Defender for Endpoint-Diensts
description: Überprüfen Sie die Integrität des Microsoft Defender for Endpoint-Diensts, überprüfen Sie, ob beim Dienst Probleme auftreten, und überprüfen Sie frühere Probleme, die behoben wurden.
keywords: dashboard, service, issues, service health, current status, status history, summary of impact, preliminary root cause, resolution, resolution time, expected resolution time
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
ms.technology: mde
ms.openlocfilehash: 1b4545daace5df1a1a9c6e827f7d8f1b522a690c
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687625"
---
# <a name="check-the-microsoft-defender-for-endpoint-service-health"></a><span data-ttu-id="448ef-104">Überprüfen der Integrität des Microsoft Defender for Endpoint-Diensts</span><span class="sxs-lookup"><span data-stu-id="448ef-104">Check the Microsoft Defender for Endpoint service health</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="448ef-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="448ef-105">**Applies to:**</span></span>
- [<span data-ttu-id="448ef-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="448ef-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)



><span data-ttu-id="448ef-107">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="448ef-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="448ef-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="448ef-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-servicestatus-abovefoldlink)

<span data-ttu-id="448ef-109">**Der Dienststatus** enthält Informationen zum aktuellen Status des Defender for Endpoint-Diensts.</span><span class="sxs-lookup"><span data-stu-id="448ef-109">**Service health** provides information on the current status of the Defender for Endpoint service.</span></span> <span data-ttu-id="448ef-110">Sie können überprüfen, ob der Dienstzustand fehlerfrei ist oder aktuelle Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="448ef-110">You'll be able to verify that the service health is healthy or if there are current issues.</span></span> <span data-ttu-id="448ef-111">Wenn Probleme auftreten, werden Informationen wie der Zeitpunkt des Auftretens des Problems, die vorläufige Ursache und die erwartete Lösungszeit ermittelt.</span><span class="sxs-lookup"><span data-stu-id="448ef-111">If there are issues, you'll see information such as when the issue was detected, what the preliminary root cause is, and the expected resolution time.</span></span>

<span data-ttu-id="448ef-112">Außerdem werden Informationen zu behobenen verlaufshistorischen Problemen sowie Details wie Datum und Uhrzeit der Problem behoben.</span><span class="sxs-lookup"><span data-stu-id="448ef-112">You'll also see information on historical issues that have been resolved and details such as the date and time when the issue was resolved.</span></span> <span data-ttu-id="448ef-113">Wenn keine Probleme mit dem Dienst auftreten, wird ein fehlerfreier Status angezeigt.</span><span class="sxs-lookup"><span data-stu-id="448ef-113">When there are no issues on the service, you'll see a healthy status.</span></span>

<span data-ttu-id="448ef-114">Sie können Details zum Dienstzustand anzeigen, indem  Sie im Dashboard für Sicherheitsvorgänge auf die Kachel klicken oder im Navigationsbereich das Menü Dienstintehzustand auswählen. </span><span class="sxs-lookup"><span data-stu-id="448ef-114">You can view details on the service health by clicking the tile from the **Security operations dashboard** or selecting the **Service health** menu from the navigation pane.</span></span>

<span data-ttu-id="448ef-115">Auf der Seite Dienstintegtezustandsdetails sind die folgenden Registerkarten verfügbar: </span><span class="sxs-lookup"><span data-stu-id="448ef-115">The **Service health** details page has the following tabs:</span></span>

- <span data-ttu-id="448ef-116">**Aktueller Status**</span><span class="sxs-lookup"><span data-stu-id="448ef-116">**Current status**</span></span>
- <span data-ttu-id="448ef-117">**Statusverlauf**</span><span class="sxs-lookup"><span data-stu-id="448ef-117">**Status history**</span></span>

## <a name="current-status"></a><span data-ttu-id="448ef-118">Aktueller Status</span><span class="sxs-lookup"><span data-stu-id="448ef-118">Current status</span></span>
<span data-ttu-id="448ef-119">Auf **der Registerkarte Aktueller Status** wird der aktuelle Status des Defender for Endpoint-Diensts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="448ef-119">The **Current status** tab shows the current state of the Defender for Endpoint service.</span></span> <span data-ttu-id="448ef-120">Wenn der Dienst reibungslos ausgeführt wird, wird ein fehlerfreier Dienstzustand angezeigt.</span><span class="sxs-lookup"><span data-stu-id="448ef-120">When the service is running smoothly a healthy service health is shown.</span></span> <span data-ttu-id="448ef-121">Wenn Probleme auftreten, werden die folgenden Dienstdetails angezeigt, um ihnen einen besseren Einblick in das Problem zu verschaffen:</span><span class="sxs-lookup"><span data-stu-id="448ef-121">If there are issues seen, the following service details are shown to help you gain better insight about the issue:</span></span>

- <span data-ttu-id="448ef-122">Datum und Uhrzeit, zu dem das Problem erkannt wurde</span><span class="sxs-lookup"><span data-stu-id="448ef-122">Date and time for when the issue was detected</span></span>
- <span data-ttu-id="448ef-123">Eine kurze Beschreibung des Problems</span><span class="sxs-lookup"><span data-stu-id="448ef-123">A short description of the issue</span></span>
- <span data-ttu-id="448ef-124">Updatezeit</span><span class="sxs-lookup"><span data-stu-id="448ef-124">Update time</span></span>
- <span data-ttu-id="448ef-125">Zusammenfassung der Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="448ef-125">Summary of impact</span></span>
- <span data-ttu-id="448ef-126">Vorläufige Ursache</span><span class="sxs-lookup"><span data-stu-id="448ef-126">Preliminary root cause</span></span>
- <span data-ttu-id="448ef-127">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="448ef-127">Next steps</span></span>
- <span data-ttu-id="448ef-128">Erwartete Auflösungszeit</span><span class="sxs-lookup"><span data-stu-id="448ef-128">Expected resolution time</span></span>

<span data-ttu-id="448ef-129">Updates zum Fortschritt eines Problems werden auf der Seite angezeigt, sobald das Problem behoben wird.</span><span class="sxs-lookup"><span data-stu-id="448ef-129">Updates on the progress of an issue are reflected on the page as the issue gets resolved.</span></span> <span data-ttu-id="448ef-130">Es werden Updates zu Informationen wie einer aktualisierten Schätzungsauflösungszeit oder den nächsten Schritten zu sehen sein.</span><span class="sxs-lookup"><span data-stu-id="448ef-130">You'll see updates on information such as an updated estimate resolution time or next steps.</span></span>

<span data-ttu-id="448ef-131">Wenn ein Problem behoben wird, wird es auf der Registerkarte **Statusverlauf** aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="448ef-131">When an issue is resolved, it gets recorded in the **Status history** tab.</span></span>

## <a name="status-history"></a><span data-ttu-id="448ef-132">Statusverlauf</span><span class="sxs-lookup"><span data-stu-id="448ef-132">Status history</span></span>
<span data-ttu-id="448ef-133">Die **Registerkarte Statusverlauf** gibt alle historischen Probleme wieder, die angezeigt und behoben wurden.</span><span class="sxs-lookup"><span data-stu-id="448ef-133">The **Status history** tab reflects all the historical issues that were seen and resolved.</span></span> <span data-ttu-id="448ef-134">Sie sehen Details zu den behobenen Problemen zusammen mit den anderen Informationen, die während der Lösung enthalten waren.</span><span class="sxs-lookup"><span data-stu-id="448ef-134">You'll see details of the resolved issues along with the other information that were included while it was being resolved.</span></span>

### <a name="related-topic"></a><span data-ttu-id="448ef-135">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="448ef-135">Related topic</span></span>
- [<span data-ttu-id="448ef-136">Anzeigen des Dashboards für Sicherheitsvorgänge</span><span class="sxs-lookup"><span data-stu-id="448ef-136">View the Security operations dashboard</span></span>](security-operations-dashboard.md)
