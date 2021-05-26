---
title: Microsoft Defender for Identity-Sicherheitswarnungen in Microsoft 365 Defender
description: Informationen zum Verwalten und Überprüfen von Sicherheitswarnungen von Microsoft Defender for Identity in Microsoft 365 Defender
ms.date: 05/20/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
manager: raynew
ms.openlocfilehash: 0c48c9076d05cd352229477acc28b32185eef54f
ms.sourcegitcommit: 4f6ef4cd09c3ed36dc0be3702b0636bad6cff8a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/26/2021
ms.locfileid: "52657851"
---
# <a name="defender-for-identity-security-alerts-in-microsoft-365-defender"></a><span data-ttu-id="ef99c-103">Sicherheitswarnungen für Defender for Identity in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ef99c-103">Defender for Identity security alerts in Microsoft 365 Defender</span></span>

<span data-ttu-id="ef99c-104">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="ef99c-104">**Applies to:**</span></span>

- <span data-ttu-id="ef99c-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ef99c-105">Microsoft 365 Defender</span></span>
- <span data-ttu-id="ef99c-106">Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="ef99c-106">Defender for Identity</span></span>

<span data-ttu-id="ef99c-107">In diesem Artikel werden die Grundlagen der Verwendung von [Microsoft Defender for Identity-Sicherheitswarnungen](/defender-for-identity) im Microsoft 365 [erläutert.](/microsoft-365/security/defender/overview-security-center)</span><span class="sxs-lookup"><span data-stu-id="ef99c-107">This article explains the basics of how to work with [Microsoft Defender for Identity](/defender-for-identity) security alerts in the [Microsoft 365 security center](/microsoft-365/security/defender/overview-security-center).</span></span>

<span data-ttu-id="ef99c-108">Defender for Identity-Warnungen werden nativ in das [Microsoft 365 Security Center](https://security.microsoft.com) mit einem dedizierten Format der Identitätsbenachrichtigungsseite integriert.</span><span class="sxs-lookup"><span data-stu-id="ef99c-108">Defender for Identity alerts are natively integrated into the [Microsoft 365 security center](https://security.microsoft.com) with a dedicated Identity alert page format.</span></span> <span data-ttu-id="ef99c-109">Dies ist der erste Schritt auf dem Weg zur Einführung der vollständigen [Microsoft Defender for Identity-Erfahrung in Microsoft 365 Defender](/defender-for-identity/defender-for-identity-in-microsoft-365-defender).</span><span class="sxs-lookup"><span data-stu-id="ef99c-109">This marks the first step in the journey to [introduce the full Microsoft Defender for Identity experience into Microsoft 365 Defender](/defender-for-identity/defender-for-identity-in-microsoft-365-defender).</span></span>

<span data-ttu-id="ef99c-110">Die neue Seite für Identitätsbenachrichtigungen bietet Microsoft Defender for Identity-Kunden eine bessere domänenübergreifende Signalerweiterung und neue automatisierte Funktionen zur Identitätsantwort.</span><span class="sxs-lookup"><span data-stu-id="ef99c-110">The new Identity alert page gives Microsoft Defender for Identity customers better cross-domain signal enrichment and new automated identity response capabilities.</span></span> <span data-ttu-id="ef99c-111">Dadurch wird sichergestellt, dass Sie sicher bleiben und die Effizienz Ihrer Sicherheitsvorgänge verbessern.</span><span class="sxs-lookup"><span data-stu-id="ef99c-111">It ensures that you stay secure and helps improve the efficiency of your security operations.</span></span>

<span data-ttu-id="ef99c-112">Einer der Vorteile der Untersuchung von Warnungen über [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender) ist, dass Microsoft Defender for Identity-Warnungen weiter mit den Informationen korreliert werden, die von jedem der anderen Produkte in der Suite erhalten wurden.</span><span class="sxs-lookup"><span data-stu-id="ef99c-112">One of the benefits of investigating alerts through [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender) is that Microsoft Defender for Identity alerts are further correlated with information obtained from each of the other products in the suite.</span></span> <span data-ttu-id="ef99c-113">Diese erweiterten Warnungen sind mit den anderen Microsoft 365 Defender-Warnungsformaten konsistent, die von [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security) und Microsoft Defender for Endpoint [stammen.](/microsoft-365/security/defender-endpoint)</span><span class="sxs-lookup"><span data-stu-id="ef99c-113">These enhanced alerts are consistent with the other Microsoft 365 Defender alert formats originating from [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security) and [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).</span></span> <span data-ttu-id="ef99c-114">Die neue Seite entfällt effektiv die Notwendigkeit, zu einem anderen Produktportal zu navigieren, um Warnungen im Zusammenhang mit der Identität zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="ef99c-114">The new page effectively eliminates the need to navigate to another product portal to investigate alerts associated with identity.</span></span>

<span data-ttu-id="ef99c-115">Warnungen, die von Defender for Identity stammen, können nun die automatisierten Untersuchungs- und Reaktionsfunktionen [von Microsoft 365 Defender auslösen,](/microsoft-365/security/defender/m365d-autoir) einschließlich der automatischen Behebung von Warnungen und der Minderung von Tools und Prozessen, die zur verdächtigen Aktivität beitragen können.</span><span class="sxs-lookup"><span data-stu-id="ef99c-115">Alerts originating from Defender for Identity can now trigger the [Microsoft 365 Defender automated investigation and response (AIR)](/microsoft-365/security/defender/m365d-autoir) capabilities, including automatically remediating alerts and the mitigation of tools and processes that can contribute to the suspicious activity.</span></span>

>[!IMPORTANT]
><span data-ttu-id="ef99c-116">Im Rahmen der Konvergenz mit Microsoft 365 Defender haben sich einige Optionen und Details von ihrem Speicherort im Defender for Identity-Portal geändert.</span><span class="sxs-lookup"><span data-stu-id="ef99c-116">As part of the convergence with Microsoft 365 Defender, some options and details have changed from their location in the Defender for Identity portal.</span></span> <span data-ttu-id="ef99c-117">Lesen Sie die folgenden Details, um herauszufinden, wo Sie sowohl die vertrauten als auch die neuen Features finden können.</span><span class="sxs-lookup"><span data-stu-id="ef99c-117">Please read the details below to discover where to find both the familiar and new features.</span></span>

## <a name="review-security-alerts"></a><span data-ttu-id="ef99c-118">Überprüfen von Sicherheitswarnungen</span><span class="sxs-lookup"><span data-stu-id="ef99c-118">Review security alerts</span></span>

<span data-ttu-id="ef99c-119">Der Zugriff auf Warnungen kann  von mehreren  Speicherorten aus möglich sein, einschließlich der Seite Warnungen, der Seite Vorfälle, der Seiten einzelner Geräte und der Seite Erweiterte **Suche.**</span><span class="sxs-lookup"><span data-stu-id="ef99c-119">Alerts can be accessed from multiple locations, including the **Alerts** page, the **Incidents** page, the pages of individual **Devices**, and from the **Advanced hunting** page.</span></span> <span data-ttu-id="ef99c-120">In diesem Beispiel wird die Seite "Warnungen" **überprüft.**</span><span class="sxs-lookup"><span data-stu-id="ef99c-120">In this example, we'll review the **Alerts page**.</span></span>  

<span data-ttu-id="ef99c-121">Wechseln Sie [Microsoft 365 Sicherheitscenter](https://security.microsoft.com/)zu Vorfälle **&** Warnungen und dann zu **Warnungen**.</span><span class="sxs-lookup"><span data-stu-id="ef99c-121">In the [Microsoft 365 security center](https://security.microsoft.com/), go to **Incidents & alerts** and then to **Alerts**.</span></span>

![Wechseln Sie zu Vorfälle und Warnungen und dann zu Warnungen](../../media/defender-identity/incidents-alerts.png)

<span data-ttu-id="ef99c-123">Um Warnungen von Defender for Identity anzuzeigen, wählen Sie oben rechts **Filter** aus, und wählen Sie dann unter **Dienstquellen** **Microsoft Defender for Identity** aus, und wählen Sie **Übernehmen** aus:</span><span class="sxs-lookup"><span data-stu-id="ef99c-123">To see alerts from Defender for Identity, on the top-right select **Filter**, and then under **Service sources** select **Microsoft Defender for Identity**, and select **Apply**:</span></span>

![Filtern nach Defender for Identity-Ereignissen](../../media/defender-identity/filter-defender-for-identity.png)

<span data-ttu-id="ef99c-125">Die Warnungen werden mit Informationen in den folgenden Spalten **angezeigt:** Warnungsname , **Tags** **,** Schweregrad **,** Untersuchungsstatus , **Status**, **Kategorie**, **Erkennungsquelle** **,** Auswirkungsressourcen , **Erste** Aktivität und **Letzte Aktivität**.</span><span class="sxs-lookup"><span data-stu-id="ef99c-125">The alerts are displayed with information in the following columns: **Alert name**, **Tags**, **Severity**, **Investigation state**, **Status**, **Category**, **Detection source**, **Impacted assets**, **First activity**, and **Last activity**.</span></span>

![Defender for Identity-Ereignisse](../../media/defender-identity/filtered-alerts.png)

## <a name="manage-alerts"></a><span data-ttu-id="ef99c-127">Verwalten von Warnungen</span><span class="sxs-lookup"><span data-stu-id="ef99c-127">Manage alerts</span></span>

<span data-ttu-id="ef99c-128">Wenn Sie auf den **Warnungsnamen** für eine der Warnungen klicken, wechseln Sie zur Seite mit Details zur Warnung.</span><span class="sxs-lookup"><span data-stu-id="ef99c-128">If you click the **Alert name** for one of the alerts, you'll go to the page with details about the alert.</span></span> <span data-ttu-id="ef99c-129">Im linken Bereich sehen Sie eine Zusammenfassung von **Was passiert ist:**</span><span class="sxs-lookup"><span data-stu-id="ef99c-129">In the left pane, you'll see a summary of **What happened**:</span></span>

![Was in der Warnung passiert ist](../../media/defender-identity/what-happened.png)

<span data-ttu-id="ef99c-131">Über dem **Feld Was passiert** ist, befinden sich Schaltflächen für die **Konten,** **den Zielhost** und den **Quellhost** der Warnung.</span><span class="sxs-lookup"><span data-stu-id="ef99c-131">Above the **What happened** box are buttons for the **Accounts**, **Destination Host** and **Source Host** of the alert.</span></span> <span data-ttu-id="ef99c-132">Für andere Warnungen werden möglicherweise Schaltflächen für Details zu zusätzlichen Hosts, Konten, IP-Adressen, Domänen und Sicherheitsgruppen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ef99c-132">For other alerts, you might see buttons for details about additional hosts, accounts, IP addresses, domains, and security groups.</span></span> <span data-ttu-id="ef99c-133">Wählen Sie einen dieser Elemente aus, um weitere Details zu den beteiligten Entitäten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ef99c-133">Select any of them to get more details about the entities involved.</span></span>

<span data-ttu-id="ef99c-134">Im rechten Bereich werden die **Warnungsdetails angezeigt.**</span><span class="sxs-lookup"><span data-stu-id="ef99c-134">On the right pane, you'll see the **Alert details**.</span></span> <span data-ttu-id="ef99c-135">Hier können Sie weitere Details anzeigen und verschiedene Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="ef99c-135">Here you can see more details and perform several tasks:</span></span>

- <span data-ttu-id="ef99c-136">**Klassifizieren dieser Warnung** – Hier können Sie diese Warnung als **True- oder** **False-Warnung festlegen.**</span><span class="sxs-lookup"><span data-stu-id="ef99c-136">**Classify this alert** - Here you can designate this alert as a **True alert** or **False alert**</span></span>

    ![Klassifizieren von Warnungen](../../media/defender-identity/classify-alert.png)

- <span data-ttu-id="ef99c-138">**Warnungsstatus** : Unter **Klassifizierung festlegen** können Sie die Warnung als **True oder** **False klassifizieren.**</span><span class="sxs-lookup"><span data-stu-id="ef99c-138">**Alert state** - In **Set Classification**, you can classify the alert as **True** or **False**.</span></span> <span data-ttu-id="ef99c-139">In **Assigned to** können Sie die Warnung sich selbst zuweisen oder sie nicht mehr zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ef99c-139">In **Assigned to**, you can assign the alert to yourself or unassign it.</span></span>

    ![Warnungsstatus](../../media/defender-identity/alert-state.png)

- <span data-ttu-id="ef99c-141"> Warnungsdetails: Unter Warnungsdetails finden Sie weitere Informationen zu der spezifischen Warnung, folgen Sie einem Link zur Dokumentation zum Typ der Warnung, sehen Sie, welchem Vorfall die Warnung zugeordnet ist, überprüfen Sie alle automatisierten Untersuchungen, die mit diesem Warnungstyp verknüpft sind, und sehen Sie sich die betroffenen Geräte und Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="ef99c-141">**Alert details** - Under **Alert details**, you can find more information about the specific alert, follow a link to documentation about the type of alert, see which incident the alert is associated with, review any automated investigations linked to this alert type, and see the impacted devices and users.</span></span>

    ![Warnungsdetails](../../media/defender-identity/alert-details.png)

- <span data-ttu-id="ef99c-143">**Kommentare & -** Hier können Sie Ihre Kommentare zur Warnung hinzufügen und den Verlauf aller Aktionen im Zusammenhang mit der Warnung sehen.</span><span class="sxs-lookup"><span data-stu-id="ef99c-143">**Comments & history** - Here you can add your comments to the alert, and see the history of all actions associated with the alert.</span></span>

    ![Kommentare und Verlauf](../../media/defender-identity/comments-history.png)

- <span data-ttu-id="ef99c-145">**Warnung verwalten** : Wenn Sie Warnung **verwalten** auswählen, wechseln Sie zu einem Bereich, in dem Sie die:</span><span class="sxs-lookup"><span data-stu-id="ef99c-145">**Manage alert** - If you select **Manage alert**, you'll go to a pane that will allow you to edit the:</span></span>
  - <span data-ttu-id="ef99c-146">**Status** : Sie können **Neu,** **Aufgelöst** oder **In Bearbeitung auswählen.**</span><span class="sxs-lookup"><span data-stu-id="ef99c-146">**Status** - You can choose **New**, **Resolved** or **In progress**.</span></span>
  - <span data-ttu-id="ef99c-147">**Klassifizierung** : Sie können True **alert oder** False **alert auswählen.**</span><span class="sxs-lookup"><span data-stu-id="ef99c-147">**Classification** - You can choose **True alert** or **False alert**.</span></span>
  - <span data-ttu-id="ef99c-148">**Kommentar** : Sie können einen Kommentar zu der Warnung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ef99c-148">**Comment** - You can add a comment about the alert.</span></span>

    <span data-ttu-id="ef99c-149">Wenn Sie die drei Punkte neben Warnung verwalten **auswählen,**  können Sie einen Bedrohungsexperten **konsultieren,** die Warnung in eine Excel exportieren oder mit einem anderen Vorfall **verknüpfen**.</span><span class="sxs-lookup"><span data-stu-id="ef99c-149">If you select the three dots next to **Manage alert**, you can **Consult a threat expert**, **Export** the alert to an Excel file, or **Link to another incident**.</span></span>

    ![Verwalten von Warnungen](../../media/defender-identity/manage-alert.png)

    >[!NOTE]
    ><span data-ttu-id="ef99c-151">In der Excel haben Sie nun zwei Links verfügbar: **Anzeigen in Microsoft Defender for Identity** und View in Microsoft 365 **Defender**.</span><span class="sxs-lookup"><span data-stu-id="ef99c-151">In the Excel file, you now have two links available: **View in Microsoft Defender for Identity** and **View in Microsoft 365 Defender**.</span></span> <span data-ttu-id="ef99c-152">Jeder Link bringt Sie zum entsprechenden Portal und stellt Dort Informationen zur Warnung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ef99c-152">Each link will bring you to the relevant portal, and provide information about the alert there.</span></span>

## <a name="see-also"></a><span data-ttu-id="ef99c-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef99c-153">See also</span></span>

- [<span data-ttu-id="ef99c-154">Untersuchen von Warnungen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ef99c-154">Investigate alerts in Microsoft 365 Defender</span></span>](../defender/investigate-alerts.md)
