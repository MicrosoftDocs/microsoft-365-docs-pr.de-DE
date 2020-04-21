---
title: Freigeben von Kalendern für externe Benutzer
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: 'Erfahren Sie, wie Sie Ihren Benutzern die Freigabe Ihrer Kalender mit externen Benutzern für Besprechungen und Termine ermöglichen können. '
ms.openlocfilehash: bd297fc2d684357d0500495e5a8263e5279efa39
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628040"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="85bcc-103">Freigeben von Kalendern für externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="85bcc-103">Share calendars with external users</span></span>

<span data-ttu-id="85bcc-104">[] Es ist oft notwendig, Besprechungen mit Personen außerhalb Ihrer Organisation zu planen.</span><span class="sxs-lookup"><span data-stu-id="85bcc-104">It's often necessary to schedule meetings with people outside your organization.</span></span> <span data-ttu-id="85bcc-105">Um den Prozess der Suche nach gegenseitig annehmbaren Besprechungszeiten zu vereinfachen, ermöglicht Ihnen Microsoft 365 das Bereitstellen von Kalendern für "externe Benutzer", die Frei/Gebucht-Zeiten anzeigen müssen, aber keine Benutzerkonten für Ihre Microsoft 365-Umgebung haben.</span><span class="sxs-lookup"><span data-stu-id="85bcc-105">To simplify the process of finding mutually agreeable meeting times, Microsoft 365 enables you to make calendars available to "external users," those who need to see free/busy time but don't have user accounts for your Microsoft 365 environment.</span></span>
  
<span data-ttu-id="85bcc-106">Die Kalenderfreigabe ist eine globale Einstellung, was bedeutet, dass Sie Sie als Administrator für alle Benutzer im Mandanten aktivieren können.</span><span class="sxs-lookup"><span data-stu-id="85bcc-106">Calendar sharing is a global setting, meaning that you, the admin, can enable it for all users in the tenant.</span></span> <span data-ttu-id="85bcc-107">Nachdem die Freigabe aktiviert wurde, können Benutzer Outlook Web App verwenden, um ihre Kalender mit beliebigen Personen innerhalb oder außerhalb der Organisation zu teilen.</span><span class="sxs-lookup"><span data-stu-id="85bcc-107">Once sharing is enabled, users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="85bcc-108">Personen innerhalb der Organisation können freigegebene Kalender neben ihren eigenen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="85bcc-108">People inside the organization can view the shared calendar side-by-side with their own.</span></span> <span data-ttu-id="85bcc-109">An Personen außerhalb der Organisation wird eine URL gesendet, über die sie den Kalender anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="85bcc-109">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="85bcc-110">Die Benutzer entscheiden, wann sie teilen möchten, wie viel sie teilen möchten und wann sie ihre Kalender privat halten möchten.</span><span class="sxs-lookup"><span data-stu-id="85bcc-110">Users decide when to share, how much to share, and when to keep their calendars private.</span></span>
  
> [!NOTE]
> <span data-ttu-id="85bcc-p103">Wenn Sie Kalender für eine Organisation freigeben möchten, die Exchange Server 2013 (eine lokale Lösung) verwendet, muss der Exchange-Administrator eine Authentifizierungsbeziehung mit der Cloud einrichten. Dies wird als "Verbund" bezeichnet und muss die minimalen Softwareanforderungen erfüllen. Weitere Informationen finden Sie unter [Freigeben](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="85bcc-p103">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud. This is known as "federation" and must meet minimum software requirements. See [Sharing](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) for more information.</span></span> 
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="85bcc-114">Aktivieren der Kalenderfreigabe mit dem Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="85bcc-114">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="85bcc-115">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Dienste und Add-Ins</a>.</span><span class="sxs-lookup"><span data-stu-id="85bcc-115">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services & add-ins</a> page.</span></span> 
    
  
2. <span data-ttu-id="85bcc-116">Wählen Sie auf der Seite **Dienste &amp; -Add-ins** die Option **Kalender**aus.</span><span class="sxs-lookup"><span data-stu-id="85bcc-116">On the **Services &amp; add-ins** page, select **Calendar**.</span></span>
  
3. <span data-ttu-id="85bcc-117">Wählen Sie auf der daraufhin geöffneten **Kalender** Seite aus, ob Ihre Benutzer ihre Kalender für Personen außerhalb Ihrer Organisation freigeben möchten, die über Microsoft 365 oder Exchange verfügen.</span><span class="sxs-lookup"><span data-stu-id="85bcc-117">On the **Calendar** page that opens, choose whether you want to let your users share their calendars with people outside of your organization who have Microsoft 365 or Exchange.</span></span>
    
4. <span data-ttu-id="85bcc-118">Wählen Sie aus, ob Sie anonymen Benutzern (Benutzern ohne Anmeldeinformationen) den Zugriff auf Kalender über eine e-Mail-Einladung erlauben möchten.</span><span class="sxs-lookup"><span data-stu-id="85bcc-118">Choose whether you want to allow anonymous users (users without logon credentials) to access calendars via an email invitation.</span></span>

5. <span data-ttu-id="85bcc-119">Wählen Sie den Typ der Kalenderinformationen aus, die für Benutzer verfügbar gemacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="85bcc-119">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="85bcc-120">Sie können alle Informationen zulassen oder nur auf Zeit, Zeit, Betreff und Ort beschränken.</span><span class="sxs-lookup"><span data-stu-id="85bcc-120">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

    
## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="85bcc-121">Personen zum Zugreifen auf Kalender einladen</span><span class="sxs-lookup"><span data-stu-id="85bcc-121">Invite people to access calendars</span></span>

<span data-ttu-id="85bcc-p105">Nachdem die Freigabe für den Mandanten aktiviert wurde, können die Besitzer von Kalendern Einladungen an bestimmte Benutzer senden. Anweisungen finden Sie unter [Freigabe Ihres Kalenders in Outlook-Webanwendung](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5.aspx).</span><span class="sxs-lookup"><span data-stu-id="85bcc-p105">Once sharing is enabled for the tenant, calendar owners can extend invitations to specific users. See [Sharing your calendar in Outlook Web App](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5.aspx) for instructions.</span></span> 
  

