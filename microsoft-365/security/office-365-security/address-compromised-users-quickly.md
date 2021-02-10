---
title: Reagieren auf gefährdete Benutzerkonten mit automatischer Untersuchung und Reaktion
keywords: AIR, AutoIR, ATP, automatisiert, Untersuchung, Reaktion, Korrektur, Bedrohungen, fortgeschritten, Bedrohung, Schutz, kompromittiert
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/25/2020
description: Erfahren Sie, wie Sie den Prozess der Erkennung und Behandlung von gefährdeten Benutzerkonten mit automatisierten Untersuchungs- und Reaktionsfunktionen in Microsoft Defender für Office 365 Plan 2 beschleunigen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2159ab7ad7e13c4cd4c2c428317ee7d99f78158c
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/10/2021
ms.locfileid: "50176063"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a><span data-ttu-id="84478-104">Reagieren auf gefährdete Benutzerkonten mit automatischer Untersuchung und Reaktion</span><span class="sxs-lookup"><span data-stu-id="84478-104">Address compromised user accounts with automated investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="84478-105">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="84478-105">**Applies to**</span></span>
- [<span data-ttu-id="84478-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="84478-106">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="84478-107">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="84478-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="84478-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="84478-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="84478-109">[Microsoft Defender für Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) umfasst leistungsstarke funktionen für [automatisierte Untersuchung](office-365-air.md) und Reaktion (AIR).</span><span class="sxs-lookup"><span data-stu-id="84478-109">[Microsoft Defender for Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) includes powerful [automated investigation and response](office-365-air.md) (AIR) capabilities.</span></span> <span data-ttu-id="84478-110">Solche Funktionen können Ihrem Sicherheitsteam viel Zeit und Mühe beim Umgang mit Bedrohungen sparen.</span><span class="sxs-lookup"><span data-stu-id="84478-110">Such capabilities can save your security operations team a lot of time and effort dealing with threats.</span></span> <span data-ttu-id="84478-111">Microsoft verbessert weiterhin die Sicherheitsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="84478-111">Microsoft continues to improve security capabilities.</span></span> <span data-ttu-id="84478-112">Kürzlich wurden die Funktionen von AIR um ein gefährdetes Benutzersicherheits-Playbook erweitert (derzeit in der Vorschau).</span><span class="sxs-lookup"><span data-stu-id="84478-112">Recently, AIR capabilities were enhanced to include a compromised user security playbook (currently in preview).</span></span> <span data-ttu-id="84478-113">Lesen Sie diesen Artikel, um mehr über das Playbook für die Sicherheit gefährdeter Benutzer zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="84478-113">Read this article to learn more about the compromised user security playbook.</span></span> <span data-ttu-id="84478-114">Weitere Details finden Sie im Blogbeitrag "Beschleunigen der Zeit zum Erkennen und Reagieren auf Benutzerverstöße und Zum Einschränken des Umfangs von Sicherheitsverletzungen mit [Microsoft Defender für Office 365".](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053)</span><span class="sxs-lookup"><span data-stu-id="84478-114">And see the blog post [Speed up time to detect and respond to user compromise and limit breach scope with Microsoft Defender for Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) for additional details.</span></span>

![Automatische Untersuchung eines gefährdeten Benutzers](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

<span data-ttu-id="84478-116">Das Sicherheits-Playbook für gefährdete Benutzer ermöglicht dem Sicherheitsteam Ihrer Organisation:</span><span class="sxs-lookup"><span data-stu-id="84478-116">The compromised user security playbook enables your organization's security team to:</span></span>

- <span data-ttu-id="84478-117">Beschleunigen der Erkennung von gefährdeten Benutzerkonten;</span><span class="sxs-lookup"><span data-stu-id="84478-117">Speed up detection of compromised user accounts;</span></span>

- <span data-ttu-id="84478-118">Einschränken des Umfangs einer Verletzung, wenn ein Konto gefährdet ist; und</span><span class="sxs-lookup"><span data-stu-id="84478-118">Limit the scope of a breach when an account is compromised; and</span></span>

- <span data-ttu-id="84478-119">Reagieren Sie effektiver und effizienter auf gefährdete Benutzer.</span><span class="sxs-lookup"><span data-stu-id="84478-119">Respond to compromised users more effectively and efficiently.</span></span>

## <a name="compromised-user-alerts"></a><span data-ttu-id="84478-120">Warnungen von gefährdeten Benutzern</span><span class="sxs-lookup"><span data-stu-id="84478-120">Compromised user alerts</span></span>

<span data-ttu-id="84478-121">Wenn ein Benutzerkonto gefährdet ist, treten atypische oder anomale Verhaltensweisen auf.</span><span class="sxs-lookup"><span data-stu-id="84478-121">When a user account is compromised, atypical or anomalous behaviors occur.</span></span> <span data-ttu-id="84478-122">Beispielsweise können Phishing- und Spamnachrichten intern von einem vertrauenswürdigen Benutzerkonto gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="84478-122">For example, phishing and spam messages might be sent internally from a trusted user account.</span></span> <span data-ttu-id="84478-123">Defender für Office 365 kann solche Anomalien in E-Mail-Mustern und Aktivitäten zur Zusammenarbeit in Office 365 erkennen.</span><span class="sxs-lookup"><span data-stu-id="84478-123">Defender for Office 365 can detect such anomalies in email patterns and collaboration activity within Office 365.</span></span> <span data-ttu-id="84478-124">Wenn dies geschieht, werden Warnungen ausgelöst, und der Prozess zur Risikominderung beginnt.</span><span class="sxs-lookup"><span data-stu-id="84478-124">When this happens, alerts are triggered, and the threat mitigation process begins.</span></span>

<span data-ttu-id="84478-125">Hier ist beispielsweise eine Warnung, die aufgrund verdächtigen Sendens von E-Mails ausgelöst wurde:</span><span class="sxs-lookup"><span data-stu-id="84478-125">For example, here's an alert that was triggered because of suspicious email sending:</span></span>

![Warnung aufgrund verdächtigen Sendens von E-Mails ausgelöst](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

<span data-ttu-id="84478-127">Hier ist ein Beispiel für eine Warnung, die ausgelöst wurde, wenn ein Sendegrenzwert für einen Benutzer erreicht wurde:</span><span class="sxs-lookup"><span data-stu-id="84478-127">And here's an example of an alert that was triggered when a sending limit was reached for a user:</span></span>

![Warnung ausgelöst durch Erreichen des Sendegrenzwerts](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a><span data-ttu-id="84478-129">Untersuchen und Reagieren auf einen gefährdeten Benutzer</span><span class="sxs-lookup"><span data-stu-id="84478-129">Investigate and respond to a compromised user</span></span>

<span data-ttu-id="84478-130">Wenn ein Benutzerkonto gefährdet ist, werden Warnungen ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="84478-130">When a user account is compromised, alerts are triggered.</span></span> <span data-ttu-id="84478-131">Und in einigen Fällen wird dieses Benutzerkonto blockiert und daran gehindert, weitere E-Mail-Nachrichten zu senden, bis das Problem vom Sicherheitsteam Ihrer Organisation behoben wurde.</span><span class="sxs-lookup"><span data-stu-id="84478-131">And in some cases, that user account is blocked and prevented from sending any further email messages until the issue is resolved by your organization's security operations team.</span></span> <span data-ttu-id="84478-132">In anderen Fällen beginnt eine automatisierte Untersuchung, die zu empfohlenen Maßnahmen führen kann, die Ihr Sicherheitsteam ergreifen sollte.</span><span class="sxs-lookup"><span data-stu-id="84478-132">In other cases, an automated investigation begins which can result in recommended actions that your security team should take.</span></span>

- [<span data-ttu-id="84478-133">Anzeigen und Untersuchen eingeschränkter Benutzer</span><span class="sxs-lookup"><span data-stu-id="84478-133">View and investigate restricted users</span></span>](#view-and-investigate-restricted-users)

- [<span data-ttu-id="84478-134">Anzeigen von Details zu automatisierten Untersuchungen</span><span class="sxs-lookup"><span data-stu-id="84478-134">View details about automated investigations</span></span>](#view-details-about-automated-investigations)

> [!IMPORTANT]
> <span data-ttu-id="84478-135">Sie müssen über die entsprechenden Berechtigungen zum Ausführen der folgenden Aufgaben verfügen.</span><span class="sxs-lookup"><span data-stu-id="84478-135">You must have appropriate permissions to perform the following tasks.</span></span> <span data-ttu-id="84478-136">Siehe ["Erforderliche Berechtigungen zum Verwenden von AIR-Funktionen".](office-365-air.md#required-permissions-to-use-air-capabilities)</span><span class="sxs-lookup"><span data-stu-id="84478-136">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

### <a name="view-and-investigate-restricted-users"></a><span data-ttu-id="84478-137">Anzeigen und Untersuchen eingeschränkter Benutzer</span><span class="sxs-lookup"><span data-stu-id="84478-137">View and investigate restricted users</span></span>

<span data-ttu-id="84478-138">Sie haben einige Optionen, um zu einer Liste eingeschränkter Benutzer zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="84478-138">You have a few options for navigating to a list of restricted users.</span></span> <span data-ttu-id="84478-139">Beispielsweise können Sie im Security & Compliance Center zu  "Bedrohungsverwaltung Überprüfen \>  \> **eingeschränkter Benutzer" wechseln.**</span><span class="sxs-lookup"><span data-stu-id="84478-139">For example, in the Security & Compliance Center, you can go to **Threat management** \> **Review** \> **Restricted Users**.</span></span> <span data-ttu-id="84478-140">Im folgenden Verfahren wird die Navigation mithilfe **des** Benachrichtigungsdashboards beschrieben. Dies ist eine gute Möglichkeit, verschiedene Arten von Warnungen anzuzeigen, die möglicherweise ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="84478-140">The following procedure describes navigation using the **Alerts** dashboard, which is a good way to see various kinds of alerts that might have been triggered.</span></span>

1. <span data-ttu-id="84478-141">Gehen Sie auf <https://protection.office.com>, und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="84478-141">Go to <https://protection.office.com> and sign in.</span></span>

2. <span data-ttu-id="84478-142">Wählen Sie im Navigationsbereich **"Warnungsdashboard"** \> **aus.**</span><span class="sxs-lookup"><span data-stu-id="84478-142">In the navigation pane, choose **Alerts** \> **Dashboard**.</span></span>

3. <span data-ttu-id="84478-143">Wählen Sie **im Widget "Andere Warnungen"** die Option **"Eingeschränkte Benutzer" aus.**</span><span class="sxs-lookup"><span data-stu-id="84478-143">In the **Other alerts** widget, choose **Restricted Users**.</span></span>

   ![Widget für andere Warnungen](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   <span data-ttu-id="84478-145">Dadurch wird die Liste der eingeschränkten Benutzer geöffnet.</span><span class="sxs-lookup"><span data-stu-id="84478-145">This opens the list of restricted users.</span></span>

   ![Eingeschränkte Benutzer in Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. <span data-ttu-id="84478-147">Wählen Sie ein Benutzerkonto in der Liste aus, um Details anzuzeigen und Maßnahmen zu ergreifen, z. B. [freigeben des eingeschränkten Benutzers.](removing-user-from-restricted-users-portal-after-spam.md)</span><span class="sxs-lookup"><span data-stu-id="84478-147">Select a user account in the list to view details and take action, such as [releasing the restricted user](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="view-details-about-automated-investigations"></a><span data-ttu-id="84478-148">Anzeigen von Details zu automatisierten Untersuchungen</span><span class="sxs-lookup"><span data-stu-id="84478-148">View details about automated investigations</span></span>

<span data-ttu-id="84478-149">Wenn eine automatisierte Untersuchung begonnen hat, können Sie ihre Details und Ergebnisse im Security & Compliance Center anzeigen.</span><span class="sxs-lookup"><span data-stu-id="84478-149">When an automated investigation has begun, you can see its details and results in the Security & Compliance Center.</span></span> <span data-ttu-id="84478-150">Wechseln Sie zu **"Threat Management** Investigations", und wählen Sie dann \> eine Untersuchung aus, um deren Details anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="84478-150">Go to **Threat management** \> **Investigations**, and then select an investigation to view its details.</span></span>

<span data-ttu-id="84478-151">Weitere Informationen finden Sie unter [Anzeigen von Details zu einer Untersuchung.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="84478-151">To learn more, see [View details of an investigation](air-view-investigation-results.md).</span></span>

## <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="84478-152">Beachten Sie die folgenden Punkte:</span><span class="sxs-lookup"><span data-stu-id="84478-152">Keep the following points in mind</span></span>

- <span data-ttu-id="84478-153">**Bleiben Sie über Ihre Warnungen auf dem Besten.**</span><span class="sxs-lookup"><span data-stu-id="84478-153">**Stay on top of your alerts**.</span></span> <span data-ttu-id="84478-154">Wie Sie wissen, gilt: Je länger ein Kompromiss unentdeckt bleibt, desto größer ist das Potenzial für weit verbreitete Auswirkungen und Kosten für Ihre Organisation, Ihre Kunden und Partner.</span><span class="sxs-lookup"><span data-stu-id="84478-154">As you know, the longer a compromise goes undetected, the larger the potential for widespread impact and cost to your organization, customers, and partners.</span></span> <span data-ttu-id="84478-155">Eine frühzeitige Erkennung und zeitnahe Reaktion sind entscheidend, um Bedrohungen zu mindern, insbesondere, wenn das Konto eines Benutzers gefährdet ist.</span><span class="sxs-lookup"><span data-stu-id="84478-155">Early detection and timely response are critical to mitigate threats, and especially when a user's account is compromised.</span></span>

- <span data-ttu-id="84478-156">**Die Automatisierung unterstützt Ihr Sicherheitsteam, ersetzt aber nicht.**</span><span class="sxs-lookup"><span data-stu-id="84478-156">**Automation assists, but does not replace, your security operations team**.</span></span> <span data-ttu-id="84478-157">Automatisierte Untersuchungs- und Reaktionsfunktionen können einen gefährdeten Benutzer frühzeitig erkennen, aber Ihr Sicherheitsteam muss sich wahrscheinlich einarbeiten und einige Untersuchungen und Korrekturen unternehmen.</span><span class="sxs-lookup"><span data-stu-id="84478-157">Automated investigation and response capabilities can detect a compromised user early on, but your security operations team will likely need to engage and do some investigation and remediation.</span></span> <span data-ttu-id="84478-158">Benötigen Sie Hilfe dazu?</span><span class="sxs-lookup"><span data-stu-id="84478-158">Need some help with this?</span></span> <span data-ttu-id="84478-159">Siehe Überprüfen [und Genehmigen von Aktionen.](air-review-approve-pending-completed-actions.md)</span><span class="sxs-lookup"><span data-stu-id="84478-159">See [Review and approve actions](air-review-approve-pending-completed-actions.md).</span></span>

- <span data-ttu-id="84478-160">**Verlassen Sie sich nicht auf eine verdächtige Anmeldewarnung als einzigen Indikator.**</span><span class="sxs-lookup"><span data-stu-id="84478-160">**Don't rely on a suspicious login alert as your only indicator**.</span></span> <span data-ttu-id="84478-161">Wenn ein Benutzerkonto gefährdet ist, wird möglicherweise eine verdächtige Anmeldebenachrichtigung ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="84478-161">When a user account is compromised, it might or might not trigger a suspicious login alert.</span></span> <span data-ttu-id="84478-162">Manchmal ist es die Reihe von Aktivitäten, die auftreten, nachdem ein Konto gefährdet wurde, das eine Warnung auslöst.</span><span class="sxs-lookup"><span data-stu-id="84478-162">Sometimes it's the series of activities that occur after an account is compromised that triggers an alert.</span></span> <span data-ttu-id="84478-163">Möchten Sie mehr über Warnungen erfahren?</span><span class="sxs-lookup"><span data-stu-id="84478-163">Want to know more about alerts?</span></span> <span data-ttu-id="84478-164">Siehe [Warnungsrichtlinien](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span><span class="sxs-lookup"><span data-stu-id="84478-164">See [Alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span></span>

## <a name="next-steps"></a><span data-ttu-id="84478-165">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="84478-165">Next steps</span></span>

- [<span data-ttu-id="84478-166">Überprüfen der erforderlichen Berechtigungen für die Verwendung von AIR-Funktionen</span><span class="sxs-lookup"><span data-stu-id="84478-166">Review the required permissions to use AIR capabilities</span></span>](office-365-air.md#required-permissions-to-use-air-capabilities)

- [<span data-ttu-id="84478-167">Suchen und Untersuchen bösartiger E-Mails in Office 365</span><span class="sxs-lookup"><span data-stu-id="84478-167">Find and investigate malicious email in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="84478-168">Informationen zu AIR in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="84478-168">Learn about AIR in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="84478-169">Besuchen Sie die Microsoft 365-Roadmap, um zu sehen, was in Kürze verfügbar ist, und die Roll-out-Website.</span><span class="sxs-lookup"><span data-stu-id="84478-169">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)
