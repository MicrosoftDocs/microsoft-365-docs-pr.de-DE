---
title: Get devices onboarded to Microsoft Defender for Endpoint
description: Verfolgen Sie das Onboarding von von Intune verwalteten Geräten zu Microsoft Defender for Endpoint, und erhöhen Sie die Onboardingrate.
keywords: Onboard, Intune-Verwaltung, MDATP, WDATP, Microsoft Defender, Windows Defender, erweiterter Bedrohungsschutz, Konfigurationsverwaltung
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5e20c424f15561c8b6f0544b80aca6e30c56409d
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893329"
---
# <a name="get-devices-onboarded-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="371f7-104">Get devices onboarded to Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="371f7-104">Get devices onboarded to Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="371f7-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="371f7-105">**Applies to:**</span></span>
- [<span data-ttu-id="371f7-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="371f7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="371f7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="371f7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="371f7-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="371f7-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="371f7-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="371f7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="371f7-110">Jedes integrierte Gerät fügt einen zusätzlichen Endpunkterkennungs- und -reaktionssensor (EDR) hinzu und erhöht die Sichtbarkeit der Verletzungsaktivität in Ihrem Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="371f7-110">Each onboarded device adds an additional endpoint detection and response (EDR) sensor and increases visibility over breach activity in your network.</span></span> <span data-ttu-id="371f7-111">Das Onboarding stellt außerdem sicher, dass ein Gerät auf anfällige Komponenten sowie Sicherheitskonfigurationsprobleme überprüft werden kann und kritische Korrekturaktionen während von Angriffen erhalten kann.</span><span class="sxs-lookup"><span data-stu-id="371f7-111">Onboarding also ensures that a device can be checked for vulnerable components as well security configuration issues and can receive critical remediation actions during attacks.</span></span>

<span data-ttu-id="371f7-112">Bevor Sie das Onboarding von Geräten nachverfolgen und verwalten können:</span><span class="sxs-lookup"><span data-stu-id="371f7-112">Before you can track and manage onboarding of devices:</span></span>
- [<span data-ttu-id="371f7-113">Registrieren Ihrer Geräte bei der Intune-Verwaltung</span><span class="sxs-lookup"><span data-stu-id="371f7-113">Enroll your devices to Intune management</span></span>](configure-machines.md#enroll-devices-to-intune-management)
- [<span data-ttu-id="371f7-114">Sicherstellen, dass Sie über die erforderlichen Berechtigungen verfügen</span><span class="sxs-lookup"><span data-stu-id="371f7-114">Ensure you have the necessary permissions</span></span>](configure-machines.md#obtain-required-permissions)

## <a name="discover-and-track-unprotected-devices"></a><span data-ttu-id="371f7-115">Ermitteln und Nachverfolgen ungeschützter Geräte</span><span class="sxs-lookup"><span data-stu-id="371f7-115">Discover and track unprotected devices</span></span>

<span data-ttu-id="371f7-116">Die **Onboardingkarte** bietet einen umfassenden Überblick über Ihre Onboardingrate, indem sie die Anzahl der Windows 10-Geräte, die tatsächlich in Defender for Endpoint integrierte wurden, mit der Gesamtzahl der von Intune verwalteten Windows 10-Geräte vergleichen.</span><span class="sxs-lookup"><span data-stu-id="371f7-116">The **Onboarding** card provides a high-level overview of your onboarding rate by comparing the number of Windows 10 devices that have actually onboarded to Defender for Endpoint against the total number of Intune-managed Windows 10 devices.</span></span>

<span data-ttu-id="371f7-117">![Onboardingkarte für die Gerätekonfigurationsverwaltung](images/secconmgmt_onboarding_card.png)</span><span class="sxs-lookup"><span data-stu-id="371f7-117">![Device configuration management Onboarding card](images/secconmgmt_onboarding_card.png)</span></span><br>
<span data-ttu-id="371f7-118">*Karte mit integrierten Geräten im Vergleich zur Gesamtzahl der von Intune verwalteten Windows 10-Geräte*</span><span class="sxs-lookup"><span data-stu-id="371f7-118">*Card showing onboarded devices compared to the total number of Intune-managed Windows 10 device*</span></span>

>[!NOTE]
><span data-ttu-id="371f7-119">Wenn Sie Security Center Configuration Manager, das Onboardingskript oder andere Onboardingmethoden verwendet haben, die keine Intune-Profile verwenden, können Datenabweichungen auftreten.</span><span class="sxs-lookup"><span data-stu-id="371f7-119">If you used Security Center Configuration Manager, the onboarding script, or other onboarding methods that don’t use Intune profiles, you might encounter data discrepancies.</span></span> <span data-ttu-id="371f7-120">Um diese Abweichungen zu beheben, erstellen Sie ein entsprechendes Intune-Konfigurationsprofil für das Defender for Endpoint-Onboarding, und weisen Sie dieses Profil Ihren Geräten zu.</span><span class="sxs-lookup"><span data-stu-id="371f7-120">To resolve these discrepancies, create a corresponding Intune configuration profile for Defender for Endpoint onboarding and assign that profile to your devices.</span></span>

## <a name="onboard-more-devices-with-intune-profiles"></a><span data-ttu-id="371f7-121">Onboarding von weiteren Geräten mit Intune-Profilen</span><span class="sxs-lookup"><span data-stu-id="371f7-121">Onboard more devices with Intune profiles</span></span>

<span data-ttu-id="371f7-122">Defender for Endpoint bietet verschiedene praktische Optionen für [das Onboarding von Windows 10-Geräten.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="371f7-122">Defender for Endpoint provides several convenient options for [onboarding Windows 10 devices](onboard-configure.md).</span></span> <span data-ttu-id="371f7-123">Für von Intune verwaltete Geräte können Sie jedoch Intune-Profile nutzen, um den Defender for Endpoint-Sensor bequem bereitzustellen, um Geräte auszuwählen und diese Geräte effektiv in den Dienst zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="371f7-123">For Intune-managed devices, however, you can leverage Intune profiles to conveniently deploy the Defender for Endpoint sensor to select devices, effectively onboarding these devices to the service.</span></span>

<span data-ttu-id="371f7-124">Wählen Sie **auf der Onboardingkarte** weitere Geräte **integrieren** aus, um ein Profil in Intune zu erstellen und zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="371f7-124">From the **Onboarding** card, select **Onboard more devices** to create and assign a profile on Intune.</span></span> <span data-ttu-id="371f7-125">Der Link führt Sie zur Seite "Gerätekonformität" auf Intune, die eine ähnliche Übersicht über Ihren Onboardingstatus bietet.</span><span class="sxs-lookup"><span data-stu-id="371f7-125">The link takes you to the device compliance page on Intune, which provides a similar overview of your onboarding state.</span></span>

<span data-ttu-id="371f7-126">![Microsoft Defender ATP-Gerätekonformitätsseite zur Intune-Geräteverwaltung](images/secconmgmt_onboarding_1deviceconfprofile.png)</span><span class="sxs-lookup"><span data-stu-id="371f7-126">![Microsoft Defender ATP device compliance page on Intune device management](images/secconmgmt_onboarding_1deviceconfprofile.png)</span></span><br>
   <span data-ttu-id="371f7-127">*Microsoft Defender ATP-Gerätekonformitätsseite zur Intune-Geräteverwaltung*</span><span class="sxs-lookup"><span data-stu-id="371f7-127">*Microsoft Defender ATP device compliance page on Intune device management*</span></span>

>[!TIP]
><span data-ttu-id="371f7-128">Alternativ können Sie im [Microsoft Azure-Portal](https://portal.azure.com/) von Allen Diensten > Intune > Device compliance > **Microsoft Defender ATP** zur Seite Defender for Endpoint-Onboarding-Compliance navigieren.</span><span class="sxs-lookup"><span data-stu-id="371f7-128">Alternatively, you can navigate to the Defender for Endpoint onboarding compliance page in the [Microsoft Azure portal](https://portal.azure.com/) from **All services > Intune > Device compliance > Microsoft Defender ATP**.</span></span>

>[!NOTE]
> <span data-ttu-id="371f7-129">Wenn Sie die neuesten Gerätedaten anzeigen möchten, klicken Sie auf Liste der Geräte **ohne ATP-Sensor**.</span><span class="sxs-lookup"><span data-stu-id="371f7-129">If you want to view the most up-to-date device data, click on **List of devices without ATP sensor**.</span></span>

<span data-ttu-id="371f7-130">Erstellen Sie auf der Seite Gerätekonformität ein Konfigurationsprofil speziell für die Bereitstellung des Defender for Endpoint-Sensors, und weisen Sie dieses Profil den Geräten zu, die Sie onboarden möchten.</span><span class="sxs-lookup"><span data-stu-id="371f7-130">From the device compliance page, create a configuration profile specifically for the deployment of the Defender for Endpoint sensor and assign that profile to the devices you want to onboard.</span></span> <span data-ttu-id="371f7-131">Dazu können Sie entweder:</span><span class="sxs-lookup"><span data-stu-id="371f7-131">To do this, you can either:</span></span>

- <span data-ttu-id="371f7-132">Wählen **Sie Erstellen eines Gerätekonfigurationsprofils aus, um den ATP-Sensor** so zu konfigurieren, dass er mit einem vordefinierten Gerätekonfigurationsprofil beginnt.</span><span class="sxs-lookup"><span data-stu-id="371f7-132">Select **Create a device configuration profile to configure ATP sensor** to start with a predefined device configuration profile.</span></span>
- <span data-ttu-id="371f7-133">Erstellen Sie das Gerätekonfigurationsprofil von Grund auf neu.</span><span class="sxs-lookup"><span data-stu-id="371f7-133">Create the device configuration profile from scratch.</span></span>

<span data-ttu-id="371f7-134">Weitere Informationen finden Sie [unter Verwenden von Intune-Gerätekonfigurationsprofilen zum Onboarding von Geräten in Defender for Endpoint](https://docs.microsoft.com/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile).</span><span class="sxs-lookup"><span data-stu-id="371f7-134">For more information, [read about using Intune device configuration profiles to onboard devices to Defender for Endpoint](https://docs.microsoft.com/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile).</span></span>

><span data-ttu-id="371f7-135">Möchten Sie Microsoft Defender ATP erleben?</span><span class="sxs-lookup"><span data-stu-id="371f7-135">Want to experience Microsoft Defender ATP?</span></span> [<span data-ttu-id="371f7-136">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="371f7-136">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="371f7-137">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="371f7-137">Related topics</span></span>
- [<span data-ttu-id="371f7-138">Sicherstellen, dass Ihre Geräte ordnungsgemäß konfiguriert sind</span><span class="sxs-lookup"><span data-stu-id="371f7-138">Ensure your devices are configured properly</span></span>](configure-machines.md)
- [<span data-ttu-id="371f7-139">Erhöhen der Einhaltung der Sicherheitsgrundlinie für Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="371f7-139">Increase compliance to the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md)
- [<span data-ttu-id="371f7-140">Optimieren der Bereitstellung und Erkennung von ASR-Regeln</span><span class="sxs-lookup"><span data-stu-id="371f7-140">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md)
