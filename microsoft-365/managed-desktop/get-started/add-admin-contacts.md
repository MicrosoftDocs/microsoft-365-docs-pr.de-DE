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
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="063f7-104">Hinzufügen und Überprüfen von Administrator-Kontakten im Administratorportal</span><span class="sxs-lookup"><span data-stu-id="063f7-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="063f7-105">Es gibt verschiedene Möglichkeiten, Microsoft Managed Desktop Dienst mit Kunden kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="063f7-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="063f7-106">Um die Kommunikation zu optimieren und sicherzustellen, dass wir mit den richtigen Personen suchen, müssen Sie eine Reihe von Administratorkontakten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="063f7-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="063f7-107">Microsoft Managed Desktop IT-Vorgänge wenden sich an diese Personen, um Unterstützung bei der Problembehandlung für Ihren Mandanten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="063f7-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="063f7-108">Möglicherweise haben Sie diese Kontakte bereits im Administratorportal hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="063f7-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="063f7-109">Wenn ja, nehmen Sie sich jetzt einen Moment Zeit, um zu  überprüfen, ob die Kontaktliste richtig ist, da Microsoft Managed Desktop in der Lage sein muss, sie zu erreichen, wenn ein schwerwiegender Vorfall auftritt.</span><span class="sxs-lookup"><span data-stu-id="063f7-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="063f7-110">Azure Active Directory für Microsoft Managed Desktop Administratorportal</span><span class="sxs-lookup"><span data-stu-id="063f7-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="063f7-111">Microsoft Managed Desktop Das Administratorportal erfordert, dass Personen, die auf das Portal zugreifen, über eine der folgenden Azure Active Directory (AD) verfügen:</span><span class="sxs-lookup"><span data-stu-id="063f7-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="063f7-112">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="063f7-112">Global Administrator</span></span>
- <span data-ttu-id="063f7-113">Intune-Dienstadministrator</span><span class="sxs-lookup"><span data-stu-id="063f7-113">Intune Service Administrator</span></span>
- <span data-ttu-id="063f7-114">Globaler Leser</span><span class="sxs-lookup"><span data-stu-id="063f7-114">Global Reader</span></span>
- <span data-ttu-id="063f7-115">Dienstunterstützungsadministrator</span><span class="sxs-lookup"><span data-stu-id="063f7-115">Service Support Administrator</span></span>

<span data-ttu-id="063f7-116">Der globale Administrator muss der Benutzer sein, der Ihre Organisation bei der Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="063f7-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="063f7-117">Alle fünf Rollen verfügen über denselben Zugriff innerhalb des Administratorportals zum Initiieren und Anzeigen von Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="063f7-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="063f7-118">Weitere Informationen zum Zuweisen dieser Rollen in Azure AD finden Sie unter [Administratorrollenberechtigungen in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="063f7-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="063f7-119">Fokusbereiche für Administratorkontakte</span><span class="sxs-lookup"><span data-stu-id="063f7-119">Admin contact areas of focus</span></span>

<span data-ttu-id="063f7-120">Administratorkontakte sollten die beste Person oder Gruppe sein, die Fragen beantworten und Entscheidungen für verschiedene Schwerpunktbereiche treffen kann.</span><span class="sxs-lookup"><span data-stu-id="063f7-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="063f7-121">**Microsoft Managed Desktop Die Vorgänge wenden sich an diese Administratorkontakte für Fragen im Zusammenhang mit Supportanfragen, die vom Kunden gestellt wurden.**</span><span class="sxs-lookup"><span data-stu-id="063f7-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="063f7-122">Diese Administratorkontakte erhalten Benachrichtigungen für Supportanforderungsupdates und neue Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="063f7-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="063f7-123">Zu diesen Bereichen gehören:</span><span class="sxs-lookup"><span data-stu-id="063f7-123">These areas include:</span></span>

<span data-ttu-id="063f7-124">Fokusbereich</span><span class="sxs-lookup"><span data-stu-id="063f7-124">Area of focus</span></span> | <span data-ttu-id="063f7-125">Für Fragen zu</span><span class="sxs-lookup"><span data-stu-id="063f7-125">For questions about</span></span>
--- | ---
<span data-ttu-id="063f7-126">App-Verpackung</span><span class="sxs-lookup"><span data-stu-id="063f7-126">App packaging</span></span> | <span data-ttu-id="063f7-127">Problembehandlung beim Packen von Apps</span><span class="sxs-lookup"><span data-stu-id="063f7-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="063f7-128">Geräte</span><span class="sxs-lookup"><span data-stu-id="063f7-128">Devices</span></span> | <span data-ttu-id="063f7-129">Geräteinte health, Problembehandlung bei Microsoft Managed Desktop Geräten</span><span class="sxs-lookup"><span data-stu-id="063f7-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="063f7-130">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="063f7-130">Security</span></span> | <span data-ttu-id="063f7-131">Problembehandlung bei Sicherheitsproblemen mit Microsoft Managed Desktop Geräten</span><span class="sxs-lookup"><span data-stu-id="063f7-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="063f7-132">IT-Helpdesk</span><span class="sxs-lookup"><span data-stu-id="063f7-132">IT help desk</span></span> | <span data-ttu-id="063f7-133">in Fällen, in denen unsere Supportmitarbeiter Benutzertickets außerhalb der Microsoft Managed Desktop aushändigen</span><span class="sxs-lookup"><span data-stu-id="063f7-133">in cases where our Support staff hands over user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="063f7-134">Andere</span><span class="sxs-lookup"><span data-stu-id="063f7-134">Other</span></span> | <span data-ttu-id="063f7-135">Bei Problemen, die nicht von anderen Bereichen abgedeckt werden</span><span class="sxs-lookup"><span data-stu-id="063f7-135">For issues not covered by other areas</span></span>

<span data-ttu-id="063f7-136">**Wer auch immer Sie für diese Kontakte auswählen, muss über das Wissen und die Autorität verfügen, um Entscheidungen für Ihre Umgebung Microsoft Managed Desktop treffen.**</span><span class="sxs-lookup"><span data-stu-id="063f7-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="063f7-137">Wenn Sie Ihre Microsoft Managed Desktop integrieren, werden Sie aufgefordert, Kontakte für Ihren lokalen Helpdesk und Die Sicherheit hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="063f7-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="063f7-138">Administratorkontakte sind erforderlich, wenn [Sie eine Supportanfrage übermitteln.](../service-description/support.md)</span><span class="sxs-lookup"><span data-stu-id="063f7-138">Admin contacts are required when you [submit a Support request](../service-description/support.md).</span></span> <span data-ttu-id="063f7-139">Sie benötigen einen Administratorkontakt für den Fokusbereich der Supportanfrage.</span><span class="sxs-lookup"><span data-stu-id="063f7-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="063f7-140">**So fügen Sie Administratorkontakte hinzu**</span><span class="sxs-lookup"><span data-stu-id="063f7-140">**To add admin contacts**</span></span>

1.  <span data-ttu-id="063f7-141">Melden Sie sich bei [Microsoft Managed Desktop Administratorportal an.](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="063f7-141">Sign in to [Microsoft Managed Desktop admin portal](https://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="063f7-142">Wählen **Sie unter Support** die Option **Administratorkontakte aus.**</span><span class="sxs-lookup"><span data-stu-id="063f7-142">Under **Support**, select **Admin contacts**.</span></span> 

    ![Supportmenü, Administratorkontakte in der Nähe der oberen auswahl](../../media/admincontacts.png)

3. <span data-ttu-id="063f7-144">Wählen Sie **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="063f7-144">Select **Add**.</span></span>

    ![Administratorportal, Schaltfläche Hinzufügen links von Export and Refresh](../../media/adminadd.png)

4.  <span data-ttu-id="063f7-146">Wählen Sie **einen Fokusbereich aus,** und geben Sie die Informationen für den Kontakt ein.</span><span class="sxs-lookup"><span data-stu-id="063f7-146">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![die Liste der Schwerpunktbereiche, z. B. Other, Apps und Sicherheit](../../media/areaoffocus.png)

5. <span data-ttu-id="063f7-148">Wiederholen Sie dies für jeden Fokusbereich.</span><span class="sxs-lookup"><span data-stu-id="063f7-148">Repeat for each area of focus.</span></span> 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="063f7-149">Schritte zum Einstieg in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="063f7-149">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="063f7-150">Hinzufügen und Überprüfen von Administratorkontakten im Administratorportal (in diesem Thema)</span><span class="sxs-lookup"><span data-stu-id="063f7-150">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="063f7-151">Bedingten Zugriff anpassen</span><span class="sxs-lookup"><span data-stu-id="063f7-151">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="063f7-152">Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="063f7-152">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="063f7-153">Installieren des Intune Company Portals auf Geräten</span><span class="sxs-lookup"><span data-stu-id="063f7-153">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="063f7-154">Aktivieren von Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="063f7-154">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="063f7-155">Richten Sie Microsoft Managed Desktop-Geräte ein</span><span class="sxs-lookup"><span data-stu-id="063f7-155">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="063f7-156">Vorbereiten Ihrer Benutzer für die Verwendung von Geräten</span><span class="sxs-lookup"><span data-stu-id="063f7-156">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="063f7-157">Stellen Sie Anwendungen auf Geräten bereit</span><span class="sxs-lookup"><span data-stu-id="063f7-157">Deploy apps to devices</span></span>](deploy-apps.md)