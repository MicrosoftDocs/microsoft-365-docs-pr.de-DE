---
title: Hinzufügen von Administrator Kontakten im Microsoft Managed Desktop Admin Portal
description: Teilen Sie uns mit, wer für jeden Fokusbereich kontaktiert werden soll.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 014404ab38ff5871289be186dec150115c3be6ec
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277538"
---
# <a name="add-admin-contacts-in-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="85ba9-104">Hinzufügen von Administrator Kontakten im Microsoft Managed Desktop Admin Portal</span><span class="sxs-lookup"><span data-stu-id="85ba9-104">Add Admin contacts in Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="85ba9-105">Es gibt mehrere Möglichkeiten, wie Microsoft Managed Desktop Service mit Kunden kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="85ba9-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="85ba9-106">Um die Kommunikation zu rationalisieren und sicherzustellen, dass wir die besten Kontakte überprüfen, müssen Sie eine Reihe von Administrator Kontakten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="85ba9-106">To streamline communication and ensure we’re checking with the best contacts, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="85ba9-107">Microsoft Managed Desktop IT-Vorgänge wenden sich an diese Personen, um Hilfe bei der Problembehandlung für Ihren Mandanten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="85ba9-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span> 

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="85ba9-108">Azure Active Directory-Zugriff für Microsoft Managed Desktop-Verwaltungsportal</span><span class="sxs-lookup"><span data-stu-id="85ba9-108">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="85ba9-109">Microsoft Managed Desktop Admin Portal erfordert, dass Personen, die auf das Portal zugreifen, über eine dieser Azure Active Directory-Rollen (AD) verfügen:</span><span class="sxs-lookup"><span data-stu-id="85ba9-109">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="85ba9-110">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="85ba9-110">Global Administrator</span></span>
- <span data-ttu-id="85ba9-111">InTune-Dienst Administrator</span><span class="sxs-lookup"><span data-stu-id="85ba9-111">Intune Service Administrator</span></span>
- <span data-ttu-id="85ba9-112">Rechnungs Administrator</span><span class="sxs-lookup"><span data-stu-id="85ba9-112">Billing Administrator</span></span>
- <span data-ttu-id="85ba9-113">Dienst Administrator</span><span class="sxs-lookup"><span data-stu-id="85ba9-113">Service Support Administrator</span></span>

<span data-ttu-id="85ba9-114">Der globale Administrator muss derjenige sein, der den Kunden in Microsoft Managed Desktop registriert.</span><span class="sxs-lookup"><span data-stu-id="85ba9-114">The Global Administrator must be the one to enroll the customer in Microsoft Managed Desktop.</span></span>  <span data-ttu-id="85ba9-115">Alle fünf Rollen haben den gleichen Zugriff innerhalb des Verwaltungsportals, um Aufgaben zu initiieren und anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="85ba9-115">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span>  <span data-ttu-id="85ba9-116">Weitere Informationen zum Zuweisen dieser Rollen in Azure AD finden Sie unter [Administrator Role Permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="85ba9-116">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-focus-areas"></a><span data-ttu-id="85ba9-117">Fokusbereiche für den admin-Kontakt</span><span class="sxs-lookup"><span data-stu-id="85ba9-117">Admin contact focus areas</span></span>

<span data-ttu-id="85ba9-118">Administrator Kontakte sollten die beste Person oder Gruppe sein, die Fragen beantworten und Entscheidungen für unterschiedliche Fokusbereiche treffen kann.</span><span class="sxs-lookup"><span data-stu-id="85ba9-118">Admin contacts should be the best person or group that can answer questions and make decisions for different focus areas.</span></span>  <span data-ttu-id="85ba9-119">Microsoft Managed Desktop Operations wendet sich an diese Administrator Kontakte für Fragen im Zusammenhang mit Supportanfragen des Kunden.</span><span class="sxs-lookup"><span data-stu-id="85ba9-119">Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.</span></span>  <span data-ttu-id="85ba9-120">Diese Administrator Kontakte erhalten Benachrichtigungen für Updates für Supportanfragen und neue Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="85ba9-120">These Admin contacts will receive notifications for support request updates and new messages.</span></span>  <span data-ttu-id="85ba9-121">Hierzu gehört Folgendes:</span><span class="sxs-lookup"><span data-stu-id="85ba9-121">These areas include:</span></span>

<span data-ttu-id="85ba9-122">Fokusbereich</span><span class="sxs-lookup"><span data-stu-id="85ba9-122">Focus area</span></span> | <span data-ttu-id="85ba9-123">Fragen zu</span><span class="sxs-lookup"><span data-stu-id="85ba9-123">For questions about</span></span>
--- | ---
<span data-ttu-id="85ba9-124">Apps</span><span class="sxs-lookup"><span data-stu-id="85ba9-124">Apps</span></span> | <span data-ttu-id="85ba9-125">Problembehandlung bei App-Verpackungen</span><span class="sxs-lookup"><span data-stu-id="85ba9-125">Troubleshooting App Packaging</span></span>
<span data-ttu-id="85ba9-126">Geräte</span><span class="sxs-lookup"><span data-stu-id="85ba9-126">Devices</span></span> | <span data-ttu-id="85ba9-127">Geräte Integrität, Problembehandlung mit Microsoft Managed Desktop-Geräten</span><span class="sxs-lookup"><span data-stu-id="85ba9-127">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="85ba9-128">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="85ba9-128">Security</span></span> | <span data-ttu-id="85ba9-129">Behandeln von Sicherheitsproblemen mit Microsoft Managed Desktop-Geräten</span><span class="sxs-lookup"><span data-stu-id="85ba9-129">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="85ba9-130">Andere</span><span class="sxs-lookup"><span data-stu-id="85ba9-130">Other</span></span> | <span data-ttu-id="85ba9-131">Für Probleme, die nicht durch andere Bereiche abgedeckt werden</span><span class="sxs-lookup"><span data-stu-id="85ba9-131">For issues not covered by other areas</span></span>

<span data-ttu-id="85ba9-132">Wer immer Sie für diese Kontakte auswählen, muss über das Wissen und die Autorität verfügen, um Entscheidungen für Ihre Microsoft Managed Desktop-Umgebung treffen zu können.</span><span class="sxs-lookup"><span data-stu-id="85ba9-132">Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.</span></span> <span data-ttu-id="85ba9-133">Wenn Sie Ihre Microsoft Managed Desktop-Umgebung Onboarding, werden Sie aufgefordert, Kontakte für Ihren lokalen Helpdesk und die Sicherheit hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="85ba9-133">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="85ba9-134">Administrator Kontakte sind erforderlich, wenn Sie [eine Support Anfrage übermitteln](../working-with-managed-desktop/support.md).</span><span class="sxs-lookup"><span data-stu-id="85ba9-134">Admin contacts are required when you [submit a Support request](../working-with-managed-desktop/support.md).</span></span> <span data-ttu-id="85ba9-135">Sie benötigen einen Administratorkontakt für den Fokusbereich der Support Anfrage.</span><span class="sxs-lookup"><span data-stu-id="85ba9-135">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="85ba9-136">**So fügen Sie Administrator Kontakte hinzu**</span><span class="sxs-lookup"><span data-stu-id="85ba9-136">**To add admin contacts**</span></span>

1.  <span data-ttu-id="85ba9-137">Melden Sie sich beim [Microsoft Managed Desktop Admin Portal](http://aka.ms/mwaasportal)an.</span><span class="sxs-lookup"><span data-stu-id="85ba9-137">Sign in to [Microsoft Managed Desktop admin portal](http://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="85ba9-138">Wählen Sie unter **Support**die Option **Administrator Kontakte**aus.</span><span class="sxs-lookup"><span data-stu-id="85ba9-138">Under **Support**, select **Admin contacts**.</span></span> 

    ![Support Menü, Administrator Kontakte](images/admincontacts.png)

3. <span data-ttu-id="85ba9-140">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="85ba9-140">Select **Add**.</span></span>

    ![Schaltfläche "Admin Portal hinzufügen"](images/adminadd.png)

4.  <span data-ttu-id="85ba9-142">Wählen Sie einen **Fokusbereich** aus, und geben Sie die Informationen für den Kontakt ein.</span><span class="sxs-lookup"><span data-stu-id="85ba9-142">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![die Liste der Fokusbereiche](images/areaoffocus.png)

5. <span data-ttu-id="85ba9-144">Wiederholen Sie diese Schritte für jeden Fokusbereich.</span><span class="sxs-lookup"><span data-stu-id="85ba9-144">Repeat for each area of focus.</span></span> 

