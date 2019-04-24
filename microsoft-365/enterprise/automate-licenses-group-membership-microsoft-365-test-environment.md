---
title: Automatisieren von Lizenzen und Gruppenmitgliedschaften für Ihre Microsoft 365 Enterprise-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Konfigurieren Sie die Gruppenbasierte Lizenzierung und die dynamische Gruppenmitgliedschaft in Ihrer Microsoft 365 Enterprise-Testumgebung.
ms.openlocfilehash: 8ced249ee56e15c057001af60d790a8a4315dd17
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277241"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="baba4-103">Automatisieren von Lizenzen und Gruppenmitgliedschaften für Ihre Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="baba4-103">Automate licensing and group membership for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="baba4-104">Bei der gruppenbasierten Lizenzierung werden Lizenzen für ein Benutzerkonto basierend auf der Gruppenmitgliedschaft automatisch zugewiesen oder entfernt.</span><span class="sxs-lookup"><span data-stu-id="baba4-104">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="baba4-105">Die dynamische Gruppenmitgliedschaft fügt Mitglieder zu einer Gruppe hinzu oder entfernt Sie basierend auf Benutzerkontoeigenschaften wie Abteilung oder Land.</span><span class="sxs-lookup"><span data-stu-id="baba4-105">Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country.</span></span> <span data-ttu-id="baba4-106">Dieser Artikel führt Sie durch eine Demonstration beider in Ihrer Microsoft 365 Enterprise-Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="baba4-106">This article steps you through a demonstration of both in your Microsoft 365 Enterprise test environment.</span></span>

<span data-ttu-id="baba4-107">Es gibt zwei Phasen zum Einrichten der automatischen Lizenzierung und der dynamischen Gruppenmitgliedschaft in Ihrer Microsoft 365 Enterprise-Testumgebung:</span><span class="sxs-lookup"><span data-stu-id="baba4-107">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="baba4-108">Erstellen Sie die Microsoft 365 Enterprise-Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="baba4-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="baba4-109">Konfigurieren und testen Sie die dynamische Gruppenmitgliedschaft und die automatische Lizenzierung.</span><span class="sxs-lookup"><span data-stu-id="baba4-109">Configure and test dynamic group membership and automatic licensing.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="baba4-111">Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="baba4-111">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="baba4-112">Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="baba4-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="baba4-113">Wenn Sie die automatische Lizenzierung und Gruppenmitgliedschaft auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="baba4-113">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="baba4-114">Wenn Sie die automatische Lizenzierung und Gruppenmitgliedschaft in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Passthrough-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="baba4-114">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="baba4-115">Das Testen der automatisierten Lizenzierung und der Gruppenmitgliedschaft erfordert nicht die simulierte Enterprise-Testumgebung, die ein simuliertes Intranet enthält, das mit dem Internet und der Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="baba4-115">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="baba4-116">Sie wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und die Gruppenmitgliedschaft testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="baba4-116">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="baba4-117">Phase 2: Konfigurieren und Testen der dynamischen Gruppenmitgliedschaft und der automatischen Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="baba4-117">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="baba4-118">Zunächst erstellen Sie eine neue Vertriebsgruppe und fügen eine dynamische Gruppen Mitgliedschaftsregel hinzu, sodass Benutzerkonten mit der Abteilung "Sales" automatisch der Gruppe "Sales" hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="baba4-118">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="baba4-119">Melden Sie sich über eine private Instanz Ihres Internet Browsers im Office-Portal unter [https://office.com](https://office.com) mit dem globalen Administratorkonto ihres Office 365 E5-Testabonnements an.</span><span class="sxs-lookup"><span data-stu-id="baba4-119">Using a private instance of your Internet browser, sign in to the Office portal at [https://office.com](https://office.com) with the global administrator account of your Office 365 E5 trial subscription.</span></span>
2. <span data-ttu-id="baba4-120">Wechseln Sie auf einer separaten Registerkarte in Ihrem Browser zum Azure-Portal [https://portal.azure.com](https://portal.azure.com)unter.</span><span class="sxs-lookup"><span data-stu-id="baba4-120">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="baba4-121">Klicken Sie im Azure-Portal auf **Azure Active Directory > Benutzer und Gruppen > Alle Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="baba4-121">In the Azure portal, click **Azure Active Directory > Users and groups > All groups**.</span></span>
4. <span data-ttu-id="baba4-122">Klicken Sie auf dem Blatt **alle Gruppen** auf **neue Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="baba4-122">On the **All groups** blade, click **New group**.</span></span>
5. <span data-ttu-id="baba4-123">Wählen \*\*\*\* Sie unter Gruppentyp die option **Office 365**aus.</span><span class="sxs-lookup"><span data-stu-id="baba4-123">In **Group type**, select **Office 365**.</span></span>
6. <span data-ttu-id="baba4-124">Geben Sie unter **Gruppenname den Namen** **Sales**ein.</span><span class="sxs-lookup"><span data-stu-id="baba4-124">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="baba4-125">Wählen \*\*\*\* Sie unter Mitgliedstyp die Option **dynamischer Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="baba4-125">In **Membership type**, select **Dynamic user** .</span></span>
8. <span data-ttu-id="baba4-126">Klicken Sie auf **Dynamische Abfrage hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="baba4-126">Click **Add dynamic query**.</span></span>
9. <span data-ttu-id="baba4-127">Wählen Sie unter **Benutzer hinzufügen**die Option **Abteilung** aus.</span><span class="sxs-lookup"><span data-stu-id="baba4-127">In **Add users where**, select **department**.</span></span>
10. <span data-ttu-id="baba4-128">Wählen Sie im nächsten Feld **Gleich** aus.</span><span class="sxs-lookup"><span data-stu-id="baba4-128">In the next field, select **Equals**.</span></span>
11. <span data-ttu-id="baba4-129">Geben Sie im nächsten Feld **Umsatz**ein.</span><span class="sxs-lookup"><span data-stu-id="baba4-129">In the next field, type **Sales**.</span></span>
12. <span data-ttu-id="baba4-130">Klicken Sie auf **Abfrage hinzufügen**, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="baba4-130">Click **Add query**, and then click **Create**.</span></span>
13. <span data-ttu-id="baba4-131">Schließt die **Gruppe** und **alle Gruppen-** Blades.</span><span class="sxs-lookup"><span data-stu-id="baba4-131">Close the **Group** and **Groups-All groups** blades.</span></span>

<span data-ttu-id="baba4-132">Als Nächstes konfigurieren Sie die Gruppe "Sales" so, dass Mitgliedern automatisch Office 365 E5 und Enterprise Mobility + Security E5-Lizenzen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="baba4-132">Next, you configure the Sales group so that members are automatically assigned Office 365 E5 and Enterprise Mobility + Security E5 licenses.</span></span>

1. <span data-ttu-id="baba4-133">Klicken Sie auf dem Blatt **Übersicht** für Azure Active Directory auf **Lizenzen > alle Produkte**.</span><span class="sxs-lookup"><span data-stu-id="baba4-133">On the **Overview** blade for Azure Active Directory, click **Licenses > All products**.</span></span>
2. <span data-ttu-id="baba4-134">Wählen Sie in der Liste **Enterprise Mobility + Security E5** und **Office 365 Enterprise E5** aus, und klicken Sie dann auf **Zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="baba4-134">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **Assign**.</span></span>
3. <span data-ttu-id="baba4-135">Klicken Sie auf der **Lizenzblatt zuweisen** auf **Benutzer und Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="baba4-135">On the **Assign license** blade, click **Users and groups**.</span></span>
4. <span data-ttu-id="baba4-136">Wählen Sie in der Liste der Gruppen die Gruppe **Sales** aus.</span><span class="sxs-lookup"><span data-stu-id="baba4-136">In the list of groups, select the **Sales** group.</span></span>
5. <span data-ttu-id="baba4-137">Klicken Sie auf **Auswählen** und dann auf **Zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="baba4-137">Click **Select**, and then click **Assign**.</span></span>
6. <span data-ttu-id="baba4-138">Schließen Sie die Registerkarte für das Azure Portal in Ihrem Browser.</span><span class="sxs-lookup"><span data-stu-id="baba4-138">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="baba4-139">Als nächstes testen Sie die dynamische Gruppenmitgliedschaft und die automatische Lizenzierung für das Benutzer 4-Konto.</span><span class="sxs-lookup"><span data-stu-id="baba4-139">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="baba4-140">Klicken Sie auf der Registerkarte **Microsoft Office Home** in Ihrem Browser auf **Admin**.</span><span class="sxs-lookup"><span data-stu-id="baba4-140">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="baba4-141">Klicken Sie auf der Registerkarte **Microsoft 365 Admin Center** auf **aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="baba4-141">From the **Microsoft 365 admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="baba4-142">Klicken Sie auf der Seite **aktive Benutzer** auf das Konto **Benutzer 4** .</span><span class="sxs-lookup"><span data-stu-id="baba4-142">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="baba4-143">Klicken Sie im Bereich **Benutzer 4** auf für **Produktlizenzen** **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="baba4-143">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="baba4-144">Aktivieren Sie im Bereich **Produktlizenzen** die Lizenzen **Enterprise Mobility + Security e5** und **Office 365 Enterprise E5** , und klicken Sie dann auf **> speichern**.</span><span class="sxs-lookup"><span data-stu-id="baba4-144">On the **Product licenses** pane, turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses off, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="baba4-145">Vergewissern Sie sich, dass in den Eigenschaften des Benutzer 4-Kontos keine Produktlizenzen zugewiesen wurden und keine Gruppenmitgliedschaften vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="baba4-145">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="baba4-146">Klicken Sie auf **Bearbeiten** für **Kontaktinformationen**.</span><span class="sxs-lookup"><span data-stu-id="baba4-146">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="baba4-147">Klicken Sie im Bereich **Kontaktinformationen bearbeiten** auf **Kontaktinformationen**.</span><span class="sxs-lookup"><span data-stu-id="baba4-147">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="baba4-148">Geben Sie im Feld **Abteilung** den Namen **Sales**ein, und klicken Sie dann auf **> speichern**.</span><span class="sxs-lookup"><span data-stu-id="baba4-148">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="baba4-149">Warten Sie einige Minuten, und klicken Sie dann regelmäßig auf das Aktualisierungssymbol in der oberen rechten Ecke des Benutzer 4-Konto Bereichs.</span><span class="sxs-lookup"><span data-stu-id="baba4-149">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="baba4-150">In der Zeit sollten Sie Folgendes sehen:</span><span class="sxs-lookup"><span data-stu-id="baba4-150">In time you should see the:</span></span>

- <span data-ttu-id="baba4-151">Die **Group Memberships** -Eigenschaft wurde mit der Gruppe " **Sales** " aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="baba4-151">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="baba4-152">Eigenschaft **Product licenses** , die mit den Lizenzen **Enterprise Mobility + Security E5** und **Office 365 Enterprise E5** aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="baba4-152">**Product licenses** property updated with the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses.</span></span>

<span data-ttu-id="baba4-153">Weitere Informationen und Links zur Bereitstellung der dynamischen Gruppenmitgliedschaft und der automatischen Lizenzierung in der Produktion finden Sie in den folgenden Schritten in der Identitäts Phase:</span><span class="sxs-lookup"><span data-stu-id="baba4-153">See these steps in the Identity phase for information and links to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="baba4-154">Einrichten der automatischen Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="baba4-154">Set up automatic licensing</span></span>](identity-self-service-group-management.md#identity-group-license)
- [<span data-ttu-id="baba4-155">Einrichten der dynamischen Gruppenmitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="baba4-155">Set up dynamic group membership</span></span>](identity-self-service-group-management.md#identity-dyn-groups)

## <a name="next-step"></a><span data-ttu-id="baba4-156">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="baba4-156">Next step</span></span>

<span data-ttu-id="baba4-157">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="baba4-157">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="baba4-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="baba4-158">See also</span></span>

[<span data-ttu-id="baba4-159">Phase 2: Identität</span><span class="sxs-lookup"><span data-stu-id="baba4-159">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="baba4-160">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="baba4-160">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="baba4-161">Microsoft 365 Enterprise-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="baba4-161">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="baba4-162">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="baba4-162">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
