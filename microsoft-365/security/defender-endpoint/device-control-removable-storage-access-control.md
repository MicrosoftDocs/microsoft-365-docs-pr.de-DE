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
ms.openlocfilehash: 0b0f7c5a4a75fdc80509dbc02a43d28f7c93fd7c
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327047"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a><span data-ttu-id="9e23c-104">Microsoft Defender für Endpunkt-Gerätesteuerung , wechselbar Storage Zugriffssteuerung</span><span class="sxs-lookup"><span data-stu-id="9e23c-104">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="9e23c-105">Microsoft Defender für Endpunkt-Gerätesteuerung – Wechselmedien Storage Zugriffssteuerung ermöglicht Ihnen die folgende Aufgabe:</span><span class="sxs-lookup"><span data-stu-id="9e23c-105">Microsoft Defender for Endpoint Device Control Removable Storage Access Control enables you to do the following task:</span></span>

- <span data-ttu-id="9e23c-106">Überwachen, Zulassen oder Verhindern des Lese-, Schreib- oder Ausführungszugriffs auf Wechselmedien mit oder ohne Ausschluss</span><span class="sxs-lookup"><span data-stu-id="9e23c-106">auditing, allowing or preventing the read, write or execute access to removable storage with or without exclusion</span></span>

|<span data-ttu-id="9e23c-107">Privileg</span><span class="sxs-lookup"><span data-stu-id="9e23c-107">Privilege</span></span> |<span data-ttu-id="9e23c-108">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="9e23c-108">Permission</span></span>  |
|---------|---------|
|<span data-ttu-id="9e23c-109">Zugriff</span><span class="sxs-lookup"><span data-stu-id="9e23c-109">Access</span></span>    |  <span data-ttu-id="9e23c-110">Lese-/Schreib-/Ausführungszugriff</span><span class="sxs-lookup"><span data-stu-id="9e23c-110">Read, Write, Execute</span></span>       |
|<span data-ttu-id="9e23c-111">Aktionsmodus</span><span class="sxs-lookup"><span data-stu-id="9e23c-111">Action Mode</span></span>    |    <span data-ttu-id="9e23c-112">Überwachen, Zulassen, Verhindern</span><span class="sxs-lookup"><span data-stu-id="9e23c-112">Audit, Allow, Prevent</span></span>     |
|<span data-ttu-id="9e23c-113">CSP-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="9e23c-113">CSP Support</span></span>   |   <span data-ttu-id="9e23c-114">Ja</span><span class="sxs-lookup"><span data-stu-id="9e23c-114">Yes</span></span>      |
|<span data-ttu-id="9e23c-115">GPO-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="9e23c-115">GPO Support</span></span>    |   <span data-ttu-id="9e23c-116">Ja</span><span class="sxs-lookup"><span data-stu-id="9e23c-116">Yes</span></span>      |
|<span data-ttu-id="9e23c-117">Benutzerbasierter Support</span><span class="sxs-lookup"><span data-stu-id="9e23c-117">User-based Support</span></span>     |   <span data-ttu-id="9e23c-118">Ja</span><span class="sxs-lookup"><span data-stu-id="9e23c-118">Yes</span></span>      |
|<span data-ttu-id="9e23c-119">Computerbasierter Support</span><span class="sxs-lookup"><span data-stu-id="9e23c-119">Machine-based Support</span></span>    |    <span data-ttu-id="9e23c-120">Ja</span><span class="sxs-lookup"><span data-stu-id="9e23c-120">Yes</span></span>     |

## <a name="prepare-your-endpoints"></a><span data-ttu-id="9e23c-121">Vorbereiten der Endpunkte</span><span class="sxs-lookup"><span data-stu-id="9e23c-121">Prepare your endpoints</span></span>

<span data-ttu-id="9e23c-122">Bereitstellen von wechselbaren Storage Zugriffssteuerung auf Windows 10 Geräten mit Antischadsoftware-Clientversion **4.18.2103.3 oder höher.**</span><span class="sxs-lookup"><span data-stu-id="9e23c-122">Deploy Removable Storage Access Control on Windows 10 devices that have antimalware client version **4.18.2103.3 or later**.</span></span>

- <span data-ttu-id="9e23c-123">**4.18.2104 oder höher:** Hinzufügen von SerialNumberId, VID_PID, dateipfadbasierter GPO-Unterstützung, ComputerSid</span><span class="sxs-lookup"><span data-stu-id="9e23c-123">**4.18.2104 or later**: Add SerialNumberId, VID_PID, filepath-based GPO support, ComputerSid</span></span>

- <span data-ttu-id="9e23c-124">**4.18.2105 oder höher:** Hinzufügen von Platzhalterunterstützung für HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, die Kombination aus einem bestimmten Benutzer auf einem bestimmten Computer, entfernender SSD (sanDisk Extreme SSD)/USB Attached SCSI (UAS)-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="9e23c-124">**4.18.2105 or later**: Add Wildcard support for HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, the combination of specific user on specific machine, removeable SSD (a SanDisk Extreme SSD)/USB Attached SCSI (UAS) support</span></span>

- <span data-ttu-id="9e23c-125">**4.18.2107 oder höher:** Hinzufügen Windows Unterstützung für tragbare Geräte (WPD) (für mobile Geräte wie Tablets)</span><span class="sxs-lookup"><span data-stu-id="9e23c-125">**4.18.2107 or later**: Add Windows Portable Device (WPD) support (for mobile devices, such as tablets)</span></span>

:::image type="content" source="images/powershell.png" alt-text="Die PowerShell-Schnittstelle":::

> [!NOTE]
> <span data-ttu-id="9e23c-127">Keine der Windows-Sicherheit Komponenten aktiv sein muss, können Sie removable Storage Access Control unabhängig von Windows-Sicherheit Status ausführen.</span><span class="sxs-lookup"><span data-stu-id="9e23c-127">None of Windows Security components need to be active, you can run Removable Storage Access Control independent of Windows Security status.</span></span>

## <a name="policy-properties"></a><span data-ttu-id="9e23c-128">Richtlinieneigenschaften</span><span class="sxs-lookup"><span data-stu-id="9e23c-128">Policy properties</span></span>

<span data-ttu-id="9e23c-129">Sie können die folgenden Eigenschaften verwenden, um eine Wechselmediengruppe zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="9e23c-129">You can use the following properties to create a removable storage group:</span></span>

<span data-ttu-id="9e23c-130">**Eigenschaftenname: Gruppen-ID**</span><span class="sxs-lookup"><span data-stu-id="9e23c-130">**Property name: Group Id**</span></span>

1. <span data-ttu-id="9e23c-131">Beschreibung: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), eine eindeutige ID, stellt die Gruppe dar und wird in der Richtlinie verwendet.</span><span class="sxs-lookup"><span data-stu-id="9e23c-131">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the group and will be used in the policy.</span></span>

<span data-ttu-id="9e23c-132">**Eigenschaftenname: DescriptorIdList**</span><span class="sxs-lookup"><span data-stu-id="9e23c-132">**Property name: DescriptorIdList**</span></span>

2. <span data-ttu-id="9e23c-133">Beschreibung: Auflisten der Geräteeigenschaften, die Sie in der Gruppe abdecken möchten.</span><span class="sxs-lookup"><span data-stu-id="9e23c-133">Description: List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="9e23c-134">Weitere Informationen zu jeder Geräteeigenschaft finden Sie weiter oben im Abschnitt **"Geräteeigenschaften".**</span><span class="sxs-lookup"><span data-stu-id="9e23c-134">For each device property, see **Device Properties** section above for more detail.</span></span>

3. <span data-ttu-id="9e23c-135">Optionen:</span><span class="sxs-lookup"><span data-stu-id="9e23c-135">Options:</span></span>
    - <span data-ttu-id="9e23c-136">PrimaryId</span><span class="sxs-lookup"><span data-stu-id="9e23c-136">PrimaryId</span></span>
        - <span data-ttu-id="9e23c-137">RemovableMediaDevices</span><span class="sxs-lookup"><span data-stu-id="9e23c-137">RemovableMediaDevices</span></span>
        - <span data-ttu-id="9e23c-138">CdRomDevices</span><span class="sxs-lookup"><span data-stu-id="9e23c-138">CdRomDevices</span></span>
        - <span data-ttu-id="9e23c-139">WpdDevices</span><span class="sxs-lookup"><span data-stu-id="9e23c-139">WpdDevices</span></span>
    - <span data-ttu-id="9e23c-140">Deviceid</span><span class="sxs-lookup"><span data-stu-id="9e23c-140">DeviceId</span></span>
    - <span data-ttu-id="9e23c-141">HardwareId</span><span class="sxs-lookup"><span data-stu-id="9e23c-141">HardwareId</span></span>
    - <span data-ttu-id="9e23c-142">InstancePathId: InstancePathId ist eine Zeichenfolge, die das Gerät im System eindeutig identifiziert, z. B. USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span><span class="sxs-lookup"><span data-stu-id="9e23c-142">InstancePathId: InstancePathId is a string that uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span></span> <span data-ttu-id="9e23c-143">Die Zahl am Ende (z. **B.&0)** stellt den verfügbaren Steckplatz dar und kann sich von Gerät zu Gerät ändern.</span><span class="sxs-lookup"><span data-stu-id="9e23c-143">The number at the end (for example **&0**) represents the available slot and may change from device to device.</span></span> <span data-ttu-id="9e23c-144">Um optimale Ergebnisse zu erzielen, verwenden Sie am Ende einen Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="9e23c-144">For best results, use a wildcard at the end.</span></span> <span data-ttu-id="9e23c-145">Beispiel: USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span><span class="sxs-lookup"><span data-stu-id="9e23c-145">For example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span></span>
    - <span data-ttu-id="9e23c-146">FriendlyNameId</span><span class="sxs-lookup"><span data-stu-id="9e23c-146">FriendlyNameId</span></span>
    - <span data-ttu-id="9e23c-147">SerialNumberId</span><span class="sxs-lookup"><span data-stu-id="9e23c-147">SerialNumberId</span></span>
    - <span data-ttu-id="9e23c-148">Vid</span><span class="sxs-lookup"><span data-stu-id="9e23c-148">VID</span></span>
    - <span data-ttu-id="9e23c-149">Pid</span><span class="sxs-lookup"><span data-stu-id="9e23c-149">PID</span></span>
    - <span data-ttu-id="9e23c-150">VID_PID</span><span class="sxs-lookup"><span data-stu-id="9e23c-150">VID_PID</span></span>
        - <span data-ttu-id="9e23c-151">0751_55E0: Übereinstimmung mit diesem genauen VID/PID-Paar</span><span class="sxs-lookup"><span data-stu-id="9e23c-151">0751_55E0: match this exact VID/PID pair</span></span>
        - <span data-ttu-id="9e23c-152">_55E0: Abgleichen von Medien mit PID=55E0</span><span class="sxs-lookup"><span data-stu-id="9e23c-152">_55E0: match any media with PID=55E0</span></span>
        - <span data-ttu-id="9e23c-153">0751_: Alle Medien mit VID=0751 abgleichen</span><span class="sxs-lookup"><span data-stu-id="9e23c-153">0751_: match any media with VID=0751</span></span>
        
<span data-ttu-id="9e23c-154">**Eigenschaftenname: MatchType**</span><span class="sxs-lookup"><span data-stu-id="9e23c-154">**Property name: MatchType**</span></span> 

1. <span data-ttu-id="9e23c-155">Beschreibung: Wenn mehrere Geräteeigenschaften in der DescriptorIDList verwendet werden, definiert MatchType die Beziehung.</span><span class="sxs-lookup"><span data-stu-id="9e23c-155">Description: When there are multiple device properties being used in the DescriptorIDList, MatchType defines the relationship.</span></span>

2. <span data-ttu-id="9e23c-156">Optionen:</span><span class="sxs-lookup"><span data-stu-id="9e23c-156">Options:</span></span>

    - <span data-ttu-id="9e23c-157">MatchAll: Alle Attribute unter der DescriptorIdList sind **"And"-Beziehung;** Wenn der Administrator beispielsweise DeviceID und InstancePathID platziert, überprüft das System für jeden angeschlossenen USB-Stick, ob der USB beide Werte erfüllt.</span><span class="sxs-lookup"><span data-stu-id="9e23c-157">MatchAll: Any attributes under the DescriptorIdList will be **And** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will check to see whether the USB meets both values.</span></span>
    - <span data-ttu-id="9e23c-158">MatchAny: Die Attribute unter "DescriptorIdList" sind **"Or".** Wenn der Administrator beispielsweise DeviceID und InstancePathID platziert, führt das System für jeden angeschlossenen USB-Stick die Erzwingung aus, solange der USB-Stick entweder über einen identischen **DeviceID-** oder **InstanceID-Wert** verfügt.</span><span class="sxs-lookup"><span data-stu-id="9e23c-158">MatchAny: The attributes under the DescriptorIdList will be **Or** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will do the enforcement as long as the USB has either an identical **DeviceID** or **InstanceID** value.</span></span>

<span data-ttu-id="9e23c-159">Es folgen die Eigenschaften der Zugriffssteuerungsrichtlinie:</span><span class="sxs-lookup"><span data-stu-id="9e23c-159">Following are the access control policy properties:</span></span>

<span data-ttu-id="9e23c-160">**Eigenschaftenname: PolicyRuleId**</span><span class="sxs-lookup"><span data-stu-id="9e23c-160">**Property name: PolicyRuleId**</span></span>

1. <span data-ttu-id="9e23c-161">Beschreibung: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), eine eindeutige ID, stellt die Richtlinie dar und wird in der Berichterstellung und Problembehandlung verwendet.</span><span class="sxs-lookup"><span data-stu-id="9e23c-161">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the policy and will be used in the reporting and troubleshooting.</span></span>

<span data-ttu-id="9e23c-162">**Eigenschaftenname: IncludedIdList**</span><span class="sxs-lookup"><span data-stu-id="9e23c-162">**Property name: IncludedIdList**</span></span>

1. <span data-ttu-id="9e23c-163">Beschreibung: Die Gruppen, auf die die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="9e23c-163">Description: The group(s) that the policy will be applied to.</span></span> <span data-ttu-id="9e23c-164">Wenn mehrere Gruppen hinzugefügt werden, wird die Richtlinie auf alle Medien in allen diesen Gruppen angewendet.</span><span class="sxs-lookup"><span data-stu-id="9e23c-164">If multiple groups are added, the policy will be applied to any media in all those groups.</span></span>

2. <span data-ttu-id="9e23c-165">Optionen: Die Gruppen-ID/GUID muss in dieser Instanz verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9e23c-165">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="9e23c-166">Das folgende Beispiel zeigt die Verwendung von GroupID:</span><span class="sxs-lookup"><span data-stu-id="9e23c-166">The following example shows the usage of GroupID:</span></span>

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

<span data-ttu-id="9e23c-167">**Eigenschaftenname: ExcludedIDList**</span><span class="sxs-lookup"><span data-stu-id="9e23c-167">**Property name: ExcludedIDList**</span></span>

<span data-ttu-id="9e23c-168">Beschreibung: Die Gruppen, auf die die Richtlinie nicht angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="9e23c-168">Description: The group(s) that the policy will not be applied to.</span></span>

<span data-ttu-id="9e23c-169">Optionen: Die Gruppen-ID/GUID muss in dieser Instanz verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9e23c-169">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="9e23c-170">**Eigenschaftenname: Eintrags-ID**</span><span class="sxs-lookup"><span data-stu-id="9e23c-170">**Property name: Entry Id**</span></span>

1. <span data-ttu-id="9e23c-171">Beschreibung: One PolicyRule kann mehrere Einträge haben; Jeder Eintrag mit einer eindeutigen GUID teilt der Gerätesteuerung eine Einschränkung mit.</span><span class="sxs-lookup"><span data-stu-id="9e23c-171">Description: One PolicyRule can have multiple entries; each entry with a unique GUID tells Device Control one restriction.</span></span>

<span data-ttu-id="9e23c-172">**Eigenschaftenname: Typ**</span><span class="sxs-lookup"><span data-stu-id="9e23c-172">**Property name: Type**</span></span>

1. <span data-ttu-id="9e23c-173">Beschreibung: Definiert die Aktion für die Wechselmediengruppen in IncludedIDList.</span><span class="sxs-lookup"><span data-stu-id="9e23c-173">Description: Defines the action for the removable storage groups in IncludedIDList.</span></span>
    - <span data-ttu-id="9e23c-174">Erzwingung: Zulassen oder Verweigern</span><span class="sxs-lookup"><span data-stu-id="9e23c-174">Enforcement: Allow or Deny</span></span>
    - <span data-ttu-id="9e23c-175">Audit: AuditAllowed oder AuditDenied</span><span class="sxs-lookup"><span data-stu-id="9e23c-175">Audit: AuditAllowed or AuditDenied</span></span> 

2. <span data-ttu-id="9e23c-176">Optionen:</span><span class="sxs-lookup"><span data-stu-id="9e23c-176">Options:</span></span>

    - <span data-ttu-id="9e23c-177">Zulassen</span><span class="sxs-lookup"><span data-stu-id="9e23c-177">Allow</span></span>
    - <span data-ttu-id="9e23c-178">Verweigern</span><span class="sxs-lookup"><span data-stu-id="9e23c-178">Deny</span></span>
    - <span data-ttu-id="9e23c-179">AuditAllowed: Definiert Benachrichtigung und Ereignis, wenn der Zugriff zulässig ist</span><span class="sxs-lookup"><span data-stu-id="9e23c-179">AuditAllowed: Defines notification and event when access is allowed</span></span>
    - <span data-ttu-id="9e23c-180">AuditDenied: Definiert Benachrichtigung und Ereignis, wenn der Zugriff verweigert wird; muss mit **der Verweigerungseingabe zusammenarbeiten.**</span><span class="sxs-lookup"><span data-stu-id="9e23c-180">AuditDenied: Defines notification and event when access is denied; has to work together with **Deny** entry.</span></span>

<span data-ttu-id="9e23c-181">Wenn es Konflikttypen für dieselben Medien gibt, wendet das System den ersten in der Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="9e23c-181">When there are conflict types for the same media, the system will apply the first one in the policy.</span></span> <span data-ttu-id="9e23c-182">Ein Beispiel für einen Konflikttyp ist **Allow** and **Deny**.</span><span class="sxs-lookup"><span data-stu-id="9e23c-182">An example of a conflict type is **Allow** and **Deny**.</span></span>

<span data-ttu-id="9e23c-183">**Eigenschaftenname: Sid**</span><span class="sxs-lookup"><span data-stu-id="9e23c-183">**Property name: Sid**</span></span>

<span data-ttu-id="9e23c-184">Beschreibung: Die Sid des lokalen Computers oder die Sid des AD-Objekts definiert, ob diese Richtlinie auf einen bestimmten Benutzer oder eine bestimmte Benutzergruppe angewendet werden soll. Ein Eintrag kann maximal eine Sid haben, und ein Eintrag ohne Sid bedeutet, dass die Richtlinie auf dem Computer angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="9e23c-184">Description: Local computer Sid or the Sid of the AD object, defines whether to apply this policy over a specific user or user group; one entry can have a maximum of one Sid and an entry without any Sid means applying the policy over the machine.</span></span>

<span data-ttu-id="9e23c-185">**Eigenschaftenname: ComputerSid**</span><span class="sxs-lookup"><span data-stu-id="9e23c-185">**Property name: ComputerSid**</span></span>

<span data-ttu-id="9e23c-186">Beschreibung: Die Sid des lokalen Computers oder die Sid des AD-Objekts definiert, ob diese Richtlinie auf einen bestimmten Computer oder eine bestimmte Computergruppe angewendet werden soll. Ein Eintrag kann maximal eine Computer-ID haben, und ein Eintrag ohne ComputerSid bedeutet, dass die Richtlinie auf dem Computer angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="9e23c-186">Description: Local computer Sid or the Sid of the AD object, defines whether to apply this policy over a specific machine or machine group; one entry can have a maximum of one ComputerSid and an entry without any ComputerSid means applying the policy over the machine.</span></span> <span data-ttu-id="9e23c-187">Wenn Sie einen Eintrag auf einen bestimmten Benutzer und einen bestimmten Computer anwenden möchten, fügen Sie sid und computerSid demselben Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="9e23c-187">If you want to apply an Entry to a specific user and specific machine, add both Sid and ComputerSid into the same Entry.</span></span>

<span data-ttu-id="9e23c-188">**Eigenschaftenname: Optionen**</span><span class="sxs-lookup"><span data-stu-id="9e23c-188">**Property name: Options**</span></span>

<span data-ttu-id="9e23c-189">Beschreibung: Definiert, ob eine Benachrichtigung angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9e23c-189">Description: Defines whether to display notification or not.</span></span>

   :::image type="content" source="images/device-status.png" alt-text="Der Bildschirm, auf dem der Status des Geräts angezeigt werden kann":::

<span data-ttu-id="9e23c-191">Optionen: 0-4.</span><span class="sxs-lookup"><span data-stu-id="9e23c-191">Options: 0-4.</span></span> <span data-ttu-id="9e23c-192">Wenn "Zulassen" oder "Verweigern" ausgewählt ist:</span><span class="sxs-lookup"><span data-stu-id="9e23c-192">When Type Allow or Deny is selected:</span></span>

   - <span data-ttu-id="9e23c-193">0: nothing</span><span class="sxs-lookup"><span data-stu-id="9e23c-193">0: nothing</span></span>
   - <span data-ttu-id="9e23c-194">4: Deaktivieren Sie **"AuditAllowed"** und **"AuditDenied"** für diesen Eintrag.</span><span class="sxs-lookup"><span data-stu-id="9e23c-194">4: disable **AuditAllowed** and **AuditDenied** for this Entry.</span></span> <span data-ttu-id="9e23c-195">Selbst wenn **"Blockieren"** erfolgt und die **"AuditDenied"-Einstellung** konfiguriert ist, zeigt das System keine Benachrichtigung an.</span><span class="sxs-lookup"><span data-stu-id="9e23c-195">Even if **Block** happens and the **AuditDenied** is setting configured, the system will not show notification.</span></span>

   <span data-ttu-id="9e23c-196">Wenn **"AuditAllowed"** oder **"AuditDenied"** ausgewählt ist:</span><span class="sxs-lookup"><span data-stu-id="9e23c-196">When Type **AuditAllowed** or **AuditDenied** is selected:</span></span>

   - <span data-ttu-id="9e23c-197">0: nothing</span><span class="sxs-lookup"><span data-stu-id="9e23c-197">0: nothing</span></span>
   - <span data-ttu-id="9e23c-198">1: Benachrichtigung anzeigen</span><span class="sxs-lookup"><span data-stu-id="9e23c-198">1: show notification</span></span>
   - <span data-ttu-id="9e23c-199">2: Send-Ereignis</span><span class="sxs-lookup"><span data-stu-id="9e23c-199">2: send event</span></span>
   - <span data-ttu-id="9e23c-200">3: Benachrichtigungs- und Sendeereignis anzeigen</span><span class="sxs-lookup"><span data-stu-id="9e23c-200">3: show notification and send event</span></span>

<span data-ttu-id="9e23c-201">**Eigenschaftenname: AccessMask**</span><span class="sxs-lookup"><span data-stu-id="9e23c-201">**Property name: AccessMask**</span></span>

<span data-ttu-id="9e23c-202">Beschreibung: Definiert den Zugriff.</span><span class="sxs-lookup"><span data-stu-id="9e23c-202">Description: Defines the access.</span></span>

<span data-ttu-id="9e23c-203">Optionen 1 bis 7:</span><span class="sxs-lookup"><span data-stu-id="9e23c-203">Options 1-7:</span></span>
  - <span data-ttu-id="9e23c-204">1: Lesen</span><span class="sxs-lookup"><span data-stu-id="9e23c-204">1: Read</span></span>
  - <span data-ttu-id="9e23c-205">2: Schreiben</span><span class="sxs-lookup"><span data-stu-id="9e23c-205">2: Write</span></span>
  - <span data-ttu-id="9e23c-206">3: Lesen und Schreiben</span><span class="sxs-lookup"><span data-stu-id="9e23c-206">3: Read and Write</span></span>
  - <span data-ttu-id="9e23c-207">4: Ausführen</span><span class="sxs-lookup"><span data-stu-id="9e23c-207">4: Execute</span></span>
  - <span data-ttu-id="9e23c-208">5: Lesen und Ausführen</span><span class="sxs-lookup"><span data-stu-id="9e23c-208">5: Read and Execute</span></span>
  - <span data-ttu-id="9e23c-209">6: Schreiben und Ausführen</span><span class="sxs-lookup"><span data-stu-id="9e23c-209">6: Write and Execute</span></span>
  - <span data-ttu-id="9e23c-210">7: Lesen und Schreiben und Ausführen</span><span class="sxs-lookup"><span data-stu-id="9e23c-210">7: Read and Write and Execute</span></span>

## <a name="common-removable-storage-access-control-scenarios"></a><span data-ttu-id="9e23c-211">Allgemeine Szenarien für die Zugriffssteuerung für wechselbare Storage</span><span class="sxs-lookup"><span data-stu-id="9e23c-211">Common Removable Storage Access Control scenarios</span></span>

<span data-ttu-id="9e23c-212">Um Sie mit Microsoft Defender für Endpunkt-Wechselmedien Storage Zugriffssteuerung vertraut zu machen, haben wir einige häufige Szenarien für Sie zusammengestellt.</span><span class="sxs-lookup"><span data-stu-id="9e23c-212">To help familiarize you with Microsoft Defender for Endpoint Removable Storage Access Control, we have put together some common scenarios for you to follow.</span></span>

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a><span data-ttu-id="9e23c-213">Szenario 1: Verhindern des Schreib- und Ausführungszugriffs auf alle genehmigten USBs, aber zulassen</span><span class="sxs-lookup"><span data-stu-id="9e23c-213">Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs</span></span>

1. <span data-ttu-id="9e23c-214">Erstellen von Gruppen</span><span class="sxs-lookup"><span data-stu-id="9e23c-214">Create groups</span></span>

    1. <span data-ttu-id="9e23c-215">Gruppe 1: Wechselmedien und CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="9e23c-215">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="9e23c-216">Ein Beispiel für einen Wechselmedien und eine CD/DVD ist: Gruppe **9b28fae8-72f7-4267-a1a5-685f747a7146** in der Beispieldatei ["Any Removable Storage" und "CD-DVD Group.xml".](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="9e23c-216">An example of a removable storage and CD/DVD is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="9e23c-217">Gruppe 2: Genehmigte USBs basierend auf Geräteeigenschaften.</span><span class="sxs-lookup"><span data-stu-id="9e23c-217">Group 2: Approved USBs based on device properties.</span></span> <span data-ttu-id="9e23c-218">Ein Beispiel für diesen Anwendungsfall ist: Instanz-ID – Gruppe **65fa649a-a111-4912-9294-fb6337a25038** in der Beispieldatei [für genehmigte USBs Group.xml.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="9e23c-218">An example for this use case is: Instance ID – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Approved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9e23c-219">Sie müssen `&` `&amp;` im Wert ersetzen.</span><span class="sxs-lookup"><span data-stu-id="9e23c-219">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="9e23c-220">Richtlinie erstellen</span><span class="sxs-lookup"><span data-stu-id="9e23c-220">Create policy</span></span>

    1. <span data-ttu-id="9e23c-221">Richtlinie 1: Schreib- und Ausführungszugriff blockieren, aber genehmigte USBs zulassen.</span><span class="sxs-lookup"><span data-stu-id="9e23c-221">Policy 1: Block Write and Execute Access but allow approved USBs.</span></span> <span data-ttu-id="9e23c-222">Ein Beispiel für diesen Anwendungsfall ist: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="9e23c-222">An example for this use case is: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="9e23c-223">Richtlinie 2: Überwachen des Schreib- und Ausführungszugriffs auf zulässige USBs.</span><span class="sxs-lookup"><span data-stu-id="9e23c-223">Policy 2: Audit Write and Execute access to allowed USBs.</span></span> <span data-ttu-id="9e23c-224">Ein Beispiel für diesen Anwendungsfall ist: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** im [Beispielszenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="9e23c-224">An example for this use case is: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** in the sample [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a><span data-ttu-id="9e23c-225">Szenario 2: Überwachen des Schreib- und Ausführungszugriffs auf alle nicht genehmigten USBs außer Blockieren bestimmter nicht genehmigter USBs</span><span class="sxs-lookup"><span data-stu-id="9e23c-225">Scenario 2: Audit Write and Execute access to all but block specific unapproved USBs</span></span>

1. <span data-ttu-id="9e23c-226">Erstellen von Gruppen</span><span class="sxs-lookup"><span data-stu-id="9e23c-226">Create groups</span></span>

    1. <span data-ttu-id="9e23c-227">Gruppe 1: Wechselmedien und CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="9e23c-227">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="9e23c-228">Ein Beispiel für diesen Anwendungsfall ist: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="9e23c-228">An example for this use case is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="9e23c-229">Gruppe 2: Nicht genehmigte USBs basierend auf Geräteeigenschaften, z. B. Anbieter-ID/Produkt-ID, Anzeigename – Gruppe **65fa649a-a111-4912-9294-fb6337a25038** in der Beispieldatei "Nicht genehmigte [USBs Group.xml".](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="9e23c-229">Group 2: Unapproved USBs based on device properties, for example, Vendor ID / Product ID, Friendly Name – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Unapproved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="9e23c-230">Sie müssen `&` `&amp;` im Wert ersetzen.</span><span class="sxs-lookup"><span data-stu-id="9e23c-230">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="9e23c-231">Richtlinie erstellen</span><span class="sxs-lookup"><span data-stu-id="9e23c-231">Create policy</span></span>

    1. <span data-ttu-id="9e23c-232">Richtlinie 1: Schreib- und Ausführungszugriff auf alle nicht genehmigten USBs blockieren.</span><span class="sxs-lookup"><span data-stu-id="9e23c-232">Policy 1: Block Write and Execute access to all but block specific unapproved USBs.</span></span> <span data-ttu-id="9e23c-233">Ein Beispiel für diesen Anwendungsfall ist: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** im [Beispielszenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="9e23c-233">An example of this use case is: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** in the sample [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="9e23c-234">Richtlinie 2: Überwachen des Schreib- und Ausführungszugriffs auf andere Personen.</span><span class="sxs-lookup"><span data-stu-id="9e23c-234">Policy 2: Audit Write and Execute access to others.</span></span> <span data-ttu-id="9e23c-235">Ein Beispiel für diesen Anwendungsfall ist: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** im [Beispielszenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="9e23c-235">An example of this use case is: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** in the sample [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

## <a name="deploying-and-managing-policy-via-group-policy"></a><span data-ttu-id="9e23c-236">Bereitstellen und Verwalten von Richtlinien über Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="9e23c-236">Deploying and managing policy via Group Policy</span></span>

<span data-ttu-id="9e23c-237">Mit dem Feature für die Zugriffssteuerung für Wechselmedien Storage können Sie Richtlinien über Gruppenrichtlinien entweder auf Benutzer oder Geräte oder auf beides anwenden.</span><span class="sxs-lookup"><span data-stu-id="9e23c-237">The Removable Storage Access Control feature enables you to apply policy via Group Policy to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="9e23c-238">Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="9e23c-238">Licensing</span></span>

<span data-ttu-id="9e23c-239">Bevor Sie mit wechselbaren Storage Zugriffssteuerung beginnen, müssen Sie Ihr [Microsoft 365 Abonnement](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)bestätigen.</span><span class="sxs-lookup"><span data-stu-id="9e23c-239">Before you get started with Removable Storage Access Control, you must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="9e23c-240">Um auf wechselbare Storage Zugriffssteuerung zuzugreifen und sie zu verwenden, müssen Sie über Microsoft 365 E3 oder Microsoft 365 E5 verfügen.</span><span class="sxs-lookup"><span data-stu-id="9e23c-240">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="deploying-policy-via-group-policy"></a><span data-ttu-id="9e23c-241">Bereitstellen von Richtlinien über Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="9e23c-241">Deploying policy via Group Policy</span></span>

1. <span data-ttu-id="9e23c-242">Kombinieren Sie alle Darin enthaltenen Gruppen `<Groups>` `</Groups>` in einer XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="9e23c-242">Combine all groups within `<Groups>` `</Groups>` into one xml file.</span></span> 

    <span data-ttu-id="9e23c-243">Die folgende Abbildung veranschaulicht das Beispiel von [Szenario 1: Verhindern des Schreib- und Ausführungszugriffs auf alle genehmigten USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)außer zulassen.</span><span class="sxs-lookup"><span data-stu-id="9e23c-243">The following image illustrates the example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="Der Bildschirm mit den Konfigurationseinstellungen, die bestimmte genehmigte USBs auf Geräten zulassen":::
    
2. <span data-ttu-id="9e23c-245">Kombinieren Sie alle darin enthaltenen Regeln `<PolicyRules>` `</PolicyRules>` in einer XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="9e23c-245">Combine all rules within `<PolicyRules>` `</PolicyRules>` into one xml file.</span></span> 

    <span data-ttu-id="9e23c-246">Wenn Sie einen bestimmten Benutzer einschränken möchten, verwenden Sie die SID-Eigenschaft im Eintrag.</span><span class="sxs-lookup"><span data-stu-id="9e23c-246">If you want to restrict a specific user, then use SID property into the Entry.</span></span> <span data-ttu-id="9e23c-247">Wenn der Richtlinieneintrag keine SID enthält, wird der Eintrag auf alle Anmeldeinstanzen für den Computer angewendet.</span><span class="sxs-lookup"><span data-stu-id="9e23c-247">If there is no SID in the policy Entry, the Entry will be applied to everyone login instance for the machine.</span></span>
    
    <span data-ttu-id="9e23c-248">Die folgende Abbildung veranschaulicht die Verwendung der SID-Eigenschaft und ein Beispiel für [Szenario 1: Verhindern des Schreib- und Ausführungszugriffs auf alle genehmigten USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)außer zulassen.</span><span class="sxs-lookup"><span data-stu-id="9e23c-248">The following image illustrates the usage of SID property, and an example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="Der Bildschirm mit einem Code, der die Verwendung des SID-Eigenschaftsattributs angibt":::

3. <span data-ttu-id="9e23c-250">Speichern Sie sowohl Regel- als auch Gruppen-XML-Dateien im Netzwerkfreigabeordner, und fügen Sie den Pfad des Netzwerkfreigabeordners in die Gruppenrichtlinieneinstellung ein: **Computerkonfiguration - > Administrative Vorlagen -> Windows Komponenten -> Microsoft Defender Antivirus -> Gerätesteuerung: "Gerätesteuerungsrichtliniengruppen definieren" und "Gerätesteuerungsrichtlinienregeln definieren".**</span><span class="sxs-lookup"><span data-stu-id="9e23c-250">Save both rule and group XML files on network share folder and put network share folder path into the Group Policy setting: **Computer Configuration -> Administrative Templates -> Windows Components -> Microsoft Defender Antivirus -> Device Control: ‘Define device control policy groups’ and ‘Define device control policy rules’**.</span></span>

    - <span data-ttu-id="9e23c-251">Der Zielcomputer muss auf die Netzwerkfreigabe zugreifen können, damit die Richtlinie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="9e23c-251">The target machine must be able to access the network share to have the policy.</span></span> <span data-ttu-id="9e23c-252">Nachdem die Richtlinie gelesen wurde, ist die Netzwerkfreigabeverbindung jedoch auch nach dem Computerneustart nicht mehr erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9e23c-252">However, once the policy is read, the network share connection is no longer required, even after machine reboot.</span></span>

    :::image type="content" source="images/device-control.png" alt-text="Der Bildschirm des Gerätesteuerelements":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a><span data-ttu-id="9e23c-254">Bereitstellen und Verwalten von Richtlinien über Intune OMA-URI</span><span class="sxs-lookup"><span data-stu-id="9e23c-254">Deploying and managing policy via Intune OMA-URI</span></span>

<span data-ttu-id="9e23c-255">Mit dem Feature für die Zugriffssteuerung für wechselbare Storage können Sie Richtlinien über OMA-URI entweder auf Benutzer oder Geräte oder auf beides anwenden.</span><span class="sxs-lookup"><span data-stu-id="9e23c-255">The Removable Storage Access Control feature enables you to apply policy via OMA-URI to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="9e23c-256">Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="9e23c-256">Licensing</span></span>

<span data-ttu-id="9e23c-257">Bevor Sie mit wechselbaren Storage Zugriffssteuerung beginnen, müssen Sie Ihr [Microsoft 365 Abonnement](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)bestätigen.</span><span class="sxs-lookup"><span data-stu-id="9e23c-257">Before you get started with Removable Storage Access Control, you  must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="9e23c-258">Um auf wechselbare Storage Zugriffssteuerung zuzugreifen und sie zu verwenden, müssen Sie über Microsoft 365 E3 oder Microsoft 365 E5 verfügen.</span><span class="sxs-lookup"><span data-stu-id="9e23c-258">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="permission"></a><span data-ttu-id="9e23c-259">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="9e23c-259">Permission</span></span>

<span data-ttu-id="9e23c-260">Für die Richtlinienbereitstellung in Intune muss das Konto über Berechtigungen zum Erstellen, Bearbeiten, Aktualisieren oder Löschen von Gerätekonfigurationsprofilen verfügen.</span><span class="sxs-lookup"><span data-stu-id="9e23c-260">For policy deployment in Intune, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="9e23c-261">Sie können benutzerdefinierte Rollen erstellen oder eine der integrierten Rollen mit diesen Berechtigungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="9e23c-261">You can create custom roles or use any of the built-in roles with these permissions.</span></span>

- <span data-ttu-id="9e23c-262">Rolle "Richtlinien- und Profil-Manager"</span><span class="sxs-lookup"><span data-stu-id="9e23c-262">Policy and profile Manager role</span></span>
- <span data-ttu-id="9e23c-263">Benutzerdefinierte Rolle mit aktivierten Berechtigungen zum Erstellen/Bearbeiten/Aktualisieren/Lesen/Löschen/Anzeigen von Berichten für Gerätekonfigurationsprofile</span><span class="sxs-lookup"><span data-stu-id="9e23c-263">Custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="9e23c-264">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="9e23c-264">Global administrator</span></span>

### <a name="deploying-policy-via-oma-uri"></a><span data-ttu-id="9e23c-265">Bereitstellen von Richtlinien über OMA-URI</span><span class="sxs-lookup"><span data-stu-id="9e23c-265">Deploying policy via OMA-URI</span></span>

<span data-ttu-id="9e23c-266">**Microsoft Endpoint Manager Admin Center ( https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span><span class="sxs-lookup"><span data-stu-id="9e23c-266">**Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span></span>

1. <span data-ttu-id="9e23c-267">Erstellen Sie für jede Gruppe eine OMA-URI-Regel:</span><span class="sxs-lookup"><span data-stu-id="9e23c-267">For each Group, create an OMA-URI rule:</span></span>
    - <span data-ttu-id="9e23c-268">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="9e23c-268">OMA-URI:</span></span>

      <span data-ttu-id="9e23c-269">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="9e23c-269">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span></span>

      <span data-ttu-id="9e23c-270">For example, for **any removable storage and CD/DVD** group in the sample, the link must be:</span><span class="sxs-lookup"><span data-stu-id="9e23c-270">For example, for **any removable storage and CD/DVD** group in the sample, the link must be:</span></span>

      <span data-ttu-id="9e23c-271">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="9e23c-271">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span></span>

    - <span data-ttu-id="9e23c-272">Datentyp: Zeichenfolge (XML-Datei)</span><span class="sxs-lookup"><span data-stu-id="9e23c-272">Data Type: String (XML file)</span></span>
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="Die XML-Datei für den DATENTYP STRING":::

2. <span data-ttu-id="9e23c-274">Erstellen Sie für jede Richtlinie auch einen OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="9e23c-274">For each policy, also create an OMA-URI:</span></span>

    - <span data-ttu-id="9e23c-275">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="9e23c-275">OMA-URI:</span></span>

      <span data-ttu-id="9e23c-276">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span><span class="sxs-lookup"><span data-stu-id="9e23c-276">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span></span>

      <span data-ttu-id="9e23c-277">For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be:</span><span class="sxs-lookup"><span data-stu-id="9e23c-277">For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be:</span></span> 

      <span data-ttu-id="9e23c-278">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span><span class="sxs-lookup"><span data-stu-id="9e23c-278">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span></span>

    - <span data-ttu-id="9e23c-279">Datentyp: Zeichenfolge (XML-Datei)</span><span class="sxs-lookup"><span data-stu-id="9e23c-279">Data Type: String (XML file)</span></span>

      :::image type="content" source="images/xml-data-type-string-2.png" lightbox="images/xml-data-type-string-2.png" alt-text="Anzeigen der XML-Datei für den DATENTYP STRING":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a><span data-ttu-id="9e23c-281">Bereitstellen und Verwalten von Richtlinien mithilfe der Intune-Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="9e23c-281">Deploying and managing policy by using Intune user interface</span></span>

<span data-ttu-id="9e23c-282">Diese Funktion (im Microsoft Endpoint Manager Admin Center ( https://endpoint.microsoft.com/) > Geräte > Konfigurationsprofile > Profil > Plattform erstellen: Windows 10 und höher & Profil: Gerätesteuerung) ist noch nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9e23c-282">This capability (in Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) > Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control) is not yet available.</span></span> 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="9e23c-283">Anzeigen von Wechseldaten von Gerätesteuerungen Storage Zugriffssteuerungsdaten in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9e23c-283">View Device Control Removable Storage Access Control data in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="9e23c-284">Das Microsoft 365-Sicherheitsportal zeigt Wechselmedien an, die von der Gerätesteuerung (Removable Storage Access Control) blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="9e23c-284">The Microsoft 365 security portal shows removable storage blocked by the Device Control Removable Storage Access Control.</span></span> <span data-ttu-id="9e23c-285">Um auf die Microsoft 365 Sicherheit zugreifen zu können, müssen Sie über das folgende Abonnement verfügen:</span><span class="sxs-lookup"><span data-stu-id="9e23c-285">To access the Microsoft 365 security, you must have the following subscription:</span></span>

- <span data-ttu-id="9e23c-286">Microsoft 365 für E5-Berichte</span><span class="sxs-lookup"><span data-stu-id="9e23c-286">Microsoft 365 for E5 reporting</span></span>

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

## <a name="frequently-asked-questions"></a><span data-ttu-id="9e23c-288">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="9e23c-288">Frequently asked questions</span></span>

<span data-ttu-id="9e23c-289">**Was ist die Beschränkung für Wechselmedien für die maximale Anzahl von USBs?**</span><span class="sxs-lookup"><span data-stu-id="9e23c-289">**What is the removable storage media limitation for the maximum number of USBs?**</span></span>

<span data-ttu-id="9e23c-290">Wir haben eine USB-Gruppe mit 100.000 Medien – bis zu 7 MB Größe – überprüft.</span><span class="sxs-lookup"><span data-stu-id="9e23c-290">We have validated one USB group with 100,000 media - up to 7 MB in size.</span></span> <span data-ttu-id="9e23c-291">Die Richtlinie funktioniert sowohl in Intune als auch im Gruppenrichtlinienobjekt ohne Leistungsprobleme.</span><span class="sxs-lookup"><span data-stu-id="9e23c-291">The policy works in both Intune and GPO without performance issues.</span></span>

<span data-ttu-id="9e23c-292">**Warum funktioniert die Richtlinie nicht?**</span><span class="sxs-lookup"><span data-stu-id="9e23c-292">**Why does the policy not work?**</span></span>

<span data-ttu-id="9e23c-293">Der häufigste Grund ist, dass keine erforderliche [Antischadsoftware-Clientversion](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints)vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="9e23c-293">The most common reason is there is no required [antimalware client version](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints).</span></span>

<span data-ttu-id="9e23c-294">Ein weiterer Grund kann sein, dass die XML-Datei nicht richtig formatiert ist, z. B. nicht die richtige Markdownformatierung für das Zeichen "&" in der XML-Datei verwendet wird, oder dass der Texteditor am Anfang der Dateien eine Bytereihenfolgemarke (Byte Order Mark, BOM) 0xEF 0xBB 0xBF hinzugibt, was dazu führt, dass die XML-Analyse nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="9e23c-294">Another reason could be that the XML file is not correctly formatted, for example, not using the correct markdown formatting for the "&" character in the XML file, or the text editor might add a byte order mark (BOM) 0xEF 0xBB 0xBF at the beginning of the files which causes the XML parsing not to work.</span></span> <span data-ttu-id="9e23c-295">Eine einfache Lösung besteht darin, die [Beispieldatei](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) (wählen Sie **"Raw"** und dann **"Speichern unter")** herunterzuladen und dann zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="9e23c-295">One simple solution is to download the [sample file](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) (select **Raw** and then **Save as**) and then update.</span></span>

<span data-ttu-id="9e23c-296">Wenn ein Wert vorhanden ist und die Richtlinie über die Gruppenrichtlinie verwaltet wird, überprüfen Sie, ob das Clientgerät auf den RICHTLINIEN-XML-Pfad zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="9e23c-296">If there is a value and the policy is managed via Group Policy, check whether the client device can access the policy XML path.</span></span>

<span data-ttu-id="9e23c-297">**Wie kann ich wissen, welcher Computer die veraltete Clientversion für Antischadsoftware in der Organisation verwendet?**</span><span class="sxs-lookup"><span data-stu-id="9e23c-297">**How can I know which machine is using out of date antimalware client version in the organization?**</span></span>

<span data-ttu-id="9e23c-298">Sie können die folgende Abfrage verwenden, um die Clientversion für Antischadsoftware im Microsoft 365 Sicherheitsportal abzurufen:</span><span class="sxs-lookup"><span data-stu-id="9e23c-298">You can use following query to get antimalware client version on the Microsoft 365 security portal:</span></span>
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
