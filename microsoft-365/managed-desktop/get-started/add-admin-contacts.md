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
ms.openlocfilehash: 18823db8ca8d4bfa82b8ab6265ee8a0902a13e79
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925892"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="20c3e-104">Hinzufügen und Überprüfen von Administrator-Kontakten im Administratorportal</span><span class="sxs-lookup"><span data-stu-id="20c3e-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="20c3e-105">Es gibt verschiedene Möglichkeiten, wie der Microsoft Managed Desktop-Dienst mit Kunden kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="20c3e-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="20c3e-106">Um die Kommunikation zu optimieren und sicherzustellen, dass wir mit den richtigen Personen suchen, müssen Sie eine Reihe von Administratorkontakten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="20c3e-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="20c3e-107">Microsoft Managed Desktop IT Operations kontaktiert diese Personen, um Unterstützung bei der Problembehandlung für Ihren Mandanten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="20c3e-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="20c3e-108">Möglicherweise haben Sie diese Kontakte bereits im Administratorportal hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="20c3e-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="20c3e-109">Wenn ja, nehmen Sie sich jetzt einen Moment Zeit, um zu überprüfen, ob die Kontaktliste korrekt ist, da Microsoft Managed **Desktop** in der Lage sein muss, sie zu erreichen, wenn ein schwerwiegender Vorfall auftritt.</span><span class="sxs-lookup"><span data-stu-id="20c3e-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="20c3e-110">Azure Active Directory Access for Microsoft Managed Desktop Admin Portal</span><span class="sxs-lookup"><span data-stu-id="20c3e-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="20c3e-111">Für das Microsoft Managed Desktop Admin-Portal müssen Benutzer, die auf das Portal zugreifen, über eine der folgenden Azure Active Directory (AD)-Rollen verfügen:</span><span class="sxs-lookup"><span data-stu-id="20c3e-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="20c3e-112">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="20c3e-112">Global Administrator</span></span>
- <span data-ttu-id="20c3e-113">Intune-Dienstadministrator</span><span class="sxs-lookup"><span data-stu-id="20c3e-113">Intune Service Administrator</span></span>
- <span data-ttu-id="20c3e-114">Globaler Leser</span><span class="sxs-lookup"><span data-stu-id="20c3e-114">Global Reader</span></span>
- <span data-ttu-id="20c3e-115">Dienstunterstützungsadministrator</span><span class="sxs-lookup"><span data-stu-id="20c3e-115">Service Support Administrator</span></span>

<span data-ttu-id="20c3e-116">Der globale Administrator muss der Benutzer sein, der Ihre Organisation bei Microsoft Managed Desktop registriert.</span><span class="sxs-lookup"><span data-stu-id="20c3e-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="20c3e-117">Alle fünf Rollen verfügen über denselben Zugriff innerhalb des Administratorportals zum Initiieren und Anzeigen von Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="20c3e-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="20c3e-118">Weitere Informationen zum Zuweisen dieser Rollen in Azure AD finden Sie unter [Administratorrollenberechtigungen in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="20c3e-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="20c3e-119">Fokusbereiche für Administratorkontakte</span><span class="sxs-lookup"><span data-stu-id="20c3e-119">Admin contact areas of focus</span></span>

<span data-ttu-id="20c3e-120">Administratorkontakte sollten die beste Person oder Gruppe sein, die Fragen beantworten und Entscheidungen für verschiedene Schwerpunktbereiche treffen kann.</span><span class="sxs-lookup"><span data-stu-id="20c3e-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="20c3e-121">**Microsoft Managed Desktop Operations kontaktiert diese Administratorkontakte bei Fragen zu Supportanfragen, die vom Kunden gestellt wurden.**</span><span class="sxs-lookup"><span data-stu-id="20c3e-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="20c3e-122">Diese Administratorkontakte erhalten Benachrichtigungen für Supportanforderungsupdates und neue Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="20c3e-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="20c3e-123">Zu diesen Bereichen gehören:</span><span class="sxs-lookup"><span data-stu-id="20c3e-123">These areas include:</span></span>

<span data-ttu-id="20c3e-124">Fokusbereich</span><span class="sxs-lookup"><span data-stu-id="20c3e-124">Area of focus</span></span> | <span data-ttu-id="20c3e-125">Für Fragen zu</span><span class="sxs-lookup"><span data-stu-id="20c3e-125">For questions about</span></span>
--- | ---
<span data-ttu-id="20c3e-126">App-Verpackung</span><span class="sxs-lookup"><span data-stu-id="20c3e-126">App packaging</span></span> | <span data-ttu-id="20c3e-127">Problembehandlung beim Packen von Apps</span><span class="sxs-lookup"><span data-stu-id="20c3e-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="20c3e-128">Geräte</span><span class="sxs-lookup"><span data-stu-id="20c3e-128">Devices</span></span> | <span data-ttu-id="20c3e-129">Geräteinte health, Problembehandlung mit Microsoft Managed Desktop-Geräten</span><span class="sxs-lookup"><span data-stu-id="20c3e-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="20c3e-130">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="20c3e-130">Security</span></span> | <span data-ttu-id="20c3e-131">Problembehandlung bei Sicherheitsproblemen mit Microsoft Managed Desktop-Geräten</span><span class="sxs-lookup"><span data-stu-id="20c3e-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="20c3e-132">IT-Helpdesk</span><span class="sxs-lookup"><span data-stu-id="20c3e-132">IT help desk</span></span> | <span data-ttu-id="20c3e-133">In Fällen, in denen unsere Supportmitarbeiter Benutzertickets außerhalb von Microsoft Managed Desktop-Supportbereichen aushändigen</span><span class="sxs-lookup"><span data-stu-id="20c3e-133">in cases where our Support staff hands over user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="20c3e-134">Andere</span><span class="sxs-lookup"><span data-stu-id="20c3e-134">Other</span></span> | <span data-ttu-id="20c3e-135">Bei Problemen, die nicht von anderen Bereichen abgedeckt werden</span><span class="sxs-lookup"><span data-stu-id="20c3e-135">For issues not covered by other areas</span></span>

<span data-ttu-id="20c3e-136">**Wer immer Sie für diese Kontakte auswählen, muss über das Wissen und die Autorität verfügen, entscheidungen für Ihre Microsoft Managed Desktop-Umgebung zu treffen.**</span><span class="sxs-lookup"><span data-stu-id="20c3e-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="20c3e-137">Wenn Sie Ihre Microsoft Managed Desktop-Umgebung integrieren, werden Sie aufgefordert, Kontakte für Ihren lokalen Helpdesk und die Sicherheit hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="20c3e-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="20c3e-138">Administratorkontakte sind erforderlich, wenn [Sie eine Supportanfrage übermitteln.](../service-description/support.md)</span><span class="sxs-lookup"><span data-stu-id="20c3e-138">Admin contacts are required when you [submit a Support request](../service-description/support.md).</span></span> <span data-ttu-id="20c3e-139">Sie benötigen einen Administratorkontakt für den Fokusbereich der Supportanfrage.</span><span class="sxs-lookup"><span data-stu-id="20c3e-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="20c3e-140">**So fügen Sie Administratorkontakte hinzu**</span><span class="sxs-lookup"><span data-stu-id="20c3e-140">**To add admin contacts**</span></span>

1.  <span data-ttu-id="20c3e-141">Melden Sie sich beim [Microsoft Managed Desktop Admin Portal an.](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="20c3e-141">Sign in to [Microsoft Managed Desktop admin portal](https://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="20c3e-142">Wählen **Sie unter Support** die Option **Administratorkontakte aus.**</span><span class="sxs-lookup"><span data-stu-id="20c3e-142">Under **Support**, select **Admin contacts**.</span></span> 

    ![Supportmenü, Administratorkontakte in der Nähe der oberen auswahl](../../media/admincontacts.png)

3. <span data-ttu-id="20c3e-144">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="20c3e-144">Select **Add**.</span></span>

    ![Administratorportal, Schaltfläche Hinzufügen links von Export and Refresh](../../media/adminadd.png)

4.  <span data-ttu-id="20c3e-146">Wählen Sie **einen Fokusbereich aus,** und geben Sie die Informationen für den Kontakt ein.</span><span class="sxs-lookup"><span data-stu-id="20c3e-146">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![die Liste der Schwerpunktbereiche, z. B. Other, Apps und Sicherheit](../../media/areaoffocus.png)

5. <span data-ttu-id="20c3e-148">Wiederholen Sie dies für jeden Fokusbereich.</span><span class="sxs-lookup"><span data-stu-id="20c3e-148">Repeat for each area of focus.</span></span> 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="20c3e-149">Schritte zum Einstieg in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="20c3e-149">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="20c3e-150">Hinzufügen und Überprüfen von Administratorkontakten im Administratorportal (in diesem Thema)</span><span class="sxs-lookup"><span data-stu-id="20c3e-150">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="20c3e-151">Bedingten Zugriff anpassen</span><span class="sxs-lookup"><span data-stu-id="20c3e-151">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="20c3e-152">Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="20c3e-152">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="20c3e-153">Installieren des Intune Company Portals auf Geräten</span><span class="sxs-lookup"><span data-stu-id="20c3e-153">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="20c3e-154">Aktivieren von Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="20c3e-154">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="20c3e-155">Richten Sie Microsoft Managed Desktop-Geräte ein</span><span class="sxs-lookup"><span data-stu-id="20c3e-155">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="20c3e-156">Vorbereiten Ihrer Benutzer für die Verwendung von Geräten</span><span class="sxs-lookup"><span data-stu-id="20c3e-156">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="20c3e-157">Stellen Sie Anwendungen auf Geräten bereit</span><span class="sxs-lookup"><span data-stu-id="20c3e-157">Deploy apps to devices</span></span>](deploy-apps.md)