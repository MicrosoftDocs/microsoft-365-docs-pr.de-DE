---
title: Microsoft Defender for Endpoint Device Control Removable Storage Protection
description: Verstehen der "Funktionen, die verhindern, dass Benutzer oder Computer oder beide nicht autorisierte Wechselmedien verwenden
keywords: Wechselmedien
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-smandalika
author: v-smandalika
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c9b97c2157ba8090628af23b2ab54cf38f04d8c6
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538387"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a><span data-ttu-id="e59f1-104">Microsoft Defender for Endpoint Device Control Removable Storage Protection</span><span class="sxs-lookup"><span data-stu-id="e59f1-104">Microsoft Defender for Endpoint Device Control Removable Storage Protection</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="e59f1-105">Microsoft Defender for Endpoint Device Control Storage Protection verhindert, dass Benutzer oder Computer oder beide nicht autorisierte Wechselmedien verwenden.</span><span class="sxs-lookup"><span data-stu-id="e59f1-105">Microsoft Defender for Endpoint Device Control Removable Storage Protection prevents user or machine or both from using unauthorized removable storage media.</span></span>

## <a name="protection-policies"></a><span data-ttu-id="e59f1-106">Schutzrichtlinien</span><span class="sxs-lookup"><span data-stu-id="e59f1-106">Protection policies</span></span>

### <a name="device-installation"></a><span data-ttu-id="e59f1-107">Geräteinstallation</span><span class="sxs-lookup"><span data-stu-id="e59f1-107">Device installation</span></span>

<span data-ttu-id="e59f1-108">**Funktionen** – Verhindern der Installation mit oder ohne Ausschluss basierend auf verschiedenen Geräteeigenschaften.</span><span class="sxs-lookup"><span data-stu-id="e59f1-108">**Capabilities** - Prevent installation with or without exclusion based on various device properties.</span></span>

<span data-ttu-id="e59f1-109">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e59f1-109">**Description**</span></span>
- <span data-ttu-id="e59f1-110">Auf Computerebene angewendet: Die gleiche Richtlinie gilt für alle angemeldeten Benutzer.</span><span class="sxs-lookup"><span data-stu-id="e59f1-110">Applied at machine level: the same policy applies for any logged on user.</span></span>
- <span data-ttu-id="e59f1-111">Unterstützt MEM und GPO.</span><span class="sxs-lookup"><span data-stu-id="e59f1-111">Supports MEM and GPO.</span></span>
- <span data-ttu-id="e59f1-112">Unterstützte '[Geräteeigenschaften](#device-properties)' wie aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="e59f1-112">Supported  ‘[Device Properties](#device-properties)’ as listed.</span></span>
- <span data-ttu-id="e59f1-113">Weitere Informationen zu Windows finden Sie unter Steuern von USB-Geräten und anderen Wechselmedien mithilfe [von Microsoft Defender for Endpoint](control-usb-devices-using-intune.md).</span><span class="sxs-lookup"><span data-stu-id="e59f1-113">For more information on Windows, see [How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md).</span></span>

<span data-ttu-id="e59f1-114">**Unterstützte Plattform** – Windows 10</span><span class="sxs-lookup"><span data-stu-id="e59f1-114">**Supported Platform** - Windows 10</span></span>

<span data-ttu-id="e59f1-115">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e59f1-115">**Description**</span></span>
- <span data-ttu-id="e59f1-116">Auf Computerebene angewendet: Die gleiche Richtlinie gilt für alle angemeldeten Benutzer</span><span class="sxs-lookup"><span data-stu-id="e59f1-116">Applied at machine level: the same policy applies for any logged on user</span></span>
- <span data-ttu-id="e59f1-117">MacOS-spezifische Informationen finden Sie unter [Gerätesteuerelement für macOS](mac-device-control-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e59f1-117">For macOS specific information, see [Device control for macOS](mac-device-control-overview.md).</span></span>
 
<span data-ttu-id="e59f1-118">**Unterstützte Plattform** – macOS Catalina 10.15.4+ (mit aktivierten Systemerweiterungen)</span><span class="sxs-lookup"><span data-stu-id="e59f1-118">**Supported platform** - macOS Catalina 10.15.4+ (with system extensions enabled)</span></span>

### <a name="removable-storage-access-control"></a><span data-ttu-id="e59f1-119">Zugriffssteuerung für Wechselmedien</span><span class="sxs-lookup"><span data-stu-id="e59f1-119">Removable storage Access Control</span></span>

<span data-ttu-id="e59f1-120">**Capabilities**</span><span class="sxs-lookup"><span data-stu-id="e59f1-120">**Capabilities**</span></span>
- <span data-ttu-id="e59f1-121">*Überwachung* Lese-, Schreib- oder Ausführungszugriff auf Wechseldatenträger basierend auf verschiedenen Geräteeigenschaften, mit oder ohne Ausschluss.</span><span class="sxs-lookup"><span data-stu-id="e59f1-121">*Audit* Read or Write or Execute access to removable storage based on various device properties, with or without an exclusion.</span></span>
- <span data-ttu-id="e59f1-122">*Verhindern* Lese- oder Schreibzugriff oder Ausführen des Zugriffs mit oder ohne Ausschluss – Zulassen eines bestimmten Geräts basierend auf verschiedenen Geräteeigenschaften.</span><span class="sxs-lookup"><span data-stu-id="e59f1-122">*Prevent* Read or Write or Execute access with or without an exclusion - Allow specific device based on various device properties.</span></span>

<span data-ttu-id="e59f1-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e59f1-123">**Description**</span></span>
- <span data-ttu-id="e59f1-124">Wird auf einem Computer oder Benutzer oder auf beiden Angewendet – nur bestimmten Personen, die Lese-/Schreib-/Ausführungszugriff auf bestimmte Wechseldatenträger auf einem bestimmten Computer ausführen, erlauben.</span><span class="sxs-lookup"><span data-stu-id="e59f1-124">Applied at either machine or user or both – only allow specific people performing Read/Write/Execute access to specific removable storage on specific machine.</span></span>
- <span data-ttu-id="e59f1-125">Unterstützt MEM OMA-URI und GPO.</span><span class="sxs-lookup"><span data-stu-id="e59f1-125">Support MEM OMA-URI and GPO.</span></span>
- <span data-ttu-id="e59f1-126">Unterstützte '[Geräteeigenschaften](#device-properties)' wie aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="e59f1-126">Supported  ‘[Device Properties](#device-properties)’ as listed.</span></span>
- <span data-ttu-id="e59f1-127">Informationen zu features in Windows finden Sie unter [Wechselmedienzugriffssteuerung](device-control-removable-storage-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="e59f1-127">For feature in Windows, see [Removable storage Access Control](device-control-removable-storage-access-control.md).</span></span>

<span data-ttu-id="e59f1-128">**Unterstützte Plattform** – Windows 10</span><span class="sxs-lookup"><span data-stu-id="e59f1-128">**Supported Platform** - Windows 10</span></span>

<span data-ttu-id="e59f1-129">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e59f1-129">**Description**</span></span>
- <span data-ttu-id="e59f1-130">Auf Computerebene angewendet: Die gleiche Richtlinie gilt für alle angemeldeten Benutzer.</span><span class="sxs-lookup"><span data-stu-id="e59f1-130">Applied at machine level: the same policy applies for any logged on user.</span></span>
- <span data-ttu-id="e59f1-131">MacOS-spezifische Informationen finden Sie unter [Gerätesteuerelement für macOS](mac-device-control-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e59f1-131">For macOS specific information, see [Device control for macOS](mac-device-control-overview.md).</span></span>
 
<span data-ttu-id="e59f1-132">**Unterstützte Plattform** – macOS Catalina 10.15.4+ (mit aktivierten Systemerweiterungen)</span><span class="sxs-lookup"><span data-stu-id="e59f1-132">**Supported platform** - macOS Catalina 10.15.4+ (with system extensions enabled)</span></span>

### <a name="windows-portable-device-access-control"></a><span data-ttu-id="e59f1-133">Windows Zugriffssteuerung für tragbare Geräte</span><span class="sxs-lookup"><span data-stu-id="e59f1-133">Windows Portable Device Access Control</span></span>

<span data-ttu-id="e59f1-134">**Funktionen** – Verweigern des Lese- oder Schreibzugriffs auf [Windows tragbaren](/windows-hardware/drivers/portable/)Gerät, z. B. Tablet, iPhone.</span><span class="sxs-lookup"><span data-stu-id="e59f1-134">**Capabilities** - Deny Read or Write access to any [Windows Portable Device](/windows-hardware/drivers/portable/), for example: Tablet, iPhone.</span></span>

<span data-ttu-id="e59f1-135">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e59f1-135">**Description**</span></span>
- <span data-ttu-id="e59f1-136">Wird auf dem Computer oder Benutzer oder auf beiden angewendet.</span><span class="sxs-lookup"><span data-stu-id="e59f1-136">Applied at either machine or user or both.</span></span>
- <span data-ttu-id="e59f1-137">Unterstützt MEM OMA-URI und GPO.</span><span class="sxs-lookup"><span data-stu-id="e59f1-137">Support MEM OMA-URI and GPO.</span></span>

<span data-ttu-id="e59f1-138">**Unterstützte Plattform** – Windows 10</span><span class="sxs-lookup"><span data-stu-id="e59f1-138">**Supported Platform** - Windows 10</span></span>

### <a name="endpoint-dlp-removable-storage"></a><span data-ttu-id="e59f1-139">Endpunkt-DLP-Wechseldatenträger</span><span class="sxs-lookup"><span data-stu-id="e59f1-139">Endpoint DLP Removable storage</span></span>

<span data-ttu-id="e59f1-140">**Funktionen** – Überwachen oder Warnen oder Verhindern, dass ein Benutzer ein Element oder Informationen auf Wechselmedien oder USB-Geräte kopiert.</span><span class="sxs-lookup"><span data-stu-id="e59f1-140">**Capabilities** - Audit or Warn or Prevent a user from copying an item or information to removable media or USB device.</span></span>

<span data-ttu-id="e59f1-141">**Beschreibung** – Weitere Informationen zu Windows finden Sie [unter Learn about Microsoft 365 Endpoint data loss prevention](../../compliance/endpoint-dlp-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="e59f1-141">**Description** - For more information on Windows, see [Learn about Microsoft 365 Endpoint data loss prevention](../../compliance/endpoint-dlp-learn-about.md).</span></span>

<span data-ttu-id="e59f1-142">**Unterstützte Plattform** – Windows 10</span><span class="sxs-lookup"><span data-stu-id="e59f1-142">**Supported Platform** - Windows 10</span></span>

### <a name="bitlocker"></a><span data-ttu-id="e59f1-143">BitLocker</span><span class="sxs-lookup"><span data-stu-id="e59f1-143">BitLocker</span></span> 

<span data-ttu-id="e59f1-144">**Capabilities**</span><span class="sxs-lookup"><span data-stu-id="e59f1-144">**Capabilities**</span></span>
- <span data-ttu-id="e59f1-145">Blockieren von Daten, die auf Wechseldatenträger geschrieben werden sollen, die nicht BitLocker sind.</span><span class="sxs-lookup"><span data-stu-id="e59f1-145">Block data to be written to removable drives that aren't BitLocker protected.</span></span>
- <span data-ttu-id="e59f1-146">Blockieren des Zugriffs auf Wechseldatenträger, es sei denn, sie wurden auf einem Computer im Besitz Ihrer Organisation verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="e59f1-146">Block access to removable drives unless they were encrypted on a computer owned by your organization</span></span>
 
<span data-ttu-id="e59f1-147">**Beschreibung** – Weitere Informationen zu Windows finden Sie [unter BitLocker – Wechseldatenträger Einstellungen](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings).</span><span class="sxs-lookup"><span data-stu-id="e59f1-147">**Description** - For more information on Windows, see [BitLocker – Removable Drive Settings](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings).</span></span>

<span data-ttu-id="e59f1-148">**Unterstützte Plattform** – Windows 10</span><span class="sxs-lookup"><span data-stu-id="e59f1-148">**Supported Platform** - Windows 10</span></span>

## <a name="device-properties"></a><span data-ttu-id="e59f1-149">Geräteeigenschaften</span><span class="sxs-lookup"><span data-stu-id="e59f1-149">Device properties</span></span>

<span data-ttu-id="e59f1-150">Mit Microsoft Defender for Endpoint Device Control Removable Storage Protection können Sie den Wechselspeicherzugriff basierend auf den in der folgenden Tabelle beschriebenen Eigenschaften einschränken:</span><span class="sxs-lookup"><span data-stu-id="e59f1-150">Microsoft Defender for Endpoint Device Control Removable Storage Protection allows you to restrict the removable storage access based on the properties described in the table below:</span></span>


|<span data-ttu-id="e59f1-151">Eigenschaftenname</span><span class="sxs-lookup"><span data-stu-id="e59f1-151">Property Name</span></span>  |<span data-ttu-id="e59f1-152">Anwendbare Richtlinien</span><span class="sxs-lookup"><span data-stu-id="e59f1-152">Applicable Policies</span></span>  |<span data-ttu-id="e59f1-153">Gilt für Betriebssysteme</span><span class="sxs-lookup"><span data-stu-id="e59f1-153">Applies to Operating Systems</span></span>  |<span data-ttu-id="e59f1-154">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e59f1-154">Description</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="e59f1-155">Geräteklasse</span><span class="sxs-lookup"><span data-stu-id="e59f1-155">Device Class</span></span>    |     [<span data-ttu-id="e59f1-156">Steuern von USB-Geräten und anderen Wechselmedien mithilfe von Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e59f1-156">How to control USB devices and other removable media using Microsoft Defender for Endpoint</span></span>](control-usb-devices-using-intune.md)     |   <span data-ttu-id="e59f1-157">Windows</span><span class="sxs-lookup"><span data-stu-id="e59f1-157">Windows</span></span>      |  <span data-ttu-id="e59f1-158">Weitere Informationen zu Geräte-ID-Formaten finden Sie unter [Geräteeinrichtungsklasse](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors).</span><span class="sxs-lookup"><span data-stu-id="e59f1-158">For information about Device ID formats, see [device setup class](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors).</span></span> <span data-ttu-id="e59f1-159">**Hinweis:** Die Geräteinstallation kann auf alle Geräte angewendet werden, nicht nur auf Wechselmedien.</span><span class="sxs-lookup"><span data-stu-id="e59f1-159">**Note**: Device Installation can be applied to any devices, not only Removable storage.</span></span>       |
|<span data-ttu-id="e59f1-160">Primäre ID</span><span class="sxs-lookup"><span data-stu-id="e59f1-160">Primary ID</span></span>   |     <span data-ttu-id="e59f1-161">Zugriffssteuerung für Wechselmedien</span><span class="sxs-lookup"><span data-stu-id="e59f1-161">Removable storage Access Control</span></span>    |   <span data-ttu-id="e59f1-162">Windows</span><span class="sxs-lookup"><span data-stu-id="e59f1-162">Windows</span></span>      |      <span data-ttu-id="e59f1-163">Die primäre ID umfasst Wechseldatenträger und CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="e59f1-163">The Primary ID includes removable storage and CD/DVD.</span></span>   |
|<span data-ttu-id="e59f1-164">Geräte-ID</span><span class="sxs-lookup"><span data-stu-id="e59f1-164">Device ID</span></span>     |  <span data-ttu-id="e59f1-165">[Steuern von #A0 und anderen Wechselmedien mithilfe von Microsoft Defender for Endpoint](control-usb-devices-using-intune.md); Zugriffssteuerung für Wechselmedien</span><span class="sxs-lookup"><span data-stu-id="e59f1-165">[How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md); Removable storage Access Control</span></span>       |      <span data-ttu-id="e59f1-166">Windows</span><span class="sxs-lookup"><span data-stu-id="e59f1-166">Windows</span></span>   |    <span data-ttu-id="e59f1-167">Weitere Informationen zu Geräte-ID-Formaten finden Sie unter [Standard USB Identifiers,](/windows-hardware/drivers/install/standard-usb-identifiers)z. B. USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07</span><span class="sxs-lookup"><span data-stu-id="e59f1-167">For information about Device ID formats, see [Standard USB Identifiers](/windows-hardware/drivers/install/standard-usb-identifiers), for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07</span></span>      |
|<span data-ttu-id="e59f1-168">Hardware-ID</span><span class="sxs-lookup"><span data-stu-id="e59f1-168">Hardware ID</span></span>     |     <span data-ttu-id="e59f1-169">[Steuern von #A0 und anderen Wechselmedien mithilfe von Microsoft Defender for Endpoint](control-usb-devices-using-intune.md); Zugriffssteuerung für Wechselmedien</span><span class="sxs-lookup"><span data-stu-id="e59f1-169">[How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md); Removable storage Access Control</span></span>    |     <span data-ttu-id="e59f1-170">Windows</span><span class="sxs-lookup"><span data-stu-id="e59f1-170">Windows</span></span>    |    <span data-ttu-id="e59f1-171">Eine Zeichenfolge hat das Gerät im System identifiziert, z. B. USBSTOR\DiskGeneric_Flash_Disk______8.07; **Hinweis:** Hardware-ID ist nicht eindeutig; unterschiedliche Geräte können denselben Wert haben.</span><span class="sxs-lookup"><span data-stu-id="e59f1-171">A string identified the device in the system, for example, USBSTOR\DiskGeneric_Flash_Disk______8.07; **Note**: Hardware ID is not unique; different devices may share same value.</span></span>|
|<span data-ttu-id="e59f1-172">Instanz-ID</span><span class="sxs-lookup"><span data-stu-id="e59f1-172">Instance ID</span></span>    | <span data-ttu-id="e59f1-173">Geräteinstallation; Zugriffssteuerung für Wechselmedien</span><span class="sxs-lookup"><span data-stu-id="e59f1-173">Device Installation; Removable storage Access Control</span></span>     |     <span data-ttu-id="e59f1-174">Windows</span><span class="sxs-lookup"><span data-stu-id="e59f1-174">Windows</span></span>    |   <span data-ttu-id="e59f1-175">Eine Zeichenfolge identifiziert das Gerät im System eindeutig, z. B. USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0</span><span class="sxs-lookup"><span data-stu-id="e59f1-175">A string uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0</span></span>      |
|<span data-ttu-id="e59f1-176">Anzeigename</span><span class="sxs-lookup"><span data-stu-id="e59f1-176">Friendly Name</span></span>     |     <span data-ttu-id="e59f1-177">Zugriffssteuerung für Wechselmedien</span><span class="sxs-lookup"><span data-stu-id="e59f1-177">Removable storage Access Control</span></span>    |   <span data-ttu-id="e59f1-178">Windows</span><span class="sxs-lookup"><span data-stu-id="e59f1-178">Windows</span></span>      |    <span data-ttu-id="e59f1-179">Eine zeichenfolge, die an das Gerät angefügt ist, z. B. generic Flash Disk USB Device</span><span class="sxs-lookup"><span data-stu-id="e59f1-179">A string attached to the device, for example, Generic Flash Disk USB Device</span></span>     |
|<span data-ttu-id="e59f1-180">Hersteller-ID/Produkt-ID</span><span class="sxs-lookup"><span data-stu-id="e59f1-180">Vendor ID / Product ID</span></span>     |  <span data-ttu-id="e59f1-181">Zugriffssteuerung für Wechselmedien</span><span class="sxs-lookup"><span data-stu-id="e59f1-181">Removable storage Access Control</span></span>       |   <span data-ttu-id="e59f1-182">Windows Mac</span><span class="sxs-lookup"><span data-stu-id="e59f1-182">Windows Mac</span></span>      |     <span data-ttu-id="e59f1-183">Die Hersteller-ID ist der vierstellige Anbietercode, den der USB-Ausschuss dem Anbieter zurentsprecht.</span><span class="sxs-lookup"><span data-stu-id="e59f1-183">Vendor ID is the four-digit vendor code that the USB committee assigns to the vendor.</span></span> <span data-ttu-id="e59f1-184">Die Produkt-ID ist der vierstellige Produktcode, den der Hersteller dem Gerät zur zuordnen hat. Unterstützung eines Platzhalters.</span><span class="sxs-lookup"><span data-stu-id="e59f1-184">Product ID is the four-digit product code that the vendor assigns to the device; Support wildcard.</span></span>    |
|<span data-ttu-id="e59f1-185">Serial NumberId</span><span class="sxs-lookup"><span data-stu-id="e59f1-185">Serial NumberId</span></span>     |     <span data-ttu-id="e59f1-186">Zugriffssteuerung für Wechselmedien</span><span class="sxs-lookup"><span data-stu-id="e59f1-186">Removable storage Access Control</span></span>    |      <span data-ttu-id="e59f1-187">Windows Mac</span><span class="sxs-lookup"><span data-stu-id="e59f1-187">Windows Mac</span></span>   |     <span data-ttu-id="e59f1-188">Beispiel: <SerialNumberId>002324B534BCB431B000058A</SerialNumberId></span><span class="sxs-lookup"><span data-stu-id="e59f1-188">For example, <SerialNumberId>002324B534BCB431B000058A</SerialNumberId></span></span>    |

## <a name="related-topic"></a><span data-ttu-id="e59f1-189">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="e59f1-189">Related topic</span></span>

- [<span data-ttu-id="e59f1-190">Microsoft Defender for Endpoint Device Control Wechseldatenträger Storage Zugriffssteuerung</span><span class="sxs-lookup"><span data-stu-id="e59f1-190">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>](device-control-removable-storage-access-control.md)

