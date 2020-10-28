---
title: Integrierte Windows 10-Geräte mit Tools zur Verwaltung mobiler Geräte
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Verwenden Sie die Tools für die Verwaltung mobiler Geräte, um das Konfigurationspaket auf Geräten bereitzustellen, damit diese in den Dienst eingehen.
ms.openlocfilehash: 1480c918589a1f00e00ceb1233e9a62887ccff32
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769481"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="02d1a-103">Integrierte Windows 10-Geräte mit Tools zur Verwaltung mobiler Geräte</span><span class="sxs-lookup"><span data-stu-id="02d1a-103">Onboard Windows 10 devices using Mobile Device Management tools</span></span>

<span data-ttu-id="02d1a-104">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="02d1a-104">**Applies to:**</span></span>

- [<span data-ttu-id="02d1a-105">Microsoft 365 Endpunkt-Datenverlust Verhinderung (DLP)</span><span class="sxs-lookup"><span data-stu-id="02d1a-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

<span data-ttu-id="02d1a-106">Sie können MDM-Lösungen (Mobile Device Management) zum Konfigurieren von Geräten verwenden.</span><span class="sxs-lookup"><span data-stu-id="02d1a-106">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="02d1a-107">Microsoft 365 Endpoint Data Loss Prevention unterstützt MDMs, indem OMA-URIs zum Erstellen von Richtlinien zum Verwalten von Geräten bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="02d1a-107">Microsoft 365 Endpoint data loss prevention supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="02d1a-108">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="02d1a-108">Before you begin</span></span>
<span data-ttu-id="02d1a-109">Wenn Sie Microsoft InTune verwenden, muss das Gerät MDM registriert sein.</span><span class="sxs-lookup"><span data-stu-id="02d1a-109">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="02d1a-110">Andernfalls werden Einstellungen nicht erfolgreich angewendet.</span><span class="sxs-lookup"><span data-stu-id="02d1a-110">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="02d1a-111">Weitere Informationen zum Aktivieren von MDM mit Microsoft InTune finden Sie unter [Device Enrollment (Microsoft InTune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment).</span><span class="sxs-lookup"><span data-stu-id="02d1a-111">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="02d1a-112">Integrierte Geräte mit Microsoft InTune</span><span class="sxs-lookup"><span data-stu-id="02d1a-112">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="02d1a-113">Befolgen Sie die Anweisungen von [InTune](https://docs.microsoft.com/intune/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="02d1a-113">Follow the instructions from [Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span></span>

> [!NOTE]
> - <span data-ttu-id="02d1a-114">Der **Integritäts Status für die Richtlinie für integrierte Geräte** verwendet schreibgeschützte Eigenschaften und kann nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="02d1a-114">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="02d1a-115">Extern und Überwachen von Geräten mithilfe von Tools zur Verwaltung mobiler Geräte</span><span class="sxs-lookup"><span data-stu-id="02d1a-115">Offboard and monitor devices using Mobile Device Management tools</span></span>

<span data-ttu-id="02d1a-116">Aus Sicherheitsgründen läuft das Paket, das für extern-Geräte verwendet wird, 30 Tage nach dem heruntergeladenen Datum ab.</span><span class="sxs-lookup"><span data-stu-id="02d1a-116">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="02d1a-117">Abgelaufene offboarding-Pakete, die an ein Gerät gesendet werden, werden zurückgewiesen.</span><span class="sxs-lookup"><span data-stu-id="02d1a-117">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="02d1a-118">Wenn Sie ein offboarding-Paket herunterladen, werden Sie über das Ablaufdatum der Pakete benachrichtigt, und es wird auch in den Paketnamen eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="02d1a-118">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="02d1a-119">Onboarding-und offboarding-Richtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, da dies andernfalls zu unvorhersehbaren Konflikten führen kann.</span><span class="sxs-lookup"><span data-stu-id="02d1a-119">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="02d1a-120">Rufen Sie das offboarding-Paket im [Microsoft Compliance Center](https://compliance.microsoft.com/)ab.</span><span class="sxs-lookup"><span data-stu-id="02d1a-120">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="02d1a-121">Wählen Sie im Navigationsbereich **Einstellungen**  >  **Gerät Onboarding**  >  **Offboarding** .</span><span class="sxs-lookup"><span data-stu-id="02d1a-121">In the navigation pane, select **Settings** > **Device onboarding** > **Offboarding** .</span></span>

3. <span data-ttu-id="02d1a-122">Wählen Sie im Feld **Bereitstellungsmethode** die Option **Verwaltung mobiler Geräte/Microsoft InTune** aus.</span><span class="sxs-lookup"><span data-stu-id="02d1a-122">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune** .</span></span>
    
4. <span data-ttu-id="02d1a-123">Klicken Sie auf **Paket herunterladen** , und speichern Sie die ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="02d1a-123">Click **Download package** , and save the .zip file.</span></span>

5. <span data-ttu-id="02d1a-124">Extrahieren Sie den Inhalt der ZIP-Datei an einen freigegebenen, schreibgeschützten Speicherort, auf den die Netzwerkadministratoren zugreifen können, die das Paket bereitstellen werden.</span><span class="sxs-lookup"><span data-stu-id="02d1a-124">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="02d1a-125">Sie sollten über eine Datei mit dem Namen *DeviceCompliance_valid_until_YYYY-mm-dd. offboarding* verfügen.</span><span class="sxs-lookup"><span data-stu-id="02d1a-125">You should have a file named *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding* .</span></span>

6. <span data-ttu-id="02d1a-126">Verwenden Sie die benutzerdefinierte Konfigurationsrichtlinie von Microsoft InTune, um die folgenden unterstützten Oma-URI-Einstellungen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="02d1a-126">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="02d1a-127">Oma-URI:./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span><span class="sxs-lookup"><span data-stu-id="02d1a-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span>      
      <span data-ttu-id="02d1a-128">Date-Typ: String</span><span class="sxs-lookup"><span data-stu-id="02d1a-128">Date type: String</span></span>      
      <span data-ttu-id="02d1a-129">Wert: [Kopieren und Einfügen des Werts aus dem Inhalt der Datei DeviceCompliance_valid_until_YYYY-mm-dd. offboarding]</span><span class="sxs-lookup"><span data-stu-id="02d1a-129">Value: [Copy and paste the value from the content of the DeviceCompliance_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="02d1a-130">Weitere Informationen zu den Microsoft InTune-Richtlinieneinstellungen finden Sie unter [Windows 10-Richtlinieneinstellungen in Microsoft InTune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="02d1a-130">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>

> [!NOTE]
> <span data-ttu-id="02d1a-131">Der **Integritäts Status für** die Richtlinie für offboarded-Geräte verwendet schreibgeschützte Eigenschaften und kann nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="02d1a-131">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="02d1a-132">Offboarding bewirkt, dass das Gerät das Senden von Sensordaten an das Portal beendet, aber die Daten des Geräts, einschließlich des Verweises auf bereits gemachte Warnungen, werden bis zu 6 Monate aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="02d1a-132">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="02d1a-133">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="02d1a-133">Related topics</span></span>
- [<span data-ttu-id="02d1a-134">Integrierte Windows 10-Geräte mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="02d1a-134">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="02d1a-135">Onboard-Windows 10-Geräte mit Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="02d1a-135">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="02d1a-136">Onboard-Windows 10-Geräte mithilfe eines lokalen Skripts</span><span class="sxs-lookup"><span data-stu-id="02d1a-136">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="02d1a-137">Onboard-VDI-Geräte (Non-persistent Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="02d1a-137">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="02d1a-138">Problembehandlung bei Onboarding-Problemen bei Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="02d1a-138">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
