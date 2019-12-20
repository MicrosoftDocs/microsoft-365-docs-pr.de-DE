---
title: Automatisieren der Lizenzierung und der Gruppenmitgliedschaft für Ihre Microsoft 365 Enterprise-Testumgebung
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
description: Konfigurieren Sie die Gruppenbasierte Lizenzierung und die dynamische Gruppenmitgliedschaft in Ihrer Microsoft 365 Enterprise-Testumgebung.
ms.openlocfilehash: facff7eb556299c0312fa7488a35a96151bb1882
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802120"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="6105d-103">Automatisieren der Lizenzierung und der Gruppenmitgliedschaft für Ihre Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="6105d-103">Automate licensing and group membership for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="6105d-104">*Diese Testumgebungsanleitung kann nur für Microsoft 365 Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="6105d-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="6105d-105">Bei der gruppenbasierten Lizenzierung werden basierend auf der Gruppenmitgliedschaft automatisch Lizenzen für ein Benutzerkonto zugewiesen oder entfernt.</span><span class="sxs-lookup"><span data-stu-id="6105d-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="6105d-106">Durch die dynamische Gruppenmitgliedschaft werden Mitglieder einer Gruppe basierend auf den Eigenschaften des Benutzerkontos wie Abteilung oder Land hinzugefügt oder entfernt.</span><span class="sxs-lookup"><span data-stu-id="6105d-106">Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country.</span></span> <span data-ttu-id="6105d-107">In diesem Artikel werden Sie durch eine Demonstration beider Schritte in Ihrer Microsoft 365 Enterprise-Testumgebung geführt.</span><span class="sxs-lookup"><span data-stu-id="6105d-107">This article steps you through a demonstration of both in your Microsoft 365 Enterprise test environment.</span></span>

<span data-ttu-id="6105d-108">Es gibt zwei Phasen zum Einrichten der automatischen Lizenzierung und der dynamischen Gruppenmitgliedschaft in Ihrer Microsoft 365 Enterprise-Testumgebung:</span><span class="sxs-lookup"><span data-stu-id="6105d-108">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="6105d-109">Erstellen Sie die Microsoft 365 Enterprise-Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="6105d-109">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="6105d-110">Konfigurieren und Testen der dynamischen Gruppenmitgliedschaft und der automatischen Lizenzierung.</span><span class="sxs-lookup"><span data-stu-id="6105d-110">Configure and test dynamic group membership and automatic licensing.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="6105d-112">Klicken Sie [hier](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6105d-112">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="6105d-113">Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="6105d-113">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="6105d-114">Wenn Sie die automatische Lizenzierung und Gruppenmitgliedschaft nur auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="6105d-114">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="6105d-115">Wenn Sie die automatische Lizenzierung und Gruppenmitgliedschaft in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="6105d-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6105d-116">Für das Testen der automatischen Lizenzierung und Gruppenmitgliedschaft ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS)-Gesamtstruktur umfasst.</span><span class="sxs-lookup"><span data-stu-id="6105d-116">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="6105d-117">Sie wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="6105d-117">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="6105d-118">Phase 2: Konfigurieren und Testen der dynamischen Gruppenmitgliedschaft und der automatischen Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="6105d-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="6105d-119">Zunächst erstellen Sie eine neue Gruppe "Sales" und fügen eine dynamische Gruppen Mitgliedschaftsregel hinzu, sodass Benutzerkonten mit der Abteilung "Sales" automatisch der Gruppe "Sales" hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="6105d-119">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="6105d-120">Melden Sie sich mit einer privaten Instanz Ihres Internet Browsers beim Office 365-Portal unter [https://portal.office.com](https://portal.office.com) mit dem globalen Administratorkonto Ihres Microsoft 365 E5 Test Lab-Abonnements an.</span><span class="sxs-lookup"><span data-stu-id="6105d-120">Using a private instance of your Internet browser, sign in to the Office 365 portal at [https://portal.office.com](https://portal.office.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="6105d-121">Wechseln Sie auf einer separaten Registerkarte Ihres Browsers zum Azure-Portal unter [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="6105d-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="6105d-122">Geben Sie im Azure-Portal **Gruppen** in das Suchfeld ein, und klicken Sie dann auf **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="6105d-122">In the Azure portal, type **groups** in the search box, and then click **Groups**.</span></span>
4. <span data-ttu-id="6105d-123">Klicken Sie im Bereich **alle Gruppen** auf **neue Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="6105d-123">in the **All groups** pane, click **New group**.</span></span>
5. <span data-ttu-id="6105d-124">Wählen Sie unter **Gruppentyp**die Option **Office 365**aus.</span><span class="sxs-lookup"><span data-stu-id="6105d-124">In **Group type**, select **Office 365**.</span></span>
6. <span data-ttu-id="6105d-125">Geben Sie unter **Gruppenname den Namen** **Sales**ein.</span><span class="sxs-lookup"><span data-stu-id="6105d-125">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="6105d-126">Wählen Sie im **Typ Mitgliedschaft**die Option **dynamischer Benutzer**aus.</span><span class="sxs-lookup"><span data-stu-id="6105d-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="6105d-127">Klicken Sie auf **dynamische Benutzer Mitglieder**.</span><span class="sxs-lookup"><span data-stu-id="6105d-127">Click **Dynamic user members**.</span></span>
9. <span data-ttu-id="6105d-128">Im Bereich **Dynamische Mitgliedschaftsregeln** :</span><span class="sxs-lookup"><span data-stu-id="6105d-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="6105d-129">Wählen Sie die Eigenschaft **Department** aus.</span><span class="sxs-lookup"><span data-stu-id="6105d-129">Select the **department** property.</span></span>
   - <span data-ttu-id="6105d-130">Wählen Sie den **Equals** -Operator aus.</span><span class="sxs-lookup"><span data-stu-id="6105d-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="6105d-131">Geben Sie **Umsatz** in **value**ein.</span><span class="sxs-lookup"><span data-stu-id="6105d-131">Type **Sales** in **Value**.</span></span>
10. <span data-ttu-id="6105d-132">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="6105d-132">Click **Save**.</span></span>
11. <span data-ttu-id="6105d-133">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="6105d-133">Click **Create**.</span></span>

<span data-ttu-id="6105d-134">Als Nächstes konfigurieren Sie die Gruppe "Sales" so, dass Mitgliedern automatisch die Microsoft 365 E5-Lizenz zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="6105d-134">Next, you configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="6105d-135">Klicken Sie auf die Gruppe **Vertrieb** , und klicken Sie dann auf **Lizenzen**.</span><span class="sxs-lookup"><span data-stu-id="6105d-135">Click the **Sales** group, and then click **Licenses**.</span></span>
2. <span data-ttu-id="6105d-136">Wählen Sie im Bereich **Lizenzzuweisungen aktualisieren** die Option **Microsoft 365 E5**aus, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="6105d-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then click **Save**.</span></span>
3. <span data-ttu-id="6105d-137">Schließen Sie die Registerkarte für das Azure Portal in Ihrem Browser.</span><span class="sxs-lookup"><span data-stu-id="6105d-137">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="6105d-138">Als nächstes testen Sie die dynamische Gruppenmitgliedschaft und die automatische Lizenzierung für das Benutzerkonto 4.</span><span class="sxs-lookup"><span data-stu-id="6105d-138">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="6105d-139">Klicken Sie auf der Registerkarte **Microsoft Office Start** in Ihrem Browser auf **Administrator**.</span><span class="sxs-lookup"><span data-stu-id="6105d-139">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="6105d-140">Klicken Sie auf der Registerkarte **Microsoft 365 Admin Center** auf **aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="6105d-140">From the **Microsoft 365 admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="6105d-141">Klicken Sie auf der Seite **aktive Benutzer** auf das Konto **Benutzer 4** .</span><span class="sxs-lookup"><span data-stu-id="6105d-141">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="6105d-142">Klicken Sie im Bereich **Benutzer 4** auf für **Produktlizenzen** **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="6105d-142">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="6105d-143">Deaktivieren Sie im Bereich **Produktlizenzen** die Lizenz **Microsoft 365 E5** , und klicken Sie dann auf **#a0 schließen speichern**.</span><span class="sxs-lookup"><span data-stu-id="6105d-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="6105d-144">Überprüfen Sie in den Eigenschaften des Benutzerkontos 4, dass keine Produktlizenzen zugewiesen wurden und keine Gruppenmitgliedschaften vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="6105d-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="6105d-145">Klicken Sie auf **Bearbeiten** , um **Kontaktinformationen zu erhalten**.</span><span class="sxs-lookup"><span data-stu-id="6105d-145">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="6105d-146">Klicken Sie im Bereich **Kontaktinformationen bearbeiten** auf **Kontaktinformationen**.</span><span class="sxs-lookup"><span data-stu-id="6105d-146">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="6105d-147">Geben Sie im Feld **Abteilung** den Namen **Sales**ein, und klicken Sie dann auf **#a0 schließen speichern**.</span><span class="sxs-lookup"><span data-stu-id="6105d-147">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="6105d-148">Warten Sie einige Minuten, und klicken Sie dann regelmäßig auf das Aktualisierungssymbol in der oberen rechten Ecke des Benutzer-4-Konto Bereichs.</span><span class="sxs-lookup"><span data-stu-id="6105d-148">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="6105d-149">In der Zeit sollte Folgendes angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="6105d-149">In time you should see the:</span></span>

- <span data-ttu-id="6105d-150">**Group Memberships** -Eigenschaft mit der Gruppe " **Sales** " aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="6105d-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="6105d-151">Die Eigenschaft " **Produktlizenzen** " wurde mit der **Microsoft 365 E5** -Lizenz aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="6105d-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="6105d-152">In den folgenden Schritten in der Identitäts Phase finden Sie Informationen und Links zum Bereitstellen der dynamischen Gruppenmitgliedschaft und der automatischen Lizenzierung in der Produktionsumgebung:</span><span class="sxs-lookup"><span data-stu-id="6105d-152">See these steps in the Identity phase for information and links to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="6105d-153">Einrichten der automatischen Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="6105d-153">Set up automatic licensing</span></span>](identity-use-group-management.md#identity-group-license)
- [<span data-ttu-id="6105d-154">Einrichten der dynamischen Gruppenmitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="6105d-154">Set up dynamic group membership</span></span>](identity-use-group-management.md#identity-dyn-groups)

## <a name="next-step"></a><span data-ttu-id="6105d-155">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="6105d-155">Next step</span></span>

<span data-ttu-id="6105d-156">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="6105d-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="6105d-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6105d-157">See also</span></span>

[<span data-ttu-id="6105d-158">Phase 2: Identität</span><span class="sxs-lookup"><span data-stu-id="6105d-158">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="6105d-159">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6105d-159">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="6105d-160">Microsoft 365 Enterprise-Bereitstellungshandbuch</span><span class="sxs-lookup"><span data-stu-id="6105d-160">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="6105d-161">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6105d-161">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
