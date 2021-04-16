---
title: Vorfälle in Microsoft 365 Defender
description: Untersuchen Sie Vorfälle, die auf Geräten, bei Benutzern und in Postfächern auftreten.
keywords: Vorfälle, Warnungen, untersuchen, Korrelation, Angriff, Computer, Geräte, Benutzer, Identitäten, Identität, Postfach, E-Mail, 365, Microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e1e028f7b58df07eccf945b3a79012b4ea12366d
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861623"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="22a26-104">Vorfälle in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="22a26-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="22a26-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="22a26-105">**Applies to:**</span></span>
- <span data-ttu-id="22a26-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="22a26-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="22a26-107">Sie möchten Microsoft 365 Defender ausprobieren?</span><span class="sxs-lookup"><span data-stu-id="22a26-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="22a26-108">Sie können [in einer Laborumgebung auswerten](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) oder [ein Pilotprojekt in der Produktionsumgebung ausführen](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="22a26-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="22a26-109">Bei einem Vorfall in Microsoft 365 Defender handelt es sich um eine Sammlung korrelierter Warnungen und zugehöriger Daten, die die Geschichte eines Angriffs enthalten.</span><span class="sxs-lookup"><span data-stu-id="22a26-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="22a26-110">Microsoft 365-Dienste und -Apps erstellen Warnungen, wenn sie ein verdächtiges oder böswilliges Ereignis oder eine Aktivität erkennen.</span><span class="sxs-lookup"><span data-stu-id="22a26-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="22a26-111">Einzelne Warnungen liefern wertvolle Hinweise zu einem abgeschlossenen oder laufenden Angriff.</span><span class="sxs-lookup"><span data-stu-id="22a26-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="22a26-112">Bei Angriffen werden jedoch in der Regel verschiedene Techniken gegen verschiedene Typen von Entitäten verwendet, z. B. Geräte, Benutzer und Postfächer.</span><span class="sxs-lookup"><span data-stu-id="22a26-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="22a26-113">Das Ergebnis sind mehrere Warnungen für mehrere Entitäten in Ihrem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="22a26-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="22a26-114">Da das Verbinden der einzelnen Warnungen, um Einblick in einen Angriff zu erhalten, eine Herausforderung und zeitaufwändige Aufgabe sein kann, aggregiert Microsoft 365 Defender die Warnungen und ihre zugehörigen Informationen automatisch zu einem Vorfall.</span><span class="sxs-lookup"><span data-stu-id="22a26-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Korrelieren von Ereignissen von Entitäten zu einem Vorfall in Microsoft 365 Defender":::

<span data-ttu-id="22a26-116">Sehen Sie sich diese kurze Übersicht über Vorfälle in Microsoft 365 Defender (4 Minuten) an.</span><span class="sxs-lookup"><span data-stu-id="22a26-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="22a26-117">Durch das Gruppieren verwandter Warnungen zu einem Vorfall erhalten Sie eine umfassende Ansicht eines Angriffs.</span><span class="sxs-lookup"><span data-stu-id="22a26-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="22a26-118">Sie können z. B. folgende Informationen sehen:</span><span class="sxs-lookup"><span data-stu-id="22a26-118">For example, you can see:</span></span>

- <span data-ttu-id="22a26-119">An der Stelle, an der der Angriff begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="22a26-119">Where the attack started.</span></span>
- <span data-ttu-id="22a26-120">Welche Taktiken verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="22a26-120">What tactics were used.</span></span>
- <span data-ttu-id="22a26-121">Wie weit der Angriff in Ihren Mandanten gegangen ist.</span><span class="sxs-lookup"><span data-stu-id="22a26-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="22a26-122">Der Umfang des Angriffs, z. B. wie viele Geräte, Benutzer und Postfächer betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="22a26-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="22a26-123">Alle dem Angriff zugeordneten Daten.</span><span class="sxs-lookup"><span data-stu-id="22a26-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="22a26-124">Wenn [diese Option](m365d-enable.md)aktiviert ist, kann Microsoft 365 Defender Warnungen automatisch durch Automatisierung und künstliche Intelligenz untersuchen und auflösen.</span><span class="sxs-lookup"><span data-stu-id="22a26-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can automatically investigate and resolve alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="22a26-125">Sie können auch zusätzliche Korrekturschritte ausführen, um den Angriff zu beheben.</span><span class="sxs-lookup"><span data-stu-id="22a26-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a><span data-ttu-id="22a26-126">Vorfälle und Warnungen im Microsoft 365 Security Center</span><span class="sxs-lookup"><span data-stu-id="22a26-126">Incidents and alerts in the Microsoft 365 security center</span></span>

<span data-ttu-id="22a26-127">Sie verwalten Vorfälle aus Vorfällen **& Warnungen > Vorfällen** beim Schnellstart des Microsoft 365 Security Centers ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="22a26-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="22a26-128">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="22a26-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Die Seite &quot;Vorfälle&quot; im Microsoft 365 Security Center":::

<span data-ttu-id="22a26-130">Wenn Sie einen Vorfallnamen auswählen, wird eine Zusammenfassung des Vorfalls und der Zugriff auf Registerkarten mit zusätzlichen Informationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="22a26-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Beispiel für die Zusammenfassungsseite für einen Vorfall im Microsoft 365 Security Center":::

<span data-ttu-id="22a26-132">Die zusätzlichen Registerkarten für einen Vorfall sind:</span><span class="sxs-lookup"><span data-stu-id="22a26-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="22a26-133">Warnungen</span><span class="sxs-lookup"><span data-stu-id="22a26-133">Alerts</span></span> 

  <span data-ttu-id="22a26-134">Alle Warnungen im Zusammenhang mit dem Vorfall und deren Informationen.</span><span class="sxs-lookup"><span data-stu-id="22a26-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="22a26-135">Geräte</span><span class="sxs-lookup"><span data-stu-id="22a26-135">Devices</span></span>

  <span data-ttu-id="22a26-136">Alle Geräte, die als Teil oder im Zusammenhang mit dem Vorfall identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="22a26-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="22a26-137">Benutzer</span><span class="sxs-lookup"><span data-stu-id="22a26-137">Users</span></span>

  <span data-ttu-id="22a26-138">Alle Benutzer, die als Teil des Vorfalls oder im Zusammenhang mit dem Vorfall identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="22a26-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="22a26-139">Postfächer</span><span class="sxs-lookup"><span data-stu-id="22a26-139">Mailboxes</span></span>

  <span data-ttu-id="22a26-140">Alle Postfächer, die als Teil oder im Zusammenhang mit dem Vorfall identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="22a26-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="22a26-141">Untersuchungen</span><span class="sxs-lookup"><span data-stu-id="22a26-141">Investigations</span></span>

  <span data-ttu-id="22a26-142">Alle automatisierten Untersuchungen, die durch Warnungen im Vorfall ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="22a26-142">All the automated investigations triggered by alerts in the incident.</span></span>

- <span data-ttu-id="22a26-143">Nachweis und Antwort</span><span class="sxs-lookup"><span data-stu-id="22a26-143">Evidence and Response</span></span>

  <span data-ttu-id="22a26-144">Alle unterstützten Ereignisse und verdächtigen Entitäten in den Warnungen im Vorfall.</span><span class="sxs-lookup"><span data-stu-id="22a26-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

<span data-ttu-id="22a26-145">Hier sehen Sie die Beziehung zwischen einem Vorfall und seinen Daten und den Registerkarten eines Vorfalls im Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="22a26-145">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="Die Beziehung eines Vorfalls und seiner Daten zu den Registerkarten eines Vorfalls im Microsoft 365 Security Center":::

## <a name="next-step"></a><span data-ttu-id="22a26-147">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="22a26-147">Next step</span></span>

<span data-ttu-id="22a26-148">In der Warteschleife auf der **Seite** Vorfälle werden die neuesten Vorfälle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="22a26-148">The incident queue from the **Incidents** page lists the most recent incidents.</span></span> <span data-ttu-id="22a26-149">Hier haben Sie folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="22a26-149">From here, you can:</span></span>

- <span data-ttu-id="22a26-150">Sehen Sie sich an, welche [Vorfälle](incident-queue.md) basierend auf dem Schweregrad und anderen Faktoren priorisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="22a26-150">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 
- <span data-ttu-id="22a26-151">Führen Sie eine [Untersuchung](investigate-incidents.md) eines Vorfalls durch.</span><span class="sxs-lookup"><span data-stu-id="22a26-151">Perform an [investigation](investigate-incidents.md) of an incident.</span></span>
- <span data-ttu-id="22a26-152">[Verwalten von Vorfällen,](manage-incidents.md)einschließlich Umbenennen, Zuweisen, Klassifizieren und Hinzufügen von Tags für Ihren Workflow für die Vorfallverwaltung.</span><span class="sxs-lookup"><span data-stu-id="22a26-152">[Manage incidents](manage-incidents.md), which includes renaming, assigning them, classifying, and adding tags for your incident management workflow.</span></span>
