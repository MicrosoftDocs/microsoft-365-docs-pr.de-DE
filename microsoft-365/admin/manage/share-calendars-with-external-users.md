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
description: Erfahren Sie, wie Sie Ihren Benutzern die Freigabe Ihrer Kalender mit externen Benutzern für Besprechungen und Termine ermöglichen können.
ms.openlocfilehash: 8204dc025f843953af13cba58fa0cf2e4d76de45
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760054"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="ba1f8-103">Freigeben von Kalendern für externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="ba1f8-103">Share calendars with external users</span></span>

<span data-ttu-id="ba1f8-104">Manchmal ist es für Ihre Benutzer erforderlich, Besprechungen mit Personen außerhalb Ihrer Organisation zu planen.</span><span class="sxs-lookup"><span data-stu-id="ba1f8-104">It's sometimes necessary for your users to schedule meetings with people outside your organization.</span></span> <span data-ttu-id="ba1f8-105">Um den Prozess des Findens allgemeiner Besprechungszeiten zu vereinfachen, ermöglicht Ihnen Microsoft 365 das Bereitstellen von Kalendern für diese Personen.</span><span class="sxs-lookup"><span data-stu-id="ba1f8-105">To simplify the process of finding common meeting times, Microsoft 365 enables you to make calendars available to these people.</span></span> <span data-ttu-id="ba1f8-106">Dabei handelt es sich um Personen, die freie und beschäftigte Zeiten für Benutzer in Ihrer Organisation sehen müssen, aber keine Benutzerkonten für Ihre Microsoft 365-Organisation haben.</span><span class="sxs-lookup"><span data-stu-id="ba1f8-106">These are people who need to see free and busy times for users in your organization, but don't have user accounts for your Microsoft 365 organization.</span></span>

<span data-ttu-id="ba1f8-107">Sie können die Kalenderfreigabe für alle Benutzer in Ihrer Organisation im Microsoft 365 Admin Center aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ba1f8-107">You can enable calendar sharing for all users in your organization in the Microsoft 365 admin center.</span></span> <span data-ttu-id="ba1f8-108">Sobald die Freigabe aktiviert ist, können Ihre Benutzer Outlook Web App verwenden, um Ihre Kalender für Personen innerhalb oder außerhalb der Organisation freizugeben.</span><span class="sxs-lookup"><span data-stu-id="ba1f8-108">Once sharing is enabled, your users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="ba1f8-109">Personen innerhalb der Organisation können den freigegebenen Kalender zusammen mit Ihrem eigenen Kalender anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ba1f8-109">People inside the organization can view the shared calendar along with their own calendar.</span></span> <span data-ttu-id="ba1f8-110">An Personen außerhalb der Organisation wird eine URL gesendet, über die sie den Kalender anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="ba1f8-110">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="ba1f8-111">Benutzer in Ihrer Organisation entscheiden, wann Sie freigeben und wie viel Sie freigeben möchten.</span><span class="sxs-lookup"><span data-stu-id="ba1f8-111">Users in your organization decide when to share and how much to share.</span></span>

> [!NOTE]
> <span data-ttu-id="ba1f8-112">Wenn Sie Kalender für eine Organisation freigeben möchten, die Exchange Server 2013 (eine lokale Lösung) verwendet, muss der Exchange-Administrator eine Authentifizierungsbeziehung mit der Cloud einrichten.</span><span class="sxs-lookup"><span data-stu-id="ba1f8-112">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud.</span></span> <span data-ttu-id="ba1f8-113">Dies wird als Verbund bezeichnet und muss die minimalen Softwareanforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="ba1f8-113">This is known as federation, and must meet minimum software requirements.</span></span> <span data-ttu-id="ba1f8-114">Weitere Informationen finden Sie unter [Freigeben](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="ba1f8-114">See [Sharing](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) for more information.</span></span>
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="ba1f8-115">Aktivieren der Kalenderfreigabe mit dem Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="ba1f8-115">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="ba1f8-116">Navigieren Sie im Admin Center zu **Einstellungen** \> **org Settings**.</span><span class="sxs-lookup"><span data-stu-id="ba1f8-116">In the admin center, go to **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="ba1f8-117">Wählen Sie auf der Registerkarte **Dienste** die Option **Kalender** aus.</span><span class="sxs-lookup"><span data-stu-id="ba1f8-117">On the **Services** tab, select **Calendar**.</span></span>
  
3. <span data-ttu-id="ba1f8-118">Geben Sie auf der Seite **Kalender** an, ob Benutzer ihre Kalender für Personen außerhalb Ihrer Organisation freigeben möchten, die über Microsoft 365 oder Exchange verfügen.</span><span class="sxs-lookup"><span data-stu-id="ba1f8-118">On the **Calendar** page, choose whether you want to let users share their calendars with people outside of your organization who have Microsoft 365 or Exchange.</span></span> <span data-ttu-id="ba1f8-119">Wählen Sie aus, ob Sie anonymen Benutzern (Benutzern ohne Anmeldeinformationen) den Zugriff auf Kalender über eine e-Mail-Einladung erlauben möchten.</span><span class="sxs-lookup"><span data-stu-id="ba1f8-119">Choose whether you want to allow anonymous users (users without credentials) to access calendars via an email invitation.</span></span>

4. <span data-ttu-id="ba1f8-120">Wählen Sie den Typ der Kalenderinformationen aus, die für Benutzer verfügbar gemacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ba1f8-120">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="ba1f8-121">Sie können alle Informationen zulassen oder nur auf Zeit, Zeit, Betreff und Ort beschränken.</span><span class="sxs-lookup"><span data-stu-id="ba1f8-121">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="ba1f8-122">Personen zum Zugreifen auf Kalender einladen</span><span class="sxs-lookup"><span data-stu-id="ba1f8-122">Invite people to access calendars</span></span>

<span data-ttu-id="ba1f8-123">Sobald die Freigabe aktiviert ist, können Kalenderbesitzer Einladungen für bestimmte Benutzer erweitern.</span><span class="sxs-lookup"><span data-stu-id="ba1f8-123">Once sharing is enabled, calendar owners can extend invitations to specific users.</span></span> <span data-ttu-id="ba1f8-124">Anweisungen finden Sie unter [Freigabe Ihres Kalenders in Outlook-Webanwendung](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5).</span><span class="sxs-lookup"><span data-stu-id="ba1f8-124">See [Sharing your calendar in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5) for instructions.</span></span>