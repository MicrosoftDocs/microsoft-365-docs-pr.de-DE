---
title: Automatisieren der Lizenzierung und Gruppe Mitgliedschaft für Ihre Umgebung für Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Konfigurieren von Arbeitsgruppen-Lizenzierung und dynamische Gruppenmitgliedschaft in Ihrer testumgebung Microsoft 365 Enterprise.
ms.openlocfilehash: 46d2f0ca063b387d1a4a51b4ea97bd5d60c03fe5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867947"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="aaacd-103">Automatisieren der Lizenzierung und Gruppe Mitgliedschaft für Ihre Umgebung für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="aaacd-103">Automate licensing and group membership for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="aaacd-p101">Arbeitsgruppen-Lizenzierung automatisch weist oder Lizenzen für ein Benutzerkonto basierend auf der Gruppenmitgliedschaft entfernt. Dynamische Gruppenmitgliedschaft hinzugefügt oder entfernt Mitglieder einer Gruppe basierend auf Benutzerkontoeigenschaften wie Abteilung oder jedes Land. Dieser Artikel führt Sie schrittweise durch eine Demonstration von sowohl in Ihrer testumgebung Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="aaacd-p101">Group-based licensing automatically assigns or removes licenses for a user account based on group membership. Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country. This article steps you through a demonstration of both in your Microsoft 365 Enterprise test environment.</span></span>

<span data-ttu-id="aaacd-107">Es gibt zwei Phasen Auto-Lizenzierung und dynamische Gruppenmitgliedschaft in Ihrer Microsoft 365 Enterprise-testumgebung einrichten:</span><span class="sxs-lookup"><span data-stu-id="aaacd-107">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="aaacd-108">Erstellen der testumgebung Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="aaacd-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="aaacd-109">Konfigurieren und Testen von dynamischen Gruppenmitgliedschaft und automatische Lizenzierung.</span><span class="sxs-lookup"><span data-stu-id="aaacd-109">Configure and test dynamic group membership and automatic licensing.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="aaacd-111">Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="aaacd-111">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="aaacd-112">Phase 1: Erstellen Sie Ihre Umgebung für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="aaacd-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="aaacd-113">Wenn Sie automatisierte Lizenzierung und Gruppenmitgliedschaft auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen in der [Lightweight Basiskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="aaacd-113">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="aaacd-114">Wenn Sie automatisierte Lizenzierung und Gruppenmitgliedschaft in einer simulierten Enterprise testen möchten, befolgen Sie die Anweisungen in [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="aaacd-114">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="aaacd-p102">Testen der automatisiert Lizenzierung und Gruppenmitgliedschaft erfordert keinen der simulierten Enterprise-testumgebung, einschließlich einer simulierten Intranet mit dem Internet verbunden und Directory-Synchronisierung für eine Windows Server Active Directory-Gesamtstruktur. Erfolgt hier als eine Option, damit Sie automatisierte Lizenzierung und Gruppenmitgliedschaft testen können, und probieren Sie es in einer Umgebung, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="aaacd-p102">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="aaacd-117">Phase 2: Konfigurieren und Testen von dynamischen Gruppenmitgliedschaft und automatische Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="aaacd-117">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="aaacd-118">Zuerst erstellen eine neue Gruppe "Sales" und eine dynamische Gruppenmitgliedschaft Regel hinzufügen, sodass Benutzerkonten mit der Abteilung, legen Sie auf dem Umsatz automatisch der Gruppe "Sales" hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="aaacd-118">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="aaacd-119">Verwenden eine private Instanz des Internetbrowsers, melden Sie sich bei Office 365-Portal unter [https://portal.office.com](https://portal.office.com) mit das globale Administratorkonto des Office 365 E5 Test-Abonnement.</span><span class="sxs-lookup"><span data-stu-id="aaacd-119">Using a private instance of your Internet browser, sign in to the Office 365 portal at [https://portal.office.com](https://portal.office.com) with the global administrator account of your Office 365 E5 trial subscription.</span></span>
2. <span data-ttu-id="aaacd-120">Wechseln Sie auf einer separaten Registerkarte Ihres Browsers zu der Azure-Portal unter [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="aaacd-120">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="aaacd-121">Klicken Sie im Azure-Portal auf **Azure Active Directory > Benutzer und Gruppen > Alle Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="aaacd-121">In the Azure portal, click **Azure Active Directory > Users and groups > All groups**.</span></span>
4. <span data-ttu-id="aaacd-122">Klicken Sie auf das Blade **alle Gruppen** auf **neue Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="aaacd-122">On the **All groups** blade, click **New group**.</span></span>
5. <span data-ttu-id="aaacd-123">Wählen Sie im **Gruppentyp** **Office 365**.</span><span class="sxs-lookup"><span data-stu-id="aaacd-123">In **Group type**, select **Office 365**.</span></span>
6. <span data-ttu-id="aaacd-124">Geben Sie im Feld **Gruppenname** **Sales**.</span><span class="sxs-lookup"><span data-stu-id="aaacd-124">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="aaacd-125">Wählen Sie unter **Typ der Mitgliedschaft** **dynamische Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="aaacd-125">In **Membership type**, select **Dynamic user** .</span></span>
8. <span data-ttu-id="aaacd-126">Klicken Sie auf **Dynamische Abfrage hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="aaacd-126">Click **Add dynamic query**.</span></span>
9. <span data-ttu-id="aaacd-127">Wählen Sie unter **Benutzer hinzufügen**die Option **Abteilung** aus.</span><span class="sxs-lookup"><span data-stu-id="aaacd-127">In **Add users where**, select **department**.</span></span>
10. <span data-ttu-id="aaacd-128">Wählen Sie im nächsten Feld **Gleich** aus.</span><span class="sxs-lookup"><span data-stu-id="aaacd-128">In the next field, select **Equals**.</span></span>
11. <span data-ttu-id="aaacd-129">Geben Sie in das nächste Feld **Sales**.</span><span class="sxs-lookup"><span data-stu-id="aaacd-129">In the next field, type **Sales**.</span></span>
12. <span data-ttu-id="aaacd-130">Klicken Sie auf **Abfrage hinzufügen**, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="aaacd-130">Click **Add query**, and then click **Create**.</span></span>
13. <span data-ttu-id="aaacd-131">Schließen Sie die **Gruppe** und **alle Gruppen Gruppen** Blade.</span><span class="sxs-lookup"><span data-stu-id="aaacd-131">Close the **Group** and **Groups-All groups** blades.</span></span>

<span data-ttu-id="aaacd-132">Im nächsten Schritt konfigurieren Sie die Gruppe "Sales", sodass Elemente automatisch, Office 365 E5 und Enterprise-Mobilität + Sicherheit E5 Lizenzen zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="aaacd-132">Next, you configure the Sales group so that members are automatically assigned Office 365 E5 and Enterprise Mobility + Security E5 licenses.</span></span>

1. <span data-ttu-id="aaacd-133">Klicken Sie in der **Übersicht über die** Blade für Azure Active Directory, auf **Lizenzen > alle Produkte**.</span><span class="sxs-lookup"><span data-stu-id="aaacd-133">On the **Overview** blade for Azure Active Directory, click **Licenses > All products**.</span></span>
2. <span data-ttu-id="aaacd-134">Wählen Sie in der Liste **Enterprise Mobility + Security E5** und **Office 365 Enterprise E5** aus, und klicken Sie dann auf **Zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="aaacd-134">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **Assign**.</span></span>
3. <span data-ttu-id="aaacd-135">Klicken Sie in der Blade **Lizenz zuweisen** auf **Benutzer und Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="aaacd-135">On the **Assign license** blade, click **Users and groups**.</span></span>
4. <span data-ttu-id="aaacd-136">Wählen Sie in der Liste der Gruppen die Gruppe " **Sales** " aus.</span><span class="sxs-lookup"><span data-stu-id="aaacd-136">In the list of groups, select the **Sales** group.</span></span>
5. <span data-ttu-id="aaacd-137">Klicken Sie auf **Auswählen** und dann auf **Zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="aaacd-137">Click **Select**, and then click **Assign**.</span></span>
6. <span data-ttu-id="aaacd-138">Schließen Sie die Registerkarte für das Azure Portal in Ihrem Browser.</span><span class="sxs-lookup"><span data-stu-id="aaacd-138">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="aaacd-139">Im nächsten Schritt testen Sie dynamische Gruppenmitgliedschaft und automatische Lizenzierung für das Konto des Benutzers 4.</span><span class="sxs-lookup"><span data-stu-id="aaacd-139">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="aaacd-140">Klicken Sie auf der Registerkarte **Startseite von Microsoft Office** in Ihrem Browser auf **Admin**.</span><span class="sxs-lookup"><span data-stu-id="aaacd-140">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="aaacd-141">Klicken Sie auf der Registerkarte **Office Admin Center** auf **aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="aaacd-141">From the **Office Admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="aaacd-142">Klicken Sie auf der Seite **aktive Benutzer** auf das Konto des **Benutzers 4** .</span><span class="sxs-lookup"><span data-stu-id="aaacd-142">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="aaacd-143">Klicken Sie im Bereich **Benutzer 4** für **Lizenzen**auf **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="aaacd-143">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="aaacd-144">Klicken Sie im Bereich **Lizenzen** Aktivieren der **Enterprise-Mobilität + Sicherheit E5** und **Office 365 Enterprise E5** Lizenzen deaktiviert, und klicken Sie dann auf **Speichern > Schließen**.</span><span class="sxs-lookup"><span data-stu-id="aaacd-144">On the **Product licenses** pane, turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses off, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="aaacd-145">In den Eigenschaften des Kontos Benutzer 4 Stellen Sie sicher, dass keine Lizenzen zugewiesen wurden, und es keine Gruppenmitgliedschaften werden.</span><span class="sxs-lookup"><span data-stu-id="aaacd-145">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="aaacd-146">Klicken Sie auf **Bearbeiten** , um die **Kontaktinformationen**.</span><span class="sxs-lookup"><span data-stu-id="aaacd-146">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="aaacd-147">Klicken Sie auf **Kontaktinformationen**, klicken Sie im Bereich **Kontaktinformationen bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="aaacd-147">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="aaacd-148">Geben Sie in das Feld **Abteilung** **Sales**, und klicken Sie dann auf **Speichern > Schließen**.</span><span class="sxs-lookup"><span data-stu-id="aaacd-148">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="aaacd-149">Warten Sie einige Minuten, und klicken Sie dann in regelmäßigen Abständen auf das Aktualisierungssymbol in der rechten oberen Ecke des Bereichs Konto Benutzer 4.</span><span class="sxs-lookup"><span data-stu-id="aaacd-149">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="aaacd-150">Zeitpunkt sollten Sie sehen die:</span><span class="sxs-lookup"><span data-stu-id="aaacd-150">In time you should see the:</span></span>

- <span data-ttu-id="aaacd-151">**Gruppenmitgliedschaften** -Eigenschaft mit der Gruppe " **Sales** " aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="aaacd-151">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="aaacd-152">**Lizenzen** -Eigenschaft mit der **Mobilität in Unternehmen + Sicherheit E5** und **Office 365 Enterprise E5** Lizenzen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="aaacd-152">**Product licenses** property updated with the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses.</span></span>

<span data-ttu-id="aaacd-153">Finden Sie diese Schritte in der Phase Identität Informationen und Links zu dynamischen Gruppenmitgliedschaft und automatische Lizenzierung in der Produktion bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="aaacd-153">See these steps in the Identity phase for information and links to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="aaacd-154">Einrichten der automatischen Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="aaacd-154">Set up automatic licensing</span></span>](identity-group-based-licensing.md)
- [<span data-ttu-id="aaacd-155">Einrichten der dynamischen Gruppenmitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="aaacd-155">Set up dynamic group membership</span></span>](identity-automatic-group-membership.md)

## <a name="next-step"></a><span data-ttu-id="aaacd-156">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="aaacd-156">Next step</span></span>

<span data-ttu-id="aaacd-157">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="aaacd-157">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="aaacd-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aaacd-158">See also</span></span>

[<span data-ttu-id="aaacd-159">Phase 2: Identität</span><span class="sxs-lookup"><span data-stu-id="aaacd-159">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="aaacd-160">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="aaacd-160">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="aaacd-161">Bereitstellung von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="aaacd-161">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="aaacd-162">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="aaacd-162">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
