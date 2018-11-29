---
title: Registrieren von iOS- und Android-Geräten in Ihrer Testumgebung für Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Verwenden Sie diese Test Lab Guide zum Registrieren von Geräten in Ihrer Microsoft 365 Test-Umgebung und Remote zu verwalten.
ms.openlocfilehash: 98696104ee8453adb7449980cf439eeb152aeea9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867696"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="6f2ea-103">Registrieren von iOS- und Android-Geräten in Ihrer Testumgebung für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6f2ea-103">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="6f2ea-104">Gemäß die Anweisungen in diesem Artikel müssen Sie möglicherweise zum Registrieren und Testen grundlegende Mobilgerät Management-Funktionen für iOS und Android-Geräte in Ihrer testumgebung Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="6f2ea-104">By following the instructions provided in this article, you'll be able to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 Enterprise test environment.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="6f2ea-106">Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6f2ea-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="6f2ea-107">Phase 1: Erstellen Sie Ihre Umgebung für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6f2ea-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="6f2ea-108">Wenn Sie auf einfache Weise mit den Mindestanforderungen iOS und Android-Geräte registrieren möchten, befolgen Sie die Anweisungen in der [Lightweight Basiskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="6f2ea-108">If you just want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="6f2ea-109">Wenn Sie iOS und Android-Geräte in einem simulierten Unternehmen registrieren möchten, befolgen Sie die Anweisungen in [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="6f2ea-109">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6f2ea-p101">Testen der automatisiert Lizenzierung und Gruppenmitgliedschaft erfordert keinen der simulierten Enterprise-testumgebung, einschließlich einer simulierten Intranet mit dem Internet verbunden und Directory-Synchronisierung für eine Windows Server Active Directory-Gesamtstruktur. Erfolgt hier als eine Option, damit Sie automatisierte Lizenzierung und Gruppenmitgliedschaft testen können, und probieren Sie es in einer Umgebung, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="6f2ea-p101">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="6f2ea-112">Phase 2: Registrieren Sie Ihre iOS und Android-Geräte</span><span class="sxs-lookup"><span data-stu-id="6f2ea-112">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="6f2ea-113">Verwenden Sie zunächst die Anweisungen in [Installieren und melden Sie sich die app Unternehmensportal](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) zum Anpassen von Microsoft Intune Unternehmensportal-app für Ihre testumgebung.</span><span class="sxs-lookup"><span data-stu-id="6f2ea-113">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="6f2ea-114">Im nächsten Schritt verwenden Sie die Anweisungen in [Richten Sie Ihre Unternehmensressourcen zugreifen,](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) einer iOS-Geräte zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="6f2ea-114">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="6f2ea-115">Im nächsten Schritt verwenden Sie die Anweisungen in [Registrieren Ihrer Android-Gerät im Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) Android-Gerät zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="6f2ea-115">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="6f2ea-116">Phase 3: Verwalten Sie Ihrer iOS und Android-Geräte Remote</span><span class="sxs-lookup"><span data-stu-id="6f2ea-116">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="6f2ea-p102">Bietet Microsoft Intune remote sperren und die Kennung Funktionen zurückgesetzt. Wenn eine Person ihr Gerät verliert, können Sie das Gerät Remote sperren. Wenn eine Person ihre Kennung vergisst, können Sie es Remote zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="6f2ea-p102">Microsoft Intune provides both remote lock and passcode reset capabilities. If someone loses their device, you can lock the device remotely. If someone forgets their passcode, you can reset it remotely.</span></span>
  
<span data-ttu-id="6f2ea-120">Um eine IOS- oder Android-Gerät remote zu sperren:</span><span class="sxs-lookup"><span data-stu-id="6f2ea-120">To lock an iOS or Android device remotely:</span></span>

1. <span data-ttu-id="6f2ea-121">Melden Sie sich bei der Azure-Portal unter [https://portal.azure.com](https://portal.azure.com) mit den Anmeldeinformationen Ihres Kontos globaler Administrator.</span><span class="sxs-lookup"><span data-stu-id="6f2ea-121">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="6f2ea-122">Klicken Sie auf **alle Dienste**, geben Sie **Intune**, und klicken Sie dann auf **Intune**.</span><span class="sxs-lookup"><span data-stu-id="6f2ea-122">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="6f2ea-123">Klicken Sie auf **Geräte > alle Geräte**.</span><span class="sxs-lookup"><span data-stu-id="6f2ea-123">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="6f2ea-124">Klicken Sie in der Liste der Geräte auf eine IOS- oder Android-Gerät, und klicken Sie dann auf die Aktion **Remote Sperren** .</span><span class="sxs-lookup"><span data-stu-id="6f2ea-124">In the list of devices, click an iOS or Android device, and then click the **Remote lock** action.</span></span>

    
<span data-ttu-id="6f2ea-125">So setzen Sie den Zugangscode remote zurück</span><span class="sxs-lookup"><span data-stu-id="6f2ea-125">To reset the passcode remotely:</span></span>

1. <span data-ttu-id="6f2ea-126">Falls erforderlich, melden Sie sich bei der Azure-Portal unter [https://portal.azure.com](https://portal.azure.com) mit den Anmeldeinformationen Ihres Kontos globaler Administrator.</span><span class="sxs-lookup"><span data-stu-id="6f2ea-126">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="6f2ea-127">Klicken Sie auf **alle Dienste**, geben Sie **Intune**, und klicken Sie dann auf **Intune**.</span><span class="sxs-lookup"><span data-stu-id="6f2ea-127">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="6f2ea-128">Klicken Sie auf **Geräte > alle Geräte**.</span><span class="sxs-lookup"><span data-stu-id="6f2ea-128">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="6f2ea-p103">Aus der Liste der Geräte verwalten, klicken Sie auf eine IOS- oder Android-Gerät und wählen Sie **... Weitere**. Wählen Sie dann die **Kennung entfernen** Gerät remote-Aktion aus.</span><span class="sxs-lookup"><span data-stu-id="6f2ea-p103">From the list of devices you manage, click an iOS or Android device, and choose **...More**. Then choose the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="6f2ea-131">Weitere Versuche finden Sie unter [verfügbare Gerät Aktionen](https://docs.microsoft.com/intune/device-management#available-device-actions).</span><span class="sxs-lookup"><span data-stu-id="6f2ea-131">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>

    
## <a name="next-step"></a><span data-ttu-id="6f2ea-132">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="6f2ea-132">Next step</span></span>

<span data-ttu-id="6f2ea-133">Hier finden Sie zusätzliche [Verwaltung mobiler Geräte](m365-enterprise-test-lab-guides.md#mobile-device-management) Features und Funktionen in Ihrer testumgebung.</span><span class="sxs-lookup"><span data-stu-id="6f2ea-133">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f2ea-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f2ea-134">See Also</span></span>

[<span data-ttu-id="6f2ea-135">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6f2ea-135">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="6f2ea-136">MAM-Richtlinien für die Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="6f2ea-136">MAM policies for your Microsoft 365 Enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="6f2ea-137">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6f2ea-137">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="6f2ea-138">Enterprise-Mobilität + Sicherheit (zur Abstimmung)</span><span class="sxs-lookup"><span data-stu-id="6f2ea-138">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
