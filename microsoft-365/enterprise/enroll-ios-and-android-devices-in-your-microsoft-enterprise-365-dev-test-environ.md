---
title: Registrieren von IOS-und Android-Geräten in Ihrer Microsoft 365 for Enterprise-Testumgebung
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
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Verwenden Sie diese Test Umgebungs Anleitung, um Geräte in Ihrer Microsoft 365-Testumgebung zu registrieren und Remote zu verwalten.
ms.openlocfilehash: 3736934dbb62e84aad6a91fcd1d65b4a47ef8637
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487696"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="ad76d-103">Registrieren von IOS-und Android-Geräten in Ihrer Microsoft 365 for Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="ad76d-103">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="ad76d-104">*Diese Test Umgebungs Anleitung kann nur für Microsoft 365 für Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="ad76d-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="ad76d-105">In diesem Artikel wird beschrieben, wie Sie grundlegende Funktionen für die Verwaltung mobiler Geräte für IOS-und Android-Geräte in Ihrer Microsoft 365 for Enterprise-Testumgebung registrieren und testen.</span><span class="sxs-lookup"><span data-stu-id="ad76d-105">This article describes how to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="ad76d-106">Das Registrieren von IOS-und Android-Geräten in Ihrer Testumgebung umfasst drei Phasen:</span><span class="sxs-lookup"><span data-stu-id="ad76d-106">Enrolling iOS and Android devices in your test environment involves three phases:</span></span>
- [<span data-ttu-id="ad76d-107">Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="ad76d-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="ad76d-108">Phase 2: Registrieren von IOS-und Android-Geräten</span><span class="sxs-lookup"><span data-stu-id="ad76d-108">Phase 2: Enroll your iOS and Android devices</span></span>](#phase-2-enroll-your-ios-and-android-devices)
- [<span data-ttu-id="ad76d-109">Phase 3: Remoteverwaltung von IOS-und Android-Geräten</span><span class="sxs-lookup"><span data-stu-id="ad76d-109">Phase 3: Manage your iOS and Android devices remotely</span></span>](#phase-3-manage-your-ios-and-android-devices-remotely)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="ad76d-111">Eine visuelle Zuordnung zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide Stack finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="ad76d-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="ad76d-112">Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="ad76d-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="ad76d-113">Wenn Sie IOS-und Android-Geräte auf einfache Weise mit den Mindestanforderungen registrieren möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="ad76d-113">If you want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="ad76d-114">Wenn Sie IOS-und Android-Geräte in einem simulierten Unternehmen registrieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="ad76d-114">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ad76d-115">Für das Testen der automatisierten Lizenzierung und der Gruppenmitgliedschaft ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst.</span><span class="sxs-lookup"><span data-stu-id="ad76d-115">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="ad76d-116">Er wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen können, und Sie können damit in einer Umgebung experimentieren, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="ad76d-116">It's provided here as an option so that you can test automated licensing and group membership, and you can experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="ad76d-117">Phase 2: Registrieren von IOS-und Android-Geräten</span><span class="sxs-lookup"><span data-stu-id="ad76d-117">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="ad76d-118">Verwenden Sie zunächst die Anweisungen unter [Install, und melden Sie sich bei der Unternehmensportal-App](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) an, um die Microsoft InTune-Unternehmensportal-App für Ihre Testumgebung anzupassen.</span><span class="sxs-lookup"><span data-stu-id="ad76d-118">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="ad76d-119">Verwenden Sie als nächstes die Anweisungen unter [Einrichten des Zugriffs auf Ihre Unternehmensressourcen](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) , um ein IOS-Gerät zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="ad76d-119">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="ad76d-120">Verwenden Sie als nächstes die Anweisungen unter [Registrieren Ihres Android-Geräts in InTune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) , um ein Android-Gerät zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="ad76d-120">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="ad76d-121">Phase 3: Remoteverwaltung von IOS-und Android-Geräten</span><span class="sxs-lookup"><span data-stu-id="ad76d-121">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="ad76d-122">Microsoft Intune bietet sowohl Funktionen für eine Remotesperre und das Zurücksetzen der Kennung.</span><span class="sxs-lookup"><span data-stu-id="ad76d-122">Microsoft Intune provides both remote lock and passcode reset capabilities.</span></span> <span data-ttu-id="ad76d-123">Wenn ein Benutzer Ihr Gerät verliert, können Sie das Gerät Remote Sperren.</span><span class="sxs-lookup"><span data-stu-id="ad76d-123">If someone loses their device, you can remotely lock the device.</span></span> <span data-ttu-id="ad76d-124">Wenn jemand Ihren Code vergisst, können Sie ihn Remote zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="ad76d-124">If someone forgets their passcode, you can remotely reset it.</span></span>
  
<span data-ttu-id="ad76d-125">So sperren Sie ein IOS-oder Android-Gerät per Remotezugriff:</span><span class="sxs-lookup"><span data-stu-id="ad76d-125">To remotely lock an iOS or Android device:</span></span>

1. <span data-ttu-id="ad76d-126">Melden Sie sich beim Azure-Portal unter [https://portal.azure.com](https://portal.azure.com) mit den Anmeldeinformationen Ihres globalen Administratorkontos an.</span><span class="sxs-lookup"><span data-stu-id="ad76d-126">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="ad76d-127">Geben Sie im Azure-Portal in das Suchfeld **InTune** ein, und wählen Sie dann **InTune**aus.</span><span class="sxs-lookup"><span data-stu-id="ad76d-127">In the Azure portal, enter **Intune** in the search box, and then select **Intune**.</span></span>
3. <span data-ttu-id="ad76d-128">Klicken Sie auf **Geräte > alle Geräte**.</span><span class="sxs-lookup"><span data-stu-id="ad76d-128">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="ad76d-129">Wählen Sie in der Liste der Geräte ein IOS-oder Android-Gerät aus, und wählen Sie dann die Aktion **Remote Sperre** aus.</span><span class="sxs-lookup"><span data-stu-id="ad76d-129">In the list of devices, select an iOS or Android device, and then select the **Remote lock** action.</span></span>
    
<span data-ttu-id="ad76d-130">So stellen Sie den Code Remote zurück:</span><span class="sxs-lookup"><span data-stu-id="ad76d-130">To remotely reset the passcode:</span></span>

1. <span data-ttu-id="ad76d-131">Melden Sie sich bei Bedarf im Azure-Portal unter [https://portal.azure.com](https://portal.azure.com) mit den Anmeldeinformationen Ihres globalen Administratorkontos an.</span><span class="sxs-lookup"><span data-stu-id="ad76d-131">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="ad76d-132">Geben Sie im Azure-Portal in das Suchfeld **InTune** ein, und wählen Sie dann **InTune**aus.</span><span class="sxs-lookup"><span data-stu-id="ad76d-132">In the Azure portal, enter **Intune** in the search box, and then select **Intune**.</span></span>
3. <span data-ttu-id="ad76d-133">Wählen Sie **Geräte**  >  **alle Geräte**aus.</span><span class="sxs-lookup"><span data-stu-id="ad76d-133">Select **Devices** > **All devices**.</span></span>
4. <span data-ttu-id="ad76d-134">Wählen Sie aus der Liste der Geräte, die Sie verwalten, ein IOS-oder Android-Gerät aus, und wählen Sie dann \*\*... \*\*Und wählen Sie dann die Remote Aktion Kennwort-Gerät **Entfernen** aus.</span><span class="sxs-lookup"><span data-stu-id="ad76d-134">From the list of devices you manage, select an iOS or Android device, select **...More**, and then select the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="ad76d-135">Weitere Experimente finden Sie unter [Verfügbare Geräteaktionen](https://docs.microsoft.com/intune/device-management#available-device-actions).</span><span class="sxs-lookup"><span data-stu-id="ad76d-135">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>
    
## <a name="next-step"></a><span data-ttu-id="ad76d-136">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="ad76d-136">Next step</span></span>

<span data-ttu-id="ad76d-137">Untersuchen Sie weitere Features und Funktionen zur [Verwaltung mobiler Geräte](m365-enterprise-test-lab-guides.md#mobile-device-management) in Ihrer Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="ad76d-137">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad76d-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad76d-138">See Also</span></span>

[<span data-ttu-id="ad76d-139">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ad76d-139">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="ad76d-140">Geräte Konformitätsrichtlinien für Ihre Microsoft 365 für Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="ad76d-140">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="ad76d-141">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ad76d-141">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)
