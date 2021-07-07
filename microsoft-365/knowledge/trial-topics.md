---
title: Ausführen einer Testversion von Microsoft Viva Topics
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: ''
search.appverid: ''
localization_priority: Normal
description: Erfahren Sie, wie Sie ein Testpilotprogramm für Microsoft Viva Topics in Ihrer Organisation planen und ausführen.
ms.openlocfilehash: 128e82e7664a76baa55d37e983319c9f344624fd
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327113"
---
# <a name="run-a-trial-of-microsoft-viva-topics"></a><span data-ttu-id="9bebe-103">Ausführen einer Testversion von Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="9bebe-103">Run a trial of Microsoft Viva Topics</span></span>

<span data-ttu-id="9bebe-104">In diesem Artikel wird beschrieben, wie Sie ein Testpilotprogramm einrichten und ausführen, um Viva Topics in Ihrer Organisation bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="9bebe-104">This article describes how to set up and run a trial pilot program to deploy Viva Topics to your organization.</span></span> <span data-ttu-id="9bebe-105">In diesem Artikel werden auch bewährte Methoden für die Testversion empfohlen.</span><span class="sxs-lookup"><span data-stu-id="9bebe-105">This article also recommends best practices for the trial.</span></span>

## <a name="sign-up-for-a-trial"></a><span data-ttu-id="9bebe-106">Registrieren für eine Testversion</span><span class="sxs-lookup"><span data-stu-id="9bebe-106">Sign up for a trial</span></span>

<span data-ttu-id="9bebe-107">Testversionen sind aus einer der folgenden Quellen öffentlich verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9bebe-107">Trials are publicly available from one of the following sources.</span></span> <span data-ttu-id="9bebe-108">Diese Testversionen bieten 25 Benutzern 30 Tage lang Zugriff auf Viva Topics.</span><span class="sxs-lookup"><span data-stu-id="9bebe-108">These trials offer 25 users access to Viva Topics for 30 days.</span></span>

- <span data-ttu-id="9bebe-109">Die [Viva Topics-Produktseite](https://www.microsoft.com/microsoft-viva/topics?activetab=pivot:overviewtab)</span><span class="sxs-lookup"><span data-stu-id="9bebe-109">The [Viva Topics product page](https://www.microsoft.com/microsoft-viva/topics?activetab=pivot:overviewtab)</span></span>

- <span data-ttu-id="9bebe-110">Die [Microsoft 365 Admin Center](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="9bebe-110">The [Microsoft 365 admin center](https://admin.microsoft.com)</span></span>
    1.  <span data-ttu-id="9bebe-111">Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.</span><span class="sxs-lookup"><span data-stu-id="9bebe-111">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
    2.  <span data-ttu-id="9bebe-112">Wechseln Sie zu  >  **Abrechnungskaufdienste**.</span><span class="sxs-lookup"><span data-stu-id="9bebe-112">Go to **Billing** > **Purchase Services**.</span></span>
    3.  <span data-ttu-id="9bebe-113">Blättern Sie nach unten zum Bereich **Add-Ons**.</span><span class="sxs-lookup"><span data-stu-id="9bebe-113">Scroll down to the **Add-Ons** section.</span></span>
    4.  <span data-ttu-id="9bebe-114">Wählen Sie auf der Kachel **"Themenoberflächen"** die Option **"Details"** aus.</span><span class="sxs-lookup"><span data-stu-id="9bebe-114">On the **Topic Experiences** tile, select **Details**.</span></span>
    5.  <span data-ttu-id="9bebe-115">Wählen Sie **Kostenlose Testversion abrufen** aus.</span><span class="sxs-lookup"><span data-stu-id="9bebe-115">Select **Get free trial**.</span></span>
    6.  <span data-ttu-id="9bebe-116">Führen Sie die verbleibenden Schritte des Assistenten aus, um die Testversion zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="9bebe-116">Follow the remaining wizard steps to confirm the trial.</span></span>

<span data-ttu-id="9bebe-117">Sie müssen ein Microsoft 365 globaler Administrator oder Abrechnungsadministrator sein, um eine Testversion zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9bebe-117">You must be a Microsoft 365 global administrator or billing administrator to activate a trial.</span></span>

> [!NOTE]
> <span data-ttu-id="9bebe-118">Öffentliche Testversionen können nur einmal für jeden Microsoft 365 Mandanten hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="9bebe-118">Public trials can only be added once for each Microsoft 365 tenant.</span></span>

### <a name="who-should-be-involved-in-a-trial"></a><span data-ttu-id="9bebe-119">Wer an einer Testversion beteiligt sein sollten</span><span class="sxs-lookup"><span data-stu-id="9bebe-119">Who should be involved in a trial</span></span>

|<span data-ttu-id="9bebe-120">Rolle</span><span class="sxs-lookup"><span data-stu-id="9bebe-120">Role</span></span>  |<span data-ttu-id="9bebe-121">Aktivität</span><span class="sxs-lookup"><span data-stu-id="9bebe-121">Activity</span></span>  |
|---------|---------|
|<span data-ttu-id="9bebe-122">Microsoft 365 globaler Administrator oder Abrechnungsadministrator</span><span class="sxs-lookup"><span data-stu-id="9bebe-122">Microsoft 365 global admin or billing admin</span></span>  |   <span data-ttu-id="9bebe-123">Aktivieren der Testversion und Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="9bebe-123">Activate the trial and assign licenses</span></span>      |
|<span data-ttu-id="9bebe-124">Microsoft 365 globaler Administrator oder SharePoint-Administrator</span><span class="sxs-lookup"><span data-stu-id="9bebe-124">Microsoft 365 global admin or SharePoint admin</span></span>    |       <span data-ttu-id="9bebe-125">Konfigurieren von Viva Topics und Erstellen von Themencentern</span><span class="sxs-lookup"><span data-stu-id="9bebe-125">Configure  Viva Topics and create topic centers</span></span>  |
|<span data-ttu-id="9bebe-126">Geschäftsbenutzer</span><span class="sxs-lookup"><span data-stu-id="9bebe-126">Business user</span></span>     |   <span data-ttu-id="9bebe-127">Durchführen von Rollen als Wissensmanager, Themenmitwirkender und Themenkunde</span><span class="sxs-lookup"><span data-stu-id="9bebe-127">Perform knowledge manager, topic contributor, and topic consumer roles</span></span>      |

### <a name="before-you-activate-a-trial"></a><span data-ttu-id="9bebe-128">Vor der Aktivierung einer Testversion</span><span class="sxs-lookup"><span data-stu-id="9bebe-128">Before you activate a trial</span></span>

<span data-ttu-id="9bebe-129">Die Planung ist für eine effektive Testversion von Viva Topics unerlässlich.</span><span class="sxs-lookup"><span data-stu-id="9bebe-129">Planning is essential for an effective trial of Viva Topics.</span></span> <span data-ttu-id="9bebe-130">Der Testzeitraum ist begrenzt und muss die Themensuche umfassen und themenbezogene Qualität, Verwaltung und Endbenutzererfahrungen untersuchen.</span><span class="sxs-lookup"><span data-stu-id="9bebe-130">The trial period is limited and must include topic discovery and exploring topic quality, management, and end-user experiences.</span></span>

#### <a name="discovery"></a><span data-ttu-id="9bebe-131">Discovery</span><span class="sxs-lookup"><span data-stu-id="9bebe-131">Discovery</span></span>

<span data-ttu-id="9bebe-132">Es gibt zwei allgemeine Strategieoptionen für die Konfiguration der Themenermittlung während einer Testversion:</span><span class="sxs-lookup"><span data-stu-id="9bebe-132">There are two high-level strategy options for configuration of topic discovery during a trial:</span></span>

- <span data-ttu-id="9bebe-133">Indizieren Sie alle oder den größten Teil Ihrer SharePoint Onlineinhalte.</span><span class="sxs-lookup"><span data-stu-id="9bebe-133">Index all or most of your SharePoint Online content.</span></span>
   - <span data-ttu-id="9bebe-134">Bei großen Mandanten kann es bis zu zwei Wochen dauern, bis die Indizierung vollständig erfolgt ist.</span><span class="sxs-lookup"><span data-stu-id="9bebe-134">Large tenants can take up to two weeks to fully index.</span></span> <span data-ttu-id="9bebe-135">Während Themen während dieses Zeitraums inkrementell generiert werden, kann die vollständige Indizierung bis zur Hälfte des Testzeitraums beanspruchen.</span><span class="sxs-lookup"><span data-stu-id="9bebe-135">While topics will be generated incrementally throughout this period, full indexing could consume up to half the trial period.</span></span>
   - <span data-ttu-id="9bebe-136">Für Mandanten mit einem erheblichen Datenvolumen kann diese Option eine sehr große Anzahl von Themen erzeugen, möglicherweise Zehntausend.</span><span class="sxs-lookup"><span data-stu-id="9bebe-136">For tenants with a significant volume of data, this option can produce a very large number of topics, perhaps tens of thousands.</span></span>

- <span data-ttu-id="9bebe-137">Identifizieren Sie eine Teilmenge Ihrer SharePoint Websites für die Indizierung.</span><span class="sxs-lookup"><span data-stu-id="9bebe-137">Identify a subset of your SharePoint sites for indexing.</span></span>

<span data-ttu-id="9bebe-138">Die Auswahl dieser Strategien ist eine Balance zwischen den folgenden beiden Faktoren:</span><span class="sxs-lookup"><span data-stu-id="9bebe-138">The choice of these strategies is a balance of the following two factors:</span></span>

- <span data-ttu-id="9bebe-139">Genügend Daten, um sinnvolle Themen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="9bebe-139">Having enough data to generate meaningful topics.</span></span> <span data-ttu-id="9bebe-140">Die KI in Viva Topics ist auf die Arbeit mit großen Datasets abgestimmt, idealerweise an Datasets mit mehr als 10.000 Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="9bebe-140">The AI in Viva Topics is tuned to work on large datasets, ideally ones that have more than 10,000 documents.</span></span>
- <span data-ttu-id="9bebe-141">Es ist überwältigend, während des Testzeitraums nicht so viele Themen zu generieren, dass die Auswertung während des verfügbaren Zeitraums überwältigend ist.</span><span class="sxs-lookup"><span data-stu-id="9bebe-141">Not generating so many topics during the trial period that evaluating them during the available time period is overwhelming.</span></span>

<span data-ttu-id="9bebe-142">Für die meisten Organisationen ergibt die zweite Strategie das beste Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="9bebe-142">For most organizations, the second strategy produces the best outcome.</span></span>

> [!NOTE]
> <span data-ttu-id="9bebe-143">Aufgrund der Anzahl von Dokumenten, die für die KI erforderlich sind, empfehlen wir, Viva Topics-Testversionen auf einem Produktionsmandanten auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9bebe-143">Due to the number of documents required by the AI, we recommend that you run Viva Topics trials on a production tenant.</span></span> <span data-ttu-id="9bebe-144">Es gibt keine Auswirkungen auf die Leistung des Mandanten während dieses Zeitraums.</span><span class="sxs-lookup"><span data-stu-id="9bebe-144">There’s no impact on the performance of the tenant during this period.</span></span> <span data-ttu-id="9bebe-145">Nur Benutzer, die über eine Testlizenz verfügen, können auf die Viva Topics-Benutzeroberfläche zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9bebe-145">Only users who have a trial license can access Viva Topics user experiences.</span></span>

#### <a name="roles"></a><span data-ttu-id="9bebe-146">Rollen</span><span class="sxs-lookup"><span data-stu-id="9bebe-146">Roles</span></span>

<span data-ttu-id="9bebe-147">Während der Testversion müssen drei Rollen aktiv sein, die in der folgenden Tabelle beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="9bebe-147">During the trial, there are three roles that must be active, which are described in the following table.</span></span>

|<span data-ttu-id="9bebe-148">Rolle</span><span class="sxs-lookup"><span data-stu-id="9bebe-148">Role</span></span>  |<span data-ttu-id="9bebe-149">Aktivität</span><span class="sxs-lookup"><span data-stu-id="9bebe-149">Activity</span></span>  |
|---------|---------|
|<span data-ttu-id="9bebe-150">Wissensmanager</span><span class="sxs-lookup"><span data-stu-id="9bebe-150">Knowledge manager</span></span>     |   <span data-ttu-id="9bebe-151">Steuern der Lebenszyklusphasen von Themen; Themen bestätigen und entfernen; Als Community-Manager für Themenmitwirkende fungieren</span><span class="sxs-lookup"><span data-stu-id="9bebe-151">Control the lifecycle stages of topics; confirm and remove topics; act as a community manager for topic contributors</span></span>      |
|<span data-ttu-id="9bebe-152">Themenmitwirkender</span><span class="sxs-lookup"><span data-stu-id="9bebe-152">Topic contributor</span></span>    |      <span data-ttu-id="9bebe-153">Fachexperten für Inhalte, die Folgendes können:</span><span class="sxs-lookup"><span data-stu-id="9bebe-153">Content subject matter experts, who can:</span></span><br> <span data-ttu-id="9bebe-154">Themen überprüfen, um die Qualität von DURCH KI definierten Inhalten zu bewerten</span><span class="sxs-lookup"><span data-stu-id="9bebe-154">Review topics to evaluate the quality of AI-defined content</span></span><br><span data-ttu-id="9bebe-155">Kuratieren von entdeckten Themen mit zusätzlichem Inhalt</span><span class="sxs-lookup"><span data-stu-id="9bebe-155">Curate discovered topics with additional content</span></span><br><span data-ttu-id="9bebe-156">Erstellen zusätzlicher Themen, die von KI nicht entdeckt wurden</span><span class="sxs-lookup"><span data-stu-id="9bebe-156">Create additional topics that weren’t discovered by AI</span></span>   |
|<span data-ttu-id="9bebe-157">Topic Consumer</span><span class="sxs-lookup"><span data-stu-id="9bebe-157">Topic consumer</span></span>    |     <span data-ttu-id="9bebe-158">Themen über Seitenhighlights und Suche nutzen</span><span class="sxs-lookup"><span data-stu-id="9bebe-158">Consume topics through page highlights and search</span></span><br><span data-ttu-id="9bebe-159">Geben Sie Feedback zum Wert der präsentierten Themen.</span><span class="sxs-lookup"><span data-stu-id="9bebe-159">Provide feedback on the value of the topics presented</span></span>    |

#### <a name="expected-topics"></a><span data-ttu-id="9bebe-160">Themen erwartet</span><span class="sxs-lookup"><span data-stu-id="9bebe-160">Expected topics</span></span>

<span data-ttu-id="9bebe-161">Es kann hilfreich sein, die Themen zu dokumentieren, von denen Sie erwarten, dass sie von der KI generiert werden, auch wenn dies nur auf Annahmen basiert.</span><span class="sxs-lookup"><span data-stu-id="9bebe-161">It can be useful to document the topics you expect to be generated by the AI, even if this is based only on assumptions.</span></span> <span data-ttu-id="9bebe-162">Diese Aufgabe wird am einfachsten abgeschlossen, wenn Sie eine definierte Teilmenge Ihrer SharePoint Websites indizieren, für die SMEs leicht identifiziert werden können.</span><span class="sxs-lookup"><span data-stu-id="9bebe-162">This task is most easily completed when you index a defined subset of your SharePoint sites for which SMEs can be easily identified.</span></span>

<span data-ttu-id="9bebe-163">Eine dokumentierte Liste hilft Ihnen dabei:</span><span class="sxs-lookup"><span data-stu-id="9bebe-163">Having a documented list will help you to:</span></span>

- <span data-ttu-id="9bebe-164">Überprüfen Sie die Liste der durch KI generierten Themen, die möglicherweise größer als erwartet sind.</span><span class="sxs-lookup"><span data-stu-id="9bebe-164">Review the list of AI-generated topics, which might be larger than you expect.</span></span>
- <span data-ttu-id="9bebe-165">Kennen Sie die Themen, die Sie möglicherweise manuell erstellen müssen oder die Prioritäten für die Kuratierung sind.</span><span class="sxs-lookup"><span data-stu-id="9bebe-165">Know the topics you might need to manually create or that are priorities for curation.</span></span>

<span data-ttu-id="9bebe-166">Bei einer erfolgreichen Bereitstellung oder Testversion von Viva Topics ist immer eine Mischung aus von KI definierten und vom Menschen erstellten Themen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9bebe-166">There will always be a need for a mixture of AI-defined and human-created topics in a successful deployment or trial of Viva Topics.</span></span>

## <a name="activate-a-trial"></a><span data-ttu-id="9bebe-167">Aktivieren einer Testversion</span><span class="sxs-lookup"><span data-stu-id="9bebe-167">Activate a trial</span></span>

<span data-ttu-id="9bebe-168">Wenn Sie eine Testversion initiieren, müssen Sie:</span><span class="sxs-lookup"><span data-stu-id="9bebe-168">When you initiate a trial, you need to:</span></span>

- <span data-ttu-id="9bebe-169">Weisen Sie den relevanten Benutzern Lizenzen zu.</span><span class="sxs-lookup"><span data-stu-id="9bebe-169">Assign licenses to the relevant users.</span></span>
- <span data-ttu-id="9bebe-170">Führen Sie [eine zusätzliche Einrichtung](set-up-topic-experiences.md) von Viva Topics durch.</span><span class="sxs-lookup"><span data-stu-id="9bebe-170">Perform [additional setup](set-up-topic-experiences.md) of Viva Topics.</span></span>

<span data-ttu-id="9bebe-171">Wenn die Testversion aktiviert ist, beginnt der Themenermittlungsprozess.</span><span class="sxs-lookup"><span data-stu-id="9bebe-171">When the trial is activated, the topic discovery process begins.</span></span>

## <a name="during-a-trial"></a><span data-ttu-id="9bebe-172">Während einer Testversion</span><span class="sxs-lookup"><span data-stu-id="9bebe-172">During a trial</span></span>

<span data-ttu-id="9bebe-173">Der Testzeitraum sollte verwendet werden, um die folgenden Komponenten von Viva Topics zu bewerten:</span><span class="sxs-lookup"><span data-stu-id="9bebe-173">The trial period should be used to evaluate the following components of Viva Topics:</span></span>

- <span data-ttu-id="9bebe-174">Die ki-vorgeschlagenen Themen und Themeninhalte</span><span class="sxs-lookup"><span data-stu-id="9bebe-174">The AI-suggested topics and topic content</span></span>
- <span data-ttu-id="9bebe-175">Die Endbenutzeroberflächen, das Anzeigen von Themenkarten auf modernen SharePoint Seiten und in Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="9bebe-175">The end-user experiences, surfacing topic cards on modern SharePoint pages and in Microsoft Search</span></span>

<span data-ttu-id="9bebe-176">Die folgenden Faktoren sollten Sie in Ihrem Plan berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="9bebe-176">Consider these factors:</span></span>

- <span data-ttu-id="9bebe-177">Damit Viva Topics den maximalen Wert liefern kann, müssen die Inhalte in Themen eine Kombination aus ki-definierten Inhalten und von Menschen zusammengestellten Inhalten sein.</span><span class="sxs-lookup"><span data-stu-id="9bebe-177">For Viva Topics to deliver the maximum value, the content in topics needs to be a combination of AI-defined content and human-curated content.</span></span>
- <span data-ttu-id="9bebe-178">Alle Benutzeroberflächen sind "Berechtigungskürzung" (einschließlich der Ansicht des Wissensmanagers auf der Seite **"Themen verwalten").**</span><span class="sxs-lookup"><span data-stu-id="9bebe-178">All user experiences are “permission trimmed” (including the knowledge manager’s view on the **Manage topics** page).</span></span> <span data-ttu-id="9bebe-179">Benutzer sehen ein Thema nur, wenn sie über Berechtigungen zum Anzeigen einiger Ressourcen verfügen, die zum Generieren des Themas verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="9bebe-179">Users will only see a topic if they have permissions to view some of the resources that were used to generate the topic.</span></span> <span data-ttu-id="9bebe-180">Dies bedeutet, dass verschiedene Benutzer möglicherweise unterschiedliche Inhalte auf derselben Themenseite sehen.</span><span class="sxs-lookup"><span data-stu-id="9bebe-180">This means that different users might see different content on the same topic page.</span></span>
- <span data-ttu-id="9bebe-181">Benutzern werden möglicherweise auf der Seite **"Themen verwalten"** mehrere Themen mit demselben Namen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9bebe-181">Users might see multiple topics that have the same name in the **Manage topics** page.</span></span> <span data-ttu-id="9bebe-182">Diese Themen sind nicht notwendigerweise Duplikate, sondern können auf einen einzelnen Begriff zurückzuführen sein, der in mehreren Kontexten in den Daten verwendet wird, z. B. einem Projektcodenamen, der von zwei unterschiedlichen Projekten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9bebe-182">These topics aren't necessarily duplicates but might be because of a single term that’s used in multiple contexts in the data, such as a project code name that’s used by two distinct projects.</span></span>

## <a name="after-a-trial"></a><span data-ttu-id="9bebe-183">Nach einer Testversion</span><span class="sxs-lookup"><span data-stu-id="9bebe-183">After a trial</span></span>

<span data-ttu-id="9bebe-184">Basierend auf dem Ergebnis der Testversion können Sie entscheiden, ob Sie mit der Produktionsverwendung von Viva Topics fortfahren möchten.</span><span class="sxs-lookup"><span data-stu-id="9bebe-184">Based on the outcome of the trial, you can decide whether to proceed to production use of Viva Topics.</span></span>

### <a name="proceed-to-production-use"></a><span data-ttu-id="9bebe-185">Fahren Sie mit der Produktionsverwendung fort</span><span class="sxs-lookup"><span data-stu-id="9bebe-185">Proceed to production use</span></span>

<span data-ttu-id="9bebe-186">Um die Kontinuität des Dienstes sicherzustellen, müssen Sie die erforderliche Anzahl von Lizenzen erwerben und diese Lizenzen Benutzern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="9bebe-186">To ensure continuity of service, you must purchase the required number of licenses and assign those licenses to users.</span></span> <span data-ttu-id="9bebe-187">Testbenutzer, die am Ende des Testzeitraums keine Volllizenz haben, können nicht auf Viva Topics-Erfahrungen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9bebe-187">Trial users who don’t have a full license at the end of the trial period won’t be able to access any Viva Topics experiences.</span></span>

### <a name="dont-proceed-to-production-use"></a><span data-ttu-id="9bebe-188">Fahren Sie nicht mit der Produktionsverwendung fort</span><span class="sxs-lookup"><span data-stu-id="9bebe-188">Don’t proceed to production use</span></span>

<span data-ttu-id="9bebe-189">Wenn Sie nach der Testversion keine Lizenzen erwerben:</span><span class="sxs-lookup"><span data-stu-id="9bebe-189">If you don’t purchase licenses following the trial:</span></span>

- <span data-ttu-id="9bebe-190">Die Themensuche wird beendet.</span><span class="sxs-lookup"><span data-stu-id="9bebe-190">Topic discovery will stop.</span></span>
- <span data-ttu-id="9bebe-191">Benutzer sehen keine Themenhighlights oder Karten mehr.</span><span class="sxs-lookup"><span data-stu-id="9bebe-191">Users will no longer see topic highlights or cards.</span></span>
- <span data-ttu-id="9bebe-192">Das Themencenter wird nicht gelöscht, aber die vorgeschlagenen Themen und die Themenverwaltung sind nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9bebe-192">The topic center won’t be deleted, but the suggested topics and manage topics experiences won’t be available.</span></span>
- <span data-ttu-id="9bebe-193">Alle ki-definierten Themen sind verloren.</span><span class="sxs-lookup"><span data-stu-id="9bebe-193">Any AI-defined topics will be lost.</span></span>
- <span data-ttu-id="9bebe-194">Themen, die von einem Themenmitwirkenden bearbeitet wurden, verbleiben in der Bibliothek für Themencenterseiten.</span><span class="sxs-lookup"><span data-stu-id="9bebe-194">Topics that have been edited by a topic contributor will remain in the topic center pages library.</span></span> <span data-ttu-id="9bebe-195">Nur der manuell bereitgestellte Inhalt verbleibt auf diesen Seiten, nicht auf ki-vorgeschlagenen Inhalten.</span><span class="sxs-lookup"><span data-stu-id="9bebe-195">Only the manually provided content will remain on these pages, not any AI-suggested content.</span></span>

## <a name="see-also"></a><span data-ttu-id="9bebe-196">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9bebe-196">See also</span></span>

[<span data-ttu-id="9bebe-197">Erste Schritte zur Einführung von Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="9bebe-197">Get started driving adoption of Microsoft Viva Topics</span></span>](topics-adoption-getstarted.md)

