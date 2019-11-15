---
title: Registrieren von IOS-und Android-Geräten in Ihrer Microsoft 365 Enterprise-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/11/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Verwenden Sie diese Test Umgebungs Anleitung, um Geräte in Ihrer Microsoft 365-Testumgebung zu registrieren und Remote zu verwalten.
ms.openlocfilehash: 0d7e03d1dcc6e8f401258587c1dbc083b1237d49
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640377"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="88e36-103">Registrieren von IOS-und Android-Geräten in Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="88e36-103">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="88e36-104">Wenn Sie die Anweisungen in diesem Artikel befolgen, können Sie die grundlegenden Funktionen der mobilen Geräteverwaltung für IOS-und Android-Geräte in Ihrer Microsoft 365 Enterprise-Testumgebung registrieren und testen.</span><span class="sxs-lookup"><span data-stu-id="88e36-104">By following the instructions provided in this article, you'll be able to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 Enterprise test environment.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="88e36-106">Klicken Sie [hier](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="88e36-106">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="88e36-107">Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="88e36-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="88e36-108">Wenn Sie IOS-und Android-Geräte nur auf einfache Weise mit den Mindestanforderungen registrieren möchten, befolgen Sie die Anweisungen in [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="88e36-108">If you just want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="88e36-109">Wenn Sie IOS-und Android-Geräte in einem simulierten Unternehmen registrieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="88e36-109">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="88e36-110">Für das Testen der automatischen Lizenzierung und der Gruppenmitgliedschaft ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst.</span><span class="sxs-lookup"><span data-stu-id="88e36-110">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="88e36-111">Sie wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="88e36-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="88e36-112">Phase 2: Registrieren von IOS-und Android-Geräten</span><span class="sxs-lookup"><span data-stu-id="88e36-112">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="88e36-113">Verwenden Sie zunächst die Anweisungen unter [Install, und melden Sie sich bei der Unternehmensportal-App](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) an, um die Microsoft InTune-Unternehmensportal-App für Ihre Testumgebung anzupassen.</span><span class="sxs-lookup"><span data-stu-id="88e36-113">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="88e36-114">Verwenden Sie als nächstes die Anweisungen unter [Einrichten des Zugriffs auf Ihre Unternehmensressourcen](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) , um ein IOS-Gerät zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="88e36-114">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="88e36-115">Verwenden Sie als nächstes die Anweisungen unter [Registrieren Ihres Android-Geräts in InTune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) , um ein Android-Gerät zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="88e36-115">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="88e36-116">Phase 3: Remoteverwaltung von IOS-und Android-Geräten</span><span class="sxs-lookup"><span data-stu-id="88e36-116">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="88e36-117">Microsoft Intune bietet sowohl Funktionen für eine Remotesperre und das Zurücksetzen der Kennung.</span><span class="sxs-lookup"><span data-stu-id="88e36-117">Microsoft Intune provides both remote lock and passcode reset capabilities.</span></span> <span data-ttu-id="88e36-118">Wenn jemand sein Gerät verliert, können Sie das Gerät remote sperren.</span><span class="sxs-lookup"><span data-stu-id="88e36-118">If someone loses their device, you can lock the device remotely.</span></span> <span data-ttu-id="88e36-119">Wenn jemand Ihren Code vergisst, können Sie ihn Remote zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="88e36-119">If someone forgets their passcode, you can reset it remotely.</span></span>
  
<span data-ttu-id="88e36-120">So sperren Sie ein IOS-oder Android-Gerät Remote:</span><span class="sxs-lookup"><span data-stu-id="88e36-120">To lock an iOS or Android device remotely:</span></span>

1. <span data-ttu-id="88e36-121">Melden Sie sich beim Azure-Portal [https://portal.azure.com](https://portal.azure.com) unter mit den Anmeldeinformationen Ihres globalen Administratorkontos an.</span><span class="sxs-lookup"><span data-stu-id="88e36-121">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="88e36-122">Klicken Sie auf **alle Dienste**, geben Sie **InTune**ein, und klicken Sie dann auf **InTune**.</span><span class="sxs-lookup"><span data-stu-id="88e36-122">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="88e36-123">Klicken Sie auf **Geräte #a0 alle Geräte**.</span><span class="sxs-lookup"><span data-stu-id="88e36-123">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="88e36-124">Klicken Sie in der Liste der Geräte auf ein IOS-oder Android-Gerät, und klicken Sie dann auf die Aktion **Remote Sperre** .</span><span class="sxs-lookup"><span data-stu-id="88e36-124">In the list of devices, click an iOS or Android device, and then click the **Remote lock** action.</span></span>

    
<span data-ttu-id="88e36-125">So setzen Sie den Zugangscode remote zurück</span><span class="sxs-lookup"><span data-stu-id="88e36-125">To reset the passcode remotely:</span></span>

1. <span data-ttu-id="88e36-126">Melden Sie sich bei Bedarf im Azure-Portal unter [https://portal.azure.com](https://portal.azure.com) mit den Anmeldeinformationen Ihres globalen Administratorkontos an.</span><span class="sxs-lookup"><span data-stu-id="88e36-126">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="88e36-127">Klicken Sie auf **alle Dienste**, geben Sie **InTune**ein, und klicken Sie dann auf **InTune**.</span><span class="sxs-lookup"><span data-stu-id="88e36-127">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="88e36-128">Klicken Sie auf **Geräte #a0 alle Geräte**.</span><span class="sxs-lookup"><span data-stu-id="88e36-128">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="88e36-129">Klicken Sie in der Liste der Geräte, die Sie verwalten, auf ein IOS-oder Android-Gerät, und wählen Sie **... Mehr**.</span><span class="sxs-lookup"><span data-stu-id="88e36-129">From the list of devices you manage, click an iOS or Android device, and choose **...More**.</span></span> <span data-ttu-id="88e36-130">Klicken Sie dann auf die Remote Aktion Kennwort-Gerät **Entfernen** .</span><span class="sxs-lookup"><span data-stu-id="88e36-130">Then choose the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="88e36-131">Weitere Experimente finden Sie unter [Verfügbare Geräteaktionen](https://docs.microsoft.com/intune/device-management#available-device-actions).</span><span class="sxs-lookup"><span data-stu-id="88e36-131">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>

    
## <a name="next-step"></a><span data-ttu-id="88e36-132">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="88e36-132">Next step</span></span>

<span data-ttu-id="88e36-133">Untersuchen Sie weitere Features und Funktionen zur [Verwaltung mobiler Geräte](m365-enterprise-test-lab-guides.md#mobile-device-management) in Ihrer Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="88e36-133">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="88e36-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="88e36-134">See Also</span></span>

[<span data-ttu-id="88e36-135">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="88e36-135">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="88e36-136">Geräte Konformitätsrichtlinien für Ihre Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="88e36-136">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="88e36-137">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="88e36-137">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

