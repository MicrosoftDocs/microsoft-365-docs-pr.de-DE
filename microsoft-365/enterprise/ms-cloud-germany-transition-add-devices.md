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
description: 'Zusammenfassung: weitere Geräteinformationen zu Diensten beim Wechsel von Microsoft Cloud Deutschland (Microsoft Cloud Deutschland) zu Office 365 Diensten im neuen rechenzentrumsbereich.'
ms.openlocfilehash: 1bbb4bf39db61a93844c21cd6062a70699b5d6d7
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688654"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="01c23-103">Zusätzliche Geräteinformationen für die Migration von Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="01c23-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="01c23-104">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="01c23-104">Frequently asked questions</span></span>

<span data-ttu-id="01c23-105">**Woran kann ich erkennen, ob meine Organisation betroffen ist?**</span><span class="sxs-lookup"><span data-stu-id="01c23-105">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="01c23-106">Administratoren sollten überprüfen `https://portal.microsoftazure.de` , ob Sie über registrierte Geräte verfügen.</span><span class="sxs-lookup"><span data-stu-id="01c23-106">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered devices.</span></span> <span data-ttu-id="01c23-107">Wenn Ihre Organisation über registrierte Geräte verfügt, sind Sie davon betroffen.</span><span class="sxs-lookup"><span data-stu-id="01c23-107">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="01c23-108">**Was sind die Auswirkungen auf meine Benutzer?**</span><span class="sxs-lookup"><span data-stu-id="01c23-108">**What is the impact on my users?**</span></span>

<span data-ttu-id="01c23-109">Benutzer von einem registrierten Gerät können sich nicht mehr anmelden, nachdem die Migration in die Azure AD Migrationsphase [abgeschlossen](ms-cloud-germany-transition.md#how-is-the-migration-organized) wurde.</span><span class="sxs-lookup"><span data-stu-id="01c23-109">Users from a registered device will no longer be able to sign in after your migration enters the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>  

<span data-ttu-id="01c23-110">Stellen Sie sicher, dass alle Ihre Geräte beim weltweiten Endpunkt registriert sind, bevor Ihre Organisation von Microsoft Cloud Deutschland getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="01c23-110">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="01c23-111">**Wann werden meine Benutzer ihre Geräte erneut registrieren?**</span><span class="sxs-lookup"><span data-stu-id="01c23-111">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="01c23-112">Entscheidend für Ihren Erfolg ist, dass Sie Ihre Geräte nur in der [separaten Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) -Migrationsphase aufheben und neu registrieren.</span><span class="sxs-lookup"><span data-stu-id="01c23-112">It's critical to your success that you only unregister and re-register your devices during the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="01c23-113">**Wie stelle ich den Gerätestatus nach der Migration wieder her?**</span><span class="sxs-lookup"><span data-stu-id="01c23-113">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="01c23-114">Für Hybrid Azure AD-geteilte und unternehmenseigene Windows-Geräte, die bei Azure AD registriert sind, können Administratoren die Migration dieser Geräte über Remote ausgelöste Workflows verwalten, mit denen die Registrierung der alten Gerätezustände aufgehoben wird.</span><span class="sxs-lookup"><span data-stu-id="01c23-114">For hybrid Azure AD–joined and company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="01c23-115">Für alle anderen Geräte, einschließlich persönlicher Windows-Geräte, die in Azure AD registriert sind, muss der Endbenutzer diese Schritte manuell ausführen.</span><span class="sxs-lookup"><span data-stu-id="01c23-115">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="01c23-116">Für Azure AD-verbundene Geräte müssen Benutzer über ein lokales Administratorkonto verfügen, um die Registrierung aufzuheben und die Geräte dann erneut zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="01c23-116">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="01c23-117">Microsoft veröffentlicht Anweisungen zur erfolgreichen Wiederherstellung des Gerätestatus.</span><span class="sxs-lookup"><span data-stu-id="01c23-117">Microsoft will publish instructions for how to successfully restore device state.</span></span> 
 
<span data-ttu-id="01c23-118">**Woher weiß ich, dass alle meine Geräte in der öffentlichen Cloud registriert sind?**</span><span class="sxs-lookup"><span data-stu-id="01c23-118">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="01c23-119">Um zu überprüfen, ob Ihre Geräte in der öffentlichen Cloud registriert sind, sollten Sie die Liste der Geräte aus dem Azure AD Portal in ein Excel-Arbeitsblatt exportieren und herunterladen.</span><span class="sxs-lookup"><span data-stu-id="01c23-119">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="01c23-120">Filtern Sie dann die Geräte, die registriert sind (mithilfe der Spalte " _registered_ Zeit") nach der [separaten Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) -Migrationsphase.</span><span class="sxs-lookup"><span data-stu-id="01c23-120">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="01c23-121">Die Geräteregistrierung wird nach der Migration des Mandanten deaktiviert und kann nicht aktiviert oder deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="01c23-121">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> <span data-ttu-id="01c23-122">Wenn InTune nicht verwendet wird, melden Sie sich bei Ihrem Abonnement an, und führen Sie diesen Befehl aus, um die Option erneut zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="01c23-122">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="windows-hybrid-azure-ad-join"></a><span data-ttu-id="01c23-123">Windows-Hybrid Azure AD beitreten</span><span class="sxs-lookup"><span data-stu-id="01c23-123">Windows Hybrid Azure AD join</span></span>

### <a name="windows-down-level"></a><span data-ttu-id="01c23-124">Windows-Down-Level</span><span class="sxs-lookup"><span data-stu-id="01c23-124">Windows down-level</span></span>

<span data-ttu-id="01c23-125">_Windows-untergeordnete Geräte_ sind Windows-Geräte, die derzeit frühere Versionen von Windows (beispielsweise Windows 8.1 oder Windows 7) ausführen oder die Windows Server-Versionen vor 2019 und 2016 ausführen.</span><span class="sxs-lookup"><span data-stu-id="01c23-125">_Windows down-level devices_ are Windows devices that currently run earlier versions of Windows (such as Windows 8.1 or Windows 7), or that run Windows Server versions earlier than 2019 and 2016.</span></span> <span data-ttu-id="01c23-126">Wenn diese Geräte zuvor registriert wurden, müssen Sie diese Geräte aufheben und erneut registrieren.</span><span class="sxs-lookup"><span data-stu-id="01c23-126">If such devices were registered before, you'll need to unregister and re-register those devices.</span></span> 

<span data-ttu-id="01c23-127">Verwenden Sie den folgenden Befehl auf dem Gerät, um festzustellen, ob ein Windows-Gerät auf der untersten Ebene zuvor zu Azure AD hinzugefügt wurde:</span><span class="sxs-lookup"><span data-stu-id="01c23-127">To determine whether a Windows down-level device was previously joined to Azure AD, use following command on the device:</span></span>

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

<span data-ttu-id="01c23-128">Wenn das Gerät zuvor mit Azure AD verbunden wurde und das Gerät über eine Netzwerkverbindung mit globalen Azure AD Endpunkten verfügt, wird die folgende Ausgabe angezeigt:</span><span class="sxs-lookup"><span data-stu-id="01c23-128">If the device was previously joined to Azure AD, and if the device has network connectivity to global Azure AD endpoints, you would see the following output:</span></span>

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

<span data-ttu-id="01c23-129">Die betroffenen Geräte haben den "Gerätestatus" mit dem Wert "unbekannt".</span><span class="sxs-lookup"><span data-stu-id="01c23-129">The affected devices will have the "Device state" with value of "Unknown".</span></span> <span data-ttu-id="01c23-130">Wenn die Ausgabe "Device not Joined" ist oder deren Wert "Gerätestatus" "OK" lautet, ignorieren Sie die folgende Anleitung.</span><span class="sxs-lookup"><span data-stu-id="01c23-130">If the output is "Device not joined" or whose "Device state" value is "Okay", ignore the following guidance.</span></span>

<span data-ttu-id="01c23-131">Nur für Geräte, die anzeigen, dass das Gerät verbunden ist (aufgrund von Geräte-und Fingerabdruck usw.) und dessen Wert "Gerätestatus" "unbekannt" ist, sollten Administratoren den folgenden Befehl im Kontext eines Domänenbenutzers ausführen, der sich auf einem solchen untergeordneten Gerät anmeldet:</span><span class="sxs-lookup"><span data-stu-id="01c23-131">Only for devices that show that the device is joined (by virtue of deviceId, thumbprint, and so on) and whose "Device state" value is "Unknown", admins should run the following command in the context of a domain user signing in on such a down-level device:</span></span>

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

<span data-ttu-id="01c23-132">Der obige Befehl muss nur einmal pro Domänenbenutzer ausgeführt werden, der sich auf dem Windows-Down-Level-Gerät anmeldet.</span><span class="sxs-lookup"><span data-stu-id="01c23-132">The preceding command only needs to be run once per domain user signing in on the Windows down-level device.</span></span> <span data-ttu-id="01c23-133">Dieser Befehl sollte im Kontext des Domänenbenutzers ausgeführt werden, der sich anmeldet.</span><span class="sxs-lookup"><span data-stu-id="01c23-133">This command should be run in the context of the domain user signing in.</span></span> 

<span data-ttu-id="01c23-134">Es muss ausreichend darauf geachtet werden, diesen Befehl nicht auszuführen, wenn der Benutzer sich anschließend anmeldet.</span><span class="sxs-lookup"><span data-stu-id="01c23-134">Sufficient care must be taken to not run this command when the user subsequently signs in.</span></span> <span data-ttu-id="01c23-135">Wenn der obige Befehl ausgeführt wird, wird der verbundene Status des lokalen Hybriden Azure AD-verbundenen Computers für den Benutzer, der sich angemeldet hat, gelöscht.</span><span class="sxs-lookup"><span data-stu-id="01c23-135">When the preceding command runs, it will clear the joined state of the local hybrid Azure AD–joined computer for the user who signed in.</span></span> <span data-ttu-id="01c23-136">Wenn der Computer noch als Hybrid Azure AD konfiguriert ist – im Mandanten verbunden, versucht er, sich anzumelden, wenn sich der Benutzer erneut anmeldet.</span><span class="sxs-lookup"><span data-stu-id="01c23-136">And, if the computer is still configured to be hybrid Azure AD–joined in the tenant, it will attempt to join when the user signs in again.</span></span>

### <a name="windows-current"></a><span data-ttu-id="01c23-137">Windows Current</span><span class="sxs-lookup"><span data-stu-id="01c23-137">Windows Current</span></span>

#### <a name="unjoin"></a><span data-ttu-id="01c23-138">Trennungs</span><span class="sxs-lookup"><span data-stu-id="01c23-138">Unjoin</span></span>

<span data-ttu-id="01c23-139">Führen Sie den folgenden Befehl auf dem Gerät aus, um festzustellen, ob das Windows 10-Gerät zuvor zu Azure AD hinzugefügt wurde:</span><span class="sxs-lookup"><span data-stu-id="01c23-139">To determine whether the Windows 10 device was previously joined to Azure AD, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="01c23-140">Wenn das Gerät Hybrid Azure AD – Joined ist, würde der Administrator die folgende Ausgabe sehen:</span><span class="sxs-lookup"><span data-stu-id="01c23-140">If the device is hybrid Azure AD–joined, the admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

<span data-ttu-id="01c23-141">Wenn die Ausgabe "AzureAdJoined: No" lautet, ignorieren Sie die folgende Anleitung.</span><span class="sxs-lookup"><span data-stu-id="01c23-141">If the output is "AzureAdJoined : No", ignore the following guidance.</span></span>

<span data-ttu-id="01c23-142">Führen Sie den folgenden Befehl als Administrator aus, um den verbundenen Status des Geräts zu entfernen, nur für Geräte, die anzeigen, dass das Gerät mit Azure AD verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="01c23-142">Only for devices that show that the device is joined to Azure AD, run the following command as an admin to remove the joined state of the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="01c23-143">Der obige Befehl muss nur einmal in einem administrativen Kontext auf dem Windows-Gerät ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="01c23-143">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span>

#### <a name="hybrid-ad-joinre-registration"></a><span data-ttu-id="01c23-144">Hybrid-AD-Join\Re-Registration</span><span class="sxs-lookup"><span data-stu-id="01c23-144">Hybrid AD Join\Re-Registration</span></span>

<span data-ttu-id="01c23-145">Das Gerät wird automatisch mit Azure AD ohne Benutzer-oder Administratoreingriff verbunden, solange das Gerät über eine Netzwerkverbindung mit globalen Azure AD Endpunkten verfügt.</span><span class="sxs-lookup"><span data-stu-id="01c23-145">The device is automatically joined to Azure AD without user or admin intervention as long as the device has network connectivity to global Azure AD endpoints.</span></span> 


## <a name="windows-azure-ad-join"></a><span data-ttu-id="01c23-146">Windows Azure AD beitreten</span><span class="sxs-lookup"><span data-stu-id="01c23-146">Windows Azure AD Join</span></span>

<span data-ttu-id="01c23-147">**Wichtig:** Der InTune-Dienstprinzipal wird nach der Commerce-Migration aktiviert, was die Aktivierung Azure AD Geräteregistrierung impliziert.</span><span class="sxs-lookup"><span data-stu-id="01c23-147">**IMPORTANT:** The Intune service principal will be enabled after commerce migration, which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="01c23-148">Wenn Sie Azure AD Geräteregistrierung vor der Migration blockiert haben, müssen Sie den InTune-Dienstprinzipal mit PowerShell deaktivieren, um Azure AD Geräteregistrierung erneut mit dem Azure AD Portal zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="01c23-148">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="01c23-149">Sie können den InTune-Dienstprinzipal mit diesem Befehl im Azure Active Directory PowerShell for Graph-Modul deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="01c23-149">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a><span data-ttu-id="01c23-150">Trennungs</span><span class="sxs-lookup"><span data-stu-id="01c23-150">Unjoin</span></span>

<span data-ttu-id="01c23-151">Um zu ermitteln, ob das Windows 10-Gerät zuvor mit Azure AD verbunden wurde, kann der Benutzer oder Administrator den folgenden Befehl auf dem Gerät ausführen:</span><span class="sxs-lookup"><span data-stu-id="01c23-151">To determine whether the Windows 10 device was previously joined to Azure AD, the user or admin can run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="01c23-152">Wenn das Gerät mit Azure AD verbunden ist, wird dem Benutzer oder Administrator die folgende Ausgabe angezeigt:</span><span class="sxs-lookup"><span data-stu-id="01c23-152">If the device is joined to Azure AD, the user or admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

<span data-ttu-id="01c23-153">Wenn die Ausgabe "AzureAdJoined: No" lautet, ignorieren Sie die folgende Anleitung.</span><span class="sxs-lookup"><span data-stu-id="01c23-153">If the output is "AzureAdJoined : NO", ignore the following guidance.</span></span>

<span data-ttu-id="01c23-154">Benutzer: Wenn das Gerät Azure AD verbunden ist, kann ein Benutzer die Verknüpfung des Geräts von den Einstellungen trennen.</span><span class="sxs-lookup"><span data-stu-id="01c23-154">User: If the device is Azure AD joined, a user can unjoin the device from the settings.</span></span> <span data-ttu-id="01c23-155">Stellen Sie sicher, dass auf dem Gerät ein lokales Administratorkonto vorhanden ist, bevor Sie von Azure AD auf das Gerät aufschließen.</span><span class="sxs-lookup"><span data-stu-id="01c23-155">Verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="01c23-156">Das lokale Administratorkonto muss sich wieder am Gerät anmelden.</span><span class="sxs-lookup"><span data-stu-id="01c23-156">The local administrator account is required to sign back into the device.</span></span>

<span data-ttu-id="01c23-157">Admin: Wenn der Administrator der Organisation die Verknüpfung der Benutzer Geräte aufheben möchte, die Azure AD – beigetreten sind, können Sie den folgenden Befehl auf jedem der Geräte mithilfe eines Mechanismus wie der Gruppenrichtlinie ausführen.</span><span class="sxs-lookup"><span data-stu-id="01c23-157">Admin: If the organization's admin wants to unjoin the users' devices that are Azure AD–joined, they can do so by running the following command on each of the devices by using a mechanism such as Group Policy.</span></span> <span data-ttu-id="01c23-158">Der Administrator muss überprüfen, ob ein lokales Administratorkonto auf dem Gerät vorhanden ist, bevor die Verbindung mit dem Gerät von Azure AD entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="01c23-158">The admin must verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="01c23-159">Das lokale Administratorkonto wird benötigt, um sich wieder am Gerät anzumelden.</span><span class="sxs-lookup"><span data-stu-id="01c23-159">The local administrator account is needed to sign back into the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="01c23-160">Der obige Befehl muss nur einmal in einem administrativen Kontext auf dem Windows-Gerät ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="01c23-160">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span> 

### <a name="azure-ad-joinre-registration"></a><span data-ttu-id="01c23-161">Azure AD beitreten/erneute Registrierung</span><span class="sxs-lookup"><span data-stu-id="01c23-161">Azure AD Join/Re-Registration</span></span>

<span data-ttu-id="01c23-162">Der Benutzer kann dem Gerät Azure AD von Windows-Einstellungen hinzufügen: **Einstellungen > Konten > Access work oder School > Connect**.</span><span class="sxs-lookup"><span data-stu-id="01c23-162">The user can join the device to Azure AD from Windows settings: **Settings > Accounts > Access Work Or School > Connect**.</span></span>
 

## <a name="windows-azure-ad-registered-company-owned"></a><span data-ttu-id="01c23-163">Windows Azure AD registriert (im Unternehmen)</span><span class="sxs-lookup"><span data-stu-id="01c23-163">Windows Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="01c23-164">Führen Sie den folgenden Befehl auf dem Gerät aus, um festzustellen, ob das Gerät Windows 10 Azure AD – registriert ist:</span><span class="sxs-lookup"><span data-stu-id="01c23-164">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="01c23-165">Wenn das Gerät Azure AD registriert ist, wird die folgende Ausgabe angezeigt:</span><span class="sxs-lookup"><span data-stu-id="01c23-165">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="01c23-166">So entfernen Sie das vorhandene Azure AD registrierte Konto auf dem Gerät:</span><span class="sxs-lookup"><span data-stu-id="01c23-166">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="01c23-167">Verwenden Sie zum Entfernen des Azure AD-registrierten Kontos auf dem Gerät CleanupWPJ, ein Tool, das Sie hier herunterladen können: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span><span class="sxs-lookup"><span data-stu-id="01c23-167">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="01c23-168">Extrahieren Sie die ZIP-Datei, und führen Sie **WPJCleanup. cmd** aus.</span><span class="sxs-lookup"><span data-stu-id="01c23-168">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="01c23-169">Dieses Tool startet die richtige ausführbare Datei basierend auf der Windows-Version auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="01c23-169">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="01c23-170">Mithilfe eines Mechanismus wie Gruppenrichtlinie kann der Administrator den Befehl auf dem Gerät im Kontext eines beliebigen Benutzers ausführen, der auf dem Gerät angemeldet ist.</span><span class="sxs-lookup"><span data-stu-id="01c23-170">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="01c23-171">Um die Eingabeaufforderung des Webkonto-Managers zum Registrieren des Geräts in Azure AD zu deaktivieren, fügen Sie diesen Registrierungswert hinzu:</span><span class="sxs-lookup"><span data-stu-id="01c23-171">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="01c23-172">Speicherort: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="01c23-172">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="01c23-173">Typ: DWORD (32 Bit)</span><span class="sxs-lookup"><span data-stu-id="01c23-173">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="01c23-174">Name: BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="01c23-174">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="01c23-175">Wert Daten: 1</span><span class="sxs-lookup"><span data-stu-id="01c23-175">Value data: 1</span></span>

<span data-ttu-id="01c23-176">Das vorhanden sein dieses Registrierungswerts sollte einen Arbeitsplatz Beitritt blockieren und verhindern, dass Benutzer Ansagen zum Beitritt zum Gerät anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="01c23-176">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="01c23-177">Android</span><span class="sxs-lookup"><span data-stu-id="01c23-177">Android</span></span>

<span data-ttu-id="01c23-178">Für Android müssen Benutzer die Registrierung aufheben und Ihre Geräte erneut registrieren.</span><span class="sxs-lookup"><span data-stu-id="01c23-178">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="01c23-179">Dies kann über die Microsoft Authenticator-APP oder die Unternehmens Portal-App erfolgen.</span><span class="sxs-lookup"><span data-stu-id="01c23-179">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="01c23-180">Von der Microsoft Authenticator-App aus können Benutzer zu **Einstellungen > Geräteregistrierung** wechseln.</span><span class="sxs-lookup"><span data-stu-id="01c23-180">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="01c23-181">Von dort können Benutzer die Registrierung Ihres Geräts aufheben und erneut registrieren.</span><span class="sxs-lookup"><span data-stu-id="01c23-181">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="01c23-182">Über das Unternehmens Portal können Benutzer zur Registerkarte **Geräte** wechseln und das Gerät entfernen.</span><span class="sxs-lookup"><span data-stu-id="01c23-182">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="01c23-183">Registrieren Sie das Gerät anschließend mithilfe des Unternehmensportals neu.</span><span class="sxs-lookup"><span data-stu-id="01c23-183">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="01c23-184">Benutzer können die Registrierung und erneute Registrierung auch aufheben, indem Sie das Konto auf der Seite Kontoeinstellungen entfernen und dann das Arbeitskonto erneut hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="01c23-184">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="01c23-185">So heben Sie die Registrierung und das erneute Registrieren des Geräts unter Android mithilfe der Microsoft Authenticator-App auf:</span><span class="sxs-lookup"><span data-stu-id="01c23-185">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="01c23-186">Öffnen Sie die Microsoft Authenticator-APP, und wechseln Sie zu **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="01c23-186">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="01c23-187">Wählen Sie **Geräteregistrierung** aus.</span><span class="sxs-lookup"><span data-stu-id="01c23-187">Select **Device registration**.</span></span>
3.  <span data-ttu-id="01c23-188">Heben Sie die Registrierung des Geräts auf, indem Sie **Aufheben der Registrierung** auswählen.</span><span class="sxs-lookup"><span data-stu-id="01c23-188">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="01c23-189">Registrieren Sie das Gerät bei der **Geräteregistrierung** erneut, indem Sie Ihre e-Mail-Adresse eingeben, und wählen Sie dann **registrieren** aus.</span><span class="sxs-lookup"><span data-stu-id="01c23-189">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="01c23-190">So heben Sie die Registrierung und das erneute Registrieren eines Android-Geräts mit der Android-Einstellungsseite auf:</span><span class="sxs-lookup"><span data-stu-id="01c23-190">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="01c23-191">Öffnen Sie die **Geräteeinstellungen** , und wechseln Sie zu **Konten**.</span><span class="sxs-lookup"><span data-stu-id="01c23-191">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="01c23-192">Wählen Sie das Arbeitskonto aus, das Sie erneut registrieren möchten, und wählen Sie **Konto entfernen** aus.</span><span class="sxs-lookup"><span data-stu-id="01c23-192">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="01c23-193">Nachdem das Konto entfernt wurde, wählen Sie auf der Seite **Konten** die Option **Konto > Arbeitskonto hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="01c23-193">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="01c23-194">Geben Sie für **Workplace Join** Ihre e-Mail-Adresse ein, und wählen Sie **beitreten** aus, um die Registrierung des Geräts abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="01c23-194">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="01c23-195">So heben Sie die Registrierung und Erneutes Registrieren des Geräts unter Android im Unternehmens Portal auf:</span><span class="sxs-lookup"><span data-stu-id="01c23-195">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="01c23-196">Starten Sie das Unternehmens Portal, und wechseln Sie zur Registerkarte **Geräte** .</span><span class="sxs-lookup"><span data-stu-id="01c23-196">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="01c23-197">Wählen Sie das Gerät aus, um die Gerätedetails anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="01c23-197">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="01c23-198">Wählen Sie im Menü Ellipsen (drei Punkte) die Option **Gerät entfernen** aus, und schließen Sie das Entfernen ab, indem Sie im Dialogfeld bestätigen.</span><span class="sxs-lookup"><span data-stu-id="01c23-198">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="01c23-199">Sie sollten jetzt von der Unternehmens Portal-App abgemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="01c23-199">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="01c23-200">Wählen Sie **Anmelden** aus, um das Gerät erneut zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="01c23-200">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="01c23-201">Weitere Informationen zu den erforderlichen Aktionen während der Migrationsphase dieser Arbeitsauslastung oder zu den Auswirkungen auf die Verwaltung oder Verwendung finden Sie in den Informationen zu Azure Active Directory (Azure AD) in [zusätzlichen Azure AD Informationen für die Migration von Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span><span class="sxs-lookup"><span data-stu-id="01c23-201">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="01c23-202">iOS</span><span class="sxs-lookup"><span data-stu-id="01c23-202">iOS</span></span>

<span data-ttu-id="01c23-203">Auf IOS-Geräten muss ein Benutzer alle zwischengespeicherten Konten manuell aus dem Microsoft Authenticator entfernen, die Registrierung des Geräts aufheben und sich von allen systemeigenen apps auf dem Gerät abmelden.</span><span class="sxs-lookup"><span data-stu-id="01c23-203">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="01c23-204">Schritt 1: Entfernen Sie das Konto, falls vorhanden, aus der Microsoft Authenticator-app.</span><span class="sxs-lookup"><span data-stu-id="01c23-204">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="01c23-205">Tippen Sie auf das Konto in der Microsoft Authenticator-app.</span><span class="sxs-lookup"><span data-stu-id="01c23-205">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="01c23-206">Tippen Sie in der oberen rechten Ecke auf das Symbol " **Einstellungen** ".</span><span class="sxs-lookup"><span data-stu-id="01c23-206">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="01c23-207">Wenn das Symbol " **Einstellungen** " nicht angezeigt wird, verwenden Sie möglicherweise nicht die neueste Version von Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="01c23-207">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="01c23-208">Tippen Sie auf die Schaltfläche **Konto entfernen** .</span><span class="sxs-lookup"><span data-stu-id="01c23-208">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="01c23-209">Tippen Sie **auf alle apps auf diesem Gerät**.</span><span class="sxs-lookup"><span data-stu-id="01c23-209">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="01c23-210">Schritt 2: Aufheben der Registrierung des Geräts über die Microsoft Authenticator-App</span><span class="sxs-lookup"><span data-stu-id="01c23-210">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="01c23-211">Tippen Sie auf das Menüsymbol in der oberen rechten Ecke.</span><span class="sxs-lookup"><span data-stu-id="01c23-211">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="01c23-212">Tippen Sie auf **Einstellungen** und dann auf **Geräteregistrierung**.</span><span class="sxs-lookup"><span data-stu-id="01c23-212">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="01c23-213">Wenn Ihr Konto angezeigt wird, tippen Sie auf **Gerät aufheben** und im Dialogfeld auf **weiter** .</span><span class="sxs-lookup"><span data-stu-id="01c23-213">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="01c23-214">Danach sollte kein Konto angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="01c23-214">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="01c23-215">Schritt 3: Abmelden von einzelnen Apps bei Bedarf</span><span class="sxs-lookup"><span data-stu-id="01c23-215">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="01c23-216">Benutzer können zu einzelnen apps wie Outlook, Microsoft Teams und OneDrive wechseln und Konten aus diesen apps entfernen.</span><span class="sxs-lookup"><span data-stu-id="01c23-216">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="01c23-217">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="01c23-217">More information</span></span>

<span data-ttu-id="01c23-218">Erste Schritte:</span><span class="sxs-lookup"><span data-stu-id="01c23-218">Getting started:</span></span>

- [<span data-ttu-id="01c23-219">Migration von Microsoft Cloud Deutschland zu Office 365 Diensten in den neuen Regionen des deutschen Rechenzentrums</span><span class="sxs-lookup"><span data-stu-id="01c23-219">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="01c23-220">Hilfe zur Microsoft Cloud Deutschland-Migration Assistance</span><span class="sxs-lookup"><span data-stu-id="01c23-220">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="01c23-221">So können Sie sich für die Migration anmelden</span><span class="sxs-lookup"><span data-stu-id="01c23-221">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="01c23-222">Kundenerfahrung während der Migration</span><span class="sxs-lookup"><span data-stu-id="01c23-222">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="01c23-223">Navigieren durch den Übergang:</span><span class="sxs-lookup"><span data-stu-id="01c23-223">Moving through the transition:</span></span>

- [<span data-ttu-id="01c23-224">Phasen, Aktionen und Auswirkungen der Migration</span><span class="sxs-lookup"><span data-stu-id="01c23-224">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="01c23-225">Zusätzliche vorab Arbeit</span><span class="sxs-lookup"><span data-stu-id="01c23-225">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="01c23-226">Zusätzliche Informationen zu [Azure AD](ms-cloud-germany-transition-azure-ad.md), [Geräten](ms-cloud-germany-transition-add-devices.md), [Erfahrungen](ms-cloud-germany-transition-add-experience.md)und [AD FS](ms-cloud-germany-transition-add-adfs.md).</span><span class="sxs-lookup"><span data-stu-id="01c23-226">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="01c23-227">Cloud-apps:</span><span class="sxs-lookup"><span data-stu-id="01c23-227">Cloud apps:</span></span>

- [<span data-ttu-id="01c23-228">Informationen zum Dynamics 365-Migrationsprogramm</span><span class="sxs-lookup"><span data-stu-id="01c23-228">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="01c23-229">Informationen zum Power BI-Migrationsprogramm</span><span class="sxs-lookup"><span data-stu-id="01c23-229">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="01c23-230">Erste Schritte mit dem Upgrade von Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="01c23-230">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
