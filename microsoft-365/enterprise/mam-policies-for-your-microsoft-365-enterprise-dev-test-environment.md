---
title: Geräte Konformitätsrichtlinien für Ihre Microsoft 365 Enterprise-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Verwenden Sie diese Test Umgebungs Anleitung, um InTune-Geräte Konformitätsrichtlinien zu Ihrer Microsoft 365 Enterprise-Testumgebung hinzuzufügen.
ms.openlocfilehash: c323779399f6f440e1f9104e6611023a18ffe59e
ms.sourcegitcommit: ea48c86c727dcd9d4b3b970b14a4260337f158f9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2019
ms.locfileid: "38694102"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="adcc9-103">Geräte Konformitätsrichtlinien für Ihre Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="adcc9-103">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="adcc9-104">*Diese Testumgebungsanleitung kann nur für Microsoft 365 Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="adcc9-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="adcc9-105">Mit den Anweisungen in diesem Artikel fügen Sie eine InTune-Geräte Konformitätsrichtlinie zu Ihrer Microsoft 365 Enterprise-Testumgebung hinzu.</span><span class="sxs-lookup"><span data-stu-id="adcc9-105">With the instructions in this article, you add an Intune device compliance policy to your Microsoft 365 Enterprise test environment.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="adcc9-107">Klicken Sie [hier](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="adcc9-107">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="adcc9-108">Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="adcc9-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="adcc9-109">Wenn Sie MAM-Richtlinien nur auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="adcc9-109">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="adcc9-110">Wenn Sie MAM-Richtlinien in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="adcc9-110">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="adcc9-111">Für das Testen der automatischen Lizenzierung und der Gruppenmitgliedschaft ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst.</span><span class="sxs-lookup"><span data-stu-id="adcc9-111">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="adcc9-112">Sie wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="adcc9-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="adcc9-113">Phase 2: Erstellen einer Geräte Kompatibilitäts Richtlinie für Windows 10-Geräte</span><span class="sxs-lookup"><span data-stu-id="adcc9-113">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="adcc9-114">In dieser Phase erstellen Sie eine Geräte Kompatibilitäts Richtlinie für Windows 10-Geräte.</span><span class="sxs-lookup"><span data-stu-id="adcc9-114">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="adcc9-115">Wechseln Sie zum Office 365 Portal unter ([https://portal.office.com](https://portal.office.com)), und melden Sie sich bei Ihrem Office 365 Test Lab-Abonnement mit ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="adcc9-115">Go to the Office 365 portal at ([https://portal.office.com](https://portal.office.com)) and sign in to your Office 365 test lab subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="adcc9-116">Öffnen Sie auf einer neuen Registerkarte Ihres Browsers das Azure-Portal [https://portal.azure.com](https://portal.azure.com)unter.</span><span class="sxs-lookup"><span data-stu-id="adcc9-116">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="adcc9-117">Klicken Sie auf der Registerkarte Azure Portal in Ihrem Browser im Navigationsbereich auf **alle Dienste**, geben Sie **InTune**ein, und klicken Sie dann auf **InTune**.</span><span class="sxs-lookup"><span data-stu-id="adcc9-117">On the Azure portal tab in your browser, in the navigation pane, click **All services**, type **Intune**, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="adcc9-118">Wenn Sie auf dem **Microsoft InTune** -Blade sehen, dass die Meldung **Geräteverwaltung noch nicht aktiviert** ist, klicken Sie darauf.</span><span class="sxs-lookup"><span data-stu-id="adcc9-118">If you see a **You haven't enabled device management yet** message on the **Microsoft Intune** blade, click it.</span></span> <span data-ttu-id="adcc9-119">Klicken Sie auf dem Blatt der **Verwaltungsautorität der mobilen Geräte** auf **InTune-MDM-Autorität**und dann auf **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="adcc9-119">On the **Mobile Device Management authority** blade, click **Intune MDM Authority**, and then click **Choose**.</span></span> <span data-ttu-id="adcc9-120">Aktualisieren Sie die Registerkarte Browser.</span><span class="sxs-lookup"><span data-stu-id="adcc9-120">Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="adcc9-121">Klicken Sie im linken Navigationsbereich auf **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="adcc9-121">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="adcc9-122">Klicken Sie auf dem Blatt **Gruppen-alle Gruppen** auf **+ neue Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="adcc9-122">On the **Groups-All groups** blade, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="adcc9-123">Wählen Sie auf dem **Gruppen** Blatt **Office 365** oder **Sicherheit** für **Gruppentyp?**, geben Sie **verwaltete Windows 10-Geräte Benutzer** unter **Name**ein, wählen Sie in **Mitgliedschafts** **zugewiesen** aus, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="adcc9-123">On the **Group** blade, select **Office 365** or **Security** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="adcc9-124">Schließen Sie das Blatt **Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="adcc9-124">Close the **Group** blade.</span></span>
    
11. <span data-ttu-id="adcc9-125">Schließen Sie das Blade **Gruppen – alle Gruppen** .</span><span class="sxs-lookup"><span data-stu-id="adcc9-125">Close the **Groups-All groups** blade.</span></span>
    
12. <span data-ttu-id="adcc9-126">Klicken Sie auf dem **Microsoft InTune** -Blade in der Liste **schnell Aufgaben** auf **Konformitätsrichtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="adcc9-126">On the **Microsoft Intune** blade, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
13. <span data-ttu-id="adcc9-127">Klicken Sie auf dem Blatt **Kompatibilitätsrichtlinienprofile** auf **Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="adcc9-127">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
14. <span data-ttu-id="adcc9-128">Geben Sie auf dem Blatt **Richtlinien erstellen** unter **Name den Namen** **Windows 10**ein.</span><span class="sxs-lookup"><span data-stu-id="adcc9-128">On the **Create Policy** blade, in **Name**, type **Windows 10**.</span></span> <span data-ttu-id="adcc9-129">Wählen Sie unter **Plattform**die Option **Windows 10 und höher**aus, klicken Sie auf dem Blade **Windows 10-Konformitätsrichtlinie** auf **OK** , und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="adcc9-129">In **Platform**, select **Windows 10 and later**, click **OK** on the **Windows 10 compliance policy** blade, and then click **Create**.</span></span> <span data-ttu-id="adcc9-130">Schließen Sie das **Windows 10** -Blade.</span><span class="sxs-lookup"><span data-stu-id="adcc9-130">Close the **Windows 10** blade.</span></span>
    
15. <span data-ttu-id="adcc9-131">Klicken Sie auf dem Blatt **Konformitätsrichtlinien profile** auf den Richtliniennamen **Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="adcc9-131">On the **Compliance Policy Profiles** blade, click the **Windows 10** policy name.</span></span>
    
16. <span data-ttu-id="adcc9-132">Klicken Sie auf dem **Windows 10** -Blade auf **Zuweisungen**, und klicken Sie dann auf **einzubeziehende Gruppen auswählen**.</span><span class="sxs-lookup"><span data-stu-id="adcc9-132">On the **Windows 10** blade, click **Assignments**, and then click **Select groups to include**.</span></span>
    
17. <span data-ttu-id="adcc9-133">Klicken Sie auf der Gruppe **zum einschließen** von Blade-Gruppen auswählen auf die Gruppe **verwaltete Windows 10-Geräte Benutzer** , und klicken Sie dann auf **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="adcc9-133">On the **Select groups to include** blade, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
18. <span data-ttu-id="adcc9-134">Klicken Sie auf **Speichern**, und schließen Sie dann das Blade **Windows 10-Assignments** .</span><span class="sxs-lookup"><span data-stu-id="adcc9-134">Click **Save**, and then close the **Windows 10 - Assignments** blade.</span></span>
    
19. <span data-ttu-id="adcc9-135">Schließen Sie das Blatt **Kompatibilitätsrichtlinienprofile**.</span><span class="sxs-lookup"><span data-stu-id="adcc9-135">Close the **Compliance Policy Profiles** blade.</span></span>
    
20. <span data-ttu-id="adcc9-136">Klicken Sie auf dem **Microsoft InTune** -Blade im linken Navigationsbereich auf **Client-apps** .</span><span class="sxs-lookup"><span data-stu-id="adcc9-136">On the **Microsoft Intune** blade, click **Client apps** in the left navigation.</span></span>
    
21. <span data-ttu-id="adcc9-137">Klicken Sie auf dem Blade **Client apps** auf **apps**, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="adcc9-137">On the **Client Apps** blade, click **Apps**, and then click **Add**.</span></span> 

22. <span data-ttu-id="adcc9-138">Wählen Sie im App-Blade **Hinzufügen** die Option **App-Typ**aus, und wählen Sie dann unter **Office 365 Suite**die Option **Windows 10** aus.</span><span class="sxs-lookup"><span data-stu-id="adcc9-138">In the **Add app** blade, select **App type**, and then select **Windows 10** under **Office 365 Suite**.</span></span>

23. <span data-ttu-id="adcc9-139">Klicken Sie auf **App-Suite konfigurieren**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="adcc9-139">Click **Configure App Suite**, and then click **OK**.</span></span>

24. <span data-ttu-id="adcc9-140">Klicken Sie auf **App Suite-Informationen**, geben Sie **Office-Apps für Windows 10** in **Suite Name**, **Office-Apps für Windows 10** in **Suite Description**ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="adcc9-140">Click **App Suite Information**, type **Office Apps for Windows 10** in **Suite Name**, **Office Apps for Windows 10** in **Suite Description**, and then click **OK**.</span></span>

25. <span data-ttu-id="adcc9-141">Klicken Sie auf **App Suite-Einstellungen**, wählen Sie **halbjährlich** in **Update Kanal**aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="adcc9-141">Click **App Suite Settings**, select **Semi-Annual** in **Update channel**, and then click **OK**.</span></span>

26. <span data-ttu-id="adcc9-142">Klicken Sie auf dem Blatt **app hinzufügen** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="adcc9-142">On the **Add app** blade, click **Add**.</span></span>

<span data-ttu-id="adcc9-143">Sie verfügen nun über eine Geräte Kompatibilitäts Richtlinie zum Testen der ausgewählten apps in der **Windows 10** -Geräte Kompatibilitäts Richtlinie und für Mitglieder der **verwalteten Windows 10-Geräte Benutzer** Gruppe.</span><span class="sxs-lookup"><span data-stu-id="adcc9-143">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="adcc9-144">Beachten Sie, dass beim Auswählen von Office 365 als Gruppentyp zusätzliche Ressourcen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="adcc9-144">Please note that selecting Office 365 as the group type will create additional resources.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="adcc9-145">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="adcc9-145">Next step</span></span>

<span data-ttu-id="adcc9-146">Untersuchen Sie weitere Features und Funktionen zur [Verwaltung mobiler Geräte](m365-enterprise-test-lab-guides.md#mobile-device-management) in Ihrer Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="adcc9-146">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="adcc9-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="adcc9-147">See also</span></span>

<span data-ttu-id="adcc9-148">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="adcc9-148">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="adcc9-149">Registrieren von IOS-und Android-Geräten in Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="adcc9-149">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="adcc9-150">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="adcc9-150">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="adcc9-151">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="adcc9-151">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
