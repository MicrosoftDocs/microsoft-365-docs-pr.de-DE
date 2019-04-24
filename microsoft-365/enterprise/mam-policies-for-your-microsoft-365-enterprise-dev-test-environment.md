---
title: Geräte Konformitätsrichtlinien für Ihre Microsoft 365 Enterprise-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Verwenden Sie dieses Test Labor Handbuch, um der Microsoft 365 Enterprise-Testumgebung InTune-Geräte Konformitätsrichtlinien hinzuzufügen.
ms.openlocfilehash: 5b587bd702071f325310ebd9979cf611f20e3205
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279063"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="c72dc-103">Geräte Konformitätsrichtlinien für Ihre Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="c72dc-103">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="c72dc-104">Mit den Anweisungen in diesem Artikel fügen Sie Ihrer Microsoft 365 Enterprise-Testumgebung eine InTune-Geräte Konformitätsrichtlinie hinzu.</span><span class="sxs-lookup"><span data-stu-id="c72dc-104">With the instructions in this article, you add an Intune device compliance policy to your Microsoft 365 Enterprise test environment.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="c72dc-106">Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c72dc-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="c72dc-107">Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="c72dc-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="c72dc-108">Wenn Sie MAM-Richtlinien nur auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="c72dc-108">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="c72dc-109">Wenn Sie MAM-Richtlinien in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Passthrough-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="c72dc-109">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c72dc-110">Das Testen der automatisierten Lizenzierung und der Gruppenmitgliedschaft erfordert nicht die simulierte Enterprise-Testumgebung, die ein simuliertes Intranet enthält, das mit dem Internet und der Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="c72dc-110">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="c72dc-111">Sie wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und die Gruppenmitgliedschaft testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="c72dc-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="c72dc-112">Phase 2: Erstellen einer Geräte Konformitätsrichtlinie für Windows 10-Geräte</span><span class="sxs-lookup"><span data-stu-id="c72dc-112">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="c72dc-113">In dieser Phase erstellen Sie eine Geräte Konformitätsrichtlinie für Windows 10-Geräte.</span><span class="sxs-lookup"><span data-stu-id="c72dc-113">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="c72dc-114">Wechseln Sie zum Office-Portal unter[https://office.com](https://office.com)(), und melden Sie sich bei ihrem Office 365-Testabonnement mit ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="c72dc-114">Go to the Office portal at ([https://office.com](https://office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="c72dc-115">Öffnen Sie auf einer neuen Registerkarte Ihres Browsers das Azure-Portal [https://portal.azure.com](https://portal.azure.com)unter.</span><span class="sxs-lookup"><span data-stu-id="c72dc-115">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="c72dc-116">Klicken Sie auf der Registerkarte Azure Portal in Ihrem Browser im Navigationsbereich auf **alle Dienste**, geben Sie **InTune**ein, und klicken Sie dann auf **InTune**.</span><span class="sxs-lookup"><span data-stu-id="c72dc-116">On the Azure portal tab in your browser, in the navigation pane, click **All services**, type **Intune**, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="c72dc-117">Wenn Sie auf dem **Microsoft InTune** -Blatt eine Meldung zur **Geräteverwaltung noch nicht aktiviert haben** , klicken Sie darauf.</span><span class="sxs-lookup"><span data-stu-id="c72dc-117">If you see a **You haven't enabled device management yet** message on the **Microsoft Intune** blade, click it.</span></span> <span data-ttu-id="c72dc-118">Klicken Sie auf dem Blatt für die **Verwaltung mobiler Geräte** auf **InTune MDM Authority**, und klicken Sie dann auf **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="c72dc-118">On the **Mobile Device Management authority** blade, click **Intune MDM Authority**, and then click **Choose**.</span></span> <span data-ttu-id="c72dc-119">Aktualisieren Sie die Registerkarte Browser.</span><span class="sxs-lookup"><span data-stu-id="c72dc-119">Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="c72dc-120">Klicken Sie im linken Navigationsbereich auf **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="c72dc-120">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="c72dc-121">Klicken Sie auf dem Blatt **Gruppen-alle Gruppen** auf **+ neue Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="c72dc-121">On the **Groups-All groups** blade, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="c72dc-122">wählen sie im **gruppen** blatt **Office 365** für gruppentyp **?** aus, geben sie **verwaltete Windows 10-geräte benutzer** unter **Name**ein, wählen sie **zugewiesen** unter mitgliedschafts aus, und klicken sie dann auf **erstellen**. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c72dc-122">On the **Group** blade, select **Office 365** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="c72dc-123">Schließen Sie das Blatt **Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="c72dc-123">Close the **Group** blade.</span></span>
    
11. <span data-ttu-id="c72dc-124">Schließt das Blatt **Groups-all Groups** .</span><span class="sxs-lookup"><span data-stu-id="c72dc-124">Close the **Groups-All groups** blade.</span></span>
    
12. <span data-ttu-id="c72dc-125">Klicken Sie auf dem **Microsoft InTune** -Blade in der Liste **schnell Aufgaben** auf **Konformitätsrichtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="c72dc-125">On the **Microsoft Intune** blade, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
13. <span data-ttu-id="c72dc-126">Klicken Sie auf dem Blatt **Kompatibilitätsrichtlinienprofile** auf **Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="c72dc-126">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
14. <span data-ttu-id="c72dc-127">Geben Sie auf dem Blatt **Richtlinie erstellen** unter **Name den Namen** **Windows 10**ein.</span><span class="sxs-lookup"><span data-stu-id="c72dc-127">On the **Create Policy** blade, in **Name**, type **Windows 10**.</span></span> <span data-ttu-id="c72dc-128">Wählen Sie unter **Plattform**die Option **Windows 10 und höher**aus, klicken Sie auf dem Blatt **Windows 10-Konformitätsrichtlinie** auf **OK** , und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="c72dc-128">In **Platform**, select **Windows 10 and later**, click **OK** on the **Windows 10 compliance policy** blade, and then click **Create**.</span></span> <span data-ttu-id="c72dc-129">Schließt das **Windows 10** -Blade.</span><span class="sxs-lookup"><span data-stu-id="c72dc-129">Close the **Windows 10** blade.</span></span>
    
15. <span data-ttu-id="c72dc-130">Klicken Sie auf dem Blatt **Kompatibilitätsrichtlinien profile** auf den Richtliniennamen **Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="c72dc-130">On the **Compliance Policy Profiles** blade, click the **Windows 10** policy name.</span></span>
    
16. <span data-ttu-id="c72dc-131">Klicken Sie auf dem Blade **Windows 10** auf **Zuweisungen**, und klicken Sie dann auf einzuschließende **Gruppen auswählen**.</span><span class="sxs-lookup"><span data-stu-id="c72dc-131">On the **Windows 10** blade, click **Assignments**, and then click **Select groups to include**.</span></span>
    
17. <span data-ttu-id="c72dc-132">Klicken Sie auf dem Blade **zu verwendende Gruppen auswählen** auf die Gruppe **verwaltete Windows 10-Geräte Benutzer** , und klicken Sie dann auf **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="c72dc-132">On the **Select groups to include** blade, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
18. <span data-ttu-id="c72dc-133">Klicken Sie auf **Speichern**, und schließen Sie dann das Blade **Windows 10-Assignments** .</span><span class="sxs-lookup"><span data-stu-id="c72dc-133">Click **Save**, and then close the **Windows 10 - Assignments** blade.</span></span>
    
19. <span data-ttu-id="c72dc-134">Schließen Sie das Blatt **Kompatibilitätsrichtlinienprofile**.</span><span class="sxs-lookup"><span data-stu-id="c72dc-134">Close the **Compliance Policy Profiles** blade.</span></span>
    
20. <span data-ttu-id="c72dc-135">Klicken Sie auf dem **Microsoft InTune** -Blatt im linken navigationsBereich auf **Client-apps** .</span><span class="sxs-lookup"><span data-stu-id="c72dc-135">On the **Microsoft Intune** blade, click **Client apps** in the left navigation.</span></span>
    
21. <span data-ttu-id="c72dc-136">Klicken Sie auf dem Blatt **Client apps** auf **apps**, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c72dc-136">On the **Client Apps** blade, click **Apps**, and then click **Add**.</span></span> 

22. <span data-ttu-id="c72dc-137">Wählen Sie im Blade **app hinzufügen** die Option **App-Typ**aus, und wählen Sie dann **Windows 10** unter **Office 365 Suite**aus.</span><span class="sxs-lookup"><span data-stu-id="c72dc-137">In the **Add app** blade, select **App type**, and then select **Windows 10** under **Office 365 Suite**.</span></span>

23. <span data-ttu-id="c72dc-138">Klicken Sie auf **App-Suite konfigurieren**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c72dc-138">Click **Configure App Suite**, and then click **OK**.</span></span>

24. <span data-ttu-id="c72dc-139">Klicken Sie auf **App-Suite-Informationen**, geben Sie Office- **Apps für Windows 10** unter **Suite Name**, **Office-Apps für Windows 10** in **Suite Description**ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c72dc-139">Click **App Suite Information**, type **Office Apps for Windows 10** in **Suite Name**, **Office Apps for Windows 10** in **Suite Description**, and then click **OK**.</span></span>

25. <span data-ttu-id="c72dc-140">Klicken Sie auf **App**-suiteeinstellungen, wählen Sie **halbjährlich** im **Kanal aktualisieren**aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c72dc-140">Click **App Suite Settings**, select **Semi-Annual** in **Update channel**, and then click **OK**.</span></span>

26. <span data-ttu-id="c72dc-141">Klicken Sie auf dem Blatt **app hinzufügen** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c72dc-141">On the **Add app** blade, click **Add**.</span></span>

<span data-ttu-id="c72dc-142">Sie verfügen jetzt über eine Geräte Konformitätsrichtlinie zum Testen der ausgewählten apps in der **Windows 10** -Geräte Konformitätsrichtlinie und für Mitglieder der **verwalteten Windows 10-Geräte Benutzer** Gruppe.</span><span class="sxs-lookup"><span data-stu-id="c72dc-142">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="c72dc-143">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="c72dc-143">Next step</span></span>

<span data-ttu-id="c72dc-144">Erkunden Sie zusätzliche Features und Funktionen für die [Verwaltung mobiler Geräte](m365-enterprise-test-lab-guides.md#mobile-device-management) in Ihrer Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="c72dc-144">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="c72dc-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c72dc-145">See also</span></span>

<span data-ttu-id="c72dc-146">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="c72dc-146">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="c72dc-147">Registrieren von iOS-und Android-Geräten in Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="c72dc-147">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="c72dc-148">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c72dc-148">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="c72dc-149">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="c72dc-149">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
