---
title: Geräte Konformitätsrichtlinien für Ihre Microsoft 365 Enterprise-Testumgebung
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
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Verwenden Sie diese Test Umgebungs Anleitung, um InTune-Geräte Konformitätsrichtlinien zu Ihrer Microsoft 365 Enterprise-Testumgebung hinzuzufügen.
ms.openlocfilehash: 5ef39310ff74e5d5a38e8a5dd8c7ca24a126af58
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679026"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="1c8d2-103">Geräte Konformitätsrichtlinien für Ihre Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="1c8d2-103">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="1c8d2-104">*Diese Testumgebungsanleitung kann nur für Microsoft 365 Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="1c8d2-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="1c8d2-105">Mit den Anweisungen in diesem Artikel fügen Sie eine InTune-Geräte Konformitätsrichtlinie für Windows 10-Geräte und Microsoft 365-Apps für Enterprise zu Ihrer Microsoft 365 Enterprise-Testumgebung hinzu.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-105">With the instructions in this article, you add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 Enterprise test environment.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="1c8d2-107">Klicken Sie [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="1c8d2-108">Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="1c8d2-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="1c8d2-109">Wenn Sie MAM-Richtlinien nur auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="1c8d2-109">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="1c8d2-110">Wenn Sie MAM-Richtlinien in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="1c8d2-110">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1c8d2-111">Für das Testen der automatischen Lizenzierung und der Gruppenmitgliedschaft ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-111">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="1c8d2-112">Sie wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="1c8d2-113">Phase 2: Erstellen einer Geräte Kompatibilitäts Richtlinie für Windows 10-Geräte</span><span class="sxs-lookup"><span data-stu-id="1c8d2-113">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="1c8d2-114">In dieser Phase erstellen Sie eine Geräte Kompatibilitäts Richtlinie für Windows 10-Geräte.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-114">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="1c8d2-115">Wechseln Sie zum Office 365 Portal unter ( [https://portal.office.com](https://portal.office.com) ), und melden Sie sich bei Ihrem Office 365 Test Lab-Abonnement mit ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-115">Go to the Office 365 portal at ([https://portal.office.com](https://portal.office.com)) and sign in to your Office 365 test lab subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="1c8d2-116">Öffnen Sie auf einer neuen Registerkarte Ihres Browsers das Azure-Portal unter [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="1c8d2-116">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="1c8d2-117">Geben Sie auf der Registerkarte Azure Portal in Ihrem Browser **InTune** in das Suchfeld ein, und klicken Sie dann auf **InTune**.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-117">From the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="1c8d2-118">Wenn Sie im Bereich **Microsoft InTune** sehen, dass die Meldung **Geräteverwaltung noch nicht aktiviert** ist, klicken Sie darauf.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-118">If you see a **You haven't enabled device management yet** message In the **Microsoft Intune** pane, click it.</span></span> <span data-ttu-id="1c8d2-119">Klicken Sie im Bereich **Verwaltung von mobilen Geräten** auf **InTune MDM Authority**, und klicken Sie dann auf **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-119">In the **Mobile Device Management authority** pane, click **Intune MDM Authority**, and then click **Choose**.</span></span> <span data-ttu-id="1c8d2-120">Aktualisieren Sie die Registerkarte Browser.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-120">Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="1c8d2-121">Klicken Sie im linken Navigationsbereich auf **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-121">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="1c8d2-122">Klicken Sie im Bereich **Gruppen-alle Gruppen** auf **+ neue Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-122">In the **Groups-All groups** pane, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="1c8d2-123">Wählen Sie im Bereich **Gruppe** **Office 365** oder **Sicherheit** für **Gruppentyp?**, geben Sie **verwaltete Windows 10-Geräte Benutzer** unter **Name**ein, wählen Sie in **Mitgliedschafts** **zugewiesen** aus, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-123">In the **Group** pane, select **Office 365** or **Security** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="1c8d2-124">Klicken Sie auf **Microsoft InTune**.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-124">Click **Microsoft Intune**.</span></span> <span data-ttu-id="1c8d2-125">Klicken Sie im Bereich **Microsoft InTune** in der Liste **schnell Aufgaben** auf **Konformitätsrichtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-125">In the **Microsoft Intune** pane, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
9. <span data-ttu-id="1c8d2-126">Klicken Sie im Bereich **Konformitätsrichtlinien profile** auf **Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-126">In the **Compliance Policy Profiles** pane, click **Create Policy**.</span></span>
    
10. <span data-ttu-id="1c8d2-127">Geben Sie im Bereich **Richtlinie erstellen** unter **Name den Namen** **Windows 10**ein.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-127">In the **Create Policy** pane, in **Name**, type **Windows 10**.</span></span> <span data-ttu-id="1c8d2-128">Wählen Sie unter **Plattform**die Option **Windows 10 und höher**aus, klicken Sie im Bereich **Compliance-Richtlinie von Windows 10** auf **OK** , und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-128">In **Platform**, select **Windows 10 and later**, click **OK** In the **Windows 10 compliance policy** pane, and then click **Create**.</span></span> 
    
11. <span data-ttu-id="1c8d2-129">Klicken Sie auf **Konformitätsrichtlinien profile**, und klicken Sie dann auf den Richtliniennamen **Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="1c8d2-129">Click **Compliance Policy Profiles**, and then click the **Windows 10** policy name.</span></span>
    
12. <span data-ttu-id="1c8d2-130">Klicken Sie im Fensterbereich von **Windows 10** auf **Zuweisungen**, und klicken Sie dann auf **einzubeziehende Gruppen auswählen**.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-130">In the **Windows 10** pane, click **Assignments**, and then click **Select groups to include**.</span></span>
    
13. <span data-ttu-id="1c8d2-131">Klicken Sie im Bereich **einzuschließende Gruppen auswählen** auf die Gruppe **verwaltete Windows 10-Geräte Benutzer** , und klicken Sie dann auf **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-131">In the **Select groups to include** pane, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
14. <span data-ttu-id="1c8d2-132">Klicken Sie auf **Speichern**, klicken Sie auf **Microsoft InTune-Übersicht**, und klicken Sie dann im linken Navigationsbereich auf **Client-apps** .</span><span class="sxs-lookup"><span data-stu-id="1c8d2-132">Click **Save**, click **Microsoft Intune-Overview**, and then click **Client apps** in the left navigation.</span></span>
    
15. <span data-ttu-id="1c8d2-133">Klicken Sie im Bereich **Client apps** auf **apps**, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-133">In the **Client Apps** pane, click **Apps**, and then click **Add**.</span></span> 

16. <span data-ttu-id="1c8d2-134">Wählen Sie im Bereich **app hinzufügen** die Option **App-Typ**aus, und wählen Sie dann unter **Office 365 Suite**die Option **Windows 10** aus.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-134">In the **Add app** pane, select **App type**, and then select **Windows 10** under **Office 365 Suite**.</span></span>

17. <span data-ttu-id="1c8d2-135">Wählen Sie im Bereich **app hinzufügen** die Option **App Suite-Informationen**aus.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-135">In the **Add App** pane, select **App Suite Information**.</span></span>
 
18. <span data-ttu-id="1c8d2-136">Geben Sie im Bereich **Informationen zur APP-Suite** **Microsoft 365 apps for Enterprise** in **Suite Name** und **Suite Description**ein.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-136">In the **App Suite Information** pane, type **Microsoft 365 Apps for enterprise** in both **Suite Name** and **Suite Description**.</span></span>
<span data-ttu-id="1c8d2-137">Klicken Sie auf "OK".</span><span class="sxs-lookup"><span data-stu-id="1c8d2-137">Click OK.</span></span>

19. <span data-ttu-id="1c8d2-138">Wählen Sie im Bereich **app hinzufügen** die Option **App Suite konfigurieren**aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-138">In the **Add App** pane, select **Configure App Suite**, and then click **OK**.</span></span>

20. <span data-ttu-id="1c8d2-139">Wählen Sie im Bereich **app hinzufügen** die Option **App Suite Settings**aus.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-139">In the **Add App** pane, select **App Suite Settings**.</span></span>

21. <span data-ttu-id="1c8d2-140">Wählen Sie für **Update Kanal** **halbjährliche Enterprise**aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-140">For **Update Channel**, select **Semi-Annual Enterprise**, and then click **OK**.</span></span>

22. <span data-ttu-id="1c8d2-141">Klicken Sie im Bereich **app hinzufügen** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-141">In the **Add app** pane, click **Add**.</span></span>

<span data-ttu-id="1c8d2-142">Sie verfügen nun über eine Geräte Kompatibilitäts Richtlinie zum Testen der ausgewählten apps in der **Windows 10** -Geräte Kompatibilitäts Richtlinie und für Mitglieder der **verwalteten Windows 10-Geräte Benutzer** Gruppe.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-142">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="1c8d2-143">Beachten Sie, dass beim Auswählen von Office 365 als Gruppentyp zusätzliche Ressourcen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-143">Please note that selecting Office 365 as the group type will create additional resources.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="1c8d2-144">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="1c8d2-144">Next step</span></span>

<span data-ttu-id="1c8d2-145">Untersuchen Sie weitere Features und Funktionen zur [Verwaltung mobiler Geräte](m365-enterprise-test-lab-guides.md#mobile-device-management) in Ihrer Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="1c8d2-145">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="1c8d2-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c8d2-146">See also</span></span>

<span data-ttu-id="1c8d2-147">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="1c8d2-147">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="1c8d2-148">Registrieren von IOS-und Android-Geräten in Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="1c8d2-148">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="1c8d2-149">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1c8d2-149">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="1c8d2-150">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="1c8d2-150">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
