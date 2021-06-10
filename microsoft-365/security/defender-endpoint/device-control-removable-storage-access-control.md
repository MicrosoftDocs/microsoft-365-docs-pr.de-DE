---
title: Microsoft Defender für Endpunkt-Gerätesteuerung – Wechselmedien Storage Zugriffssteuerung
description: Eine exemplarische Vorgehensweise zu Microsoft Defender für Endpunkt
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
ms.openlocfilehash: cf8e74a6886d7086da062d6258e3e1e1a1cbd730
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861719"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a><span data-ttu-id="7297f-104">Microsoft Defender für Endpunkt-Gerätesteuerung – Wechselmedien Storage Zugriffssteuerung</span><span class="sxs-lookup"><span data-stu-id="7297f-104">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="7297f-105">Microsoft Defender für Endpunkt-Gerätesteuerung – Wechselmedien Storage Zugriffssteuerung ermöglicht Ihnen die folgende Aufgabe:</span><span class="sxs-lookup"><span data-stu-id="7297f-105">Microsoft Defender for Endpoint Device Control Removable Storage Access Control enables you to do the following task:</span></span>
- <span data-ttu-id="7297f-106">Überwachen, Zulassen oder Verhindern des Lese-, Schreib- oder Ausführungszugriffs auf Wechselmedien mit oder ohne Ausschluss</span><span class="sxs-lookup"><span data-stu-id="7297f-106">auditing, allowing or preventing the read, write or execute access to removable storage with or without exclusion</span></span>

|<span data-ttu-id="7297f-107">Privileg</span><span class="sxs-lookup"><span data-stu-id="7297f-107">Privilege</span></span> |<span data-ttu-id="7297f-108">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="7297f-108">Permission</span></span>  |
|---------|---------|
|<span data-ttu-id="7297f-109">Zugriff</span><span class="sxs-lookup"><span data-stu-id="7297f-109">Access</span></span>    |  <span data-ttu-id="7297f-110">Lese-/Schreib-/Ausführungszugriff</span><span class="sxs-lookup"><span data-stu-id="7297f-110">Read, Write, Execute</span></span>       |
|<span data-ttu-id="7297f-111">Aktionsmodus</span><span class="sxs-lookup"><span data-stu-id="7297f-111">Action Mode</span></span>    |    <span data-ttu-id="7297f-112">Überwachen, Zulassen, Verhindern</span><span class="sxs-lookup"><span data-stu-id="7297f-112">Audit, Allow, Prevent</span></span>     |
|<span data-ttu-id="7297f-113">CSP-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="7297f-113">CSP Support</span></span>   |   <span data-ttu-id="7297f-114">Ja</span><span class="sxs-lookup"><span data-stu-id="7297f-114">Yes</span></span>      |
|<span data-ttu-id="7297f-115">GPO-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="7297f-115">GPO Support</span></span>    |   <span data-ttu-id="7297f-116">Ja</span><span class="sxs-lookup"><span data-stu-id="7297f-116">Yes</span></span>      |
|<span data-ttu-id="7297f-117">Benutzerbasierter Support</span><span class="sxs-lookup"><span data-stu-id="7297f-117">User-based Support</span></span>     |   <span data-ttu-id="7297f-118">Ja</span><span class="sxs-lookup"><span data-stu-id="7297f-118">Yes</span></span>      |
|<span data-ttu-id="7297f-119">Computerbasierter Support</span><span class="sxs-lookup"><span data-stu-id="7297f-119">Machine-based Support</span></span>    |    <span data-ttu-id="7297f-120">Ja</span><span class="sxs-lookup"><span data-stu-id="7297f-120">Yes</span></span>     |

## <a name="prepare-your-endpoints"></a><span data-ttu-id="7297f-121">Vorbereiten der Endpunkte</span><span class="sxs-lookup"><span data-stu-id="7297f-121">Prepare your endpoints</span></span>

<span data-ttu-id="7297f-122">Bereitstellen von Wechseldatenträgern Storage Zugriffssteuerung auf Windows 10 Geräten mit Der Clientversion **4.18.2103.3 oder höher** für Antischadsoftware.</span><span class="sxs-lookup"><span data-stu-id="7297f-122">Deploy Removable Storage Access Control on Windows 10 devices that have Anti-malware Client Version **4.18.2103.3 or later**.</span></span>
1. <span data-ttu-id="7297f-123">**4.18.2104 oder höher:** Hinzufügen von SerialNumberId, VID_PID, dateipfadbasierter GPO-Unterstützung, ComputerSid</span><span class="sxs-lookup"><span data-stu-id="7297f-123">**4.18.2104 or later**: Add SerialNumberId, VID_PID, filepath-based GPO support, ComputerSid</span></span>

2. <span data-ttu-id="7297f-124">**4.18.2105 oder höher:** Hinzufügen von Platzhalterunterstützung für HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, die Kombination aus einem bestimmten Benutzer auf einem bestimmten Computer, entfernender SSD (sanDisk Extreme SSD)/USB Attached SCSI (UAS)-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="7297f-124">**4.18.2105 or later**: Add Wildcard support for HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, the combination of specific user on specific machine, removeable SSD (a SanDisk Extreme SSD)/USB Attached SCSI (UAS) support</span></span>

:::image type="content" source="images/powershell.png" alt-text="Die PowerShell-Schnittstelle":::

   > [!NOTE]
   > <span data-ttu-id="7297f-126">Keine der Windows-Sicherheit Komponenten aktiv sein muss, können Sie wechselbare Storage Zugriffssteuerung unabhängig von Windows-Sicherheit Status ausführen.</span><span class="sxs-lookup"><span data-stu-id="7297f-126">None of Windows Security components need to be active, you can run Removable Storage Access Control independent of Windows Security status.</span></span>

## <a name="policy-properties"></a><span data-ttu-id="7297f-127">Richtlinieneigenschaften</span><span class="sxs-lookup"><span data-stu-id="7297f-127">Policy properties</span></span>


<span data-ttu-id="7297f-128">Sie können die folgenden Eigenschaften verwenden, um eine Wechselmediengruppe zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="7297f-128">You can use the following properties to create a removable storage group:</span></span>

<span data-ttu-id="7297f-129">**Eigenschaftenname: Gruppen-ID**</span><span class="sxs-lookup"><span data-stu-id="7297f-129">**Property name: Group Id**</span></span>

1. <span data-ttu-id="7297f-130">Beschreibung: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), eine eindeutige ID, stellt die Gruppe dar und wird in der Richtlinie verwendet.</span><span class="sxs-lookup"><span data-stu-id="7297f-130">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the group and will be used in the policy.</span></span>

<span data-ttu-id="7297f-131">**Eigenschaftenname: DescriptorIdList**</span><span class="sxs-lookup"><span data-stu-id="7297f-131">**Property name: DescriptorIdList**</span></span>

1. <span data-ttu-id="7297f-132">Beschreibung: Auflisten der Geräteeigenschaften, die Sie in der Gruppe abdecken möchten.</span><span class="sxs-lookup"><span data-stu-id="7297f-132">Description: List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="7297f-133">Listet die Geräteeigenschaften auf, die Sie in der Gruppe abdecken möchten.</span><span class="sxs-lookup"><span data-stu-id="7297f-133">List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="7297f-134">Weitere Informationen zu jeder Geräteeigenschaft finden Sie weiter oben im Abschnitt **"Geräteeigenschaften".**</span><span class="sxs-lookup"><span data-stu-id="7297f-134">For each device property, see **Device Properties** section above for more detail.</span></span>

1. <span data-ttu-id="7297f-135">Optionen:</span><span class="sxs-lookup"><span data-stu-id="7297f-135">Options:</span></span>
    - <span data-ttu-id="7297f-136">Primäre ID</span><span class="sxs-lookup"><span data-stu-id="7297f-136">Primary ID</span></span>
        - <span data-ttu-id="7297f-137">RemovableMediaDevices</span><span class="sxs-lookup"><span data-stu-id="7297f-137">RemovableMediaDevices</span></span>
        - <span data-ttu-id="7297f-138">CdRomDevices</span><span class="sxs-lookup"><span data-stu-id="7297f-138">CdRomDevices</span></span>
    - <span data-ttu-id="7297f-139">Deviceid</span><span class="sxs-lookup"><span data-stu-id="7297f-139">DeviceId</span></span>
    - <span data-ttu-id="7297f-140">HardwareId</span><span class="sxs-lookup"><span data-stu-id="7297f-140">HardwareId</span></span>
    - <span data-ttu-id="7297f-141">InstancePathId: InstancePathId ist eine Zeichenfolge, die das Gerät im System eindeutig identifiziert, z. B. USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span><span class="sxs-lookup"><span data-stu-id="7297f-141">InstancePathId: InstancePathId is a string that uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span></span> <span data-ttu-id="7297f-142">Die Zahl am Ende (z. **B.&0)** stellt den verfügbaren Steckplatz dar und kann sich von Gerät zu Gerät ändern.</span><span class="sxs-lookup"><span data-stu-id="7297f-142">The number at the end (for example **&0**) represents the available slot and may change from device to device.</span></span> <span data-ttu-id="7297f-143">Um optimale Ergebnisse zu erzielen, verwenden Sie am Ende einen Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="7297f-143">For best results, use a wildcard at the end.</span></span> <span data-ttu-id="7297f-144">Beispiel: USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span><span class="sxs-lookup"><span data-stu-id="7297f-144">For example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span></span>
    - <span data-ttu-id="7297f-145">FriendlyNameId</span><span class="sxs-lookup"><span data-stu-id="7297f-145">FriendlyNameId</span></span>
    - <span data-ttu-id="7297f-146">SerialNumberId</span><span class="sxs-lookup"><span data-stu-id="7297f-146">SerialNumberId</span></span>
    - <span data-ttu-id="7297f-147">Vid</span><span class="sxs-lookup"><span data-stu-id="7297f-147">VID</span></span>
    - <span data-ttu-id="7297f-148">Pid</span><span class="sxs-lookup"><span data-stu-id="7297f-148">PID</span></span>
    - <span data-ttu-id="7297f-149">VID_PID</span><span class="sxs-lookup"><span data-stu-id="7297f-149">VID_PID</span></span>
        - <span data-ttu-id="7297f-150">0751_55E0: Übereinstimmung mit diesem genauen VID/PID-Paar</span><span class="sxs-lookup"><span data-stu-id="7297f-150">0751_55E0: match this exact VID/PID pair</span></span>
        - <span data-ttu-id="7297f-151">_55E0: Abgleichen von Medien mit PID=55E0</span><span class="sxs-lookup"><span data-stu-id="7297f-151">_55E0: match any media with PID=55E0</span></span>
        - <span data-ttu-id="7297f-152">0751_: Alle Medien mit VID=0751 abgleichen</span><span class="sxs-lookup"><span data-stu-id="7297f-152">0751_: match any media with VID=0751</span></span>
        
<span data-ttu-id="7297f-153">**Eigenschaftenname: MatchType**</span><span class="sxs-lookup"><span data-stu-id="7297f-153">**Property name: MatchType**</span></span> 

1. <span data-ttu-id="7297f-154">Beschreibung: Wenn mehrere Geräteeigenschaften in der DescriptorIDList verwendet werden, definiert MatchType die Beziehung.</span><span class="sxs-lookup"><span data-stu-id="7297f-154">Description: When there are multiple device properties being used in the DescriptorIDList, MatchType defines the relationship.</span></span>

1. <span data-ttu-id="7297f-155">Optionen:</span><span class="sxs-lookup"><span data-stu-id="7297f-155">Options:</span></span>
    - <span data-ttu-id="7297f-156">MatchAll: Alle Attribute unter der DescriptorIdList sind **"And"-Beziehung;** Wenn der Administrator beispielsweise DeviceID und InstancePathID platziert, überprüft das System für jeden angeschlossenen USB-Stick, ob der USB beide Werte erfüllt.</span><span class="sxs-lookup"><span data-stu-id="7297f-156">MatchAll: Any attributes under the DescriptorIdList will be **And** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will check to see whether the USB meets both values.</span></span>

    - <span data-ttu-id="7297f-157">MatchAny: Die Attribute unter "DescriptorIdList" sind **"Or".** Wenn der Administrator beispielsweise DeviceID und InstancePathID platziert, führt das System für jeden angeschlossenen USB-Stick die Erzwingung aus, solange der USB-Stick entweder über einen identischen **DeviceID-** oder **InstanceID-Wert** verfügt.</span><span class="sxs-lookup"><span data-stu-id="7297f-157">MatchAny: The attributes under the DescriptorIdList will be **Or** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will do the enforcement as long as the USB has either an identical **DeviceID** or **InstanceID** value.</span></span>



<span data-ttu-id="7297f-158">Es folgen die Eigenschaften der Zugriffssteuerungsrichtlinie:</span><span class="sxs-lookup"><span data-stu-id="7297f-158">Following are the access control policy properties:</span></span>

<span data-ttu-id="7297f-159">**Eigenschaftenname: PolicyRuleId**</span><span class="sxs-lookup"><span data-stu-id="7297f-159">**Property name: PolicyRuleId**</span></span>

1. <span data-ttu-id="7297f-160">Beschreibung: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), eine eindeutige ID, stellt die Richtlinie dar und wird in der Berichterstellung und Problembehandlung verwendet.</span><span class="sxs-lookup"><span data-stu-id="7297f-160">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the policy and will be used in the reporting and troubleshooting.</span></span>

<span data-ttu-id="7297f-161">**Eigenschaftenname: IncludedIdList**</span><span class="sxs-lookup"><span data-stu-id="7297f-161">**Property name: IncludedIdList**</span></span>

1. <span data-ttu-id="7297f-162">Beschreibung: Die Gruppen, auf die die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="7297f-162">Description: The group(s) that the policy will be applied to.</span></span> <span data-ttu-id="7297f-163">Wenn mehrere Gruppen hinzugefügt werden, wird die Richtlinie auf alle Medien in allen diesen Gruppen angewendet.</span><span class="sxs-lookup"><span data-stu-id="7297f-163">If multiple groups are added, the policy will be applied to any media in all those groups.</span></span>

1. <span data-ttu-id="7297f-164">Optionen: Die Gruppen-ID/GUID muss in dieser Instanz verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7297f-164">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="7297f-165">Das folgende Beispiel zeigt die Verwendung von GroupID:</span><span class="sxs-lookup"><span data-stu-id="7297f-165">The following example shows the usage of GroupID:</span></span>

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

<span data-ttu-id="7297f-166">**Eigenschaftenname: ExcludedIDList**</span><span class="sxs-lookup"><span data-stu-id="7297f-166">**Property name: ExcludedIDList**</span></span>

1. <span data-ttu-id="7297f-167">Beschreibung: Die Gruppen, auf die die Richtlinie nicht angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="7297f-167">Description: The group(s) that the policy will not be applied to.</span></span>
1. <span data-ttu-id="7297f-168">Optionen: Die Gruppen-ID/GUID muss in dieser Instanz verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7297f-168">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="7297f-169">**Eigenschaftenname: Eintrags-ID**</span><span class="sxs-lookup"><span data-stu-id="7297f-169">**Property name: Entry Id**</span></span>

1. <span data-ttu-id="7297f-170">Beschreibung: One PolicyRule kann mehrere Einträge haben; Jeder Eintrag mit einer eindeutigen GUID teilt der Gerätesteuerung eine Einschränkung mit.</span><span class="sxs-lookup"><span data-stu-id="7297f-170">Description: One PolicyRule can have multiple entries; each entry with a unique GUID tells Device Control one restriction.</span></span>

<span data-ttu-id="7297f-171">**Eigenschaftenname: Typ**</span><span class="sxs-lookup"><span data-stu-id="7297f-171">**Property name: Type**</span></span>

1. <span data-ttu-id="7297f-172">Beschreibung: Definiert die Aktion für die Wechselmediengruppen in IncludedIDList.</span><span class="sxs-lookup"><span data-stu-id="7297f-172">Description: Defines the action for the removable storage groups in IncludedIDList.</span></span>
    - <span data-ttu-id="7297f-173">Erzwingung: Zulassen oder Verweigern</span><span class="sxs-lookup"><span data-stu-id="7297f-173">Enforcement: Allow or Deny</span></span>
    - <span data-ttu-id="7297f-174">Audit: AuditAllowed oder AuditDenied</span><span class="sxs-lookup"><span data-stu-id="7297f-174">Audit: AuditAllowed or AuditDenied</span></span> 
1. <span data-ttu-id="7297f-175">Optionen:</span><span class="sxs-lookup"><span data-stu-id="7297f-175">Options:</span></span>
    - <span data-ttu-id="7297f-176">Zulassen</span><span class="sxs-lookup"><span data-stu-id="7297f-176">Allow</span></span>
    - <span data-ttu-id="7297f-177">Verweigern</span><span class="sxs-lookup"><span data-stu-id="7297f-177">Deny</span></span>
    - <span data-ttu-id="7297f-178">AuditAllowed: Definiert Benachrichtigung und Ereignis, wenn der Zugriff zulässig ist</span><span class="sxs-lookup"><span data-stu-id="7297f-178">AuditAllowed: Defines notification and event when access is allowed</span></span>
    - <span data-ttu-id="7297f-179">AuditDenied: Definiert Benachrichtigung und Ereignis, wenn der Zugriff verweigert wird; muss mit **der Verweigerungseingabe zusammenarbeiten.**</span><span class="sxs-lookup"><span data-stu-id="7297f-179">AuditDenied: Defines notification and event when access is denied; has to work together with **Deny** entry.</span></span>

<span data-ttu-id="7297f-180">Wenn es Konflikttypen für dieselben Medien gibt, wendet das System den ersten in der Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="7297f-180">When there are conflict types for the same media, the system will apply the first one in the policy.</span></span> <span data-ttu-id="7297f-181">Ein Beispiel für einen Konflikttyp ist **Allow** and **Deny**.</span><span class="sxs-lookup"><span data-stu-id="7297f-181">An example of a conflict type is **Allow** and **Deny**.</span></span>

<span data-ttu-id="7297f-182">**Eigenschaftenname: Sid**</span><span class="sxs-lookup"><span data-stu-id="7297f-182">**Property name: Sid**</span></span>

1. <span data-ttu-id="7297f-183">Beschreibung: Definiert, ob diese Richtlinie auf bestimmte Benutzer oder Benutzergruppen angewendet wird; Ein Eintrag kann maximal eine Sid haben, und ein Eintrag ohne Sid bedeutet, dass die Richtlinie auf dem Computer angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="7297f-183">Description: Defines whether apply this policy over specific user or user group; one entry can have maximum one Sid and an entry without any Sid means applying the policy over the machine.</span></span>

<span data-ttu-id="7297f-184">**Eigenschaftenname: ComputerSid**</span><span class="sxs-lookup"><span data-stu-id="7297f-184">**Property name: ComputerSid**</span></span>

1. <span data-ttu-id="7297f-185">Beschreibung: Definiert, ob diese Richtlinie auf bestimmte Computer oder Computergruppen angewendet wird; Ein Eintrag kann maximal eine ComputerSid haben, und ein Eintrag ohne ComputerSid bedeutet, dass die Richtlinie auf dem Computer angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="7297f-185">Description: Defines whether apply this policy over specific machine or machine group; one entry can have maximum one ComputerSid and an entry without any ComputerSid means applying the policy over the machine.</span></span> <span data-ttu-id="7297f-186">Wenn Sie einen Eintrag auf einen bestimmten Benutzer und einen bestimmten Computer anwenden möchten, fügen Sie sid und computerSid demselben Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="7297f-186">If you want to apply an Entry to a specific user and specific machine, add both Sid and ComputerSid into the same Entry.</span></span>

<span data-ttu-id="7297f-187">**Eigenschaftenname: Optionen**</span><span class="sxs-lookup"><span data-stu-id="7297f-187">**Property name: Options**</span></span>

1. <span data-ttu-id="7297f-188">Beschreibung: Definiert, ob eine Benachrichtigung angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7297f-188">Description: Defines whether to display notification or not.</span></span>

   :::image type="content" source="images/device-status.png" alt-text="Der Bildschirm, auf dem der Status des Geräts angezeigt werden kann":::

1. <span data-ttu-id="7297f-190">Optionen: 0-4.</span><span class="sxs-lookup"><span data-stu-id="7297f-190">Options: 0-4.</span></span> <span data-ttu-id="7297f-191">Wenn "Zulassen" oder "Verweigern" ausgewählt ist:</span><span class="sxs-lookup"><span data-stu-id="7297f-191">When Type Allow or Deny is selected:</span></span>

   - <span data-ttu-id="7297f-192">0: nothing</span><span class="sxs-lookup"><span data-stu-id="7297f-192">0: nothing</span></span>
   - <span data-ttu-id="7297f-193">4: Deaktivieren Sie **"AuditAllowed"** und **"AuditDenied"** für diesen Eintrag.</span><span class="sxs-lookup"><span data-stu-id="7297f-193">4: disable **AuditAllowed** and **AuditDenied** for this Entry.</span></span> <span data-ttu-id="7297f-194">Selbst wenn **"Blockieren"** erfolgt und die **"AuditDenied"-Einstellung** konfiguriert ist, zeigt das System keine Benachrichtigung an.</span><span class="sxs-lookup"><span data-stu-id="7297f-194">Even if **Block** happens and the **AuditDenied** is setting configured, the system will not show notification.</span></span>

   <span data-ttu-id="7297f-195">Wenn **"AuditAllowed"** oder **"AuditDenied"** ausgewählt ist:</span><span class="sxs-lookup"><span data-stu-id="7297f-195">When Type **AuditAllowed** or **AuditDenied** is selected:</span></span>

   - <span data-ttu-id="7297f-196">0: nothing</span><span class="sxs-lookup"><span data-stu-id="7297f-196">0: nothing</span></span>
   - <span data-ttu-id="7297f-197">1: Benachrichtigung anzeigen</span><span class="sxs-lookup"><span data-stu-id="7297f-197">1: show notification</span></span>
   - <span data-ttu-id="7297f-198">2: Send-Ereignis</span><span class="sxs-lookup"><span data-stu-id="7297f-198">2: send event</span></span>
   - <span data-ttu-id="7297f-199">3: Benachrichtigungs- und Sendeereignis anzeigen</span><span class="sxs-lookup"><span data-stu-id="7297f-199">3: show notification and send event</span></span>

<span data-ttu-id="7297f-200">**Eigenschaftenname: AccessMask**</span><span class="sxs-lookup"><span data-stu-id="7297f-200">**Property name: AccessMask**</span></span>

1. <span data-ttu-id="7297f-201">Beschreibung: Definiert den Zugriff.</span><span class="sxs-lookup"><span data-stu-id="7297f-201">Description: Defines the access.</span></span>

1. <span data-ttu-id="7297f-202">Optionen: 1-7:</span><span class="sxs-lookup"><span data-stu-id="7297f-202">Options: 1-7:</span></span>
    - <span data-ttu-id="7297f-203">1: Lesen</span><span class="sxs-lookup"><span data-stu-id="7297f-203">1: Read</span></span>
    - <span data-ttu-id="7297f-204">2: Schreiben</span><span class="sxs-lookup"><span data-stu-id="7297f-204">2: Write</span></span>
    - <span data-ttu-id="7297f-205">3: Lesen und Schreiben</span><span class="sxs-lookup"><span data-stu-id="7297f-205">3: Read and Write</span></span>
    - <span data-ttu-id="7297f-206">4: Ausführen</span><span class="sxs-lookup"><span data-stu-id="7297f-206">4: Execute</span></span>
    - <span data-ttu-id="7297f-207">5: Lesen und Ausführen</span><span class="sxs-lookup"><span data-stu-id="7297f-207">5: Read and Execute</span></span>
    - <span data-ttu-id="7297f-208">6: Schreiben und Ausführen</span><span class="sxs-lookup"><span data-stu-id="7297f-208">6: Write and Execute</span></span>
    - <span data-ttu-id="7297f-209">7: Lesen und Schreiben und Ausführen</span><span class="sxs-lookup"><span data-stu-id="7297f-209">7: Read and Write and Execute</span></span>

## <a name="common-removable-storage-access-control-scenarios"></a><span data-ttu-id="7297f-210">Allgemeine Szenarien für die Zugriffssteuerung für wechselbare Storage</span><span class="sxs-lookup"><span data-stu-id="7297f-210">Common Removable Storage Access Control scenarios</span></span>

<span data-ttu-id="7297f-211">Um Sie mit Microsoft Defender für Endpunkt-Wechselmedien Storage Zugriffssteuerung vertraut zu machen, haben wir einige häufige Szenarien für Sie zusammengestellt.</span><span class="sxs-lookup"><span data-stu-id="7297f-211">To help familiarize you with Microsoft Defender for Endpoint Removable Storage Access Control, we have put together some common scenarios for you to follow.</span></span>

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a><span data-ttu-id="7297f-212">Szenario 1: Verhindern des Schreib- und Ausführungszugriffs auf alle genehmigten USBs, aber zulassen</span><span class="sxs-lookup"><span data-stu-id="7297f-212">Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs</span></span>

1. <span data-ttu-id="7297f-213">Erstellen von Gruppen</span><span class="sxs-lookup"><span data-stu-id="7297f-213">Create groups</span></span>
    1. <span data-ttu-id="7297f-214">Gruppe 1: Wechselmedien und CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="7297f-214">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="7297f-215">Ein Beispiel für einen Wechselmedien und eine CD/DVD ist: Gruppe **9b28fae8-72f7-4267-a1a5-685f747a7146** in der Beispieldatei ["Any Removable Storage" und "CD-DVD Group.xml".](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="7297f-215">An example of a removable storage and CD/DVD is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="7297f-216">Gruppe 2: Genehmigte USBs basierend auf Geräteeigenschaften.</span><span class="sxs-lookup"><span data-stu-id="7297f-216">Group 2: Approved USBs based on device properties.</span></span> <span data-ttu-id="7297f-217">Ein Beispiel für diesen Anwendungsfall ist: Instanz-ID – Gruppe **65fa649a-a111-4912-9294-fb6337a25038** in der Beispieldatei [für genehmigte USBs Group.xml.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="7297f-217">An example for this use case is: Instance ID – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Approved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7297f-218">Sie müssen `&` `&amp;` im Wert ersetzen.</span><span class="sxs-lookup"><span data-stu-id="7297f-218">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="7297f-219">Richtlinie erstellen</span><span class="sxs-lookup"><span data-stu-id="7297f-219">Create policy</span></span>
    1. <span data-ttu-id="7297f-220">Richtlinie 1: Schreib- und Ausführungszugriff blockieren, aber genehmigte USBs zulassen.</span><span class="sxs-lookup"><span data-stu-id="7297f-220">Policy 1: Block Write and Execute Access but allow approved USBs.</span></span> <span data-ttu-id="7297f-221">Ein Beispiel für diesen Anwendungsfall ist: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs .xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="7297f-221">An example for this use case is: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs .xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="7297f-222">Richtlinie 2: Überwachen des Schreib- und Ausführungszugriffs auf zulässige USBs.</span><span class="sxs-lookup"><span data-stu-id="7297f-222">Policy 2: Audit Write and Execute access to allowed USBs.</span></span> <span data-ttu-id="7297f-223">Ein Beispiel für diesen Anwendungsfall ist: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** im [Beispielszenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="7297f-223">An example for this use case is: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** in the sample [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a><span data-ttu-id="7297f-224">Szenario 2: Überwachen des Schreib- und Ausführungszugriffs auf alle nicht genehmigten USBs außer Blockieren bestimmter nicht genehmigter USBs</span><span class="sxs-lookup"><span data-stu-id="7297f-224">Scenario 2: Audit Write and Execute access to all but block specific unapproved USBs</span></span>

1. <span data-ttu-id="7297f-225">Erstellen von Gruppen</span><span class="sxs-lookup"><span data-stu-id="7297f-225">Create groups</span></span>
    1. <span data-ttu-id="7297f-226">Gruppe 1: Wechselmedien und CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="7297f-226">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="7297f-227">Ein Beispiel für diesen Anwendungsfall ist: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="7297f-227">An example for this use case is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="7297f-228">Gruppe 2: Nicht genehmigte USBs basierend auf Geräteeigenschaften, z. B. Anbieter-ID/Produkt-ID, Anzeigename – Gruppe **65fa649a-a111-4912-9294-fb6337a25038** in der Beispieldatei "Nicht genehmigte [USBs Group.xml".](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="7297f-228">Group 2: Unapproved USBs based on device properties, for example, Vendor ID / Product ID, Friendly Name – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Unapproved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="7297f-229">Sie müssen `&` `&amp;` im Wert ersetzen.</span><span class="sxs-lookup"><span data-stu-id="7297f-229">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="7297f-230">Richtlinie erstellen</span><span class="sxs-lookup"><span data-stu-id="7297f-230">Create policy</span></span>
    1. <span data-ttu-id="7297f-231">Richtlinie 1: Schreib- und Ausführungszugriff auf alle nicht genehmigten USBs blockieren.</span><span class="sxs-lookup"><span data-stu-id="7297f-231">Policy 1: Block Write and Execute access to all but block specific unapproved USBs.</span></span> <span data-ttu-id="7297f-232">Ein Beispiel für diesen Anwendungsfall ist: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** im [Beispielszenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="7297f-232">An example of this use case is: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** in the sample [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="7297f-233">Richtlinie 2: Überwachen des Schreib- und Ausführungszugriffs auf andere Personen.</span><span class="sxs-lookup"><span data-stu-id="7297f-233">Policy 2: Audit Write and Execute access to others.</span></span> <span data-ttu-id="7297f-234">Ein Beispiel für diesen Anwendungsfall ist: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** in the sample [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="7297f-234">An example of this use case is: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** in the sample [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

## <a name="deploying-and-managing-policy-via-group-policy"></a><span data-ttu-id="7297f-235">Bereitstellen und Verwalten von Richtlinien über Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="7297f-235">Deploying and managing policy via Group Policy</span></span>

<span data-ttu-id="7297f-236">Mit dem Feature "Wechselbare Storage Zugriffssteuerung" können Sie Richtlinien über Gruppenrichtlinien entweder auf Benutzer oder Geräte oder auf beides anwenden.</span><span class="sxs-lookup"><span data-stu-id="7297f-236">The Removable Storage Access Control feature enables you to apply policy via Group Policy to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="7297f-237">Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="7297f-237">Licensing</span></span>

<span data-ttu-id="7297f-238">Bevor Sie mit wechselbaren Storage Zugriffssteuerung beginnen, müssen Sie Ihr [Microsoft 365 Abonnement](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)bestätigen.</span><span class="sxs-lookup"><span data-stu-id="7297f-238">Before you get started with Removable Storage Access Control, you must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="7297f-239">Um auf wechselbare Storage Zugriffssteuerung zuzugreifen und sie zu verwenden, müssen Sie über Microsoft 365 E3 oder Microsoft 365 E5 verfügen.</span><span class="sxs-lookup"><span data-stu-id="7297f-239">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="deploying-policy-via-group-policy"></a><span data-ttu-id="7297f-240">Bereitstellen von Richtlinien über Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="7297f-240">Deploying policy via Group Policy</span></span>

1. <span data-ttu-id="7297f-241">Kombinieren Sie alle Darin enthaltenen Gruppen `<Groups>` `</Groups>` in einer XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="7297f-241">Combine all groups within `<Groups>` `</Groups>` into one xml file.</span></span> 

    <span data-ttu-id="7297f-242">Die folgende Abbildung veranschaulicht das Beispiel von [Szenario 1: Verhindern des Schreib- und Ausführungszugriffs auf alle genehmigten USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)außer zulassen.</span><span class="sxs-lookup"><span data-stu-id="7297f-242">The following image illustrates the example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="Der Bildschirm mit den Konfigurationseinstellungen, die bestimmte genehmigte USBs auf Geräten zulassen":::
    
2. <span data-ttu-id="7297f-244">Kombinieren Sie alle darin enthaltenen Regeln `<PolicyRules>` `</PolicyRules>` in einer XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="7297f-244">Combine all rules within `<PolicyRules>` `</PolicyRules>` into one xml file.</span></span> 

    <span data-ttu-id="7297f-245">Wenn Sie einen bestimmten Benutzer einschränken möchten, verwenden Sie die SID-Eigenschaft im Eintrag.</span><span class="sxs-lookup"><span data-stu-id="7297f-245">If you want to restrict a specific user, then use SID property into the Entry.</span></span> <span data-ttu-id="7297f-246">Wenn der Richtlinieneintrag keine SID enthält, wird der Eintrag auf alle Anmeldeinstanzen für den Computer angewendet.</span><span class="sxs-lookup"><span data-stu-id="7297f-246">If there is no SID in the policy Entry, the Entry will be applied to everyone login instance for the machine.</span></span>
    
    <span data-ttu-id="7297f-247">Die folgende Abbildung veranschaulicht die Verwendung der SID-Eigenschaft und ein Beispiel für [Szenario 1: Verhindern des Schreib- und Ausführungszugriffs auf alle genehmigten USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)außer zulassen.</span><span class="sxs-lookup"><span data-stu-id="7297f-247">The following image illustrates the usage of SID property, and an example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="Der Bildschirm mit einem Code, der die Verwendung des SID-Eigenschaftsattributs angibt":::

3. <span data-ttu-id="7297f-249">Speichern Sie sowohl Regel- als auch Gruppen-XML-Dateien im Netzwerkfreigabeordner, und fügen Sie den Pfad des Netzwerkfreigabeordners in die Gruppenrichtlinieneinstellung ein: **Computerkonfiguration -> Administrative Vorlagen -> Windows Komponenten -> Microsoft Defender Antivirus -> Gerätesteuerung: "Gerätesteuerungsrichtliniengruppen definieren" und "Gerätesteuerungsrichtlinienregeln definieren".**</span><span class="sxs-lookup"><span data-stu-id="7297f-249">Save both rule and group XML files on network share folder and put network share folder path into the Group Policy setting: **Computer Configuration -> Administrative Templates -> Windows Components -> Microsoft Defender Antivirus -> Device Control: ‘Define device control policy groups’ and ‘Define device control policy rules’**.</span></span>

    - <span data-ttu-id="7297f-250">Der Zielcomputer muss auf die Netzwerkfreigabe zugreifen können, um über die Richtlinie verfügen zu können.</span><span class="sxs-lookup"><span data-stu-id="7297f-250">The target machine must be able to access the network share to have the policy.</span></span> <span data-ttu-id="7297f-251">Nachdem die Richtlinie gelesen wurde, ist die Netzwerkfreigabeverbindung jedoch auch nach dem Computerneustart nicht mehr erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7297f-251">However, once the policy is read, the network share connection is no longer required, even after machine reboot.</span></span>

    :::image type="content" source="images/device-control.png" alt-text="Der Bildschirm des Gerätesteuerelements":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a><span data-ttu-id="7297f-253">Bereitstellen und Verwalten von Richtlinien über Intune OMA-URI</span><span class="sxs-lookup"><span data-stu-id="7297f-253">Deploying and managing policy via Intune OMA-URI</span></span>

<span data-ttu-id="7297f-254">Mit dem Feature "Wechselbare Storage Zugriffssteuerung" können Sie Richtlinien über OMA-URI entweder auf Benutzer oder Geräte oder auf beides anwenden.</span><span class="sxs-lookup"><span data-stu-id="7297f-254">The Removable Storage Access Control feature enables you to apply policy via OMA-URI to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="7297f-255">Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="7297f-255">Licensing</span></span>

<span data-ttu-id="7297f-256">Bevor Sie mit wechselbaren Storage Zugriffssteuerung beginnen, müssen Sie Ihr [Microsoft 365 Abonnement](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)bestätigen.</span><span class="sxs-lookup"><span data-stu-id="7297f-256">Before you get started with Removable Storage Access Control, you  must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="7297f-257">Um auf wechselbare Storage Zugriffssteuerung zuzugreifen und sie zu verwenden, müssen Sie über Microsoft 365 E3 oder Microsoft 365 E5 verfügen.</span><span class="sxs-lookup"><span data-stu-id="7297f-257">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="permission"></a><span data-ttu-id="7297f-258">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="7297f-258">Permission</span></span>

<span data-ttu-id="7297f-259">Für die Richtlinienbereitstellung in Intune muss das Konto über Berechtigungen zum Erstellen, Bearbeiten, Aktualisieren oder Löschen von Gerätekonfigurationsprofilen verfügen.</span><span class="sxs-lookup"><span data-stu-id="7297f-259">For policy deployment in Intune, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="7297f-260">Sie können benutzerdefinierte Rollen erstellen oder eine der integrierten Rollen mit diesen Berechtigungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="7297f-260">You can create custom roles or use any of the built-in roles with these permissions.</span></span>

- <span data-ttu-id="7297f-261">Rolle "Richtlinien- und Profil-Manager"</span><span class="sxs-lookup"><span data-stu-id="7297f-261">Policy and profile Manager role</span></span>
- <span data-ttu-id="7297f-262">Benutzerdefinierte Rolle mit aktivierten Berechtigungen zum Erstellen/Bearbeiten/Aktualisieren/Lesen/Löschen/Anzeigen von Berichten für Gerätekonfigurationsprofile</span><span class="sxs-lookup"><span data-stu-id="7297f-262">Custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="7297f-263">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="7297f-263">Global administrator</span></span>

### <a name="deploying-policy-via-oma-uri"></a><span data-ttu-id="7297f-264">Bereitstellen von Richtlinien über OMA-URI</span><span class="sxs-lookup"><span data-stu-id="7297f-264">Deploying policy via OMA-URI</span></span>

<span data-ttu-id="7297f-265">**Microsoft Endpoint Manager Admin Center ( https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span><span class="sxs-lookup"><span data-stu-id="7297f-265">**Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span></span>

1. <span data-ttu-id="7297f-266">Erstellen Sie für jede Gruppe eine OMA-URI-Regel:</span><span class="sxs-lookup"><span data-stu-id="7297f-266">For each Group, create an OMA-URI rule:</span></span>
    - <span data-ttu-id="7297f-267">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="7297f-267">OMA-URI:</span></span>

      <span data-ttu-id="7297f-268">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="7297f-268">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span></span>

      <span data-ttu-id="7297f-269">For example, for **any removable storage and CD/DVD** group in the sample, the link must be:</span><span class="sxs-lookup"><span data-stu-id="7297f-269">For example, for **any removable storage and CD/DVD** group in the sample, the link must be:</span></span>

      <span data-ttu-id="7297f-270">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="7297f-270">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span></span>

    - <span data-ttu-id="7297f-271">Datentyp: Zeichenfolge (XML-Datei)</span><span class="sxs-lookup"><span data-stu-id="7297f-271">Data Type: String (XML file)</span></span>
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="Die XML-Datei für den DATENTYP STRING":::

2. <span data-ttu-id="7297f-273">Erstellen Sie für jede Richtlinie auch einen OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="7297f-273">For each policy, also create an OMA-URI:</span></span>

    - <span data-ttu-id="7297f-274">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="7297f-274">OMA-URI:</span></span>

      <span data-ttu-id="7297f-275">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span><span class="sxs-lookup"><span data-stu-id="7297f-275">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span></span>

      <span data-ttu-id="7297f-276">For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be:</span><span class="sxs-lookup"><span data-stu-id="7297f-276">For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be:</span></span> 

      <span data-ttu-id="7297f-277">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span><span class="sxs-lookup"><span data-stu-id="7297f-277">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span></span>

    - <span data-ttu-id="7297f-278">Datentyp: Zeichenfolge (XML-Datei)</span><span class="sxs-lookup"><span data-stu-id="7297f-278">Data Type: String (XML file)</span></span>

      :::image type="content" source="images/xml-data-type-string-2.png" lightbox="images/xml-data-type-string-2.png" alt-text="Anzeigen der XML-Datei für den DATENTYP STRING":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a><span data-ttu-id="7297f-280">Bereitstellen und Verwalten von Richtlinien mithilfe der Intune-Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="7297f-280">Deploying and managing policy by using Intune user interface</span></span>

<span data-ttu-id="7297f-281">Diese Funktion (in Microsoft Endpoint Manager Admin Center ( https://endpoint.microsoft.com/) > Geräte > Konfigurationsprofile > Profil > Plattform erstellen: Windows 10 und höher & Profil: Gerätesteuerung) ist noch nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7297f-281">This capability (in Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) > Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control) is not yet available.</span></span> 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="7297f-282">Anzeigen von Wechseldaten von Gerätesteuerungen Storage Zugriffssteuerungsdaten in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="7297f-282">View Device Control Removable Storage Access Control data in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="7297f-283">Das Microsoft 365-Sicherheitsportal zeigt Wechselmedien an, die von der Gerätesteuerung (Removable Storage Access Control) blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="7297f-283">The Microsoft 365 security portal shows removable storage blocked by the Device Control Removable Storage Access Control.</span></span> <span data-ttu-id="7297f-284">Um auf die Microsoft 365 Sicherheit zugreifen zu können, benötigen Sie das folgende Abonnement:</span><span class="sxs-lookup"><span data-stu-id="7297f-284">To access the Microsoft 365 security, you must have the following subscription:</span></span>

- <span data-ttu-id="7297f-285">Microsoft 365 für E5-Berichte</span><span class="sxs-lookup"><span data-stu-id="7297f-285">Microsoft 365 for E5 reporting</span></span>

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
