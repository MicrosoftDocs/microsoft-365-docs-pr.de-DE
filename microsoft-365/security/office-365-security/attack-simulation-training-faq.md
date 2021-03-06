---
title: Überlegungen zur Bereitstellung von Schulungspaketen für Angriffssimulationen und häufig gestellte Fragen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Administratoren können sich über Bereitstellungsüberlegungen und häufig gestellte Fragen zur Angriffssimulation und -schulung in Microsoft 365 E5- oder Microsoft Defender for Office 365 Plan 2-Organisationen informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b57252252d8a22ade4b8e1a18f42d7fdce91324e
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454734"
---
# <a name="attack-simulation-training-deployment-considerations-and-faq"></a><span data-ttu-id="77821-103">Überlegungen zur Bereitstellung von Schulungspaketen für Angriffssimulationen und häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="77821-103">Attack simulation training deployment considerations and FAQ</span></span>

<span data-ttu-id="77821-104">Das Training zur Angriffssimulation ist [jetzt allgemein verfügbar.](https://techcommunity.microsoft.com/t5/microsoft-security-and/attack-simulation-training-in-microsoft-defender-for-office-365/ba-p/2037291)</span><span class="sxs-lookup"><span data-stu-id="77821-104">Attack simulation training is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-security-and/attack-simulation-training-in-microsoft-defender-for-office-365/ba-p/2037291).</span></span> <span data-ttu-id="77821-105">Die Schulung zur Angriffssimulation ermöglicht Microsoft 365 E5- oder Microsoft Defender für Office 365 Plan 2-Organisationen das Messen und Verwalten von Social Engineering-Risiken, indem die Erstellung und Verwaltung von Phishingsimulationen ermöglicht wird, die von realen, entwaffnten Phishing-Nutzlasten unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="77821-105">Attack simulation training enables Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2 organizations to measure and manage social engineering risk by allowing the creation and management of phishing simulations that are powered by real-world, de-weaponized phishing payloads.</span></span> <span data-ttu-id="77821-106">Hyper gezielte Schulungen, die in Zusammenarbeit mit der Sicherheit von "Teronova" zur Verbesserung von Kenntnissen und zum Ändern des Verhaltens von Mitarbeitern führen.</span><span class="sxs-lookup"><span data-stu-id="77821-106">Hyper-targeted training, delivered in partnership with Terranova security, helps improve knowledge and change employee behavior.</span></span>

<span data-ttu-id="77821-107">Weitere Informationen zu den ersten Schritte mit attack simulation training finden Sie unter [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span><span class="sxs-lookup"><span data-stu-id="77821-107">For more information about getting started with Attack simulation training, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>

<span data-ttu-id="77821-108">Während die gesamte Simulationserstellungs- und Zeitplanungsumgebung frei fließend und reibungsfrei konzipiert wurde, ist für das Ausführen von Simulationen auf Unternehmensskala häufig eine Planung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="77821-108">While the whole simulation creation and scheduling experience has been designed to be free-flowing and frictionless, running simulations at an enterprise scale often requires planning.</span></span> <span data-ttu-id="77821-109">Dieser Artikel hilft dabei, bestimmte Herausforderungen zu bewältigen, die wir sehen, wenn unsere Kunden Simulationen in ihren eigenen Umgebungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="77821-109">This article helps address specific challenges that we see as our customers run simulations in their own environments.</span></span>

## <a name="issues-with-end-user-experiences"></a><span data-ttu-id="77821-110">Probleme mit der Endbenutzererfahrung</span><span class="sxs-lookup"><span data-stu-id="77821-110">Issues with end user experiences</span></span>

### <a name="phishing-simulation-urls-blocked-by-google-safe-browsing"></a><span data-ttu-id="77821-111">Phishingsimulations-URLs, die von Google Safe Browsing blockiert werden</span><span class="sxs-lookup"><span data-stu-id="77821-111">Phishing simulation URLs blocked by Google Safe Browsing</span></span>

<span data-ttu-id="77821-112">Ein URL-Reputationsdienst kann eine oder mehrere der URLs identifizieren, die von attack simulation training als unsicher verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="77821-112">A URL reputation service might identify one or more of the URLs that are used by Attack simulation training as unsafe.</span></span> <span data-ttu-id="77821-113">Google Safe Browsing in Google Chrome blockiert einige der simulierten Phishing-URLs mit einer **trügerischen Website-Vorausmeldung.**</span><span class="sxs-lookup"><span data-stu-id="77821-113">Google Safe Browsing in Google Chrome blocks some of the simulated phishing URLs with a **Deceptive site ahead** message.</span></span> <span data-ttu-id="77821-114">Wir arbeiten zwar mit vielen ANBIETER für die URL-Reputation zusammen, um unsere Simulations-URLs immer zu erlauben, aber nicht immer haben wir eine vollständige Abdeckung.</span><span class="sxs-lookup"><span data-stu-id="77821-114">While we work with many URL reputation vendors to always allow our simulation URLs, we don't always have full coverage.</span></span>

![Warnung vor einer trügerischen Website in Google Chrome](../../media/attack-sim-chrome-deceptive-site-message.png)

<span data-ttu-id="77821-116">Beachten Sie, dass dieses Problem keine Auswirkungen auf Microsoft Edge hat.</span><span class="sxs-lookup"><span data-stu-id="77821-116">Note that this issue does not affect Microsoft Edge.</span></span>

<span data-ttu-id="77821-117">Überprüfen Sie im Rahmen der Planungsphase unbedingt die Verfügbarkeit der URL in Ihren unterstützten Webbrowsern, bevor Sie die URL in einer Phishingkampagne verwenden.</span><span class="sxs-lookup"><span data-stu-id="77821-117">As part of the planning phase, be sure to check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="77821-118">Wenn die URLs von Google Safe Browsing blockiert [werden,](https://support.google.com/chrome/a/answer/7532419) befolgen Sie diese Anleitung von Google, um den Zugriff auf die URLs zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="77821-118">If the URLs are blocked by Google Safe Browsing, [follow this guidance](https://support.google.com/chrome/a/answer/7532419) from Google to allow access to the URLs.</span></span>

<span data-ttu-id="77821-119">Informationen zur Liste der URLs, die derzeit von [Attack Simulation Training](attack-simulation-training-get-started.md) verwendet werden, finden Sie unter Erste Schritte bei der Verwendung von Angriffssimulationsschulungen.</span><span class="sxs-lookup"><span data-stu-id="77821-119">Refer to [Get started using Attack simulation training](attack-simulation-training-get-started.md) for the list of URLs that are currently used by Attack simulation training.</span></span>

### <a name="phishing-simulation-and-admin-urls-blocked-by-network-proxy-solutions-and-filter-drivers"></a><span data-ttu-id="77821-120">Phishingsimulation und Administrator-URLs, die von Netzwerkproxylösungen und Filtertreibern blockiert werden</span><span class="sxs-lookup"><span data-stu-id="77821-120">Phishing simulation and admin URLs blocked by network proxy solutions and filter drivers</span></span>

<span data-ttu-id="77821-121">Sowohl Phishingsimulations-URLs als auch Administrator-URLs können von Ihren Zwischensicherheitsgeräten oder -filtern blockiert oder verworfen werden.</span><span class="sxs-lookup"><span data-stu-id="77821-121">Both phishing simulation URLs and admin URLs might be blocked or dropped by your intermediate security devices or filters.</span></span> <span data-ttu-id="77821-122">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="77821-122">For example:</span></span>

- <span data-ttu-id="77821-123">Firewalls</span><span class="sxs-lookup"><span data-stu-id="77821-123">Firewalls</span></span>
- <span data-ttu-id="77821-124">Web Application Firewall (WAF)-Lösungen</span><span class="sxs-lookup"><span data-stu-id="77821-124">Web Application Firewall (WAF) solutions</span></span>
- <span data-ttu-id="77821-125">Filtertreiber von Drittanbietern (z. B. Kernelmodusfilter)</span><span class="sxs-lookup"><span data-stu-id="77821-125">Third-party filter drivers (for example, kernel mode filters)</span></span>

<span data-ttu-id="77821-126">Wir haben zwar gesehen, dass auf dieser Ebene nur wenige Kunden blockiert wurden, aber dies geschieht.</span><span class="sxs-lookup"><span data-stu-id="77821-126">While we have seen few customers being blocked at this layer, it does happen.</span></span> <span data-ttu-id="77821-127">Wenn Probleme auftreten, sollten Sie die folgenden URLs konfigurieren, um die Überprüfung durch Ihre Sicherheitsgeräte oder Filter nach Bedarf zu umgehen:</span><span class="sxs-lookup"><span data-stu-id="77821-127">If you encounter problems, consider configuring the following URLs to bypass scanning by your security devices or filters as required:</span></span>

- <span data-ttu-id="77821-128">Die simulierten Phishing-URLs, wie unter [Erste Schritte mit Attack Simulation Training beschrieben.](attack-simulation-training-get-started.md)</span><span class="sxs-lookup"><span data-stu-id="77821-128">The simulated phishing URLs as described in [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>
- <https://security.microsoft.com/attacksimulator>
- <https://security.microsoft.com/attacksimulationreport>
- <https://security.microsoft.com/trainingassignments>

### <a name="simulation-messages-not-delivered-to-all-targeted-users"></a><span data-ttu-id="77821-129">Simulationsmeldungen, die nicht an alle Zielbenutzer übermittelt werden</span><span class="sxs-lookup"><span data-stu-id="77821-129">Simulation messages not delivered to all targeted users</span></span>

<span data-ttu-id="77821-130">Es ist möglich, dass die Anzahl der Benutzer, die die Simulations-E-Mail-Nachrichten tatsächlich empfangen, kleiner ist als die Anzahl der Benutzer, die von der Simulation gezielt wurden.</span><span class="sxs-lookup"><span data-stu-id="77821-130">It's possible that the number of users who actually receive the simulation email messages is less than the number of users who were targeted by the simulation.</span></span> <span data-ttu-id="77821-131">Die folgenden Benutzertypen werden im Rahmen der Zielüberprüfung ausgeschlossen:</span><span class="sxs-lookup"><span data-stu-id="77821-131">The following types of users will be excluded as part of target validation:</span></span>

- <span data-ttu-id="77821-132">Ungültige Empfänger-E-Mail-Adressen.</span><span class="sxs-lookup"><span data-stu-id="77821-132">Invalid recipient email addresses.</span></span>
- <span data-ttu-id="77821-133">Gastbenutzer.</span><span class="sxs-lookup"><span data-stu-id="77821-133">Guest users.</span></span>
- <span data-ttu-id="77821-134">Benutzer, die nicht mehr in Azure Active Directory (Azure AD) aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="77821-134">Users that are no longer active in Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="77821-135">Nur gültige, nicht gastfreie Benutzer mit einem gültigen Postfach werden in Simulationen einbezogen.</span><span class="sxs-lookup"><span data-stu-id="77821-135">Only valid, non-guest users with a valid mailbox will be included in simulations.</span></span> <span data-ttu-id="77821-136">Wenn Sie Verteilergruppen oder E-Mail-aktivierte Sicherheitsgruppen für Zielbenutzer verwenden, können Sie das [Cmdlet Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember) in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) verwenden, um Verteilergruppenmitglieder zu anzeigen und zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="77821-136">If you use distribution groups or mail-enabled security groups to target users, you can use the [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember) cmdlet in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) to view and validate distribution group members.</span></span>

## <a name="issues-with-attack-simulation-training-reporting"></a><span data-ttu-id="77821-137">Probleme bei der Berichterstellung für Angriffssimulationsschulungen</span><span class="sxs-lookup"><span data-stu-id="77821-137">Issues with Attack simulation training reporting</span></span>

### <a name="attack-simulation-training-reports-do-not-contain-any-activity-details"></a><span data-ttu-id="77821-138">Schulungsberichte zur Angriffssimulation enthalten keine Aktivitätsdetails</span><span class="sxs-lookup"><span data-stu-id="77821-138">Attack simulation training reports do not contain any activity details</span></span>

<span data-ttu-id="77821-139">Das Training zur Angriffssimulation bietet umfassende, umsetzbare Einblicke, die Sie über den Fortschritt der Bedrohungsbereitschaft Ihrer Mitarbeiter informieren.</span><span class="sxs-lookup"><span data-stu-id="77821-139">Attack simulation training comes with rich, actionable insights that keep you informed of the threat readiness progress of your employees.</span></span> <span data-ttu-id="77821-140">Wenn Angriffssimulationsschulungsberichte nicht mit Daten gefüllt werden, überprüfen Sie, ob die Überwachungsprotokollsuche in Ihrer Organisation aktiviert ist (standardmäßig aktiviert).</span><span class="sxs-lookup"><span data-stu-id="77821-140">If Attack simulation training reports are not populated with data, verify that audit log search is turned on in your organization (it's on by default).</span></span>

<span data-ttu-id="77821-141">Die Überwachungsprotokollsuche ist für die Attack Simulationsschulung erforderlich, damit Ereignisse erfasst, aufgezeichnet und zurückgelesen werden können.</span><span class="sxs-lookup"><span data-stu-id="77821-141">Audit log search is required by Attack simulation training so events can be captured, recorded, and read back.</span></span> <span data-ttu-id="77821-142">Das Deaktivieren der Überwachungsprotokollsuche hat die folgenden Folgen für das Training der Angriffssimulation:</span><span class="sxs-lookup"><span data-stu-id="77821-142">Turning off audit log search has the following consequences for Attack simulation training:</span></span>

- <span data-ttu-id="77821-143">Berichtsdaten sind nicht in allen Berichten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="77821-143">Reporting data is not available across all reports.</span></span> <span data-ttu-id="77821-144">Die Berichte werden leer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="77821-144">The reports will appear empty.</span></span>
- <span data-ttu-id="77821-145">Schulungszuweisungen werden blockiert, da keine Daten verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="77821-145">Training assignments are blocked, because data is not available.</span></span>

<span data-ttu-id="77821-146">Informationen zum Aktivieren der Überwachungsprotokollsuche finden Sie unter Aktivieren oder Deaktivieren der [Überwachungsprotokollsuche.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="77821-146">To turn on audit log search, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

> [!NOTE]
> <span data-ttu-id="77821-147">Leere Aktivitätsdetails können auch dadurch verursacht werden, dass benutzern keine E5-Lizenzen zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="77821-147">Empty activity details can also be caused by no E5 licenses being assigned to users.</span></span> <span data-ttu-id="77821-148">Überprüfen Sie, ob einem aktiven Benutzer mindestens eine E5-Lizenz zugewiesen ist, um sicherzustellen, dass Berichterstellungsereignisse erfasst und aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="77821-148">Verify at least one E5 license is assigned to an active user to ensure that reporting events are captured and recorded.</span></span>

### <a name="simulation-reports-are-not-updated-immediately"></a><span data-ttu-id="77821-149">Simulationsberichte werden nicht sofort aktualisiert</span><span class="sxs-lookup"><span data-stu-id="77821-149">Simulation reports are not updated immediately</span></span>

<span data-ttu-id="77821-150">Detaillierte Simulationsberichte werden nicht unmittelbar nach dem Starten einer Kampagne aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="77821-150">Detailed simulation reports are not updated immediately after you launch a campaign.</span></span> <span data-ttu-id="77821-151">Machen Sie sich keine Sorgen. dieses Verhalten wird erwartet.</span><span class="sxs-lookup"><span data-stu-id="77821-151">Don't worry; this behavior is expected.</span></span>

<span data-ttu-id="77821-152">Jede Simulationskampagne hat einen Lebenszyklus.</span><span class="sxs-lookup"><span data-stu-id="77821-152">Every simulation campaign has a lifecycle.</span></span> <span data-ttu-id="77821-153">Beim ersten Erstellen befindet sich die Simulation im **Planzustand.**</span><span class="sxs-lookup"><span data-stu-id="77821-153">When first created, the simulation is in the **Scheduled** state.</span></span> <span data-ttu-id="77821-154">Wenn die Simulation gestartet wird, wird sie in den Status **In Bearbeitung** überwechselt.</span><span class="sxs-lookup"><span data-stu-id="77821-154">When the simulation starts, it transitions to the **In progress** state.</span></span> <span data-ttu-id="77821-155">Nach Abschluss wird die Simulation in den Status **Abgeschlossen** überwechselt.</span><span class="sxs-lookup"><span data-stu-id="77821-155">When completed, the simulation transitions to the **Completed** state.</span></span>

<span data-ttu-id="77821-156">Während sich eine Simulation im **Planzustand** befindet, sind die Simulationsberichte größtenteils leer.</span><span class="sxs-lookup"><span data-stu-id="77821-156">While a simulation is in the **Scheduled** state, the simulation reports will be mostly empty.</span></span> <span data-ttu-id="77821-157">In dieser Phase wird das Simulationsmodul die E-Mail-Adressen des Zielbenutzers auflösen, Verteilergruppen erweitern, Gastbenutzer aus der Liste entfernen usw.:</span><span class="sxs-lookup"><span data-stu-id="77821-157">During this stage, the simulation engine is resolving the target user email addresses, expanding distribution groups, removing guest users from the list, etc.:</span></span>

![Berichterstellung im Status "Geplant"](../../media/attack-sim-empty-reporting.png)

<span data-ttu-id="77821-159">Sobald die Simulation in die **Phase In Bearbeitung** einschreitet, werden Sie feststellen, dass die Informationen in die Berichterstellung einfingen:</span><span class="sxs-lookup"><span data-stu-id="77821-159">Once the simulation enters the **In progress** stage, you will notice information starting to trickle into the reporting:</span></span>

![Berichterstellung im Status In Bearbeitung](../../media/attack-sim-in-progress.png)

<span data-ttu-id="77821-161">Es kann bis zu 30 Minuten dauern, bis die einzelnen Simulationsberichte nach dem Übergang zum Status **In Bearbeitung aktualisiert** werden.</span><span class="sxs-lookup"><span data-stu-id="77821-161">It can take up to 30 minutes for the individual simulation reports to update after the transition to the **In progress** state.</span></span> <span data-ttu-id="77821-162">Die Berichtsdaten werden weiter entwickelt, bis die Simulation den Status **Abgeschlossen** erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="77821-162">The report data continues to build until the simulation reaches the **Completed** state.</span></span> <span data-ttu-id="77821-163">Berichterstellungsupdates erfolgen in den folgenden Intervallen:</span><span class="sxs-lookup"><span data-stu-id="77821-163">Reporting updates occur at the following intervals:</span></span>

- <span data-ttu-id="77821-164">Alle 10 Minuten für die ersten 60 Minuten.</span><span class="sxs-lookup"><span data-stu-id="77821-164">Every 10 minutes for the first 60 minutes.</span></span>
- <span data-ttu-id="77821-165">Alle 15 Minuten nach 60 Minuten bis 2 Tage.</span><span class="sxs-lookup"><span data-stu-id="77821-165">Every 15 minutes after 60 minutes until 2 days.</span></span>
- <span data-ttu-id="77821-166">Alle 30 Minuten nach 2 Tagen bis 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="77821-166">Every 30 minutes after 2 days until 7 days.</span></span>
- <span data-ttu-id="77821-167">Alle 60 Minuten nach 7 Tagen.</span><span class="sxs-lookup"><span data-stu-id="77821-167">Every 60 minutes after 7 days.</span></span>

<span data-ttu-id="77821-168">Widgets auf der **Seite Übersicht** bieten eine kurze Momentaufnahme der simulationsbasierten Sicherheitslage Ihrer Organisation im Laufe der Zeit.</span><span class="sxs-lookup"><span data-stu-id="77821-168">Widgets on the **Overview** page provide a quick snapshot of your organization's simulation-based security posture over time.</span></span> <span data-ttu-id="77821-169">Da diese Widgets Ihre allgemeine Sicherheitslage und Denkzeit widerspiegeln, werden sie nach Abschluss jeder Simulationskampagne aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="77821-169">Because these widgets reflect your overall security posture and journey over time, they're updated after each simulation campaign is completed.</span></span>

> [!NOTE]
> <span data-ttu-id="77821-170">Sie können die Option **Export auf** den verschiedenen Berichtsseiten verwenden, um Daten zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="77821-170">You can use the **Export** option on the various reporting pages to extract data.</span></span>

### <a name="messages-reported-as-phishing-by-users-arent-appearing-in-simulation-reports"></a><span data-ttu-id="77821-171">Von Benutzern als Phishing gemeldete Nachrichten werden in Simulationsberichten nicht angezeigt</span><span class="sxs-lookup"><span data-stu-id="77821-171">Messages reported as phishing by users aren't appearing in simulation reports</span></span>

<span data-ttu-id="77821-172">Simulationsberichte in Attack simulator training enthalten Details zur Benutzeraktivität.</span><span class="sxs-lookup"><span data-stu-id="77821-172">Simulation reports in Attack simulator training provide details on user activity.</span></span> <span data-ttu-id="77821-173">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="77821-173">For example:</span></span>

- <span data-ttu-id="77821-174">Benutzer, die auf den Link in der Nachricht geklickt haben.</span><span class="sxs-lookup"><span data-stu-id="77821-174">Users who clicked on the link in the message.</span></span>
- <span data-ttu-id="77821-175">Benutzer, die ihre Anmeldeinformationen aufgaben.</span><span class="sxs-lookup"><span data-stu-id="77821-175">Users who gave up their credentials.</span></span>
- <span data-ttu-id="77821-176">Benutzer, die die Nachricht als Phishing gemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="77821-176">Users who reported the message as phishing.</span></span>

<span data-ttu-id="77821-177">Wenn Nachrichten, die Von Benutzern als Phishing gemeldet wurden, nicht in Simulationsberichten zur Simulation von Angriffen erfasst werden, gibt es möglicherweise eine Exchange-Nachrichtenflussregel (auch als Transportregel bezeichnet), die die Zustellung der gemeldeten Nachrichten an Microsoft blockiert.</span><span class="sxs-lookup"><span data-stu-id="77821-177">If messages that users reported as phishing aren't captured in Attack simulation training simulation reports, there might be an Exchange mail flow rule (also known as a transport rule) that's blocking the delivery of the reported messages to Microsoft.</span></span> <span data-ttu-id="77821-178">Stellen Sie sicher, dass Nachrichtenflussregeln die Zustellung an die folgenden E-Mail-Adressen nicht blockieren:</span><span class="sxs-lookup"><span data-stu-id="77821-178">Verify that any mail flow rules aren't blocking delivery to the following email addresses:</span></span>

- <span data-ttu-id="77821-179">junk@office365.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="77821-179">junk@office365.microsoft.com</span></span>
- <span data-ttu-id="77821-180">abuse@messaging.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="77821-180">abuse@messaging.microsoft.com</span></span>
- <span data-ttu-id="77821-181">phish@office365.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="77821-181">phish@office365.microsoft.com</span></span>
- <span data-ttu-id="77821-182">nicht \_ junk@office365.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="77821-182">not\_junk@office365.microsoft.com</span></span>

## <a name="other-frequently-asked-questions"></a><span data-ttu-id="77821-183">Weitere häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="77821-183">Other frequently asked questions</span></span>

### <a name="q-what-is-the-recommended-method-to-target-users-for-simulation-campaigns"></a><span data-ttu-id="77821-184">F: Welche Methode wird empfohlen, um Benutzer für Simulationskampagnen zu verwenden?</span><span class="sxs-lookup"><span data-stu-id="77821-184">Q: What is the recommended method to target users for simulation campaigns?</span></span>

<span data-ttu-id="77821-185">A: Für Zielbenutzer stehen mehrere Optionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="77821-185">A: Several options are available to target users:</span></span>

- <span data-ttu-id="77821-186">Schließen Sie alle Benutzer ein (derzeit für Organisationen mit weniger als 40.000 Benutzern verfügbar).</span><span class="sxs-lookup"><span data-stu-id="77821-186">Include all users (currently available to organizations with less than 40,000 users).</span></span>
- <span data-ttu-id="77821-187">Wählen Sie bestimmte Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="77821-187">Choose specific users.</span></span>
- <span data-ttu-id="77821-188">Wählen Sie Benutzer aus einer CSV-Datei aus.</span><span class="sxs-lookup"><span data-stu-id="77821-188">Select users from a CSV file.</span></span>
- <span data-ttu-id="77821-189">Gruppenbasiertes Azure AD-Ziel.</span><span class="sxs-lookup"><span data-stu-id="77821-189">Azure AD group-based targeting.</span></span>

<span data-ttu-id="77821-190">Wir haben festgestellt, dass Kampagnen, bei denen die Zielbenutzer von Azure AD-Gruppen identifiziert werden, im Allgemeinen einfacher zu verwalten sind.</span><span class="sxs-lookup"><span data-stu-id="77821-190">We've found that campaigns where the targeted users are identified by Azure AD groups are generally easier to manage.</span></span>

### <a name="q-are-there-any-limits-in-targeting-users-while-importing-from-a-csv-or-adding-users"></a><span data-ttu-id="77821-191">F: Gibt es Einschränkungen bei der Zielgruppensteuerung beim Importieren aus einer CSV oder beim Hinzufügen von Benutzern?</span><span class="sxs-lookup"><span data-stu-id="77821-191">Q: Are there any limits in targeting users while importing from a CSV or adding users?</span></span>

<span data-ttu-id="77821-192">A: Der Grenzwert für das Importieren von Empfängern aus einer CSV-Datei oder das Hinzufügen einzelner Empfänger zu einer Simulation beträgt 40.000.</span><span class="sxs-lookup"><span data-stu-id="77821-192">A: The limit for importing recipients from a CSV file or adding individual recipients to a simulation is 40,000.</span></span>

<span data-ttu-id="77821-193">Ein Empfänger kann ein einzelner Benutzer oder eine Gruppe sein.</span><span class="sxs-lookup"><span data-stu-id="77821-193">A recipient can be an individual user or a group.</span></span> <span data-ttu-id="77821-194">Eine Gruppe kann Hunderte oder Tausende von Empfängern enthalten, sodass für die Anzahl der einzelnen Benutzer kein tatsächlicher Grenzwert gesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="77821-194">A group might contain hundreds or thousands of recipients, so an actual limit isn't placed on the number of individual users.</span></span>

<span data-ttu-id="77821-195">Das Verwalten einer großen CSV-Datei oder das Hinzufügen vieler einzelner Empfänger kann umständlich sein.</span><span class="sxs-lookup"><span data-stu-id="77821-195">Managing a large CSV file or adding many individual recipients can be cumbersome.</span></span> <span data-ttu-id="77821-196">Die Verwendung von Azure AD-Gruppen vereinfacht die Gesamtverwaltung der Simulation.</span><span class="sxs-lookup"><span data-stu-id="77821-196">Using Azure AD groups will simplify the overall management of the simulation.</span></span>

### <a name="q-does-microsoft-provide-payloads-in-other-languages"></a><span data-ttu-id="77821-197">F: Stellt Microsoft Nutzlasten in anderen Sprachen zur Verfügung?</span><span class="sxs-lookup"><span data-stu-id="77821-197">Q: Does Microsoft provide payloads in other languages?</span></span>

<span data-ttu-id="77821-198">A: Derzeit sind 5 lokalisierte Nutzlasten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="77821-198">A: Currently, there are 5 localized payloads available.</span></span> <span data-ttu-id="77821-199">Es ist uns aufgefallen, dass direkte oder maschinelle Übersetzungen vorhandener Nutzlasten in andere Sprachen zu Ungenauigkeiten und einer verringerten Relevanz führen.</span><span class="sxs-lookup"><span data-stu-id="77821-199">We've noticed than any direct or machine translations of existing payloads to other languages will lead to inaccuracies and decreased relevance.</span></span>

<span data-ttu-id="77821-200">Sie können jedoch ihre eigene Nutzlast in der Sprache Ihrer Wahl mithilfe der benutzerdefinierten Nutzlasterstellungserfahrung erstellen.</span><span class="sxs-lookup"><span data-stu-id="77821-200">That being said, you can create your own payload in the language of your choice using the custom payload authoring experience.</span></span> <span data-ttu-id="77821-201">Außerdem wird dringend empfohlen, vorhandene Nutzlasten zu verwenden, die für Benutzer in einer bestimmten Geografischen Region verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="77821-201">We also strongly recommend that you harvest existing payloads that were used to target users in a specific geography.</span></span> <span data-ttu-id="77821-202">Mit anderen Worten: Lassen Sie die Angreifer den Inhalt für Sie lokalisieren.</span><span class="sxs-lookup"><span data-stu-id="77821-202">In other words, let the attackers localize the content for you.</span></span>

### <a name="q-how-can-i-switch-to-other-languages-for-my-admin-portal-and-training-experience"></a><span data-ttu-id="77821-203">F: Wie kann ich für mein Administratorportal und meine Schulungserfahrung zu anderen Sprachen wechseln?</span><span class="sxs-lookup"><span data-stu-id="77821-203">Q: How can I switch to other languages for my admin portal and training experience?</span></span>

<span data-ttu-id="77821-204">A: In Microsoft 365 oder Office 365 ist die Sprachkonfiguration für jedes Benutzerkonto spezifisch und zentralisiert.</span><span class="sxs-lookup"><span data-stu-id="77821-204">A: In Microsoft 365 or Office 365, language configuration is specific and centralized for each user account.</span></span> <span data-ttu-id="77821-205">Anweisungen zum Ändern Ihrer Spracheinstellung finden Sie unter Ändern der Anzeigesprache und Zeitzone [in Microsoft 365 for Business](https://support.microsoft.com/office/6f238bff-5252-441e-b32b-655d5d85d15b).</span><span class="sxs-lookup"><span data-stu-id="77821-205">For instructions on how to change your language setting, see [Change your display language and time zone in Microsoft 365 for Business](https://support.microsoft.com/office/6f238bff-5252-441e-b32b-655d5d85d15b).</span></span>

<span data-ttu-id="77821-206">Beachten Sie, dass es bis zu 30 Minuten dauern kann, bis die Konfigurationsänderung für alle Dienste synchronisiert wird.</span><span class="sxs-lookup"><span data-stu-id="77821-206">Note that the configuration change might take up to 30 minutes to synchronize across all services.</span></span>

### <a name="q-can-i-trigger-a-test-simulation-to-understand-what-it-looks-like-prior-to-launching-a-full-fledged-campaign"></a><span data-ttu-id="77821-207">F: Kann ich eine Testsimulation auslösen, um zu verstehen, wie sie vor dem Starten einer vollständigen Kampagne aussieht?</span><span class="sxs-lookup"><span data-stu-id="77821-207">Q: Can I trigger a test simulation to understand what it looks like prior to launching a full-fledged campaign?</span></span>

<span data-ttu-id="77821-208">A: Ja, sie können!</span><span class="sxs-lookup"><span data-stu-id="77821-208">A: Yes you can!</span></span> <span data-ttu-id="77821-209">Auf der letzten Seite **Simulation** überprüfen im Assistenten zum Erstellen einer neuen Simulation gibt es eine Option zum Senden **eines Tests**.</span><span class="sxs-lookup"><span data-stu-id="77821-209">On the very last **Review Simulation** page in the wizard to create a new simulation, there's an option to **Send a test**.</span></span> <span data-ttu-id="77821-210">Diese Option sendet eine Beispielnachricht zur Phishingsimulation an den aktuell angemeldeten Benutzer.</span><span class="sxs-lookup"><span data-stu-id="77821-210">This option will send a sample phishing simulation message to the currently logged in user.</span></span> <span data-ttu-id="77821-211">Nachdem Sie die Phishingnachricht in Ihrem Posteingang überprüft haben, können Sie die Simulation übermitteln.</span><span class="sxs-lookup"><span data-stu-id="77821-211">After you validate the phishing message in your Inbox, you can submit the simulation.</span></span>

![Senden einer Testschaltfläche auf der Seite Simulation überprüfen](../../media/attack-sim-review-simulation-page.png)

### <a name="q-can-i-target-users-that-belong-to-a-different-tenant-as-part-of-the-same-simulation-campaign"></a><span data-ttu-id="77821-213">F: Kann ich Benutzer, die zu einem anderen Mandanten gehören, im Rahmen derselben Simulationskampagne gezielt verwenden?</span><span class="sxs-lookup"><span data-stu-id="77821-213">Q: Can I target users that belong to a different tenant as part of the same simulation campaign?</span></span>

<span data-ttu-id="77821-214">A: Nein.</span><span class="sxs-lookup"><span data-stu-id="77821-214">A: No.</span></span> <span data-ttu-id="77821-215">Derzeit werden mandantenübergreifende Simulationen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="77821-215">Currently, cross-tenant simulations are not supported.</span></span> <span data-ttu-id="77821-216">Stellen Sie sicher, dass sich alle Ihre Zielbenutzer im gleichen Mandanten befinden.</span><span class="sxs-lookup"><span data-stu-id="77821-216">Verify that all of your targeted users are in the same tenant.</span></span> <span data-ttu-id="77821-217">Mandantenübergreifende Benutzer oder Gastbenutzer werden von der Simulationskampagne ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="77821-217">Any cross-tenant users or guest users will be excluded from the simulation campaign.</span></span>

### <a name="q-how-does-region-aware-delivery-work"></a><span data-ttu-id="77821-218">F: Wie funktioniert die regions bewusste Zustellung?</span><span class="sxs-lookup"><span data-stu-id="77821-218">Q: How does region aware delivery work?</span></span>

<span data-ttu-id="77821-219">A: Die regionsorientierte Zustellung verwendet das TimeZone-Attribut des Postfachs des Zielbenutzers und die Logik "nicht vor", um zu bestimmen, wann die Nachricht zu senden ist.</span><span class="sxs-lookup"><span data-stu-id="77821-219">A: Region aware delivery uses the TimeZone attribute of the targeted user's mailbox and 'not before' logic to determine when to deliver the message.</span></span> <span data-ttu-id="77821-220">Berücksichtigen Sie beispielsweise das folgende Szenario:</span><span class="sxs-lookup"><span data-stu-id="77821-220">For example, consider the following scenario:</span></span>

- <span data-ttu-id="77821-221">Um 7:00 Uhr in der Pazifischen Zeitzone (UTC-8) erstellt und plant ein Administrator eine Kampagne, die am selben Tag um 9:00 Uhr beginnt.</span><span class="sxs-lookup"><span data-stu-id="77821-221">At 7:00 AM in the Pacific time zone (UTC-8), an admin creates and schedules a campaign to start at 9:00 AM on the same day.</span></span>
- <span data-ttu-id="77821-222">UserA befindet sich in der Zeitzone "Ost" (UTC-5).</span><span class="sxs-lookup"><span data-stu-id="77821-222">UserA is in the Eastern time zone (UTC-5).</span></span>
- <span data-ttu-id="77821-223">UserB befindet sich auch in der Pazifischen Zeitzone.</span><span class="sxs-lookup"><span data-stu-id="77821-223">UserB is also in the Pacific time zone.</span></span>

<span data-ttu-id="77821-224">Um 09:00 Uhr am gleichen Tag wird die Simulationsnachricht an UserB gesendet.</span><span class="sxs-lookup"><span data-stu-id="77821-224">At 9:00 AM on the same day, the simulation message is sent to UserB.</span></span> <span data-ttu-id="77821-225">Bei der regioninte nen Übermittlung wird die Nachricht nicht am selben Tag an UserA gesendet, da 9:00 Uhr Pazifische Zeit 12:00 Uhr Ostzeit ist.</span><span class="sxs-lookup"><span data-stu-id="77821-225">With region-aware delivery, the message is not sent to UserA on the same day, because 9:00 AM Pacific time is 12:00 PM Eastern time.</span></span> <span data-ttu-id="77821-226">Stattdessen wird die Nachricht am folgenden Tag um 9:00 Uhr Ostzeit an UserA gesendet.</span><span class="sxs-lookup"><span data-stu-id="77821-226">Instead, the message is sent to UserA at 9:00 AM Eastern time on the following day.</span></span>

<span data-ttu-id="77821-227">Bei der ersten Ausführung einer Kampagne mit aktivierter Region wird die Simulationsnachricht möglicherweise nur an Benutzer in einer bestimmten Zeitzone gesendet.</span><span class="sxs-lookup"><span data-stu-id="77821-227">So, on the initial run of a campaign with region aware delivery enabled, it might appear that the simulation message was sent only to users in a specific time zone.</span></span> <span data-ttu-id="77821-228">Doch mit der Zeit und immer mehr Benutzern werden die zielorientierten Benutzer zunehmen.</span><span class="sxs-lookup"><span data-stu-id="77821-228">But, as time passes and more users come into scope, the targeted users will increase.</span></span>