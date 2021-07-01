---
title: Sicherheitswarnungen für Microsoft Defender for Identity in Microsoft 365 Defender
description: Erfahren Sie, wie Sie von Microsoft Defender for Identity ausgegebene Sicherheitswarnungen in Microsoft 365 Defender
ms.date: 05/20/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
manager: raynew
ms.openlocfilehash: c81f14b92b285359bda7e291bd8d3a8b636ae54d
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228963"
---
# <a name="defender-for-identity-security-alerts-in-microsoft-365-defender"></a><span data-ttu-id="96128-103">Sicherheitswarnungen für Defender for Identity in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="96128-103">Defender for Identity security alerts in Microsoft 365 Defender</span></span>

<span data-ttu-id="96128-104">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="96128-104">**Applies to:**</span></span>

- <span data-ttu-id="96128-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="96128-105">Microsoft 365 Defender</span></span>
- <span data-ttu-id="96128-106">Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="96128-106">Defender for Identity</span></span>

<span data-ttu-id="96128-107">In diesem Artikel werden die Grundlagen der Verwendung von Microsoft Defender for Identity-Sicherheitswarnungen im [Microsoft 365 Security Center erläutert.](/microsoft-365/security/defender/overview-security-center) [](/defender-for-identity)</span><span class="sxs-lookup"><span data-stu-id="96128-107">This article explains the basics of how to work with [Microsoft Defender for Identity](/defender-for-identity) security alerts in the [Microsoft 365 security center](/microsoft-365/security/defender/overview-security-center).</span></span>

<span data-ttu-id="96128-108">Defender for Identity-Warnungen sind nativ in das [Microsoft 365 Security Center](https://security.microsoft.com) mit einem dedizierten Identitätswarnungsseitenformat integriert.</span><span class="sxs-lookup"><span data-stu-id="96128-108">Defender for Identity alerts are natively integrated into the [Microsoft 365 security center](https://security.microsoft.com) with a dedicated Identity alert page format.</span></span> <span data-ttu-id="96128-109">Dies ist der erste Schritt auf der Reise, um [die vollständige Microsoft Defender for Identity-Erfahrung in Microsoft 365 Defender einzuführen.](/defender-for-identity/defender-for-identity-in-microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="96128-109">This marks the first step in the journey to [introduce the full Microsoft Defender for Identity experience into Microsoft 365 Defender](/defender-for-identity/defender-for-identity-in-microsoft-365-defender).</span></span>

<span data-ttu-id="96128-110">Die neue Identitätswarnungsseite bietet Microsoft Defender for Identity-Kunden eine bessere domänenübergreifende Signalanreicherung und neue automatisierte Identitätsantwortfunktionen.</span><span class="sxs-lookup"><span data-stu-id="96128-110">The new Identity alert page gives Microsoft Defender for Identity customers better cross-domain signal enrichment and new automated identity response capabilities.</span></span> <span data-ttu-id="96128-111">Es stellt sicher, dass Sie sicher bleiben, und verbessert die Effizienz Ihrer Sicherheitsvorgänge.</span><span class="sxs-lookup"><span data-stu-id="96128-111">It ensures that you stay secure and helps improve the efficiency of your security operations.</span></span>

<span data-ttu-id="96128-112">Einer der Vorteile der Untersuchung von Warnungen über [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender) besteht darin, dass Microsoft Defender for Identity-Warnungen weiter mit Informationen korreliert werden, die von jedem der anderen Produkte in der Suite abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="96128-112">One of the benefits of investigating alerts through [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender) is that Microsoft Defender for Identity alerts are further correlated with information obtained from each of the other products in the suite.</span></span> <span data-ttu-id="96128-113">Diese erweiterten Warnungen stimmen mit den anderen Microsoft 365 Defender Warnungsformaten überein, die von [Microsoft Defender für Office 365](/microsoft-365/security/office-365-security) und Microsoft Defender für [Endpunkt](/microsoft-365/security/defender-endpoint)stammen.</span><span class="sxs-lookup"><span data-stu-id="96128-113">These enhanced alerts are consistent with the other Microsoft 365 Defender alert formats originating from [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security) and [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).</span></span> <span data-ttu-id="96128-114">Auf der neuen Seite entfällt effektiv die Notwendigkeit, zu einem anderen Produktportal zu navigieren, um mit der Identität verknüpfte Warnungen zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="96128-114">The new page effectively eliminates the need to navigate to another product portal to investigate alerts associated with identity.</span></span>

<span data-ttu-id="96128-115">Warnungen, die von Defender for Identity stammen, können jetzt die Microsoft 365 Defender Air-Funktionen [(Automated Investigation and Response, automatische Untersuchung und Reaktion)](/microsoft-365/security/defender/m365d-autoir) auslösen, einschließlich der automatischen Korrektur von Warnungen und der Minderung von Tools und Prozessen, die zu der verdächtigen Aktivität beitragen können.</span><span class="sxs-lookup"><span data-stu-id="96128-115">Alerts originating from Defender for Identity can now trigger the [Microsoft 365 Defender automated investigation and response (AIR)](/microsoft-365/security/defender/m365d-autoir) capabilities, including automatically remediating alerts and the mitigation of tools and processes that can contribute to the suspicious activity.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96128-116">Im Rahmen der Konvergenz mit Microsoft 365 Defender haben sich einige Optionen und Details von ihrem Standort im Defender for Identity-Portal geändert.</span><span class="sxs-lookup"><span data-stu-id="96128-116">As part of the convergence with Microsoft 365 Defender, some options and details have changed from their location in the Defender for Identity portal.</span></span> <span data-ttu-id="96128-117">Lesen Sie die details unten, um herauszufinden, wo Sie die vertrauten und neuen Features finden.</span><span class="sxs-lookup"><span data-stu-id="96128-117">Please read the details below to discover where to find both the familiar and new features.</span></span>

## <a name="review-security-alerts"></a><span data-ttu-id="96128-118">Überprüfen von Sicherheitswarnungen</span><span class="sxs-lookup"><span data-stu-id="96128-118">Review security alerts</span></span>

<span data-ttu-id="96128-119">Auf Warnungen kann von mehreren Standorten aus zugegriffen werden, einschließlich der Seite **"Warnungen",** der Seite **"Vorfälle",** der Seiten der einzelnen **Geräte** und der Seite **"Erweiterte Suche".**</span><span class="sxs-lookup"><span data-stu-id="96128-119">Alerts can be accessed from multiple locations, including the **Alerts** page, the **Incidents** page, the pages of individual **Devices**, and from the **Advanced hunting** page.</span></span> <span data-ttu-id="96128-120">In diesem Beispiel überprüfen wir die **Seite "Warnungen".**</span><span class="sxs-lookup"><span data-stu-id="96128-120">In this example, we'll review the **Alerts page**.</span></span>

<span data-ttu-id="96128-121">Wechseln [Sie](https://security.microsoft.com/)im Microsoft 365 Security Center zu **Vorfällen & Warnungen** und dann zu **Warnungen.**</span><span class="sxs-lookup"><span data-stu-id="96128-121">In the [Microsoft 365 security center](https://security.microsoft.com/), go to **Incidents & alerts** and then to **Alerts**.</span></span>

![Wechseln Sie zu "Vorfälle und Warnungen" und dann zu "Warnungen".](../../media/defender-identity/incidents-alerts.png)

<span data-ttu-id="96128-123">Um Warnungen von Defender for Identity anzuzeigen, wählen Sie oben rechts **"Filter"** aus, und wählen Sie dann unter **"Dienstquellen"** **Microsoft Defender for Identity** aus, und wählen Sie **"Anwenden"** aus:</span><span class="sxs-lookup"><span data-stu-id="96128-123">To see alerts from Defender for Identity, on the top-right select **Filter**, and then under **Service sources** select **Microsoft Defender for Identity**, and select **Apply**:</span></span>

![Filtern nach Defender for Identity-Ereignissen](../../media/defender-identity/filter-defender-for-identity.png)

<span data-ttu-id="96128-125">Die Warnungen werden mit Informationen in den folgenden Spalten angezeigt: **Warnungsname**, **Tags**, Schweregrad , **Untersuchungsstatus**, **Status**, **Kategorie**, **Erkennungsquelle**, **betroffene Ressourcen**, **erste Aktivität** und **letzte Aktivität**. </span><span class="sxs-lookup"><span data-stu-id="96128-125">The alerts are displayed with information in the following columns: **Alert name**, **Tags**, **Severity**, **Investigation state**, **Status**, **Category**, **Detection source**, **Impacted assets**, **First activity**, and **Last activity**.</span></span>

![Defender for Identity-Ereignisse](../../media/defender-identity/filtered-alerts.png)

## <a name="manage-alerts"></a><span data-ttu-id="96128-127">Verwalten von Warnungen</span><span class="sxs-lookup"><span data-stu-id="96128-127">Manage alerts</span></span>

<span data-ttu-id="96128-128">Wenn Sie auf den **Warnungsnamen** für eine der Warnungen klicken, wechseln Sie zur Seite mit Details zur Warnung.</span><span class="sxs-lookup"><span data-stu-id="96128-128">If you click the **Alert name** for one of the alerts, you'll go to the page with details about the alert.</span></span> <span data-ttu-id="96128-129">Im linken Bereich wird eine Zusammenfassung der **Ereignisse angezeigt:**</span><span class="sxs-lookup"><span data-stu-id="96128-129">In the left pane, you'll see a summary of **What happened**:</span></span>

![Was in der Warnung passiert ist](../../media/defender-identity/what-happened.png)

<span data-ttu-id="96128-131">Oberhalb des Felds **"Was ist passiert"** befinden sich Schaltflächen für die **Konten,** den **Zielhost** und den **Quellhost** der Warnung.</span><span class="sxs-lookup"><span data-stu-id="96128-131">Above the **What happened** box are buttons for the **Accounts**, **Destination Host** and **Source Host** of the alert.</span></span> <span data-ttu-id="96128-132">Für andere Warnungen werden möglicherweise Schaltflächen für Details zu zusätzlichen Hosts, Konten, IP-Adressen, Domänen und Sicherheitsgruppen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="96128-132">For other alerts, you might see buttons for details about additional hosts, accounts, IP addresses, domains, and security groups.</span></span> <span data-ttu-id="96128-133">Wählen Sie alle aus, um weitere Details zu den beteiligten Entitäten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="96128-133">Select any of them to get more details about the entities involved.</span></span>

<span data-ttu-id="96128-134">Im rechten Bereich werden die **Warnungsdetails angezeigt.**</span><span class="sxs-lookup"><span data-stu-id="96128-134">On the right pane, you'll see the **Alert details**.</span></span> <span data-ttu-id="96128-135">Hier können Sie weitere Details sehen und verschiedene Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="96128-135">Here you can see more details and perform several tasks:</span></span>

- <span data-ttu-id="96128-136">**Klassifizieren dieser Warnung** – Hier können Sie diese Warnung als **"True"-** oder **"False"-Warnung** festlegen.</span><span class="sxs-lookup"><span data-stu-id="96128-136">**Classify this alert** - Here you can designate this alert as a **True alert** or **False alert**</span></span>

    ![Klassifizieren von Warnungen](../../media/defender-identity/classify-alert.png)

- <span data-ttu-id="96128-138">**Warnungsstatus** : In **"Klassifizierung festlegen"** können Sie die Warnung als **"True"** oder **"False"** klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="96128-138">**Alert state** - In **Set Classification**, you can classify the alert as **True** or **False**.</span></span> <span data-ttu-id="96128-139">In **Zugewiesen** an können Sie die Warnung selbst zuweisen oder die Zuweisung aufheben.</span><span class="sxs-lookup"><span data-stu-id="96128-139">In **Assigned to**, you can assign the alert to yourself or unassign it.</span></span>

    ![Warnungsstatus](../../media/defender-identity/alert-state.png)

- <span data-ttu-id="96128-141">**Warnungsdetails** – Unter **"Warnungsdetails"** finden Sie weitere Informationen zu der spezifischen Warnung, folgen Sie einem Link zur Dokumentation zum Typ der Warnung, sehen Sie sich an, mit welchem Vorfall die Warnung verknüpft ist, überprüfen Sie alle automatisierten Untersuchungen, die mit diesem Warnungstyp verknüpft sind, und sehen Sie sich die betroffenen Geräte und Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="96128-141">**Alert details** - Under **Alert details**, you can find more information about the specific alert, follow a link to documentation about the type of alert, see which incident the alert is associated with, review any automated investigations linked to this alert type, and see the impacted devices and users.</span></span>

    ![Warnungsdetails](../../media/defender-identity/alert-details.png)

- <span data-ttu-id="96128-143">**Kommentare & Verlauf** : Hier können Sie Ihre Kommentare zur Warnung hinzufügen und den Verlauf aller aktionen anzeigen, die der Warnung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="96128-143">**Comments & history** - Here you can add your comments to the alert, and see the history of all actions associated with the alert.</span></span>

    ![Kommentare und Verlauf](../../media/defender-identity/comments-history.png)

- <span data-ttu-id="96128-145">**Warnung verwalten** – Wenn Sie **Warnung verwalten** auswählen, wechseln Sie zu einem Bereich, in dem Sie Folgendes bearbeiten können:</span><span class="sxs-lookup"><span data-stu-id="96128-145">**Manage alert** - If you select **Manage alert**, you'll go to a pane that will allow you to edit the:</span></span>
  - <span data-ttu-id="96128-146">**Status** : Sie können **neu**, **aufgelöst** oder **in Bearbeitung** auswählen.</span><span class="sxs-lookup"><span data-stu-id="96128-146">**Status** - You can choose **New**, **Resolved** or **In progress**.</span></span>
  - <span data-ttu-id="96128-147">**Klassifizierung –** Sie können **"True"-** oder **"False"-Warnung** auswählen.</span><span class="sxs-lookup"><span data-stu-id="96128-147">**Classification** - You can choose **True alert** or **False alert**.</span></span>
  - <span data-ttu-id="96128-148">**Kommentar** : Sie können einen Kommentar zu der Warnung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="96128-148">**Comment** - You can add a comment about the alert.</span></span>

    <span data-ttu-id="96128-149">Wenn Sie die drei Punkte neben **"Warnung verwalten"** auswählen, können Sie **einen Bedrohungsexperten konsultieren,** die Warnung in eine Excel-Datei **exportieren** oder **einen Link zu einem anderen Vorfall erstellen.**</span><span class="sxs-lookup"><span data-stu-id="96128-149">If you select the three dots next to **Manage alert**, you can **Consult a threat expert**, **Export** the alert to an Excel file, or **Link to another incident**.</span></span>

    ![Verwalten von Warnungen](../../media/defender-identity/manage-alert.png)

    > [!NOTE]
    > <span data-ttu-id="96128-151">In der datei Excel stehen nun zwei Links zur Verfügung: **Ansicht in Microsoft Defender for Identity** und Ansicht in **Microsoft 365 Defender**.</span><span class="sxs-lookup"><span data-stu-id="96128-151">In the Excel file, you now have two links available: **View in Microsoft Defender for Identity** and **View in Microsoft 365 Defender**.</span></span> <span data-ttu-id="96128-152">Über jeden Link gelangen Sie zum entsprechenden Portal und geben Dort Informationen zu der Warnung an.</span><span class="sxs-lookup"><span data-stu-id="96128-152">Each link will bring you to the relevant portal, and provide information about the alert there.</span></span>

## <a name="see-also"></a><span data-ttu-id="96128-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96128-153">See also</span></span>

- [<span data-ttu-id="96128-154">Untersuchen von Warnungen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="96128-154">Investigate alerts in Microsoft 365 Defender</span></span>](../defender/investigate-alerts.md)
