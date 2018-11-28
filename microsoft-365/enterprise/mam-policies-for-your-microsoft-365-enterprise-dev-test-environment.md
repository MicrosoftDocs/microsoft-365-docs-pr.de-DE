---
title: Gerät Kompatibilitätsrichtlinien für Ihr Unternehmen der Microsoft 365 test Environment.
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Verwenden Sie in diesem Test Lab Guide hinzufügen, dass Intune Gerät Kompatibilitätsrichtlinien zu Ihrem Unternehmen der Microsoft 365 test Environment.
ms.openlocfilehash: 73e22d3f5760d3b9cbd4b5391030d29c77815094
ms.sourcegitcommit: 42e4d280b562304335efc93787c89992504c5823
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "26538672"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="9c1af-103">Gerät Kompatibilitätsrichtlinien für Ihr Unternehmen der Microsoft 365 test Environment.</span><span class="sxs-lookup"><span data-stu-id="9c1af-103">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="9c1af-104">Mit den Anweisungen in diesem Artikel fügen Sie eine Richtlinie Intune Geräte Kompatibilität in Ihrer testumgebung Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="9c1af-104">With the instructions in this article, you add an Intune device compliance policy to your Microsoft 365 Enterprise test environment.</span></span>

![Testumgebungsanleitungen für die Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="9c1af-106">Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="9c1af-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="9c1af-107">Phase 1: Erstellen Sie Ihre Umgebung für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9c1af-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="9c1af-108">Wenn Sie auf einfache Weise mit den Mindestanforderungen MAM Richtlinien konfigurieren möchten, befolgen Sie die Anweisungen in der [Lightweight Basiskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="9c1af-108">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="9c1af-109">Wenn Sie in einer simulierten Enterprise MAM Richtlinien konfigurieren möchten, befolgen Sie die Anweisungen in [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="9c1af-109">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9c1af-p101">Testen der automatisiert Lizenzierung und Gruppenmitgliedschaft erfordert keinen der simulierten Enterprise-testumgebung, einschließlich einer simulierten Intranet mit dem Internet verbunden und Directory-Synchronisierung für eine Windows Server Active Directory-Gesamtstruktur. Erfolgt hier als eine Option, damit Sie automatisierte Lizenzierung und Gruppenmitgliedschaft testen können, und probieren Sie es in einer Umgebung, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="9c1af-p101">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="9c1af-112">Phase 2: Erstellen einer Richtlinie für Geräte Compliance für Windows 10 Geräte</span><span class="sxs-lookup"><span data-stu-id="9c1af-112">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="9c1af-113">In dieser Phase erstellen Sie eine Richtlinie für Geräte Compliance für Windows 10 Geräte.</span><span class="sxs-lookup"><span data-stu-id="9c1af-113">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="9c1af-114">Wechseln Sie zu der Office-Portal unter ([https://office.com](https://office.com)) und melden Sie sich Test Office 365-Abonnement mit Ihrer globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="9c1af-114">Go to the Office portal at ([https://office.com](https://office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="9c1af-115">Öffnen Sie auf einer neuen Registerkarte Ihres Browsers das Azure-Portal unter [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="9c1af-115">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="9c1af-116">Klicken Sie auf der Azure Portal Registerkarte in Ihrem Browser, klicken Sie im Navigationsbereich klicken Sie auf **alle Dienste**, geben Sie **Intune**, und klicken Sie dann auf **Intune**.</span><span class="sxs-lookup"><span data-stu-id="9c1af-116">On the Azure portal tab in your browser, in the navigation pane, click **All services**, type **Intune**, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="9c1af-p102">Wenn Sie auf der **Microsoft-Intune** Blade **Sie noch nicht aktiviert noch Gerätemanagement** Meldung angezeigt wird, klicken Sie darauf. Klicken Sie in der **Verwaltung mobiler Geräte Autorität** Blade auf **Intune MDM Zertifizierungsstelle**, und klicken Sie dann auf **auswählen**. Aktualisieren Sie die Registerkarte Browser.</span><span class="sxs-lookup"><span data-stu-id="9c1af-p102">If you see a **You haven't enabled device management yet** message on the **Microsoft Intune** blade, click it. On the **Mobile Device Management authority** blade, click **Intune MDM Authority**, and then click **Choose**. Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="9c1af-120">Klicken Sie im linken Navigationsbereich auf **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="9c1af-120">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="9c1af-121">Klicken Sie auf das Blade **Gruppen alle Gruppen** auf **+ neue Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="9c1af-121">On the **Groups-All groups** blade, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="9c1af-122">Wählen Sie in der **Gruppe** Blade, **Office 365** für **Gruppentyp?**, geben Sie im Feld **Name** **Gerätebenutzer verwalteten Windows 10** , wählen Sie in **die Mitgliedschaft Typ** **zugewiesen** und dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="9c1af-122">On the **Group** blade, select **Office 365** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="9c1af-123">Schließen Sie das Blatt **Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="9c1af-123">Close the **Group** blade.</span></span>
    
11. <span data-ttu-id="9c1af-124">Schließen Sie das Blade **Gruppen alle Gruppen** .</span><span class="sxs-lookup"><span data-stu-id="9c1af-124">Close the **Groups-All groups** blade.</span></span>
    
12. <span data-ttu-id="9c1af-125">Klicken Sie auf der **Microsoft Intune** Blade, in der Liste **schnell Aufgaben** **Erstellen einer Compliance-Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="9c1af-125">On the **Microsoft Intune** blade, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
13. <span data-ttu-id="9c1af-126">Klicken Sie auf dem Blatt **Kompatibilitätsrichtlinienprofile** auf **Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="9c1af-126">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
14. <span data-ttu-id="9c1af-p103">Geben Sie auf der Blade **-Richtlinie erstellen** im Feld **Name** **Windows 10**. **Plattform**wählen Sie **Windows 10 und höher**, klicken Sie auf **OK** , auf dem **Windows-10-Compliance-Richtlinien** -Blade, und klicken Sie dann auf **Erstellen**. Schließen Sie das **Windows-10** -Blade.</span><span class="sxs-lookup"><span data-stu-id="9c1af-p103">On the **Create Policy** blade, in **Name**, type **Windows 10**. In **Platform**, select **Windows 10 and later**, click **OK** on the **Windows 10 compliance policy** blade, and then click **Create**. Close the **Windows 10** blade.</span></span>
    
15. <span data-ttu-id="9c1af-130">Klicken Sie auf das Blade **Compliance Richtlinienprofilen** auf den Namen der Richtlinie **Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="9c1af-130">On the **Compliance Policy Profiles** blade, click the **Windows 10** policy name.</span></span>
    
16. <span data-ttu-id="9c1af-131">Klicken Sie in der **Windows-10** -Blade auf **Aufgaben**, und klicken Sie dann auf **Gruppen enthalten auswählen**.</span><span class="sxs-lookup"><span data-stu-id="9c1af-131">On the **Windows 10** blade, click **Assignments**, and then click **Select groups to include**.</span></span>
    
17. <span data-ttu-id="9c1af-132">Klicken Sie in der Blade **Gruppen enthalten auswählen** auf der **Windows-10 verwaltete Gerät** Benutzergruppe, und klicken Sie dann auf **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="9c1af-132">On the **Select groups to include** blade, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
18. <span data-ttu-id="9c1af-133">Klicken Sie auf **Speichern**, und schließen Sie das **Windows-10 - Zuordnungen** Blade.</span><span class="sxs-lookup"><span data-stu-id="9c1af-133">Click **Save**, and then close the **Windows 10 - Assignments** blade.</span></span>
    
19. <span data-ttu-id="9c1af-134">Schließen Sie das Blatt **Kompatibilitätsrichtlinienprofile**.</span><span class="sxs-lookup"><span data-stu-id="9c1af-134">Close the **Compliance Policy Profiles** blade.</span></span>
    
20. <span data-ttu-id="9c1af-135">Klicken Sie auf der **Microsoft-Intune** Blade im linken Navigationsbereich auf **Client-apps** .</span><span class="sxs-lookup"><span data-stu-id="9c1af-135">On the **Microsoft Intune** blade, click **Client apps** in the left navigation.</span></span>
    
21. <span data-ttu-id="9c1af-136">Klicken Sie in den **Clientanwendungen** Blade auf **Apps**, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="9c1af-136">On the **Client Apps** blade, click **Apps**, and then click **Add**.</span></span> 

22. <span data-ttu-id="9c1af-137">Wählen Sie in der Blade- **app hinzufügen** **App-Typ**aus, und wählen Sie dann **Windows 10** unter **Office 365-Suite**.</span><span class="sxs-lookup"><span data-stu-id="9c1af-137">In the **Add app** blade, select **App type**, and then select **Windows 10** under **Office 365 Suite**.</span></span>

23. <span data-ttu-id="9c1af-138">Klicken Sie auf **App-Suite konfigurieren**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9c1af-138">Click **Configure App Suite**, and then click **OK**.</span></span>

24. <span data-ttu-id="9c1af-139">Klicken Sie auf **Informationen für App-Suite**, geben Sie **Office-Apps für Windows 10** **Suite Name**, **Office-Apps für Windows 10** in **Suite Beschreibung**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9c1af-139">Click **App Suite Information**, type **Office Apps for Windows 10** in **Suite Name**, **Office Apps for Windows 10** in **Suite Description**, and then click **OK**.</span></span>

25. <span data-ttu-id="9c1af-140">Klicken Sie auf **App-Suite-Einstellungen**, wählen Sie **Semikolons jährlichen** in **Update-Kanal**aus und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9c1af-140">Click **App Suite Settings**, select **Semi-Annual** in **Update channel**, and then click **OK**.</span></span>

26. <span data-ttu-id="9c1af-141">Klicken Sie auf das Blade **app hinzufügen** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="9c1af-141">On the **Add app** blade, click **Add**.</span></span>

<span data-ttu-id="9c1af-142">Sie haben nun eine Gerät Compliance-Richtlinie für den ausgewählten apps in die **Windows-10** Gerät Compliance-Richtlinien Tests und Mitglieder der Gruppe **verwaltete Windows 10 Gerätebenutzer** .</span><span class="sxs-lookup"><span data-stu-id="9c1af-142">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="9c1af-143">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="9c1af-143">Next step</span></span>

<span data-ttu-id="9c1af-144">Hier finden Sie zusätzliche [Verwaltung mobiler Geräte](m365-enterprise-test-lab-guides.md#mobile-device-management) Features und Funktionen in Ihrer testumgebung.</span><span class="sxs-lookup"><span data-stu-id="9c1af-144">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="9c1af-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c1af-145">See also</span></span>

<span data-ttu-id="9c1af-146">[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="9c1af-146">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="9c1af-147">Registrieren von iOS- und Android-Geräten in Ihrer Testumgebung für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9c1af-147">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="9c1af-148">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9c1af-148">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="9c1af-149">Enterprise-Mobilität + Sicherheit (zur Abstimmung)</span><span class="sxs-lookup"><span data-stu-id="9c1af-149">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
