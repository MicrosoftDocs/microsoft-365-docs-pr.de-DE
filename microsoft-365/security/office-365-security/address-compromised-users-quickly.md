---
title: Adressieren von kompromittierten Benutzerkonten mit automatisierter Untersuchung und Antwort
keywords: Luft, autoIR, ATP, automatisiert, Untersuchung, Antwort, Behebung, Bedrohungen, erweitert, Bedrohung, Schutz, kompromittiert
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/25/2020
description: Erfahren Sie, wie Sie das erkennen und adressieren von kompromittierten Benutzerkonten mit automatisierten Ermittlungs-und Antwortfunktionen in Microsoft Defender für Office 365 Plan 2 beschleunigen können.
ms.openlocfilehash: 80e4529f864d83d2a1711007f0f095de39955e68
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357911"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a><span data-ttu-id="d7355-104">Adressieren von kompromittierten Benutzerkonten mit automatisierter Untersuchung und Antwort</span><span class="sxs-lookup"><span data-stu-id="d7355-104">Address compromised user accounts with automated investigation and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d7355-105">[Microsoft Defender für Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) enthält leistungsstarke Funktionen für die [Automatische Untersuchung und Reaktion](office-365-air.md) (Air).</span><span class="sxs-lookup"><span data-stu-id="d7355-105">[Microsoft Defender for Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) includes powerful [automated investigation and response](office-365-air.md) (AIR) capabilities.</span></span> <span data-ttu-id="d7355-106">Solche Funktionen können Ihr Sicherheits Betriebsteam viel Zeit und Mühe beim Umgang mit Bedrohungen speichern.</span><span class="sxs-lookup"><span data-stu-id="d7355-106">Such capabilities can save your security operations team a lot of time and effort dealing with threats.</span></span> <span data-ttu-id="d7355-107">Microsoft verbessert weiterhin die Sicherheitsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="d7355-107">Microsoft continues to improve security capabilities.</span></span> <span data-ttu-id="d7355-108">In letzter Zeit wurden die Air-Funktionen erweitert, um ein kompromittiertes Benutzer Sicherheits-Textbuch (derzeit in der Vorschau) einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="d7355-108">Recently, AIR capabilities were enhanced to include a compromised user security playbook (currently in preview).</span></span> <span data-ttu-id="d7355-109">Lesen Sie diesen Artikel, um mehr über das kompromittierte User Security-Manuskript zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="d7355-109">Read this article to learn more about the compromised user security playbook.</span></span> <span data-ttu-id="d7355-110">Und lesen Sie den Blogbeitrag [beschleunigen Zeit zum erkennen und reagieren auf Benutzer Kompromisse und Grenzwerte für Verstöße mit Microsoft Defender für Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) zusätzliche Details.</span><span class="sxs-lookup"><span data-stu-id="d7355-110">And see the blog post [Speed up time to detect and respond to user compromise and limit breach scope with Microsoft Defender for Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) for additional details.</span></span>

![Automatische Untersuchung für einen kompromittierten Benutzer](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

<span data-ttu-id="d7355-112">Das kompromittierte User Security-Manuskript ermöglicht dem Sicherheitsteam Ihrer Organisation Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d7355-112">The compromised user security playbook enables your organization's security team to:</span></span>

- <span data-ttu-id="d7355-113">Schnellere Erkennung kompromittierter Benutzerkonten;</span><span class="sxs-lookup"><span data-stu-id="d7355-113">Speed up detection of compromised user accounts;</span></span>

- <span data-ttu-id="d7355-114">Einschränken des Gültigkeitsbereichs einer Verletzung, wenn ein Konto kompromittiert wird; und</span><span class="sxs-lookup"><span data-stu-id="d7355-114">Limit the scope of a breach when an account is compromised; and</span></span>

- <span data-ttu-id="d7355-115">Effektivere und effizientere Reaktion auf kompromittierte Benutzer.</span><span class="sxs-lookup"><span data-stu-id="d7355-115">Respond to compromised users more effectively and efficiently.</span></span>

## <a name="compromised-user-alerts"></a><span data-ttu-id="d7355-116">Kompromittierte Benutzer Warnungen</span><span class="sxs-lookup"><span data-stu-id="d7355-116">Compromised user alerts</span></span>

<span data-ttu-id="d7355-117">Wenn ein Benutzerkonto kompromittiert wird, treten atypische oder anomale Verhaltensweisen auf.</span><span class="sxs-lookup"><span data-stu-id="d7355-117">When a user account is compromised, atypical or anomalous behaviors occur.</span></span> <span data-ttu-id="d7355-118">Beispielsweise können Phishing-und Spamnachrichten intern von einem vertrauenswürdigen Benutzerkonto gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="d7355-118">For example, phishing and spam messages might be sent internally from a trusted user account.</span></span> <span data-ttu-id="d7355-119">Defender for Office 365 kann solche Anomalien in e-Mail-Mustern und Zusammenarbeitsaktivitäten innerhalb Office 365 erkennen.</span><span class="sxs-lookup"><span data-stu-id="d7355-119">Defender for Office 365 can detect such anomalies in email patterns and collaboration activity within Office 365.</span></span> <span data-ttu-id="d7355-120">In diesem Fall werden Warnungen ausgelöst, und der Prozess zur Bedrohungsminderung wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="d7355-120">When this happens, alerts are triggered, and the threat mitigation process begins.</span></span>

<span data-ttu-id="d7355-121">Hier ist beispielsweise eine Warnung, die aufgrund eines verdächtigen e-Mail-Sendens ausgelöst wurde:</span><span class="sxs-lookup"><span data-stu-id="d7355-121">For example, here's an alert that was triggered because of suspicious email sending:</span></span>

![Warnung aufgrund eines verdächtigen e-Mail-Sendens ausgelöst](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

<span data-ttu-id="d7355-123">Und hier ist ein Beispiel für eine Warnung, die ausgelöst wurde, als ein Sende Grenzwert für einen Benutzer erreicht wurde:</span><span class="sxs-lookup"><span data-stu-id="d7355-123">And here's an example of an alert that was triggered when a sending limit was reached for a user:</span></span>

![Warnung ausgelöst durch Sende Grenzwert erreicht](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a><span data-ttu-id="d7355-125">Untersuchen und reagieren auf einen kompromittierten Benutzer</span><span class="sxs-lookup"><span data-stu-id="d7355-125">Investigate and respond to a compromised user</span></span>

<span data-ttu-id="d7355-126">Wenn ein Benutzerkonto kompromittiert wird, werden Warnungen ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="d7355-126">When a user account is compromised, alerts are triggered.</span></span> <span data-ttu-id="d7355-127">In einigen Fällen wird das Benutzerkonto blockiert und verhindert, dass weitere e-Mail-Nachrichten gesendet werden, bis das Problem vom Security Operations-Team Ihrer Organisation behoben wurde.</span><span class="sxs-lookup"><span data-stu-id="d7355-127">And in some cases, that user account is blocked and prevented from sending any further email messages until the issue is resolved by your organization's security operations team.</span></span> <span data-ttu-id="d7355-128">In anderen Fällen beginnt eine automatisierte Untersuchung, die zu empfohlenen Aktionen führen kann, die das Sicherheitsteam durchführen sollte.</span><span class="sxs-lookup"><span data-stu-id="d7355-128">In other cases, an automated investigation begins which can result in recommended actions that your security team should take.</span></span>

- [<span data-ttu-id="d7355-129">Anzeigen und untersuchen eingeschränkter Benutzer</span><span class="sxs-lookup"><span data-stu-id="d7355-129">View and investigate restricted users</span></span>](#view-and-investigate-restricted-users)

- [<span data-ttu-id="d7355-130">Anzeigen von Details zu automatisierten Untersuchungen</span><span class="sxs-lookup"><span data-stu-id="d7355-130">View details about automated investigations</span></span>](#view-details-about-automated-investigations)

> [!IMPORTANT]
> <span data-ttu-id="d7355-131">Sie müssen über die entsprechenden Berechtigungen zum Ausführen der folgenden Aufgaben verfügen.</span><span class="sxs-lookup"><span data-stu-id="d7355-131">You must have appropriate permissions to perform the following tasks.</span></span> <span data-ttu-id="d7355-132">Siehe [erforderliche Berechtigungen für die Verwendung von Air-Funktionen](office-365-air.md#required-permissions-to-use-air-capabilities).</span><span class="sxs-lookup"><span data-stu-id="d7355-132">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

### <a name="view-and-investigate-restricted-users"></a><span data-ttu-id="d7355-133">Anzeigen und untersuchen eingeschränkter Benutzer</span><span class="sxs-lookup"><span data-stu-id="d7355-133">View and investigate restricted users</span></span>

<span data-ttu-id="d7355-134">Sie haben einige Optionen, um zu einer Liste eingeschränkter Benutzer zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="d7355-134">You have a few options for navigating to a list of restricted users.</span></span> <span data-ttu-id="d7355-135">Im Security & Compliance Center können Sie beispielsweise zu **Threat Management**  >  **Review**  >  **restricted users** wechseln.</span><span class="sxs-lookup"><span data-stu-id="d7355-135">For example, in the Security & Compliance Center, you can go to **Threat management** > **Review** > **Restricted Users**.</span></span> <span data-ttu-id="d7355-136">Im folgenden Verfahren wird die Navigation mithilfe des **Alerts** -Dashboards beschrieben, eine gute Möglichkeit, um verschiedene Arten von Warnungen anzuzeigen, die möglicherweise ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="d7355-136">The following procedure describes navigation using the **Alerts** dashboard, which is a good way to see various kinds of alerts that might have been triggered.</span></span>

1. <span data-ttu-id="d7355-137">Gehen Sie zu [https://protection.office.com](https://protection.office.com), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="d7355-137">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span>

2. <span data-ttu-id="d7355-138">Wählen Sie im Navigationsbereich **Warnungs**  >  **Dashboard** aus.</span><span class="sxs-lookup"><span data-stu-id="d7355-138">In the navigation pane, choose **Alerts** > **Dashboard**.</span></span>

3. <span data-ttu-id="d7355-139">Wählen Sie im Widget **andere Benachrichtigungen** die Option **eingeschränkte Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="d7355-139">In the **Other alerts** widget, choose **Restricted Users**.</span></span>

   ![Widget "andere Warnungen"](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   <span data-ttu-id="d7355-141">Dadurch wird die Liste der eingeschränkten Benutzer geöffnet.</span><span class="sxs-lookup"><span data-stu-id="d7355-141">This opens the list of restricted users.</span></span>

   ![Eingeschränkte Benutzer in Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. <span data-ttu-id="d7355-143">Wählen Sie ein Benutzerkonto in der Liste aus, um Details anzuzeigen und Aktionen durchführen zu können, beispielsweise [das Freigeben des eingeschränkten Benutzers](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="d7355-143">Select a user account in the list to view details and take action, such as [releasing the restricted user](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="view-details-about-automated-investigations"></a><span data-ttu-id="d7355-144">Anzeigen von Details zu automatisierten Untersuchungen</span><span class="sxs-lookup"><span data-stu-id="d7355-144">View details about automated investigations</span></span>

<span data-ttu-id="d7355-145">Wenn eine automatisierte Untersuchung begonnen hat, können Sie Details und Ergebnisse im Security & Compliance Center anzeigen.</span><span class="sxs-lookup"><span data-stu-id="d7355-145">When an automated investigation has begun, you can see its details and results in the Security & Compliance Center.</span></span> <span data-ttu-id="d7355-146">Wechseln Sie zu **Threat Management**  >  **Investigations**, und wählen Sie dann eine Untersuchung aus, um die Details anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d7355-146">Go to **Threat management** > **Investigations**, and then select an investigation to view its details.</span></span>

<span data-ttu-id="d7355-147">Weitere Informationen finden Sie unter [View Details of a Investigation](air-view-investigation-results.md).</span><span class="sxs-lookup"><span data-stu-id="d7355-147">To learn more, see [View details of an investigation](air-view-investigation-results.md).</span></span>

## <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="d7355-148">Beachten Sie die folgenden Punkte:</span><span class="sxs-lookup"><span data-stu-id="d7355-148">Keep the following points in mind</span></span>

- <span data-ttu-id="d7355-149">**Behalten Sie Ihre Benachrichtigungen im Vorder** Grund.</span><span class="sxs-lookup"><span data-stu-id="d7355-149">**Stay on top of your alerts**.</span></span> <span data-ttu-id="d7355-150">Wie Sie wissen, gilt: je länger ein Kompromiss unentdeckt bleibt, desto größer ist das Potenzial für weit verbreitete Auswirkungen und Kosten für Ihre Organisation, Kunden und Partner.</span><span class="sxs-lookup"><span data-stu-id="d7355-150">As you know, the longer a compromise goes undetected, the larger the potential for widespread impact and cost to your organization, customers, and partners.</span></span> <span data-ttu-id="d7355-151">Frühzeitige Erkennung und zeitnahe Reaktion sind wichtig, um Bedrohungen zu minimieren, insbesondere dann, wenn das Konto eines Benutzers kompromittiert wird.</span><span class="sxs-lookup"><span data-stu-id="d7355-151">Early detection and timely response are critical to mitigate threats, and especially when a user's account is compromised.</span></span>

- <span data-ttu-id="d7355-152">**Automatisierung unterstützt, ersetzt aber Ihr Sicherheits Betriebsteam**.</span><span class="sxs-lookup"><span data-stu-id="d7355-152">**Automation assists, but does not replace, your security operations team**.</span></span> <span data-ttu-id="d7355-153">Automatisierte Ermittlungs-und Antwortfunktionen können einen gefährdeten Benutzer frühzeitig erkennen, aber Ihr Sicherheits Betriebsteam muss wahrscheinlich einige Untersuchungen und Korrekturen durchführen.</span><span class="sxs-lookup"><span data-stu-id="d7355-153">Automated investigation and response capabilities can detect a compromised user early on, but your security operations team will likely need to engage and do some investigation and remediation.</span></span> <span data-ttu-id="d7355-154">Benötigen Sie Hilfe?</span><span class="sxs-lookup"><span data-stu-id="d7355-154">Need some help with this?</span></span> <span data-ttu-id="d7355-155">Weitere Informationen finden Sie unter [überprüfen und Genehmigen von Aktionen](air-review-approve-pending-completed-actions.md).</span><span class="sxs-lookup"><span data-stu-id="d7355-155">See [Review and approve actions](air-review-approve-pending-completed-actions.md).</span></span>

- <span data-ttu-id="d7355-156">**Verlassen Sie sich nicht auf eine verdächtige Anmelde Warnung als einzigen Indikator**.</span><span class="sxs-lookup"><span data-stu-id="d7355-156">**Don't rely on a suspicious login alert as your only indicator**.</span></span> <span data-ttu-id="d7355-157">Wenn ein Benutzerkonto kompromittiert wird, wird möglicherweise eine verdächtige Anmelde Warnung ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="d7355-157">When a user account is compromised, it might or might not trigger a suspicious login alert.</span></span> <span data-ttu-id="d7355-158">Manchmal handelt es sich um die Reihe von Aktivitäten, die auftreten, nachdem ein Konto kompromittiert wurde, das eine Warnung auslöst.</span><span class="sxs-lookup"><span data-stu-id="d7355-158">Sometimes it's the series of activities that occur after an account is compromised that triggers an alert.</span></span> <span data-ttu-id="d7355-159">Möchten Sie mehr über Benachrichtigungen erfahren?</span><span class="sxs-lookup"><span data-stu-id="d7355-159">Want to know more about alerts?</span></span> <span data-ttu-id="d7355-160">Siehe [Warnungsrichtlinien](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span><span class="sxs-lookup"><span data-stu-id="d7355-160">See [Alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d7355-161">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="d7355-161">Next steps</span></span>

- [<span data-ttu-id="d7355-162">Überprüfen der erforderlichen Berechtigungen für die Verwendung von Air-Funktionen</span><span class="sxs-lookup"><span data-stu-id="d7355-162">Review the required permissions to use AIR capabilities</span></span>](office-365-air.md#required-permissions-to-use-air-capabilities)

- [<span data-ttu-id="d7355-163">Suchen und untersuchen von böswilligen e-Mails in Office 365</span><span class="sxs-lookup"><span data-stu-id="d7355-163">Find and investigate malicious email in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="d7355-164">Informationen zu Air in Microsoft Defender für Endpoint</span><span class="sxs-lookup"><span data-stu-id="d7355-164">Learn about AIR in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="d7355-165">Besuchen Sie die Microsoft 365-Roadmap, um zu sehen, was bald kommt und wie Sie Rollen</span><span class="sxs-lookup"><span data-stu-id="d7355-165">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)
