---
title: Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten
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
description: Verwenden Sie Tools für die Verwaltung mobiler Geräte, um das Konfigurationspaket auf Geräten zu bereitstellen, sodass sie in den Dienst integrierte werden.
ms.openlocfilehash: 1ad1115308257fa3ce63f10edebb9129638fd52f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917991"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="762f8-103">Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten</span><span class="sxs-lookup"><span data-stu-id="762f8-103">Onboard Windows 10 devices using Mobile Device Management tools</span></span>

<span data-ttu-id="762f8-104">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="762f8-104">**Applies to:**</span></span>

- [<span data-ttu-id="762f8-105">Microsoft 365 Verhinderung von Endpunktdatenverlusten (Endpoint Data Loss Prevention, DLP)</span><span class="sxs-lookup"><span data-stu-id="762f8-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="762f8-106">Sie können Mobile Device Management (MDM)-Lösungen verwenden, um Geräte zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="762f8-106">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="762f8-107">Microsoft 365 Die Verhinderung von Endpunktdatenverlusten unterstützt MDMs, indem OMA-URIs zum Erstellen von Richtlinien zum Verwalten von Geräten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="762f8-107">Microsoft 365 Endpoint data loss prevention supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="762f8-108">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="762f8-108">Before you begin</span></span>
<span data-ttu-id="762f8-109">Wenn Sie eine Microsoft Intune verwenden, muss das Gerät MDM registriert sein.</span><span class="sxs-lookup"><span data-stu-id="762f8-109">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="762f8-110">Andernfalls werden einstellungen nicht erfolgreich angewendet.</span><span class="sxs-lookup"><span data-stu-id="762f8-110">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="762f8-111">Weitere Informationen zum Aktivieren von MDM mit Microsoft Intune finden Sie unter [Device enrollment (Microsoft Intune).](/mem/intune/enrollment/device-enrollment)</span><span class="sxs-lookup"><span data-stu-id="762f8-111">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="762f8-112">Onboarding von Geräten mithilfe Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="762f8-112">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="762f8-113">Befolgen Sie die Anweisungen von [Intune](/intune/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="762f8-113">Follow the instructions from [Intune](/intune/advanced-threat-protection).</span></span>

> [!NOTE]
> - <span data-ttu-id="762f8-114">Die **Richtlinie Integritätsstatus für integrierte Geräte** verwendet schreibgeschützte Eigenschaften und kann nicht behoben werden.</span><span class="sxs-lookup"><span data-stu-id="762f8-114">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="762f8-115">Offboard und Überwachen von Geräten mithilfe von Mobile Device Management Tools</span><span class="sxs-lookup"><span data-stu-id="762f8-115">Offboard and monitor devices using Mobile Device Management tools</span></span>

<span data-ttu-id="762f8-116">Aus Sicherheitsgründen läuft das für Offboard-Geräte verwendete Paket 30 Tage nach dem Downloaddatum ab.</span><span class="sxs-lookup"><span data-stu-id="762f8-116">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="762f8-117">Abgelaufene offboarding-Pakete, die an ein Gerät gesendet werden, werden abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="762f8-117">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="762f8-118">Beim Herunterladen eines offboarding-Pakets werden Sie über das Ablaufdatum der Pakete benachrichtigt und es wird auch im Paketnamen enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="762f8-118">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="762f8-119">Onboarding- und Offboardingrichtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, da andernfalls unvorhersehbare Kollisionen verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="762f8-119">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="762f8-120">Holen Sie sich das offboarding-Paket aus [dem Microsoft Compliance Center](https://compliance.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="762f8-120">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="762f8-121">Wählen Sie im Navigationsbereich die **option Einstellungen**  >  **Device onboarding**  >  **Offboarding aus.**</span><span class="sxs-lookup"><span data-stu-id="762f8-121">In the navigation pane, select **Settings** > **Device onboarding** > **Offboarding**.</span></span>

3. <span data-ttu-id="762f8-122">Wählen Sie **im Feld Bereitstellungsmethode** die Option **Mobile Geräteverwaltung/-Microsoft Intune.**</span><span class="sxs-lookup"><span data-stu-id="762f8-122">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune**.</span></span>
    
4. <span data-ttu-id="762f8-123">Klicken **Sie auf Paket** herunterladen, und speichern Sie .zip Datei.</span><span class="sxs-lookup"><span data-stu-id="762f8-123">Click **Download package**, and save the .zip file.</span></span>

5. <span data-ttu-id="762f8-124">Extrahieren Sie den Inhalt der .zip an einen freigegebenen, schreibgeschützten Speicherort, auf den die Netzwerkadministratoren zugreifen können, die das Paket bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="762f8-124">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="762f8-125">Sie sollten über eine Datei namens *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding verfügen.*</span><span class="sxs-lookup"><span data-stu-id="762f8-125">You should have a file named *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding*.</span></span>

6. <span data-ttu-id="762f8-126">Verwenden Sie Microsoft Intune benutzerdefinierte Konfigurationsrichtlinie, um die folgenden unterstützten OMA-URI-Einstellungen zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="762f8-126">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="762f8-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span><span class="sxs-lookup"><span data-stu-id="762f8-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span>      
      <span data-ttu-id="762f8-128">Datumstyp: Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="762f8-128">Date type: String</span></span>      
      <span data-ttu-id="762f8-129">Wert: [Kopieren und Einfügen des Werts aus dem Inhalt der DeviceCompliance_valid_until_YYYY-MM-DD.offboarding-Datei]</span><span class="sxs-lookup"><span data-stu-id="762f8-129">Value: [Copy and paste the value from the content of the DeviceCompliance_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="762f8-130">Weitere Informationen zu Microsoft Intune Richtlinieneinstellungen finden Sie [unter Windows 10 richtlinieneinstellungen in Microsoft Intune](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="762f8-130">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>

> [!NOTE]
> <span data-ttu-id="762f8-131">Die **Richtlinie Integritätsstatus für Offboardgeräte** verwendet schreibgeschützte Eigenschaften und kann nicht behoben werden.</span><span class="sxs-lookup"><span data-stu-id="762f8-131">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="762f8-132">Offboarding bewirkt, dass das Gerät das Senden von Sensordaten an das Portal beendet, aber Daten vom Gerät, einschließlich Verweis auf alle Warnungen, die es erhalten hat, werden für bis zu 6 Monate aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="762f8-132">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="762f8-133">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="762f8-133">Related topics</span></span>
- [<span data-ttu-id="762f8-134">Onboarding Windows 10 Geräte mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="762f8-134">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="762f8-135">Onboarding Windows 10 Geräte mithilfe Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="762f8-135">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="762f8-136">Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts</span><span class="sxs-lookup"><span data-stu-id="762f8-136">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="762f8-137">Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)</span><span class="sxs-lookup"><span data-stu-id="762f8-137">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="762f8-138">Problembehandlung bei Microsoft Defender Advanced Threat Protection Onboardingproblemen</span><span class="sxs-lookup"><span data-stu-id="762f8-138">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)