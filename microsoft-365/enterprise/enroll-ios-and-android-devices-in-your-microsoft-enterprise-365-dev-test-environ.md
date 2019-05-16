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
description: Verwenden Sie dieses Test Labor Handbuch, um Geräte in Ihrer Microsoft 365-Testumgebung zu registrieren und Remote zu verwalten.
ms.openlocfilehash: b72298df3dbc470358f8cd87e5ca249999812516
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073715"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="4720a-103">Registrieren von IOS-und Android-Geräten in Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="4720a-103">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="4720a-104">Durch Befolgen der Anweisungen in diesem Artikel können Sie die grundlegenden Funktionen für die Verwaltung mobiler Geräte für IOS-und Android-Geräte in Ihrer Microsoft 365 Enterprise-Testumgebung registrieren und testen.</span><span class="sxs-lookup"><span data-stu-id="4720a-104">By following the instructions provided in this article, you'll be able to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 Enterprise test environment.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="4720a-106">Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4720a-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="4720a-107">Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="4720a-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="4720a-108">Wenn Sie nur IOS-und Android-Geräte mit den Mindestanforderungen auf einfache Weise registrieren möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="4720a-108">If you just want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="4720a-109">Wenn Sie IOS-und Android-Geräte in einem simulierten Unternehmen registrieren möchten, befolgen Sie die Anweisungen unter [Passthrough-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="4720a-109">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4720a-110">Das Testen der automatisierten Lizenzierung und der Gruppenmitgliedschaft erfordert nicht die simulierte Enterprise-Testumgebung, die ein simuliertes Intranet enthält, das mit dem Internet und der Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="4720a-110">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="4720a-111">Sie wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und die Gruppenmitgliedschaft testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="4720a-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="4720a-112">Phase 2: Registrieren der IOS-und Android-Geräte</span><span class="sxs-lookup"><span data-stu-id="4720a-112">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="4720a-113">Verwenden Sie zunächst die Anweisungen unter [Installieren und Anmelden bei der Unternehmensportal-App](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) , um die Microsoft InTune-Unternehmensportal-App für Ihre Testumgebung anzupassen.</span><span class="sxs-lookup"><span data-stu-id="4720a-113">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="4720a-114">Verwenden Sie als nächstes die Anweisungen unter [Einrichten des Zugriffs auf Ihre Unternehmensressourcen](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) , um ein IOS-Gerät einzuschreiben.</span><span class="sxs-lookup"><span data-stu-id="4720a-114">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="4720a-115">Verwenden Sie als nächstes die Anweisungen unter [Registrieren Ihres Android-Geräts in InTune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) , um ein Android-Gerät zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="4720a-115">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="4720a-116">Phase 3: Remoteverwaltung von IOS-und Android-Geräten</span><span class="sxs-lookup"><span data-stu-id="4720a-116">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="4720a-117">Microsoft Intune bietet sowohl Funktionen für eine Remotesperre und das Zurücksetzen der Kennung.</span><span class="sxs-lookup"><span data-stu-id="4720a-117">Microsoft Intune provides both remote lock and passcode reset capabilities.</span></span> <span data-ttu-id="4720a-118">Wenn jemand sein Gerät verliert, können Sie das Gerät remote sperren.</span><span class="sxs-lookup"><span data-stu-id="4720a-118">If someone loses their device, you can lock the device remotely.</span></span> <span data-ttu-id="4720a-119">Wenn Ihr Kennwort von einem Benutzer vergessen wird, können Sie es Remote zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="4720a-119">If someone forgets their passcode, you can reset it remotely.</span></span>
  
<span data-ttu-id="4720a-120">So sperren Sie ein IOS-oder Android-Gerät Remote</span><span class="sxs-lookup"><span data-stu-id="4720a-120">To lock an iOS or Android device remotely:</span></span>

1. <span data-ttu-id="4720a-121">Melden Sie sich beim Azure-Portal [https://portal.azure.com](https://portal.azure.com) unter mit den Anmeldeinformationen des globalen Administratorkontos an.</span><span class="sxs-lookup"><span data-stu-id="4720a-121">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="4720a-122">Klicken Sie auf **alle Dienste**, geben Sie **InTune**ein, und klicken Sie dann auf **InTune**.</span><span class="sxs-lookup"><span data-stu-id="4720a-122">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="4720a-123">Klicken Sie auf **Geräte > alle Geräte**.</span><span class="sxs-lookup"><span data-stu-id="4720a-123">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="4720a-124">Klicken Sie in der Liste der Geräte auf ein IOS-oder Android-Gerät, und klicken Sie dann auf die **Remote Sperr** Aktion.</span><span class="sxs-lookup"><span data-stu-id="4720a-124">In the list of devices, click an iOS or Android device, and then click the **Remote lock** action.</span></span>

    
<span data-ttu-id="4720a-125">So setzen Sie den Zugangscode remote zurück</span><span class="sxs-lookup"><span data-stu-id="4720a-125">To reset the passcode remotely:</span></span>

1. <span data-ttu-id="4720a-126">Melden Sie sich bei Bedarf im Azure-Portal unter [https://portal.azure.com](https://portal.azure.com) mit den Anmeldeinformationen des globalen Administratorkontos an.</span><span class="sxs-lookup"><span data-stu-id="4720a-126">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="4720a-127">Klicken Sie auf **alle Dienste**, geben Sie **InTune**ein, und klicken Sie dann auf **InTune**.</span><span class="sxs-lookup"><span data-stu-id="4720a-127">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="4720a-128">Klicken Sie auf **Geräte > alle Geräte**.</span><span class="sxs-lookup"><span data-stu-id="4720a-128">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="4720a-129">Klicken Sie in der Liste der Geräte, die Sie verwalten, auf ein IOS-oder Android-Gerät, und wählen Sie dann **... Mehr**.</span><span class="sxs-lookup"><span data-stu-id="4720a-129">From the list of devices you manage, click an iOS or Android device, and choose **...More**.</span></span> <span data-ttu-id="4720a-130">Wählen Sie dann die Remote Aktion "Kenncode-Gerät **Entfernen** " aus.</span><span class="sxs-lookup"><span data-stu-id="4720a-130">Then choose the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="4720a-131">Weitere Tests finden Sie unter [Verfügbare Geräteaktionen](https://docs.microsoft.com/intune/device-management#available-device-actions).</span><span class="sxs-lookup"><span data-stu-id="4720a-131">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>

    
## <a name="next-step"></a><span data-ttu-id="4720a-132">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="4720a-132">Next step</span></span>

<span data-ttu-id="4720a-133">Erkunden Sie zusätzliche Features und Funktionen für die [Verwaltung mobiler Geräte](m365-enterprise-test-lab-guides.md#mobile-device-management) in Ihrer Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="4720a-133">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="4720a-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4720a-134">See Also</span></span>

[<span data-ttu-id="4720a-135">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4720a-135">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="4720a-136">Geräte Konformitätsrichtlinien für Ihre Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="4720a-136">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="4720a-137">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4720a-137">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="4720a-138">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="4720a-138">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
