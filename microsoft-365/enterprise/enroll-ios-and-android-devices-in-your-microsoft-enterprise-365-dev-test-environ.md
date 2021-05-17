---
title: Registrieren von iOS-/iPadOS- und Android-Geräten in Microsoft 365 Unternehmenstestumgebung
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
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Verwenden Sie diese Testumgebungsanleitung, um Geräte in Ihrer Microsoft 365 zu registrieren und remote zu verwalten.
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367083"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="ba2bf-103">Registrieren von iOS- und Android-Geräten in Microsoft 365 für Unternehmenstestumgebung</span><span class="sxs-lookup"><span data-stu-id="ba2bf-103">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="ba2bf-104">*Diese Testumgebungsanleitung kann nur für Microsoft 365 für Unternehmenstestumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="ba2bf-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="ba2bf-105">In diesem Artikel wird beschrieben, wie Sie grundlegende Verwaltungsfunktionen für mobile Geräte für iOS/iPadOS- und Android-Geräte in Ihrer Microsoft 365 Unternehmenstestumgebung registrieren und testen.</span><span class="sxs-lookup"><span data-stu-id="ba2bf-105">This article describes how to enroll and test basic mobile device management capabilities for iOS/iPadOS and Android devices in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="ba2bf-106">Die Registrierung von iOS/iPadOS- und Android-Geräten in Ihrer Testumgebung umfasst drei Phasen:</span><span class="sxs-lookup"><span data-stu-id="ba2bf-106">Enrolling iOS/iPadOS and Android devices in your test environment involves three phases:</span></span>
- [<span data-ttu-id="ba2bf-107">Phase 1: Build out your Microsoft 365 for Enterprise test environment</span><span class="sxs-lookup"><span data-stu-id="ba2bf-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="ba2bf-108">Phase 2: Registrieren Ihrer iOS/iPadOS- und Android-Geräte</span><span class="sxs-lookup"><span data-stu-id="ba2bf-108">Phase 2: Enroll your iOS/iPadOS and Android devices</span></span>](#phase-2-enroll-your-ios-and-android-devices)
- [<span data-ttu-id="ba2bf-109">Phase 3: Remoteverwaltung Ihrer iOS/iPadOS- und Android-Geräte</span><span class="sxs-lookup"><span data-stu-id="ba2bf-109">Phase 3: Manage your iOS/iPadOS and Android devices remotely</span></span>](#phase-3-manage-your-ios-and-android-devices-remotely)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="ba2bf-111">Eine visuelle Karte zu allen Artikeln im Stapel Microsoft 365 test lab guide für unternehmen finden Sie unter [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="ba2bf-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="ba2bf-112">Phase 1: Build out your Microsoft 365 for Enterprise test environment</span><span class="sxs-lookup"><span data-stu-id="ba2bf-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="ba2bf-113">Wenn Sie iOS/iPadOS- und Android-Geräte auf einfache Weise mit den Mindestanforderungen registrieren möchten, befolgen Sie die Anweisungen unter [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="ba2bf-113">If you want to enroll iOS/iPadOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="ba2bf-114">Wenn Sie iOS/iPadOS- und Android-Geräte in einem simulierten Unternehmen registrieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="ba2bf-114">If you want to enroll iOS/iPadOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ba2bf-115">Das Testen der automatisierten Lizenzierung und Gruppenmitgliedschaft erfordert keine simulierte Unternehmenstestumgebung, die ein simuliertes Intranet, das mit dem Internet verbunden ist, und die Verzeichnissynchronisierung für eine Active Directory Domain Services (AD DS)-Gesamtstruktur umfasst.</span><span class="sxs-lookup"><span data-stu-id="ba2bf-115">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="ba2bf-116">Es wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="ba2bf-116">It's provided here as an option so that you can test automated licensing and group membership, and you can experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="ba2bf-117">Phase 2: Registrieren Ihrer iOS- und Android-Geräte</span><span class="sxs-lookup"><span data-stu-id="ba2bf-117">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="ba2bf-118">Wenn Sie eine Mobile Device Management (MDM)-Lösung zum Verwalten Ihrer Geräte in Betracht ziehen, können Sie Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="ba2bf-118">If you're considering a mobile device management (MDM) solution to manage your devices, you can use Microsoft Intune.</span></span> <span data-ttu-id="ba2bf-119">Bei der Arbeit mit einem beliebigen MDM-Anbieter, einschließlich Intune, werden Geräte "registriert".</span><span class="sxs-lookup"><span data-stu-id="ba2bf-119">When working with any MDM provider, including Intune, devices are "enrolled".</span></span> <span data-ttu-id="ba2bf-120">Bei der Registrierung erhalten sie die features und einstellungen, die Sie konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ba2bf-120">When enrolled, they receive the features and settings you configure.</span></span> 

<span data-ttu-id="ba2bf-121">In Intune gibt es mehrere Möglichkeiten, Ihre iOS/iPadOS- und Android-Geräte zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="ba2bf-121">In Intune, there are a few ways to enroll your iOS/iPadOS and Android devices.</span></span> <span data-ttu-id="ba2bf-122">Sie können die Registrierungsoption auswählen, die für Ihre Organisation am besten funktioniert.</span><span class="sxs-lookup"><span data-stu-id="ba2bf-122">You can choose the enrollment option that works best for your organization.</span></span> <span data-ttu-id="ba2bf-123">Weitere Informationen und Anleitungen finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="ba2bf-123">For more information and guidance, see the following articles:</span></span>

- [<span data-ttu-id="ba2bf-124">Bereitstellungshandbuch: Registrieren von iOS- und iPadOS-Geräten in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ba2bf-124">Deployment guide: Enroll iOS and iPadOS devices in Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [<span data-ttu-id="ba2bf-125">Bereitstellungshandbuch: Registrieren von Android-Geräten in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ba2bf-125">Deployment guide: Enroll Android devices in Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-enrollment-android)

<span data-ttu-id="ba2bf-126">Wenn Sie bereit sind, Intune für die Geräteverwaltung zu verwenden, und einige Anleitungen benötigen, können die folgenden Informationen hilfreich sein:</span><span class="sxs-lookup"><span data-stu-id="ba2bf-126">If you're ready to use Intune for device management, and want some guidance, then the following information may help:</span></span>

- [<span data-ttu-id="ba2bf-127">Übersicht über die Geräteverwaltung</span><span class="sxs-lookup"><span data-stu-id="ba2bf-127">Device management overview</span></span>](/mem/intune/fundamentals/what-is-device-management)
- [<span data-ttu-id="ba2bf-128">Lernprogramm: Walkthrough Intune in Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="ba2bf-128">Tutorial: Walkthrough Intune in Microsoft Endpoint Manager</span></span>](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [<span data-ttu-id="ba2bf-129">Bereitstellungshandbuch: Einrichten oder Verschieben zu Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ba2bf-129">Deployment guide: Setup or move to Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="ba2bf-130">Phase 3: Remoteverwaltung Ihrer iOS- und Android-Geräte</span><span class="sxs-lookup"><span data-stu-id="ba2bf-130">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="ba2bf-131">Microsoft Intune bietet die Funktion zum Zurücksetzen von Remotesperren und Kennungen.</span><span class="sxs-lookup"><span data-stu-id="ba2bf-131">Microsoft Intune provides remote lock and passcode reset feature.</span></span> <span data-ttu-id="ba2bf-132">Wenn jemand sein Gerät verliert, können Sie das Gerät remote sperren.</span><span class="sxs-lookup"><span data-stu-id="ba2bf-132">If someone loses their device, you can remotely lock the device.</span></span> <span data-ttu-id="ba2bf-133">Wenn jemand seine Kennung vergisst, können Sie ihn remote zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="ba2bf-133">If someone forgets their passcode, you can remotely reset it.</span></span>

- <span data-ttu-id="ba2bf-134">Informationen zum Remotesperren eines iOS/iPadOS- oder Android-Geräts finden Sie unter [Remote lock devices with Intune](/mem/intune/remote-actions/device-remote-lock).</span><span class="sxs-lookup"><span data-stu-id="ba2bf-134">To remotely lock an iOS/iPadOS or Android device, see [Remotely lock devices with Intune](/mem/intune/remote-actions/device-remote-lock).</span></span>
- <span data-ttu-id="ba2bf-135">Informationen zum Remote zurücksetzen der Kennung finden Sie unter [Reset or remove a device passcode in Intune](/mem/intune/remote-actions/device-passcode-reset).</span><span class="sxs-lookup"><span data-stu-id="ba2bf-135">To remotely reset the passcode, see [Reset or remove a device passcode in Intune](/mem/intune/remote-actions/device-passcode-reset).</span></span>

<span data-ttu-id="ba2bf-136">Weitere Aufgaben, die Sie remote ausführen können, finden Sie unter [Verfügbare Geräteaktionen](/mem/intune/remote-actions/device-management#available-device-actions).</span><span class="sxs-lookup"><span data-stu-id="ba2bf-136">For additional tasks you can run remotely, see [available device actions](/mem/intune/remote-actions/device-management#available-device-actions).</span></span>
    
## <a name="next-step"></a><span data-ttu-id="ba2bf-137">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="ba2bf-137">Next step</span></span>

<span data-ttu-id="ba2bf-138">Erkunden Sie [zusätzliche Features und](m365-enterprise-test-lab-guides.md#mobile-device-management) Funktionen für die Verwaltung mobiler Geräte in Ihrer Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="ba2bf-138">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="ba2bf-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba2bf-139">See Also</span></span>

[<span data-ttu-id="ba2bf-140">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ba2bf-140">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="ba2bf-141">Gerätekonformitätsrichtlinien für Microsoft 365 für Unternehmenstestumgebung</span><span class="sxs-lookup"><span data-stu-id="ba2bf-141">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="ba2bf-142">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ba2bf-142">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)
