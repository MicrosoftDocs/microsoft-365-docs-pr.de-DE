---
title: Zusätzliche Geräteinformationen für die Migration von Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Zusammenfassung: Zusätzliche Geräteinformationen für Dienste beim Übergang von Microsoft Cloud Germany (Microsoft Cloud Deutschland) zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen.'
ms.openlocfilehash: 27426a26befab85bf62a0a143861e447dd722724
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861304"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="d3727-103">Zusätzliche Geräteinformationen für die Migration von Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="d3727-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="d3727-104">Mit Azure AD verbundene und registrierte Geräte, die mit Microsoft Cloud Deutschland verbunden sind, müssen nach Phase 9 und vor Phase 10 migriert werden.</span><span class="sxs-lookup"><span data-stu-id="d3727-104">Azure AD joined and registered devices connected to Microsoft Cloud Deutschland must be migrated after phase 9 and before phase 10.</span></span> <span data-ttu-id="d3727-105">Die Migration eines Geräts hängt vom Gerätetyp, dem Betriebssystem und der AAD-Beziehung ab.</span><span class="sxs-lookup"><span data-stu-id="d3727-105">The migration of a device depends on the devices type, operating system and AAD relation.</span></span> 

## <a name="frequently-asked-questions"></a><span data-ttu-id="d3727-106">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="d3727-106">Frequently asked questions</span></span>

<span data-ttu-id="d3727-107">**Wie kann ich feststellen, ob meine Organisation betroffen ist?**</span><span class="sxs-lookup"><span data-stu-id="d3727-107">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="d3727-108">Administratoren sollten `https://portal.microsoftazure.de` überprüfen, ob sie über registrierte oder in Azure AD eingebundene Geräte verfügen.</span><span class="sxs-lookup"><span data-stu-id="d3727-108">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered or Azure AD joined devices.</span></span> <span data-ttu-id="d3727-109">Wenn Ihre Organisation registrierte Geräte hat, sind Sie betroffen.</span><span class="sxs-lookup"><span data-stu-id="d3727-109">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="d3727-110">**Was sind die Auswirkungen für meine Benutzer?**</span><span class="sxs-lookup"><span data-stu-id="d3727-110">**What is the impact on my users?**</span></span>

<span data-ttu-id="d3727-111">Benutzer von einem registrierten Gerät können sich nach Abschluss der [Migrationsphase 10](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) nicht mehr anmelden, und die Endpunkte für Microsoft Cloud Deutschland wurden deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="d3727-111">Users from a registered device will no longer be able to sign in after [migration phase 10](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed and the endpoints for Microsoft Cloud Deutschland have been disabled.</span></span>  

<span data-ttu-id="d3727-112">Stellen Sie sicher, dass all Ihre Geräte mit dem weltweiten Endpunkt registriert sind, bevor die Verbindung Ihrer Organisation mit Microsoft Cloud Deutschland aufgehoben wird.</span><span class="sxs-lookup"><span data-stu-id="d3727-112">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="d3727-113">**Wann müssen meine Benutzer Ihre Geräte wieder registrieren?**</span><span class="sxs-lookup"><span data-stu-id="d3727-113">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="d3727-114">Für Ihren Erfolg ist es wichtig, dass Sie die Registrierung ihrer Geräte erst nach Abschluss der [Phase 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) aufheben und erneut registrieren.</span><span class="sxs-lookup"><span data-stu-id="d3727-114">It's critical to your success that you only unregister and re-register your devices after [phase 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed.</span></span> <span data-ttu-id="d3727-115">Sie müssen die erneute Registrierung vor Beginn der Phase 10 abschließen, andernfalls könnten Sie den Zugriff auf Ihr Gerät verlieren.</span><span class="sxs-lookup"><span data-stu-id="d3727-115">You must finish the re-registration before phase 10 starts, otherwise you could lose access to your device.</span></span>

<span data-ttu-id="d3727-116">**Wie kann ich meinen Gerätstatus nach der Migration wiederherstellen?**</span><span class="sxs-lookup"><span data-stu-id="d3727-116">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="d3727-117">Für unternehmenseigene Windows Geräte, die bei Azure AD registriert sind, können Administratoren die Migration dieser Geräte über remote ausgelöste Workflows verwalten, die die Registrierung der alten Gerätezustände aufheben.</span><span class="sxs-lookup"><span data-stu-id="d3727-117">For company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="d3727-118">Für alle anderen Geräte, einschließliche persönliche Windows-Geräte, die in Azure AD registriert sind, muss der Benutzer diese Schritte manuell ausführen.</span><span class="sxs-lookup"><span data-stu-id="d3727-118">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="d3727-119">Für mit Azure AD verbundene Geräte müssen Benutzer ein lokales Administratorkonto haben, um ihre Geräte abzumelden und dann wieder zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="d3727-119">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="d3727-120">Ausführliche Anweisungen zum erfolgreichen Wiederherstellen von Gerätezuständen finden Sie weiter unten.</span><span class="sxs-lookup"><span data-stu-id="d3727-120">Please refer to detailed instructions for how to successfully restore device states below.</span></span> 
 
<span data-ttu-id="d3727-121">**Wie stelle ich fest, ob alle meine Geräte in der Public Cloud registriert sind?**</span><span class="sxs-lookup"><span data-stu-id="d3727-121">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="d3727-122">Um zu prüfen, ob Ihre Geräte in der Public Cloud registriert sind, sollten Sie die Liste der Geräte aus dem Azure AD-Portal in eine Excel-Tabelle exportieren und herunterladen.</span><span class="sxs-lookup"><span data-stu-id="d3727-122">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="d3727-123">Filtern Sie danach die registrierten Geräte (verwenden Sie die Spalte _registeredTime_) nach der Migrationsphase [Trennen von der Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized).</span><span class="sxs-lookup"><span data-stu-id="d3727-123">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="d3727-124">Zusätzliche Überlegungen</span><span class="sxs-lookup"><span data-stu-id="d3727-124">Additional considerations</span></span>
<span data-ttu-id="d3727-125">Die Geräteregistrierung ist nach der Migration des Mandanten deaktiviert und kann nicht mehr aktiviert oder deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="d3727-125">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> 

<span data-ttu-id="d3727-126">Wenn Sie Intune nicht verwenden, melden Sie sich bei Ihrem Abonnement an und führen Sie folgenden Befehl aus, um die Option wieder zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="d3727-126">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```
<span data-ttu-id="d3727-127">**WICHTIG:** Der Intune-Dienstprinzipal wird nach der Commerce-Migration aktiviert, was die Aktivierung von Azure AD Device Registration impliziert.</span><span class="sxs-lookup"><span data-stu-id="d3727-127">**IMPORTANT:** The Intune service principal will be enabled after commerce migration, which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="d3727-128">Wenn Sie Azure AD Device Registration vor der Migration blockiert haben, müssen Sie den Intune-Dienstprinzipal mit PowerShell deaktivieren, um die Azure AD-Geräteregistrierung mit dem Azure AD-Portal erneut zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="d3727-128">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="d3727-129">Sie können den Intune-Dienstprinzipal mit diesem Befehl im Azure Active Directory PowerShell für Graph-Modul deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="d3727-129">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```


## <a name="azure-ad-join"></a><span data-ttu-id="d3727-130">Azure AD Join</span><span class="sxs-lookup"><span data-stu-id="d3727-130">Azure AD Join</span></span>
<span data-ttu-id="d3727-131">Dies gilt für Windows 10 Geräte.</span><span class="sxs-lookup"><span data-stu-id="d3727-131">This applies to Windows 10 devices.</span></span> 

<span data-ttu-id="d3727-132">Wenn ein Gerät mit Azure AD verbunden ist, muss es von Azure AD getrennt und erneut verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="d3727-132">If a device is Azure AD joined, it must be disconnected from Azure AD and be connected again.</span></span> 

<span data-ttu-id="d3727-133">[![Azure AD-GeräteRe-Join Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d3727-133">[ ![Azure AD Device Re-Join Flow](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png) ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span></span>


<span data-ttu-id="d3727-134">Wenn der Benutzer ein Administrator auf dem Windows 10 Gerät ist, kann der Benutzer die Registrierung des Geräts bei Azure AD aufheben und es erneut verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="d3727-134">If the user is an administrator on the Windows 10 device, the user can unregister the device from Azure AD and re-join it again.</span></span> <span data-ttu-id="d3727-135">Wenn er über keine Administratorrechte verfügt, benötigt der Benutzer Anmeldeinformationen eines lokalen Administratorkontos auf diesem Computer.</span><span class="sxs-lookup"><span data-stu-id="d3727-135">If he has no administrator privileges, the user needs credentials of a local administrator account on this machine.</span></span> 


<span data-ttu-id="d3727-136">Ein Administrator kann ein lokales Administratorkonto auf dem Gerät erstellen, das folgendem Konfigurationspfad folgt:</span><span class="sxs-lookup"><span data-stu-id="d3727-136">An Administrator can create an local administrator account on the device following this configuration path:</span></span>

<span data-ttu-id="d3727-137">*Einstellungen > Konten > Andere Konten > Anmeldeinformationen unbekannt > Benutzer ohne Microsoft-Konto hinzufügen*</span><span class="sxs-lookup"><span data-stu-id="d3727-137">*Settings > Accounts > Other Accounts > Credentials unknown > Add user without Microsoft-Account*</span></span>

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a><span data-ttu-id="d3727-138">Schritt 1: Ermitteln, ob das Gerät mit azure-ID verknüpft ist</span><span class="sxs-lookup"><span data-stu-id="d3727-138">Step 1: Determine if the device is Azure ID joined</span></span>
1.  <span data-ttu-id="d3727-139">Melden Sie sich mit E-Mail-Adresse und Kennwort des Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="d3727-139">Sign In with users E-mail and password.</span></span>
2.  <span data-ttu-id="d3727-140">Wechseln Sie zu Einstellungen > Konten, > auf Arbeits- oder Schulkonto zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d3727-140">Go to Settings > Accounts > Access Work Or School.</span></span> 
3.  <span data-ttu-id="d3727-141">Suchen Sie nach einem Benutzer in der Liste, der **mit ... Azure AD .**</span><span class="sxs-lookup"><span data-stu-id="d3727-141">Look for a user in the list with **connected to … ‘s Azure AD**.</span></span> 
4.  <span data-ttu-id="d3727-142">Wenn ein verbundener Benutzer vorhanden ist, fahren Sie mit Schritt 2 fort.</span><span class="sxs-lookup"><span data-stu-id="d3727-142">If a connected user exists, proceed with Step 2.</span></span> <span data-ttu-id="d3727-143">Wenn nicht, ist keine weitere Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d3727-143">If not, no further action is required.</span></span>
### <a name="step-2-disconnect-the-device-from-azure-ad"></a><span data-ttu-id="d3727-144">Schritt 2: Trennen des Geräts von Azure AD</span><span class="sxs-lookup"><span data-stu-id="d3727-144">Step 2: Disconnect the device from Azure AD</span></span>
1.  <span data-ttu-id="d3727-145">Tippen Sie auf **"Trennen"** für das verbundene Geschäfts-, Schul- oder Unikonto.</span><span class="sxs-lookup"><span data-stu-id="d3727-145">Tap **Disconnect** on the connected work or School Account.</span></span> 
2.  <span data-ttu-id="d3727-146">Bestätigen Sie die Verbindung zweimal.</span><span class="sxs-lookup"><span data-stu-id="d3727-146">Confirm the disconnect twice.</span></span> 
3.  <span data-ttu-id="d3727-147">Geben Sie den Benutzernamen und das Kennwort des lokalen Administrators ein.</span><span class="sxs-lookup"><span data-stu-id="d3727-147">Enter the local administrator username and password.</span></span> <span data-ttu-id="d3727-148">Das Gerät wird getrennt.</span><span class="sxs-lookup"><span data-stu-id="d3727-148">The device is disconnected.</span></span>
4.  <span data-ttu-id="d3727-149">Starten Sie das Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="d3727-149">Restart the device.</span></span>
### <a name="step-3-join-the-device-to-azure-ad"></a><span data-ttu-id="d3727-150">Schritt 3: Verknüpfen des Geräts mit Azure AD</span><span class="sxs-lookup"><span data-stu-id="d3727-150">Step 3: Join the device to Azure AD</span></span>
1.  <span data-ttu-id="d3727-151">Der Benutzer meldet sich mit den Anmeldeinformationen des lokalen Administrators an.</span><span class="sxs-lookup"><span data-stu-id="d3727-151">the user signs in with the credentials of the local administrator</span></span>
2.  <span data-ttu-id="d3727-152">Wechseln Sie zu **Einstellungen** **dann** konten, und greifen Sie dann auf Arbeit oder **Schule zu**</span><span class="sxs-lookup"><span data-stu-id="d3727-152">Go to **Settings** then **Accounts** then **Access Work Or School**</span></span>
3.  <span data-ttu-id="d3727-153">Tippen **auf Verbinden**</span><span class="sxs-lookup"><span data-stu-id="d3727-153">Tap **Connect**</span></span>
4.  <span data-ttu-id="d3727-154">**WICHTIG:** Tippen **Sie auf "Beitritt zu Azure AD"**</span><span class="sxs-lookup"><span data-stu-id="d3727-154">**IMPORTANT**: Tap **Join to Azure AD**</span></span>
5.  <span data-ttu-id="d3727-155">Geben Sie die E-Mail-Adresse und das Kennwort des Benutzers ein.</span><span class="sxs-lookup"><span data-stu-id="d3727-155">Enter the e-mail address and password of the user.</span></span> <span data-ttu-id="d3727-156">Das Gerät ist verbunden</span><span class="sxs-lookup"><span data-stu-id="d3727-156">The device is connected</span></span>
6.  <span data-ttu-id="d3727-157">Starten Sie das Gerät neu.</span><span class="sxs-lookup"><span data-stu-id="d3727-157">Restart the device</span></span> 
7.  <span data-ttu-id="d3727-158">sign with your e-mail address and password</span><span class="sxs-lookup"><span data-stu-id="d3727-158">sign with your e-mail address and password</span></span>

## <a name="azure-ad-registered-company-owned"></a><span data-ttu-id="d3727-159">Azure AD-registriert (Unternehmensbesitz)</span><span class="sxs-lookup"><span data-stu-id="d3727-159">Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="d3727-160">Um herauszufinden, ob ein Windows 10-Gerät Azure AD-registriert ist, führen Sie auf dem Gerät folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="d3727-160">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="d3727-161">Wenn das Gerät Azure AD-registriert ist, würden Sie folgende Ausgabe sehen:</span><span class="sxs-lookup"><span data-stu-id="d3727-161">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="d3727-162">Um das bestehende Azure AD-registrierte Konto auf dem Gerät zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="d3727-162">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="d3727-163">Um das bestehende Azure AD-registrierte Konto auf dem Gerät zu entfernen verwenden Sie CleanupWPJ, ein Tool, das Sie hier herunterladen können: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span><span class="sxs-lookup"><span data-stu-id="d3727-163">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="d3727-164">Extrahieren Sie die ZIP-Datei und führen Sie **WPJCleanup.cmd** aus.</span><span class="sxs-lookup"><span data-stu-id="d3727-164">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="d3727-165">Dieses Tool wird basierend auf der Windows-Version auf dem Gerät die richtige ausführbare Datei starten.</span><span class="sxs-lookup"><span data-stu-id="d3727-165">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="d3727-166">Wenn Sie einen Mechanismus wie die Gruppenrichtlinie verwenden, kann der Administrator den Befehl im Kontext jedes auf dem Gerät angemeldeten Benutzers ausführen.</span><span class="sxs-lookup"><span data-stu-id="d3727-166">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="d3727-167">Um die Web Account Manager-Eingabeaufforderungen zur Registrierung des Geräts in Azure AD zu deaktivieren, fügen Sie folgenden Registry-Wert hinzu:</span><span class="sxs-lookup"><span data-stu-id="d3727-167">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="d3727-168">Ort: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="d3727-168">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="d3727-169">Typ: DWORD (32 bit)</span><span class="sxs-lookup"><span data-stu-id="d3727-169">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="d3727-170">Name: BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="d3727-170">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="d3727-171">Wertdaten: 1</span><span class="sxs-lookup"><span data-stu-id="d3727-171">Value data: 1</span></span>

<span data-ttu-id="d3727-172">Das Vorhandensein dieses Registry-Werts sollte die Arbeitsplatz-Verknüpfung blockieren und verhindern, dass Benutzer Eingabeaufforderungen zum Verknüpfen des Geräts sehen.</span><span class="sxs-lookup"><span data-stu-id="d3727-172">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="d3727-173">Android</span><span class="sxs-lookup"><span data-stu-id="d3727-173">Android</span></span>

<span data-ttu-id="d3727-174">Für Android müssen Benutzer ihre Geräte abmelden und wieder registrieren.</span><span class="sxs-lookup"><span data-stu-id="d3727-174">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="d3727-175">Dies kann mit der Microsoft Authenticator-App oder der Unternehmensportal-App geschehen.</span><span class="sxs-lookup"><span data-stu-id="d3727-175">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="d3727-176">Aus der Microsoft Authenticator-App können die Benutzer zu **Einstellungen > Geräteregistrierung** gehen.</span><span class="sxs-lookup"><span data-stu-id="d3727-176">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="d3727-177">Von dort aus können die Benutzer ihre Geräte abmelden und wieder registrieren.</span><span class="sxs-lookup"><span data-stu-id="d3727-177">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="d3727-178">Aus dem Unternehmensportal können die Benutzer zu Registerkarte **Geräte** gehen und das Gerät entfernen.</span><span class="sxs-lookup"><span data-stu-id="d3727-178">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="d3727-179">Danach registrieren Sie das Gerät erneut über das Unternehmensportal.</span><span class="sxs-lookup"><span data-stu-id="d3727-179">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="d3727-180">Benutzer können das Gerät auch abmelden und wieder registrieren, indem Sie das Konto von der Seite „Kontoeinstellungen“ entfernen und dann das Geschäftskonto wieder hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d3727-180">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="d3727-181">Um das Gerät mit der Microsoft Authenticator-App auf Android abzumelden und wieder zu registrieren:</span><span class="sxs-lookup"><span data-stu-id="d3727-181">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="d3727-182">Öffnen Sie die Microsoft Authenticator-App und gehen Sie zu **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="d3727-182">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="d3727-183">Wählen Sie **Geräteregistrierung**.</span><span class="sxs-lookup"><span data-stu-id="d3727-183">Select **Device registration**.</span></span>
3.  <span data-ttu-id="d3727-184">Melden Sie das Gerät ab, indem Sie **Registrierung aufheben** auswählen.</span><span class="sxs-lookup"><span data-stu-id="d3727-184">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="d3727-185">Für die **Geräteregistrierung** registrieren Sie das Gerät erneut, indem Sie Ihre E-Mail-Adresse eingeben und **Registrieren** auswählen.</span><span class="sxs-lookup"><span data-stu-id="d3727-185">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="d3727-186">Um ein Android-Gerät mit der Seite für Android-Einstellungen abzumelden und wieder zu registrieren:</span><span class="sxs-lookup"><span data-stu-id="d3727-186">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="d3727-187">Öffnen Sie **Geräteeinstellungen** und gehen sie zu **Konten**.</span><span class="sxs-lookup"><span data-stu-id="d3727-187">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="d3727-188">Wählen das Geschäftskonto aus, das Sie wieder registrieren wollen und wählen Sie **Konto entfernen**.</span><span class="sxs-lookup"><span data-stu-id="d3727-188">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="d3727-189">Nachdem das Konto entfernt wurde, wählen Sie von der **Konto**-Seite aus **Konto hinzufügen > Geschäftskonto**.</span><span class="sxs-lookup"><span data-stu-id="d3727-189">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="d3727-190">Für die **Arbeitsplatz-Verknüpfung** geben Sie Ihre E-Mail-Adresse ein und wählen Sie **Verknüpfung**, um die Registrierung des Geräts abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="d3727-190">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="d3727-191">Um das Gerät auf Android über das Unternehmensportal abzumelden und neu zu registrieren:</span><span class="sxs-lookup"><span data-stu-id="d3727-191">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="d3727-192">Starten Sie das Unternehmensportal und gehen Sie zur Registerkarte **Geräte**.</span><span class="sxs-lookup"><span data-stu-id="d3727-192">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="d3727-193">Wählen Sie das Gerät aus, um die Gerätedetails zu sehen.</span><span class="sxs-lookup"><span data-stu-id="d3727-193">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="d3727-194">Aus dem Ellipsen-Menü (drei Punkte) wählen Sie **Gerät entfernen** und schließen das Entfernen ab, indem Sie dies im Dialogfeld bestätigen.</span><span class="sxs-lookup"><span data-stu-id="d3727-194">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="d3727-195">Sie sollten jetzt von der Unternehmensportal-App abgemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="d3727-195">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="d3727-196">Wählen Sie **Anmelden**, um das Gerät wieder zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="d3727-196">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="d3727-197">Weitere Informationen zu Aktionen, die während der Migrationsphase dieses Workloads erforderlich sind, oder zu Auswirkungen auf die Verwaltung oder Verwendung finden Sie in den Informationen zu Azure Active Directory (Azure AD) unter [Zusätzliche Azure AD-Informationen für die Migration von Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span><span class="sxs-lookup"><span data-stu-id="d3727-197">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="d3727-198">iOS</span><span class="sxs-lookup"><span data-stu-id="d3727-198">iOS</span></span>

<span data-ttu-id="d3727-199">Auf iOS-Geräten muss ein Benutzer alle zwischengespeicherten Konten manuell aus dem Microsoft Authenticator entfernen, die Registrierung des Geräts aufheben und sich von allen nativen Apps auf dem Gerät abmelden.</span><span class="sxs-lookup"><span data-stu-id="d3727-199">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="d3727-200">Schritt 1: Wenn vorhanden, entfernen Sie das Konto aus der Microsoft Authenticator-App</span><span class="sxs-lookup"><span data-stu-id="d3727-200">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="d3727-201">Tippen Sie auf des Konto in der Microsoft Authenticator-App.</span><span class="sxs-lookup"><span data-stu-id="d3727-201">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="d3727-202">Tippen Sie auf das Symbol **Einstellungen** in der oberen rechten Ecke. </span><span class="sxs-lookup"><span data-stu-id="d3727-202">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="d3727-203">Wenn Sie das Symbol **Einstellungen** nicht sehen, verwenden Sie möglicherweise nicht die aktuelle Version des Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="d3727-203">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="d3727-204">Tippen Sie die Schaltfläche **Konto entfernen**.</span><span class="sxs-lookup"><span data-stu-id="d3727-204">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="d3727-205">Tippen Sie auf **Alle Apps auf diesem Gerät**.</span><span class="sxs-lookup"><span data-stu-id="d3727-205">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="d3727-206">Schritt 2: Registrierung des Geräts in der Microsoft Authenticator-App aufheben</span><span class="sxs-lookup"><span data-stu-id="d3727-206">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="d3727-207">Tippen Sie auf das Menu-Symbol in der oberen rechten Ecke. </span><span class="sxs-lookup"><span data-stu-id="d3727-207">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="d3727-208">Tippen Sie **Einstellungen** und dann **Geräteregistrierung**.</span><span class="sxs-lookup"><span data-stu-id="d3727-208">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="d3727-209">Wenn Ihr Konto angezeigt wird, tippen Sie im Dialog auf **Registrierung des Geräts aufheben** und **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d3727-209">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="d3727-210">Sie sollten danach kein Konto mehr sehen.</span><span class="sxs-lookup"><span data-stu-id="d3727-210">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="d3727-211">Schritt 3: Abmelden aus individuellen Apps wenn notwendig.</span><span class="sxs-lookup"><span data-stu-id="d3727-211">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="d3727-212">Benutzer können zu individuellen Apps wie Outlook, Teams oder OneDrive wechseln und Konten aus diese Apps entfernen.</span><span class="sxs-lookup"><span data-stu-id="d3727-212">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="d3727-213">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d3727-213">More information</span></span>

<span data-ttu-id="d3727-214">Erste Schritte:</span><span class="sxs-lookup"><span data-stu-id="d3727-214">Getting started:</span></span>

- [<span data-ttu-id="d3727-215">Migration von Microsoft Cloud Deutschland zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen</span><span class="sxs-lookup"><span data-stu-id="d3727-215">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="d3727-216">Hilfe zur Microsoft Cloud Deutschland-Migration Assistance</span><span class="sxs-lookup"><span data-stu-id="d3727-216">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="d3727-217">So können Sie sich für die Migration anmelden</span><span class="sxs-lookup"><span data-stu-id="d3727-217">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="d3727-218">Kundenerfahrung während der Migration</span><span class="sxs-lookup"><span data-stu-id="d3727-218">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="d3727-219">Der Weg durch die Umstellung:</span><span class="sxs-lookup"><span data-stu-id="d3727-219">Moving through the transition:</span></span>

- [<span data-ttu-id="d3727-220">Phasen, Aktionen und Auswirkungen der Migration</span><span class="sxs-lookup"><span data-stu-id="d3727-220">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="d3727-221">Zusätzliche Vorarbeit</span><span class="sxs-lookup"><span data-stu-id="d3727-221">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="d3727-222">Zusätzliche Informationen zu [Azure AD](ms-cloud-germany-transition-azure-ad.md), [Geräte](ms-cloud-germany-transition-add-devices.md), [Erfahrungen](ms-cloud-germany-transition-add-experience.md) und [AD FS](ms-cloud-germany-transition-add-adfs.md).</span><span class="sxs-lookup"><span data-stu-id="d3727-222">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="d3727-223">Cloud-Apps:</span><span class="sxs-lookup"><span data-stu-id="d3727-223">Cloud apps:</span></span>

- [<span data-ttu-id="d3727-224">Informationen zum Dynamics 365-Migrationsprogramm</span><span class="sxs-lookup"><span data-stu-id="d3727-224">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="d3727-225">Informationen zum Power BI-Migrationsprogramm</span><span class="sxs-lookup"><span data-stu-id="d3727-225">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="d3727-226">Erste Schritte mit dem Upgrade von Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d3727-226">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)