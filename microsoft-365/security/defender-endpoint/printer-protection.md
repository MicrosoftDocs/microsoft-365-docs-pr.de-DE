---
title: Microsoft Defender für Endpunkt Gerätesteuerungsdruckerschutz
description: Microsoft Defender für Endpunkt Gerätesteuerungsdruckerschutz verhindert, dass Benutzer über Nicht-Unternehmensdrucker oder nicht genehmigte USB-Drucker drucken.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.author: v-lsaldanha
author: lovina-saldanha
ms.reviewer: dansimp
manager: dansimp
audience: ITPro
ms.technology: mde
ms.openlocfilehash: 431497ded684543c33d91c49a0da47e92297321f
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809260"
---
# <a name="device-control-printer-protection"></a><span data-ttu-id="37b27-103">Gerätesteuerungsdruckerschutz</span><span class="sxs-lookup"><span data-stu-id="37b27-103">Device Control Printer Protection</span></span> 

<span data-ttu-id="37b27-104">Microsoft Defender für Endpunkt Gerätesteuerungsdruckerschutz verhindert, dass Benutzer über Nicht-Unternehmensdrucker oder nicht genehmigte USB-Drucker drucken.</span><span class="sxs-lookup"><span data-stu-id="37b27-104">Microsoft Defender for Endpoint Device Control Printer Protection blocks people from printing via non-corporate printers or non-approved USB printer.</span></span>

## <a name="licensing"></a><span data-ttu-id="37b27-105">Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="37b27-105">Licensing</span></span> 

<span data-ttu-id="37b27-106">Bevor Sie mit Printer Protection beginnen, sollten Sie [Ihr Microsoft 365 Abonnement bestätigen.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)</span><span class="sxs-lookup"><span data-stu-id="37b27-106">Before you get started with Printer Protection, you should [confirm your Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1).</span></span> <span data-ttu-id="37b27-107">Für den Zugriff auf und die Verwendung von Printer Protection benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="37b27-107">To access and use Printer Protection, you must have the following:</span></span>

- <span data-ttu-id="37b27-108">Microsoft 365 E3 für die Bereitstellung von Funktionen/Richtlinien</span><span class="sxs-lookup"><span data-stu-id="37b27-108">Microsoft 365 E3 for functionality/policy deployment</span></span> 
- <span data-ttu-id="37b27-109">Microsoft 365 E5 für die Berichterstellung</span><span class="sxs-lookup"><span data-stu-id="37b27-109">Microsoft 365 E5 for reporting</span></span> 

## <a name="permission"></a><span data-ttu-id="37b27-110">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="37b27-110">Permission</span></span> 

<span data-ttu-id="37b27-111">Für die Richtlinienbereitstellung in Intune muss das Konto zum Bereitstellen von Richtlinien über OMA-URI über Berechtigungen zum Erstellen, Bearbeiten, Aktualisieren oder Löschen von Gerätekonfigurationsprofilen verfügen.</span><span class="sxs-lookup"><span data-stu-id="37b27-111">For Policy deployment in Intune, to deploy policy via OMA-URI, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="37b27-112">Sie können benutzerdefinierte Rollen erstellen oder eine der integrierten Rollen mit diesen Berechtigungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="37b27-112">You can create custom roles or use any of the built-in roles with these permissions:</span></span>  

- <span data-ttu-id="37b27-113">Rolle "Richtlinien- und Profil-Manager".</span><span class="sxs-lookup"><span data-stu-id="37b27-113">Policy and profile Manager role.</span></span> 
- <span data-ttu-id="37b27-114">Oder benutzerdefinierte Rolle mit aktivierten Berechtigungen zum Erstellen/Bearbeiten/Aktualisieren/Lesen/Löschen/Anzeigen von Berichten für Gerätekonfigurationsprofile</span><span class="sxs-lookup"><span data-stu-id="37b27-114">Or custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>  
- <span data-ttu-id="37b27-115">Oder globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="37b27-115">Or Global admin</span></span>

<span data-ttu-id="37b27-116">Um Gerätekonfigurationsberichte anzuzeigen, muss das Konto über Anzeigeberichtsberechtigungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="37b27-116">To see device configuration reports, the account must have view reports permissions.</span></span> <span data-ttu-id="37b27-117">Sie können benutzerdefinierte Rollen erstellen oder die integrierten Rollen mit diesen Berechtigungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="37b27-117">You can create custom roles or use the built-in roles with these permissions:</span></span>  

- <span data-ttu-id="37b27-118">Globaler Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="37b27-118">Global security admin</span></span>
- <span data-ttu-id="37b27-119">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="37b27-119">Security admin</span></span>
- <span data-ttu-id="37b27-120">Sicherheitsleseberechtigter</span><span class="sxs-lookup"><span data-stu-id="37b27-120">Security Reader</span></span> 

## <a name="prepare-your-endpoints"></a><span data-ttu-id="37b27-121">Vorbereiten der Endpunkte</span><span class="sxs-lookup"><span data-stu-id="37b27-121">Prepare your endpoints</span></span>

<span data-ttu-id="37b27-122">Stellen Sie sicher, dass die Windows 10 Geräte, die Sie für die Bereitstellung von Printer Protection planen, um diese Anforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="37b27-122">Make sure that the Windows 10 devices that you plan on deploying Printer Protection to meet these requirements.</span></span>

1. <span data-ttu-id="37b27-123">Treten Sie dem Insider-Programm bei.</span><span class="sxs-lookup"><span data-stu-id="37b27-123">Join the Insider Program.</span></span>

1. <span data-ttu-id="37b27-124">Die folgenden Windows-Updates sind installiert.</span><span class="sxs-lookup"><span data-stu-id="37b27-124">The following Windows Updates are installed.</span></span> 

    - <span data-ttu-id="37b27-125">For Windows 1809: install Windows Update [KB5003217](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)</span><span class="sxs-lookup"><span data-stu-id="37b27-125">For Windows 1809: install Windows Update [KB5003217](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)</span></span> 
    - <span data-ttu-id="37b27-126">For Windows 1909: install Windows Update [KB5003212](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)</span><span class="sxs-lookup"><span data-stu-id="37b27-126">For Windows 1909: install Windows Update [KB5003212](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)</span></span>
    - <span data-ttu-id="37b27-127">Für Windows 2004 oder höher</span><span class="sxs-lookup"><span data-stu-id="37b27-127">For Windows 2004 or later</span></span> 
    
1. <span data-ttu-id="37b27-128">Wenn Sie die Bereitstellung von Richtlinien über Gruppenrichtlinien planen, muss das Gerät MDATP eingebunden sein. Wenn Sie eine Richtlinie über MEM bereitstellen möchten, muss das Gerät intune-mitglied sein.</span><span class="sxs-lookup"><span data-stu-id="37b27-128">If you're planning to deploy policy via Group Policy, the device must be MDATP joined; if you're planning to deploy policy via MEM, the device must be Intune joined.</span></span>

## <a name="deploy-device-control-printer-protection-policy"></a><span data-ttu-id="37b27-129">Bereitstellen der Druckerschutzrichtlinie für Gerätesteuerung</span><span class="sxs-lookup"><span data-stu-id="37b27-129">Deploy Device Control Printer Protection policy</span></span>

<span data-ttu-id="37b27-130">Sie können die Richtlinie über gruppenrichtlinien oder Intune bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="37b27-130">You can deploy the policy via Group Policy or Intune.</span></span>

| <span data-ttu-id="37b27-131">Titel</span><span class="sxs-lookup"><span data-stu-id="37b27-131">Title</span></span> | <span data-ttu-id="37b27-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="37b27-132">Description</span></span> | <span data-ttu-id="37b27-133">CSP-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="37b27-133">CSP Support</span></span> | <span data-ttu-id="37b27-134">GPO-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="37b27-134">GPO Support</span></span> | <span data-ttu-id="37b27-135">Benutzerbasierter Support</span><span class="sxs-lookup"><span data-stu-id="37b27-135">User-based Support</span></span> | <span data-ttu-id="37b27-136">Computerbasierter Support</span><span class="sxs-lookup"><span data-stu-id="37b27-136">Machine-based Support</span></span> |
|:--|:--|:--|:--|:--|:--|
|<span data-ttu-id="37b27-137">**Aktivieren von Druckeinschränkungen für Gerätesteuerelemente**</span><span class="sxs-lookup"><span data-stu-id="37b27-137">**Enable Device control Printing Restrictions**</span></span>|<span data-ttu-id="37b27-138">Blockieren des Druckens über einen Drucker, der kein Unternehmen ist</span><span class="sxs-lookup"><span data-stu-id="37b27-138">Block people from printing via non-corporate printer</span></span>|<span data-ttu-id="37b27-139">Ja</span><span class="sxs-lookup"><span data-stu-id="37b27-139">Yes</span></span>|<span data-ttu-id="37b27-140">Ja</span><span class="sxs-lookup"><span data-stu-id="37b27-140">Yes</span></span>|<span data-ttu-id="37b27-141">Ja</span><span class="sxs-lookup"><span data-stu-id="37b27-141">Yes</span></span>|<span data-ttu-id="37b27-142">Ja</span><span class="sxs-lookup"><span data-stu-id="37b27-142">Yes</span></span>|
|<span data-ttu-id="37b27-143">**Liste der genehmigten USB-verbundenen Druckgeräte**\*</span><span class="sxs-lookup"><span data-stu-id="37b27-143">**List of Approved USB-connected print devices** \*</span></span>|<span data-ttu-id="37b27-144">Zulassen eines bestimmten USB-Druckers</span><span class="sxs-lookup"><span data-stu-id="37b27-144">Allow specific USB printer</span></span>|<span data-ttu-id="37b27-145">Ja</span><span class="sxs-lookup"><span data-stu-id="37b27-145">Yes</span></span>|<span data-ttu-id="37b27-146">Ja</span><span class="sxs-lookup"><span data-stu-id="37b27-146">Yes</span></span>|<span data-ttu-id="37b27-147">Ja</span><span class="sxs-lookup"><span data-stu-id="37b27-147">Yes</span></span>|<span data-ttu-id="37b27-148">Ja</span><span class="sxs-lookup"><span data-stu-id="37b27-148">Yes</span></span>|
|||||||

<span data-ttu-id="37b27-149">\*Diese Richtlinie muss zusammen mit **Den Druckeinschränkungen** für die Gerätesteuerung aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="37b27-149">\* This policy must be used together with **Enable Device control Printing Restrictions**</span></span>
## <a name="deploy-policy-via-intune"></a><span data-ttu-id="37b27-150">Bereitstellen von Richtlinien über Intune</span><span class="sxs-lookup"><span data-stu-id="37b27-150">Deploy policy via Intune</span></span> 

<span data-ttu-id="37b27-151">Für Intune unterstützt der Gerätesteuerungsdruckerschutz derzeit nur OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="37b27-151">For Intune, currently Device Control Printer Protection supports OMA-URI only.</span></span>

<span data-ttu-id="37b27-152">**Szenario 1: Blockieren des Druckens über einen beliebigen Drucker, der kein Unternehmen ist**</span><span class="sxs-lookup"><span data-stu-id="37b27-152">**Scenario 1: Block people from printing via any non-corporate printer**</span></span> 

 - <span data-ttu-id="37b27-153">Anwenden von Richtlinien über Computer:</span><span class="sxs-lookup"><span data-stu-id="37b27-153">Apply policy over machine:</span></span> 

    - <span data-ttu-id="37b27-154">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl</span><span class="sxs-lookup"><span data-stu-id="37b27-154">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl</span></span> 

- <span data-ttu-id="37b27-155">Wenden Sie die Richtlinie über den Benutzer an:</span><span class="sxs-lookup"><span data-stu-id="37b27-155">Apply policy over user:</span></span> 

    - <span data-ttu-id="37b27-156">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser</span><span class="sxs-lookup"><span data-stu-id="37b27-156">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser</span></span> 

<span data-ttu-id="37b27-157">Die CSP-Unterstützungszeichenfolge `` <enabled/>`` mit:</span><span class="sxs-lookup"><span data-stu-id="37b27-157">The CSP support string with `` <enabled/>``:</span></span> 

:::image type="content" source="../../media/customeditrow.png" alt-text="Benutzerdefinierte Bearbeitungszeile":::

<span data-ttu-id="37b27-159">**Szenario 2: Zulassen bestimmter genehmigter USB-Drucker**</span><span class="sxs-lookup"><span data-stu-id="37b27-159">**Scenario 2: Allow specific approved USB printers**</span></span>

- <span data-ttu-id="37b27-160">Anwenden von Richtlinien über Computer:</span><span class="sxs-lookup"><span data-stu-id="37b27-160">Apply policy over machine:</span></span> 

    - <span data-ttu-id="37b27-161">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices</span><span class="sxs-lookup"><span data-stu-id="37b27-161">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices</span></span> 

- <span data-ttu-id="37b27-162">Wenden Sie die Richtlinie über den Benutzer an:</span><span class="sxs-lookup"><span data-stu-id="37b27-162">Apply policy over user:</span></span> 

    - <span data-ttu-id="37b27-163">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser</span><span class="sxs-lookup"><span data-stu-id="37b27-163">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser</span></span>  

<span data-ttu-id="37b27-164">Die CSP-Unterstützungszeichenfolge mit genehmigten USB-Druckern über die Eigenschaft "ApprovedUsbPrintDevices", `` <enabled/><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872"/>`` Beispiel:</span><span class="sxs-lookup"><span data-stu-id="37b27-164">The CSP support string with approved USB printers via ‘ApprovedUsbPrintDevices’ property, example `` <enabled/><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872"/>``:</span></span> 

:::image type="content" source="../../media/editrow.png" alt-text="Zeile bearbeiten":::

## <a name="deploy-policy-via-group-policy"></a><span data-ttu-id="37b27-166">Bereitstellen von Richtlinien über Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="37b27-166">Deploy policy via Group Policy</span></span> 

<span data-ttu-id="37b27-167">Wenn das Gerät nicht in Intune eingebunden ist, können Sie die Richtlinie auch über die Gruppenrichtlinie bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="37b27-167">If the device isn't Intune joined, you can also deploy the policy via Group Policy.</span></span> 

<span data-ttu-id="37b27-168">**Szenario 1: Blockieren des Druckens über einen beliebigen Drucker, der kein Unternehmen ist**</span><span class="sxs-lookup"><span data-stu-id="37b27-168">**Scenario 1: Block people from printing via any non-corporate printer**</span></span> 

- <span data-ttu-id="37b27-169">Anwenden von Richtlinien über Computer:</span><span class="sxs-lookup"><span data-stu-id="37b27-169">Apply policy over machine:</span></span> 

    - <span data-ttu-id="37b27-170">Computerkonfiguration > Administrative Vorlagen > Drucker: Aktivieren von Druckeinschränkungen für Gerätesteuerelemente</span><span class="sxs-lookup"><span data-stu-id="37b27-170">Computer Configuration > Administrative Templates > Printer: Enable Device control Printing Restrictions</span></span> 

- <span data-ttu-id="37b27-171">Wenden Sie die Richtlinie über den Benutzer an:</span><span class="sxs-lookup"><span data-stu-id="37b27-171">Apply policy over user:</span></span> 

    - <span data-ttu-id="37b27-172">Benutzerkonfiguration > Administrative Vorlagen > Systemsteuerung > Drucker: Aktivieren von Druckeinschränkungen für Gerätesteuerelemente</span><span class="sxs-lookup"><span data-stu-id="37b27-172">User Configuration > Administrative Templates > Control Panel > Printers: Enable Device control Printing Restrictions</span></span> 

:::image type="content" source="../../media/enable-device-ctrl-printing-restrictions.png" alt-text="Aktivieren von Einschränkungen beim Drucken von Geräten":::
 

<span data-ttu-id="37b27-174">**Szenario 2: Zulassen bestimmter genehmigter USB-Drucker**</span><span class="sxs-lookup"><span data-stu-id="37b27-174">**Scenario 2: Allow specific approved USB printers**</span></span>

- <span data-ttu-id="37b27-175">Anwenden von Richtlinien über Computer:</span><span class="sxs-lookup"><span data-stu-id="37b27-175">Apply policy over machine:</span></span> 

    - <span data-ttu-id="37b27-176">Computerkonfiguration > Administrative Vorlagen > Drucker: Liste der genehmigten USB-verbundenen Druckgeräte</span><span class="sxs-lookup"><span data-stu-id="37b27-176">Computer Configuration > Administrative Templates > Printer:  List of Approved USB-connected print devices</span></span> 

- <span data-ttu-id="37b27-177">Wenden Sie die Richtlinie über den Benutzer an:</span><span class="sxs-lookup"><span data-stu-id="37b27-177">Apply policy over user:</span></span>  

    - <span data-ttu-id="37b27-178">Benutzerkonfiguration > Administrative Vorlagen > Systemsteuerung > Drucker: Liste der genehmigten USB-verbundenen Druckgeräte</span><span class="sxs-lookup"><span data-stu-id="37b27-178">User Configuration > Administrative Templates > Control Panel > Printers: List of Approved USB-connected print devices</span></span> 
 
 :::image type="content" source="../../media/list-of-approved-connected-print-devices.png" alt-text="Liste der genehmigten usb-verbundenen Druckgeräte":::

## <a name="view-device-control-printer-protection-data-in-microsoft-defender-for-endpoint-portal"></a><span data-ttu-id="37b27-180">Anzeigen von Gerätesteuerungsdrucker-Schutzdaten im Microsoft Defender für Endpunkt-Portal</span><span class="sxs-lookup"><span data-stu-id="37b27-180">View Device Control Printer Protection data in Microsoft Defender for Endpoint portal</span></span> 

<span data-ttu-id="37b27-181">Im [Microsoft 365 Security Center](https://security.microsoft.com) wird das Drucken angezeigt, das durch die oben aufgeführte Richtlinie für den Gerätesteuerungsdruckerschutz blockiert wurde.</span><span class="sxs-lookup"><span data-stu-id="37b27-181">The [Microsoft 365 security center](https://security.microsoft.com) shows printing blocked by the Device Control Printer Protection policy above.</span></span>
 
```sql
DeviceEvents 

|where ActionType == 'PrintJobBlocked' 

| extend parsed=parse_json(AdditionalFields) 

| extend PrintedFile=tostring(parsed.JobOrDocumentName) 

| extend PrintPortName=tostring(parsed.PortName) 

| extend PrinterName=tostring(parsed.PrinterName) 

| extend Policy=tostring(parsed.RestrictionReason)  

| project Timestamp, DeviceId, DeviceName, ActionType, InitiatingProcessAccountName,Policy, PrintedFile, PrinterName, PrintPortName, AdditionalFields 

| order by Timestamp desc 
```

 :::image type="content" source="../../media/device-control-advanced-hunting.png" alt-text="Erweiterte Suche":::
