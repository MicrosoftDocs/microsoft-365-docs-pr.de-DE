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
ms.openlocfilehash: 151fcac882dc91d96df3ece000c28d1a7abe1d1f
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780296"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="c31da-103">Zusätzliche Geräteinformationen für die Migration von Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="c31da-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="c31da-104">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="c31da-104">Frequently asked questions</span></span>

<span data-ttu-id="c31da-105">**Wie kann ich feststellen, ob meine Organisation betroffen ist?**</span><span class="sxs-lookup"><span data-stu-id="c31da-105">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="c31da-106">Administratoren sollten `https://portal.microsoftazure.de` überprüfen, um festzustellen, ob sie registrierte Geräte haben.</span><span class="sxs-lookup"><span data-stu-id="c31da-106">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered devices.</span></span> <span data-ttu-id="c31da-107">Wenn Ihre Organisation registrierte Geräte hat, sind Sie betroffen.</span><span class="sxs-lookup"><span data-stu-id="c31da-107">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="c31da-108">**Was sind die Auswirkungen für meine Benutzer?**</span><span class="sxs-lookup"><span data-stu-id="c31da-108">**What is the impact on my users?**</span></span>

<span data-ttu-id="c31da-109">Benutzer mit registrierten Geräten können sich nicht mehr anmelden, sobald Ihre Migration mit der Migrationsphase [Azure AD abschließen](ms-cloud-germany-transition.md#how-is-the-migration-organized) beginnt.</span><span class="sxs-lookup"><span data-stu-id="c31da-109">Users from a registered device will no longer be able to sign in after your migration enters the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>  

<span data-ttu-id="c31da-110">Stellen Sie sicher, dass all Ihre Geräte mit dem weltweiten Endpunkt registriert sind, bevor die Verbindung Ihrer Organisation mit Microsoft Cloud Deutschland aufgehoben wird.</span><span class="sxs-lookup"><span data-stu-id="c31da-110">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="c31da-111">**Wann müssen meine Benutzer Ihre Geräte wieder registrieren?**</span><span class="sxs-lookup"><span data-stu-id="c31da-111">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="c31da-112">Es ist für Ihren Erfolg kritisch, dass Sie Ihre Geräte nur während der Migrationsphase [Trennen von Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) abmelden und wieder registrieren.</span><span class="sxs-lookup"><span data-stu-id="c31da-112">It's critical to your success that you only unregister and re-register your devices during the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="c31da-113">**Wie kann ich meinen Gerätstatus nach der Migration wiederherstellen?**</span><span class="sxs-lookup"><span data-stu-id="c31da-113">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="c31da-114">Bei mit Azure AD Hybrid verbundenen und bei firmeneigenen Windows-Geräten, die bei Azure AD registriert sind, können Administratoren die Migration dieser Geräte über remote ausgelöste Workflows verwalten, bei denen die Registrierung der alten Gerätezustände aufgehoben wird.</span><span class="sxs-lookup"><span data-stu-id="c31da-114">For hybrid Azure AD–joined and company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="c31da-115">Für alle anderen Geräte, einschließliche persönliche Windows-Geräte, die in Azure AD registriert sind, muss der Benutzer diese Schritte manuell ausführen.</span><span class="sxs-lookup"><span data-stu-id="c31da-115">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="c31da-116">Für mit Azure AD verbundene Geräte müssen Benutzer ein lokales Administratorkonto haben, um ihre Geräte abzumelden und dann wieder zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="c31da-116">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="c31da-117">Microsoft wird Anweisungen veröffentlichen, wie Sie den Gerätestatus erfolgreich wiederherstellen können.</span><span class="sxs-lookup"><span data-stu-id="c31da-117">Microsoft will publish instructions for how to successfully restore device state.</span></span> 
 
<span data-ttu-id="c31da-118">**Wie stelle ich fest, ob alle meine Geräte in der Public Cloud registriert sind?**</span><span class="sxs-lookup"><span data-stu-id="c31da-118">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="c31da-119">Um zu prüfen, ob Ihre Geräte in der Public Cloud registriert sind, sollten Sie die Liste der Geräte aus dem Azure AD-Portal in eine Excel-Tabelle exportieren und herunterladen.</span><span class="sxs-lookup"><span data-stu-id="c31da-119">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="c31da-120">Filtern Sie danach die registrierten Geräte (verwenden Sie die Spalte _registeredTime_) nach der Migrationsphase [Trennen von der Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized).</span><span class="sxs-lookup"><span data-stu-id="c31da-120">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="c31da-121">Die Geräteregistrierung ist nach der Migration des Mandanten deaktiviert und kann nicht mehr aktiviert oder deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="c31da-121">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> <span data-ttu-id="c31da-122">Wenn Sie Intune nicht verwenden, melden Sie sich bei Ihrem Abonnement an und führen Sie folgenden Befehl aus, um die Option wieder zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="c31da-122">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="hybrid-azure-ad-join"></a><span data-ttu-id="c31da-123">Hybride Einbindung in Azure AD</span><span class="sxs-lookup"><span data-stu-id="c31da-123">Hybrid Azure AD join</span></span>

### <a name="windows-down-level"></a><span data-ttu-id="c31da-124">Kompatibles Windows</span><span class="sxs-lookup"><span data-stu-id="c31da-124">Windows down-level</span></span>

<span data-ttu-id="c31da-125">_Kompatible Windows-Geräte_ sind Windows-Geräte, welche eine frühere Version von Windows ausführen (wie z. B. Windows 8.1 oder Windows 7), oder die Windows Server-Versionen vor 2019 und 2016 ausführen.</span><span class="sxs-lookup"><span data-stu-id="c31da-125">_Windows down-level devices_ are Windows devices that currently run earlier versions of Windows (such as Windows 8.1 or Windows 7), or that run Windows Server versions earlier than 2019 and 2016.</span></span> <span data-ttu-id="c31da-126">Wenn solche Geräte früher registriert wurden, müssen Sie diese Geräte abmelden und wieder registrieren.</span><span class="sxs-lookup"><span data-stu-id="c31da-126">If such devices were registered before, you'll need to unregister and re-register those devices.</span></span> 

<span data-ttu-id="c31da-127">Um herauszufinden, ob ein kompatibles Windows-Gerät früher mit Azure AD verbunden wurde, führen Sie auf dem Gerät folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c31da-127">To determine whether a Windows down-level device was previously joined to Azure AD, use following command on the device:</span></span>

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

<span data-ttu-id="c31da-128">Wenn das Gerät früher mit Azure AD verbunden war, und wenn das Gerät eine Netzwerkverbindung mit globalen Azure AD-Endpunkten hat, würden Sie die folgende Ausgabe sehen:</span><span class="sxs-lookup"><span data-stu-id="c31da-128">If the device was previously joined to Azure AD, and if the device has network connectivity to global Azure AD endpoints, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device Details                                                       |
+----------------------------------------------------------------------+
         DeviceId : AEE2B956-DA62-48D0-BB47-046DD992A110
       Thumbprint : 00fdfa2de5c32feae57489873a13aa6a3ff7433b
             User : user1@<tenantname>.de
Private key state : Okay
     Device state : Unknown
```

<span data-ttu-id="c31da-129">Die betroffenen Geräte werden einen „Gerätestatus“ mit Wert „Unbekannt“ haben.</span><span class="sxs-lookup"><span data-stu-id="c31da-129">The affected devices will have the "Device state" with value of "Unknown".</span></span> <span data-ttu-id="c31da-130">Für Geräte mit Ausgabewert „Gerät nicht verbunden“ oder für Geräte mit „Gerätestatus“-Wert „Okay“ können Sie die folgende Anleitung ignorieren.</span><span class="sxs-lookup"><span data-stu-id="c31da-130">If the output is "Device not joined" or whose "Device state" value is "Okay", ignore the following guidance.</span></span>

<span data-ttu-id="c31da-131">Nur für Geräte, die anzeigen, dass das Gerät verbunden ist (aufgrund von Geräte-ID, Fingerabdruck usw.) und deren „Gerätestatus“-Wert „Unbekannt“ ist, sollten Administratoren den folgenden Befehl im Kontext eines Domänenbenutzers ausführen, der sich bei einem solchen kompatiblen Gerät anmeldet:</span><span class="sxs-lookup"><span data-stu-id="c31da-131">Only for devices that show that the device is joined (by virtue of deviceId, thumbprint, and so on) and whose "Device state" value is "Unknown", admins should run the following command in the context of a domain user signing in on such a down-level device:</span></span>

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

<span data-ttu-id="c31da-132">Der vorstehende Befehl muss nur einmal pro Domänenbenutzer ausgeführt werden, der sich auf dem kompatiblen Windows-Gerät anmeldet.</span><span class="sxs-lookup"><span data-stu-id="c31da-132">The preceding command only needs to be run once per domain user signing in on the Windows down-level device.</span></span> <span data-ttu-id="c31da-133">Dieser Befehl sollte im Kontext eines sich anmeldenden Domänenbenutzers ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c31da-133">This command should be run in the context of the domain user signing in.</span></span> 

<span data-ttu-id="c31da-134">Es muss sichergestellt werden, dass dieser Befehl nicht ausgeführt wird, wenn sich der Benutzer anschließend anmeldet.</span><span class="sxs-lookup"><span data-stu-id="c31da-134">Sufficient care must be taken to not run this command when the user subsequently signs in.</span></span> <span data-ttu-id="c31da-135">Wenn der vorhergehende Befehl ausgeführt wird, wird der verbundene Status des lokalen Azure AD Hybrid-verbundenen Computers für den Benutzer gelöscht, der sich angemeldet hat.</span><span class="sxs-lookup"><span data-stu-id="c31da-135">When the preceding command runs, it will clear the joined state of the local hybrid Azure AD–joined computer for the user who signed in.</span></span> <span data-ttu-id="c31da-136">Und wenn der Computer im Mandanten immer noch als Azure AD Hybrid-verbunden konfiguriert ist, wird er versuchen, sich wieder zu verknüpfen, wenn der Benutzer sich anmeldet.</span><span class="sxs-lookup"><span data-stu-id="c31da-136">And, if the computer is still configured to be hybrid Azure AD–joined in the tenant, it will attempt to join when the user signs in again.</span></span>

### <a name="windows-current"></a><span data-ttu-id="c31da-137">Aktuelles Windows</span><span class="sxs-lookup"><span data-stu-id="c31da-137">Windows Current</span></span>

#### <a name="unjoin"></a><span data-ttu-id="c31da-138">Verknüpfung auflösen</span><span class="sxs-lookup"><span data-stu-id="c31da-138">Unjoin</span></span>

<span data-ttu-id="c31da-139">Um herauszufinden, ob ein Windows 10-Gerät früher mit Azure AD verbunden wurde, führen Sie auf dem Gerät folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c31da-139">To determine whether the Windows 10 device was previously joined to Azure AD, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="c31da-140">Wenn das Gerät Azure AD Hybrid-verbunden ist, würde der Administrator die folgende Ausgabe sehen:</span><span class="sxs-lookup"><span data-stu-id="c31da-140">If the device is hybrid Azure AD–joined, the admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

<span data-ttu-id="c31da-141">Wenn die Ausgabe „AzureAdJoined: Nein“ ist, können Sie die folgende Anleitung ignorieren.</span><span class="sxs-lookup"><span data-stu-id="c31da-141">If the output is "AzureAdJoined : No", ignore the following guidance.</span></span>

<span data-ttu-id="c31da-142">Führen Sie nur für Geräte, die anzeigen, dass das Gerät mit Azure AD verbunden ist, den folgenden Befehl als Administrator aus, um den verbundenen Status des Geräts zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="c31da-142">Only for devices that show that the device is joined to Azure AD, run the following command as an admin to remove the joined state of the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="c31da-143">Der vorstehende Befehl muss nur einmal in einem administrativen Kontext auf dem Windows-Gerät ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c31da-143">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span>

#### <a name="hybrid-ad-joinre-registration"></a><span data-ttu-id="c31da-144">AD Hybrid Beitritt/Wieder-Registrierung</span><span class="sxs-lookup"><span data-stu-id="c31da-144">Hybrid AD Join\Re-Registration</span></span>

<span data-ttu-id="c31da-145">Das Gerät wird automatisch ohne Benutzer- oder Administratoreingriff mit Azure AD verbunden, solange das Gerät über eine Netzwerkverbindung zu globalen Azure AD-Endpunkten verfügt.</span><span class="sxs-lookup"><span data-stu-id="c31da-145">The device is automatically joined to Azure AD without user or admin intervention as long as the device has network connectivity to global Azure AD endpoints.</span></span> 


## <a name="azure-ad-join"></a><span data-ttu-id="c31da-146">Azure AD Join</span><span class="sxs-lookup"><span data-stu-id="c31da-146">Azure AD Join</span></span>

<span data-ttu-id="c31da-147">**WICHTIG:** Der Intune-Dienstprinzipal wird nach der Commerce-Migration aktiviert, was die Aktivierung von Azure AD Device Registration impliziert.</span><span class="sxs-lookup"><span data-stu-id="c31da-147">**IMPORTANT:** The Intune service principal will be enabled after commerce migration, which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="c31da-148">Wenn Sie Azure AD Device Registration vor der Migration blockiert haben, müssen Sie den Intune-Dienstprinzipal mit PowerShell deaktivieren, um die Azure AD-Geräteregistrierung mit dem Azure AD-Portal erneut zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c31da-148">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="c31da-149">Sie können den Intune-Dienstprinzipal mit diesem Befehl im Azure Active Directory PowerShell für Graph-Modul deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c31da-149">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a><span data-ttu-id="c31da-150">Verknüpfung auflösen</span><span class="sxs-lookup"><span data-stu-id="c31da-150">Unjoin</span></span>

<span data-ttu-id="c31da-151">Um herauszufinden, ob ein Windows 10-Gerät früher mit Azure AD verbunden wurde, kann der Benutzer oder Administrator auf dem Gerät folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="c31da-151">To determine whether the Windows 10 device was previously joined to Azure AD, the user or admin can run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="c31da-152">Wenn das Gerät mit Azure AD verbunden ist, würden der Benutzer oder der Administrator die folgende Ausgabe sehen:</span><span class="sxs-lookup"><span data-stu-id="c31da-152">If the device is joined to Azure AD, the user or admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

<span data-ttu-id="c31da-153">Wenn die Ausgabe „AzureAdJoined: NEIN“ ist, können Sie die folgende Anleitung ignorieren.</span><span class="sxs-lookup"><span data-stu-id="c31da-153">If the output is "AzureAdJoined : NO", ignore the following guidance.</span></span>

<span data-ttu-id="c31da-154">Benutzer: Wenn das Gerät mit Azure AD verbunden ist, kann ein Benutzer die Verknüpfung des Geräts in den Einstellungen auflösen.</span><span class="sxs-lookup"><span data-stu-id="c31da-154">User: If the device is Azure AD joined, a user can unjoin the device from the settings.</span></span> <span data-ttu-id="c31da-155">Stellen Sie sicher, dass ein lokales Administratorkonto auf dem Gerät vorhanden ist, bevor Sie die Verknüpfung des Geräts mit Azure AD aufheben.</span><span class="sxs-lookup"><span data-stu-id="c31da-155">Verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="c31da-156">Das lokale Administratorkonto wird benötigt, um sich wieder am Gerät anzumelden.</span><span class="sxs-lookup"><span data-stu-id="c31da-156">The local administrator account is required to sign back into the device.</span></span>

<span data-ttu-id="c31da-157">Administrator: Wenn der Administrator einer Organisation die Verknüpfung der Azure AD-verbundenen Geräte eines Benutzers aufheben will, kann er dies durch das Ausführen des folgenden Befehls auf jedem der Geräte machen, indem er einen Mechanismus wie z. B. die Gruppenrichtlinie verwendet.</span><span class="sxs-lookup"><span data-stu-id="c31da-157">Admin: If the organization's admin wants to unjoin the users' devices that are Azure AD–joined, they can do so by running the following command on each of the devices by using a mechanism such as Group Policy.</span></span> <span data-ttu-id="c31da-158">Der Administrator muss sicherstellen, dass ein lokales Administratorkonto auf dem Gerät vorhanden ist, bevor er die Verknüpfung des Geräts mit Azure AD aufhebt.</span><span class="sxs-lookup"><span data-stu-id="c31da-158">The admin must verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="c31da-159">Das lokale Administratorkonto ist notwendig, um sich wieder am Gerät anzumelden.</span><span class="sxs-lookup"><span data-stu-id="c31da-159">The local administrator account is needed to sign back into the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="c31da-160">Der vorstehende Befehl muss nur einmal in einem administrativen Kontext auf dem Windows-Gerät ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c31da-160">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span> 

### <a name="azure-ad-joinre-registration"></a><span data-ttu-id="c31da-161">Azure AD Beitritt/Wieder-Registrierung</span><span class="sxs-lookup"><span data-stu-id="c31da-161">Azure AD Join/Re-Registration</span></span>

<span data-ttu-id="c31da-162">Der Benutzer kann das Gerät über die Windows-Einstellungen zu Azure AD verknüpfen: **Einstellungen > Konten > Zugriff auf Arbeit oder Schule > Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="c31da-162">The user can join the device to Azure AD from Windows settings: **Settings > Accounts > Access Work Or School > Connect**.</span></span>
 

## <a name="azure-ad-registered-company-owned"></a><span data-ttu-id="c31da-163">Azure AD Registered (Im Besitz des Unternehmens)</span><span class="sxs-lookup"><span data-stu-id="c31da-163">Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="c31da-164">Um herauszufinden, ob ein Windows 10-Gerät Azure AD-registriert ist, führen Sie auf dem Gerät folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c31da-164">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="c31da-165">Wenn das Gerät Azure AD-registriert ist, würden Sie folgende Ausgabe sehen:</span><span class="sxs-lookup"><span data-stu-id="c31da-165">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="c31da-166">Um das bestehende Azure AD-registrierte Konto auf dem Gerät zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="c31da-166">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="c31da-167">Um das bestehende Azure AD-registrierte Konto auf dem Gerät zu entfernen verwenden Sie CleanupWPJ, ein Tool, das Sie hier herunterladen können: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span><span class="sxs-lookup"><span data-stu-id="c31da-167">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="c31da-168">Extrahieren Sie die ZIP-Datei und führen Sie **WPJCleanup.cmd** aus.</span><span class="sxs-lookup"><span data-stu-id="c31da-168">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="c31da-169">Dieses Tool wird basierend auf der Windows-Version auf dem Gerät die richtige ausführbare Datei starten.</span><span class="sxs-lookup"><span data-stu-id="c31da-169">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="c31da-170">Wenn Sie einen Mechanismus wie die Gruppenrichtlinie verwenden, kann der Administrator den Befehl im Kontext jedes auf dem Gerät angemeldeten Benutzers ausführen.</span><span class="sxs-lookup"><span data-stu-id="c31da-170">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="c31da-171">Um die Web Account Manager-Eingabeaufforderungen zur Registrierung des Geräts in Azure AD zu deaktivieren, fügen Sie folgenden Registry-Wert hinzu:</span><span class="sxs-lookup"><span data-stu-id="c31da-171">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="c31da-172">Ort: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="c31da-172">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="c31da-173">Typ: DWORD (32 bit)</span><span class="sxs-lookup"><span data-stu-id="c31da-173">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="c31da-174">Name: BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="c31da-174">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="c31da-175">Wertdaten: 1</span><span class="sxs-lookup"><span data-stu-id="c31da-175">Value data: 1</span></span>

<span data-ttu-id="c31da-176">Das Vorhandensein dieses Registry-Werts sollte die Arbeitsplatz-Verknüpfung blockieren und verhindern, dass Benutzer Eingabeaufforderungen zum Verknüpfen des Geräts sehen.</span><span class="sxs-lookup"><span data-stu-id="c31da-176">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="c31da-177">Android</span><span class="sxs-lookup"><span data-stu-id="c31da-177">Android</span></span>

<span data-ttu-id="c31da-178">Für Android müssen Benutzer ihre Geräte abmelden und wieder registrieren.</span><span class="sxs-lookup"><span data-stu-id="c31da-178">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="c31da-179">Dies kann mit der Microsoft Authenticator-App oder der Unternehmensportal-App geschehen.</span><span class="sxs-lookup"><span data-stu-id="c31da-179">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="c31da-180">Aus der Microsoft Authenticator-App können die Benutzer zu **Einstellungen > Geräteregistrierung** gehen.</span><span class="sxs-lookup"><span data-stu-id="c31da-180">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="c31da-181">Von dort aus können die Benutzer ihre Geräte abmelden und wieder registrieren.</span><span class="sxs-lookup"><span data-stu-id="c31da-181">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="c31da-182">Aus dem Unternehmensportal können die Benutzer zu Registerkarte **Geräte** gehen und das Gerät entfernen.</span><span class="sxs-lookup"><span data-stu-id="c31da-182">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="c31da-183">Danach registrieren Sie das Gerät erneut über das Unternehmensportal.</span><span class="sxs-lookup"><span data-stu-id="c31da-183">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="c31da-184">Benutzer können das Gerät auch abmelden und wieder registrieren, indem Sie das Konto von der Seite „Kontoeinstellungen“ entfernen und dann das Geschäftskonto wieder hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c31da-184">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="c31da-185">Um das Gerät mit der Microsoft Authenticator-App auf Android abzumelden und wieder zu registrieren:</span><span class="sxs-lookup"><span data-stu-id="c31da-185">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="c31da-186">Öffnen Sie die Microsoft Authenticator-App und gehen Sie zu **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="c31da-186">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="c31da-187">Wählen Sie **Geräteregistrierung**.</span><span class="sxs-lookup"><span data-stu-id="c31da-187">Select **Device registration**.</span></span>
3.  <span data-ttu-id="c31da-188">Melden Sie das Gerät ab, indem Sie **Registrierung aufheben** auswählen.</span><span class="sxs-lookup"><span data-stu-id="c31da-188">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="c31da-189">Für die **Geräteregistrierung** registrieren Sie das Gerät erneut, indem Sie Ihre E-Mail-Adresse eingeben und **Registrieren** auswählen.</span><span class="sxs-lookup"><span data-stu-id="c31da-189">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="c31da-190">Um ein Android-Gerät mit der Seite für Android-Einstellungen abzumelden und wieder zu registrieren:</span><span class="sxs-lookup"><span data-stu-id="c31da-190">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="c31da-191">Öffnen Sie **Geräteeinstellungen** und gehen sie zu **Konten**.</span><span class="sxs-lookup"><span data-stu-id="c31da-191">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="c31da-192">Wählen das Geschäftskonto aus, das Sie wieder registrieren wollen und wählen Sie **Konto entfernen**.</span><span class="sxs-lookup"><span data-stu-id="c31da-192">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="c31da-193">Nachdem das Konto entfernt wurde, wählen Sie von der **Konto**-Seite aus **Konto hinzufügen > Geschäftskonto**.</span><span class="sxs-lookup"><span data-stu-id="c31da-193">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="c31da-194">Für die **Arbeitsplatz-Verknüpfung** geben Sie Ihre E-Mail-Adresse ein und wählen Sie **Verknüpfung**, um die Registrierung des Geräts abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="c31da-194">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="c31da-195">Um das Gerät auf Android über das Unternehmensportal abzumelden und neu zu registrieren:</span><span class="sxs-lookup"><span data-stu-id="c31da-195">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="c31da-196">Starten Sie das Unternehmensportal und gehen Sie zur Registerkarte **Geräte**.</span><span class="sxs-lookup"><span data-stu-id="c31da-196">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="c31da-197">Wählen Sie das Gerät aus, um die Gerätedetails zu sehen.</span><span class="sxs-lookup"><span data-stu-id="c31da-197">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="c31da-198">Aus dem Ellipsen-Menü (drei Punkte) wählen Sie **Gerät entfernen** und schließen das Entfernen ab, indem Sie dies im Dialogfeld bestätigen.</span><span class="sxs-lookup"><span data-stu-id="c31da-198">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="c31da-199">Sie sollten jetzt von der Unternehmensportal-App abgemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="c31da-199">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="c31da-200">Wählen Sie **Anmelden**, um das Gerät wieder zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="c31da-200">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="c31da-201">Weitere Informationen zu Aktionen, die während der Migrationsphase dieses Workloads erforderlich sind, oder zu Auswirkungen auf die Verwaltung oder Verwendung finden Sie in den Informationen zu Azure Active Directory (Azure AD) unter [Zusätzliche Azure AD-Informationen für die Migration von Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span><span class="sxs-lookup"><span data-stu-id="c31da-201">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="c31da-202">iOS</span><span class="sxs-lookup"><span data-stu-id="c31da-202">iOS</span></span>

<span data-ttu-id="c31da-203">Auf iOS-Geräten muss ein Benutzer alle zwischengespeicherten Konten manuell aus dem Microsoft Authenticator entfernen, die Registrierung des Geräts aufheben und sich von allen nativen Apps auf dem Gerät abmelden.</span><span class="sxs-lookup"><span data-stu-id="c31da-203">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="c31da-204">Schritt 1: Wenn vorhanden, entfernen Sie das Konto aus der Microsoft Authenticator-App</span><span class="sxs-lookup"><span data-stu-id="c31da-204">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="c31da-205">Tippen Sie auf des Konto in der Microsoft Authenticator-App.</span><span class="sxs-lookup"><span data-stu-id="c31da-205">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="c31da-206">Tippen Sie auf das Symbol **Einstellungen** in der oberen rechten Ecke. </span><span class="sxs-lookup"><span data-stu-id="c31da-206">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="c31da-207">Wenn Sie das Symbol **Einstellungen** nicht sehen, verwenden Sie möglicherweise nicht die aktuelle Version des Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="c31da-207">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="c31da-208">Tippen Sie die Schaltfläche **Konto entfernen**.</span><span class="sxs-lookup"><span data-stu-id="c31da-208">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="c31da-209">Tippen Sie auf **Alle Apps auf diesem Gerät**.</span><span class="sxs-lookup"><span data-stu-id="c31da-209">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="c31da-210">Schritt 2: Registrierung des Geräts in der Microsoft Authenticator-App aufheben</span><span class="sxs-lookup"><span data-stu-id="c31da-210">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="c31da-211">Tippen Sie auf das Menu-Symbol in der oberen rechten Ecke. </span><span class="sxs-lookup"><span data-stu-id="c31da-211">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="c31da-212">Tippen Sie **Einstellungen** und dann **Geräteregistrierung**.</span><span class="sxs-lookup"><span data-stu-id="c31da-212">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="c31da-213">Wenn Ihr Konto angezeigt wird, tippen Sie im Dialog auf **Registrierung des Geräts aufheben** und **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c31da-213">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="c31da-214">Sie sollten danach kein Konto mehr sehen.</span><span class="sxs-lookup"><span data-stu-id="c31da-214">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="c31da-215">Schritt 3: Abmelden aus individuellen Apps wenn notwendig.</span><span class="sxs-lookup"><span data-stu-id="c31da-215">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="c31da-216">Benutzer können zu individuellen Apps wie Outlook, Teams oder OneDrive wechseln und Konten aus diese Apps entfernen.</span><span class="sxs-lookup"><span data-stu-id="c31da-216">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="c31da-217">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c31da-217">More information</span></span>

<span data-ttu-id="c31da-218">Erste Schritte:</span><span class="sxs-lookup"><span data-stu-id="c31da-218">Getting started:</span></span>

- [<span data-ttu-id="c31da-219">Migration von Microsoft Cloud Deutschland zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen</span><span class="sxs-lookup"><span data-stu-id="c31da-219">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="c31da-220">Hilfe zur Microsoft Cloud Deutschland-Migration Assistance</span><span class="sxs-lookup"><span data-stu-id="c31da-220">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="c31da-221">So können Sie sich für die Migration anmelden</span><span class="sxs-lookup"><span data-stu-id="c31da-221">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="c31da-222">Kundenerfahrung während der Migration</span><span class="sxs-lookup"><span data-stu-id="c31da-222">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="c31da-223">Der Weg durch die Umstellung:</span><span class="sxs-lookup"><span data-stu-id="c31da-223">Moving through the transition:</span></span>

- [<span data-ttu-id="c31da-224">Aktionen und Auswirkungen der Migrationsphasen</span><span class="sxs-lookup"><span data-stu-id="c31da-224">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="c31da-225">Zusätzliche Vorarbeit</span><span class="sxs-lookup"><span data-stu-id="c31da-225">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="c31da-226">Zusätzliche Informationen für [Azure AD](ms-cloud-germany-transition-azure-ad.md), [Geräte](ms-cloud-germany-transition-add-devices.md), [Erfahrungen](ms-cloud-germany-transition-add-experience.md) und [AD FS](ms-cloud-germany-transition-add-adfs.md).</span><span class="sxs-lookup"><span data-stu-id="c31da-226">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="c31da-227">Cloud-Apps:</span><span class="sxs-lookup"><span data-stu-id="c31da-227">Cloud apps:</span></span>

- [<span data-ttu-id="c31da-228">Informationen zum Dynamics 365-Migrationsprogramm</span><span class="sxs-lookup"><span data-stu-id="c31da-228">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="c31da-229">Informationen zum Power BI-Migrationsprogramm</span><span class="sxs-lookup"><span data-stu-id="c31da-229">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="c31da-230">Erste Schritte mit dem Upgrade von Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c31da-230">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
