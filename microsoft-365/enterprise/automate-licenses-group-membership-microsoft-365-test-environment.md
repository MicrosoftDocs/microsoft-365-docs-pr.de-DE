---
title: Automatisieren der Lizenzierung und der Gruppenmitgliedschaft für Ihre Microsoft 365 Enterprise-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Konfigurieren Sie die Gruppenbasierte Lizenzierung und die dynamische Gruppenmitgliedschaft in Ihrer Microsoft 365 Enterprise-Testumgebung.
ms.openlocfilehash: cb01e1a405e7cff1f9965e34751b3ce638dd8018
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071724"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="9fc5a-103">Automatisieren der Lizenzierung und der Gruppenmitgliedschaft für Ihre Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="9fc5a-103">Automate licensing and group membership for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="9fc5a-104">Bei der gruppenbasierten Lizenzierung werden basierend auf der Gruppenmitgliedschaft automatisch Lizenzen für ein Benutzerkonto zugewiesen oder entfernt.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-104">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="9fc5a-105">Durch die dynamische Gruppenmitgliedschaft werden Mitglieder einer Gruppe basierend auf den Eigenschaften des Benutzerkontos wie Abteilung oder Land hinzugefügt oder entfernt.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-105">Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country.</span></span> <span data-ttu-id="9fc5a-106">In diesem Artikel werden Sie durch eine Demonstration beider Schritte in Ihrer Microsoft 365 Enterprise-Testumgebung geführt.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-106">This article steps you through a demonstration of both in your Microsoft 365 Enterprise test environment.</span></span>

<span data-ttu-id="9fc5a-107">Es gibt zwei Phasen zum Einrichten der automatischen Lizenzierung und der dynamischen Gruppenmitgliedschaft in Ihrer Microsoft 365 Enterprise-Testumgebung:</span><span class="sxs-lookup"><span data-stu-id="9fc5a-107">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="9fc5a-108">Erstellen Sie die Microsoft 365 Enterprise-Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="9fc5a-109">Konfigurieren und Testen der dynamischen Gruppenmitgliedschaft und der automatischen Lizenzierung.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-109">Configure and test dynamic group membership and automatic licensing.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="9fc5a-111">Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-111">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="9fc5a-112">Phase 1: Erstellen der Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="9fc5a-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="9fc5a-113">Wenn Sie die automatische Lizenzierung und Gruppenmitgliedschaft nur auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="9fc5a-113">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="9fc5a-114">Wenn Sie die automatische Lizenzierung und Gruppenmitgliedschaft in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="9fc5a-114">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9fc5a-115">Für das Testen der automatischen Lizenzierung und der Gruppenmitgliedschaft ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-115">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="9fc5a-116">Sie wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-116">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="9fc5a-117">Phase 2: Konfigurieren und Testen der dynamischen Gruppenmitgliedschaft und der automatischen Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="9fc5a-117">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="9fc5a-118">Zunächst erstellen Sie eine neue Gruppe "Sales" und fügen eine dynamische Gruppen Mitgliedschaftsregel hinzu, sodass Benutzerkonten mit der Abteilung "Sales" automatisch der Gruppe "Sales" hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-118">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="9fc5a-119">Melden Sie sich mit einer privaten Instanz Ihres Internet Browsers beim Office 365-Portal unter [https://portal.office.com](https://portal.office.com) mit dem globalen Administratorkonto Ihres Office 365 E5 Test Lab-Abonnements an.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-119">Using a private instance of your Internet browser, sign in to the Office 365 portal at [https://portal.office.com](https://portal.office.com) with the global administrator account of your Office 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="9fc5a-120">Wechseln Sie auf einer separaten Registerkarte Ihres Browsers zum Azure-Portal unter [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="9fc5a-120">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="9fc5a-121">Klicken Sie im Azure-Portal auf **Azure Active Directory > Benutzer und Gruppen > Alle Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-121">In the Azure portal, click **Azure Active Directory > Users and groups > All groups**.</span></span>
4. <span data-ttu-id="9fc5a-122">Klicken Sie auf dem Blatt **alle Gruppen** auf **neue Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-122">On the **All groups** blade, click **New group**.</span></span>
5. <span data-ttu-id="9fc5a-123">Wählen Sie unter **Gruppentyp**die Option **Office 365**aus.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-123">In **Group type**, select **Office 365**.</span></span>
6. <span data-ttu-id="9fc5a-124">Geben Sie unter **Gruppenname den Namen** **Sales**ein.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-124">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="9fc5a-125">Wählen Sie im **Typ Mitgliedschaft**die Option **dynamischer Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-125">In **Membership type**, select **Dynamic user** .</span></span>
8. <span data-ttu-id="9fc5a-126">Klicken Sie auf **Dynamische Abfrage hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-126">Click **Add dynamic query**.</span></span>
9. <span data-ttu-id="9fc5a-127">Wählen Sie unter **Benutzer hinzufügen**die Option **Abteilung** aus.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-127">In **Add users where**, select **department**.</span></span>
10. <span data-ttu-id="9fc5a-128">Wählen Sie im nächsten Feld **Gleich** aus.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-128">In the next field, select **Equals**.</span></span>
11. <span data-ttu-id="9fc5a-129">Geben Sie im nächsten Feld **Umsatz**ein.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-129">In the next field, type **Sales**.</span></span>
12. <span data-ttu-id="9fc5a-130">Klicken Sie auf **Abfrage hinzufügen**, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-130">Click **Add query**, and then click **Create**.</span></span>
13. <span data-ttu-id="9fc5a-131">Schließen Sie die Blades **Gruppe** und **Gruppen – alle Gruppen** .</span><span class="sxs-lookup"><span data-stu-id="9fc5a-131">Close the **Group** and **Groups-All groups** blades.</span></span>

<span data-ttu-id="9fc5a-132">Als Nächstes konfigurieren Sie die Gruppe "Sales" so, dass Mitgliedern automatisch Office 365 E5-und Enterprise Mobility + Security E5-Lizenzen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-132">Next, you configure the Sales group so that members are automatically assigned Office 365 E5 and Enterprise Mobility + Security E5 licenses.</span></span>

1. <span data-ttu-id="9fc5a-133">Klicken Sie auf der Active Directory **Übersicht** Blade for Azure auf **Lizenzen #a0 alle Produkte**.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-133">On the **Overview** blade for Azure Active Directory, click **Licenses > All products**.</span></span>
2. <span data-ttu-id="9fc5a-134">Wählen Sie in der Liste **Enterprise Mobility + Security E5** und **Office 365 Enterprise E5** aus, und klicken Sie dann auf **Zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-134">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **Assign**.</span></span>
3. <span data-ttu-id="9fc5a-135">Klicken Sie auf dem Blatt **Lizenz zuweisen** auf **Benutzer und Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-135">On the **Assign license** blade, click **Users and groups**.</span></span>
4. <span data-ttu-id="9fc5a-136">Wählen Sie in der Liste der Gruppen die Gruppe **Vertrieb** aus.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-136">In the list of groups, select the **Sales** group.</span></span>
5. <span data-ttu-id="9fc5a-137">Klicken Sie auf **Auswählen** und dann auf **Zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-137">Click **Select**, and then click **Assign**.</span></span>
6. <span data-ttu-id="9fc5a-138">Schließen Sie die Registerkarte für das Azure Portal in Ihrem Browser.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-138">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="9fc5a-139">Als nächstes testen Sie die dynamische Gruppenmitgliedschaft und die automatische Lizenzierung für das Benutzerkonto 4.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-139">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="9fc5a-140">Klicken Sie auf der Registerkarte **Microsoft Office Start** in Ihrem Browser auf **Administrator**.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-140">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="9fc5a-141">Klicken Sie auf der Registerkarte **Microsoft 365 Admin Center** auf **aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-141">From the **Microsoft 365 admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="9fc5a-142">Klicken Sie auf der Seite **aktive Benutzer** auf das Konto **Benutzer 4** .</span><span class="sxs-lookup"><span data-stu-id="9fc5a-142">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="9fc5a-143">Klicken Sie im Bereich **Benutzer 4** auf für **Produktlizenzen** **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="9fc5a-143">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="9fc5a-144">Aktivieren Sie im Bereich " **Produktlizenzen** " die Lizenzen " **Enterprise Mobility + Security E5** " und " **Office 365 Enterprise E5** " aus, und klicken Sie dann auf **Save #a0 close**.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-144">On the **Product licenses** pane, turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses off, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="9fc5a-145">Überprüfen Sie in den Eigenschaften des Benutzerkontos 4, dass keine Produktlizenzen zugewiesen wurden und keine Gruppenmitgliedschaften vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-145">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="9fc5a-146">Klicken Sie auf **Bearbeiten** , um **Kontaktinformationen zu erhalten**.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-146">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="9fc5a-147">Klicken Sie im Bereich **Kontaktinformationen bearbeiten** auf **Kontaktinformationen**.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-147">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="9fc5a-148">Geben Sie im Feld **Abteilung** den Namen **Sales**ein, und klicken Sie dann auf **#a0 schließen speichern**.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-148">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="9fc5a-149">Warten Sie einige Minuten, und klicken Sie dann regelmäßig auf das Aktualisierungssymbol in der oberen rechten Ecke des Benutzer-4-Konto Bereichs.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-149">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="9fc5a-150">In der Zeit sollte Folgendes angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="9fc5a-150">In time you should see the:</span></span>

- <span data-ttu-id="9fc5a-151">**Group Memberships** -Eigenschaft mit der Gruppe " **Sales** " aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-151">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="9fc5a-152">**Product licenses** -Eigenschaft mit den Lizenzen **Enterprise Mobility + Security E5** und **Office 365 Enterprise E5** aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-152">**Product licenses** property updated with the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses.</span></span>

<span data-ttu-id="9fc5a-153">In den folgenden Schritten in der Identitäts Phase finden Sie Informationen und Links zum Bereitstellen der dynamischen Gruppenmitgliedschaft und der automatischen Lizenzierung in der Produktionsumgebung:</span><span class="sxs-lookup"><span data-stu-id="9fc5a-153">See these steps in the Identity phase for information and links to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="9fc5a-154">Einrichten der automatischen Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="9fc5a-154">Set up automatic licensing</span></span>](identity-use-group-management.md#identity-group-license)
- [<span data-ttu-id="9fc5a-155">Einrichten der dynamischen Gruppenmitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="9fc5a-155">Set up dynamic group membership</span></span>](identity-use-group-management.md#identity-dyn-groups)

## <a name="next-step"></a><span data-ttu-id="9fc5a-156">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="9fc5a-156">Next step</span></span>

<span data-ttu-id="9fc5a-157">Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.</span><span class="sxs-lookup"><span data-stu-id="9fc5a-157">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="9fc5a-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9fc5a-158">See also</span></span>

[<span data-ttu-id="9fc5a-159">Phase 2: Identität</span><span class="sxs-lookup"><span data-stu-id="9fc5a-159">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="9fc5a-160">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9fc5a-160">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="9fc5a-161">Microsoft 365 Enterprise-Bereitstellungshandbuch</span><span class="sxs-lookup"><span data-stu-id="9fc5a-161">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="9fc5a-162">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9fc5a-162">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
