---
title: Microsoft Defender for Endpoint Device Control Wechseldatenträgerzugriffssteuerung
description: Ein Walk-Through zu Microsoft Defender for Endpoint
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
ms.openlocfilehash: 46ea74d11f9c54cd1d967058433a74ef4c1ead19
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300176"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a><span data-ttu-id="8c65b-104">Microsoft Defender for Endpoint Device Control Wechseldatenträgerzugriffssteuerung</span><span class="sxs-lookup"><span data-stu-id="8c65b-104">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="8c65b-105">Microsoft Defender for Endpoint Device Control Removable Storage Access Control ermöglicht Ihnen die folgende Aufgabe:</span><span class="sxs-lookup"><span data-stu-id="8c65b-105">Microsoft Defender for Endpoint Device Control Removable Storage Access Control enables you to do the following task:</span></span>
- <span data-ttu-id="8c65b-106">Überwachung, Zulassen oder Verhindern des Lese-, Schreib- oder Ausführungszugriffs auf Wechselmedien mit oder ohne Ausschluss</span><span class="sxs-lookup"><span data-stu-id="8c65b-106">auditing, allowing or preventing the read, write or execute access to removable storage with or without exclusion</span></span>

|<span data-ttu-id="8c65b-107">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="8c65b-107">Privilege</span></span> |<span data-ttu-id="8c65b-108">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="8c65b-108">Permission</span></span>  |
|---------|---------|
|<span data-ttu-id="8c65b-109">Zugriff</span><span class="sxs-lookup"><span data-stu-id="8c65b-109">Access</span></span>    |  <span data-ttu-id="8c65b-110">Lese-/Schreib-/Ausführungszugriff</span><span class="sxs-lookup"><span data-stu-id="8c65b-110">Read, Write, Execute</span></span>       |
|<span data-ttu-id="8c65b-111">Aktionsmodus</span><span class="sxs-lookup"><span data-stu-id="8c65b-111">Action Mode</span></span>    |    <span data-ttu-id="8c65b-112">Überwachung, Zulassen, Verhindern</span><span class="sxs-lookup"><span data-stu-id="8c65b-112">Audit, Allow, Prevent</span></span>     |
|<span data-ttu-id="8c65b-113">CSP-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="8c65b-113">CSP Support</span></span>   |   <span data-ttu-id="8c65b-114">Ja</span><span class="sxs-lookup"><span data-stu-id="8c65b-114">Yes</span></span>      |
|<span data-ttu-id="8c65b-115">GPO-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="8c65b-115">GPO Support</span></span>    |   <span data-ttu-id="8c65b-116">Ja</span><span class="sxs-lookup"><span data-stu-id="8c65b-116">Yes</span></span>      |
|<span data-ttu-id="8c65b-117">Benutzerbasierter Support</span><span class="sxs-lookup"><span data-stu-id="8c65b-117">User-based Support</span></span>     |   <span data-ttu-id="8c65b-118">Ja</span><span class="sxs-lookup"><span data-stu-id="8c65b-118">Yes</span></span>      |
|<span data-ttu-id="8c65b-119">Computerbasierte Unterstützung</span><span class="sxs-lookup"><span data-stu-id="8c65b-119">Machine-based Support</span></span>    |    <span data-ttu-id="8c65b-120">Ja</span><span class="sxs-lookup"><span data-stu-id="8c65b-120">Yes</span></span>     |

## <a name="prepare-your-endpoints"></a><span data-ttu-id="8c65b-121">Vorbereiten der Endpunkte</span><span class="sxs-lookup"><span data-stu-id="8c65b-121">Prepare your endpoints</span></span>

<span data-ttu-id="8c65b-122">Bereitstellen der Wechseldatenträgerzugriffssteuerung auf Windows 10-Geräten mit Clientversion **4.18.2103.3 oder höher.**</span><span class="sxs-lookup"><span data-stu-id="8c65b-122">Deploy Removable Storage Access Control on Windows 10 devices that have Anti-malware Client Version **4.18.2103.3 or later**.</span></span>
1. <span data-ttu-id="8c65b-123">**4.18.2104 oder höher**: Hinzufügen von SerialNumberId, VID_PID, filepath-basierter Gruppenrichtlinienobjektunterstützung</span><span class="sxs-lookup"><span data-stu-id="8c65b-123">**4.18.2104 or later**: Add SerialNumberId, VID_PID, filepath-based GPO support</span></span>

2. <span data-ttu-id="8c65b-124">**4.18.2105 oder höher**: Hinzufügen von Platzhalterunterstützung für HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, die Kombination bestimmter Benutzer auf einem bestimmten Computer, absetzbare SSD (eine SanDisk Extreme SSD)/USB Attached SCSI (UAS)</span><span class="sxs-lookup"><span data-stu-id="8c65b-124">**4.18.2105 or later**: Add Wildcard support for HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, the combination of specific user on specific machine, removeable SSD (a SanDisk Extreme SSD)/USB Attached SCSI (UAS) support</span></span>

:::image type="content" source="images/powershell.png" alt-text="Die PowerShell-Schnittstelle":::

## <a name="policy-properties"></a><span data-ttu-id="8c65b-126">Richtlinieneigenschaften</span><span class="sxs-lookup"><span data-stu-id="8c65b-126">Policy properties</span></span>

<span data-ttu-id="8c65b-127">Sie können die folgenden Eigenschaften verwenden, um eine Wechselspeichergruppe zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="8c65b-127">You can use the following properties to create a removable storage group:</span></span>

<span data-ttu-id="8c65b-128">**Eigenschaftsname: Gruppen-ID**</span><span class="sxs-lookup"><span data-stu-id="8c65b-128">**Property name: Group ID**</span></span>

1. <span data-ttu-id="8c65b-129">Beschreibung: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), eine eindeutige ID, stellt die Gruppe dar und wird in der Richtlinie verwendet.</span><span class="sxs-lookup"><span data-stu-id="8c65b-129">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the group and will be used in the policy.</span></span>

<span data-ttu-id="8c65b-130">**Eigenschaftsname: DescriptorIdList**</span><span class="sxs-lookup"><span data-stu-id="8c65b-130">**Property name: DescriptorIdList**</span></span>

1. <span data-ttu-id="8c65b-131">Beschreibung: Listet die Geräteeigenschaften auf, die Sie in der Gruppe abdecken möchten.</span><span class="sxs-lookup"><span data-stu-id="8c65b-131">Description: List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="8c65b-132">Listet die Geräteeigenschaften auf, die Sie in der Gruppe abdecken möchten.</span><span class="sxs-lookup"><span data-stu-id="8c65b-132">List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="8c65b-133">Weitere Informationen zu jeder Geräteeigenschaft finden Sie **weiter** oben im Abschnitt Geräteeigenschaften.</span><span class="sxs-lookup"><span data-stu-id="8c65b-133">For each device property, see **Device Properties** section above for more detail.</span></span>

1. <span data-ttu-id="8c65b-134">Optionen:</span><span class="sxs-lookup"><span data-stu-id="8c65b-134">Options:</span></span>
    - <span data-ttu-id="8c65b-135">Primäre ID</span><span class="sxs-lookup"><span data-stu-id="8c65b-135">Primary ID</span></span>
        - <span data-ttu-id="8c65b-136">RemovableMediaDevices</span><span class="sxs-lookup"><span data-stu-id="8c65b-136">RemovableMediaDevices</span></span>
        - <span data-ttu-id="8c65b-137">CdRomDevices</span><span class="sxs-lookup"><span data-stu-id="8c65b-137">CdRomDevices</span></span>
    - <span data-ttu-id="8c65b-138">DeviceId</span><span class="sxs-lookup"><span data-stu-id="8c65b-138">DeviceId</span></span>
    - <span data-ttu-id="8c65b-139">HardwareId</span><span class="sxs-lookup"><span data-stu-id="8c65b-139">HardwareId</span></span>
    - <span data-ttu-id="8c65b-140">InstancePathId</span><span class="sxs-lookup"><span data-stu-id="8c65b-140">InstancePathId</span></span>
    - <span data-ttu-id="8c65b-141">FriendlyNameId</span><span class="sxs-lookup"><span data-stu-id="8c65b-141">FriendlyNameId</span></span>
    - <span data-ttu-id="8c65b-142">SerialNumberId</span><span class="sxs-lookup"><span data-stu-id="8c65b-142">SerialNumberId</span></span>
    - <span data-ttu-id="8c65b-143">VID</span><span class="sxs-lookup"><span data-stu-id="8c65b-143">VID</span></span>
    - <span data-ttu-id="8c65b-144">PID</span><span class="sxs-lookup"><span data-stu-id="8c65b-144">PID</span></span>
    - <span data-ttu-id="8c65b-145">VID_PID</span><span class="sxs-lookup"><span data-stu-id="8c65b-145">VID_PID</span></span>
        - <span data-ttu-id="8c65b-146">0751_55E0: Übereinstimmung mit diesem genauen VID/PID-Paar</span><span class="sxs-lookup"><span data-stu-id="8c65b-146">0751_55E0: match this exact VID/PID pair</span></span>
        - <span data-ttu-id="8c65b-147">_55E0: Übereinstimmen beliebiger Medien mit PID=55E0</span><span class="sxs-lookup"><span data-stu-id="8c65b-147">_55E0: match any media with PID=55E0</span></span>
        - <span data-ttu-id="8c65b-148">0751_: Übereinstimmen beliebiger Medien mit VID=0751</span><span class="sxs-lookup"><span data-stu-id="8c65b-148">0751_: match any media with VID=0751</span></span>
        
<span data-ttu-id="8c65b-149">**Eigenschaftsname: MatchType**</span><span class="sxs-lookup"><span data-stu-id="8c65b-149">**Property name: MatchType**</span></span> 

1. <span data-ttu-id="8c65b-150">Beschreibung: Wenn mehrere Geräteeigenschaften in descriptorIDList verwendet werden, definiert MatchType die Beziehung.</span><span class="sxs-lookup"><span data-stu-id="8c65b-150">Description: When there are multiple device properties being used in the DescriptorIDList, MatchType defines the relationship.</span></span>

1. <span data-ttu-id="8c65b-151">Optionen:</span><span class="sxs-lookup"><span data-stu-id="8c65b-151">Options:</span></span>
    - <span data-ttu-id="8c65b-152">MatchAll: Alle Attribute unter descriptorIdList sind **And-Beziehung;** Wenn der Administrator z. B. DeviceID und InstancePathID für jeden angeschlossenen USB-Speicher einriert, überprüft das System, ob der USB beide Werte erfüllt.</span><span class="sxs-lookup"><span data-stu-id="8c65b-152">MatchAll: Any attributes under the DescriptorIdList will be **And** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will check to see whether the USB meets both values.</span></span>

    - <span data-ttu-id="8c65b-153">MatchAny: Die Attribute unter descriptorIdList lauten **Or-Beziehung;** Wenn der Administrator z. B. DeviceID und InstancePathID für jeden angeschlossenen USB-Speicher einriert, führt das System die Erzwingung aus, solange der USB entweder einen identischen **DeviceID-** oder **InstanceID-Wert** hat.</span><span class="sxs-lookup"><span data-stu-id="8c65b-153">MatchAny: The attributes under the DescriptorIdList will be **Or** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will do the enforcement as long as the USB has either an identical **DeviceID** or **InstanceID** value.</span></span>

<span data-ttu-id="8c65b-154">Im Folgenden finden Sie die Eigenschaften der Zugriffssteuerungsrichtlinie:</span><span class="sxs-lookup"><span data-stu-id="8c65b-154">Following are the access control policy properties:</span></span>

<span data-ttu-id="8c65b-155">**Eigenschaftsname: PolicyRuleId**</span><span class="sxs-lookup"><span data-stu-id="8c65b-155">**Property name: PolicyRuleId**</span></span>

1. <span data-ttu-id="8c65b-156">Beschreibung: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), eine eindeutige ID, stellt die Richtlinie dar und wird in der Berichterstellung und Problembehandlung verwendet.</span><span class="sxs-lookup"><span data-stu-id="8c65b-156">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the policy and will be used in the reporting and troubleshooting.</span></span>

<span data-ttu-id="8c65b-157">**Eigenschaftsname: IncludedIdList**</span><span class="sxs-lookup"><span data-stu-id="8c65b-157">**Property name: IncludedIdList**</span></span>

1. <span data-ttu-id="8c65b-158">Beschreibung: Die Gruppen, auf die die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="8c65b-158">Description: The group(s) that the policy will be applied to.</span></span> <span data-ttu-id="8c65b-159">Wenn mehrere Gruppen hinzugefügt werden, wird die Richtlinie auf alle Medien in allen diesen Gruppen angewendet.</span><span class="sxs-lookup"><span data-stu-id="8c65b-159">If multiple groups are added, the policy will be applied to any media in all those groups.</span></span>

1. <span data-ttu-id="8c65b-160">Optionen: Die Gruppen-ID/GUID muss in dieser Instanz verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8c65b-160">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="8c65b-161">Das folgende Beispiel zeigt die Verwendung von GroupID:</span><span class="sxs-lookup"><span data-stu-id="8c65b-161">The following example shows the usage of GroupID:</span></span>

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

<span data-ttu-id="8c65b-162">**Eigenschaftsname: ExcludedIDList**</span><span class="sxs-lookup"><span data-stu-id="8c65b-162">**Property name: ExcludedIDList**</span></span>

1. <span data-ttu-id="8c65b-163">Beschreibung: Die Gruppen, auf die die Richtlinie nicht angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="8c65b-163">Description: The group(s) that the policy will not be applied to.</span></span>
1. <span data-ttu-id="8c65b-164">Optionen: Die Gruppen-ID/GUID muss in dieser Instanz verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8c65b-164">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="8c65b-165">**Eigenschaftsname: Eintrags-ID**</span><span class="sxs-lookup"><span data-stu-id="8c65b-165">**Property name: Entry ID**</span></span>

1. <span data-ttu-id="8c65b-166">Beschreibung: Ein PolicyRule kann mehrere Einträge haben; Jeder Eintrag mit einer eindeutigen GUID teilt der Gerätesteuerung eine Einschränkung mit.</span><span class="sxs-lookup"><span data-stu-id="8c65b-166">Description: One PolicyRule can have multiple entries; each entry with a unique GUID tells Device Control one restriction.</span></span>

<span data-ttu-id="8c65b-167">**Eigenschaftsname: Type**</span><span class="sxs-lookup"><span data-stu-id="8c65b-167">**Property name: Type**</span></span>

1. <span data-ttu-id="8c65b-168">Beschreibung: Definiert die Aktion für die Wechselspeichergruppen in IncludedIDList.</span><span class="sxs-lookup"><span data-stu-id="8c65b-168">Description: Defines the action for the removable storage groups in IncludedIDList.</span></span>
    - <span data-ttu-id="8c65b-169">Erzwingung: Zulassen oder Verweigern</span><span class="sxs-lookup"><span data-stu-id="8c65b-169">Enforcement: Allow or Deny</span></span>
    - <span data-ttu-id="8c65b-170">Überwachung: AuditAllowed oder AuditDenied</span><span class="sxs-lookup"><span data-stu-id="8c65b-170">Audit: AuditAllowed or AuditDenied</span></span> 
1. <span data-ttu-id="8c65b-171">Optionen:</span><span class="sxs-lookup"><span data-stu-id="8c65b-171">Options:</span></span>
    - <span data-ttu-id="8c65b-172">Zulassen</span><span class="sxs-lookup"><span data-stu-id="8c65b-172">Allow</span></span>
    - <span data-ttu-id="8c65b-173">Verweigern</span><span class="sxs-lookup"><span data-stu-id="8c65b-173">Deny</span></span>
    - <span data-ttu-id="8c65b-174">AuditAllowed: Definiert Benachrichtigung und Ereignis, wenn der Zugriff zulässig ist</span><span class="sxs-lookup"><span data-stu-id="8c65b-174">AuditAllowed: Defines notification and event when access is allowed</span></span>
    - <span data-ttu-id="8c65b-175">AuditDenied: Definiert Benachrichtigung und Ereignis, wenn der Zugriff verweigert wird; muss mit dem Eintrag **Verweigern zusammenarbeiten.**</span><span class="sxs-lookup"><span data-stu-id="8c65b-175">AuditDenied: Defines notification and event when access is denied; has to work together with **Deny** entry.</span></span>

<span data-ttu-id="8c65b-176">Wenn Konflikttypen für dasselbe Medium verfügbar sind, wird der erste in der Richtlinie vom System angewendet.</span><span class="sxs-lookup"><span data-stu-id="8c65b-176">When there are conflict types for the same media, the system will apply the first one in the policy.</span></span> <span data-ttu-id="8c65b-177">Ein Beispiel für einen Konflikttyp ist **Allow** und **Deny**.</span><span class="sxs-lookup"><span data-stu-id="8c65b-177">An example of a conflict type is **Allow** and **Deny**.</span></span>

<span data-ttu-id="8c65b-178">**Eigenschaftsname: Optionen**</span><span class="sxs-lookup"><span data-stu-id="8c65b-178">**Property name: Options**</span></span>

1. <span data-ttu-id="8c65b-179">Beschreibung: Definiert, ob eine Benachrichtigung angezeigt werden soll oder nicht.</span><span class="sxs-lookup"><span data-stu-id="8c65b-179">Description: Defines whether to display notification or not.</span></span>

   :::image type="content" source="images/device-status.png" alt-text="Der Bildschirm, auf dem der Status des Geräts angezeigt werden kann":::

1. <span data-ttu-id="8c65b-181">Optionen: 0-4.</span><span class="sxs-lookup"><span data-stu-id="8c65b-181">Options: 0-4.</span></span> <span data-ttu-id="8c65b-182">Wenn Typ Zulassen oder Verweigern ausgewählt ist:</span><span class="sxs-lookup"><span data-stu-id="8c65b-182">When Type Allow or Deny is selected:</span></span>

   - <span data-ttu-id="8c65b-183">0: nothing</span><span class="sxs-lookup"><span data-stu-id="8c65b-183">0: nothing</span></span>
   - <span data-ttu-id="8c65b-184">4: Deaktivieren **Sie AuditAllowed** und **AuditDenied** für diesen Eintrag.</span><span class="sxs-lookup"><span data-stu-id="8c65b-184">4: disable **AuditAllowed** and **AuditDenied** for this Entry.</span></span> <span data-ttu-id="8c65b-185">Selbst wenn **Block** auftritt und **die Einstellung AuditDenied** konfiguriert ist, zeigt das System keine Benachrichtigung an.</span><span class="sxs-lookup"><span data-stu-id="8c65b-185">Even if **Block** happens and the **AuditDenied** is setting configured, the system will not show notification.</span></span>

   <span data-ttu-id="8c65b-186">Wenn Typ **AuditAllowed oder** **AuditDenied** ausgewählt ist:</span><span class="sxs-lookup"><span data-stu-id="8c65b-186">When Type **AuditAllowed** or **AuditDenied** is selected:</span></span>

   - <span data-ttu-id="8c65b-187">0: nothing</span><span class="sxs-lookup"><span data-stu-id="8c65b-187">0: nothing</span></span>
   - <span data-ttu-id="8c65b-188">1: Benachrichtigung anzeigen</span><span class="sxs-lookup"><span data-stu-id="8c65b-188">1: show notification</span></span>
   - <span data-ttu-id="8c65b-189">2: Send-Ereignis</span><span class="sxs-lookup"><span data-stu-id="8c65b-189">2: send event</span></span>
   - <span data-ttu-id="8c65b-190">3: Benachrichtigungs- und Sendeereignis anzeigen</span><span class="sxs-lookup"><span data-stu-id="8c65b-190">3: show notification and send event</span></span>

<span data-ttu-id="8c65b-191">**Eigenschaftsname: AccessMask**</span><span class="sxs-lookup"><span data-stu-id="8c65b-191">**Property name: AccessMask**</span></span>

1. <span data-ttu-id="8c65b-192">Beschreibung: Definiert den Zugriff.</span><span class="sxs-lookup"><span data-stu-id="8c65b-192">Description: Defines the access.</span></span>

1. <span data-ttu-id="8c65b-193">Optionen: 1-7:</span><span class="sxs-lookup"><span data-stu-id="8c65b-193">Options: 1-7:</span></span>
    - <span data-ttu-id="8c65b-194">1: Lesen</span><span class="sxs-lookup"><span data-stu-id="8c65b-194">1: Read</span></span>
    - <span data-ttu-id="8c65b-195">2: Schreiben</span><span class="sxs-lookup"><span data-stu-id="8c65b-195">2: Write</span></span>
    - <span data-ttu-id="8c65b-196">3: Lese- und Schreibzugriff</span><span class="sxs-lookup"><span data-stu-id="8c65b-196">3: Read and Write</span></span>
    - <span data-ttu-id="8c65b-197">4: Ausführen</span><span class="sxs-lookup"><span data-stu-id="8c65b-197">4: Execute</span></span>
    - <span data-ttu-id="8c65b-198">5: Lesen und Ausführen</span><span class="sxs-lookup"><span data-stu-id="8c65b-198">5: Read and Execute</span></span>
    - <span data-ttu-id="8c65b-199">6: Schreiben und Ausführen</span><span class="sxs-lookup"><span data-stu-id="8c65b-199">6: Write and Execute</span></span>
    - <span data-ttu-id="8c65b-200">7: Lesen und Schreiben und Ausführen</span><span class="sxs-lookup"><span data-stu-id="8c65b-200">7: Read and Write and Execute</span></span>

## <a name="common-removable-storage-access-control-scenarios"></a><span data-ttu-id="8c65b-201">Allgemeine Szenarien für die Speicherzugriffssteuerung für Wechselmedien</span><span class="sxs-lookup"><span data-stu-id="8c65b-201">Common Removable Storage Access Control scenarios</span></span>

<span data-ttu-id="8c65b-202">Um Sie mit Microsoft Defender for Endpoint Removable Storage Access Control vertraut zu machen, haben wir einige gängige Szenarien für Sie 2013 2013 2013 2013 2014 2013 2013 2013 2013 2013 2013 2014 20</span><span class="sxs-lookup"><span data-stu-id="8c65b-202">To help familiarize you with Microsoft Defender for Endpoint Removable Storage Access Control, we have put together some common scenarios for you to follow.</span></span>

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a><span data-ttu-id="8c65b-203">Szenario 1: Verhindern des Schreib- und Ausführungszugriffs für alle, jedoch bestimmte genehmigte USBs zulassen</span><span class="sxs-lookup"><span data-stu-id="8c65b-203">Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs</span></span>

1. <span data-ttu-id="8c65b-204">Erstellen von Gruppen</span><span class="sxs-lookup"><span data-stu-id="8c65b-204">Create groups</span></span>
    1. <span data-ttu-id="8c65b-205">Gruppe 1: Alle Wechseldatenträger und CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="8c65b-205">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="8c65b-206">Ein Beispiel für einen Wechselspeicher und cd/DVD ist: Gruppe **9b28fae8-72f7-4267-a1a5-685f747a7146** im Beispiel [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="8c65b-206">An example of a removable storage and CD/DVD is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="8c65b-207">Gruppe 2: Genehmigte USBs basierend auf Geräteeigenschaften.</span><span class="sxs-lookup"><span data-stu-id="8c65b-207">Group 2: Approved USBs based on device properties.</span></span> <span data-ttu-id="8c65b-208">Ein Beispiel für diesen Verwendungsfall ist: Instanz-ID – Gruppe **65fa649a-a111-4912-9294-fb6337a25038** in der Beispieldatei ["Approved USBs Group.xml".](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="8c65b-208">An example for this use case is: Instance ID – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Approved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8c65b-209">Sie müssen im `&` Wert `&amp;` durch ersetzen.</span><span class="sxs-lookup"><span data-stu-id="8c65b-209">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="8c65b-210">Richtlinie erstellen</span><span class="sxs-lookup"><span data-stu-id="8c65b-210">Create policy</span></span>
    1. <span data-ttu-id="8c65b-211">Richtlinie 1: Blockieren des Schreib- und Ausführungszugriffs, aber Zulassen genehmigter USBs.</span><span class="sxs-lookup"><span data-stu-id="8c65b-211">Policy 1: Block Write and Execute Access but allow approved USBs.</span></span> <span data-ttu-id="8c65b-212">Ein Beispiel für diesen Verwendungsfall ist: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** im [Beispielszenario 1 Schreib-](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) und Ausführungszugriff blockieren, aber genehmigte USBs .xmlzulassen.</span><span class="sxs-lookup"><span data-stu-id="8c65b-212">An example for this use case is: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs .xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="8c65b-213">Richtlinie 2: Überwachen des Schreib- und Ausführungszugriffs auf zulässige USBs.</span><span class="sxs-lookup"><span data-stu-id="8c65b-213">Policy 2: Audit Write and Execute access to allowed USBs.</span></span> <span data-ttu-id="8c65b-214">Ein Beispiel für diesen Use Case ist: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** im [Beispielszenario 1 Überwachung](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) des Schreib- und Ausführungszugriffs auf genehmigte USBs.xml-Datei.</span><span class="sxs-lookup"><span data-stu-id="8c65b-214">An example for this use case is: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** in the sample [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a><span data-ttu-id="8c65b-215">Szenario 2: Überwachen des Schreib- und Ausführungszugriffs auf alle, aber bestimmte nicht genehmigte USBs blockieren</span><span class="sxs-lookup"><span data-stu-id="8c65b-215">Scenario 2: Audit Write and Execute access to all but block specific unapproved USBs</span></span>

1. <span data-ttu-id="8c65b-216">Erstellen von Gruppen</span><span class="sxs-lookup"><span data-stu-id="8c65b-216">Create groups</span></span>
    1. <span data-ttu-id="8c65b-217">Gruppe 1: Alle Wechseldatenträger und CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="8c65b-217">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="8c65b-218">Ein Beispiel für diesen Fall ist: Gruppe **9b28fae8-72f7-4267-a1a5-685f747a7146** im Beispiel [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="8c65b-218">An example for this use case is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="8c65b-219">Gruppe 2: Nicht genehmigte USBs basierend auf Geräteeigenschaften, z. B. Hersteller-ID/Produkt-ID, Anzeigename – Gruppe **65fa649a-a111-4912-9294-fb6337a25038** in der Beispieldatei Nicht genehmigte [USBs Group.xml.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="8c65b-219">Group 2: Unapproved USBs based on device properties, for example, Vendor ID / Product ID, Friendly Name – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Unapproved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="8c65b-220">Sie müssen im `&` Wert `&amp;` durch ersetzen.</span><span class="sxs-lookup"><span data-stu-id="8c65b-220">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="8c65b-221">Richtlinie erstellen</span><span class="sxs-lookup"><span data-stu-id="8c65b-221">Create policy</span></span>
    1. <span data-ttu-id="8c65b-222">Richtlinie 1: Blockieren des Schreib- und Ausführungszugriffs für alle, jedoch für bestimmte nicht genehmigte USBs.</span><span class="sxs-lookup"><span data-stu-id="8c65b-222">Policy 1: Block Write and Execute access to all but block specific unapproved USBs.</span></span> <span data-ttu-id="8c65b-223">Ein Beispiel für diesen Verwendungsfall ist: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** im Beispielszenario 2 Audit Write and Execute access to all but block specific [unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="8c65b-223">An example of this use case is: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** in the sample [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="8c65b-224">Richtlinie 2: Überwachen des Schreib- und Ausführungszugriffs auf andere Personen.</span><span class="sxs-lookup"><span data-stu-id="8c65b-224">Policy 2: Audit Write and Execute access to others.</span></span> <span data-ttu-id="8c65b-225">Ein Beispiel für diesen Verwendungsfall ist: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** im [Beispielszenario 2 Überwachung](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) des Schreib- und Ausführungszugriffs auf others.xmlDatei.</span><span class="sxs-lookup"><span data-stu-id="8c65b-225">An example of this use case is: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** in the sample [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

## <a name="deploying-and-managing-policy-via-group-policy"></a><span data-ttu-id="8c65b-226">Bereitstellen und Verwalten von Richtlinien über Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="8c65b-226">Deploying and managing policy via Group Policy</span></span>

<span data-ttu-id="8c65b-227">Mit der Funktion Wechselmedienzugriffssteuerung können Sie Richtlinien über Gruppenrichtlinien auf Benutzer oder Geräte oder beides anwenden.</span><span class="sxs-lookup"><span data-stu-id="8c65b-227">The Removable Storage Access Control feature enables you to apply policy via Group Policy to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="8c65b-228">Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="8c65b-228">Licensing</span></span>

<span data-ttu-id="8c65b-229">Bevor Sie mit der Wechselmedienzugriffssteuerung beginnen, müssen Sie Ihr [Microsoft 365-Abonnement bestätigen.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)</span><span class="sxs-lookup"><span data-stu-id="8c65b-229">Before you get started with Removable Storage Access Control, you must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="8c65b-230">Für den Zugriff auf und die Verwendung der Wechselmedienzugriffssteuerung müssen Sie Microsoft 365 E5 verwenden.</span><span class="sxs-lookup"><span data-stu-id="8c65b-230">To access and use Removable Storage Access Control, you must have Microsoft 365 E5.</span></span>

### <a name="deploying-policy-via-group-policy"></a><span data-ttu-id="8c65b-231">Bereitstellen von Richtlinien über Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="8c65b-231">Deploying policy via Group Policy</span></span>

1. <span data-ttu-id="8c65b-232">Kombinieren Sie alle Gruppen `<Groups>` `</Groups>` innerhalb einer XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="8c65b-232">Combine all groups within `<Groups>` `</Groups>` into one xml file.</span></span> 

    <span data-ttu-id="8c65b-233">Die folgende Abbildung veranschaulicht das Beispiel von [Szenario 1: Verhindern](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)des Schreib- und Ausführungszugriffs auf alle, erlaubt jedoch bestimmte genehmigte USBs .</span><span class="sxs-lookup"><span data-stu-id="8c65b-233">The following image illustrates the example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="Der Bildschirm mit den Konfigurationseinstellungen, die bestimmte genehmigte USBs auf Geräten zulassen":::
    
2. <span data-ttu-id="8c65b-235">Kombinieren Sie alle Regeln in `<PolicyRules>` `</PolicyRules>` einer XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="8c65b-235">Combine all rules within `<PolicyRules>` `</PolicyRules>` into one xml file.</span></span> 

    <span data-ttu-id="8c65b-236">Wenn Sie einen bestimmten Benutzer einschränken möchten, verwenden Sie die SID-Eigenschaft in den Eintrag.</span><span class="sxs-lookup"><span data-stu-id="8c65b-236">If you want to restrict a specific user, then use SID property into the Entry.</span></span> <span data-ttu-id="8c65b-237">Wenn in der Richtlinie Eintrag keine SID vorhanden ist, wird der Eintrag auf alle Anmeldeinstanzen für den Computer angewendet.</span><span class="sxs-lookup"><span data-stu-id="8c65b-237">If there is no SID in the policy Entry, the Entry will be applied to everyone login instance for the machine.</span></span>
    
    <span data-ttu-id="8c65b-238">Die folgende Abbildung veranschaulicht die Verwendung der SID-Eigenschaft und ein Beispiel für [Szenario 1: Verhindern](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)des Schreib- und Ausführungszugriffs auf alle, erlaubt jedoch bestimmte genehmigte USBs .</span><span class="sxs-lookup"><span data-stu-id="8c65b-238">The following image illustrates the usage of SID property, and an example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="Der Bildschirm mit einem Code, der die Verwendung des SID-Eigenschaftsattributs angibt":::

3. <span data-ttu-id="8c65b-240">Speichern Sie sowohl Regel- als auch Gruppen-XML-Dateien im Netzwerkfreigabeordner, und legen Sie den Pfad des Netzwerkfreigabeordners in die Gruppenrichtlinieneinstellung ein: Computerkonfiguration **-> Administrative Vorlagen -> Windows-Komponenten -> Microsoft Defender Antivirus -> Gerätesteuerung: 'Gerätesteuerungsrichtliniengruppen definieren'** und 'Richtlinienregeln für Gerätesteuerung definieren' .</span><span class="sxs-lookup"><span data-stu-id="8c65b-240">Save both rule and group XML files on network share folder and put network share folder path into the Group Policy setting: **Computer Configuration -> Administrative Templates -> Windows Components -> Microsoft Defender Antivirus -> Device Control: ‘Define device control policy groups’ and ‘Define device control policy rules’**.</span></span>

    - <span data-ttu-id="8c65b-241">Der Zielcomputer muss auf die Netzwerkfreigabe zugreifen können, damit die Richtlinie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8c65b-241">The target machine must be able to access the network share to have the policy.</span></span> <span data-ttu-id="8c65b-242">Sobald die Richtlinie jedoch gelesen wurde, ist die Netzwerkfreigabeverbindung auch nach dem Neustart des Computers nicht mehr erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8c65b-242">However, once the policy is read, the network share connection is no longer required, even after machine reboot.</span></span>

    :::image type="content" source="images/device-control.png" alt-text="Bildschirm &quot;Gerätesteuerung&quot;":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a><span data-ttu-id="8c65b-244">Bereitstellen und Verwalten von Richtlinien über Intune OMA-URI</span><span class="sxs-lookup"><span data-stu-id="8c65b-244">Deploying and managing policy via Intune OMA-URI</span></span>

<span data-ttu-id="8c65b-245">Mit der Funktion Wechselmedienzugriffssteuerung können Sie Richtlinien über OMA-URI entweder auf Benutzer oder Geräte oder beides anwenden.</span><span class="sxs-lookup"><span data-stu-id="8c65b-245">The Removable Storage Access Control feature enables you to apply policy via OMA-URI to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="8c65b-246">Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="8c65b-246">Licensing</span></span>

<span data-ttu-id="8c65b-247">Bevor Sie mit der Wechselmedienzugriffssteuerung beginnen, müssen Sie Ihr [Microsoft 365-Abonnement bestätigen.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)</span><span class="sxs-lookup"><span data-stu-id="8c65b-247">Before you get started with Removable Storage Access Control, you  must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="8c65b-248">Für den Zugriff auf und die Verwendung der Wechselmedienzugriffssteuerung müssen Sie über Microsoft 365 E3 verfügen.</span><span class="sxs-lookup"><span data-stu-id="8c65b-248">To access and use Removable Storage Access Control, you must have Microsoft 365 E3.</span></span>

### <a name="permission"></a><span data-ttu-id="8c65b-249">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="8c65b-249">Permission</span></span>

<span data-ttu-id="8c65b-250">Für die Richtlinienbereitstellung in Intune muss das Konto über Berechtigungen zum Erstellen, Bearbeiten, Aktualisieren oder Löschen von Gerätekonfigurationsprofilen verfügen.</span><span class="sxs-lookup"><span data-stu-id="8c65b-250">For policy deployment in Intune, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="8c65b-251">Sie können benutzerdefinierte Rollen erstellen oder eine der integrierten Rollen mit diesen Berechtigungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="8c65b-251">You can create custom roles or use any of the built-in roles with these permissions.</span></span>

- <span data-ttu-id="8c65b-252">Rolle "Richtlinien- und Profil-Manager"</span><span class="sxs-lookup"><span data-stu-id="8c65b-252">Policy and profile Manager role</span></span>
- <span data-ttu-id="8c65b-253">Benutzerdefinierte Rolle mit Berechtigungen zum Erstellen/Bearbeiten/Aktualisieren/Lesen/Löschen/Anzeigen von Berichten, die für Gerätekonfigurationsprofile aktiviert sind</span><span class="sxs-lookup"><span data-stu-id="8c65b-253">Custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="8c65b-254">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="8c65b-254">Global administrator</span></span>

### <a name="deploying-policy-via-oma-uri"></a><span data-ttu-id="8c65b-255">Bereitstellen von Richtlinien über OMA-URI</span><span class="sxs-lookup"><span data-stu-id="8c65b-255">Deploying policy via OMA-URI</span></span>

<span data-ttu-id="8c65b-256">**Microsoft Endpoint Manager admin center ( https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span><span class="sxs-lookup"><span data-stu-id="8c65b-256">**Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span></span>

1. <span data-ttu-id="8c65b-257">Erstellen Sie für jede Gruppe eine OMA-URI-Regel:</span><span class="sxs-lookup"><span data-stu-id="8c65b-257">For each Group, create an OMA-URI rule:</span></span>
    - <span data-ttu-id="8c65b-258">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="8c65b-258">OMA-URI:</span></span>

      <span data-ttu-id="8c65b-259">/Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="8c65b-259">/Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span></span>

      <span data-ttu-id="8c65b-260">Für jeden **Wechselspeicher und eine CD/DVD-Gruppe** im Beispiel muss der Link z. B.:</span><span class="sxs-lookup"><span data-stu-id="8c65b-260">For example, for **any removable storage and CD/DVD** group in the sample, the link must be:</span></span>

      <span data-ttu-id="8c65b-261">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="8c65b-261">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span></span>

    - <span data-ttu-id="8c65b-262">Datentyp: Zeichenfolge (XML-Datei)</span><span class="sxs-lookup"><span data-stu-id="8c65b-262">Data Type: String (XML file)</span></span>
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="Die XML-Datei für den DATENTYP STRING":::

2. <span data-ttu-id="8c65b-264">Erstellen Sie für jede Richtlinie auch einen OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="8c65b-264">For each policy, also create an OMA-URI:</span></span>

    - <span data-ttu-id="8c65b-265">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="8c65b-265">OMA-URI:</span></span>

      <span data-ttu-id="8c65b-266">/Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBF68E1%7d/RuleData</span><span class="sxs-lookup"><span data-stu-id="8c65b-266">/Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span></span>

      <span data-ttu-id="8c65b-267">Beispielsweise muss der Link für die **Regel Schreib-** und Ausführungszugriff blockieren, aber genehmigte USBs im Beispiel zulassen:</span><span class="sxs-lookup"><span data-stu-id="8c65b-267">For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be:</span></span> 

      <span data-ttu-id="8c65b-268">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span><span class="sxs-lookup"><span data-stu-id="8c65b-268">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span></span>

    - <span data-ttu-id="8c65b-269">Datentyp: Zeichenfolge (XML-Datei)</span><span class="sxs-lookup"><span data-stu-id="8c65b-269">Data Type: String (XML file)</span></span>

      :::image type="content" source="images/xml-data-type-string-2.png" alt-text="Anzeigen der XML-Datei für den DATENTYP STRING":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a><span data-ttu-id="8c65b-271">Bereitstellen und Verwalten von Richtlinien mithilfe der Intune-Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="8c65b-271">Deploying and managing policy by using Intune user interface</span></span>

<span data-ttu-id="8c65b-272">Diese Funktion ist noch nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8c65b-272">This capability is not yet available.</span></span> 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="8c65b-273">Anzeigen von Daten der Gerätesteuerung für wechselbare Speicherzugriffssteuerung in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8c65b-273">View Device Control Removable Storage Access Control data in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="8c65b-274">Das Microsoft 365-Sicherheitsportal zeigt wechselbaren Speicher an, der von der Gerätesteuerung Wechselmedienzugriffssteuerung blockiert wurde.</span><span class="sxs-lookup"><span data-stu-id="8c65b-274">The Microsoft 365 security portal shows removable storage blocked by the Device Control Removable Storage Access Control.</span></span> <span data-ttu-id="8c65b-275">Für den Zugriff auf die Microsoft 365-Sicherheit müssen Sie über das folgende Abonnement verfügen:</span><span class="sxs-lookup"><span data-stu-id="8c65b-275">To access the Microsoft 365 security, you must have the following subscription:</span></span>

- <span data-ttu-id="8c65b-276">Microsoft 365 für E5-Berichte</span><span class="sxs-lookup"><span data-stu-id="8c65b-276">Microsoft 365 for E5 reporting</span></span>

```
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

:::image type="content" source="images/block-removable-storage.png" alt-text="Der Bildschirm mit der Blockierung des Wechselspeichers":::
