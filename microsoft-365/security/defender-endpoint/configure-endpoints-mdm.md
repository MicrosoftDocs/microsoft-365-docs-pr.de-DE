---
title: Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten
description: Verwenden Sie Tools für die Verwaltung mobiler Geräte, um das Konfigurationspaket auf Geräten zu bereitstellen, sodass sie in den Dienst integrierte werden.
keywords: Onboarding von Geräten mithilfe von mdm, Geräteverwaltung, Onboarding von Windows ATP-Geräten, Onboarding von Microsoft Defender for Endpoint-Geräten, mdm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f3042ef9ced11ebc5439308d2781528d5267975f
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893613"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="a2ce0-104">Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten</span><span class="sxs-lookup"><span data-stu-id="a2ce0-104">Onboard Windows 10 devices using Mobile Device Management tools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a2ce0-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a2ce0-105">**Applies to:**</span></span>
- [<span data-ttu-id="a2ce0-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="a2ce0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a2ce0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a2ce0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="a2ce0-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="a2ce0-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a2ce0-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsmdm-abovefoldlink)

<span data-ttu-id="a2ce0-110">Sie können Mobile Device Management (MDM)-Lösungen verwenden, um Geräte zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-110">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="a2ce0-111">Defender for Endpoint unterstützt MDMs, indem OMA-URIs zum Erstellen von Richtlinien zum Verwalten von Geräten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-111">Defender for Endpoint supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>

<span data-ttu-id="a2ce0-112">Weitere Informationen zur Verwendung von Defender for Endpoint CSP finden Sie unter [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) und [WindowsAdvancedThreatProtection DDF file](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="a2ce0-112">For more information on using Defender for Endpoint CSP see, [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) and [WindowsAdvancedThreatProtection DDF file](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a2ce0-113">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="a2ce0-113">Before you begin</span></span>
<span data-ttu-id="a2ce0-114">Wenn Sie Microsoft Intune verwenden, muss das Gerät MDM registriert sein.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-114">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="a2ce0-115">Andernfalls werden einstellungen nicht erfolgreich angewendet.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-115">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="a2ce0-116">Weitere Informationen zum Aktivieren von MDM mit Microsoft Intune finden Sie unter [Device enrollment (Microsoft Intune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment).</span><span class="sxs-lookup"><span data-stu-id="a2ce0-116">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="a2ce0-117">Onboarding von Geräten mithilfe von Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a2ce0-117">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="a2ce0-118">[![Abbildung der PDF mit Onboardinggeräten für Defender for Endpoint mithilfe von Microsoft Intune ](images/onboard-intune.png)](images/onboard-intune-big.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="a2ce0-118">[![Image of the PDF showing onboarding devices to Defender for Endpoint using Microsoft Intune](images/onboard-intune.png) ](images/onboard-intune-big.png#lightbox)</span></span>

<span data-ttu-id="a2ce0-119">Sehen Sie sich [die PDF-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  oder  [Visio-Datei](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) an, um die verschiedenen Pfade bei der Bereitstellung von Defender for Endpoint zu sehen.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-119">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span> 

<span data-ttu-id="a2ce0-120">Befolgen Sie die Anweisungen von [Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="a2ce0-120">Follow the instructions from [Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span></span>

<span data-ttu-id="a2ce0-121">Weitere Informationen zur Verwendung von Defender for Endpoint CSP finden Sie unter [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) und [WindowsAdvancedThreatProtection DDF file](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="a2ce0-121">For more information on using Defender for Endpoint CSP see, [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) and [WindowsAdvancedThreatProtection DDF file](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx).</span></span>


> [!NOTE]
> - <span data-ttu-id="a2ce0-122">Die **Richtlinie Integritätsstatus für integrierte Geräte** verwendet schreibgeschützte Eigenschaften und kann nicht behoben werden.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-122">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>
> - <span data-ttu-id="a2ce0-123">Die Konfiguration der Häufigkeit der Diagnosedatenberichte ist nur für Geräte unter Windows 10, Version 1703, verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-123">Configuration of diagnostic data reporting frequency is only available for devices on Windows 10, version 1703.</span></span>


>[!TIP]
> <span data-ttu-id="a2ce0-124">Nach dem Onboarding des Geräts können Sie einen Erkennungstest ausführen, um zu überprüfen, ob ein Gerät ordnungsgemäß in den Dienst integrierte wurde.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-124">After onboarding the device, you can choose to run a detection test to verify that a device is properly onboarded to the service.</span></span> <span data-ttu-id="a2ce0-125">Weitere Informationen finden Sie unter Ausführen eines Erkennungstests auf einem neu integrierten [Microsoft Defender for Endpoint-Gerät.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="a2ce0-125">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](run-detection-test.md).</span></span>


<span data-ttu-id="a2ce0-126">Sehen Sie sich [die PDF-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  oder  [Visio-Datei](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) an, um die verschiedenen Pfade bei der Bereitstellung von Microsoft Defender for Endpoint zu sehen.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-126">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Microsoft Defender for Endpoint.</span></span>

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="a2ce0-127">Offboard und Überwachen von Geräten mithilfe von Mobile Device Management Tools</span><span class="sxs-lookup"><span data-stu-id="a2ce0-127">Offboard and monitor devices using Mobile Device Management tools</span></span>
<span data-ttu-id="a2ce0-128">Aus Sicherheitsgründen läuft das für Offboard-Geräte verwendete Paket 30 Tage nach dem Downloaddatum ab.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="a2ce0-129">Abgelaufene offboarding-Pakete, die an ein Gerät gesendet werden, werden abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-129">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="a2ce0-130">Beim Herunterladen eines offboarding-Pakets werden Sie über das Ablaufdatum der Pakete benachrichtigt und es wird auch im Paketnamen enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="a2ce0-131">Onboarding- und Offboardingrichtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, da andernfalls unvorhersehbare Kollisionen verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="a2ce0-132">Das offboarding-Paket aus [dem Microsoft Defender Security Center erhalten:](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="a2ce0-132">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

   1. <span data-ttu-id="a2ce0-133">Wählen Sie im Navigationsbereich **Einstellungen**  >  **Offboarding aus.**</span><span class="sxs-lookup"><span data-stu-id="a2ce0-133">In the navigation pane, select **Settings** > **Offboarding**.</span></span>

   1. <span data-ttu-id="a2ce0-134">Wählen Sie Windows 10 als Betriebssystem aus.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-134">Select Windows 10 as the operating system.</span></span>

   1. <span data-ttu-id="a2ce0-135">Wählen Sie **im Feld Bereitstellungsmethode** die Option **Mobile Geräteverwaltung /Microsoft Intune aus.**</span><span class="sxs-lookup"><span data-stu-id="a2ce0-135">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune**.</span></span>
    
   1. <span data-ttu-id="a2ce0-136">Klicken **Sie auf Paket herunterladen,** und speichern Sie die ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-136">Click **Download package**, and save the .zip file.</span></span>

2. <span data-ttu-id="a2ce0-137">Extrahieren Sie den Inhalt der ZIP-Datei an einen freigegebenen schreibgeschützten Speicherort, auf den die Netzwerkadministratoren zugreifen können, die das Paket bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-137">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="a2ce0-138">Sie sollten über eine Datei namens *WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding verfügen.*</span><span class="sxs-lookup"><span data-stu-id="a2ce0-138">You should have a file named *WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding*.</span></span>

3. <span data-ttu-id="a2ce0-139">Verwenden Sie die benutzerdefinierte Microsoft Intune-Konfigurationsrichtlinie, um die folgenden unterstützten OMA-URI-Einstellungen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-139">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="a2ce0-140">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span><span class="sxs-lookup"><span data-stu-id="a2ce0-140">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span><br/>
      <span data-ttu-id="a2ce0-141">Datumstyp: Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a2ce0-141">Date type: String</span></span><br/>
      <span data-ttu-id="a2ce0-142">Wert: [Kopieren und Einfügen des Werts aus dem Inhalt der WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding-Datei]</span><span class="sxs-lookup"><span data-stu-id="a2ce0-142">Value: [Copy and paste the value from the content of the WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="a2ce0-143">Weitere Informationen zu Microsoft Intune-Richtlinieneinstellungen finden Sie unter [Windows 10-Richtlinieneinstellungen in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="a2ce0-143">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>


> [!NOTE]
> <span data-ttu-id="a2ce0-144">Die **Richtlinie Integritätsstatus für Offboardgeräte** verwendet schreibgeschützte Eigenschaften und kann nicht behoben werden.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-144">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a2ce0-145">Offboarding bewirkt, dass das Gerät das Senden von Sensordaten an das Portal beendet, aber Daten vom Gerät, einschließlich Verweis auf alle Warnungen, die es erhalten hat, werden für bis zu 6 Monate aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="a2ce0-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a2ce0-146">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a2ce0-146">Related topics</span></span>
- [<span data-ttu-id="a2ce0-147">Onboarding von Windows 10-Geräten mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="a2ce0-147">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="a2ce0-148">Onboarding von Windows 10-Geräten mithilfe von Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a2ce0-148">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="a2ce0-149">Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts</span><span class="sxs-lookup"><span data-stu-id="a2ce0-149">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="a2ce0-150">Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)</span><span class="sxs-lookup"><span data-stu-id="a2ce0-150">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="a2ce0-151">Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender for Endpoint-Gerät</span><span class="sxs-lookup"><span data-stu-id="a2ce0-151">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="a2ce0-152">Behandeln von Problemen beim Onboarding von Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a2ce0-152">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
