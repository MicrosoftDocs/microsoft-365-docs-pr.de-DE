---
title: Automatisieren der Lizenzierung und der Gruppenmitgliedschaft für Ihre Microsoft 365 for Enterprise-Testumgebung
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Konfigurieren Sie die Gruppenbasierte Lizenzierung und die dynamische Gruppenmitgliedschaft in Ihrer Microsoft 365 for Enterprise-Testumgebung.
ms.openlocfilehash: d770e7be3b0b55855f1fee26a45d55260c3074cb
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487576"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="82e5c-103">Automatisieren der Lizenzierung und der Gruppenmitgliedschaft für Ihre Microsoft 365 for Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="82e5c-103">Automate licensing and group membership for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="82e5c-104">*Diese Test Umgebungs Anleitung kann nur für Microsoft 365 für Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="82e5c-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="82e5c-105">Bei der gruppenbasierten Lizenzierung werden basierend auf der Gruppenmitgliedschaft automatisch Lizenzen für ein Benutzerkonto zugewiesen oder entfernt.</span><span class="sxs-lookup"><span data-stu-id="82e5c-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="82e5c-106">Durch die dynamische Gruppenmitgliedschaft werden Mitglieder einer Gruppe basierend auf den Eigenschaften des Benutzerkontos wie **Abteilung** oder **Land**hinzugefügt oder entfernt.</span><span class="sxs-lookup"><span data-stu-id="82e5c-106">Dynamic group membership adds or removes members to a group based on user account properties, such as **Department** or **Country**.</span></span> <span data-ttu-id="82e5c-107">In diesem Artikel werden die Vorführungen für das Hinzufügen und Entfernen von Gruppenmitgliedern in Ihrer Microsoft 365 for Enterprise-Testumgebung erläutert.</span><span class="sxs-lookup"><span data-stu-id="82e5c-107">This article steps you through demonstrations of both adding and removing group members in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="82e5c-108">Das Einrichten der automatischen Lizenzierung und der dynamischen Gruppenmitgliedschaft in Ihrer Microsoft 365 for Enterprise-Testumgebung umfasst zwei Phasen:</span><span class="sxs-lookup"><span data-stu-id="82e5c-108">Setting up auto-licensing and dynamic group membership in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="82e5c-109">Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="82e5c-109">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="82e5c-110">Phase 2: Konfigurieren und Testen der dynamischen Gruppenmitgliedschaft und der automatischen Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="82e5c-110">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="82e5c-112">Eine visuelle Zuordnung zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide Stack finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="82e5c-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="82e5c-113">Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="82e5c-113">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="82e5c-114">Wenn Sie die automatische Lizenzierung und Gruppenmitgliedschaft nur auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="82e5c-114">If you want to only test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="82e5c-115">Wenn Sie die automatische Lizenzierung und Gruppenmitgliedschaft in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="82e5c-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="82e5c-116">Für das Testen der automatisierten Lizenzierung und der Gruppenmitgliedschaft ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst.</span><span class="sxs-lookup"><span data-stu-id="82e5c-116">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="82e5c-117">Er wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="82e5c-117">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="82e5c-118">Phase 2: Konfigurieren und Testen der dynamischen Gruppenmitgliedschaft und der automatischen Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="82e5c-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="82e5c-119">Erstellen Sie zuerst eine neue Gruppe mit dem Namen "Sales", und fügen Sie eine dynamische Gruppen Mitgliedschaftsregel hinzu, sodass Benutzerkonten, deren **Abteilung** " **Sales** " festgelegt ist, automatisch der Gruppe "Sales" beitreten.</span><span class="sxs-lookup"><span data-stu-id="82e5c-119">First, create a new group named Sales, and add a dynamic group membership rule so that user accounts with the **Department** set to **Sales** automatically join the Sales group.</span></span>

1. <span data-ttu-id="82e5c-120">Melden Sie sich in einer privaten Instanz Ihres Internetbrowsers beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit dem globalen Administratorkonto Ihres Microsoft 365 E5 Test Lab-Abonnements an.</span><span class="sxs-lookup"><span data-stu-id="82e5c-120">In a private instance of your internet browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="82e5c-121">Wechseln Sie auf einer separaten Registerkarte Ihres Browsers zum Azure-Portal unter [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="82e5c-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="82e5c-122">Geben Sie im Azure-Portal in das Suchfeld **Gruppen** ein, und wählen Sie dann **Gruppen**aus.</span><span class="sxs-lookup"><span data-stu-id="82e5c-122">In the Azure portal, enter **groups** in the search box, and then select **Groups**.</span></span>
4. <span data-ttu-id="82e5c-123">Wählen Sie im Bereich **alle Gruppen** die Option **neue Gruppe**aus.</span><span class="sxs-lookup"><span data-stu-id="82e5c-123">in the **All groups** pane, select **New group**.</span></span>
5. <span data-ttu-id="82e5c-124">Wählen Sie unter **Gruppentyp den Namen** **Microsoft 365**aus.</span><span class="sxs-lookup"><span data-stu-id="82e5c-124">In **Group type**, select **Microsoft 365**.</span></span>
6. <span data-ttu-id="82e5c-125">Geben Sie unter **Gruppenname den Namen** **Sales**ein.</span><span class="sxs-lookup"><span data-stu-id="82e5c-125">In **Group name**, enter **Sales**.</span></span>
7. <span data-ttu-id="82e5c-126">Wählen Sie im **Typ Mitgliedschaft**die Option **dynamischer Benutzer**aus.</span><span class="sxs-lookup"><span data-stu-id="82e5c-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="82e5c-127">Wählen Sie **dynamische Benutzer Mitglieder**aus.</span><span class="sxs-lookup"><span data-stu-id="82e5c-127">Select **Dynamic user members**.</span></span>
9. <span data-ttu-id="82e5c-128">Im Bereich **Dynamische Mitgliedschaftsregeln** :</span><span class="sxs-lookup"><span data-stu-id="82e5c-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="82e5c-129">Wählen Sie die Eigenschaft **Department** aus.</span><span class="sxs-lookup"><span data-stu-id="82e5c-129">Select the **department** property.</span></span>
   - <span data-ttu-id="82e5c-130">Wählen Sie den **Equals** -Operator aus.</span><span class="sxs-lookup"><span data-stu-id="82e5c-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="82e5c-131">Geben Sie im Feld **Wert** die Option **Sales**ein.</span><span class="sxs-lookup"><span data-stu-id="82e5c-131">In the **Value** box, enter **Sales**.</span></span>
10. <span data-ttu-id="82e5c-132">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="82e5c-132">Select **Save**.</span></span>
11. <span data-ttu-id="82e5c-133">Wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="82e5c-133">Select **Create**.</span></span>

<span data-ttu-id="82e5c-134">Konfigurieren Sie als nächstes die Gruppe "Sales" so, dass Mitgliedern automatisch die Microsoft 365 E5-Lizenz zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="82e5c-134">Next, configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="82e5c-135">Wählen Sie die Gruppe **Vertrieb** aus, und wählen Sie dann **Lizenzen**aus.</span><span class="sxs-lookup"><span data-stu-id="82e5c-135">Select the **Sales** group, and then select **Licenses**.</span></span>
2. <span data-ttu-id="82e5c-136">Wählen Sie im Bereich **Lizenzzuweisungen aktualisieren** die Option **Microsoft 365 E5**aus, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="82e5c-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then select **Save**.</span></span>
3. <span data-ttu-id="82e5c-137">Schließen Sie in Ihrem Browser die Registerkarte Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="82e5c-137">In your browser, close the Azure portal tab.</span></span>

<span data-ttu-id="82e5c-138">Testen Sie als nächstes die dynamische Gruppenmitgliedschaft und die automatische Lizenzierung für das Benutzerkonto 4:</span><span class="sxs-lookup"><span data-stu-id="82e5c-138">Next, test dynamic group membership and automatic licensing on the User 4 account:</span></span>

1. <span data-ttu-id="82e5c-139">Wählen Sie auf der Registerkarte **Microsoft Office Start** in Ihrem Browser **Administrator**aus.</span><span class="sxs-lookup"><span data-stu-id="82e5c-139">From the **Microsoft Office Home** tab in your browser, select **Admin**.</span></span>
2. <span data-ttu-id="82e5c-140">Wählen Sie auf der Registerkarte **Microsoft 365 Admin Center** die Option **aktive Benutzer**aus.</span><span class="sxs-lookup"><span data-stu-id="82e5c-140">From the **Microsoft 365 admin center** tab, select **Active users**.</span></span>
3. <span data-ttu-id="82e5c-141">Wählen Sie auf der Seite **aktive Benutzer** das Konto **Benutzer 4** aus.</span><span class="sxs-lookup"><span data-stu-id="82e5c-141">On the **Active users** page, select the **User 4** account.</span></span>
4. <span data-ttu-id="82e5c-142">Wählen Sie im Bereich **Benutzer 4** die Option für **Produktlizenzen** **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="82e5c-142">On the **User 4** pane, select **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="82e5c-143">Deaktivieren Sie im Bereich **Produktlizenzen** die **Microsoft 365 E5** -Lizenz, und wählen Sie dann **Speichern**  >  **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="82e5c-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then select **Save** > **Close**.</span></span>
6. <span data-ttu-id="82e5c-144">Überprüfen Sie in den Eigenschaften des Benutzerkontos 4, dass keine Produktlizenzen zugewiesen wurden und keine Gruppenmitgliedschaften vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="82e5c-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="82e5c-145">Wählen Sie für **Kontaktinformationen**die Option **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="82e5c-145">For **Contact information**, select **Edit**.</span></span>
8. <span data-ttu-id="82e5c-146">Wählen Sie im Bereich **Kontaktinformationen bearbeiten** die Option **Kontaktinformationen**aus.</span><span class="sxs-lookup"><span data-stu-id="82e5c-146">In the **Edit Contact information** pane, select **Contact information**.</span></span>
9. <span data-ttu-id="82e5c-147">Geben Sie im Feld **Abteilung** die Option **Sales**ein, und wählen Sie dann **Speichern**  >  **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="82e5c-147">In the **Department** box, enter **Sales**, and then select **Save** > **Close**.</span></span>
10. <span data-ttu-id="82e5c-148">Warten Sie einige Minuten, und wählen Sie dann in regelmäßigen Abständen das **Aktualisierungs** Symbol in der oberen rechten Ecke des Benutzer-4-Konto Bereichs aus.</span><span class="sxs-lookup"><span data-stu-id="82e5c-148">Wait a few minutes, and then periodically select the **Refresh** icon in the upper-right of the User 4 account pane.</span></span>

<span data-ttu-id="82e5c-149">In der Zeit sollte Folgendes angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="82e5c-149">In time, you should see the:</span></span>

- <span data-ttu-id="82e5c-150">**Group Memberships** -Eigenschaft mit der Gruppe " **Sales** " aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="82e5c-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="82e5c-151">Die Eigenschaft " **Produktlizenzen** " wurde mit der **Microsoft 365 E5** -Lizenz aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="82e5c-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="82e5c-152">Lesen Sie diese Artikel, um die dynamische Gruppenmitgliedschaft und die automatische Lizenzierung in der Produktion bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="82e5c-152">See these articles to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="82e5c-153">Gruppenbasierte Lizenzierung in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="82e5c-153">Group-based licensing in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [<span data-ttu-id="82e5c-154">Dynamische Gruppen in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="82e5c-154">Dynamic groups in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a><span data-ttu-id="82e5c-155">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="82e5c-155">Next step</span></span>

<span data-ttu-id="82e5c-156">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="82e5c-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="82e5c-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82e5c-157">See also</span></span>

[<span data-ttu-id="82e5c-158">Identity-Roadmap</span><span class="sxs-lookup"><span data-stu-id="82e5c-158">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="82e5c-159">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="82e5c-159">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="82e5c-160">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="82e5c-160">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="82e5c-161">Dokumentation zu Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="82e5c-161">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
