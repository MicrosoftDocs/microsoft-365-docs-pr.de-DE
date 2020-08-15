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
ms.openlocfilehash: a25a47b81ce8c119e7aeb44660af32bb9cafb08a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685558"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="7484e-103">Automatisieren der Lizenzierung und der Gruppenmitgliedschaft für Ihre Microsoft 365 for Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="7484e-103">Automate licensing and group membership for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="7484e-104">*Diese Test Umgebungs Anleitung kann nur für Microsoft 365 für Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="7484e-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="7484e-105">Bei der gruppenbasierten Lizenzierung werden basierend auf der Gruppenmitgliedschaft automatisch Lizenzen für ein Benutzerkonto zugewiesen oder entfernt.</span><span class="sxs-lookup"><span data-stu-id="7484e-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="7484e-106">Durch die dynamische Gruppenmitgliedschaft werden Mitglieder einer Gruppe basierend auf den Eigenschaften des Benutzerkontos wie Abteilung oder Land hinzugefügt oder entfernt.</span><span class="sxs-lookup"><span data-stu-id="7484e-106">Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country.</span></span> <span data-ttu-id="7484e-107">In diesem Artikel werden Sie durch eine Demonstration der beiden in Ihrer Microsoft 365 für Enterprise-Testumgebung erläutert.</span><span class="sxs-lookup"><span data-stu-id="7484e-107">This article steps you through a demonstration of both in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="7484e-108">Es gibt zwei Phasen zum Einrichten der automatischen Lizenzierung und der dynamischen Gruppenmitgliedschaft in Ihrer Microsoft 365 for Enterprise-Testumgebung:</span><span class="sxs-lookup"><span data-stu-id="7484e-108">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 for enterprise test environment:</span></span>

1. <span data-ttu-id="7484e-109">Erstellen Sie die Microsoft 365 for Enterprise-Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="7484e-109">Create the Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="7484e-110">Konfigurieren und Testen der dynamischen Gruppenmitgliedschaft und der automatischen Lizenzierung.</span><span class="sxs-lookup"><span data-stu-id="7484e-110">Configure and test dynamic group membership and automatic licensing.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="7484e-112">Klicken Sie [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7484e-112">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="7484e-113">Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="7484e-113">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="7484e-114">Wenn Sie die automatische Lizenzierung und Gruppenmitgliedschaft nur auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="7484e-114">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="7484e-115">Wenn Sie die automatische Lizenzierung und Gruppenmitgliedschaft in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="7484e-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7484e-116">Für das Testen der automatischen Lizenzierung und der Gruppenmitgliedschaft ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst.</span><span class="sxs-lookup"><span data-stu-id="7484e-116">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="7484e-117">Sie wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="7484e-117">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="7484e-118">Phase 2: Konfigurieren und Testen der dynamischen Gruppenmitgliedschaft und der automatischen Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="7484e-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="7484e-119">Zunächst erstellen Sie eine neue Gruppe "Sales" und fügen eine dynamische Gruppen Mitgliedschaftsregel hinzu, sodass Benutzerkonten mit der Abteilung "Sales" automatisch der Gruppe "Sales" hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="7484e-119">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="7484e-120">Melden Sie sich mit einer privaten Instanz Ihres Internet Browsers beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit dem globalen Administratorkonto Ihres Microsoft 365 E5 Test Lab-Abonnements an.</span><span class="sxs-lookup"><span data-stu-id="7484e-120">Using a private instance of your Internet browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="7484e-121">Wechseln Sie auf einer separaten Registerkarte Ihres Browsers zum Azure-Portal unter [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="7484e-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="7484e-122">Geben Sie im Azure-Portal **Gruppen** in das Suchfeld ein, und klicken Sie dann auf **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="7484e-122">In the Azure portal, type **groups** in the search box, and then click **Groups**.</span></span>
4. <span data-ttu-id="7484e-123">Klicken Sie im Bereich **alle Gruppen** auf **neue Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="7484e-123">in the **All groups** pane, click **New group**.</span></span>
5. <span data-ttu-id="7484e-124">Wählen Sie unter **Gruppentyp den Namen** **Microsoft 365**aus.</span><span class="sxs-lookup"><span data-stu-id="7484e-124">In **Group type**, select **Microsoft 365**.</span></span>
6. <span data-ttu-id="7484e-125">Geben Sie unter **Gruppenname den Namen** **Sales**ein.</span><span class="sxs-lookup"><span data-stu-id="7484e-125">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="7484e-126">Wählen Sie im **Typ Mitgliedschaft**die Option **dynamischer Benutzer**aus.</span><span class="sxs-lookup"><span data-stu-id="7484e-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="7484e-127">Klicken Sie auf **dynamische Benutzer Mitglieder**.</span><span class="sxs-lookup"><span data-stu-id="7484e-127">Click **Dynamic user members**.</span></span>
9. <span data-ttu-id="7484e-128">Im Bereich **Dynamische Mitgliedschaftsregeln** :</span><span class="sxs-lookup"><span data-stu-id="7484e-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="7484e-129">Wählen Sie die Eigenschaft **Department** aus.</span><span class="sxs-lookup"><span data-stu-id="7484e-129">Select the **department** property.</span></span>
   - <span data-ttu-id="7484e-130">Wählen Sie den **Equals** -Operator aus.</span><span class="sxs-lookup"><span data-stu-id="7484e-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="7484e-131">Geben Sie **Umsatz** in **value**ein.</span><span class="sxs-lookup"><span data-stu-id="7484e-131">Type **Sales** in **Value**.</span></span>
10. <span data-ttu-id="7484e-132">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7484e-132">Click **Save**.</span></span>
11. <span data-ttu-id="7484e-133">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="7484e-133">Click **Create**.</span></span>

<span data-ttu-id="7484e-134">Als Nächstes konfigurieren Sie die Gruppe "Sales" so, dass Mitgliedern automatisch die Microsoft 365 E5-Lizenz zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="7484e-134">Next, you configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="7484e-135">Klicken Sie auf die Gruppe **Vertrieb** , und klicken Sie dann auf **Lizenzen**.</span><span class="sxs-lookup"><span data-stu-id="7484e-135">Click the **Sales** group, and then click **Licenses**.</span></span>
2. <span data-ttu-id="7484e-136">Wählen Sie im Bereich **Lizenzzuweisungen aktualisieren** die Option **Microsoft 365 E5**aus, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7484e-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then click **Save**.</span></span>
3. <span data-ttu-id="7484e-137">Schließen Sie die Registerkarte für das Azure Portal in Ihrem Browser.</span><span class="sxs-lookup"><span data-stu-id="7484e-137">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="7484e-138">Als nächstes testen Sie die dynamische Gruppenmitgliedschaft und die automatische Lizenzierung für das Benutzerkonto 4.</span><span class="sxs-lookup"><span data-stu-id="7484e-138">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="7484e-139">Klicken Sie auf der Registerkarte **Microsoft Office Start** in Ihrem Browser auf **Administrator**.</span><span class="sxs-lookup"><span data-stu-id="7484e-139">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="7484e-140">Klicken Sie auf der Registerkarte **Microsoft 365 Admin Center** auf **aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="7484e-140">From the **Microsoft 365 admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="7484e-141">Klicken Sie auf der Seite **aktive Benutzer** auf das Konto **Benutzer 4** .</span><span class="sxs-lookup"><span data-stu-id="7484e-141">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="7484e-142">Klicken Sie im Bereich **Benutzer 4** auf für **Produktlizenzen** **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="7484e-142">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="7484e-143">Deaktivieren Sie im Bereich **Produktlizenzen** die Lizenz **Microsoft 365 E5** , und klicken Sie dann auf **> schließen speichern**.</span><span class="sxs-lookup"><span data-stu-id="7484e-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="7484e-144">Überprüfen Sie in den Eigenschaften des Benutzerkontos 4, dass keine Produktlizenzen zugewiesen wurden und keine Gruppenmitgliedschaften vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="7484e-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="7484e-145">Klicken Sie auf **Bearbeiten** , um **Kontaktinformationen zu erhalten**.</span><span class="sxs-lookup"><span data-stu-id="7484e-145">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="7484e-146">Klicken Sie im Bereich **Kontaktinformationen bearbeiten** auf **Kontaktinformationen**.</span><span class="sxs-lookup"><span data-stu-id="7484e-146">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="7484e-147">Geben Sie im Feld **Abteilung** den Namen **Sales**ein, und klicken Sie dann auf **> schließen speichern**.</span><span class="sxs-lookup"><span data-stu-id="7484e-147">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="7484e-148">Warten Sie einige Minuten, und klicken Sie dann regelmäßig auf das Aktualisierungssymbol in der oberen rechten Ecke des Benutzer-4-Konto Bereichs.</span><span class="sxs-lookup"><span data-stu-id="7484e-148">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="7484e-149">In der Zeit sollte Folgendes angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="7484e-149">In time you should see the:</span></span>

- <span data-ttu-id="7484e-150">**Group Memberships** -Eigenschaft mit der Gruppe " **Sales** " aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="7484e-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="7484e-151">Die Eigenschaft " **Produktlizenzen** " wurde mit der **Microsoft 365 E5** -Lizenz aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="7484e-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="7484e-152">Lesen Sie diese Artikel, um die dynamische Gruppenmitgliedschaft und die automatische Lizenzierung in der Produktion bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="7484e-152">See these articles to deploy dynamic group membership and automatic licensing in production:</span></span>

- <span data-ttu-id="7484e-153">Verknüpfungs Anknüpfung</span><span class="sxs-lookup"><span data-stu-id="7484e-153">LINK TBD</span></span>
- <span data-ttu-id="7484e-154">Verknüpfungs Anknüpfung</span><span class="sxs-lookup"><span data-stu-id="7484e-154">LINK TBD</span></span>

## <a name="next-step"></a><span data-ttu-id="7484e-155">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="7484e-155">Next step</span></span>

<span data-ttu-id="7484e-156">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="7484e-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="7484e-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7484e-157">See also</span></span>

[<span data-ttu-id="7484e-158">Identity-Roadmap</span><span class="sxs-lookup"><span data-stu-id="7484e-158">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="7484e-159">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7484e-159">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="7484e-160">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7484e-160">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="7484e-161">Dokumentation zu Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="7484e-161">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
