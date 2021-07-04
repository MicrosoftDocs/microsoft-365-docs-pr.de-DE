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
ms.topic: article
ms.openlocfilehash: 0f089efedef1e4fb6b146692da3f1a630f2bacac
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289691"
---
# <a name="device-control-printer-protection"></a><span data-ttu-id="34c3d-103">Druckerschutz für Gerätesteuerung</span><span class="sxs-lookup"><span data-stu-id="34c3d-103">Device Control Printer Protection</span></span>

<span data-ttu-id="34c3d-104">Microsoft Defender für Endpunkt Gerätesteuerungsdruckerschutz verhindert, dass Benutzer über Nicht-Unternehmensdrucker oder nicht genehmigte USB-Drucker drucken.</span><span class="sxs-lookup"><span data-stu-id="34c3d-104">Microsoft Defender for Endpoint Device Control Printer Protection blocks people from printing via non-corporate printers or non-approved USB printer.</span></span>

## <a name="licensing"></a><span data-ttu-id="34c3d-105">Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="34c3d-105">Licensing</span></span>

<span data-ttu-id="34c3d-106">Bevor Sie mit Printer Protection beginnen, sollten Sie [Ihr Microsoft 365 Abonnement bestätigen.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)</span><span class="sxs-lookup"><span data-stu-id="34c3d-106">Before you get started with Printer Protection, you should [confirm your Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1).</span></span> <span data-ttu-id="34c3d-107">Für den Zugriff auf und die Verwendung von Printer Protection benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="34c3d-107">To access and use Printer Protection, you must have the following:</span></span>

- <span data-ttu-id="34c3d-108">Microsoft 365 E3 für die Bereitstellung von Funktionen/Richtlinien</span><span class="sxs-lookup"><span data-stu-id="34c3d-108">Microsoft 365 E3 for functionality/policy deployment</span></span>
- <span data-ttu-id="34c3d-109">Microsoft 365 E5 für die Berichterstellung</span><span class="sxs-lookup"><span data-stu-id="34c3d-109">Microsoft 365 E5 for reporting</span></span>

## <a name="permission"></a><span data-ttu-id="34c3d-110">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="34c3d-110">Permission</span></span>

<span data-ttu-id="34c3d-111">Für die Richtlinienbereitstellung in Intune muss das Konto zum Bereitstellen von Richtlinien über OMA-URI über Berechtigungen zum Erstellen, Bearbeiten, Aktualisieren oder Löschen von Gerätekonfigurationsprofilen verfügen.</span><span class="sxs-lookup"><span data-stu-id="34c3d-111">For Policy deployment in Intune, to deploy policy via OMA-URI, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="34c3d-112">Sie können benutzerdefinierte Rollen erstellen oder eine der integrierten Rollen mit diesen Berechtigungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="34c3d-112">You can create custom roles or use any of the built-in roles with these permissions:</span></span>

- <span data-ttu-id="34c3d-113">Rolle "Richtlinien- und Profil-Manager".</span><span class="sxs-lookup"><span data-stu-id="34c3d-113">Policy and profile Manager role.</span></span>
- <span data-ttu-id="34c3d-114">Oder benutzerdefinierte Rolle mit aktivierten Berechtigungen zum Erstellen/Bearbeiten/Aktualisieren/Lesen/Löschen/Anzeigen von Berichten für Gerätekonfigurationsprofile</span><span class="sxs-lookup"><span data-stu-id="34c3d-114">Or custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="34c3d-115">Oder globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="34c3d-115">Or Global admin</span></span>

<span data-ttu-id="34c3d-116">Um Gerätekonfigurationsberichte anzuzeigen, muss das Konto über Anzeigeberichtsberechtigungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="34c3d-116">To see device configuration reports, the account must have view reports permissions.</span></span> <span data-ttu-id="34c3d-117">Sie können benutzerdefinierte Rollen erstellen oder die integrierten Rollen mit diesen Berechtigungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="34c3d-117">You can create custom roles or use the built-in roles with these permissions:</span></span>

- <span data-ttu-id="34c3d-118">Globaler Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="34c3d-118">Global security admin</span></span>
- <span data-ttu-id="34c3d-119">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="34c3d-119">Security admin</span></span>
- <span data-ttu-id="34c3d-120">Sicherheitsleseberechtigter</span><span class="sxs-lookup"><span data-stu-id="34c3d-120">Security Reader</span></span>

## <a name="prepare-your-endpoints"></a><span data-ttu-id="34c3d-121">Vorbereiten der Endpunkte</span><span class="sxs-lookup"><span data-stu-id="34c3d-121">Prepare your endpoints</span></span>

<span data-ttu-id="34c3d-122">Stellen Sie sicher, dass die Windows 10 Geräte, die Sie für die Bereitstellung von Printer Protection planen, um diese Anforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="34c3d-122">Make sure that the Windows 10 devices that you plan on deploying Printer Protection to meet these requirements.</span></span>

1. <span data-ttu-id="34c3d-123">Treten Sie dem Insider-Programm bei.</span><span class="sxs-lookup"><span data-stu-id="34c3d-123">Join the Insider Program.</span></span>

1. <span data-ttu-id="34c3d-124">Die folgenden Windows-Updates sind installiert.</span><span class="sxs-lookup"><span data-stu-id="34c3d-124">The following Windows Updates are installed.</span></span>
    - <span data-ttu-id="34c3d-125">For Windows 1809: install Windows Update [KB5003217](https://support.microsoft.com/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)</span><span class="sxs-lookup"><span data-stu-id="34c3d-125">For Windows 1809: install Windows Update [KB5003217](https://support.microsoft.com/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)</span></span>
    - <span data-ttu-id="34c3d-126">For Windows 1909: install Windows Update [KB5003212](https://support.microsoft.com/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)</span><span class="sxs-lookup"><span data-stu-id="34c3d-126">For Windows 1909: install Windows Update [KB5003212](https://support.microsoft.com/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)</span></span>
    - <span data-ttu-id="34c3d-127">Für Windows 2004 oder höher</span><span class="sxs-lookup"><span data-stu-id="34c3d-127">For Windows 2004 or later</span></span>

1. <span data-ttu-id="34c3d-128">Wenn Sie die Bereitstellung von Richtlinien über Gruppenrichtlinien planen, muss das Gerät MDATP-mitglied sein. Wenn Sie eine Richtlinie über MEM bereitstellen möchten, muss das Gerät intune-mitglied sein.</span><span class="sxs-lookup"><span data-stu-id="34c3d-128">If you're planning to deploy policy via Group Policy, the device must be MDATP joined; if you're planning to deploy policy via MEM, the device must be Intune joined.</span></span>

## <a name="deploy-device-control-printer-protection-policy"></a><span data-ttu-id="34c3d-129">Bereitstellen der Druckerschutzrichtlinie für Gerätesteuerung</span><span class="sxs-lookup"><span data-stu-id="34c3d-129">Deploy Device Control Printer Protection policy</span></span>

<span data-ttu-id="34c3d-130">Sie können die Richtlinie über gruppenrichtlinien oder Intune bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="34c3d-130">You can deploy the policy via Group Policy or Intune.</span></span>

<br>

****

|<span data-ttu-id="34c3d-131">Titel</span><span class="sxs-lookup"><span data-stu-id="34c3d-131">Title</span></span>|<span data-ttu-id="34c3d-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34c3d-132">Description</span></span>|<span data-ttu-id="34c3d-133">CSP-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="34c3d-133">CSP Support</span></span> | <span data-ttu-id="34c3d-134">GPO-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="34c3d-134">GPO Support</span></span> | <span data-ttu-id="34c3d-135">Benutzerbasierter Support</span><span class="sxs-lookup"><span data-stu-id="34c3d-135">User-based Support</span></span> | <span data-ttu-id="34c3d-136">Computerbasierter Support</span><span class="sxs-lookup"><span data-stu-id="34c3d-136">Machine-based Support</span></span> |
|---|---|:---:|:---:|:---:|:---:|
|<span data-ttu-id="34c3d-137">**Aktivieren von Druckeinschränkungen für Gerätesteuerelemente**</span><span class="sxs-lookup"><span data-stu-id="34c3d-137">**Enable Device control Printing Restrictions**</span></span>|<span data-ttu-id="34c3d-138">Blockieren des Druckens über einen Drucker, der kein Unternehmen ist</span><span class="sxs-lookup"><span data-stu-id="34c3d-138">Block people from printing via non-corporate printer</span></span>|<span data-ttu-id="34c3d-139">Ja</span><span class="sxs-lookup"><span data-stu-id="34c3d-139">Yes</span></span>|<span data-ttu-id="34c3d-140">Ja</span><span class="sxs-lookup"><span data-stu-id="34c3d-140">Yes</span></span>|<span data-ttu-id="34c3d-141">Ja</span><span class="sxs-lookup"><span data-stu-id="34c3d-141">Yes</span></span>|<span data-ttu-id="34c3d-142">Ja</span><span class="sxs-lookup"><span data-stu-id="34c3d-142">Yes</span></span>|
|<span data-ttu-id="34c3d-143">**Liste der genehmigten USB-verbundenen Druckgeräte**\*</span><span class="sxs-lookup"><span data-stu-id="34c3d-143">**List of Approved USB-connected print devices**\*</span></span>|<span data-ttu-id="34c3d-144">Zulassen eines bestimmten USB-Druckers</span><span class="sxs-lookup"><span data-stu-id="34c3d-144">Allow specific USB printer</span></span>|<span data-ttu-id="34c3d-145">Ja</span><span class="sxs-lookup"><span data-stu-id="34c3d-145">Yes</span></span>|<span data-ttu-id="34c3d-146">Ja</span><span class="sxs-lookup"><span data-stu-id="34c3d-146">Yes</span></span>|<span data-ttu-id="34c3d-147">Ja</span><span class="sxs-lookup"><span data-stu-id="34c3d-147">Yes</span></span>|<span data-ttu-id="34c3d-148">Ja</span><span class="sxs-lookup"><span data-stu-id="34c3d-148">Yes</span></span>|
|

<span data-ttu-id="34c3d-149">\* Diese Richtlinie muss zusammen mit **den Druckeinschränkungen** für die Gerätesteuerung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="34c3d-149">\* This policy must be used together with **Enable Device control Printing Restrictions**.</span></span>

## <a name="deploy-policy-via-intune"></a><span data-ttu-id="34c3d-150">Bereitstellen von Richtlinien über Intune</span><span class="sxs-lookup"><span data-stu-id="34c3d-150">Deploy policy via Intune</span></span>

<span data-ttu-id="34c3d-151">Für Intune unterstützt der Gerätesteuerungsdruckerschutz derzeit nur OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="34c3d-151">For Intune, currently Device Control Printer Protection supports OMA-URI only.</span></span>

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-intune"></a><span data-ttu-id="34c3d-152">Szenario 1: Blockieren des Druckens über einen beliebigen Drucker, der nicht zum Unternehmen gehört, mit Intune</span><span class="sxs-lookup"><span data-stu-id="34c3d-152">Scenario 1: Block people from printing via any non-corporate printer using Intune</span></span>

- <span data-ttu-id="34c3d-153">Anwenden von Richtlinien über Computer:</span><span class="sxs-lookup"><span data-stu-id="34c3d-153">Apply policy over machine:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl`

- <span data-ttu-id="34c3d-154">Wenden Sie die Richtlinie über den Benutzer an:</span><span class="sxs-lookup"><span data-stu-id="34c3d-154">Apply policy over user:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser`

<span data-ttu-id="34c3d-155">Die CSP-Unterstützungszeichenfolge `<enabled/>` mit:</span><span class="sxs-lookup"><span data-stu-id="34c3d-155">The CSP support string with `<enabled/>`:</span></span>

:::image type="content" source="../../media/customeditrow.png" alt-text="Benutzerdefinierte Bearbeitungszeile":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-intune"></a><span data-ttu-id="34c3d-157">Szenario 2: Zulassen bestimmter genehmigter USB-Drucker mit Intune</span><span class="sxs-lookup"><span data-stu-id="34c3d-157">Scenario 2: Allow specific approved USB printers using Intune</span></span>

- <span data-ttu-id="34c3d-158">Anwenden von Richtlinien über Computer:</span><span class="sxs-lookup"><span data-stu-id="34c3d-158">Apply policy over machine:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices`

- <span data-ttu-id="34c3d-159">Wenden Sie die Richtlinie über den Benutzer an:</span><span class="sxs-lookup"><span data-stu-id="34c3d-159">Apply policy over user:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser`

<span data-ttu-id="34c3d-160">Die CSP-Unterstützungszeichenfolge mit genehmigten USB-Druckern über die Eigenschaft "ApprovedUsbPrintDevices", `<enabled><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872">` Beispiel:</span><span class="sxs-lookup"><span data-stu-id="34c3d-160">The CSP support string with approved USB printers via 'ApprovedUsbPrintDevices' property, example `<enabled><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872">`:</span></span>

:::image type="content" source="../../media/editrow.png" alt-text="Zeile bearbeiten":::

## <a name="deploy-policy-via-group-policy"></a><span data-ttu-id="34c3d-162">Bereitstellen von Richtlinien über Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="34c3d-162">Deploy policy via Group Policy</span></span>

<span data-ttu-id="34c3d-163">Wenn das Gerät nicht in Intune eingebunden ist, können Sie die Richtlinie auch über die Gruppenrichtlinie bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="34c3d-163">If the device isn't Intune joined, you can also deploy the policy via Group Policy.</span></span>

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-group-policy"></a><span data-ttu-id="34c3d-164">Szenario 1: Blockieren des Druckens über einen beliebigen Nicht-Unternehmensdrucker mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="34c3d-164">Scenario 1: Block people from printing via any non-corporate printer using Group Policy</span></span>

- <span data-ttu-id="34c3d-165">Anwenden von Richtlinien über Computer:</span><span class="sxs-lookup"><span data-stu-id="34c3d-165">Apply policy over machine:</span></span>

  <span data-ttu-id="34c3d-166">Drucker für administrative Vorlagen für die \> \> Computerkonfiguration: Aktivieren von Druckeinschränkungen für Gerätesteuerelemente</span><span class="sxs-lookup"><span data-stu-id="34c3d-166">Computer Configuration \> Administrative Templates \> Printer: Enable Device control Printing Restrictions</span></span>

- <span data-ttu-id="34c3d-167">Wenden Sie die Richtlinie über den Benutzer an:</span><span class="sxs-lookup"><span data-stu-id="34c3d-167">Apply policy over user:</span></span>

  <span data-ttu-id="34c3d-168">Drucker der Systemsteuerung für administrative Vorlagen der \> Benutzerkonfiguration: Aktivieren von \> \> Druckeinschränkungen für Gerätesteuerelemente</span><span class="sxs-lookup"><span data-stu-id="34c3d-168">User Configuration \> Administrative Templates \> Control Panel \> Printers: Enable Device control Printing Restrictions</span></span>

:::image type="content" source="../../media/enable-device-ctrl-printing-restrictions.png" alt-text="Aktivieren von Einschränkungen beim Drucken von Geräten":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-group-policy"></a><span data-ttu-id="34c3d-170">Szenario 2: Zulassen bestimmter genehmigter USB-Drucker mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="34c3d-170">Scenario 2: Allow specific approved USB printers using Group Policy</span></span>

- <span data-ttu-id="34c3d-171">Anwenden von Richtlinien über Computer:</span><span class="sxs-lookup"><span data-stu-id="34c3d-171">Apply policy over machine:</span></span>

  <span data-ttu-id="34c3d-172">Drucker für administrative Vorlagen für die \> Computerkonfiguration: \> Liste der genehmigten USB-verbundenen Druckgeräte</span><span class="sxs-lookup"><span data-stu-id="34c3d-172">Computer Configuration \> Administrative Templates \> Printer:  List of Approved USB-connected print devices</span></span>

- <span data-ttu-id="34c3d-173">Wenden Sie die Richtlinie über den Benutzer an:</span><span class="sxs-lookup"><span data-stu-id="34c3d-173">Apply policy over user:</span></span>

  <span data-ttu-id="34c3d-174">Benutzerkonfiguration \> Administrative Vorlagen \> \> Systemsteuerungsdrucker: Liste der genehmigten USB-verbundenen Druckgeräte</span><span class="sxs-lookup"><span data-stu-id="34c3d-174">User Configuration \> Administrative Templates \> Control Panel \> Printers: List of Approved USB-connected print devices</span></span>

:::image type="content" source="../../media/list-of-approved-connected-print-devices.png" alt-text="Liste der genehmigten usb-verbundenen Druckgeräte":::

## <a name="view-device-control-printer-protection-data-in-microsoft-defender-for-endpoint-portal"></a><span data-ttu-id="34c3d-176">Anzeigen von Gerätesteuerungsdrucker-Schutzdaten im Microsoft Defender für Endpunkt-Portal</span><span class="sxs-lookup"><span data-stu-id="34c3d-176">View Device Control Printer Protection data in Microsoft Defender for Endpoint portal</span></span>

<span data-ttu-id="34c3d-177">Das [Microsoft 365 Security Center](https://security.microsoft.com) zeigt das Drucken an, das durch die oben beschriebene Richtlinie für den Gerätesteuerungsdruckerschutz blockiert wurde.</span><span class="sxs-lookup"><span data-stu-id="34c3d-177">The [Microsoft 365 security center](https://security.microsoft.com) shows printing blocked by the Device Control Printer Protection policy above.</span></span>

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
