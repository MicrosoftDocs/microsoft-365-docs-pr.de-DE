---
title: Registrieren von IOS/iPads und Android-Geräten in Ihrer Microsoft 365 for Enterprise-Testumgebung
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
description: Verwenden Sie diese Test Umgebungs Anleitung, um Geräte in Ihrer Microsoft 365-Testumgebung zu registrieren und Remote zu verwalten.
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367083"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="d2a5e-103">Registrieren von IOS-und Android-Geräten in Ihrer Microsoft 365 for Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="d2a5e-103">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="d2a5e-104">*Diese Test Umgebungs Anleitung kann nur für Microsoft 365 für Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="d2a5e-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="d2a5e-105">In diesem Artikel wird beschrieben, wie Sie grundlegende Funktionen für die Verwaltung mobiler Geräte für IOS/iPad und Android-Geräte in Ihrer Microsoft 365 for Enterprise-Testumgebung registrieren und testen.</span><span class="sxs-lookup"><span data-stu-id="d2a5e-105">This article describes how to enroll and test basic mobile device management capabilities for iOS/iPadOS and Android devices in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="d2a5e-106">Das Registrieren von IOS/iPads und Android-Geräten in Ihrer Testumgebung umfasst drei Phasen:</span><span class="sxs-lookup"><span data-stu-id="d2a5e-106">Enrolling iOS/iPadOS and Android devices in your test environment involves three phases:</span></span>
- [<span data-ttu-id="d2a5e-107">Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="d2a5e-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="d2a5e-108">Phase 2: Registrieren Ihrer IOS/iPad-und Android-Geräte</span><span class="sxs-lookup"><span data-stu-id="d2a5e-108">Phase 2: Enroll your iOS/iPadOS and Android devices</span></span>](#phase-2-enroll-your-ios-and-android-devices)
- [<span data-ttu-id="d2a5e-109">Phase 3: Remoteverwaltung Ihrer IOS/iPad-und Android-Geräte</span><span class="sxs-lookup"><span data-stu-id="d2a5e-109">Phase 3: Manage your iOS/iPadOS and Android devices remotely</span></span>](#phase-3-manage-your-ios-and-android-devices-remotely)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="d2a5e-111">Eine visuelle Zuordnung zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide Stack finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="d2a5e-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="d2a5e-112">Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="d2a5e-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="d2a5e-113">Wenn Sie IOS/iPad und Android-Geräte auf einfache Weise mit den Mindestanforderungen registrieren möchten, befolgen Sie die Anweisungen in [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="d2a5e-113">If you want to enroll iOS/iPadOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="d2a5e-114">Wenn Sie IOS/iPads und Android-Geräte in einem simulierten Unternehmen registrieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="d2a5e-114">If you want to enroll iOS/iPadOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d2a5e-115">Für das Testen der automatisierten Lizenzierung und der Gruppenmitgliedschaft ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst.</span><span class="sxs-lookup"><span data-stu-id="d2a5e-115">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="d2a5e-116">Er wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen können, und Sie können damit in einer Umgebung experimentieren, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="d2a5e-116">It's provided here as an option so that you can test automated licensing and group membership, and you can experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="d2a5e-117">Phase 2: Registrieren von IOS-und Android-Geräten</span><span class="sxs-lookup"><span data-stu-id="d2a5e-117">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="d2a5e-118">Wenn Sie eine MDM-Lösung (Mobile Device Management) zum Verwalten Ihrer Geräte erwägen, können Sie Microsoft InTune verwenden.</span><span class="sxs-lookup"><span data-stu-id="d2a5e-118">If you're considering a mobile device management (MDM) solution to manage your devices, you can use Microsoft Intune.</span></span> <span data-ttu-id="d2a5e-119">Bei der Arbeit mit einem MDM-Anbieter, einschließlich InTune, werden Geräte "registriert".</span><span class="sxs-lookup"><span data-stu-id="d2a5e-119">When working with any MDM provider, including Intune, devices are "enrolled".</span></span> <span data-ttu-id="d2a5e-120">Bei der Registrierung erhalten Sie die von Ihnen konfigurierten Features und Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="d2a5e-120">When enrolled, they receive the features and settings you configure.</span></span> 

<span data-ttu-id="d2a5e-121">In InTune gibt es einige Möglichkeiten, um Ihre IOS/iPads und Android-Geräte zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="d2a5e-121">In Intune, there are a few ways to enroll your iOS/iPadOS and Android devices.</span></span> <span data-ttu-id="d2a5e-122">Sie können die Registrierungsoption auswählen, die für Ihre Organisation am besten geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="d2a5e-122">You can choose the enrollment option that works best for your organization.</span></span> <span data-ttu-id="d2a5e-123">Weitere Informationen und Anleitungen finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="d2a5e-123">For more information and guidance, see the following articles:</span></span>

- [<span data-ttu-id="d2a5e-124">Bereitstellungshandbuch: Registrieren von IOS-und iPad-Geräten in Microsoft InTune</span><span class="sxs-lookup"><span data-stu-id="d2a5e-124">Deployment guide: Enroll iOS and iPadOS devices in Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [<span data-ttu-id="d2a5e-125">Bereitstellungshandbuch: Registrieren von Android-Geräten in Microsoft InTune</span><span class="sxs-lookup"><span data-stu-id="d2a5e-125">Deployment guide: Enroll Android devices in Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-enrollment-android)

<span data-ttu-id="d2a5e-126">Wenn Sie InTune für die Geräteverwaltung verwenden möchten und einige Anleitungen wünschen, können Ihnen die folgenden Informationen helfen:</span><span class="sxs-lookup"><span data-stu-id="d2a5e-126">If you're ready to use Intune for device management, and want some guidance, then the following information may help:</span></span>

- [<span data-ttu-id="d2a5e-127">Geräteverwaltung (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="d2a5e-127">Device management overview</span></span>](/mem/intune/fundamentals/what-is-device-management)
- [<span data-ttu-id="d2a5e-128">Lernprogramm: Exemplarische Vorgehensweise InTune in Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="d2a5e-128">Tutorial: Walkthrough Intune in Microsoft Endpoint Manager</span></span>](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [<span data-ttu-id="d2a5e-129">Bereitstellungshandbuch: Einrichten oder Migrieren zu Microsoft InTune</span><span class="sxs-lookup"><span data-stu-id="d2a5e-129">Deployment guide: Setup or move to Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="d2a5e-130">Phase 3: Remoteverwaltung von IOS-und Android-Geräten</span><span class="sxs-lookup"><span data-stu-id="d2a5e-130">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="d2a5e-131">Microsoft InTune bietet Funktionen für das Zurücksetzen von Remote Sperren und-Codes.</span><span class="sxs-lookup"><span data-stu-id="d2a5e-131">Microsoft Intune provides remote lock and passcode reset feature.</span></span> <span data-ttu-id="d2a5e-132">Wenn ein Benutzer Ihr Gerät verliert, können Sie das Gerät Remote Sperren.</span><span class="sxs-lookup"><span data-stu-id="d2a5e-132">If someone loses their device, you can remotely lock the device.</span></span> <span data-ttu-id="d2a5e-133">Wenn jemand Ihren Code vergisst, können Sie ihn Remote zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="d2a5e-133">If someone forgets their passcode, you can remotely reset it.</span></span>

- <span data-ttu-id="d2a5e-134">Informationen zum Remote Sperren eines IOS/iPad oder Android-Geräts finden Sie unter [Remote Sperr Geräte mit InTune](/mem/intune/remote-actions/device-remote-lock).</span><span class="sxs-lookup"><span data-stu-id="d2a5e-134">To remotely lock an iOS/iPadOS or Android device, see [Remotely lock devices with Intune](/mem/intune/remote-actions/device-remote-lock).</span></span>
- <span data-ttu-id="d2a5e-135">Informationen zum Remote-Zurücksetzen des Codes finden Sie unter [Zurücksetzen oder Entfernen eines Gerätecodes in InTune](/mem/intune/remote-actions/device-passcode-reset).</span><span class="sxs-lookup"><span data-stu-id="d2a5e-135">To remotely reset the passcode, see [Reset or remove a device passcode in Intune](/mem/intune/remote-actions/device-passcode-reset).</span></span>

<span data-ttu-id="d2a5e-136">Weitere Aufgaben, die Sie Remote ausführen können, finden Sie unter [Verfügbare Geräteaktionen](/mem/intune/remote-actions/device-management#available-device-actions).</span><span class="sxs-lookup"><span data-stu-id="d2a5e-136">For additional tasks you can run remotely, see [available device actions](/mem/intune/remote-actions/device-management#available-device-actions).</span></span>
    
## <a name="next-step"></a><span data-ttu-id="d2a5e-137">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="d2a5e-137">Next step</span></span>

<span data-ttu-id="d2a5e-138">Untersuchen Sie weitere Features und Funktionen zur [Verwaltung mobiler Geräte](m365-enterprise-test-lab-guides.md#mobile-device-management) in Ihrer Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="d2a5e-138">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="d2a5e-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2a5e-139">See Also</span></span>

[<span data-ttu-id="d2a5e-140">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d2a5e-140">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="d2a5e-141">Geräte Konformitätsrichtlinien für Ihre Microsoft 365 für Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="d2a5e-141">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="d2a5e-142">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d2a5e-142">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)
