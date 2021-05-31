---
title: Exchange Online-Überwachung für Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/03/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- NOCSH
description: Verwenden Sie die Exchange Online-Überwachung, um Informationen zu E-Mail-Vorfällen oder Empfehlungen in Microsoft 365 zu erhalten.
ms.openlocfilehash: ee31f8e152d7c54e37b850563bea57971e07f61c
ms.sourcegitcommit: 76c91e7b0d3172de57988eb4576d2b91c2f9ce18
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52707296"
---
# <a name="exchange-online-monitoring-for-microsoft-365"></a><span data-ttu-id="ff2fa-103">Exchange Online-Überwachung für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ff2fa-103">Exchange Online monitoring for Microsoft 365</span></span>

<span data-ttu-id="ff2fa-104">Mithilfe der Exchange Online-Überwachungsfunktion im Microsoft 365 Admin Center können Sie den Status des Exchange-Diensts für das Microsoft 365-Abonnement Ihrer Organisation überwachen.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-104">You can use Exchange Online monitoring in the Microsoft 365 admin center to monitor the health of the Exchange service for your organization’s Microsoft 365 subscription.</span></span> <span data-ttu-id="ff2fa-105">Über die Exchange Online-Überwachung erhalten Sie Informationen zu Vorfällen und Empfehlungen in bzw. zu den folgenden Kategorien:</span><span class="sxs-lookup"><span data-stu-id="ff2fa-105">Exchange Online monitoring provides you with information about incidents and advisories that are collected in these categories:</span></span>

- <span data-ttu-id="ff2fa-106">**Infrastruktur**: Es werden Probleme in der Microsoft 365-Infrastruktur von Microsoft ermittelt für die Bereitstellung regulärer Updates und die Lösung der Probleme.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-106">**Infrastructure**: Issue is detected in the Microsoft 365 infrastructure that Microsoft owns for providing regular updates and resolving the issue.</span></span> <span data-ttu-id="ff2fa-107">Beispiel: Benutzer können aufgrund von Problemen mit Exchange oder einer anderen Microsoft 365-Cloud-Infrastruktur nicht auf Exchange Online zugreifen.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-107">For example, users cannot access Exchange Online because of issues with Exchange or other Microsoft 365 cloud infrastructure.</span></span>
- <span data-ttu-id="ff2fa-108">**Infrastruktur eines Drittanbieters**: Es werden Probleme in der Infrastruktur eines Drittanbieters ermittelt, von der Ihre Organisation abhängig ist, die Maßnahmen zu deren Behebung von Seiten Ihrer Organisation erfordern.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-108">**Third-party infrastructure**: Issue is detected in third-party infrastructure on which your organization has taken a dependency and requires action from your organization for resolution.</span></span> <span data-ttu-id="ff2fa-109">Beispiel: Transaktionen zur Benutzerauthentifizierung werden durch einen Sicherheitstokendienst (STS, Security Token Service) eines Drittanbieters eingeschränkt, der verhindert, dass Benutzer eine Verbindung mit Exchange Online herstellen können.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-109">For example, user authentication transactions are getting throttled by a third-party security token service (STS) provider that prevents users from connecting to Exchange Online.</span></span>
- <span data-ttu-id="ff2fa-110">**Kundeninfrastruktur**: Es werden Probleme in der Infrastruktur Ihrer Organisation ermittelt, die Maßnahmen zu deren Behebung von Seiten Ihrer Organisation erfordern.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-110">**Customer infrastructure**: Issue is detected in your organization's infrastructure and requires action from your organization for resolution.</span></span> <span data-ttu-id="ff2fa-111">Beispiel: Benutzer können nicht auf Exchange Online zugreifen, da sie aufgrund eines abgelaufenen Zertifikats kein Authentifizierungstoken vom STS-Anbieter erhalten, der von Ihrer Organisation gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-111">For example, users cannot access Exchange Online because they are unable to obtain an authentication token from STS provider hosted by your organization because of an expired certificate.</span></span>

<span data-ttu-id="ff2fa-112">Nachfolgend sehen Sie ein Beispiel für die Seite **Dienststatus** im Microsoft 365 Admin Center, die über **Integrität > Dienststatus** zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-112">Here is an example of the **Service health** page in the Microsoft 365 admin center, available from **Health > Service health**.</span></span>

![Seite "Dienststatus" im Microsoft 365 Admin Center](../media/microsoft-365-exchange-monitoring/service-health-dashboard-example.png)

<span data-ttu-id="ff2fa-114">Der Wert der Spalte **Status** gibt an, ob der Dienst ordnungsgemäß ausgeführt wird, oder es werden basierend auf den von Microsoft verwalteten Cloud-Diensten Empfehlungen bzw. Vorfälle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-114">The value of the **Status** column indicates whether the service is healthy or has advisories or incidents based on the cloud services that Microsoft maintains.</span></span> 

<span data-ttu-id="ff2fa-115">Der Wert der Spalte **Probleme Ihrer Organisation und von Drittanbietern** gibt an, dass sich die Infrastruktur Ihres Unternehmens oder die Software von Drittanbietern auf die Nutzung der Dienste durch Ihre Benutzer in Exchange Online auswirkt.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-115">The value of the **Your org and 3rd party issues** column indicates that your organization's infrastructure or third-party software affects your users service health experience with Exchange Online.</span></span> <span data-ttu-id="ff2fa-116">Bei Empfehlungen oder Vorfällen sind Maßnahmen von *Ihrer* Seite erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-116">Advisories or incidents require *your* actions to resolve.</span></span>

<span data-ttu-id="ff2fa-117">Nachfolgend sehen Sie ein Beispiel für die **Exchange Online**-Überwachungsseite im Microsoft 365 Admin Center, die über **Integrität > Dienststatus > Exchange Online** zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-117">Here is an example of the **Exchange Online** monitoring page in the Microsoft 365 admin center, available from **Health > Service health > Exchange Online**.</span></span>

![Die Exchange Online-Überwachungsseite im Microsoft 365 Admin Center](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example.png)

<span data-ttu-id="ff2fa-119">Auf der **Exchange Online**-Überwachungsseite können Sie sehen, ob der Exchange Online-Dienst ordnungsgemäß funktioniert oder Probleme vorliegen, und ob damit zusammenhängende Vorfälle oder Empfehlungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-119">With the **Exchange Online** monitoring page, you can see whether the Exchange Online service is healthy or not and whether there are any associated incidents or advisories.</span></span> <span data-ttu-id="ff2fa-120">Mithilfe der Exchange Online-Überwachung können Sie sich den Dienststatus für bestimmte E-Mail-Szenarien ansehen und nahezu in Echtzeit Signale anzeigen, um die Auswirkungen nach Szenarien zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-120">With Exchange Online monitoring, you can look at the service health for specific email scenarios and view near real-time signals to determine the impact by scenario.</span></span> 

## <a name="requirements"></a><span data-ttu-id="ff2fa-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ff2fa-121">Requirements</span></span>

<span data-ttu-id="ff2fa-122">Diese Vorschau ist für Kunden verfügbar, die die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="ff2fa-122">This preview is enabled for customers who meet these requirements:</span></span> 

- <span data-ttu-id="ff2fa-123">Ihre Organisation muss über mindestens 5000 Lizenzen für eines oder eine Kombination dieser Produkte verfügen: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-123">Your organization needs to have a license count of at least 5,000, from one or a combination of these products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> 

  <span data-ttu-id="ff2fa-124">So kann Ihre Organisation beispielsweise über 3000 Office 365 E3-Lizenzen und 2500 Microsoft 365 E5-Lizenzen verfügen, die insgesamt 5500 Lizenzen für berechtigende Produkte ergeben.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-124">For example, your organization can have 3,000 Office 365 E3 licenses and 2,500 Microsoft 365 E5, for a total of 5,500 licenses from the qualifying products.</span></span>

- <span data-ttu-id="ff2fa-125">Ihre Organisation muss über mindestens 50 monatlich aktive Exchange Online-Benutzer verfügen.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-125">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

<span data-ttu-id="ff2fa-126">Mithilfe der Exchange Online-Überwachung können Sie den Status der folgenden E-Mail-Clients basierend auf den E-Mail-Leseaktivitäten anzeigen:</span><span class="sxs-lookup"><span data-stu-id="ff2fa-126">With Exchange Online monitoring you can view the health for the following email clients based on email read activity:</span></span>

- <span data-ttu-id="ff2fa-127">Outlook Desktop</span><span class="sxs-lookup"><span data-stu-id="ff2fa-127">Outlook Desktop</span></span>
- <span data-ttu-id="ff2fa-128">Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="ff2fa-128">Outlook on the Web</span></span>
- <span data-ttu-id="ff2fa-129">Native E-Mail-Clients von iOS und Android</span><span class="sxs-lookup"><span data-stu-id="ff2fa-129">Native mail clients of iOS and Android</span></span> 
- <span data-ttu-id="ff2fa-130">Mobile Outlook-App in iOS und Android</span><span class="sxs-lookup"><span data-stu-id="ff2fa-130">Outlook Mobile app in iOS and Android</span></span> 
- <span data-ttu-id="ff2fa-131">Outlook-Mac-Client</span><span class="sxs-lookup"><span data-stu-id="ff2fa-131">Outlook Mac client</span></span>

<span data-ttu-id="ff2fa-132">Für diese Clients können Sie die Anzahl der aktiven Benutzer in den letzten 30 Minuten anzeigen, basierend auf den Benutzern, die eine E-Mail gelesen haben, sowie die Anzahl der Vorfälle und Empfehlungen im Dashboard.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-132">For these clients, you can see the number of active users in the last 30 minutes based on users reading an email, along with number of incidents and advisories in the dashboard.</span></span> <span data-ttu-id="ff2fa-133">Diese Daten werden mit jenen desselben Intervalls für die vorherige Woche verglichen, um festzustellen, ob ein Problem vorliegt.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-133">This data is compared to the same interval for the previous week to see if there’s an issue.</span></span> 

>[!Note]
> <span data-ttu-id="ff2fa-134">Die Anzahl der aktiven Benutzer wird anhand einer einzelnen Aktivität wie beispielsweise das Lesen einer E-Mail erfasst.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-134">Active user count is measured by a single activity, for example, when a user reads an email.</span></span> <span data-ttu-id="ff2fa-135">Dabei werden nur die letzten 30 Minuten der Aktivität berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-135">It only accounts for the last 30 minutes of activity.</span></span>
>

<span data-ttu-id="ff2fa-136">Sie können den Exchange Online-Status auch für die folgenden Szenarien überwachen:</span><span class="sxs-lookup"><span data-stu-id="ff2fa-136">You can also monitor Exchange Online health for the following scenarios:</span></span>

- <span data-ttu-id="ff2fa-137">**E-Mail-Fluss**: die Anzahl der Nachrichten, die nach dem Erreichen des Microsoft 365-Netzwerks ohne Verzögerungen an ein Postfach übermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-137">**Mail flow**: The number of messages successfully delivered to a mailbox without any delay after the message reached the Microsoft 365 network.</span></span> 
- <span data-ttu-id="ff2fa-138">**Standardauthentifizierung und moderne Authentifizierung**: die Anzahl der Benutzer, die im Exchange Online-Dienst erfolgreich überprüft wurden.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-138">**Basic Authentication and Modern Authentication**: The number of users successfully validated in the Exchange Online service.</span></span>

![Beispiel für die Überwachung des Exchange-Status im Hinblick auf die E-Mail-Zustellung](../media/microsoft-365-exchange-monitoring/exhange-monitoring-scenario-example.png)

<span data-ttu-id="ff2fa-140">Die Schlüsselzahlen im Hauptdashboard zu all diesen Szenarien beziehen auf die letzten 30 Minuten.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-140">For all these scenarios, the key numbers are for the last 30 minutes in the main dashboard.</span></span> <span data-ttu-id="ff2fa-141">In detaillierten Ansichten für jedes dieser Szenarien wird der Beinah-Echtzeit-Trend für sieben Tage mit den aggregierten 30-Minuten-Daten im Vergleich zur vorherigen Woche angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-141">Detailed views for each of these scenarios shows the near real-time trend for seven days with the 30-minute aggregate compared with the previous week.</span></span> 

## <a name="send-us-feedback"></a><span data-ttu-id="ff2fa-142">Senden Sie uns Ihr Feedback</span><span class="sxs-lookup"><span data-stu-id="ff2fa-142">Send us feedback</span></span>

<span data-ttu-id="ff2fa-143">Es gibt zwei Möglichkeiten, Feedback zu senden:</span><span class="sxs-lookup"><span data-stu-id="ff2fa-143">There are two ways you can provide feedback:</span></span>

- <span data-ttu-id="ff2fa-144">Verwenden Sie die **Feedback**-Option, die auf allen Seiten des Microsoft 365 Admin Centers verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-144">Use the **Give feedback** option available on every page of the Microsoft 365 admin center.</span></span>
- <span data-ttu-id="ff2fa-145">Übermitteln Sie Ihr Feedback über den Link **Ist dieser Beitrag hilfreich?** zu einem bestimmten Vorfall oder einer bestimmten Empfehlung.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-145">Submit feedback using the **Is this post helpful?** link for a specific incident or advisory.</span></span>

![Der Link "Ist dieser Beitrag hilfreich?"](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example-incident-feedback.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="ff2fa-148">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="ff2fa-148">Frequently asked questions</span></span>

#### <a name="1-why-dont-i-see-exchange-online-monitoring-under-health-in-the-microsoft-365-admin-center"></a><span data-ttu-id="ff2fa-149">1. Warum wird die "Exchange Online-Überwachung" im Microsoft 365 Admin Center im Bereich "Integrität" nicht angezeigt?</span><span class="sxs-lookup"><span data-stu-id="ff2fa-149">1. Why don’t I see “Exchange Online monitoring” under Health in the Microsoft 365 admin center?</span></span> 

<span data-ttu-id="ff2fa-150">Vergewissern Sie sich zunächst, dass Sie das neue Admin Center auf der **Startseite** des Microsoft 365 Admin Centers aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-150">First, make sure you’ve enabled the new admin center on the **Home** page of the Microsoft 365 admin center.</span></span> 

<span data-ttu-id="ff2fa-151">Stellen Sie dann sicher, dass Sie die beiden folgenden Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="ff2fa-151">Then make sure you meet both of the following requirements:</span></span> 

- <span data-ttu-id="ff2fa-152">Ihre Organisation muss über mindestens 5000 Lizenzen für eines oder eine Kombination dieser Produkte verfügen: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-152">Your organization needs to have a license count of at least 5,000, from one or a combination of these products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> 
- <span data-ttu-id="ff2fa-153">Ihre Organisation muss über mindestens 50 monatlich aktive Exchange Online-Benutzer verfügen.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-153">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

<span data-ttu-id="ff2fa-154">Wenn die Anzahl der Lizenzen für Ihre Organisation unter 5000 Benutzern liegt und die monatlich aktiven Benutzer weniger als 50 sind, wird die Exchange Online-Überwachung erst aktiviert, wenn diese Voraussetzungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-154">If the license count for your organization goes below 5,000 users and the monthly active users goes below 50 users, Exchange Online monitoring won’t be enabled until these requirements are met.</span></span>

#### <a name="2-the-active-user-count-in-the-dashboard-for-each-client-appears-to-be-low-we-have-a-lot-of-active-licenses-assigned-to-users-what-does-this-mean"></a><span data-ttu-id="ff2fa-155">2. Die Anzahl der im Dashboard für jeden Client angezeigten aktiven Benutzer scheint niedrig zu sein.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-155">2. The active user count in the dashboard for each client appears to be low.</span></span> <span data-ttu-id="ff2fa-156">Wir verfügen über viele Benutzern zugewiesene aktive Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-156">We have a lot of active licenses assigned to users.</span></span> <span data-ttu-id="ff2fa-157">Was bedeutet dies?</span><span class="sxs-lookup"><span data-stu-id="ff2fa-157">What does this mean?</span></span> 

<span data-ttu-id="ff2fa-158">Die in der Überwachung angezeigte Anzahl aktiver Benutzer basiert auf einem 30-Minuten-Fenster, in dem die Benutzer die im Feature angegebene Aktivität ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-158">The active user count shown in monitoring is based on a 30-minute window where users have performed the activity called out in the feature.</span></span> <span data-ttu-id="ff2fa-159">Dies sollte nicht mit Nutzungswerten verwechselt werden.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-159">This shouldn’t be confused with usage numbers.</span></span> <span data-ttu-id="ff2fa-160">Verwenden Sie zum Anzeigen von Nutzungswerten Aktivitätsberichte im Microsoft 365 Admin Center (**Berichte > Nutzung**).</span><span class="sxs-lookup"><span data-stu-id="ff2fa-160">To view usage numbers, use activity reports in the Microsoft 365 admin center (**Reports > Usage**).</span></span>

#### <a name="3-will-there-be-other-monitoring-scenarios-for-other-services-such-as-teams-and-sharepoint"></a><span data-ttu-id="ff2fa-161">3. Wird es andere Überwachungsszenarien für andere Dienste wie Microsoft Teams und SharePoint geben?</span><span class="sxs-lookup"><span data-stu-id="ff2fa-161">3. Will there be other monitoring scenarios for other services such as Teams and SharePoint?</span></span> 

<span data-ttu-id="ff2fa-162">Dieses Feature wird von Microsoft direkt in das Dashboard "Dienststatus" im Microsoft 365 Admin Center integriert.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-162">Microsoft is integrating this experience directly inside the Service Health dashboard in the Microsoft 365 admin center.</span></span> <span data-ttu-id="ff2fa-163">Auf diese Weise kann Microsoft Überwachungsszenarien für andere Dienste erweitern. Wenn es so weit ist, wird eine entsprechende Mitteilung erfolgen.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-163">This will provide opportunities for Microsoft to extend monitoring scenarios for other services, which will be announced when there is news to share.</span></span> 

#### <a name="4-what-is-the-plan-for-general-availability-of-this-experience"></a><span data-ttu-id="ff2fa-164">4. Was sind die Absichten im Hinblick auf eine allgemeine Verfügbarkeit dieser Lösung?</span><span class="sxs-lookup"><span data-stu-id="ff2fa-164">4. What is the plan for general availability of this experience?</span></span> 

<span data-ttu-id="ff2fa-165">Microsoft hat die Exchange Online-Überwachung direkt in das Dashboard **Dienststatus** im Microsoft 365 Admin Center integriert.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-165">Microsoft has integrated Exchange Online monitoring directly on the **Service Health** dashboard in the Microsoft 365 admin center.</span></span> 

<span data-ttu-id="ff2fa-166">Microsoft möchte Ihr Feedback zu dieser neuen integrierten Lösung sammeln und anschließend Entscheidungen hinsichtlich einer allgemeinen Verfügbarkeit treffen.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-166">With this new integrated experience, Microsoft's plan is to collect your feedback and then define our plan for general availability.</span></span>

#### <a name="5-is-this-a-free-included-or-paid-extra-feature"></a><span data-ttu-id="ff2fa-167">5. Handelt es sich um ein kostenloses (inbegriffenes) oder ein kostenpflichtiges (zusätzliches) Feature?</span><span class="sxs-lookup"><span data-stu-id="ff2fa-167">5. Is this a free (included) or paid (extra) feature?</span></span> 

<span data-ttu-id="ff2fa-168">Dieses Feature befindet sich in der öffentlichen Vorschau und ist nur für Kunden verfügbar, die die in Frage 1 aufgeführten Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-168">This feature is in Public preview and only available for customers that meet the requirements in question 1.</span></span>

<!--
>[!Note]
>INTERNAL: That decision is pending
>
--> 

#### <a name="6-how-do-i-provide-feedback"></a><span data-ttu-id="ff2fa-169">6. Wie kann ich Feedback geben?</span><span class="sxs-lookup"><span data-stu-id="ff2fa-169">6. How do I provide feedback?</span></span> 

<span data-ttu-id="ff2fa-170">Verwenden Sie für allgemeines Feedback das **Feedback**-Symbol in der unteren rechten Ecke auf der **Exchange Online**-Überwachungsseite.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-170">For general feedback, use the **Give feedback** icon on the bottom-right corner of the **Exchange Online** monitoring page.</span></span> 

<span data-ttu-id="ff2fa-171">Wenn Sie Feedback zu Vorfällen oder Empfehlungen geben möchten, verwenden Sie den Link **Ist dieser Beitrag hilfreich?**.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-171">For feedback on incidents or advisories, use the **Is this post helpful?** link.</span></span>

#### <a name="7-where-is-the-data-instrumented-for-the-scenarios-that-show-activity-trends"></a><span data-ttu-id="ff2fa-172">7. Wo werden die Daten für die Szenarien instrumentiert, die Aktivitätstrends aufweisen?</span><span class="sxs-lookup"><span data-stu-id="ff2fa-172">7. Where is the data instrumented for the scenarios that show activity trends?</span></span>

<span data-ttu-id="ff2fa-p114">Die Daten werden im Exchange Online-Dienst instrumentiert. Wenn ein Fehler auftritt, bevor die Anforderung Exchange Online erreicht, oder wenn in Exchange Online ein Fehler auftritt, wird das Aktivitätssignal zurückgehen.</span><span class="sxs-lookup"><span data-stu-id="ff2fa-p114">The data is instrumented in the Exchange Online service. If there is a failure that happens before the request reaches Exchange Online or there is a failure in Exchange Online, you will see a drop in the activity signal.</span></span>

