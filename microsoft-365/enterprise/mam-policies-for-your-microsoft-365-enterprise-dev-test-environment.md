---
title: MAM-Richtlinien für die Microsoft 365 Enterprise-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Verwenden Sie in diesem Test Lab Guide hinzufügen, dass Intune mobilen Anwendung (MAM) Informationsverwaltungsrichtlinien in Ihrer Microsoft 365 Enterprise test Environment.
ms.openlocfilehash: f00379a5e70dce5e07c031a7647b27041d3fa9d1
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868188"
---
# <a name="mam-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="cd5ec-103">MAM-Richtlinien für die Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="cd5ec-103">MAM policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="cd5ec-104">Mit den Anweisungen in diesem Artikel fügen Sie Intune mobilen Anwendung (MAM) Informationsverwaltungsrichtlinien in Ihrer Microsoft 365 Enterprise test Environment.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-104">With the instructions in this article, you add Intune mobile application management (MAM) policies to your Microsoft 365 Enterprise test environment.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="cd5ec-106">Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="cd5ec-107">Phase 1: Erstellen Sie Ihre Umgebung für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cd5ec-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="cd5ec-108">Wenn Sie auf einfache Weise mit den Mindestanforderungen MAM Richtlinien konfigurieren möchten, befolgen Sie die Anweisungen in der [Lightweight Basiskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="cd5ec-108">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="cd5ec-109">Wenn Sie in einer simulierten Enterprise MAM Richtlinien konfigurieren möchten, befolgen Sie die Anweisungen in [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="cd5ec-109">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="cd5ec-p101">Testen der automatisiert Lizenzierung und Gruppenmitgliedschaft erfordert keinen der simulierten Enterprise-testumgebung, einschließlich einer simulierten Intranet mit dem Internet verbunden und Directory-Synchronisierung für eine Windows Server Active Directory-Gesamtstruktur. Erfolgt hier als eine Option, damit Sie automatisierte Lizenzierung und Gruppenmitgliedschaft testen können, und probieren Sie es in einer Umgebung, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-p101">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-and-deploy-mam-policies-for-ios-and-android-devices"></a><span data-ttu-id="cd5ec-112">Phase 2: Erstellen und Bereitstellen von MAM-Richtlinien für iOS- und Android-Geräte</span><span class="sxs-lookup"><span data-stu-id="cd5ec-112">Phase 2: Create and deploy MAM policies for iOS and Android devices</span></span>

<span data-ttu-id="cd5ec-113">In dieser Phase werden zwei verschiedene MAM-Richtlinien erstellt und bereitgestellt: eine für iOS-Geräte und eine für Android-Geräte.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-113">In this phase, you create and deploy two different MAM policies: one for iOS devices and one for Android devices.</span></span>
  
1. <span data-ttu-id="cd5ec-114">Wechseln Sie zu der Office 365-Portal unter ([https://portal.office.com](https://portal.office.com)) und melden Sie sich Test Office 365-Abonnement mit Ihrer globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-114">Go to the Office 365 portal at ([https://portal.office.com](https://portal.office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="cd5ec-115">Öffnen Sie auf einer neuen Registerkarte Ihres Browsers das Azure-Portal unter [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="cd5ec-115">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="cd5ec-116">Klicken Sie auf der Azure Portal Registerkarte in Internet Explorer im Navigationsbereich klicken Sie auf **alle Dienste**, geben Sie **Intune**, und klicken Sie dann auf **Intune**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-116">On the Azure portal tab in Internet Explorer, in the navigation pane, click **All services**, type **Intune**, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="cd5ec-p102">Wenn Sie auf der **Microsoft-Intune** Blade **Sie noch nicht aktiviert noch Gerätemanagement** Meldung angezeigt wird, klicken Sie darauf. Klicken Sie in der **Verwaltung mobiler Geräte Autorität** Blade auf **Intune MDM Zertifizierungsstelle**, und klicken Sie dann auf **auswählen**. Aktualisieren Sie die Registerkarte Browser.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-p102">If you see a **You haven't enabled device management yet** message on the **Microsoft Intune** blade, click it. On the **Mobile Device Management authority** blade, click **Intune MDM Authority**, and then click **Choose**. Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="cd5ec-120">Klicken Sie im linken Navigationsbereich auf **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-120">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="cd5ec-121">Klicken Sie auf das Blade **Gruppen alle Gruppen** auf **+ neue Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-121">On the **Groups-All groups** blade, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="cd5ec-122">Wählen Sie in der **Gruppe** Blade, **Office 365** für **Gruppentyp?**, geben Sie im Feld **Name** **iOS Gerätebenutzer verwaltet** , wählen Sie in **die Mitgliedschaft Typ** **zugewiesen** und dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-122">On the **Group** blade, select **Office 365** for **Group type?**, type **Managed iOS device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="cd5ec-123">Schließen Sie das Blatt **Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-123">Close the **Group** blade.</span></span>
    
9. <span data-ttu-id="cd5ec-124">Klicken Sie auf das Blade **Gruppen alle Gruppen** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-124">On the **Groups-All groups** blade, click **Add**.</span></span>
    
10. <span data-ttu-id="cd5ec-125">Wählen Sie in der **Gruppe** Blade, **Office 365** für **Gruppentyp?**, geben Sie im Feld **Name** **Android verwaltete Benutzer des Geräts** , wählen Sie in **die Mitgliedschaft Typ** **zugewiesen** und dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-125">On the **Group** blade, select **Office 365** for **Group type?**, type **Managed Android device user** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span>
    
11. <span data-ttu-id="cd5ec-126">Schließen Sie das Blade **Gruppen alle Gruppen** .</span><span class="sxs-lookup"><span data-stu-id="cd5ec-126">Close the **Groups-All groups** blade.</span></span>
    
12. <span data-ttu-id="cd5ec-127">Klicken Sie auf dem Blatt **Intune** in der Liste **Schnelle Aufgaben** auf **Erstellen Sie eine Konformitätsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-127">On the **Intune** blade, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
13. <span data-ttu-id="cd5ec-128">Klicken Sie auf dem Blatt **Kompatibilitätsrichtlinienprofile** auf **Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-128">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
14. <span data-ttu-id="cd5ec-p103">Geben Sie auf dem Blatt **Richtlinie erstellen** im Feld **Name**, den Text **iOS** ein. Wählen Sie für **Plattform** die Option **iOS** aus, klicken Sie auf dem Blatt \*\* 	iOS-Kompatibilitätsrichtlinie\*\* auf **OK**, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-p103">On the **Create Policy** blade, in **Name**, type **iOS**. In **Platform**, select **iOS**, click **OK** on the **iOS compliance policy** blade, and then click **Create**.</span></span>
    
15. <span data-ttu-id="cd5ec-131">Klicken Sie auf dem Blatt **Kompatibilitätsrichtlinienprofile** auf **Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-131">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
16. <span data-ttu-id="cd5ec-p104">Geben Sie auf dem Blatt **Richtlinie erstellen** im Feld **Name**, den Text **Android** ein. Wählen Sie für **Plattform** die Option **Android** aus, klicken Sie auf dem Blatt **Android-Kompatibilitätsrichtlinie** auf **OK**, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-p104">On the **Create Policy** blade, in **Name**, type **Android**. In **Platform**, select **Android**, click **OK** on the **Android compliance policy** blade, and then click **Create**.</span></span>
    
17. <span data-ttu-id="cd5ec-134">Klicken Sie auf dem Blatt **Kompatibilitätsrichtlinienprofile** auf den Richtliniennamen **Android**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-134">On the **Compliance Policy Profiles** blade, click the **Android** policy name.</span></span>
    
18. <span data-ttu-id="cd5ec-135">Klicken Sie im linken Navigationsbereich des Blatts **Android - Eigenschaften** auf **Zuweisungen**, und klicken Sie dann auf **Gruppen auswählen**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-135">In the left navigation of the **Android - Properties** blade, click **Assignments**, and then click **Select groups**.</span></span>
    
19. <span data-ttu-id="cd5ec-136">Klicken Sie auf dem Blatt **Gruppen auswählen** auf die Gruppe **Verwaltete Android-Gerätebenutzer**, und klicken Sie dann auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-136">On the **Select groups** blade, click the **Managed Android device users** group, and then click **Select**.</span></span>
    
20. <span data-ttu-id="cd5ec-137">Klicken Sie auf **Speichern**, und schließen Sie das Blade **Android - Zuordnungen** .</span><span class="sxs-lookup"><span data-stu-id="cd5ec-137">Click **Save**, and then close the **Android - Assignments** blade.</span></span>
    
21. <span data-ttu-id="cd5ec-138">Klicken Sie auf dem Blatt **Kompatibilitätsrichtlinienprofile** auf den Richtliniennamen **iOS**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-138">On the **Compliance Policy Profiles** blade, click the **iOS** policy name.</span></span>
    
22. <span data-ttu-id="cd5ec-139">Klicken Sie im linken Navigationsbereich des Blatts **iOS - Eigenschaften** auf **Zuweisungen**, und klicken Sie dann auf **Gruppen auswählen**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-139">In the left navigation of the **iOS - Properties** blade, click **Assignments**, and then click **Select groups**.</span></span>
    
23. <span data-ttu-id="cd5ec-140">Klicken Sie auf dem Blatt **Gruppen auswählen** auf die Gruppe **Verwaltete iOS-Gerätebenutzer**, und klicken Sie dann auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-140">On the **Select groups** blade, click the **Managed iOS device users** group, and then click **Select**.</span></span>
    
24. <span data-ttu-id="cd5ec-141">Klicken Sie auf **Speichern**, und schließen Sie das Blade **iOS - Zuordnungen** .</span><span class="sxs-lookup"><span data-stu-id="cd5ec-141">Click **Save**, and then close the **iOS - Assignments** blade.</span></span>
    
25. <span data-ttu-id="cd5ec-142">Schließen Sie das Blatt **Kompatibilitätsrichtlinienprofile**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-142">Close the **Compliance Policy Profiles** blade.</span></span>
    
26. <span data-ttu-id="cd5ec-143">Klicken Sie auf dem Blatt **Intune** im linken Navigationsbereich auf **Apps verwalten**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-143">On the **Intune** blade, click **Manage apps** in the left navigation.</span></span>
    
27. <span data-ttu-id="cd5ec-144">Klicken Sie auf dem Blatt **Mobile Apps** auf **Apps**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-144">On the **Mobile Apps** blade, click **Apps**.</span></span>
    
28. <span data-ttu-id="cd5ec-145">Klicken Sie in der Liste der Apps auf **PowerPoint**. </span><span class="sxs-lookup"><span data-stu-id="cd5ec-145">In the list of apps, click **PowerPoint**,</span></span> 
    
29. <span data-ttu-id="cd5ec-p105">Klicken Sie auf dem Blatt **PowerPoint-Übersicht** auf **Zuweisungen > Gruppen auswählen > Verwaltete iOS-Geräte > Auswählen**. Wählen Sie im Feld **Typ** die Option **Verfügbar** aus, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-p105">On the **PowerPoint Overview** blade, click **Assignments > Select groups > Managed iOS devices > Select**. In **Type**, select **Available**, and then click **Save**.</span></span>
    
30. <span data-ttu-id="cd5ec-148">Wiederholen Sie Schritt 29 für die folgenden apps:</span><span class="sxs-lookup"><span data-stu-id="cd5ec-148">Repeat step 29 for the following apps:</span></span>
    
    - <span data-ttu-id="cd5ec-149">Outlook für Android</span><span class="sxs-lookup"><span data-stu-id="cd5ec-149">Outlook for Android</span></span>
    
    - <span data-ttu-id="cd5ec-150">Word für iOS</span><span class="sxs-lookup"><span data-stu-id="cd5ec-150">Word for iOS</span></span>
    
    - <span data-ttu-id="cd5ec-151">Excel für iOS</span><span class="sxs-lookup"><span data-stu-id="cd5ec-151">Excel for iOS</span></span>
    
    - <span data-ttu-id="cd5ec-152">Outlook für iOS</span><span class="sxs-lookup"><span data-stu-id="cd5ec-152">Outlook for iOS</span></span>
    
    - <span data-ttu-id="cd5ec-153">Microsoft Dynamics CRM auf iPad für iOS</span><span class="sxs-lookup"><span data-stu-id="cd5ec-153">Microsoft Dynamics CRM on iPad for iOS</span></span>
    
    - <span data-ttu-id="cd5ec-154">Microsoft Dynamics CRM auf iPhone für iOS</span><span class="sxs-lookup"><span data-stu-id="cd5ec-154">Microsoft Dynamics CRM on iPhone for iOS</span></span>
    
    - <span data-ttu-id="cd5ec-155">Dynamics CRM für Smartphones für Android</span><span class="sxs-lookup"><span data-stu-id="cd5ec-155">Dynamics CRM for Phones for Android</span></span>
    
    - <span data-ttu-id="cd5ec-156">Dynamics CRM für Tablets für Android</span><span class="sxs-lookup"><span data-stu-id="cd5ec-156">Dynamics CRM for Tablets for Android</span></span>
    
    - <span data-ttu-id="cd5ec-157">Excel für Android</span><span class="sxs-lookup"><span data-stu-id="cd5ec-157">Excel for Android</span></span>
    
    - <span data-ttu-id="cd5ec-158">Word für Android</span><span class="sxs-lookup"><span data-stu-id="cd5ec-158">Word for Android</span></span>
    
    - <span data-ttu-id="cd5ec-159">OneNote für iOS</span><span class="sxs-lookup"><span data-stu-id="cd5ec-159">OneNote for iOS</span></span>
    
31. <span data-ttu-id="cd5ec-160">Schließen Sie das Blatt **Mobile Apps - Apps**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-160">Close the **Mobile Apps - Apps** blade.</span></span>
    
32. <span data-ttu-id="cd5ec-161">Klicken Sie auf dem Blatt **Mobile Apps** auf **App-Schutzrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-161">On the **Mobile Apps** blade, click **App Protection Policies**.</span></span>
    
33. <span data-ttu-id="cd5ec-162">Klicken Sie auf dem Blatt **App-Schutzrichtlinien** auf **Richtlinie hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-162">On the **App Protection Policies** blade, click **Add a policy**.</span></span>
    
34. <span data-ttu-id="cd5ec-163">Geben Sie auf dem Blatt **Richtlinie hinzufügen** den Namen **iOS** ein, und klicken Sie dann auf **Erforderliche Apps auswählen**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-163">On the **Add a policy** blade, type **iOS**, and then click **Select required apps**.</span></span>
    
35. <span data-ttu-id="cd5ec-164">Klicken Sie auf dem Blatt **Apps** auf **PowerPoint**, **Microsoft Dynamics CRM auf iPhone**, **Excel**, **Microsoft Dynamics CRM auf iPhone**, **Word**, **OneNote** und **Outlook**, und klicken Sie dann auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-164">On the **Apps** blade, click **PowerPoint**, **Microsoft Dynamics CRM on iPhone**, **Excel**, **Microsoft Dynamics CRM on iPhone**, **Word**, **OneNote**, and **Outlook**, and then click **Select**.</span></span>
    
36. <span data-ttu-id="cd5ec-165">Klicken Sie auf dem Blatt **Richtlinie hinzufügen** auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-165">On the **Add a policy** blade, click **Create**.</span></span>
    
37. <span data-ttu-id="cd5ec-166">Klicken Sie auf dem Blatt **App-Schutzrichtlinien** auf **Richtlinie hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-166">On the **App Protection Policies** blade, click **Add a policy**.</span></span>
    
38. <span data-ttu-id="cd5ec-167">Geben Sie auf dem Blatt **Richtlinie hinzufügen** den Namen **Android** ein, wählen Sie unter **Plattform** die Option **Android** aus, und klicken Sie dann auf **Erforderliche Apps auswählen**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-167">On the **Add a policy** blade, type **Android**, select **Android** in **Platform**, and then click **Select required apps**.</span></span>
    
39. <span data-ttu-id="cd5ec-168">Klicken Sie auf dem Blatt **Apps** auf **PowerPoint**, **Dynamics CRM für Tablets**, **Excel**, **Word**, **Outlook** und **Dynamics CRM für Smartphones**, und klicken Sie dann auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-168">On the **Apps** blade, click **PowerPoint**, **Dynamics CRM for tablets**, **Excel**, **Word**, **Outlook**, and **Dynamics CRM for phones**, and then click **Select**.</span></span>
    
40. <span data-ttu-id="cd5ec-169">Klicken Sie auf dem Blatt **Richtlinie hinzufügen** auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-169">On the **Add a policy** blade, click **Create**.</span></span>
    
<span data-ttu-id="cd5ec-170">Sie nun verfügen über zwei MAM-Richtlinien, eine für iOS-Geräte und eine für Android-Geräte, und können nun mit verschiedenen Einstellungen für die ausgewählten Apps experimentieren.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-170">You now have two MAM policies, one for iOS devices and one for Android devices, and are ready to experiment with testing settings for the selected apps.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="cd5ec-171">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="cd5ec-171">Next step</span></span>

<span data-ttu-id="cd5ec-172">Hier finden Sie zusätzliche [Verwaltung mobiler Geräte](m365-enterprise-test-lab-guides.md#mobile-device-management) Features und Funktionen in Ihrer testumgebung.</span><span class="sxs-lookup"><span data-stu-id="cd5ec-172">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="cd5ec-173">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd5ec-173">See also</span></span>

<span data-ttu-id="cd5ec-174">[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="cd5ec-174">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="cd5ec-175">Registrieren von iOS- und Android-Geräten in Ihrer Testumgebung für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cd5ec-175">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="cd5ec-176">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cd5ec-176">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="cd5ec-177">Enterprise-Mobilität + Sicherheit (zur Abstimmung)</span><span class="sxs-lookup"><span data-stu-id="cd5ec-177">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
