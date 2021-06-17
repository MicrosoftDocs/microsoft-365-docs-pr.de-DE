---
title: Hinzufügen und Überprüfen von Administrator-Kontakten im Administratorportal
description: Teilen Sie uns mit, wer für jeden Fokusbereich kontaktiert werden soll.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 65d7647e9000152d2eeb8d6bf36e8d45a0d4fa90
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984700"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="e571b-104">Hinzufügen und Überprüfen von Administrator-Kontakten im Administratorportal</span><span class="sxs-lookup"><span data-stu-id="e571b-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="e571b-105">Es gibt verschiedene Möglichkeiten, wie Microsoft Managed Desktop Dienst mit Kunden kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="e571b-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="e571b-106">Um die Kommunikation zu optimieren und sicherzustellen, dass wir die richtigen Personen überprüfen, müssen Sie eine Reihe von Administratorkontakten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e571b-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="e571b-107">Microsoft Managed Desktop IT-Vorgänge wenden sich an diese Personen, um Hilfe bei der Behandlung von Problemen für Ihren Mandanten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e571b-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e571b-108">Möglicherweise haben Sie diese Kontakte bereits im Verwaltungsportal hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e571b-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="e571b-109">Wenn dies der Fall ist, nehmen Sie sich einen Moment Zeit, um zu überprüfen, ob die Kontaktliste korrekt ist, da Microsoft Managed Desktop in der Lage sein **muss,** sie zu erreichen, wenn ein schwerwiegender Vorfall auftritt.</span><span class="sxs-lookup"><span data-stu-id="e571b-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="e571b-110">Azure Active Directory Zugriff für Microsoft Managed Desktop Verwaltungsportal</span><span class="sxs-lookup"><span data-stu-id="e571b-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="e571b-111">Microsoft Managed Desktop Das Verwaltungsportal erfordert, dass Personen, die auf das Portal zugreifen, über eine der folgenden Azure Active Directory (AD)-Rollen verfügen:</span><span class="sxs-lookup"><span data-stu-id="e571b-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="e571b-112">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="e571b-112">Global Administrator</span></span>
- <span data-ttu-id="e571b-113">Intune-Dienstadministrator</span><span class="sxs-lookup"><span data-stu-id="e571b-113">Intune Service Administrator</span></span>
- <span data-ttu-id="e571b-114">Globaler Leser</span><span class="sxs-lookup"><span data-stu-id="e571b-114">Global Reader</span></span>
- <span data-ttu-id="e571b-115">Dienstsupportadministrator</span><span class="sxs-lookup"><span data-stu-id="e571b-115">Service Support Administrator</span></span>

<span data-ttu-id="e571b-116">Der globale Administrator muss der Globale Administrator sein, der Ihre Organisation in Microsoft Managed Desktop registriert.</span><span class="sxs-lookup"><span data-stu-id="e571b-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="e571b-117">Alle fünf Rollen haben den gleichen Zugriff innerhalb des Verwaltungsportals, um Aufgaben zu initiieren und anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e571b-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="e571b-118">Weitere Informationen zum Zuweisen dieser Rollen in Azure AD finden Sie unter [Administratorrollenberechtigungen in Azure Active Directory.](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="e571b-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="e571b-119">Admin-Kontaktbereiche im Fokus</span><span class="sxs-lookup"><span data-stu-id="e571b-119">Admin contact areas of focus</span></span>

<span data-ttu-id="e571b-120">Administratorkontakte sollten die beste Person oder Gruppe sein, die Fragen beantworten und Entscheidungen für verschiedene Schwerpunktbereiche treffen kann.</span><span class="sxs-lookup"><span data-stu-id="e571b-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="e571b-121">**Microsoft Managed Desktop Vorgänge wenden sich an diese Administratorkontakte, um Fragen zu Supportanfragen zu erhalten, die vom Kunden eingereicht wurden.**</span><span class="sxs-lookup"><span data-stu-id="e571b-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="e571b-122">Diese Administratorkontakte erhalten Benachrichtigungen für Supportanfragen und neue Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="e571b-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="e571b-123">Zu diesen Bereichen gehören:</span><span class="sxs-lookup"><span data-stu-id="e571b-123">These areas include:</span></span>

<span data-ttu-id="e571b-124">Fokusbereich</span><span class="sxs-lookup"><span data-stu-id="e571b-124">Area of focus</span></span> | <span data-ttu-id="e571b-125">Für Fragen zu</span><span class="sxs-lookup"><span data-stu-id="e571b-125">For questions about</span></span>
--- | ---
<span data-ttu-id="e571b-126">App-Verpackung</span><span class="sxs-lookup"><span data-stu-id="e571b-126">App packaging</span></span> | <span data-ttu-id="e571b-127">Problembehandlung beim Packen von Apps</span><span class="sxs-lookup"><span data-stu-id="e571b-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="e571b-128">Geräte</span><span class="sxs-lookup"><span data-stu-id="e571b-128">Devices</span></span> | <span data-ttu-id="e571b-129">Geräteintegrität, Problembehandlung bei Microsoft Managed Desktop Geräten</span><span class="sxs-lookup"><span data-stu-id="e571b-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="e571b-130">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e571b-130">Security</span></span> | <span data-ttu-id="e571b-131">Behandeln von Sicherheitsproblemen mit Microsoft Managed Desktop Geräten</span><span class="sxs-lookup"><span data-stu-id="e571b-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="e571b-132">IT-Helpdesk</span><span class="sxs-lookup"><span data-stu-id="e571b-132">IT help desk</span></span> | <span data-ttu-id="e571b-133">in Fällen, in denen unsere Supportmitarbeiter Benutzertickets außerhalb von Microsoft Managed Desktop Supportbereichen übergeben</span><span class="sxs-lookup"><span data-stu-id="e571b-133">in cases where our Support staff hands over user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="e571b-134">Andere</span><span class="sxs-lookup"><span data-stu-id="e571b-134">Other</span></span> | <span data-ttu-id="e571b-135">Für Probleme, die nicht von anderen Bereichen abgedeckt werden</span><span class="sxs-lookup"><span data-stu-id="e571b-135">For issues not covered by other areas</span></span>

<span data-ttu-id="e571b-136">**Jeder, den Sie für diese Kontakte auswählen, muss über das Wissen und die Autorität verfügen, entscheidungen für Ihre Microsoft Managed Desktop Umgebung zu treffen.**</span><span class="sxs-lookup"><span data-stu-id="e571b-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="e571b-137">Wenn Sie Ihre Microsoft Managed Desktop Umgebung integrieren, werden Sie aufgefordert, Kontakte für Ihr lokales Helpdesk und Die Sicherheit hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e571b-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="e571b-138">Administratorkontakte sind erforderlich, wenn Sie [eine Supportanfrage senden.](../service-description/support.md)</span><span class="sxs-lookup"><span data-stu-id="e571b-138">Admin contacts are required when you [submit a Support request](../service-description/support.md).</span></span> <span data-ttu-id="e571b-139">Sie benötigen einen Administratorkontakt für den Fokusbereich der Supportanfrage.</span><span class="sxs-lookup"><span data-stu-id="e571b-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="e571b-140">**So fügen Sie Administratorkontakte hinzu**</span><span class="sxs-lookup"><span data-stu-id="e571b-140">**To add admin contacts**</span></span>

1.  <span data-ttu-id="e571b-141">Melden Sie sich bei [Microsoft Endpoint Manager](https://endpoint.microsoft.com)an.</span><span class="sxs-lookup"><span data-stu-id="e571b-141">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com).</span></span> 

2.  <span data-ttu-id="e571b-142">Suchen Sie unter **Mandantenverwaltung** nach dem **Abschnitt Microsoft Managed Desktop** und wählen Sie dann **Administratorkontakte** aus.</span><span class="sxs-lookup"><span data-stu-id="e571b-142">Under **Tenant administration**, look for the **Microsoft Managed Desktop** section then select **Admin contacts**.</span></span> 

3. <span data-ttu-id="e571b-143">Wählen Sie **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e571b-143">Select **Add**.</span></span>

4.  <span data-ttu-id="e571b-144">Wählen Sie einen **Fokusbereich aus,** und geben Sie die Informationen für den Kontakt ein.</span><span class="sxs-lookup"><span data-stu-id="e571b-144">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![die Liste der Schwerpunktbereiche, z. B. "Andere", "Apps" und "Sicherheit".](../../media/areaoffocus.png)

5. <span data-ttu-id="e571b-146">Wiederholen Sie dies für jeden Fokusbereich.</span><span class="sxs-lookup"><span data-stu-id="e571b-146">Repeat for each area of focus.</span></span> 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="e571b-147">Schritte für die ersten Schritte mit Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="e571b-147">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="e571b-148">Hinzufügen und Überprüfen von Administratorkontakten im Verwaltungsportal (dieses Thema)</span><span class="sxs-lookup"><span data-stu-id="e571b-148">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="e571b-149">Bedingten Zugriff anpassen</span><span class="sxs-lookup"><span data-stu-id="e571b-149">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="e571b-150">Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="e571b-150">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="e571b-151">Installieren des Intune Company Portals auf Geräten</span><span class="sxs-lookup"><span data-stu-id="e571b-151">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="e571b-152">Aktivieren von Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="e571b-152">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="e571b-153">Richten Sie Microsoft Managed Desktop-Geräte ein</span><span class="sxs-lookup"><span data-stu-id="e571b-153">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="e571b-154">Vorbereiten Ihrer Benutzer für die Verwendung von Geräten</span><span class="sxs-lookup"><span data-stu-id="e571b-154">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="e571b-155">Stellen Sie Anwendungen auf Geräten bereit</span><span class="sxs-lookup"><span data-stu-id="e571b-155">Deploy apps to devices</span></span>](deploy-apps.md)
