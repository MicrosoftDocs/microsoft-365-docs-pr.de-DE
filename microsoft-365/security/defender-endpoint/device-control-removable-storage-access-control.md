---
title: Microsoft Defender für Endpunkt-Gerätesteuerung , wechselbar Storage Zugriffssteuerung
description: Eine exemplarische Vorgehensweise zu Microsoft Defender für Endpunkt
keywords: Wechselmedien
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 801d94eb769c6b738a1d4c011b67f8a2a7cf81f1
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430804"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a><span data-ttu-id="8e0a4-104">Microsoft Defender für Endpunkt-Gerätesteuerung , wechselbar Storage Zugriffssteuerung</span><span class="sxs-lookup"><span data-stu-id="8e0a4-104">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="8e0a4-105">Microsoft Defender für Endpunkt-Gerätesteuerung – Wechselmedien Storage Zugriffssteuerung ermöglicht Ihnen die folgende Aufgabe:</span><span class="sxs-lookup"><span data-stu-id="8e0a4-105">Microsoft Defender for Endpoint Device Control Removable Storage Access Control enables you to do the following task:</span></span>

- <span data-ttu-id="8e0a4-106">Überwachen, Zulassen oder Verhindern des Lese-, Schreib- oder Ausführungszugriffs auf Wechselmedien mit oder ohne Ausschluss</span><span class="sxs-lookup"><span data-stu-id="8e0a4-106">auditing, allowing or preventing the read, write or execute access to removable storage with or without exclusion</span></span>

|<span data-ttu-id="8e0a4-107">Privileg</span><span class="sxs-lookup"><span data-stu-id="8e0a4-107">Privilege</span></span> |<span data-ttu-id="8e0a4-108">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="8e0a4-108">Permission</span></span>  |
|---------|---------|
|<span data-ttu-id="8e0a4-109">Access</span><span class="sxs-lookup"><span data-stu-id="8e0a4-109">Access</span></span>    |  <span data-ttu-id="8e0a4-110">Lese-/Schreib-/Ausführungszugriff</span><span class="sxs-lookup"><span data-stu-id="8e0a4-110">Read, Write, Execute</span></span>       |
|<span data-ttu-id="8e0a4-111">Aktionsmodus</span><span class="sxs-lookup"><span data-stu-id="8e0a4-111">Action Mode</span></span>    |    <span data-ttu-id="8e0a4-112">Überwachen, Zulassen, Verhindern</span><span class="sxs-lookup"><span data-stu-id="8e0a4-112">Audit, Allow, Prevent</span></span>     |
|<span data-ttu-id="8e0a4-113">CSP-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="8e0a4-113">CSP Support</span></span>   |   <span data-ttu-id="8e0a4-114">Ja</span><span class="sxs-lookup"><span data-stu-id="8e0a4-114">Yes</span></span>      |
|<span data-ttu-id="8e0a4-115">GPO-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="8e0a4-115">GPO Support</span></span>    |   <span data-ttu-id="8e0a4-116">Ja</span><span class="sxs-lookup"><span data-stu-id="8e0a4-116">Yes</span></span>      |
|<span data-ttu-id="8e0a4-117">Benutzerbasierter Support</span><span class="sxs-lookup"><span data-stu-id="8e0a4-117">User-based Support</span></span>     |   <span data-ttu-id="8e0a4-118">Ja</span><span class="sxs-lookup"><span data-stu-id="8e0a4-118">Yes</span></span>      |
|<span data-ttu-id="8e0a4-119">Computerbasierter Support</span><span class="sxs-lookup"><span data-stu-id="8e0a4-119">Machine-based Support</span></span>    |    <span data-ttu-id="8e0a4-120">Ja</span><span class="sxs-lookup"><span data-stu-id="8e0a4-120">Yes</span></span>     |

## <a name="licensing"></a><span data-ttu-id="8e0a4-121">Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="8e0a4-121">Licensing</span></span>

<span data-ttu-id="8e0a4-122">Bevor Sie mit wechselbaren Storage Zugriffssteuerung beginnen, sollten Sie [Ihr Microsoft 365 Abonnement bestätigen.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)</span><span class="sxs-lookup"><span data-stu-id="8e0a4-122">Before you get started with Removable Storage Access Control, you should [confirm your Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1).</span></span> <span data-ttu-id="8e0a4-123">Um auf wechselbare Storage Zugriffssteuerung zuzugreifen und diese zu verwenden, benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8e0a4-123">To access and use Removable Storage Access Control, you must have the following:</span></span>

- <span data-ttu-id="8e0a4-124">Microsoft 365 E3 für die Bereitstellung von Funktionen/Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-124">Microsoft 365 E3 for functionality/policy deployment.</span></span>
- <span data-ttu-id="8e0a4-125">Microsoft 365 E5 für die Berichterstellung.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-125">Microsoft 365 E5 for reporting.</span></span>

## <a name="prepare-your-endpoints"></a><span data-ttu-id="8e0a4-126">Vorbereiten der Endpunkte</span><span class="sxs-lookup"><span data-stu-id="8e0a4-126">Prepare your endpoints</span></span>

<span data-ttu-id="8e0a4-127">Bereitstellen von Wechseldatenträgern Storage Zugriffssteuerung auf Windows 10 Geräten mit Antischadsoftware-Clientversion **4.18.2103.3 oder höher.**</span><span class="sxs-lookup"><span data-stu-id="8e0a4-127">Deploy Removable Storage Access Control on Windows 10 devices that have antimalware client version **4.18.2103.3 or later**.</span></span>

- <span data-ttu-id="8e0a4-128">**4.18.2104 oder höher:** Hinzufügen von SerialNumberId, VID_PID, dateipfadbasierter GPO-Unterstützung, ComputerSid</span><span class="sxs-lookup"><span data-stu-id="8e0a4-128">**4.18.2104 or later**: Add SerialNumberId, VID_PID, filepath-based GPO support, ComputerSid</span></span>

- <span data-ttu-id="8e0a4-129">**4.18.2105 oder höher:** Hinzufügen von Platzhalterunterstützung für HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, die Kombination aus einem bestimmten Benutzer auf einem bestimmten Computer, entfernender SSD (sanDisk Extreme SSD)/USB Attached SCSI (UAS)-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="8e0a4-129">**4.18.2105 or later**: Add Wildcard support for HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, the combination of specific user on specific machine, removeable SSD (a SanDisk Extreme SSD)/USB Attached SCSI (UAS) support</span></span>

- <span data-ttu-id="8e0a4-130">**4.18.2107 oder höher:** Hinzufügen Windows WpD-Unterstützung (für mobile Geräte, z. B. Tablets)</span><span class="sxs-lookup"><span data-stu-id="8e0a4-130">**4.18.2107 or later**: Add Windows Portable Device (WPD) support (for mobile devices, such as tablets)</span></span>

:::image type="content" source="images/powershell.png" alt-text="Die PowerShell-Schnittstelle":::

> [!NOTE]
> <span data-ttu-id="8e0a4-132">Keine der Windows-Sicherheit Komponenten aktiv sein muss, können Sie wechselbare Storage Zugriffssteuerung unabhängig von Windows-Sicherheit Status ausführen.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-132">None of Windows Security components need to be active, you can run Removable Storage Access Control independent of Windows Security status.</span></span>

## <a name="policy-properties"></a><span data-ttu-id="8e0a4-133">Richtlinieneigenschaften</span><span class="sxs-lookup"><span data-stu-id="8e0a4-133">Policy properties</span></span>

<span data-ttu-id="8e0a4-134">Sie können die folgenden Eigenschaften verwenden, um eine Wechselmediengruppe zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="8e0a4-134">You can use the following properties to create a removable storage group:</span></span>

<span data-ttu-id="8e0a4-135">**Eigenschaftenname: Gruppen-ID**</span><span class="sxs-lookup"><span data-stu-id="8e0a4-135">**Property name: Group Id**</span></span>

1. <span data-ttu-id="8e0a4-136">Beschreibung: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), eine eindeutige ID, stellt die Gruppe dar und wird in der Richtlinie verwendet.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-136">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the group and will be used in the policy.</span></span>

<span data-ttu-id="8e0a4-137">**Eigenschaftenname: DescriptorIdList**</span><span class="sxs-lookup"><span data-stu-id="8e0a4-137">**Property name: DescriptorIdList**</span></span>

2. <span data-ttu-id="8e0a4-138">Beschreibung: Auflisten der Geräteeigenschaften, die Sie in der Gruppe abdecken möchten.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-138">Description: List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="8e0a4-139">Weitere Informationen zu jeder Geräteeigenschaft finden Sie weiter oben im Abschnitt **"Geräteeigenschaften".**</span><span class="sxs-lookup"><span data-stu-id="8e0a4-139">For each device property, see **Device Properties** section above for more detail.</span></span>

3. <span data-ttu-id="8e0a4-140">Optionen:</span><span class="sxs-lookup"><span data-stu-id="8e0a4-140">Options:</span></span>
    - <span data-ttu-id="8e0a4-141">PrimaryId</span><span class="sxs-lookup"><span data-stu-id="8e0a4-141">PrimaryId</span></span>
        - <span data-ttu-id="8e0a4-142">RemovableMediaDevices</span><span class="sxs-lookup"><span data-stu-id="8e0a4-142">RemovableMediaDevices</span></span>
        - <span data-ttu-id="8e0a4-143">CdRomDevices</span><span class="sxs-lookup"><span data-stu-id="8e0a4-143">CdRomDevices</span></span>
        - <span data-ttu-id="8e0a4-144">WpdDevices</span><span class="sxs-lookup"><span data-stu-id="8e0a4-144">WpdDevices</span></span>
    - <span data-ttu-id="8e0a4-145">Deviceid</span><span class="sxs-lookup"><span data-stu-id="8e0a4-145">DeviceId</span></span>
    - <span data-ttu-id="8e0a4-146">HardwareId</span><span class="sxs-lookup"><span data-stu-id="8e0a4-146">HardwareId</span></span>
    - <span data-ttu-id="8e0a4-147">InstancePathId: InstancePathId ist eine Zeichenfolge, die das Gerät im System eindeutig identifiziert, z. B. USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-147">InstancePathId: InstancePathId is a string that uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span></span> <span data-ttu-id="8e0a4-148">Die Zahl am Ende (z. **B.&0)** stellt den verfügbaren Steckplatz dar und kann sich von Gerät zu Gerät ändern.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-148">The number at the end (for example **&0**) represents the available slot and may change from device to device.</span></span> <span data-ttu-id="8e0a4-149">Um optimale Ergebnisse zu erzielen, verwenden Sie am Ende einen Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-149">For best results, use a wildcard at the end.</span></span> <span data-ttu-id="8e0a4-150">Beispiel: USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span><span class="sxs-lookup"><span data-stu-id="8e0a4-150">For example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span></span>
    - <span data-ttu-id="8e0a4-151">FriendlyNameId</span><span class="sxs-lookup"><span data-stu-id="8e0a4-151">FriendlyNameId</span></span>
    - <span data-ttu-id="8e0a4-152">SerialNumberId</span><span class="sxs-lookup"><span data-stu-id="8e0a4-152">SerialNumberId</span></span>
    - <span data-ttu-id="8e0a4-153">Vid</span><span class="sxs-lookup"><span data-stu-id="8e0a4-153">VID</span></span>
    - <span data-ttu-id="8e0a4-154">Pid</span><span class="sxs-lookup"><span data-stu-id="8e0a4-154">PID</span></span>
    - <span data-ttu-id="8e0a4-155">VID_PID</span><span class="sxs-lookup"><span data-stu-id="8e0a4-155">VID_PID</span></span>
        - <span data-ttu-id="8e0a4-156">0751_55E0: Übereinstimmung mit diesem genauen VID/PID-Paar</span><span class="sxs-lookup"><span data-stu-id="8e0a4-156">0751_55E0: match this exact VID/PID pair</span></span>
        - <span data-ttu-id="8e0a4-157">_55E0: Abgleichen von Medien mit PID=55E0</span><span class="sxs-lookup"><span data-stu-id="8e0a4-157">_55E0: match any media with PID=55E0</span></span>
        - <span data-ttu-id="8e0a4-158">0751_: Alle Medien mit VID=0751 abgleichen</span><span class="sxs-lookup"><span data-stu-id="8e0a4-158">0751_: match any media with VID=0751</span></span>
        
<span data-ttu-id="8e0a4-159">**Eigenschaftenname: MatchType**</span><span class="sxs-lookup"><span data-stu-id="8e0a4-159">**Property name: MatchType**</span></span> 

1. <span data-ttu-id="8e0a4-160">Beschreibung: Wenn mehrere Geräteeigenschaften in der DescriptorIDList verwendet werden, definiert MatchType die Beziehung.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-160">Description: When there are multiple device properties being used in the DescriptorIDList, MatchType defines the relationship.</span></span>

2. <span data-ttu-id="8e0a4-161">Optionen:</span><span class="sxs-lookup"><span data-stu-id="8e0a4-161">Options:</span></span>

    - <span data-ttu-id="8e0a4-162">MatchAll: Alle Attribute unter der DescriptorIdList sind **"And"-Beziehung;** Wenn der Administrator beispielsweise DeviceID und InstancePathID platziert, überprüft das System für jeden angeschlossenen USB-Stick, ob der USB beide Werte erfüllt.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-162">MatchAll: Any attributes under the DescriptorIdList will be **And** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will check to see whether the USB meets both values.</span></span>
    - <span data-ttu-id="8e0a4-163">MatchAny: Die Attribute unter "DescriptorIdList" sind **"Or".** Wenn der Administrator beispielsweise DeviceID und InstancePathID platziert, führt das System für jeden angeschlossenen USB-Stick die Erzwingung durch, solange der USB-Stick entweder einen identischen **DeviceID-** oder **InstanceID-Wert** aufweist.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-163">MatchAny: The attributes under the DescriptorIdList will be **Or** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will do the enforcement as long as the USB has either an identical **DeviceID** or **InstanceID** value.</span></span>

<span data-ttu-id="8e0a4-164">Es folgen die Eigenschaften der Zugriffssteuerungsrichtlinie:</span><span class="sxs-lookup"><span data-stu-id="8e0a4-164">Following are the access control policy properties:</span></span>

<span data-ttu-id="8e0a4-165">**Eigenschaftenname: PolicyRuleId**</span><span class="sxs-lookup"><span data-stu-id="8e0a4-165">**Property name: PolicyRuleId**</span></span>

1. <span data-ttu-id="8e0a4-166">Beschreibung: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), eine eindeutige ID, stellt die Richtlinie dar und wird in der Berichterstellung und Problembehandlung verwendet.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-166">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the policy and will be used in the reporting and troubleshooting.</span></span>

<span data-ttu-id="8e0a4-167">**Eigenschaftenname: IncludedIdList**</span><span class="sxs-lookup"><span data-stu-id="8e0a4-167">**Property name: IncludedIdList**</span></span>

1. <span data-ttu-id="8e0a4-168">Beschreibung: Die Gruppen, auf die die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-168">Description: The group(s) that the policy will be applied to.</span></span> <span data-ttu-id="8e0a4-169">Wenn mehrere Gruppen hinzugefügt werden, wird die Richtlinie auf alle Medien in allen diesen Gruppen angewendet.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-169">If multiple groups are added, the policy will be applied to any media in all those groups.</span></span>

2. <span data-ttu-id="8e0a4-170">Optionen: Die Gruppen-ID/GUID muss in dieser Instanz verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-170">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="8e0a4-171">Das folgende Beispiel zeigt die Verwendung von GroupID:</span><span class="sxs-lookup"><span data-stu-id="8e0a4-171">The following example shows the usage of GroupID:</span></span>

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

<span data-ttu-id="8e0a4-172">**Eigenschaftenname: ExcludedIDList**</span><span class="sxs-lookup"><span data-stu-id="8e0a4-172">**Property name: ExcludedIDList**</span></span>

<span data-ttu-id="8e0a4-173">Beschreibung: Die Gruppen, auf die die Richtlinie nicht angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-173">Description: The group(s) that the policy will not be applied to.</span></span>

<span data-ttu-id="8e0a4-174">Optionen: Die Gruppen-ID/GUID muss in dieser Instanz verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-174">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="8e0a4-175">**Eigenschaftenname: Eintrags-ID**</span><span class="sxs-lookup"><span data-stu-id="8e0a4-175">**Property name: Entry Id**</span></span>

1. <span data-ttu-id="8e0a4-176">Beschreibung: One PolicyRule kann mehrere Einträge haben; Jeder Eintrag mit einer eindeutigen GUID teilt der Gerätesteuerung eine Einschränkung mit.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-176">Description: One PolicyRule can have multiple entries; each entry with a unique GUID tells Device Control one restriction.</span></span>

<span data-ttu-id="8e0a4-177">**Eigenschaftenname: Typ**</span><span class="sxs-lookup"><span data-stu-id="8e0a4-177">**Property name: Type**</span></span>

1. <span data-ttu-id="8e0a4-178">Beschreibung: Definiert die Aktion für die Wechselmediengruppen in IncludedIDList.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-178">Description: Defines the action for the removable storage groups in IncludedIDList.</span></span>
    - <span data-ttu-id="8e0a4-179">Erzwingung: Zulassen oder Verweigern</span><span class="sxs-lookup"><span data-stu-id="8e0a4-179">Enforcement: Allow or Deny</span></span>
    - <span data-ttu-id="8e0a4-180">Audit: AuditAllowed oder AuditDenied</span><span class="sxs-lookup"><span data-stu-id="8e0a4-180">Audit: AuditAllowed or AuditDenied</span></span> 

2. <span data-ttu-id="8e0a4-181">Optionen:</span><span class="sxs-lookup"><span data-stu-id="8e0a4-181">Options:</span></span>

    - <span data-ttu-id="8e0a4-182">Zulassen</span><span class="sxs-lookup"><span data-stu-id="8e0a4-182">Allow</span></span>
    - <span data-ttu-id="8e0a4-183">Verweigern</span><span class="sxs-lookup"><span data-stu-id="8e0a4-183">Deny</span></span>
    - <span data-ttu-id="8e0a4-184">AuditAllowed: Definiert Benachrichtigung und Ereignis, wenn der Zugriff zulässig ist</span><span class="sxs-lookup"><span data-stu-id="8e0a4-184">AuditAllowed: Defines notification and event when access is allowed</span></span>
    - <span data-ttu-id="8e0a4-185">AuditDenied: Definiert Benachrichtigung und Ereignis, wenn der Zugriff verweigert wird; muss mit **der Verweigerungseingabe zusammenarbeiten.**</span><span class="sxs-lookup"><span data-stu-id="8e0a4-185">AuditDenied: Defines notification and event when access is denied; has to work together with **Deny** entry.</span></span>

<span data-ttu-id="8e0a4-186">Wenn es Konflikttypen für dieselben Medien gibt, wendet das System den ersten in der Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-186">When there are conflict types for the same media, the system will apply the first one in the policy.</span></span> <span data-ttu-id="8e0a4-187">Ein Beispiel für einen Konflikttyp ist **Allow** and **Deny**.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-187">An example of a conflict type is **Allow** and **Deny**.</span></span>

<span data-ttu-id="8e0a4-188">**Eigenschaftenname: Sid**</span><span class="sxs-lookup"><span data-stu-id="8e0a4-188">**Property name: Sid**</span></span>

<span data-ttu-id="8e0a4-189">Beschreibung: Die Sid des lokalen Computers oder die Sid des AD-Objekts definiert, ob diese Richtlinie auf einen bestimmten Benutzer oder eine bestimmte Benutzergruppe angewendet werden soll. Ein Eintrag kann maximal eine Sid haben, und ein Eintrag ohne Sid bedeutet, dass die Richtlinie auf dem Computer angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-189">Description: Local computer Sid or the Sid of the AD object, defines whether to apply this policy over a specific user or user group; one entry can have a maximum of one Sid and an entry without any Sid means applying the policy over the machine.</span></span>

<span data-ttu-id="8e0a4-190">**Eigenschaftenname: ComputerSid**</span><span class="sxs-lookup"><span data-stu-id="8e0a4-190">**Property name: ComputerSid**</span></span>

<span data-ttu-id="8e0a4-191">Beschreibung: Die Sid des lokalen Computers oder die Sid des AD-Objekts definiert, ob diese Richtlinie auf einen bestimmten Computer oder eine bestimmte Computergruppe angewendet werden soll. Ein Eintrag kann maximal eine Computer-ID haben, und ein Eintrag ohne ComputerSid bedeutet, dass die Richtlinie auf dem Computer angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-191">Description: Local computer Sid or the Sid of the AD object, defines whether to apply this policy over a specific machine or machine group; one entry can have a maximum of one ComputerSid and an entry without any ComputerSid means applying the policy over the machine.</span></span> <span data-ttu-id="8e0a4-192">Wenn Sie einen Eintrag auf einen bestimmten Benutzer und einen bestimmten Computer anwenden möchten, fügen Sie sid und computerSid demselben Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-192">If you want to apply an Entry to a specific user and specific machine, add both Sid and ComputerSid into the same Entry.</span></span>

<span data-ttu-id="8e0a4-193">**Eigenschaftenname: Optionen**</span><span class="sxs-lookup"><span data-stu-id="8e0a4-193">**Property name: Options**</span></span>

<span data-ttu-id="8e0a4-194">Beschreibung: Definiert, ob eine Benachrichtigung angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-194">Description: Defines whether to display notification or not.</span></span>

   :::image type="content" source="images/device-status.png" alt-text="Der Bildschirm, auf dem der Status des Geräts angezeigt werden kann":::

<span data-ttu-id="8e0a4-196">Optionen: 0-4.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-196">Options: 0-4.</span></span> <span data-ttu-id="8e0a4-197">Wenn "Zulassen" oder "Verweigern" ausgewählt ist:</span><span class="sxs-lookup"><span data-stu-id="8e0a4-197">When Type Allow or Deny is selected:</span></span>

   - <span data-ttu-id="8e0a4-198">0: nothing</span><span class="sxs-lookup"><span data-stu-id="8e0a4-198">0: nothing</span></span>
   - <span data-ttu-id="8e0a4-199">4: Deaktivieren Sie **"AuditAllowed"** und **"AuditDenied"** für diesen Eintrag.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-199">4: disable **AuditAllowed** and **AuditDenied** for this Entry.</span></span> <span data-ttu-id="8e0a4-200">Selbst wenn **"Blockieren"** erfolgt und die **"AuditDenied"-Einstellung** konfiguriert ist, zeigt das System keine Benachrichtigung an.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-200">Even if **Block** happens and the **AuditDenied** is setting configured, the system will not show notification.</span></span>

   <span data-ttu-id="8e0a4-201">Wenn **"AuditAllowed"** oder **"AuditDenied"** ausgewählt ist:</span><span class="sxs-lookup"><span data-stu-id="8e0a4-201">When Type **AuditAllowed** or **AuditDenied** is selected:</span></span>

   - <span data-ttu-id="8e0a4-202">0: nothing</span><span class="sxs-lookup"><span data-stu-id="8e0a4-202">0: nothing</span></span>
   - <span data-ttu-id="8e0a4-203">1: Benachrichtigung anzeigen</span><span class="sxs-lookup"><span data-stu-id="8e0a4-203">1: show notification</span></span>
   - <span data-ttu-id="8e0a4-204">2: Send-Ereignis</span><span class="sxs-lookup"><span data-stu-id="8e0a4-204">2: send event</span></span>
   - <span data-ttu-id="8e0a4-205">3: Benachrichtigungs- und Sendeereignis anzeigen</span><span class="sxs-lookup"><span data-stu-id="8e0a4-205">3: show notification and send event</span></span>

<span data-ttu-id="8e0a4-206">**Eigenschaftenname: AccessMask**</span><span class="sxs-lookup"><span data-stu-id="8e0a4-206">**Property name: AccessMask**</span></span>

<span data-ttu-id="8e0a4-207">Beschreibung: Definiert den Zugriff.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-207">Description: Defines the access.</span></span>

<span data-ttu-id="8e0a4-208">Optionen 1 bis 7:</span><span class="sxs-lookup"><span data-stu-id="8e0a4-208">Options 1-7:</span></span>
  - <span data-ttu-id="8e0a4-209">1: Lesen</span><span class="sxs-lookup"><span data-stu-id="8e0a4-209">1: Read</span></span>
  - <span data-ttu-id="8e0a4-210">2: Schreiben</span><span class="sxs-lookup"><span data-stu-id="8e0a4-210">2: Write</span></span>
  - <span data-ttu-id="8e0a4-211">3: Lesen und Schreiben</span><span class="sxs-lookup"><span data-stu-id="8e0a4-211">3: Read and Write</span></span>
  - <span data-ttu-id="8e0a4-212">4: Ausführen</span><span class="sxs-lookup"><span data-stu-id="8e0a4-212">4: Execute</span></span>
  - <span data-ttu-id="8e0a4-213">5: Lesen und Ausführen</span><span class="sxs-lookup"><span data-stu-id="8e0a4-213">5: Read and Execute</span></span>
  - <span data-ttu-id="8e0a4-214">6: Schreiben und Ausführen</span><span class="sxs-lookup"><span data-stu-id="8e0a4-214">6: Write and Execute</span></span>
  - <span data-ttu-id="8e0a4-215">7: Lesen und Schreiben und Ausführen</span><span class="sxs-lookup"><span data-stu-id="8e0a4-215">7: Read and Write and Execute</span></span>

## <a name="common-removable-storage-access-control-scenarios"></a><span data-ttu-id="8e0a4-216">Allgemeine Szenarien für die Zugriffssteuerung für wechselbare Storage</span><span class="sxs-lookup"><span data-stu-id="8e0a4-216">Common Removable Storage Access Control scenarios</span></span>

<span data-ttu-id="8e0a4-217">Um Sie mit Microsoft Defender für Endpunkt-Wechselmedien Storage Zugriffssteuerung vertraut zu machen, haben wir einige häufige Szenarien für Sie zusammengestellt.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-217">To help familiarize you with Microsoft Defender for Endpoint Removable Storage Access Control, we have put together some common scenarios for you to follow.</span></span>

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a><span data-ttu-id="8e0a4-218">Szenario 1: Verhindern des Schreib- und Ausführungszugriffs auf alle genehmigten USBs, aber zulassen</span><span class="sxs-lookup"><span data-stu-id="8e0a4-218">Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs</span></span>

1. <span data-ttu-id="8e0a4-219">Erstellen von Gruppen</span><span class="sxs-lookup"><span data-stu-id="8e0a4-219">Create groups</span></span>

    1. <span data-ttu-id="8e0a4-220">Gruppe 1: Wechselmedien und CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-220">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="8e0a4-221">Ein Beispiel für einen Wechselmedien und eine CD/DVD ist: Gruppe **9b28fae8-72f7-4267-a1a5-685f747a7146** in der Beispieldatei ["Any Removable Storage" und "CD-DVD Group.xml".](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="8e0a4-221">An example of a removable storage and CD/DVD is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="8e0a4-222">Gruppe 2: Genehmigte USBs basierend auf Geräteeigenschaften.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-222">Group 2: Approved USBs based on device properties.</span></span> <span data-ttu-id="8e0a4-223">Ein Beispiel für diesen Anwendungsfall ist: Instanz-ID – Gruppe **65fa649a-a111-4912-9294-fb6337a25038** in der Beispieldatei [für genehmigte USBs Group.xml.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="8e0a4-223">An example for this use case is: Instance ID – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Approved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8e0a4-224">Sie müssen `&` `&amp;` im Wert ersetzen.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-224">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="8e0a4-225">Richtlinie erstellen</span><span class="sxs-lookup"><span data-stu-id="8e0a4-225">Create policy</span></span>

    1. <span data-ttu-id="8e0a4-226">Richtlinie 1: Schreib- und Ausführungszugriff blockieren, aber genehmigte USBs zulassen.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-226">Policy 1: Block Write and Execute Access but allow approved USBs.</span></span> <span data-ttu-id="8e0a4-227">Ein Beispiel für diesen Anwendungsfall ist: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-227">An example for this use case is: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="8e0a4-228">Richtlinie 2: Überwachen des Schreib- und Ausführungszugriffs auf zulässige USBs.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-228">Policy 2: Audit Write and Execute access to allowed USBs.</span></span> <span data-ttu-id="8e0a4-229">Ein Beispiel für diesen Anwendungsfall ist: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** im [Beispielszenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-229">An example for this use case is: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** in the sample [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a><span data-ttu-id="8e0a4-230">Szenario 2: Überwachen des Schreib- und Ausführungszugriffs auf alle nicht genehmigten USBs außer Blockieren bestimmter nicht genehmigter USBs</span><span class="sxs-lookup"><span data-stu-id="8e0a4-230">Scenario 2: Audit Write and Execute access to all but block specific unapproved USBs</span></span>

1. <span data-ttu-id="8e0a4-231">Erstellen von Gruppen</span><span class="sxs-lookup"><span data-stu-id="8e0a4-231">Create groups</span></span>

    1. <span data-ttu-id="8e0a4-232">Gruppe 1: Wechselmedien und CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-232">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="8e0a4-233">Ein Beispiel für diesen Anwendungsfall ist: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-233">An example for this use case is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="8e0a4-234">Gruppe 2: Nicht genehmigte USBs basierend auf Geräteeigenschaften, z. B. Anbieter-ID/Produkt-ID, Anzeigename – Gruppe **65fa649a-a111-4912-9294-fb6337a25038** in der Beispieldatei ["Nicht genehmigte USBs Group.xml".](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="8e0a4-234">Group 2: Unapproved USBs based on device properties, for example, Vendor ID / Product ID, Friendly Name – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Unapproved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="8e0a4-235">Sie müssen `&` `&amp;` im Wert ersetzen.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-235">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="8e0a4-236">Richtlinie erstellen</span><span class="sxs-lookup"><span data-stu-id="8e0a4-236">Create policy</span></span>

    1. <span data-ttu-id="8e0a4-237">Richtlinie 1: Schreib- und Ausführungszugriff auf alle nicht genehmigten USBs blockieren.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-237">Policy 1: Block Write and Execute access to all but block specific unapproved USBs.</span></span> <span data-ttu-id="8e0a4-238">Ein Beispiel für diesen Anwendungsfall ist: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** im [Beispielszenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-238">An example of this use case is: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** in the sample [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="8e0a4-239">Richtlinie 2: Überwachen des Schreib- und Ausführungszugriffs auf andere Personen.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-239">Policy 2: Audit Write and Execute access to others.</span></span> <span data-ttu-id="8e0a4-240">Ein Beispiel für diesen Anwendungsfall ist: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** im [Beispielszenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-240">An example of this use case is: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** in the sample [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

## <a name="deploying-and-managing-policy-via-group-policy"></a><span data-ttu-id="8e0a4-241">Bereitstellen und Verwalten von Richtlinien über Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="8e0a4-241">Deploying and managing policy via Group Policy</span></span>

<span data-ttu-id="8e0a4-242">Das Feature "Wechselbare Storage Zugriffssteuerung" ermöglicht es Ihnen, Richtlinien über Gruppenrichtlinien entweder auf Benutzer oder Geräte oder auf beides anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-242">The Removable Storage Access Control feature enables you to apply policy via Group Policy to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="8e0a4-243">Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="8e0a4-243">Licensing</span></span>

<span data-ttu-id="8e0a4-244">Bevor Sie mit wechselbaren Storage Zugriffssteuerung beginnen, müssen Sie Ihr [Microsoft 365 Abonnement](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)bestätigen.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-244">Before you get started with Removable Storage Access Control, you must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="8e0a4-245">Um auf wechselbare Storage Zugriffssteuerung zuzugreifen und sie zu verwenden, benötigen Sie Microsoft 365 E3 oder Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-245">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="deploying-policy-via-group-policy"></a><span data-ttu-id="8e0a4-246">Bereitstellen von Richtlinien über Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="8e0a4-246">Deploying policy via Group Policy</span></span>

1. <span data-ttu-id="8e0a4-247">Kombinieren Sie alle Darin enthaltenen Gruppen `<Groups>` `</Groups>` in einer XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-247">Combine all groups within `<Groups>` `</Groups>` into one xml file.</span></span> 

    <span data-ttu-id="8e0a4-248">Die folgende Abbildung veranschaulicht das Beispiel von [Szenario 1: Verhindern des Schreib- und Ausführungszugriffs auf alle genehmigten USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)außer zulassen.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-248">The following image illustrates the example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="Der Bildschirm mit den Konfigurationseinstellungen, die bestimmte genehmigte USBs auf Geräten zulassen":::
    
2. <span data-ttu-id="8e0a4-250">Kombinieren Sie alle darin enthaltenen Regeln `<PolicyRules>` `</PolicyRules>` in einer XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-250">Combine all rules within `<PolicyRules>` `</PolicyRules>` into one xml file.</span></span> 

    <span data-ttu-id="8e0a4-251">Wenn Sie einen bestimmten Benutzer einschränken möchten, verwenden Sie die SID-Eigenschaft im Eintrag.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-251">If you want to restrict a specific user, then use SID property into the Entry.</span></span> <span data-ttu-id="8e0a4-252">Wenn der Richtlinieneintrag keine SID enthält, wird der Eintrag auf alle Anmeldeinstanzen für den Computer angewendet.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-252">If there is no SID in the policy Entry, the Entry will be applied to everyone login instance for the machine.</span></span>
    
    <span data-ttu-id="8e0a4-253">Die folgende Abbildung veranschaulicht die Verwendung der SID-Eigenschaft und ein Beispiel für [Szenario 1: Verhindern des Schreib- und Ausführungszugriffs auf alle genehmigten USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)außer zulassen.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-253">The following image illustrates the usage of SID property, and an example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="Der Bildschirm mit einem Code, der die Verwendung des SID-Eigenschaftsattributs angibt":::

3. <span data-ttu-id="8e0a4-255">Speichern Sie sowohl Regel- als auch Gruppen-XML-Dateien im Netzwerkfreigabeordner, und fügen Sie den Pfad des Netzwerkfreigabeordners in die Gruppenrichtlinieneinstellung: **Computerkonfiguration -> Administrative Vorlagen -> Windows Komponenten -> Microsoft Defender Antivirus -> Gerätesteuerung: "Gerätesteuerungsrichtliniengruppen definieren" und "Gerätesteuerungsrichtlinienregeln definieren"** ein.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-255">Save both rule and group XML files on network share folder and put network share folder path into the Group Policy setting: **Computer Configuration -> Administrative Templates -> Windows Components -> Microsoft Defender Antivirus -> Device Control: ‘Define device control policy groups’ and ‘Define device control policy rules’**.</span></span>

    - <span data-ttu-id="8e0a4-256">Der Zielcomputer muss auf die Netzwerkfreigabe zugreifen können, um über die Richtlinie verfügen zu können.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-256">The target machine must be able to access the network share to have the policy.</span></span> <span data-ttu-id="8e0a4-257">Nachdem die Richtlinie gelesen wurde, ist die Netzwerkfreigabeverbindung jedoch auch nach dem Computerneustart nicht mehr erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-257">However, once the policy is read, the network share connection is no longer required, even after machine reboot.</span></span>

    :::image type="content" source="images/device-control.png" alt-text="Der Bildschirm des Gerätesteuerelements":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a><span data-ttu-id="8e0a4-259">Bereitstellen und Verwalten von Richtlinien über Intune OMA-URI</span><span class="sxs-lookup"><span data-stu-id="8e0a4-259">Deploying and managing policy via Intune OMA-URI</span></span>

<span data-ttu-id="8e0a4-260">Mit dem Feature für die Zugriffssteuerung für Wechselmedien Storage können Sie Richtlinien über OMA-URI entweder auf Benutzer oder Geräte oder auf beides anwenden.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-260">The Removable Storage Access Control feature enables you to apply policy via OMA-URI to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="8e0a4-261">Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="8e0a4-261">Licensing</span></span>

<span data-ttu-id="8e0a4-262">Bevor Sie mit wechselbaren Storage Zugriffssteuerung beginnen, müssen Sie Ihr [Microsoft 365 Abonnement](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)bestätigen.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-262">Before you get started with Removable Storage Access Control, you  must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="8e0a4-263">Um auf wechselbare Storage Zugriffssteuerung zuzugreifen und sie zu verwenden, benötigen Sie Microsoft 365 E3 oder Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-263">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="permission"></a><span data-ttu-id="8e0a4-264">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="8e0a4-264">Permission</span></span>

<span data-ttu-id="8e0a4-265">Für die Richtlinienbereitstellung in Intune muss das Konto über Berechtigungen zum Erstellen, Bearbeiten, Aktualisieren oder Löschen von Gerätekonfigurationsprofilen verfügen.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-265">For policy deployment in Intune, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="8e0a4-266">Sie können benutzerdefinierte Rollen erstellen oder eine der integrierten Rollen mit diesen Berechtigungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-266">You can create custom roles or use any of the built-in roles with these permissions.</span></span>

- <span data-ttu-id="8e0a4-267">Rolle "Richtlinien- und Profil-Manager"</span><span class="sxs-lookup"><span data-stu-id="8e0a4-267">Policy and profile Manager role</span></span>
- <span data-ttu-id="8e0a4-268">Benutzerdefinierte Rolle mit aktivierten Berechtigungen zum Erstellen/Bearbeiten/Aktualisieren/Lesen/Löschen/Anzeigen von Berichten für Gerätekonfigurationsprofile</span><span class="sxs-lookup"><span data-stu-id="8e0a4-268">Custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="8e0a4-269">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="8e0a4-269">Global administrator</span></span>

### <a name="deploying-policy-via-oma-uri"></a><span data-ttu-id="8e0a4-270">Bereitstellen von Richtlinien über OMA-URI</span><span class="sxs-lookup"><span data-stu-id="8e0a4-270">Deploying policy via OMA-URI</span></span>

<span data-ttu-id="8e0a4-271">**Microsoft Endpoint Manager Admin Center ( https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span><span class="sxs-lookup"><span data-stu-id="8e0a4-271">**Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span></span>

1. <span data-ttu-id="8e0a4-272">Erstellen Sie für jede Gruppe eine OMA-URI-Regel:</span><span class="sxs-lookup"><span data-stu-id="8e0a4-272">For each Group, create an OMA-URI rule:</span></span>
    - <span data-ttu-id="8e0a4-273">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="8e0a4-273">OMA-URI:</span></span>

      <span data-ttu-id="8e0a4-274">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="8e0a4-274">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span></span>

      <span data-ttu-id="8e0a4-275">For example, for **any removable storage and CD/DVD** group in the sample, the link must be:</span><span class="sxs-lookup"><span data-stu-id="8e0a4-275">For example, for **any removable storage and CD/DVD** group in the sample, the link must be:</span></span>

      <span data-ttu-id="8e0a4-276">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="8e0a4-276">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span></span>

    - <span data-ttu-id="8e0a4-277">Datentyp: Zeichenfolge (XML-Datei)</span><span class="sxs-lookup"><span data-stu-id="8e0a4-277">Data Type: String (XML file)</span></span>

2. <span data-ttu-id="8e0a4-278">Erstellen Sie für jede Richtlinie auch einen OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="8e0a4-278">For each policy, also create an OMA-URI:</span></span>

    - <span data-ttu-id="8e0a4-279">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="8e0a4-279">OMA-URI:</span></span>

      <span data-ttu-id="8e0a4-280">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span><span class="sxs-lookup"><span data-stu-id="8e0a4-280">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span></span>

      <span data-ttu-id="8e0a4-281">For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be:</span><span class="sxs-lookup"><span data-stu-id="8e0a4-281">For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be:</span></span> 

      <span data-ttu-id="8e0a4-282">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-282">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span></span>

    - <span data-ttu-id="8e0a4-283">Datentyp: Zeichenfolge (XML-Datei)</span><span class="sxs-lookup"><span data-stu-id="8e0a4-283">Data Type: String (XML file)</span></span>


## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a><span data-ttu-id="8e0a4-284">Bereitstellen und Verwalten von Richtlinien mithilfe der Intune-Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="8e0a4-284">Deploying and managing policy by using Intune user interface</span></span>

<span data-ttu-id="8e0a4-285">Diese Funktion (in Microsoft Endpoint Manager Admin Center ( https://endpoint.microsoft.com/) > Geräte > Konfigurationsprofile > Profil > Plattform erstellen: Windows 10 und höher & Profil: Gerätesteuerung) ist noch nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-285">This capability (in Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) > Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control) is not yet available.</span></span> 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="8e0a4-286">Anzeigen von Wechseldaten von Gerätesteuerungen Storage Zugriffssteuerungsdaten in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="8e0a4-286">View Device Control Removable Storage Access Control data in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="8e0a4-287">Das Microsoft 365-Sicherheitsportal zeigt Wechselmedien an, die von der Wechselmediensteuerung Storage Zugriffssteuerung blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-287">The Microsoft 365 security portal shows removable storage blocked by the Device Control Removable Storage Access Control.</span></span> <span data-ttu-id="8e0a4-288">Um auf die Microsoft 365 Sicherheit zugreifen zu können, benötigen Sie das folgende Abonnement:</span><span class="sxs-lookup"><span data-stu-id="8e0a4-288">To access the Microsoft 365 security, you must have the following subscription:</span></span>

- <span data-ttu-id="8e0a4-289">Microsoft 365 für E5-Berichte</span><span class="sxs-lookup"><span data-stu-id="8e0a4-289">Microsoft 365 for E5 reporting</span></span>

```kusto
//events triggered by RemovableStoragePolicyTriggered
DeviceEvents
| where ActionType == &quot;RemovableStoragePolicyTriggered&quot; 
| extend parsed=parse_json(AdditionalFields) 
| extend RemovableStorageAccess = tostring(parsed.RemovableStorageAccess)  
| extend RemovableStoragePolicyVerdict = tostring(parsed.RemovableStoragePolicyVerdict)  
| extend MediaBusType = tostring(parsed.BusType)  
| extend MediaClassGuid = tostring(parsed.ClassGuid)
| extend MediaClassName = tostring(parsed.ClassName)
| extend MediaDeviceId = tostring(parsed.DeviceId) 
| extend MediaInstanceId = tostring(parsed.DeviceInstanceId) 
| extend MediaName = tostring(parsed.MediaName) 
| extend RemovableStoragePolicy = tostring(parsed.RemovableStoragePolicy)  
| extend MediaProductId = tostring(parsed.ProductId)  
| extend MediaVendorId = tostring(parsed.VendorId)  
| extend MediaSerialNumber = tostring(parsed.SerialNumber)  
| extend MediaVolume = tostring(parsed.Volume)  
| project Timestamp, DeviceId, DeviceName, ActionType, RemovableStorageAccess, RemovableStoragePolicyVerdict, MediaBusType, MediaClassGuid, MediaClassName, MediaDeviceId, MediaInstanceId, MediaName, RemovableStoragePolicy, MediaProductId, MediaVendorId, MediaSerialNumber, MediaVolume 
| order by Timestamp desc
```

:::image type="content" source="images/block-removable-storage.png" alt-text="Der Bildschirm, der die Blockierung des Wechselspeichers darstellt":::

## <a name="frequently-asked-questions"></a><span data-ttu-id="8e0a4-291">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="8e0a4-291">Frequently asked questions</span></span>

<span data-ttu-id="8e0a4-292">**Was ist die Beschränkung für Wechselmedien für die maximale Anzahl von USBs?**</span><span class="sxs-lookup"><span data-stu-id="8e0a4-292">**What is the removable storage media limitation for the maximum number of USBs?**</span></span>

<span data-ttu-id="8e0a4-293">Wir haben eine USB-Gruppe mit 100.000 Medien – bis zu 7 MB Größe – überprüft.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-293">We have validated one USB group with 100,000 media - up to 7 MB in size.</span></span> <span data-ttu-id="8e0a4-294">Die Richtlinie funktioniert sowohl in Intune als auch im Gruppenrichtlinienobjekt ohne Leistungsprobleme.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-294">The policy works in both Intune and GPO without performance issues.</span></span>

<span data-ttu-id="8e0a4-295">**Warum funktioniert die Richtlinie nicht?**</span><span class="sxs-lookup"><span data-stu-id="8e0a4-295">**Why does the policy not work?**</span></span>

<span data-ttu-id="8e0a4-296">Der häufigste Grund ist, dass keine erforderliche [Antischadsoftware-Clientversion](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints)vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-296">The most common reason is there is no required [antimalware client version](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints).</span></span>

<span data-ttu-id="8e0a4-297">Ein weiterer Grund kann sein, dass die XML-Datei nicht richtig formatiert ist, z. B. nicht die richtige Markdownformatierung für das Zeichen "&" in der XML-Datei verwendet wird, oder dass der Texteditor am Anfang der Dateien eine Bytereihenfolgemarke (Byte Order Mark, BOM) 0xEF 0xBB 0xBF hinzugibt, was dazu führt, dass die XML-Analyse nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-297">Another reason could be that the XML file is not correctly formatted, for example, not using the correct markdown formatting for the "&" character in the XML file, or the text editor might add a byte order mark (BOM) 0xEF 0xBB 0xBF at the beginning of the files which causes the XML parsing not to work.</span></span> <span data-ttu-id="8e0a4-298">Eine einfache Lösung besteht darin, die [Beispieldatei](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) (wählen Sie **"Raw"** und dann **"Speichern unter")** herunterzuladen und dann zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-298">One simple solution is to download the [sample file](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) (select **Raw** and then **Save as**) and then update.</span></span>

<span data-ttu-id="8e0a4-299">Wenn ein Wert vorhanden ist und die Richtlinie über die Gruppenrichtlinie verwaltet wird, überprüfen Sie, ob das Clientgerät auf den RICHTLINIEN-XML-Pfad zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="8e0a4-299">If there is a value and the policy is managed via Group Policy, check whether the client device can access the policy XML path.</span></span>

<span data-ttu-id="8e0a4-300">**Wie kann ich wissen, welcher Computer die veraltete Clientversion für Antischadsoftware in der Organisation verwendet?**</span><span class="sxs-lookup"><span data-stu-id="8e0a4-300">**How can I know which machine is using out of date antimalware client version in the organization?**</span></span>

<span data-ttu-id="8e0a4-301">Sie können die folgende Abfrage verwenden, um die Clientversion für Antischadsoftware im Microsoft 365 Sicherheitsportal abzurufen:</span><span class="sxs-lookup"><span data-stu-id="8e0a4-301">You can use following query to get antimalware client version on the Microsoft 365 security portal:</span></span>
```kusto
//check the antimalware client version
DeviceFileEvents
| where FileName == "MsMpEng.exe"
| where FolderPath contains @"C:\ProgramData\Microsoft\Windows Defender\Platform\"
| extend PlatformVersion=tostring(split(FolderPath, "\\", 5))
//| project DeviceName, PlatformVersion // check which machine is using legacy platformVersion
| summarize dcount(DeviceName) by PlatformVersion // check how many machines are using which platformVersion
| order by PlatformVersion desc
```
