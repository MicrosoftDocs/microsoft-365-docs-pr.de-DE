---
title: ATP-sichere Links für Teams, safelinks, sichere Links, blockieren schädlicher Links, Office 365 ATP, sichere Links für Teams, Beenden von Benutzern beim Klicken auf ungültige Links, böswillige Links
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 02/28/2020
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Teams haben jetzt Zugriff auf sichere Links zum Zeitpunkt des Klickens. Unabhängig davon, ob Sie Chats mit 1-zu-1-Chats, zwischen Gruppen oder in Kanälen und Registerkarten verwenden, wenn Sie ein Abonnement für Office 365 ATP haben, haben Sie die Möglichkeit, dieses Sicherheitsfeature zu aktivieren und zu verwenden.
ms.openlocfilehash: 88fe9756188eb16a2347d3c0cd4a98b4003ff457
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635998"
---
<!--06/21/2019-->

# <a name="safe-links-in-teams"></a><span data-ttu-id="1be0a-104">Sichere Links in Teams</span><span class="sxs-lookup"><span data-stu-id="1be0a-104">Safe Links in Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1be0a-105">Dieses Feature befindet sich in der **öffentlichen Vorschau** für Kunden im Microsoft Teams Technology Adoption Program (Tap) zum 28. Februar 2020.</span><span class="sxs-lookup"><span data-stu-id="1be0a-105">This feature is in **Public Preview** for customers in the Microsoft Teams Technology Adoption Program (TAP) as of Feb 28, 2020.</span></span> <span data-ttu-id="1be0a-106">Dieser Hinweis wird aus dem Artikel entfernt, wenn sichere Links für Teams häufiger verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="1be0a-106">This note will be removed from the article when Safe Links for Teams is more widely available.</span></span>

<span data-ttu-id="1be0a-107">Microsoft Teams, eine in Microsoft cloudbasierten Anwendung zur Verwaltung ihrer Arbeit, verwendet bereits sichere Anlagen (für Office 365), hat aber jetzt Zugriff auf sichere Links zum Zeitpunkt des Klickens.</span><span class="sxs-lookup"><span data-stu-id="1be0a-107">Microsoft Teams, a Microsoft cloud-based application for managing your work, already uses safe attachments (for Office 365), but it will now have access to safe links at the time of your click.</span></span> <span data-ttu-id="1be0a-108">Unabhängig davon, ob Chats mit 1-zu-1-Chats, zwischen Gruppen oder in Kanälen und Registerkarten verwendet werden, wenn Sie ein Abonnement für Office 365 ATP haben, können Sie diese Sicherheitsmaßnahme aktivieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="1be0a-108">Whether you're using chats 1-on-1 Chats, between Groups, or in Channels, and Tabs, if you have a subscription to Office 365 ATP, you will have the ability to enable and use this safety measure.</span></span>

<span data-ttu-id="1be0a-109">So funktioniert es:</span><span class="sxs-lookup"><span data-stu-id="1be0a-109">Here's how it works:</span></span> 

1. <span data-ttu-id="1be0a-110">Wenn Sie die Teams-Anwendung starten, überprüft Microsoft 365, um sicherzustellen, dass der Benutzer zu einer Organisation gehört, die über Office 365 ATP verfügt, und dass der Benutzer Teil einer aktiven Richtlinie für sichere Links ist, deren Schutz für Microsoft Teams aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1be0a-110">When you start the Teams application, Microsoft 365 will check to make sure the user belongs to an organization that has Office 365 ATP, and that the user is part of an active safe links policy with its protection enabled for Microsoft Teams.</span></span>

2. <span data-ttu-id="1be0a-111">Wenn dies der Fall ist, werden URLs zum Zeitpunkt der Klickfunktion in Chats, Gruppenchats, Kanälen und Registerkarten für diesen Benutzer überprüft.</span><span class="sxs-lookup"><span data-stu-id="1be0a-111">If the above are true, then URLs will be validated at the time of click in Chats, Group Chats, Channels, and in Tabs for that user.</span></span>
 
## <a name="what-will-users-experience"></a><span data-ttu-id="1be0a-112">Was werden Benutzer erfahren?</span><span class="sxs-lookup"><span data-stu-id="1be0a-112">What will users experience?</span></span> 

<span data-ttu-id="1be0a-113">Für alle geschützten Benutzer wird diese Erfahrung mit gefährlichen URLs verwendet:</span><span class="sxs-lookup"><span data-stu-id="1be0a-113">All protected users will have this experience with hazardous URLs:</span></span> 

- <span data-ttu-id="1be0a-114">Wenn auf den Link aus einer Microsoft Teams-Unterhaltung, einem Gruppenchat oder aus Kanälen geklickt wurde, wird eine Seite im Standardbrowser gerendert.</span><span class="sxs-lookup"><span data-stu-id="1be0a-114">If the link was clicked from a Teams conversation, group chat, or from channels, a page will render in the default browser.</span></span> <span data-ttu-id="1be0a-115">Wenn auf der Registerkarte angeheftet auf den Link geklickt wurde, wird die Seite auf der Benutzeroberfläche von Teams auf dieser Registerkarte angezeigt, und die Option zum Öffnen im Browser wird aus Sicherheitsgründen deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="1be0a-115">If the link was clicked from a pinned tab, the page will appear in the Teams GUI within that tab, and the option to open in browser will be disabled for security purposes.</span></span>

- <span data-ttu-id="1be0a-116">Dieser Benutzer wird vom Fortfahren mit der URL-Website blockiert.</span><span class="sxs-lookup"><span data-stu-id="1be0a-116">This user will be blocked from proceeding to the URL's site.</span></span>

<span data-ttu-id="1be0a-117">Wenn der Benutzer, der den Link gesendet hat, nicht durch Office 365 ATP geschützt ist, kann er auf die URL auf seinem Computer klicken und die Problem Website beheben.</span><span class="sxs-lookup"><span data-stu-id="1be0a-117">If the user who sent the link isn't protected by Office 365 ATP, he or she is free to click the URL on his or her machine and resolve the problem site.</span></span> <span data-ttu-id="1be0a-118">Auf diese Weise ist es für Administratoren doppelt wichtig, sich darüber bewusst zu sein, wer Ihre geschützten Benutzer sind und sein sollten.</span><span class="sxs-lookup"><span data-stu-id="1be0a-118">This makes it doubly important for administrators to be aware of who their protected users are and should be.</span></span>

![Eine sichere Links für Teams-Seite, die einen bösartigen Link meldet und die Übertragung auf die Seite blockiert.](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

<span data-ttu-id="1be0a-120">Wenn Sie auf dieser Seite in Microsoft Teams auf die Schaltfläche " *zurück* " klicken, wird diese geschlossen (oder es kann zu einer leeren Seite führen, wenn Benutzer schließen können).</span><span class="sxs-lookup"><span data-stu-id="1be0a-120">Clicking the *Go Back* button on this page in Teams will close it out (or may result in a blank page users  can close out).</span></span> <span data-ttu-id="1be0a-121">Durch Klicken auf den Link wird jedoch erneut die Zuverlässigkeit der Website bewertet, sodass diese Seite wieder angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1be0a-121">However, clicking on the link again will result in reassessment of the reputation of the site so that this page reappears.</span></span>

> [!NOTE]
><span data-ttu-id="1be0a-122">Einige Microsoft 365-Administratoren aktivieren die Meldung **Continue Anyway** auf der Seite blockieren.</span><span class="sxs-lookup"><span data-stu-id="1be0a-122">Some Microsoft 365 admins will enable the **Continue Anyway** message on the blocking page.</span></span> <span data-ttu-id="1be0a-123">Wenn jedoch sichere Links den Ruf einer Website misst und diese nicht mehr zur Verfügung stehen, sollte keine weitere durch Klick erfolgen.</span><span class="sxs-lookup"><span data-stu-id="1be0a-123">However, if safe links measures the reputation of a site and finds it lacking, no further click-through should be undertaken.</span></span> <span data-ttu-id="1be0a-124">Es wird nicht empfohlen, dass Benutzer Sicherheitsmaßnahmen umgehen.</span><span class="sxs-lookup"><span data-stu-id="1be0a-124">It is not recommended that users bypass safety measures.</span></span> <span data-ttu-id="1be0a-125">Wägen Sie dies bitte auf ihre Überlegungen ab, bevor Sie Continue trotzdem aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1be0a-125">Please weigh this into your considerations before enabling Continue Anyway.</span></span> 

