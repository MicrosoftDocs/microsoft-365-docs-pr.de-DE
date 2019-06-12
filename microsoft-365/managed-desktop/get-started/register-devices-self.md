---
title: Selbst registrieren von Geräten in Microsoft Managed Desktop
description: Geräte selbst registrieren, damit Sie von Microsoft Managed Desktop verwaltet werden können
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: f1e61cfc7fd1d6d597efbfa2480155e06a3d3eb7
ms.sourcegitcommit: d6fcd57a0689abbe4ab47489034f52e327f4e5f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2019
ms.locfileid: "34857298"
---
# <a name="register-devices-in-microsoft-managed-desktop"></a><span data-ttu-id="c1dd0-103">Registrieren von Geräten in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="c1dd0-103">Register devices in Microsoft Managed Desktop</span></span>

>[!NOTE]
><span data-ttu-id="c1dd0-104">In diesem Thema werden die Schritte beschrieben, mit denen Sie Geräte selbst registrieren können.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-104">This topic describes the steps for you to register devices on your own.</span></span> <span data-ttu-id="c1dd0-105">Der Prozess für Partner ist unter [Register Devices in Microsoft Managed Desktop for Partners](register-devices-partner.md)dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-105">The process for Partners is documented in [Register devices in Microsoft Managed Desktop for Partners](register-devices-partner.md).</span></span>

<span data-ttu-id="c1dd0-106">Microsoft Managed Desktop kann mit brandneuen Geräten verwendet werden, oder Sie können Geräte wieder verwenden, die Sie möglicherweise bereits haben (Dies erfordert ein erneutes Abbild).</span><span class="sxs-lookup"><span data-stu-id="c1dd0-106">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="c1dd0-107">Sie können Geräte mithilfe von Microsoft Managed Desktop im Azure-Portal registrieren oder mithilfe einer API Flexibilität erzielen.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-107">You can register devices by using Microsoft Managed Desktop on the Azure Portal or gain flexibility by using an API.</span></span>

## <a name="prepare-to-register-devices"></a><span data-ttu-id="c1dd0-108">Vorbereiten der Registrierung von Geräten</span><span class="sxs-lookup"><span data-stu-id="c1dd0-108">Prepare to register devices</span></span>

<span data-ttu-id="c1dd0-109">Wenn Sie die Geräte, die Sie verwenden möchten, noch nicht erhalten haben, überprüfen Sie [Microsoft Managed Desktop-Geräte](../service-description/device-list.md) , und arbeiten Sie mit einem Geräte Partner zusammen, um unterstützte Geräte zu beschaffen.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-109">If you haven't already obtained the devices you want to use, check [Microsoft Managed Desktop devices](../service-description/device-list.md) and work with a device partner to procure supported devices.</span></span>

<span data-ttu-id="c1dd0-110">Unabhängig davon, ob Sie mit vollständig neuen Geräten arbeiten oder vorhandene wieder verwenden, um Sie bei Microsoft Managed Desktop zu registrieren, müssen Sie eine durch **trennzeichengetrennte CSV-Datei**vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-110">Whether you're working with completely new devices or re-using existing ones, to register them with Microsoft Managed Desktop, you'll need to prepare a **comma-delimited (CSV) file**.</span></span> <span data-ttu-id="c1dd0-111">Diese Datei sollte die folgenden Informationen für jedes Gerät enthalten:</span><span class="sxs-lookup"><span data-stu-id="c1dd0-111">This file should include the following information for each device:</span></span>

>[!NOTE]
><span data-ttu-id="c1dd0-112">Dieses Format ist nur für Self-Service-Registrierungen.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-112">This format is for self-service registration only.</span></span> <span data-ttu-id="c1dd0-113">Die Format Partner sollten in [Register Devices in Microsoft Managed Desktop for Partners](register-devices-partner.md)dokumentiert werden.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-113">The format Partners should use is documented in [Register devices in Microsoft Managed Desktop for Partners](register-devices-partner.md).</span></span>

<span data-ttu-id="c1dd0-114">Diese Werte werden für Anzeigezwecke verwendet und müssen nicht genau mit den Eigenschaften des Geräts übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-114">These values are used for display purposes, and don't need to match properties from the device exactly.</span></span>
- <span data-ttu-id="c1dd0-115">Gerätehersteller (Beispiel: SpiralOrbit)</span><span class="sxs-lookup"><span data-stu-id="c1dd0-115">Device manufacturer (example: SpiralOrbit)</span></span> 
- <span data-ttu-id="c1dd0-116">Gerätemodell (Beispiel: ContosoABC)</span><span class="sxs-lookup"><span data-stu-id="c1dd0-116">Device model (example: ContosoABC)</span></span>
- <span data-ttu-id="c1dd0-117">Seriennummer des Geräts</span><span class="sxs-lookup"><span data-stu-id="c1dd0-117">Device serial number</span></span>

<span data-ttu-id="c1dd0-118">Der Hardwarehash muss eine exakte Übereinstimmung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-118">The hardware hash must be an exact match.</span></span>
- <span data-ttu-id="c1dd0-119">Hardware Hash</span><span class="sxs-lookup"><span data-stu-id="c1dd0-119">Hardware hash</span></span>

<span data-ttu-id="c1dd0-120">Um den Hardwarehash zu erhalten, können Sie Hilfe von Ihrem OEM oder Partner anfordern oder die folgenden Schritte für jedes Gerät durchführen:</span><span class="sxs-lookup"><span data-stu-id="c1dd0-120">To obtain the hardware hash you can ask for help from your OEM or Partner, or follow these steps for each device:</span></span>

1.  <span data-ttu-id="c1dd0-121">Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-121">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="c1dd0-122">Ausführen`Install-Script -Name Get-MMDRegistrationInfo`</span><span class="sxs-lookup"><span data-stu-id="c1dd0-122">Run `Install-Script -Name Get-MMDRegistrationInfo`</span></span>
3.  <span data-ttu-id="c1dd0-123">Ausführen`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="c1dd0-123">Run `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>


<span data-ttu-id="c1dd0-124">Alternativ können Sie diese Schritte auf einem brandneuen Gerät befolgen (bevor Sie die OOBE zum ersten Mal durchgehen):</span><span class="sxs-lookup"><span data-stu-id="c1dd0-124">Alternately, you can follow these steps on a brand-new device (before going through OOBE for the first time):</span></span>

1. <span data-ttu-id="c1dd0-125">Legen Sie auf einem anderen Gerät ein USB-Laufwerk ein.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-125">On a different device, insert a USB drive.</span></span>
2. <span data-ttu-id="c1dd0-126">Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-126">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="c1dd0-127">Ausführen`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="c1dd0-127">Run `Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="c1dd0-128">Aktivieren Sie das Ziel Gerät, starten Sie jedoch nicht die Setup-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-128">Turn on the target device, but do not start the setup experience.</span></span> <span data-ttu-id="c1dd0-129">Wenn Sie das Setupprogramm versehentlich gestartet haben, müssen Sie das Gerät zurücksetzen oder neu abbilden.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-129">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="c1dd0-130">Legen Sie das USB-Laufwerk ein, und drücken Sie dann UMSCHALT + F10.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-130">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="c1dd0-131">Öffnen Sie eine PowerShell-Eingabeaufforderung mit Administratorrechten, `cd <pathToUsb>`und führen Sie dann aus.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-131">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="c1dd0-132">Ausführen`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="c1dd0-132">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="c1dd0-133">Ausführen`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="c1dd0-133">Run `.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
3. <span data-ttu-id="c1dd0-134">Entfernen Sie das USB-Laufwerk, und fahren Sie dann das Gerät herunter, indem Sie`shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="c1dd0-134">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>

>[!IMPORTANT]
><span data-ttu-id="c1dd0-135">Schalten Sie das Zielgerät erst wieder ein, wenn Sie die Registrierung für dieses Gerät abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-135">Do not power on the target device again until you've completed registration for it.</span></span> 

>[!NOTE]
><span data-ttu-id="c1dd0-136">Für Ihre Bequemlichkeit können Sie eine [Vorlage](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) für diese CSV-Datei herunterladen.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-136">For your convenience, you can download a [template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) for this CSV file.</span></span>

<span data-ttu-id="c1dd0-137">Die Datei muss **exakt dieselben Spaltenüberschriften** wie das Beispiel 1 (Hersteller, Modell usw.) enthalten, aber ihre eigenen Daten für die anderen Zeilen.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-137">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="c1dd0-138">Wenn Sie die Vorlage verwenden, öffnen Sie Sie in einem Textbearbeitungstool wie Notepad, und lassen Sie alle Daten in Zeile 1 allein, und geben Sie nur Daten in Zeilen 2 und darunter ein.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-138">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="c1dd0-139">Wenn Sie vergessen, die Beispieldaten zu ändern, tritt bei der Registrierung ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-139">If you forget to change any of the sample data, registration will fail.</span></span>   


## <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="c1dd0-140">Registrieren von Geräten mithilfe des Azure-Portals</span><span class="sxs-lookup"><span data-stu-id="c1dd0-140">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="c1dd0-141">Wählen Sie im linken Navigationsbereich **Geräte** aus dem Microsoft Managed Desktop [Azure-Portal](https://aka.ms/mmdportal)aus.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-141">From the Microsoft Managed Desktop [Azure Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="c1dd0-142">Select **+ Register Devices**; das Einfliegen wird geöffnet:</span><span class="sxs-lookup"><span data-stu-id="c1dd0-142">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="c1dd0-143">[![Einfliegen nach Auswahl von Register Geräten](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="c1dd0-143">[![Fly-in after selecting Register devices](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span></span>


[//]: # (Leider ist dies nicht der Fall. Wir können diese Notiz entfernen – aber jetzt so lange, bis wir eine Möglichkeit haben, darüber zu chatten.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="c1dd0-145">Führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c1dd0-145">Follow these steps:</span></span>

1. <span data-ttu-id="c1dd0-146">Geben Sie im Feld **Dateiupload**einen Pfad zu der CSV-Datei an, die Sie zuvor erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-146">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="c1dd0-147">Optional können Sie eine **Auftrags-ID** oder eine **Einkaufs-ID** für eigene Tracking-Zwecke hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-147">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="c1dd0-148">Für diese Werte gibt es keine Formatanforderungen.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-148">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="c1dd0-149">Wählen Sie **Geräte registrieren**aus.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-149">Select **Register devices**.</span></span> <span data-ttu-id="c1dd0-150">Das System fügt die Geräte zu ihrer Geräteliste auf dem Blade- **Gerät**hinzu, das als " **Registrierung**Ausstehend" gekennzeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-150">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="c1dd0-151">Die Registrierung dauert in der Regel weniger als 10 Minuten, und wenn das Gerät erfolgreich ist, wird es **für den Benutzer bereit** angezeigt, was darauf wartet, dass ein Endbenutzer mit der Verwendung beginnt.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-151">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="c1dd0-152">Sie können den Fortschritt der Geräteregistrierung auf der Hauptseite von **Microsoft Managed Desktop-Devices** überwachen.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-152">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="c1dd0-153">Mögliche Zustände, die dort gemeldet werden, umfassen:</span><span class="sxs-lookup"><span data-stu-id="c1dd0-153">Possible states reported there include:</span></span>

| <span data-ttu-id="c1dd0-154">Status</span><span class="sxs-lookup"><span data-stu-id="c1dd0-154">State</span></span> | <span data-ttu-id="c1dd0-155">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1dd0-155">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="c1dd0-156">Registrierung ausstehend</span><span class="sxs-lookup"><span data-stu-id="c1dd0-156">Registration pending</span></span> | <span data-ttu-id="c1dd0-157">Die Registrierung ist noch nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-157">Registration is not done yet.</span></span> <span data-ttu-id="c1dd0-158">Überprüfen Sie später erneut.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-158">Check back later.</span></span> |
| <span data-ttu-id="c1dd0-159">Registrierung fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="c1dd0-159">Registration failed</span></span> | <span data-ttu-id="c1dd0-160">Die Registrierung konnte nicht abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-160">Registration could not be completed.</span></span> <span data-ttu-id="c1dd0-161">Weitere Informationen erhalten Sie unter [Problembehandlung](register-devices-self.md#troubleshooting) .</span><span class="sxs-lookup"><span data-stu-id="c1dd0-161">Refer to [Troubleshooting](register-devices-self.md#troubleshooting) for more information.</span></span> |
| <span data-ttu-id="c1dd0-162">Benutzer einsatzfähig</span><span class="sxs-lookup"><span data-stu-id="c1dd0-162">Ready for user</span></span> | <span data-ttu-id="c1dd0-163">Die Registrierung wurde erfolgreich ausgeführt, und das Gerät ist jetzt bereit, an den Endbenutzer zugestellt zu werden.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-163">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="c1dd0-164">Microsoft Managed Desktop führt Sie durch die erstmalige Einrichtung, sodass Sie keine weiteren Vorbereitungen treffen müssen.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-164">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="c1dd0-165">Aktiv</span><span class="sxs-lookup"><span data-stu-id="c1dd0-165">Active</span></span> | <span data-ttu-id="c1dd0-166">Das Gerät wurde an den Endbenutzer übermittelt, und Sie haben sich bei Ihrem Mandanten registriert.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-166">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="c1dd0-167">Dies deutet auch darauf hin, dass das Gerät regelmäßig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-167">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="c1dd0-168">Inaktiv</span><span class="sxs-lookup"><span data-stu-id="c1dd0-168">Inactive</span></span> | <span data-ttu-id="c1dd0-169">Das Gerät wurde an den Endbenutzer übermittelt, und Sie haben sich bei Ihrem Mandanten registriert.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-169">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="c1dd0-170">Sie haben das Gerät jedoch vor kurzem nicht verwendet (in den letzten 7 Tagen).</span><span class="sxs-lookup"><span data-stu-id="c1dd0-170">However, they have not used the device recently (in the last 7 days).</span></span>  | 


## <a name="register-devices-by-using-an-api"></a><span data-ttu-id="c1dd0-171">Registrieren von Geräten mithilfe einer API</span><span class="sxs-lookup"><span data-stu-id="c1dd0-171">Register devices by using an API</span></span>

<span data-ttu-id="c1dd0-172">Eine Rest-API steht Ihnen zur Verfügung, um Ihnen größere Flexibilität und Wiederholbarkeit bei häufigen separaten Geräte Registrierungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-172">A REST API is available to allow you greater flexibility and repeatability with frequent separate device registrations.</span></span> <span data-ttu-id="c1dd0-173">Um die API verwenden zu können, bitten Sie Ihren Microsoft-Kontakt um Hilfe, um an einer Vorschau dieser Funktion teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-173">Currently, to use the API, ask for help from your Microsoft contact to join a preview of this capability.</span></span>



## <a name="troubleshooting"></a><span data-ttu-id="c1dd0-174">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="c1dd0-174">Troubleshooting</span></span>

| <span data-ttu-id="c1dd0-175">Fehlermeldung</span><span class="sxs-lookup"><span data-stu-id="c1dd0-175">Error message</span></span> | <span data-ttu-id="c1dd0-176">Details</span><span class="sxs-lookup"><span data-stu-id="c1dd0-176">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="c1dd0-177">Gerät nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="c1dd0-177">Device not found</span></span> | <span data-ttu-id="c1dd0-178">Dieses Gerät konnte nicht registriert werden, da keine Übereinstimmung für den bereitgestellten Hersteller, das Modell oder die Seriennummer gefunden werden konnte.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-178">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="c1dd0-179">Bestätigen Sie diese Werte mit Ihrem Gerätelieferanten.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-179">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="c1dd0-180">Gerät nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="c1dd0-180">Device not found</span></span> | <span data-ttu-id="c1dd0-181">Dieses Gerät konnte nicht registriert werden, da es in Ihrer Organisation nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-181">We couldn’t de-register this device because it does not exist in your organization.</span></span> <span data-ttu-id="c1dd0-182">Keine weitere Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-182">No further action required.</span></span> |
| <span data-ttu-id="c1dd0-183">Hardware Hash ungültig</span><span class="sxs-lookup"><span data-stu-id="c1dd0-183">Hardware hash not valid</span></span> | <span data-ttu-id="c1dd0-184">Der für dieses Gerät angegebene Hardwarehash wurde nicht ordnungsgemäß formatiert.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-184">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="c1dd0-185">Überprüfen Sie den Hardwarehash doppelt, und senden Sie dann erneut.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-185">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="c1dd0-186">Gerät ist bereits registriert</span><span class="sxs-lookup"><span data-stu-id="c1dd0-186">Device already registered</span></span> | <span data-ttu-id="c1dd0-187">Dieses Gerät ist bereits für Ihre Organisation registriert.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-187">This device is already registered to your organization.</span></span> <span data-ttu-id="c1dd0-188">Keine weitere Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-188">No further action required.</span></span> |
| <span data-ttu-id="c1dd0-189">Von einer anderen Organisation beanspruchtes Gerät</span><span class="sxs-lookup"><span data-stu-id="c1dd0-189">Device claimed by another organization</span></span> | <span data-ttu-id="c1dd0-190">Dieses Gerät wurde bereits von einer anderen Organisation beansprucht.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-190">This device has already been claimed by another organization.</span></span> <span data-ttu-id="c1dd0-191">Erkundigen Sie sich bei Ihrem Gerätelieferanten.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-191">Check with your device supplier.</span></span> |
| <span data-ttu-id="c1dd0-192">Unerwarteter Fehler</span><span class="sxs-lookup"><span data-stu-id="c1dd0-192">Unexpected error</span></span> | <span data-ttu-id="c1dd0-193">Ihre Anforderung konnte nicht automatisch verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="c1dd0-193">Your request could not be automatically processed.</span></span> <span data-ttu-id="c1dd0-194">Kontaktieren Sie den Support, und geben Sie die Anforderungs-ID an:<requestId></span><span class="sxs-lookup"><span data-stu-id="c1dd0-194">Contact Support and provide the Request ID: <requestId></span></span> |




