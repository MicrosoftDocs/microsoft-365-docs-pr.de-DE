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
ms.openlocfilehash: fba74990d8e4465f957acda83e66e1dc43a317e8
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841186"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a><span data-ttu-id="c3c9b-104">Microsoft Defender für Endpunkt-Gerätesteuerung – Wechselmedien Storage Zugriffssteuerung</span><span class="sxs-lookup"><span data-stu-id="c3c9b-104">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="c3c9b-105">Microsoft Defender für Endpunkt-Gerätesteuerung – Wechselmedien Storage Zugriffssteuerung ermöglicht Ihnen die folgende Aufgabe:</span><span class="sxs-lookup"><span data-stu-id="c3c9b-105">Microsoft Defender for Endpoint Device Control Removable Storage Access Control enables you to do the following task:</span></span>
- <span data-ttu-id="c3c9b-106">Überwachen, Zulassen oder Verhindern des Lese-, Schreib- oder Ausführungszugriffs auf Wechselmedien mit oder ohne Ausschluss</span><span class="sxs-lookup"><span data-stu-id="c3c9b-106">auditing, allowing or preventing the read, write or execute access to removable storage with or without exclusion</span></span>

|<span data-ttu-id="c3c9b-107">Privileg</span><span class="sxs-lookup"><span data-stu-id="c3c9b-107">Privilege</span></span> |<span data-ttu-id="c3c9b-108">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="c3c9b-108">Permission</span></span>  |
|---------|---------|
|<span data-ttu-id="c3c9b-109">Zugriff</span><span class="sxs-lookup"><span data-stu-id="c3c9b-109">Access</span></span>    |  <span data-ttu-id="c3c9b-110">Lese-/Schreib-/Ausführungszugriff</span><span class="sxs-lookup"><span data-stu-id="c3c9b-110">Read, Write, Execute</span></span>       |
|<span data-ttu-id="c3c9b-111">Aktionsmodus</span><span class="sxs-lookup"><span data-stu-id="c3c9b-111">Action Mode</span></span>    |    <span data-ttu-id="c3c9b-112">Überwachen, Zulassen, Verhindern</span><span class="sxs-lookup"><span data-stu-id="c3c9b-112">Audit, Allow, Prevent</span></span>     |
|<span data-ttu-id="c3c9b-113">CSP-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="c3c9b-113">CSP Support</span></span>   |   <span data-ttu-id="c3c9b-114">Ja</span><span class="sxs-lookup"><span data-stu-id="c3c9b-114">Yes</span></span>      |
|<span data-ttu-id="c3c9b-115">GPO-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="c3c9b-115">GPO Support</span></span>    |   <span data-ttu-id="c3c9b-116">Ja</span><span class="sxs-lookup"><span data-stu-id="c3c9b-116">Yes</span></span>      |
|<span data-ttu-id="c3c9b-117">Benutzerbasierter Support</span><span class="sxs-lookup"><span data-stu-id="c3c9b-117">User-based Support</span></span>     |   <span data-ttu-id="c3c9b-118">Ja</span><span class="sxs-lookup"><span data-stu-id="c3c9b-118">Yes</span></span>      |
|<span data-ttu-id="c3c9b-119">Computerbasierter Support</span><span class="sxs-lookup"><span data-stu-id="c3c9b-119">Machine-based Support</span></span>    |    <span data-ttu-id="c3c9b-120">Ja</span><span class="sxs-lookup"><span data-stu-id="c3c9b-120">Yes</span></span>     |

## <a name="prepare-your-endpoints"></a><span data-ttu-id="c3c9b-121">Vorbereiten der Endpunkte</span><span class="sxs-lookup"><span data-stu-id="c3c9b-121">Prepare your endpoints</span></span>

<span data-ttu-id="c3c9b-122">Bereitstellen von Wechseldatenträgern Storage Zugriffssteuerung auf Windows 10 Geräten mit Der Clientversion **4.18.2103.3 oder höher** für Antischadsoftware.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-122">Deploy Removable Storage Access Control on Windows 10 devices that have Anti-malware Client Version **4.18.2103.3 or later**.</span></span>
1. <span data-ttu-id="c3c9b-123">**4.18.2104 oder höher:** Hinzufügen von SerialNumberId, VID_PID, Dateipfad-basierter GPO-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="c3c9b-123">**4.18.2104 or later**: Add SerialNumberId, VID_PID, filepath-based GPO support</span></span>

2. <span data-ttu-id="c3c9b-124">**4.18.2105 oder höher:** Hinzufügen von Platzhalterunterstützung für HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, die Kombination aus einem bestimmten Benutzer auf einem bestimmten Computer, entfernender SSD (sanDisk Extreme SSD)/USB Attached SCSI (UAS)-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="c3c9b-124">**4.18.2105 or later**: Add Wildcard support for HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, the combination of specific user on specific machine, removeable SSD (a SanDisk Extreme SSD)/USB Attached SCSI (UAS) support</span></span>

:::image type="content" source="images/powershell.png" alt-text="Die PowerShell-Schnittstelle":::

## <a name="policy-properties"></a><span data-ttu-id="c3c9b-126">Richtlinieneigenschaften</span><span class="sxs-lookup"><span data-stu-id="c3c9b-126">Policy properties</span></span>

<span data-ttu-id="c3c9b-127">Sie können die folgenden Eigenschaften verwenden, um eine Wechselmediengruppe zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="c3c9b-127">You can use the following properties to create a removable storage group:</span></span>

<span data-ttu-id="c3c9b-128">**Eigenschaftenname: Gruppen-ID**</span><span class="sxs-lookup"><span data-stu-id="c3c9b-128">**Property name: Group ID**</span></span>

1. <span data-ttu-id="c3c9b-129">Beschreibung: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), eine eindeutige ID, stellt die Gruppe dar und wird in der Richtlinie verwendet.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-129">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the group and will be used in the policy.</span></span>

<span data-ttu-id="c3c9b-130">**Eigenschaftenname: DescriptorIdList**</span><span class="sxs-lookup"><span data-stu-id="c3c9b-130">**Property name: DescriptorIdList**</span></span>

1. <span data-ttu-id="c3c9b-131">Beschreibung: Auflisten der Geräteeigenschaften, die Sie in der Gruppe abdecken möchten.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-131">Description: List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="c3c9b-132">Listet die Geräteeigenschaften auf, die Sie in der Gruppe abdecken möchten.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-132">List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="c3c9b-133">Weitere Informationen zu jeder Geräteeigenschaft finden Sie weiter oben im Abschnitt **"Geräteeigenschaften".**</span><span class="sxs-lookup"><span data-stu-id="c3c9b-133">For each device property, see **Device Properties** section above for more detail.</span></span>

1. <span data-ttu-id="c3c9b-134">Optionen:</span><span class="sxs-lookup"><span data-stu-id="c3c9b-134">Options:</span></span>
    - <span data-ttu-id="c3c9b-135">Primäre ID</span><span class="sxs-lookup"><span data-stu-id="c3c9b-135">Primary ID</span></span>
        - <span data-ttu-id="c3c9b-136">RemovableMediaDevices</span><span class="sxs-lookup"><span data-stu-id="c3c9b-136">RemovableMediaDevices</span></span>
        - <span data-ttu-id="c3c9b-137">CdRomDevices</span><span class="sxs-lookup"><span data-stu-id="c3c9b-137">CdRomDevices</span></span>
    - <span data-ttu-id="c3c9b-138">Deviceid</span><span class="sxs-lookup"><span data-stu-id="c3c9b-138">DeviceId</span></span>
    - <span data-ttu-id="c3c9b-139">HardwareId</span><span class="sxs-lookup"><span data-stu-id="c3c9b-139">HardwareId</span></span>
    - <span data-ttu-id="c3c9b-140">InstancePathId: InstancePathId ist eine Zeichenfolge, die das Gerät im System eindeutig identifiziert, z. B. USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-140">InstancePathId: InstancePathId is a string that uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span></span> <span data-ttu-id="c3c9b-141">Die Zahl am Ende (z. **B.&0)** stellt den verfügbaren Steckplatz dar und kann sich von Gerät zu Gerät ändern.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-141">The number at the end (for example **&0**) represents the available slot and may change from device to device.</span></span> <span data-ttu-id="c3c9b-142">Um optimale Ergebnisse zu erzielen, verwenden Sie am Ende einen Platzhalter.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-142">For best results, use a wildcard at the end.</span></span> <span data-ttu-id="c3c9b-143">Beispiel: USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span><span class="sxs-lookup"><span data-stu-id="c3c9b-143">For example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span></span>
    - <span data-ttu-id="c3c9b-144">FriendlyNameId</span><span class="sxs-lookup"><span data-stu-id="c3c9b-144">FriendlyNameId</span></span>
    - <span data-ttu-id="c3c9b-145">SerialNumberId</span><span class="sxs-lookup"><span data-stu-id="c3c9b-145">SerialNumberId</span></span>
    - <span data-ttu-id="c3c9b-146">Vid</span><span class="sxs-lookup"><span data-stu-id="c3c9b-146">VID</span></span>
    - <span data-ttu-id="c3c9b-147">Pid</span><span class="sxs-lookup"><span data-stu-id="c3c9b-147">PID</span></span>
    - <span data-ttu-id="c3c9b-148">VID_PID</span><span class="sxs-lookup"><span data-stu-id="c3c9b-148">VID_PID</span></span>
        - <span data-ttu-id="c3c9b-149">0751_55E0: Übereinstimmung mit diesem genauen VID/PID-Paar</span><span class="sxs-lookup"><span data-stu-id="c3c9b-149">0751_55E0: match this exact VID/PID pair</span></span>
        - <span data-ttu-id="c3c9b-150">_55E0: Abgleichen von Medien mit PID=55E0</span><span class="sxs-lookup"><span data-stu-id="c3c9b-150">_55E0: match any media with PID=55E0</span></span>
        - <span data-ttu-id="c3c9b-151">0751_: Alle Medien mit VID=0751 abgleichen</span><span class="sxs-lookup"><span data-stu-id="c3c9b-151">0751_: match any media with VID=0751</span></span>
        
<span data-ttu-id="c3c9b-152">**Eigenschaftenname: MatchType**</span><span class="sxs-lookup"><span data-stu-id="c3c9b-152">**Property name: MatchType**</span></span> 

1. <span data-ttu-id="c3c9b-153">Beschreibung: Wenn mehrere Geräteeigenschaften in der DescriptorIDList verwendet werden, definiert MatchType die Beziehung.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-153">Description: When there are multiple device properties being used in the DescriptorIDList, MatchType defines the relationship.</span></span>

1. <span data-ttu-id="c3c9b-154">Optionen:</span><span class="sxs-lookup"><span data-stu-id="c3c9b-154">Options:</span></span>
    - <span data-ttu-id="c3c9b-155">MatchAll: Alle Attribute unter der DescriptorIdList sind **"And"-Beziehung;** Wenn der Administrator beispielsweise DeviceID und InstancePathID platziert, überprüft das System für jeden angeschlossenen USB-Stick, ob der USB beide Werte erfüllt.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-155">MatchAll: Any attributes under the DescriptorIdList will be **And** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will check to see whether the USB meets both values.</span></span>

    - <span data-ttu-id="c3c9b-156">MatchAny: Die Attribute unter "DescriptorIdList" sind **"Or".** Wenn der Administrator beispielsweise DeviceID und InstancePathID platziert, führt das System für jeden angeschlossenen USB-Stick die Erzwingung aus, solange der USB-Stick entweder über einen identischen **DeviceID-** oder **InstanceID-Wert** verfügt.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-156">MatchAny: The attributes under the DescriptorIdList will be **Or** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will do the enforcement as long as the USB has either an identical **DeviceID** or **InstanceID** value.</span></span>

<span data-ttu-id="c3c9b-157">Es folgen die Eigenschaften der Zugriffssteuerungsrichtlinie:</span><span class="sxs-lookup"><span data-stu-id="c3c9b-157">Following are the access control policy properties:</span></span>

<span data-ttu-id="c3c9b-158">**Eigenschaftenname: PolicyRuleId**</span><span class="sxs-lookup"><span data-stu-id="c3c9b-158">**Property name: PolicyRuleId**</span></span>

1. <span data-ttu-id="c3c9b-159">Beschreibung: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), eine eindeutige ID, stellt die Richtlinie dar und wird in der Berichterstellung und Problembehandlung verwendet.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-159">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the policy and will be used in the reporting and troubleshooting.</span></span>

<span data-ttu-id="c3c9b-160">**Eigenschaftenname: IncludedIdList**</span><span class="sxs-lookup"><span data-stu-id="c3c9b-160">**Property name: IncludedIdList**</span></span>

1. <span data-ttu-id="c3c9b-161">Beschreibung: Die Gruppen, auf die die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-161">Description: The group(s) that the policy will be applied to.</span></span> <span data-ttu-id="c3c9b-162">Wenn mehrere Gruppen hinzugefügt werden, wird die Richtlinie auf alle Medien in allen diesen Gruppen angewendet.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-162">If multiple groups are added, the policy will be applied to any media in all those groups.</span></span>

1. <span data-ttu-id="c3c9b-163">Optionen: Die Gruppen-ID/GUID muss in dieser Instanz verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-163">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="c3c9b-164">Das folgende Beispiel zeigt die Verwendung von GroupID:</span><span class="sxs-lookup"><span data-stu-id="c3c9b-164">The following example shows the usage of GroupID:</span></span>

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

<span data-ttu-id="c3c9b-165">**Eigenschaftenname: ExcludedIDList**</span><span class="sxs-lookup"><span data-stu-id="c3c9b-165">**Property name: ExcludedIDList**</span></span>

1. <span data-ttu-id="c3c9b-166">Beschreibung: Die Gruppen, auf die die Richtlinie nicht angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-166">Description: The group(s) that the policy will not be applied to.</span></span>
1. <span data-ttu-id="c3c9b-167">Optionen: Die Gruppen-ID/GUID muss in dieser Instanz verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-167">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="c3c9b-168">**Eigenschaftenname: Eintrags-ID**</span><span class="sxs-lookup"><span data-stu-id="c3c9b-168">**Property name: Entry ID**</span></span>

1. <span data-ttu-id="c3c9b-169">Beschreibung: One PolicyRule kann mehrere Einträge haben; Jeder Eintrag mit einer eindeutigen GUID teilt der Gerätesteuerung eine Einschränkung mit.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-169">Description: One PolicyRule can have multiple entries; each entry with a unique GUID tells Device Control one restriction.</span></span>

<span data-ttu-id="c3c9b-170">**Eigenschaftenname: Typ**</span><span class="sxs-lookup"><span data-stu-id="c3c9b-170">**Property name: Type**</span></span>

1. <span data-ttu-id="c3c9b-171">Beschreibung: Definiert die Aktion für die Wechselmediengruppen in IncludedIDList.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-171">Description: Defines the action for the removable storage groups in IncludedIDList.</span></span>
    - <span data-ttu-id="c3c9b-172">Erzwingung: Zulassen oder Verweigern</span><span class="sxs-lookup"><span data-stu-id="c3c9b-172">Enforcement: Allow or Deny</span></span>
    - <span data-ttu-id="c3c9b-173">Audit: AuditAllowed oder AuditDenied</span><span class="sxs-lookup"><span data-stu-id="c3c9b-173">Audit: AuditAllowed or AuditDenied</span></span> 
1. <span data-ttu-id="c3c9b-174">Optionen:</span><span class="sxs-lookup"><span data-stu-id="c3c9b-174">Options:</span></span>
    - <span data-ttu-id="c3c9b-175">Zulassen</span><span class="sxs-lookup"><span data-stu-id="c3c9b-175">Allow</span></span>
    - <span data-ttu-id="c3c9b-176">Verweigern</span><span class="sxs-lookup"><span data-stu-id="c3c9b-176">Deny</span></span>
    - <span data-ttu-id="c3c9b-177">AuditAllowed: Definiert Benachrichtigung und Ereignis, wenn der Zugriff zulässig ist</span><span class="sxs-lookup"><span data-stu-id="c3c9b-177">AuditAllowed: Defines notification and event when access is allowed</span></span>
    - <span data-ttu-id="c3c9b-178">AuditDenied: Definiert Benachrichtigung und Ereignis, wenn der Zugriff verweigert wird; muss mit **der Verweigerungseingabe zusammenarbeiten.**</span><span class="sxs-lookup"><span data-stu-id="c3c9b-178">AuditDenied: Defines notification and event when access is denied; has to work together with **Deny** entry.</span></span>

<span data-ttu-id="c3c9b-179">Wenn es Konflikttypen für dieselben Medien gibt, wendet das System den ersten in der Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-179">When there are conflict types for the same media, the system will apply the first one in the policy.</span></span> <span data-ttu-id="c3c9b-180">Ein Beispiel für einen Konflikttyp ist **Allow** and **Deny**.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-180">An example of a conflict type is **Allow** and **Deny**.</span></span>

<span data-ttu-id="c3c9b-181">**Eigenschaftenname: Optionen**</span><span class="sxs-lookup"><span data-stu-id="c3c9b-181">**Property name: Options**</span></span>

1. <span data-ttu-id="c3c9b-182">Beschreibung: Definiert, ob eine Benachrichtigung angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-182">Description: Defines whether to display notification or not.</span></span>

   :::image type="content" source="images/device-status.png" alt-text="Der Bildschirm, auf dem der Status des Geräts angezeigt werden kann":::

1. <span data-ttu-id="c3c9b-184">Optionen: 0-4.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-184">Options: 0-4.</span></span> <span data-ttu-id="c3c9b-185">Wenn "Zulassen" oder "Verweigern" ausgewählt ist:</span><span class="sxs-lookup"><span data-stu-id="c3c9b-185">When Type Allow or Deny is selected:</span></span>

   - <span data-ttu-id="c3c9b-186">0: nothing</span><span class="sxs-lookup"><span data-stu-id="c3c9b-186">0: nothing</span></span>
   - <span data-ttu-id="c3c9b-187">4: Deaktivieren Sie **"AuditAllowed"** und **"AuditDenied"** für diesen Eintrag.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-187">4: disable **AuditAllowed** and **AuditDenied** for this Entry.</span></span> <span data-ttu-id="c3c9b-188">Selbst wenn **"Blockieren"** erfolgt und die **"AuditDenied"-Einstellung** konfiguriert ist, zeigt das System keine Benachrichtigung an.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-188">Even if **Block** happens and the **AuditDenied** is setting configured, the system will not show notification.</span></span>

   <span data-ttu-id="c3c9b-189">Wenn **"AuditAllowed"** oder **"AuditDenied"** ausgewählt ist:</span><span class="sxs-lookup"><span data-stu-id="c3c9b-189">When Type **AuditAllowed** or **AuditDenied** is selected:</span></span>

   - <span data-ttu-id="c3c9b-190">0: nothing</span><span class="sxs-lookup"><span data-stu-id="c3c9b-190">0: nothing</span></span>
   - <span data-ttu-id="c3c9b-191">1: Benachrichtigung anzeigen</span><span class="sxs-lookup"><span data-stu-id="c3c9b-191">1: show notification</span></span>
   - <span data-ttu-id="c3c9b-192">2: Send-Ereignis</span><span class="sxs-lookup"><span data-stu-id="c3c9b-192">2: send event</span></span>
   - <span data-ttu-id="c3c9b-193">3: Benachrichtigungs- und Sendeereignis anzeigen</span><span class="sxs-lookup"><span data-stu-id="c3c9b-193">3: show notification and send event</span></span>

<span data-ttu-id="c3c9b-194">**Eigenschaftenname: AccessMask**</span><span class="sxs-lookup"><span data-stu-id="c3c9b-194">**Property name: AccessMask**</span></span>

1. <span data-ttu-id="c3c9b-195">Beschreibung: Definiert den Zugriff.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-195">Description: Defines the access.</span></span>

1. <span data-ttu-id="c3c9b-196">Optionen: 1-7:</span><span class="sxs-lookup"><span data-stu-id="c3c9b-196">Options: 1-7:</span></span>
    - <span data-ttu-id="c3c9b-197">1: Lesen</span><span class="sxs-lookup"><span data-stu-id="c3c9b-197">1: Read</span></span>
    - <span data-ttu-id="c3c9b-198">2: Schreiben</span><span class="sxs-lookup"><span data-stu-id="c3c9b-198">2: Write</span></span>
    - <span data-ttu-id="c3c9b-199">3: Lesen und Schreiben</span><span class="sxs-lookup"><span data-stu-id="c3c9b-199">3: Read and Write</span></span>
    - <span data-ttu-id="c3c9b-200">4: Ausführen</span><span class="sxs-lookup"><span data-stu-id="c3c9b-200">4: Execute</span></span>
    - <span data-ttu-id="c3c9b-201">5: Lesen und Ausführen</span><span class="sxs-lookup"><span data-stu-id="c3c9b-201">5: Read and Execute</span></span>
    - <span data-ttu-id="c3c9b-202">6: Schreiben und Ausführen</span><span class="sxs-lookup"><span data-stu-id="c3c9b-202">6: Write and Execute</span></span>
    - <span data-ttu-id="c3c9b-203">7: Lesen und Schreiben und Ausführen</span><span class="sxs-lookup"><span data-stu-id="c3c9b-203">7: Read and Write and Execute</span></span>

## <a name="common-removable-storage-access-control-scenarios"></a><span data-ttu-id="c3c9b-204">Allgemeine Szenarien für die Zugriffssteuerung für wechselbare Storage</span><span class="sxs-lookup"><span data-stu-id="c3c9b-204">Common Removable Storage Access Control scenarios</span></span>

<span data-ttu-id="c3c9b-205">Um Sie mit Microsoft Defender für Endpunkt-Wechselmedien Storage Zugriffssteuerung vertraut zu machen, haben wir einige häufige Szenarien für Sie zusammengestellt.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-205">To help familiarize you with Microsoft Defender for Endpoint Removable Storage Access Control, we have put together some common scenarios for you to follow.</span></span>

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a><span data-ttu-id="c3c9b-206">Szenario 1: Verhindern des Schreib- und Ausführungszugriffs auf alle genehmigten USBs, aber zulassen</span><span class="sxs-lookup"><span data-stu-id="c3c9b-206">Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs</span></span>

1. <span data-ttu-id="c3c9b-207">Erstellen von Gruppen</span><span class="sxs-lookup"><span data-stu-id="c3c9b-207">Create groups</span></span>
    1. <span data-ttu-id="c3c9b-208">Gruppe 1: Wechselmedien und CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-208">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="c3c9b-209">Ein Beispiel für einen Wechselmedien und eine CD/DVD ist: Gruppe **9b28fae8-72f7-4267-a1a5-685f747a7146** in der Beispieldatei ["Any Removable Storage" und "CD-DVD Group.xml".](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="c3c9b-209">An example of a removable storage and CD/DVD is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="c3c9b-210">Gruppe 2: Genehmigte USBs basierend auf Geräteeigenschaften.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-210">Group 2: Approved USBs based on device properties.</span></span> <span data-ttu-id="c3c9b-211">Ein Beispiel für diesen Anwendungsfall ist: Instanz-ID – Gruppe **65fa649a-a111-4912-9294-fb6337a25038** in der Beispieldatei [für genehmigte USBs Group.xml.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="c3c9b-211">An example for this use case is: Instance ID – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Approved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c3c9b-212">Sie müssen `&` `&amp;` im Wert ersetzen.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-212">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="c3c9b-213">Richtlinie erstellen</span><span class="sxs-lookup"><span data-stu-id="c3c9b-213">Create policy</span></span>
    1. <span data-ttu-id="c3c9b-214">Richtlinie 1: Schreib- und Ausführungszugriff blockieren, aber genehmigte USBs zulassen.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-214">Policy 1: Block Write and Execute Access but allow approved USBs.</span></span> <span data-ttu-id="c3c9b-215">Ein Beispiel für diesen Anwendungsfall ist: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs .xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-215">An example for this use case is: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs .xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="c3c9b-216">Richtlinie 2: Überwachen des Schreib- und Ausführungszugriffs auf zulässige USBs.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-216">Policy 2: Audit Write and Execute access to allowed USBs.</span></span> <span data-ttu-id="c3c9b-217">Ein Beispiel für diesen Anwendungsfall ist: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** im [Beispielszenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-217">An example for this use case is: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** in the sample [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a><span data-ttu-id="c3c9b-218">Szenario 2: Überwachen des Schreib- und Ausführungszugriffs auf alle nicht genehmigten USBs außer Blockieren bestimmter nicht genehmigter USBs</span><span class="sxs-lookup"><span data-stu-id="c3c9b-218">Scenario 2: Audit Write and Execute access to all but block specific unapproved USBs</span></span>

1. <span data-ttu-id="c3c9b-219">Erstellen von Gruppen</span><span class="sxs-lookup"><span data-stu-id="c3c9b-219">Create groups</span></span>
    1. <span data-ttu-id="c3c9b-220">Gruppe 1: Wechselmedien und CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-220">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="c3c9b-221">Ein Beispiel für diesen Anwendungsfall ist: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-221">An example for this use case is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="c3c9b-222">Gruppe 2: Nicht genehmigte USBs basierend auf Geräteeigenschaften, z. B. Anbieter-ID/Produkt-ID, Anzeigename – Gruppe **65fa649a-a111-4912-9294-fb6337a25038** in der Beispieldatei "Nicht genehmigte [USBs Group.xml".](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="c3c9b-222">Group 2: Unapproved USBs based on device properties, for example, Vendor ID / Product ID, Friendly Name – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Unapproved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="c3c9b-223">Sie müssen `&` `&amp;` im Wert ersetzen.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-223">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="c3c9b-224">Richtlinie erstellen</span><span class="sxs-lookup"><span data-stu-id="c3c9b-224">Create policy</span></span>
    1. <span data-ttu-id="c3c9b-225">Richtlinie 1: Schreib- und Ausführungszugriff auf alle nicht genehmigten USBs blockieren.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-225">Policy 1: Block Write and Execute access to all but block specific unapproved USBs.</span></span> <span data-ttu-id="c3c9b-226">Ein Beispiel für diesen Anwendungsfall ist: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** im [Beispielszenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-226">An example of this use case is: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** in the sample [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="c3c9b-227">Richtlinie 2: Überwachen des Schreib- und Ausführungszugriffs auf andere Personen.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-227">Policy 2: Audit Write and Execute access to others.</span></span> <span data-ttu-id="c3c9b-228">Ein Beispiel für diesen Anwendungsfall ist: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** im [Beispielszenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-228">An example of this use case is: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** in the sample [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

## <a name="deploying-and-managing-policy-via-group-policy"></a><span data-ttu-id="c3c9b-229">Bereitstellen und Verwalten von Richtlinien über Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="c3c9b-229">Deploying and managing policy via Group Policy</span></span>

<span data-ttu-id="c3c9b-230">Mit dem Feature "Wechselbare Storage Zugriffssteuerung" können Sie Richtlinien über Gruppenrichtlinien entweder auf Benutzer oder Geräte oder auf beides anwenden.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-230">The Removable Storage Access Control feature enables you to apply policy via Group Policy to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="c3c9b-231">Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="c3c9b-231">Licensing</span></span>

<span data-ttu-id="c3c9b-232">Bevor Sie mit wechselbaren Storage Zugriffssteuerung beginnen, müssen Sie Ihr [Microsoft 365 Abonnement](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)bestätigen.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-232">Before you get started with Removable Storage Access Control, you must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="c3c9b-233">Um auf wechselbare Storage Zugriffssteuerung zuzugreifen und sie zu verwenden, benötigen Sie Microsoft 365 E3 oder Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-233">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="deploying-policy-via-group-policy"></a><span data-ttu-id="c3c9b-234">Bereitstellen von Richtlinien über Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="c3c9b-234">Deploying policy via Group Policy</span></span>

1. <span data-ttu-id="c3c9b-235">Kombinieren Sie alle Darin enthaltenen Gruppen `<Groups>` `</Groups>` in einer XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-235">Combine all groups within `<Groups>` `</Groups>` into one xml file.</span></span> 

    <span data-ttu-id="c3c9b-236">Die folgende Abbildung veranschaulicht das Beispiel von [Szenario 1: Verhindern des Schreib- und Ausführungszugriffs auf alle genehmigten USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)außer zulassen.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-236">The following image illustrates the example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="Der Bildschirm mit den Konfigurationseinstellungen, die bestimmte genehmigte USBs auf Geräten zulassen":::
    
2. <span data-ttu-id="c3c9b-238">Kombinieren Sie alle darin enthaltenen Regeln `<PolicyRules>` `</PolicyRules>` in einer XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-238">Combine all rules within `<PolicyRules>` `</PolicyRules>` into one xml file.</span></span> 

    <span data-ttu-id="c3c9b-239">Wenn Sie einen bestimmten Benutzer einschränken möchten, verwenden Sie die SID-Eigenschaft im Eintrag.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-239">If you want to restrict a specific user, then use SID property into the Entry.</span></span> <span data-ttu-id="c3c9b-240">Wenn der Richtlinieneintrag keine SID enthält, wird der Eintrag auf alle Anmeldeinstanzen für den Computer angewendet.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-240">If there is no SID in the policy Entry, the Entry will be applied to everyone login instance for the machine.</span></span>
    
    <span data-ttu-id="c3c9b-241">Die folgende Abbildung veranschaulicht die Verwendung der SID-Eigenschaft und ein Beispiel für [Szenario 1: Verhindern des Schreib- und Ausführungszugriffs auf alle genehmigten USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)außer zulassen.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-241">The following image illustrates the usage of SID property, and an example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="Der Bildschirm mit einem Code, der die Verwendung des SID-Eigenschaftsattributs angibt":::

3. <span data-ttu-id="c3c9b-243">Speichern Sie sowohl Regel- als auch Gruppen-XML-Dateien im Netzwerkfreigabeordner, und fügen Sie den Pfad des Netzwerkfreigabeordners in die Gruppenrichtlinieneinstellung ein: **Computerkonfiguration -> Administrative Vorlagen -> Windows Komponenten -> Microsoft Defender Antivirus -> Gerätesteuerung: "Gerätesteuerungsrichtliniengruppen definieren" und "Gerätesteuerungsrichtlinienregeln definieren".**</span><span class="sxs-lookup"><span data-stu-id="c3c9b-243">Save both rule and group XML files on network share folder and put network share folder path into the Group Policy setting: **Computer Configuration -> Administrative Templates -> Windows Components -> Microsoft Defender Antivirus -> Device Control: ‘Define device control policy groups’ and ‘Define device control policy rules’**.</span></span>

    - <span data-ttu-id="c3c9b-244">Der Zielcomputer muss auf die Netzwerkfreigabe zugreifen können, um über die Richtlinie verfügen zu können.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-244">The target machine must be able to access the network share to have the policy.</span></span> <span data-ttu-id="c3c9b-245">Nachdem die Richtlinie gelesen wurde, ist die Netzwerkfreigabeverbindung jedoch auch nach dem Computerneustart nicht mehr erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-245">However, once the policy is read, the network share connection is no longer required, even after machine reboot.</span></span>

    :::image type="content" source="images/device-control.png" alt-text="Der Bildschirm des Gerätesteuerelements":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a><span data-ttu-id="c3c9b-247">Bereitstellen und Verwalten von Richtlinien über Intune OMA-URI</span><span class="sxs-lookup"><span data-stu-id="c3c9b-247">Deploying and managing policy via Intune OMA-URI</span></span>

<span data-ttu-id="c3c9b-248">Mit dem Feature "Wechselbare Storage Zugriffssteuerung" können Sie Richtlinien über OMA-URI entweder auf Benutzer oder Geräte oder auf beides anwenden.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-248">The Removable Storage Access Control feature enables you to apply policy via OMA-URI to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="c3c9b-249">Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="c3c9b-249">Licensing</span></span>

<span data-ttu-id="c3c9b-250">Bevor Sie mit wechselbaren Storage Zugriffssteuerung beginnen, müssen Sie Ihr [Microsoft 365 Abonnement](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)bestätigen.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-250">Before you get started with Removable Storage Access Control, you  must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="c3c9b-251">Um auf wechselbare Storage Zugriffssteuerung zuzugreifen und sie zu verwenden, benötigen Sie Microsoft 365 E3 oder Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-251">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="permission"></a><span data-ttu-id="c3c9b-252">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="c3c9b-252">Permission</span></span>

<span data-ttu-id="c3c9b-253">Für die Richtlinienbereitstellung in Intune muss das Konto über Berechtigungen zum Erstellen, Bearbeiten, Aktualisieren oder Löschen von Gerätekonfigurationsprofilen verfügen.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-253">For policy deployment in Intune, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="c3c9b-254">Sie können benutzerdefinierte Rollen erstellen oder eine der integrierten Rollen mit diesen Berechtigungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-254">You can create custom roles or use any of the built-in roles with these permissions.</span></span>

- <span data-ttu-id="c3c9b-255">Rolle "Richtlinien- und Profil-Manager"</span><span class="sxs-lookup"><span data-stu-id="c3c9b-255">Policy and profile Manager role</span></span>
- <span data-ttu-id="c3c9b-256">Benutzerdefinierte Rolle mit aktivierten Berechtigungen zum Erstellen/Bearbeiten/Aktualisieren/Lesen/Löschen/Anzeigen von Berichten für Gerätekonfigurationsprofile</span><span class="sxs-lookup"><span data-stu-id="c3c9b-256">Custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="c3c9b-257">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="c3c9b-257">Global administrator</span></span>

### <a name="deploying-policy-via-oma-uri"></a><span data-ttu-id="c3c9b-258">Bereitstellen von Richtlinien über OMA-URI</span><span class="sxs-lookup"><span data-stu-id="c3c9b-258">Deploying policy via OMA-URI</span></span>

<span data-ttu-id="c3c9b-259">**Microsoft Endpoint Manager Admin Center ( https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span><span class="sxs-lookup"><span data-stu-id="c3c9b-259">**Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span></span>

1. <span data-ttu-id="c3c9b-260">Erstellen Sie für jede Gruppe eine OMA-URI-Regel:</span><span class="sxs-lookup"><span data-stu-id="c3c9b-260">For each Group, create an OMA-URI rule:</span></span>
    - <span data-ttu-id="c3c9b-261">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="c3c9b-261">OMA-URI:</span></span>

      <span data-ttu-id="c3c9b-262">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="c3c9b-262">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span></span>

      <span data-ttu-id="c3c9b-263">For example, for **any removable storage and CD/DVD** group in the sample, the link must be:</span><span class="sxs-lookup"><span data-stu-id="c3c9b-263">For example, for **any removable storage and CD/DVD** group in the sample, the link must be:</span></span>

      <span data-ttu-id="c3c9b-264">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="c3c9b-264">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span></span>

    - <span data-ttu-id="c3c9b-265">Datentyp: Zeichenfolge (XML-Datei)</span><span class="sxs-lookup"><span data-stu-id="c3c9b-265">Data Type: String (XML file)</span></span>
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="Die XML-Datei für den DATENTYP STRING":::

2. <span data-ttu-id="c3c9b-267">Erstellen Sie für jede Richtlinie auch einen OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="c3c9b-267">For each policy, also create an OMA-URI:</span></span>

    - <span data-ttu-id="c3c9b-268">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="c3c9b-268">OMA-URI:</span></span>

      <span data-ttu-id="c3c9b-269">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span><span class="sxs-lookup"><span data-stu-id="c3c9b-269">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span></span>

      <span data-ttu-id="c3c9b-270">For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be:</span><span class="sxs-lookup"><span data-stu-id="c3c9b-270">For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be:</span></span> 

      <span data-ttu-id="c3c9b-271">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-271">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span></span>

    - <span data-ttu-id="c3c9b-272">Datentyp: Zeichenfolge (XML-Datei)</span><span class="sxs-lookup"><span data-stu-id="c3c9b-272">Data Type: String (XML file)</span></span>

      :::image type="content" source="images/xml-data-type-string-2.png" lightbox="images/xml-data-type-string-2.png" alt-text="Anzeigen der XML-Datei für den DATENTYP STRING":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a><span data-ttu-id="c3c9b-274">Bereitstellen und Verwalten von Richtlinien mithilfe der Intune-Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="c3c9b-274">Deploying and managing policy by using Intune user interface</span></span>

<span data-ttu-id="c3c9b-275">Diese Funktion (in Microsoft Endpoint Manager Admin Center ( https://endpoint.microsoft.com/) > Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control) ist noch nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-275">This capability (in Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) > Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control) is not yet available.</span></span> 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="c3c9b-276">Anzeigen von Wechseldaten von Gerätesteuerungen Storage Zugriffssteuerungsdaten in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="c3c9b-276">View Device Control Removable Storage Access Control data in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="c3c9b-277">Das Microsoft 365-Sicherheitsportal zeigt Wechselmedien an, die von der Gerätesteuerung (Removable Storage Access Control) blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="c3c9b-277">The Microsoft 365 security portal shows removable storage blocked by the Device Control Removable Storage Access Control.</span></span> <span data-ttu-id="c3c9b-278">Um auf die Microsoft 365 Sicherheit zugreifen zu können, benötigen Sie das folgende Abonnement:</span><span class="sxs-lookup"><span data-stu-id="c3c9b-278">To access the Microsoft 365 security, you must have the following subscription:</span></span>

- <span data-ttu-id="c3c9b-279">Microsoft 365 für E5-Berichte</span><span class="sxs-lookup"><span data-stu-id="c3c9b-279">Microsoft 365 for E5 reporting</span></span>

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
