---
title: Registrieren von Geräten in Microsoft Managed Desktop yourself
description: Registrieren Sie Geräte selbst, damit Sie von Microsoft Managed Desktop verwaltet werden können.
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 217418cfce66baa02b30ae7d8a01b938a1f2366e
ms.sourcegitcommit: 7af6350fb5a6d37934c1b6bfdc38acd09b2d5d86
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "31988431"
---
# <a name="register-devices-in-microsoft-managed-desktop"></a><span data-ttu-id="6b00a-103">Registrieren von Geräten in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="6b00a-103">Register devices in Microsoft Managed Desktop</span></span>

>[!NOTE]
><span data-ttu-id="6b00a-104">In diesem Thema werden die Schritte beschrieben, mit denen Sie Geräte auf eigene Faust registrieren können.</span><span class="sxs-lookup"><span data-stu-id="6b00a-104">This topic describes the steps for you to register devices on your own.</span></span> <span data-ttu-id="6b00a-105">Der Prozess für Partner wird unter [Register Devices in Microsoft Managed Desktop for Partners](register-devices-partner.md)dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="6b00a-105">The process for Partners is documented in [Register devices in Microsoft Managed Desktop for Partners](register-devices-partner.md).</span></span>

<span data-ttu-id="6b00a-106">Microsoft Managed Desktop kann mit brandneuen Geräten verwendet werden, oder Sie können Geräte, die Sie möglicherweise bereits haben (für die Sie Sie erneut abbilden müssen) wieder verwenden.</span><span class="sxs-lookup"><span data-stu-id="6b00a-106">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="6b00a-107">Sie können Geräte mithilfe von Microsoft Managed Desktop im Azure-Portal registrieren oder mithilfe einer API Flexibilität gewinnen.</span><span class="sxs-lookup"><span data-stu-id="6b00a-107">You can register devices by using Microsoft Managed Desktop on the Azure Portal or gain flexibility by using an API.</span></span>

## <a name="prepare-to-register-devices"></a><span data-ttu-id="6b00a-108">Vorbereiten der Registrierung von Geräten</span><span class="sxs-lookup"><span data-stu-id="6b00a-108">Prepare to register devices</span></span>

<span data-ttu-id="6b00a-109">Wenn Sie die gewünschten Geräte noch nicht erhalten haben, überprüfen Sie [Microsoft Managed Desktop-Geräte](../service-description/device-list.md) , und arbeiten Sie mit einem Geräte Partner zusammen, um unterstützte Geräte zu beschaffen.</span><span class="sxs-lookup"><span data-stu-id="6b00a-109">If you haven't already obtained the devices you want to use, check [Microsoft Managed Desktop devices](../service-description/device-list.md) and work with a device partner to procure supported devices.</span></span>

<span data-ttu-id="6b00a-110">Unabhängig davon, ob Sie mit vollständig neuen Geräten arbeiten oder vorhandene wieder verwenden, um Sie bei Microsoft Managed Desktop zu registrieren, müssen Sie eine durch **trennzeichengetrennte Datei (CSV)** erstellen.</span><span class="sxs-lookup"><span data-stu-id="6b00a-110">Whether you're working with completely new devices or re-using existing ones, to register them with Microsoft Managed Desktop, you'll need to prepare a **comma-delimited (CSV) file**.</span></span> <span data-ttu-id="6b00a-111">Diese Datei sollte die folgenden Informationen für jedes Gerät aufweisen:</span><span class="sxs-lookup"><span data-stu-id="6b00a-111">This file should include the following information for each device:</span></span>

>[!NOTE]
><span data-ttu-id="6b00a-112">Dieses Format ist nur für die Self-Service-Registrierung.</span><span class="sxs-lookup"><span data-stu-id="6b00a-112">This format is for self-service registration only.</span></span> <span data-ttu-id="6b00a-113">Die zu verwendenden Format-Partner werden in [Register Devices in Microsoft Managed Desktop for Partners](register-devices-partner.md)dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="6b00a-113">The format Partners should use is documented in [Register devices in Microsoft Managed Desktop for Partners](register-devices-partner.md).</span></span>

<span data-ttu-id="6b00a-114">Diese Werte werden zu Anzeigezwecken verwendet und müssen nicht genau mit den Eigenschaften des Geräts übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="6b00a-114">These values are used for display purposes, and don't need to match properties from the device exactly.</span></span>
- <span data-ttu-id="6b00a-115">Gerätehersteller (Beispiel: SpiralOrbit)</span><span class="sxs-lookup"><span data-stu-id="6b00a-115">Device manufacturer (example: SpiralOrbit)</span></span> 
- <span data-ttu-id="6b00a-116">Gerätemodell (Beispiel: ContosoABC)</span><span class="sxs-lookup"><span data-stu-id="6b00a-116">Device model (example: ContosoABC)</span></span>
- <span data-ttu-id="6b00a-117">Seriennummer des Geräts</span><span class="sxs-lookup"><span data-stu-id="6b00a-117">Device serial number</span></span>

<span data-ttu-id="6b00a-118">Der Hardwarehash muss eine exakte Übereinstimmung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="6b00a-118">The hardware hash must be an exact match.</span></span>
- <span data-ttu-id="6b00a-119">Hardware Hash</span><span class="sxs-lookup"><span data-stu-id="6b00a-119">Hardware hash</span></span>

<span data-ttu-id="6b00a-120">Zum Abrufen des Hardware Hashs können Sie von Ihrem OEM oder Partner Hilfe anfordern oder die folgenden Schritte für jedes Gerät ausführen:</span><span class="sxs-lookup"><span data-stu-id="6b00a-120">To obtain the hardware hash you can ask for help from your OEM or Partner, or follow these steps for each device:</span></span>

1.  <span data-ttu-id="6b00a-121">Öffnen Sie eine PowerShell-Ansage mit Administratorrechten.</span><span class="sxs-lookup"><span data-stu-id="6b00a-121">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="6b00a-122">Führen`Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="6b00a-122">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="6b00a-123">Führen`powershell -ExecutionPolicy Unrestricted Get-WindowsAutopilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="6b00a-123">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutopilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>


<span data-ttu-id="6b00a-124">Alternativ können Sie die folgenden Schritte auf einem nagelneuen Gerät ausführen (bevor Sie OOBE zum ersten Mal durchgehen):</span><span class="sxs-lookup"><span data-stu-id="6b00a-124">Alternately, you can follow these steps on a brand-new device (before going through OOBE for the first time):</span></span>

1. <span data-ttu-id="6b00a-125">Legen Sie auf einem anderen Gerät ein USB-Laufwerk ein.</span><span class="sxs-lookup"><span data-stu-id="6b00a-125">On a different device, insert a USB drive.</span></span>
2. <span data-ttu-id="6b00a-126">Öffnen Sie eine PowerShell-Ansage mit Administratorrechten.</span><span class="sxs-lookup"><span data-stu-id="6b00a-126">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="6b00a-127">Führen`Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="6b00a-127">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="6b00a-128">Aktivieren Sie das Zielgerät, aber beginnen Sie nicht mit der Einrichtung.</span><span class="sxs-lookup"><span data-stu-id="6b00a-128">Turn on the target device, but do not start the setup experience.</span></span> <span data-ttu-id="6b00a-129">Wenn Sie das Setupprogramm versehentlich starten, müssen Sie das Gerät zurücksetzen oder neu abbilden.</span><span class="sxs-lookup"><span data-stu-id="6b00a-129">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="6b00a-130">Legen Sie das USB-Laufwerk ein, und drücken Sie dann UMSCHALT + F10.</span><span class="sxs-lookup"><span data-stu-id="6b00a-130">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="6b00a-131">Öffnen Sie eine PowerShell-Ansage mit Administratorrechten, und `cd <pathToUsb>`führen Sie dann aus.</span><span class="sxs-lookup"><span data-stu-id="6b00a-131">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="6b00a-132">Führen`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="6b00a-132">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="6b00a-133">Führen`.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="6b00a-133">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
3. <span data-ttu-id="6b00a-134">Entfernen Sie das USB-Laufwerk, und fahren Sie dann das Gerät herunter, indem Sie`shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="6b00a-134">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>

>[!IMPORTANT]
><span data-ttu-id="6b00a-135">Schalten Sie das Zielgerät erst wieder ein, wenn Sie die Registrierung dafür abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="6b00a-135">Do not power on the target device again until you've completed registration for it.</span></span> 

>[!NOTE]
><span data-ttu-id="6b00a-136">Zur Vereinfachung können Sie eine [Vorlage](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/raw/live/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.xlsx) für diese CSV-Datei herunterladen.</span><span class="sxs-lookup"><span data-stu-id="6b00a-136">For your convenience, you can download a [template](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/raw/live/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.xlsx) for this CSV file.</span></span>

<span data-ttu-id="6b00a-137">Die Datei muss **genau die gleichen Spaltenüberschriften** wie das Beispiel 1 (Hersteller, Modell usw.), aber eigene Daten für die anderen Zeilen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="6b00a-137">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="6b00a-138">Wenn Sie die Vorlage verwenden, öffnen Sie Sie in einem Text Bearbeitungstool wie Editor, und ziehen Sie in Erwägung, alle Daten in Zeile 1 allein zu lassen, und geben Sie nur Daten in den Zeilen 2 und darunter ein.</span><span class="sxs-lookup"><span data-stu-id="6b00a-138">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="6b00a-139">Wenn Sie vergessen haben, die Beispieldaten zu ändern, schlägt die Registrierung fehl.</span><span class="sxs-lookup"><span data-stu-id="6b00a-139">If you forget to change any of the sample data, registration will fail.</span></span>   


## <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="6b00a-140">Registrieren von Geräten mithilfe des Azure-Portals</span><span class="sxs-lookup"><span data-stu-id="6b00a-140">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="6b00a-141">Wählen Sie im Microsoft Managed Desktop [Azure](https://aka.ms/mmdportal)-Portal **Geräte** im linken Navigationsbereich aus.</span><span class="sxs-lookup"><span data-stu-id="6b00a-141">From the Microsoft Managed Desktop [Azure Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="6b00a-142">Select **+ Register Devices**; das Fly-in wird geöffnet:</span><span class="sxs-lookup"><span data-stu-id="6b00a-142">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="6b00a-143">[![Fly-in nach der Auswahl der Register Geräte](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="6b00a-143">[![Fly-in after selecting Register devices](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span></span>


[//]: # (Leider ist dies nicht der Fall. Wir können diese Notiz entfernen, aber Sie jetzt verlassen, bis wir Gelegenheit haben, darüber zu chatten.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="6b00a-145">Führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="6b00a-145">Follow these steps:</span></span>

1. <span data-ttu-id="6b00a-146">Geben Sie im Feld **Dateiupload**einen Pfad zu der zuvor erstellten CSV-Datei an.</span><span class="sxs-lookup"><span data-stu-id="6b00a-146">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="6b00a-147">Optional können Sie eine **Auftrags-ID** oder eine **Einkaufs-ID** für eigene Tracking-Zwecke hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6b00a-147">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="6b00a-148">Für diese Werte gibt es keine Formatanforderungen.</span><span class="sxs-lookup"><span data-stu-id="6b00a-148">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="6b00a-149">Wählen Sie **Geräte registrieren**aus.</span><span class="sxs-lookup"><span data-stu-id="6b00a-149">Select **Register devices**.</span></span> <span data-ttu-id="6b00a-150">Das System fügt die Geräte der Geräteliste auf dem **Blade Devices**hinzu, die als **Registrierung**ausstehend markiert sind.</span><span class="sxs-lookup"><span data-stu-id="6b00a-150">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="6b00a-151">Die Registrierung dauert in der Regel weniger als 10 Minuten, und wenn das Gerät erfolgreich ist, wird es **für den Benutzer bereit** angezeigt, sodass es bereit ist und darauf wartet, dass ein Endbenutzer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6b00a-151">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="6b00a-152">Sie können den Fortschritt der Geräteregistrierung auf der Hauptseite von **Microsoft Managed Desktop-Devices** überwachen.</span><span class="sxs-lookup"><span data-stu-id="6b00a-152">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="6b00a-153">Mögliche Statusberichte:</span><span class="sxs-lookup"><span data-stu-id="6b00a-153">Possible states reported there include:</span></span>

| <span data-ttu-id="6b00a-154">Status</span><span class="sxs-lookup"><span data-stu-id="6b00a-154">State</span></span> | <span data-ttu-id="6b00a-155">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b00a-155">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="6b00a-156">Registrierung ausstehend</span><span class="sxs-lookup"><span data-stu-id="6b00a-156">Registration pending</span></span> | <span data-ttu-id="6b00a-157">Die Registrierung ist noch nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="6b00a-157">Registration is not done yet.</span></span> <span data-ttu-id="6b00a-158">Überprüfen Sie später.</span><span class="sxs-lookup"><span data-stu-id="6b00a-158">Check back later.</span></span> |
| <span data-ttu-id="6b00a-159">Registrierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="6b00a-159">Registration failed</span></span> | <span data-ttu-id="6b00a-160">Die Registrierung konnte nicht abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="6b00a-160">Registration could not be completed.</span></span> <span data-ttu-id="6b00a-161">Weitere Informationen finden Sie unter [Problembehandlung](register-devices-self.md#troubleshooting) .</span><span class="sxs-lookup"><span data-stu-id="6b00a-161">Refer to [Troubleshooting](register-devices-self.md#troubleshooting) for more information.</span></span> |
| <span data-ttu-id="6b00a-162">Bereit für Benutzer</span><span class="sxs-lookup"><span data-stu-id="6b00a-162">Ready for user</span></span> | <span data-ttu-id="6b00a-163">Die Registrierung wurde erfolgreich durchgeführt, und das Gerät kann nun an den Endbenutzer übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="6b00a-163">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="6b00a-164">Microsoft Managed Desktop führt Sie durch die erstmalige Einrichtung, daher müssen Sie keine weiteren Vorbereitungen treffen.</span><span class="sxs-lookup"><span data-stu-id="6b00a-164">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="6b00a-165">Aktiv</span><span class="sxs-lookup"><span data-stu-id="6b00a-165">Active</span></span> | <span data-ttu-id="6b00a-166">Das Gerät wurde an den Endbenutzer übermittelt und ist bei Ihrem Mandanten registriert.</span><span class="sxs-lookup"><span data-stu-id="6b00a-166">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="6b00a-167">Dies bedeutet auch, dass Sie das Gerät regelmäßig verwenden.</span><span class="sxs-lookup"><span data-stu-id="6b00a-167">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="6b00a-168">Inaktiven</span><span class="sxs-lookup"><span data-stu-id="6b00a-168">Inactive</span></span> | <span data-ttu-id="6b00a-169">Das Gerät wurde an den Endbenutzer übermittelt und ist bei Ihrem Mandanten registriert.</span><span class="sxs-lookup"><span data-stu-id="6b00a-169">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="6b00a-170">Sie haben das Gerät jedoch erst kürzlich (in den letzten 7 Tagen) verwendet.</span><span class="sxs-lookup"><span data-stu-id="6b00a-170">However, they have not used the device recently (in the last 7 days).</span></span>  | 


## <a name="register-devices-by-using-an-api"></a><span data-ttu-id="6b00a-171">Registrieren von Geräten mithilfe einer API</span><span class="sxs-lookup"><span data-stu-id="6b00a-171">Register devices by using an API</span></span>

<span data-ttu-id="6b00a-172">Eine REST-API steht zur Verfügung, die Ihnen größere Flexibilität und Wiederholbarkeit bei häufigen separaten Geräte Registrierungen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="6b00a-172">A REST API is available to allow you greater flexibility and repeatability with frequent separate device registrations.</span></span> <span data-ttu-id="6b00a-173">Um die API verwenden zu können, bitten Sie Ihre Microsoft Contact um Hilfe, um an einer Vorschau dieser Funktion teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="6b00a-173">Currently, to use the API, ask for help from your Microsoft contact to join a preview of this capability.</span></span>



## <a name="troubleshooting"></a><span data-ttu-id="6b00a-174">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="6b00a-174">Troubleshooting</span></span>

| <span data-ttu-id="6b00a-175">Fehlermeldung</span><span class="sxs-lookup"><span data-stu-id="6b00a-175">Error message</span></span> | <span data-ttu-id="6b00a-176">Details</span><span class="sxs-lookup"><span data-stu-id="6b00a-176">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="6b00a-177">Gerät nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="6b00a-177">Device not found</span></span> | <span data-ttu-id="6b00a-178">Dieses Gerät konnte nicht registriert werden, da keine Übereinstimmung für den angegebenen Hersteller, das Modell oder die Seriennummer gefunden werden konnte.</span><span class="sxs-lookup"><span data-stu-id="6b00a-178">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="6b00a-179">Bestätigen Sie diese Werte mit Ihrem Gerätelieferanten.</span><span class="sxs-lookup"><span data-stu-id="6b00a-179">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="6b00a-180">Gerät nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="6b00a-180">Device not found</span></span> | <span data-ttu-id="6b00a-181">Dieses Gerät kann nicht deregistriert werden, da es in Ihrer Organisation nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="6b00a-181">We couldn’t de-register this device because it does not exist in your organization.</span></span> <span data-ttu-id="6b00a-182">Es ist keine weitere Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6b00a-182">No further action required.</span></span> |
| <span data-ttu-id="6b00a-183">Hardware Hash ist ungültig</span><span class="sxs-lookup"><span data-stu-id="6b00a-183">Hardware hash not valid</span></span> | <span data-ttu-id="6b00a-184">Der für dieses Gerät angegebene Hardwarehash wurde nicht ordnungsgemäß formatiert.</span><span class="sxs-lookup"><span data-stu-id="6b00a-184">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="6b00a-185">Überprüfen Sie den Hardwarehash, und senden Sie ihn erneut.</span><span class="sxs-lookup"><span data-stu-id="6b00a-185">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="6b00a-186">Gerät bereits registriert</span><span class="sxs-lookup"><span data-stu-id="6b00a-186">Device already registered</span></span> | <span data-ttu-id="6b00a-187">Dieses Gerät ist bereits für Ihre Organisation registriert.</span><span class="sxs-lookup"><span data-stu-id="6b00a-187">This device is already registered to your organization.</span></span> <span data-ttu-id="6b00a-188">Es ist keine weitere Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6b00a-188">No further action required.</span></span> |
| <span data-ttu-id="6b00a-189">Von einer anderen Organisation beanspruchtes Gerät</span><span class="sxs-lookup"><span data-stu-id="6b00a-189">Device claimed by another organization</span></span> | <span data-ttu-id="6b00a-190">Dieses Gerät wurde bereits von einer anderen Organisation beansprucht.</span><span class="sxs-lookup"><span data-stu-id="6b00a-190">This device has already been claimed by another organization.</span></span> <span data-ttu-id="6b00a-191">Erkundigen Sie sich bei Ihrem Gerätelieferanten.</span><span class="sxs-lookup"><span data-stu-id="6b00a-191">Check with your device supplier.</span></span> |
| <span data-ttu-id="6b00a-192">Unerwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="6b00a-192">Unexpected error</span></span> | <span data-ttu-id="6b00a-193">Ihre Anforderung konnte nicht automatisch verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="6b00a-193">Your request could not be automatically processed.</span></span> <span data-ttu-id="6b00a-194">Kontaktieren Sie den Support, und geben Sie die Anforderungs-ID an:<requestId></span><span class="sxs-lookup"><span data-stu-id="6b00a-194">Contact Support and provide the Request ID: <requestId></span></span> |




