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
ms.openlocfilehash: 362fb37b352a77aea07b899b707dbf4ac3d440d5
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198751"
---
<!--06/21/2019-->

# <a name="safe-links-in-teams"></a><span data-ttu-id="10597-104">Sichere Links in Teams</span><span class="sxs-lookup"><span data-stu-id="10597-104">Safe Links in Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> <span data-ttu-id="10597-105">Dieses Feature befindet sich in der **öffentlichen Vorschau** für Kunden im Microsoft Teams Technology Adoption Program (Tap) zum 28. Februar 2020.</span><span class="sxs-lookup"><span data-stu-id="10597-105">This feature is in **Public Preview** for customers in the Microsoft Teams Technology Adoption Program (TAP) as of Feb 28, 2020.</span></span> <span data-ttu-id="10597-106">Dieser Hinweis wird aus dem Artikel entfernt, wenn sichere Links für Teams häufiger verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="10597-106">This note will be removed from the article when Safe Links for Teams is more widely available.</span></span>

<span data-ttu-id="10597-107">Microsoft Teams, eine in Microsoft cloudbasierten Anwendung zur Verwaltung ihrer Arbeit, verwendet bereits sichere Anlagen (für Office 365), hat aber jetzt Zugriff auf sichere Links zum Zeitpunkt des Klickens.</span><span class="sxs-lookup"><span data-stu-id="10597-107">Microsoft Teams, a Microsoft cloud-based application for managing your work, already uses Safe Attachments (for Office 365), but it will now have access to Safe Links at the time of your click.</span></span> <span data-ttu-id="10597-108">Unabhängig davon, ob Sie Chats, Gruppenchats, Kanäle oder Registerkarten verwenden, wenn Sie über ein Abonnement für Office 365 ATP verfügen, können Sie diese Sicherheitsmaßnahme aktivieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="10597-108">Whether you're using Chats, Group Chats, Channels, or Tabs, if you have a subscription to Office 365 ATP, you will have the ability to enable and use this safety measure.</span></span> <span data-ttu-id="10597-109">Weitere Informationen zu den Lizenzierungsanforderungen finden Sie unter [Microsoft 365-Dienste auf Mandantenebene – Leitfaden zur Lizenzierung](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="10597-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="10597-110">So funktioniert es:</span><span class="sxs-lookup"><span data-stu-id="10597-110">Here's how it works:</span></span>

1. <span data-ttu-id="10597-111">Wenn Sie die Teams-Anwendung starten, überprüft Microsoft 365, um sicherzustellen, dass der Benutzer zu einer Organisation gehört, die über Office 365 ATP verfügt, und dass der Benutzer Teil einer aktiven Richtlinie für sichere Links ist, deren Schutz für Microsoft Teams aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="10597-111">When you start the Teams application, Microsoft 365 will check to make sure the user belongs to an organization that has Office 365 ATP, and that the user is part of an active safe links policy with its protection enabled for Microsoft Teams.</span></span>

2. <span data-ttu-id="10597-112">Wenn dies der Fall ist, werden URLs zum Zeitpunkt der Klickfunktion in Chats, Gruppenchats, Kanälen und Registerkarten für diesen Benutzer überprüft.</span><span class="sxs-lookup"><span data-stu-id="10597-112">If the above are true, then URLs will be validated at the time of click in Chats, Group Chats, Channels, and in Tabs for that user.</span></span>

## <a name="what-will-users-experience"></a><span data-ttu-id="10597-113">Was werden Benutzer erfahren?</span><span class="sxs-lookup"><span data-stu-id="10597-113">What will users experience?</span></span>

<span data-ttu-id="10597-114">Für alle geschützten Benutzer wird diese Erfahrung mit gefährlichen URLs verwendet:</span><span class="sxs-lookup"><span data-stu-id="10597-114">All protected users will have this experience with hazardous URLs:</span></span>

- <span data-ttu-id="10597-115">Wenn auf den Link aus einer Microsoft Teams-Unterhaltung, einem Gruppenchat oder aus Kanälen geklickt wurde, wird eine Seite im Standardbrowser gerendert.</span><span class="sxs-lookup"><span data-stu-id="10597-115">If the link was clicked from a Teams conversation, group chat, or from channels, a page will render in the default browser.</span></span> <span data-ttu-id="10597-116">Wenn auf der Registerkarte angeheftet auf den Link geklickt wurde, wird die Seite auf der Benutzeroberfläche von Teams auf dieser Registerkarte angezeigt, und die Option zum Öffnen im Browser wird aus Sicherheitsgründen deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="10597-116">If the link was clicked from a pinned tab, the page will appear in the Teams GUI within that tab, and the option to open in browser will be disabled for security purposes.</span></span>

- <span data-ttu-id="10597-117">Dieser Benutzer wird vom Fortfahren mit der URL-Website blockiert.</span><span class="sxs-lookup"><span data-stu-id="10597-117">This user will be blocked from proceeding to the URL's site.</span></span>

<span data-ttu-id="10597-118">Wenn der Benutzer, der den Link gesendet hat, nicht durch Office 365 ATP geschützt ist, kann er auf die URL auf seinem Computer klicken und die Problem Website beheben.</span><span class="sxs-lookup"><span data-stu-id="10597-118">If the user who sent the link isn't protected by Office 365 ATP, he or she is free to click the URL on his or her machine and resolve the problem site.</span></span> <span data-ttu-id="10597-119">Auf diese Weise ist es für Administratoren doppelt wichtig, sich darüber bewusst zu sein, wer Ihre geschützten Benutzer sind und sein sollten.</span><span class="sxs-lookup"><span data-stu-id="10597-119">This makes it doubly important for administrators to be aware of who their protected users are and should be.</span></span>

![Eine sichere Links für Teams-Seite, die einen bösartigen Link meldet und die Übertragung auf die Seite blockiert.](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

<span data-ttu-id="10597-121">Wenn Sie auf dieser Seite in Microsoft Teams auf die Schaltfläche " *zurück* " klicken, wird diese geschlossen (oder es kann zu einer leeren Seite führen, wenn Benutzer schließen können).</span><span class="sxs-lookup"><span data-stu-id="10597-121">Clicking the *Go Back* button on this page in Teams will close it out (or may result in a blank page users  can close out).</span></span> <span data-ttu-id="10597-122">Durch Klicken auf den Link wird jedoch erneut die Zuverlässigkeit der Website bewertet, sodass diese Seite wieder angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="10597-122">However, clicking on the link again will result in reassessment of the reputation of the site so that this page reappears.</span></span>

> [!NOTE]
> <span data-ttu-id="10597-123">Einige Microsoft 365-Administratoren aktivieren die Meldung **Continue Anyway** auf der Seite blockieren.</span><span class="sxs-lookup"><span data-stu-id="10597-123">Some Microsoft 365 admins will enable the **Continue Anyway** message on the blocking page.</span></span> <span data-ttu-id="10597-124">Wenn jedoch sichere Links den Ruf einer Website misst und diese nicht mehr zur Verfügung stehen, sollte keine weitere durch Klick erfolgen.</span><span class="sxs-lookup"><span data-stu-id="10597-124">However, if Safe Links measures the reputation of a site and finds it lacking, no further click-through should be undertaken.</span></span> <span data-ttu-id="10597-125">Es wird nicht empfohlen, dass Benutzer Sicherheitsmaßnahmen umgehen.</span><span class="sxs-lookup"><span data-stu-id="10597-125">It is not recommended that users bypass safety measures.</span></span> <span data-ttu-id="10597-126">Wägen Sie dies bitte auf ihre Überlegungen ab, bevor Sie Continue trotzdem aktivieren.</span><span class="sxs-lookup"><span data-stu-id="10597-126">Please weigh this into your considerations before enabling Continue Anyway.</span></span>
