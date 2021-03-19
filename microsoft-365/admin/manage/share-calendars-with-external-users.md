---
title: Freigeben von Kalendern für externe Benutzer
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: Erfahren Sie, wie Sie Ihre Benutzer ihre Kalender für Besprechungen und Termine mit externen Benutzern gemeinsam nutzen lassen können.
ms.openlocfilehash: 8204dc025f843953af13cba58fa0cf2e4d76de45
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760054"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="cda3d-103">Freigeben von Kalendern für externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="cda3d-103">Share calendars with external users</span></span>

<span data-ttu-id="cda3d-104">Manchmal ist es notwendig, dass Ihre Benutzer Besprechungen mit Personen außerhalb Ihres Unternehmens planen.</span><span class="sxs-lookup"><span data-stu-id="cda3d-104">It's sometimes necessary for your users to schedule meetings with people outside your organization.</span></span> <span data-ttu-id="cda3d-105">Um die Suche nach gemeinsamen Besprechungszeiten zu vereinfachen, können Sie in Microsoft 365 diesen Personen Kalender zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="cda3d-105">To simplify the process of finding common meeting times, Microsoft 365 enables you to make calendars available to these people.</span></span> <span data-ttu-id="cda3d-106">Dies sind Personen, die freie und gebuchte Zeiten für Benutzer in Ihrer Organisation sehen müssen, aber keine Benutzerkonten für Ihre Microsoft 365-Organisation haben.</span><span class="sxs-lookup"><span data-stu-id="cda3d-106">These are people who need to see free and busy times for users in your organization, but don't have user accounts for your Microsoft 365 organization.</span></span>

<span data-ttu-id="cda3d-107">Sie können die Kalenderfreigabe für alle Benutzer in Ihrer Organisation im Microsoft 365 Admin Center aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cda3d-107">You can enable calendar sharing for all users in your organization in the Microsoft 365 admin center.</span></span> <span data-ttu-id="cda3d-108">Sobald die Freigabe aktiviert ist, können Ihre Benutzer die Outlook Web App verwenden, um ihre Kalender für jeden innerhalb oder außerhalb der Organisation freizugeben.</span><span class="sxs-lookup"><span data-stu-id="cda3d-108">Once sharing is enabled, your users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="cda3d-109">Personen innerhalb der Organisation können den gemeinsamen Kalender zusammen mit ihrem eigenen Kalender anzeigen.</span><span class="sxs-lookup"><span data-stu-id="cda3d-109">People inside the organization can view the shared calendar along with their own calendar.</span></span> <span data-ttu-id="cda3d-110">Personen außerhalb der Organisation wird eine URL gesendet, mit der sie den Kalender anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="cda3d-110">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="cda3d-111">Die Benutzer in Ihrer Organisation entscheiden, wann und wie viel sie freigeben möchten.</span><span class="sxs-lookup"><span data-stu-id="cda3d-111">Users in your organization decide when to share and how much to share.</span></span>

> [!NOTE]
> <span data-ttu-id="cda3d-112">Wenn Sie Kalender für eine Organisation freigeben möchten, die Exchange Server 2013 (eine lokale Lösung) verwendet, muss der Exchange-Administrator eine Authentifizierungsbeziehung mit der Cloud einrichten.</span><span class="sxs-lookup"><span data-stu-id="cda3d-112">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud.</span></span> <span data-ttu-id="cda3d-113">Dies wird als Partnerverbund bezeichnet und muss Mindestanforderungen an die Software erfüllen.</span><span class="sxs-lookup"><span data-stu-id="cda3d-113">This is known as federation, and must meet minimum software requirements.</span></span> <span data-ttu-id="cda3d-114">Weitere Informationen finden Sie unter [Freigabe](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="cda3d-114">See [Sharing](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) for more information.</span></span>
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="cda3d-115">Aktivieren Sie die Kalenderfreigabe über das Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="cda3d-115">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="cda3d-116">Gehen Sie im Admin Center auf **Einstellungen** \> **Org-Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="cda3d-116">In the admin center, go to **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="cda3d-117">Wählen Sie auf der Registerkarte **Dienste** die Option **Kalender**.</span><span class="sxs-lookup"><span data-stu-id="cda3d-117">On the **Services** tab, select **Calendar**.</span></span>
  
3. <span data-ttu-id="cda3d-118">Wählen Sie auf der Seite **Kalender**, ob Sie es Benutzern ermöglichen möchten, ihre Kalender für Personen außerhalb Ihrer Organisation freizugeben, die Microsoft 365 oder Exchange haben.</span><span class="sxs-lookup"><span data-stu-id="cda3d-118">On the **Calendar** page, choose whether you want to let users share their calendars with people outside of your organization who have Microsoft 365 or Exchange.</span></span> <span data-ttu-id="cda3d-119">Wählen Sie, ob Sie anonymen Benutzern (Benutzern ohne Anmeldeinformationen) den Zugriff auf Kalender über eine E-Mail-Einladung erlauben wollen.</span><span class="sxs-lookup"><span data-stu-id="cda3d-119">Choose whether you want to allow anonymous users (users without credentials) to access calendars via an email invitation.</span></span>

4. <span data-ttu-id="cda3d-120">Wählen Sie, welche Art von Kalenderinformationen den Benutzern zur Verfügung gestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cda3d-120">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="cda3d-121">Sie können alle Informationen zulassen oder sie nur auf die Zeit oder nur auf Zeit, Betreff und Ort beschränken.</span><span class="sxs-lookup"><span data-stu-id="cda3d-121">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="cda3d-122">Personen zum Zugreifen auf Kalender einladen</span><span class="sxs-lookup"><span data-stu-id="cda3d-122">Invite people to access calendars</span></span>

<span data-ttu-id="cda3d-123">Sobald die Freigabe aktiviert ist, können Kalenderbesitzer Einladungen an bestimmte Benutzer aussprechen.</span><span class="sxs-lookup"><span data-stu-id="cda3d-123">Once sharing is enabled, calendar owners can extend invitations to specific users.</span></span> <span data-ttu-id="cda3d-124">Anweisungen finden Sie unter [Freigabe Ihres Kalenders in Outlook-Webanwendung](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5).</span><span class="sxs-lookup"><span data-stu-id="cda3d-124">See [Sharing your calendar in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5) for instructions.</span></span>