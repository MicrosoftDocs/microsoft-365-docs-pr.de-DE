---
title: Geräte in Microsoft Defender für Endpunkt integrieren
description: Nachverfolgen des Onboardings von von Intune verwalteten Geräten in Microsoft Defender für Endpunkt und Erhöhen der Onboardingrate.
keywords: Onboarding, Intune-Verwaltung, Microsoft Defender für Endpunkt, Microsoft Defender, Windows Defender, Konfigurationsverwaltung
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
ms.openlocfilehash: 7798f3b6bd2f99d48a8fa85ecf088023f4629b7b
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841570"
---
# <a name="get-devices-onboarded-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="30776-104">Geräte in Microsoft Defender für Endpunkt integrieren</span><span class="sxs-lookup"><span data-stu-id="30776-104">Get devices onboarded to Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="30776-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="30776-105">**Applies to:**</span></span>
- [<span data-ttu-id="30776-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="30776-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="30776-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="30776-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="30776-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="30776-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="30776-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="30776-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="30776-110">Jedes integrierte Gerät fügt einen zusätzlichen EDR (EDR)-Sensor hinzu und erhöht die Sichtbarkeit von Sicherheitsverletzungen in Ihrem Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="30776-110">Each onboarded device adds an additional endpoint detection and response (EDR) sensor and increases visibility over breach activity in your network.</span></span> <span data-ttu-id="30776-111">Durch das Onboarding wird außerdem sichergestellt, dass ein Gerät auf anfällige Komponenten sowie Auffälligkeiten bei der Sicherheitskonfiguration überprüft werden kann und kritische Abhilfemaßnahmen bei Angriffen empfangen werden können.</span><span class="sxs-lookup"><span data-stu-id="30776-111">Onboarding also ensures that a device can be checked for vulnerable components as well security configuration issues and can receive critical remediation actions during attacks.</span></span>

<span data-ttu-id="30776-112">Bevor Sie das Onboarding von Geräten nachverfolgen und verwalten können:</span><span class="sxs-lookup"><span data-stu-id="30776-112">Before you can track and manage onboarding of devices:</span></span>
- [<span data-ttu-id="30776-113">Registrieren Ihrer Geräte bei der Intune-Verwaltung</span><span class="sxs-lookup"><span data-stu-id="30776-113">Enroll your devices to Intune management</span></span>](configure-machines.md#enroll-devices-to-intune-management)
- [<span data-ttu-id="30776-114">Sicherstellen, dass Sie über die erforderlichen Berechtigungen verfügen</span><span class="sxs-lookup"><span data-stu-id="30776-114">Ensure you have the necessary permissions</span></span>](configure-machines.md#obtain-required-permissions)

## <a name="discover-and-track-unprotected-devices"></a><span data-ttu-id="30776-115">Ermitteln und Nachverfolgen ungeschützter Geräte</span><span class="sxs-lookup"><span data-stu-id="30776-115">Discover and track unprotected devices</span></span>

<span data-ttu-id="30776-116">Die **Onboardingkarte** bietet eine allgemeine Übersicht über Ihre Onboardingrate, indem die Anzahl der Windows 10 Geräte, die tatsächlich in Defender für Endpunkt integriert wurden, mit der Gesamtanzahl der von Intune verwalteten Windows 10 Geräte verglichen wird.</span><span class="sxs-lookup"><span data-stu-id="30776-116">The **Onboarding** card provides a high-level overview of your onboarding rate by comparing the number of Windows 10 devices that have actually onboarded to Defender for Endpoint against the total number of Intune-managed Windows 10 devices.</span></span>

<span data-ttu-id="30776-117">![Onboardingkarte für die Gerätekonfigurationsverwaltung](images/secconmgmt_onboarding_card.png)</span><span class="sxs-lookup"><span data-stu-id="30776-117">![Device configuration management Onboarding card](images/secconmgmt_onboarding_card.png)</span></span><br>
<span data-ttu-id="30776-118">*Karte mit integrierten Geräten im Vergleich zur Gesamtzahl der von Intune verwalteten Windows 10 Geräts*</span><span class="sxs-lookup"><span data-stu-id="30776-118">*Card showing onboarded devices compared to the total number of Intune-managed Windows 10 device*</span></span>

>[!NOTE]
><span data-ttu-id="30776-119">Wenn Sie Security Center Configuration Manager, das Onboarding-Skript oder andere Integrationsmethoden verwendet haben, die keine Intune-Profile verwenden, können Datenabweichungen auftreten.</span><span class="sxs-lookup"><span data-stu-id="30776-119">If you used Security Center Configuration Manager, the onboarding script, or other onboarding methods that don’t use Intune profiles, you might encounter data discrepancies.</span></span> <span data-ttu-id="30776-120">Um diese Abweichungen zu beheben, erstellen Sie ein entsprechendes Intune-Konfigurationsprofil für das Defender für Endpunkt-Onboarding, und weisen Sie dieses Profil Ihren Geräten zu.</span><span class="sxs-lookup"><span data-stu-id="30776-120">To resolve these discrepancies, create a corresponding Intune configuration profile for Defender for Endpoint onboarding and assign that profile to your devices.</span></span>

## <a name="onboard-more-devices-with-intune-profiles"></a><span data-ttu-id="30776-121">Onboarding weiterer Geräte mit Intune-Profilen</span><span class="sxs-lookup"><span data-stu-id="30776-121">Onboard more devices with Intune profiles</span></span>

<span data-ttu-id="30776-122">Defender für Endpunkt bietet mehrere praktische Optionen für [das Onboarding Windows 10 Geräte.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="30776-122">Defender for Endpoint provides several convenient options for [onboarding Windows 10 devices](onboard-configure.md).</span></span> <span data-ttu-id="30776-123">Für von Intune verwaltete Geräte können Sie intune-Profile jedoch nutzen, um den Defender für Endpunkt-Sensor bequem zur Auswahl von Geräten bereitzustellen und diese Geräte effektiv in den Dienst zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="30776-123">For Intune-managed devices, however, you can leverage Intune profiles to conveniently deploy the Defender for Endpoint sensor to select devices, effectively onboarding these devices to the service.</span></span>

<span data-ttu-id="30776-124">Wählen Sie auf der **Onboardingkarte** **"Onboarding" aus,** um weitere Geräte zu erstellen und ein Profil in Intune zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="30776-124">From the **Onboarding** card, select **Onboard more devices** to create and assign a profile on Intune.</span></span> <span data-ttu-id="30776-125">Der Link führt Sie zur Seite "Gerätekompatibilität" in Intune, die eine ähnliche Übersicht über Ihren Onboardingstatus bietet.</span><span class="sxs-lookup"><span data-stu-id="30776-125">The link takes you to the device compliance page on Intune, which provides a similar overview of your onboarding state.</span></span>

<span data-ttu-id="30776-126">![Microsoft Defender für Endpunkt- Gerätekompatibilitätsseite zur Intune-Geräteverwaltung](images/secconmgmt_onboarding_1deviceconfprofile.png)</span><span class="sxs-lookup"><span data-stu-id="30776-126">![Microsoft Defender for Endpoint device compliance page on Intune device management](images/secconmgmt_onboarding_1deviceconfprofile.png)</span></span><br>
   <span data-ttu-id="30776-127">*Microsoft Defender für Endpunkt- Gerätekompatibilitätsseite zur Intune-Geräteverwaltung*</span><span class="sxs-lookup"><span data-stu-id="30776-127">*Microsoft Defender for Endpoint device compliance page on Intune device management*</span></span>

>[!TIP]
><span data-ttu-id="30776-128">Alternativ können Sie im [Microsoft Azure Portal](https://portal.azure.com/) von allen Diensten > Intune **> Gerätekompatibilität**> Microsoft Defender ATP zur Complianceseite von Defender für Endpunkt navigieren.</span><span class="sxs-lookup"><span data-stu-id="30776-128">Alternatively, you can navigate to the Defender for Endpoint onboarding compliance page in the [Microsoft Azure portal](https://portal.azure.com/) from **All services > Intune > Device compliance > Microsoft Defender ATP**.</span></span>

>[!NOTE]
> <span data-ttu-id="30776-129">Wenn Sie die aktuellsten Gerätedaten anzeigen möchten, klicken Sie auf **die Liste der Geräte ohne ATP-Sensor.**</span><span class="sxs-lookup"><span data-stu-id="30776-129">If you want to view the most up-to-date device data, click on **List of devices without ATP sensor**.</span></span>

<span data-ttu-id="30776-130">Erstellen Sie auf der Seite "Gerätekompatibilität" ein Konfigurationsprofil speziell für die Bereitstellung des Defender für Endpunkt-Sensors, und weisen Sie dieses Profil den Geräten zu, die Sie integrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="30776-130">From the device compliance page, create a configuration profile specifically for the deployment of the Defender for Endpoint sensor and assign that profile to the devices you want to onboard.</span></span> <span data-ttu-id="30776-131">Zu diesem Zweck können Sie die folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="30776-131">To do this, you can either:</span></span>

- <span data-ttu-id="30776-132">Wählen Sie **"Erstellen eines Gerätekonfigurationsprofils" aus, um den ATP-Sensor** so zu konfigurieren, dass er mit einem vordefinierten Gerätekonfigurationsprofil beginnt.</span><span class="sxs-lookup"><span data-stu-id="30776-132">Select **Create a device configuration profile to configure ATP sensor** to start with a predefined device configuration profile.</span></span>
- <span data-ttu-id="30776-133">Erstellen Sie das Gerätekonfigurationsprofil von Grund auf neu.</span><span class="sxs-lookup"><span data-stu-id="30776-133">Create the device configuration profile from scratch.</span></span>

<span data-ttu-id="30776-134">Weitere Informationen [finden Sie unter Verwendung von Intune-Gerätekonfigurationsprofilen zum Onboarding von Geräten in Defender für Endpunkt.](/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile)</span><span class="sxs-lookup"><span data-stu-id="30776-134">For more information, [read about using Intune device configuration profiles to onboard devices to Defender for Endpoint](/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile).</span></span>

><span data-ttu-id="30776-135">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="30776-135">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="30776-136">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="30776-136">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="30776-137">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="30776-137">Related topics</span></span>
- [<span data-ttu-id="30776-138">Sicherstellen, dass Ihre Geräte ordnungsgemäß konfiguriert sind</span><span class="sxs-lookup"><span data-stu-id="30776-138">Ensure your devices are configured properly</span></span>](configure-machines.md)
- [<span data-ttu-id="30776-139">Erhöhen der Compliance für die Defender für Endpunkt-Sicherheitsgrundwerte</span><span class="sxs-lookup"><span data-stu-id="30776-139">Increase compliance to the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md)
- [<span data-ttu-id="30776-140">Optimieren der Bereitstellung und Erkennung von ASR-Regeln</span><span class="sxs-lookup"><span data-stu-id="30776-140">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md)
