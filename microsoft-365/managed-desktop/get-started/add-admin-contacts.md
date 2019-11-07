---
title: Hinzufügen und Überprüfen von Administrator Kontakten im Administratorportal
description: Teilen Sie uns mit, an wen Sie sich für jeden Bereich des Fokus wenden müssen.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 3f77a5f6f0af83ea82d2ab3cea0798b95e27c2d2
ms.sourcegitcommit: 3d37043c0447359c952dc99026c219dd69f6fb8d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/06/2019
ms.locfileid: "38012066"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="a2b5c-104">Hinzufügen und Überprüfen von Administrator Kontakten im Administratorportal</span><span class="sxs-lookup"><span data-stu-id="a2b5c-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="a2b5c-105">Es gibt mehrere Möglichkeiten, wie Microsoft Managed Desktop Service mit Kunden kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="a2b5c-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="a2b5c-106">Um die Kommunikation zu rationalisieren und sicherzustellen, dass die richtigen Personen überprüft werden, müssen Sie eine Reihe von Administrator Kontakten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a2b5c-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="a2b5c-107">Microsoft Managed Desktop-IT-Vorgänge wenden sich an diese Personen, um Hilfe bei der Problembehandlung für Ihren Mandanten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a2b5c-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a2b5c-108">Möglicherweise haben Sie diese Kontakte bereits im Administratorportal hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a2b5c-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="a2b5c-109">Wenn dies der Fall ist, überprüfen Sie jetzt, ob die Kontaktliste korrekt ist, da Microsoft Managed Desktop Sie bei einem schweren Vorfall **erreichen kann.**</span><span class="sxs-lookup"><span data-stu-id="a2b5c-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="a2b5c-110">Azure Active Directory Access für das Verwaltungsportal von Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="a2b5c-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="a2b5c-111">Microsoft Managed Desktop Admin Portal erfordert, dass Personen, die auf das Portal zugreifen, über eine dieser Azure Active Directory (AD)-Rollen verfügen:</span><span class="sxs-lookup"><span data-stu-id="a2b5c-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="a2b5c-112">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="a2b5c-112">Global Administrator</span></span>
- <span data-ttu-id="a2b5c-113">InTune-Dienst Administrator</span><span class="sxs-lookup"><span data-stu-id="a2b5c-113">Intune Service Administrator</span></span>
- <span data-ttu-id="a2b5c-114">Abrechnungs Administrator</span><span class="sxs-lookup"><span data-stu-id="a2b5c-114">Billing Administrator</span></span>
- <span data-ttu-id="a2b5c-115">Dienst Support Administrator</span><span class="sxs-lookup"><span data-stu-id="a2b5c-115">Service Support Administrator</span></span>

<span data-ttu-id="a2b5c-116">Der globale Administrator muss der einzige sein, der Ihre Organisation in Microsoft Managed Desktop registriert.</span><span class="sxs-lookup"><span data-stu-id="a2b5c-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="a2b5c-117">Alle fünf Rollen haben im Administratorportal denselben Zugriff, um Aufgaben zu initiieren und anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a2b5c-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="a2b5c-118">Weitere Informationen zum Zuweisen dieser Rollen in Azure AD finden Sie unter [Administrator Role Permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="a2b5c-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="a2b5c-119">Administrative Kontaktbereiche des Fokus</span><span class="sxs-lookup"><span data-stu-id="a2b5c-119">Admin contact areas of focus</span></span>

<span data-ttu-id="a2b5c-120">Administrator Kontakte sollten die beste Person oder Gruppe sein, die Fragen beantworten und Entscheidungen für unterschiedliche Fokusbereiche treffen kann.</span><span class="sxs-lookup"><span data-stu-id="a2b5c-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="a2b5c-121">**Bei Microsoft Managed Desktop Operations werden diese Administrator Kontakte für Fragen im Zusammenhang mit Supportanfragen, die vom Kunden eingereicht wurden, kontaktiert.**</span><span class="sxs-lookup"><span data-stu-id="a2b5c-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="a2b5c-122">Diese Administrator Kontakte erhalten Benachrichtigungen für Updates für Supportanfragen und neue Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="a2b5c-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="a2b5c-123">Diese Bereiche umfassen:</span><span class="sxs-lookup"><span data-stu-id="a2b5c-123">These areas include:</span></span>

<span data-ttu-id="a2b5c-124">Fokusbereich</span><span class="sxs-lookup"><span data-stu-id="a2b5c-124">Area of focus</span></span> | <span data-ttu-id="a2b5c-125">Fragen zu</span><span class="sxs-lookup"><span data-stu-id="a2b5c-125">For questions about</span></span>
--- | ---
<span data-ttu-id="a2b5c-126">App-Verpackung</span><span class="sxs-lookup"><span data-stu-id="a2b5c-126">App packaging</span></span> | <span data-ttu-id="a2b5c-127">Problembehandlung bei App-Verpackungen</span><span class="sxs-lookup"><span data-stu-id="a2b5c-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="a2b5c-128">Geräte</span><span class="sxs-lookup"><span data-stu-id="a2b5c-128">Devices</span></span> | <span data-ttu-id="a2b5c-129">Geräte Integrität, Problembehandlung mit Microsoft Managed Desktop-Geräten</span><span class="sxs-lookup"><span data-stu-id="a2b5c-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="a2b5c-130">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="a2b5c-130">Security</span></span> | <span data-ttu-id="a2b5c-131">Beheben von Sicherheitsproblemen mit Microsoft Managed Desktop-Geräten</span><span class="sxs-lookup"><span data-stu-id="a2b5c-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="a2b5c-132">IT-Helpdesk</span><span class="sxs-lookup"><span data-stu-id="a2b5c-132">IT help desk</span></span> | <span data-ttu-id="a2b5c-133">in Fällen, in denen unser Supportmitarbeiter Karten für Endbenutzer außerhalb der Microsoft Managed Desktop-Support Bereiche übergibt</span><span class="sxs-lookup"><span data-stu-id="a2b5c-133">in cases where our Support staff hands over end-user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="a2b5c-134">Andere</span><span class="sxs-lookup"><span data-stu-id="a2b5c-134">Other</span></span> | <span data-ttu-id="a2b5c-135">Für Probleme, die nicht von anderen Bereichen abgedeckt werden</span><span class="sxs-lookup"><span data-stu-id="a2b5c-135">For issues not covered by other areas</span></span>

<span data-ttu-id="a2b5c-136">**Wer auch immer Sie für diese Kontakte ausgewählt haben, muss über das Wissen und die Autorität verfügen, um Entscheidungen für Ihre von Microsoft verwaltete Desktop Umgebung zu treffen.**</span><span class="sxs-lookup"><span data-stu-id="a2b5c-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="a2b5c-137">Wenn Sie Ihre Microsoft Managed Desktop-Umgebung an Bord haben, werden Sie aufgefordert, Kontakte für den lokalen Helpdesk und die Sicherheit hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a2b5c-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="a2b5c-138">Administrator Kontakte sind erforderlich, wenn Sie [eine Support Anfrage übermitteln](../working-with-managed-desktop/support.md).</span><span class="sxs-lookup"><span data-stu-id="a2b5c-138">Admin contacts are required when you [submit a Support request](../working-with-managed-desktop/support.md).</span></span> <span data-ttu-id="a2b5c-139">Sie benötigen einen Administratorkontakt für den Fokusbereich der Support Anfrage.</span><span class="sxs-lookup"><span data-stu-id="a2b5c-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="a2b5c-140">**So fügen Sie Administrator Kontakte hinzu**</span><span class="sxs-lookup"><span data-stu-id="a2b5c-140">**To add admin contacts**</span></span>

1.  <span data-ttu-id="a2b5c-141">Melden Sie sich beim [Microsoft Managed Desktop-Verwaltungsportal](https://aka.ms/mwaasportal)an.</span><span class="sxs-lookup"><span data-stu-id="a2b5c-141">Sign in to [Microsoft Managed Desktop admin portal](https://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="a2b5c-142">Wählen Sie unter **Support**die Option **Administrator Kontakte**aus.</span><span class="sxs-lookup"><span data-stu-id="a2b5c-142">Under **Support**, select **Admin contacts**.</span></span> 

    ![Support Menü, Administrator Kontakte](images/admincontacts.png)

3. <span data-ttu-id="a2b5c-144">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a2b5c-144">Select **Add**.</span></span>

    ![Schaltfläche "Admin-Portal hinzufügen"](images/adminadd.png)

4.  <span data-ttu-id="a2b5c-146">Wählen Sie einen **Fokusbereich** aus, und geben Sie die Informationen für den Kontakt ein.</span><span class="sxs-lookup"><span data-stu-id="a2b5c-146">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![die Liste der Fokusbereiche](images/areaoffocus.png)

5. <span data-ttu-id="a2b5c-148">Wiederholen Sie diese Schritte für jeden Bereich des Fokus.</span><span class="sxs-lookup"><span data-stu-id="a2b5c-148">Repeat for each area of focus.</span></span> 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="a2b5c-149">Schritte zum Einstieg in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="a2b5c-149">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="a2b5c-150">Hinzufügen und Überprüfen von Administrator Kontakten im Administratorportal (in diesem Thema)</span><span class="sxs-lookup"><span data-stu-id="a2b5c-150">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="a2b5c-151">Anpassen des bedingten Zugriffs</span><span class="sxs-lookup"><span data-stu-id="a2b5c-151">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="a2b5c-152">Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="a2b5c-152">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="a2b5c-153">Installieren des InTune-Unternehmensportals auf auf Geräten</span><span class="sxs-lookup"><span data-stu-id="a2b5c-153">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="a2b5c-154">Aktivieren des Enterprise-Status-Roaming</span><span class="sxs-lookup"><span data-stu-id="a2b5c-154">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="a2b5c-155">Einrichten von Microsoft Managed Desktop-Geräten</span><span class="sxs-lookup"><span data-stu-id="a2b5c-155">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="a2b5c-156">Vorbereiten Ihrer Benutzer für die Verwendung von Geräten</span><span class="sxs-lookup"><span data-stu-id="a2b5c-156">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="a2b5c-157">Bereitstellen von apps auf Geräten</span><span class="sxs-lookup"><span data-stu-id="a2b5c-157">Deploy apps to devices</span></span>](deploy-apps.md)