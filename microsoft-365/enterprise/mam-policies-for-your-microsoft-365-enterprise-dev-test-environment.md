---
title: Geräte Konformitätsrichtlinien für Ihre Microsoft 365 für Enterprise-Testumgebung
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Verwenden Sie diese Test Umgebungs Anleitung zum Hinzufügen von InTune-Geräte Konformitätsrichtlinien zu Ihrer Microsoft 365 for Enterprise-Testumgebung.
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367095"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="49344-103">Geräte Konformitätsrichtlinien für Ihre Microsoft 365 für Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="49344-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="49344-104">*Diese Test Umgebungs Anleitung kann nur für Microsoft 365 für Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="49344-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="49344-105">In diesem Artikel wird beschrieben, wie Sie der Microsoft 365 für Enterprise-Testumgebung eine InTune-Geräte Kompatibilitäts Richtlinie für Windows 10-Geräte und Microsoft 365-Apps für Enterprise hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="49344-105">This article describes how to add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="49344-106">Das Hinzufügen einer InTune-Geräte Konformitätsrichtlinie umfasst zwei Phasen:</span><span class="sxs-lookup"><span data-stu-id="49344-106">Adding an Intune device compliance policy involves two phases:</span></span>
- [<span data-ttu-id="49344-107">Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="49344-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="49344-108">Phase 2: Erstellen einer Geräte Kompatibilitäts Richtlinie für Windows 10-Geräte</span><span class="sxs-lookup"><span data-stu-id="49344-108">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="49344-110">Eine visuelle Zuordnung zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide Stack finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="49344-110">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="49344-111">Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="49344-111">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="49344-112">Wenn Sie MAM-Richtlinien nur auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="49344-112">If you want to configure MAM policies in only a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="49344-113">Wenn Sie MAM-Richtlinien in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="49344-113">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="49344-114">Für das Testen der automatisierten Lizenzierung und der Gruppenmitgliedschaft ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst.</span><span class="sxs-lookup"><span data-stu-id="49344-114">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="49344-115">Er wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="49344-115">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="49344-116">Phase 2: Erstellen einer Geräte Kompatibilitäts Richtlinie für Windows 10-Geräte</span><span class="sxs-lookup"><span data-stu-id="49344-116">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="49344-117">In dieser Phase erstellen Sie eine Geräte Kompatibilitäts Richtlinie für Windows 10-Geräte.</span><span class="sxs-lookup"><span data-stu-id="49344-117">In this phase, you create a device compliance policy for Windows 10 devices.</span></span> <span data-ttu-id="49344-118">In dieser Phase wird Microsoft InTune und das [Verwaltungskonsole von Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) verwendet, um eine Gruppe hinzuzufügen und eine Konformitätsrichtlinie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="49344-118">This phase uses Microsoft Intune and the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) to add a group, and create a compliance policy.</span></span>

1. <span data-ttu-id="49344-119">Wechseln Sie zum [Microsoft 365 Admin Center](https://admin.microsoft.com), und melden Sie sich bei Ihrem Microsoft 365 Test Lab-Abonnement mit ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="49344-119">Go to the [Microsoft 365 admin center](https://admin.microsoft.com), and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span> <span data-ttu-id="49344-120">Wählen Sie das Verwaltungskonsole **EndPoint Manager** aus.</span><span class="sxs-lookup"><span data-stu-id="49344-120">Select the **Endpoint Manager** admin center.</span></span> <span data-ttu-id="49344-121">Das [Administrator Center für Endpunkt Verwaltung](https://go.microsoft.com/fwlink/?linkid=2109431) wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="49344-121">The [Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) opens.</span></span>

    <span data-ttu-id="49344-122">Wenn eine Nachricht, die Ihnen ähnlich ist, die **Geräteverwaltung noch nicht aktiviert** hat, wird die Meldung angezeigt, und wählen Sie dann InTune als MDM-Autorität aus.</span><span class="sxs-lookup"><span data-stu-id="49344-122">If a message similar to **You haven't enabled device management yet** message is shown, then select Intune as the MDM authority.</span></span> <span data-ttu-id="49344-123">Die einzelnen Schritte finden Sie unter [Festlegen der Verwaltungsautorität für mobile Geräte](/mem/intune/fundamentals/mdm-authority-set).</span><span class="sxs-lookup"><span data-stu-id="49344-123">For the specific steps, see [Set the mobile device management authority](/mem/intune/fundamentals/mdm-authority-set).</span></span>

    <span data-ttu-id="49344-124">Der Schwerpunkt des Endpoint Manager Admin Center liegt auf der Geräteverwaltung und der APP-Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="49344-124">The Endpoint Manager admin center focuses on device management and app management.</span></span> <span data-ttu-id="49344-125">Einen Rundgang durch dieses Admin Center finden Sie unter [Tutorial: Walkthrough InTune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span><span class="sxs-lookup"><span data-stu-id="49344-125">For a tour of this admin center, see [Tutorial: Walkthrough Intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span></span>

2. <span data-ttu-id="49344-126">Fügen Sie in **Gruppen** eine neue **Microsoft 365** -oder **Sicherheits** Gruppe mit dem Namen **Managed Windows 10-Geräte Benutzer** mit einem **zugewiesenen** Mitgliedschafts hinzu.</span><span class="sxs-lookup"><span data-stu-id="49344-126">In **Groups**, add a new **Microsoft 365** or **Security** group named **Managed Windows 10 device users**, with an **Assigned** membership type.</span></span> <span data-ttu-id="49344-127">In den nächsten Schritten weisen Sie die Konformitätsrichtlinie dieser Gruppe zu.</span><span class="sxs-lookup"><span data-stu-id="49344-127">In the next steps, you'll assign your compliance policy to this group.</span></span> 

    <span data-ttu-id="49344-128">Die einzelnen Schritte sowie Informationen zu **Microsoft 365** oder **Sicherheits** Gruppen finden Sie unter [Hinzufügen von Gruppen zum Organisieren von Benutzern und Geräten](/mem/intune/fundamentals/groups-add).</span><span class="sxs-lookup"><span data-stu-id="49344-128">For the specific steps, and for information on **Microsoft 365** or **Security** groups, see [Add groups to organize users and devices](/mem/intune/fundamentals/groups-add).</span></span>

3. <span data-ttu-id="49344-129">Erstellen Sie unter **Geräte** eine Windows 10-Konformitätsrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="49344-129">In **Devices**, create a Windows 10 compliance policy.</span></span> <span data-ttu-id="49344-130">Weisen Sie diese Richtlinie der **verwalteten Windows 10-Geräte Benutzer** Gruppe zu, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="49344-130">Assign this policy to the **Managed Windows 10 device users** group you created.</span></span>

    <span data-ttu-id="49344-131">In Ihrer Richtlinie können Sie einfache Kennwörter blockieren, eine Firewall erfordern, die Ausführung des Antischadsoftware-Diensts von Microsoft Defender erfordern und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="49344-131">In your policy, you can block simple passwords, require a firewall, require the Microsoft Defender Antimalware service be running, and more.</span></span> <span data-ttu-id="49344-132">Eine Konformitätsrichtlinie umfasst normalerweise die Basiseinstellungen oder ein absolutes Minimum, das jedes Gerät aufweisen sollte.</span><span class="sxs-lookup"><span data-stu-id="49344-132">A compliance policy typically includes the base settings, or bare minimum that every device should have.</span></span>

    <span data-ttu-id="49344-133">Informationen zu den einzelnen Schritten und zu den verfügbaren Kompatibilitätseinstellungen, die Sie konfigurieren können, finden Sie unter [use Compliance Policies to Sets Rules for Devices you manage](/mem/intune/protect/device-compliance-get-started).</span><span class="sxs-lookup"><span data-stu-id="49344-133">For the specific steps, and for information on the available compliance settings you can configure, see [Use compliance policies to set rules for devices you manage](/mem/intune/protect/device-compliance-get-started).</span></span>

<span data-ttu-id="49344-134">Wenn Sie fertig sind, verfügen Sie über eine Geräte Kompatibilitäts Richtlinie für das Testen von Mitgliedern in der Gruppe der **verwalteten Windows 10-Geräte Benutzer** .</span><span class="sxs-lookup"><span data-stu-id="49344-134">When finished, you have a device compliance policy for testing members in the **Managed Windows 10 device users** group.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="49344-135">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="49344-135">Next step</span></span>

<span data-ttu-id="49344-136">Untersuchen Sie weitere Features und Funktionen zur [Verwaltung mobiler Geräte](m365-enterprise-test-lab-guides.md#mobile-device-management) in Ihrer Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="49344-136">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="49344-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49344-137">See also</span></span>

<span data-ttu-id="49344-138">[Microsoft 365 for Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="49344-138">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="49344-139">Registrieren von IOS-und Android-Geräten in Ihrer Microsoft 365 for Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="49344-139">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="49344-140">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="49344-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="49344-141">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="49344-141">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
