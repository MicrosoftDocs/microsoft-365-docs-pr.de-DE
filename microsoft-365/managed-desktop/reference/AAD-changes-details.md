---
title: Details zum Azure Active Directory-Mandanten
description: In diesem Thema werden Änderungen beschrieben, die beim Registrieren von Microsoft Managed Desktop an Ihrem Aad-Konto vorgenommen wurden.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: 6b2b30d8dedba1086bfa9268fb0fdbce20367c20
ms.sourcegitcommit: dd426c686b52cf79325f11022b2d99bc45285577
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2019
ms.locfileid: "35643946"
---
# <a name="azure-active-directory-tenant-details"></a><span data-ttu-id="f4b1c-104">Details zum Azure Active Directory-Mandanten</span><span class="sxs-lookup"><span data-stu-id="f4b1c-104">Azure Active Directory tenant details</span></span>
<span data-ttu-id="f4b1c-105">{blutige Details zu Konten, API-aufrufen, perms usw., etc.}</span><span class="sxs-lookup"><span data-stu-id="f4b1c-105">{gory details about accounts, API calls, perms, etc., etc.}</span></span>


## <a name="data-transmitted-to-and-from-your-aad-account"></a><span data-ttu-id="f4b1c-106">An das und von Ihrem Aad-Konto übermittelte Daten</span><span class="sxs-lookup"><span data-stu-id="f4b1c-106">Data transmitted to and from your AAD account</span></span>


<span data-ttu-id="f4b1c-107">Daten, die von Microsoft an Ihr Konto gesendet wurden:</span><span class="sxs-lookup"><span data-stu-id="f4b1c-107">Data sent to your account from Microsoft:</span></span>

- <span data-ttu-id="f4b1c-108">Gruppennamen</span><span class="sxs-lookup"><span data-stu-id="f4b1c-108">Group names</span></span>
- <span data-ttu-id="f4b1c-109">Konfiguration der Sicherheitsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="f4b1c-109">Security policy configuration</span></span>
- <span data-ttu-id="f4b1c-110">Geräte Bestellungen</span><span class="sxs-lookup"><span data-stu-id="f4b1c-110">Device orders</span></span>
- <span data-ttu-id="f4b1c-111">Benutzerkonten (msadmin, MSTest, mwaas_soc_ro, mwaas_wdgsoc)</span><span class="sxs-lookup"><span data-stu-id="f4b1c-111">User accounts (msadmin, mstest, mwaas_soc_ro, mwaas_wdgsoc)</span></span>
- <span data-ttu-id="f4b1c-112">E5-Lizenzzuweisung zu den Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="f4b1c-112">E5 License assignment to the user accounts</span></span>
- <span data-ttu-id="f4b1c-113">Windows Update-Richtlinien für Update Ringe</span><span class="sxs-lookup"><span data-stu-id="f4b1c-113">Windows update policies for update rings</span></span>

<span data-ttu-id="f4b1c-114">Von Ihrem Konto an Microsoft gesendete Daten:</span><span class="sxs-lookup"><span data-stu-id="f4b1c-114">Data sent to Microsoft from your account:</span></span>

- <span data-ttu-id="f4b1c-115">Geräteupdate-, Nutzungs-und Zuverlässigkeitsdaten</span><span class="sxs-lookup"><span data-stu-id="f4b1c-115">Device update, usage and reliability data</span></span>
- <span data-ttu-id="f4b1c-116">App-Bereitstellungs-und Zuverlässigkeitsdaten</span><span class="sxs-lookup"><span data-stu-id="f4b1c-116">App deployment and reliability data</span></span>
- <span data-ttu-id="f4b1c-117">Update-und Sicherheitsrichtlinien Bereitstellungsdaten</span><span class="sxs-lookup"><span data-stu-id="f4b1c-117">Update and security policy deployment data</span></span>
- <span data-ttu-id="f4b1c-118">Benutzern zugewiesenen Geräten</span><span class="sxs-lookup"><span data-stu-id="f4b1c-118">Users assigned to devices</span></span>  

<span data-ttu-id="f4b1c-119">Daten, die von Ihrem Konto übermittelt werden, werden in Azure SQL-Datenbanken im Microsoft-Mandanten gespeichert, der in den USA gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="f4b1c-119">Data transmitted from your account is stored in Azure SQL databases in the Microsoft tenant hosted in the USA.</span></span> <span data-ttu-id="f4b1c-120">Die Daten werden gemäß den unter {Microsoft Azure Security} beschriebenen Richtlinien gespeichert und verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="f4b1c-120">Data is stored and handled in accordance the policies described in {Microsoft Azure security}.</span></span> 

## <a name="api-permissions-and-calls"></a><span data-ttu-id="f4b1c-121">API-Berechtigungen und-Aufrufe</span><span class="sxs-lookup"><span data-stu-id="f4b1c-121">API permissions and calls</span></span>

<span data-ttu-id="f4b1c-122">**Während der Registrierung:**</span><span class="sxs-lookup"><span data-stu-id="f4b1c-122">**During enrollment:**</span></span>

<span data-ttu-id="f4b1c-123">API-Berechtigungen:</span><span class="sxs-lookup"><span data-stu-id="f4b1c-123">API permissions:</span></span>
- <span data-ttu-id="f4b1c-124">DeviceManagementServiceConfig.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="f4b1c-124">DeviceManagementServiceConfig.ReadWrite.All</span></span>
- <span data-ttu-id="f4b1c-125">Directory.AccessAsUser.All</span><span class="sxs-lookup"><span data-stu-id="f4b1c-125">Directory.AccessAsUser.All</span></span>
- <span data-ttu-id="f4b1c-126">User.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="f4b1c-126">User.ReadWrite.All</span></span>
- <span data-ttu-id="f4b1c-127">DeviceManagementConfiguration.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="f4b1c-127">DeviceManagementConfiguration.ReadWrite.All</span></span>
- <span data-ttu-id="f4b1c-128">DeviceManagementManagedDevices.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="f4b1c-128">DeviceManagementManagedDevices.ReadWrite.All</span></span>
- <span data-ttu-id="f4b1c-129">Group.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="f4b1c-129">Group.ReadWrite.All</span></span>

<span data-ttu-id="f4b1c-130">API-Aufrufe:</span><span class="sxs-lookup"><span data-stu-id="f4b1c-130">API calls:</span></span>
- <span data-ttu-id="f4b1c-131">Post/Organization/{organizationId}/setMobileDeviceManagementAuthority</span><span class="sxs-lookup"><span data-stu-id="f4b1c-131">POST /organization/{organizationId}/setMobileDeviceManagementAuthority</span></span>
- <span data-ttu-id="f4b1c-132">Get/Post-/directoryRoles/{ID}/Members</span><span class="sxs-lookup"><span data-stu-id="f4b1c-132">GET/POST /directoryRoles/{id}/members</span></span>
- <span data-ttu-id="f4b1c-133">Get/Post-/users</span><span class="sxs-lookup"><span data-stu-id="f4b1c-133">GET/POST /users</span></span>
- <span data-ttu-id="f4b1c-134">Get/Post-/Groups</span><span class="sxs-lookup"><span data-stu-id="f4b1c-134">GET/POST /groups</span></span>
- <span data-ttu-id="f4b1c-135">Patch-/Groups/{ID}</span><span class="sxs-lookup"><span data-stu-id="f4b1c-135">PATCH /groups/{id}</span></span>
- <span data-ttu-id="f4b1c-136">Get/Post-/deviceManagement/deviceConfigurations</span><span class="sxs-lookup"><span data-stu-id="f4b1c-136">GET/POST /deviceManagement/deviceConfigurations</span></span>
- <span data-ttu-id="f4b1c-137">/DeviceManagement/detectedApps abrufen</span><span class="sxs-lookup"><span data-stu-id="f4b1c-137">GET /deviceManagement/detectedApps</span></span>

<span data-ttu-id="f4b1c-138">**Nach der Registrierung während der ordentlichen Verwaltung:**</span><span class="sxs-lookup"><span data-stu-id="f4b1c-138">**After enrollment, during ordinary management:**</span></span>

<span data-ttu-id="f4b1c-139">API-Berechtigungen:</span><span class="sxs-lookup"><span data-stu-id="f4b1c-139">API permissions:</span></span>
- <span data-ttu-id="f4b1c-140">DeviceManagementManagedDevices.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="f4b1c-140">DeviceManagementManagedDevices.ReadWrite.All</span></span>
- <span data-ttu-id="f4b1c-141">DeviceManagementApps.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="f4b1c-141">DeviceManagementApps.ReadWrite.All</span></span>
- <span data-ttu-id="f4b1c-142">DeviceManagementConfiguration.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="f4b1c-142">DeviceManagementConfiguration.ReadWrite.All</span></span>
- <span data-ttu-id="f4b1c-143">Reports.Read.All</span><span class="sxs-lookup"><span data-stu-id="f4b1c-143">Reports.Read.All</span></span>
- <span data-ttu-id="f4b1c-144">User.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="f4b1c-144">User.ReadWrite.All</span></span>
- <span data-ttu-id="f4b1c-145">Group.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="f4b1c-145">Group.ReadWrite.All</span></span>
- <span data-ttu-id="f4b1c-146">Directory.AccessAsUser.All</span><span class="sxs-lookup"><span data-stu-id="f4b1c-146">Directory.AccessAsUser.All</span></span>

<span data-ttu-id="f4b1c-147">API-Aufrufe:</span><span class="sxs-lookup"><span data-stu-id="f4b1c-147">API calls:</span></span>
- <span data-ttu-id="f4b1c-148">Get/Post-/directoryRoles/{ID}/Members</span><span class="sxs-lookup"><span data-stu-id="f4b1c-148">GET/POST /directoryRoles/{id}/members</span></span>
- <span data-ttu-id="f4b1c-149">Get/Patch/Post/users</span><span class="sxs-lookup"><span data-stu-id="f4b1c-149">GET/PATCH/POST /users</span></span>
- <span data-ttu-id="f4b1c-150">Get/Post-/Groups</span><span class="sxs-lookup"><span data-stu-id="f4b1c-150">GET/POST /groups</span></span>
- <span data-ttu-id="f4b1c-151">Patch-/Groups/{ID}</span><span class="sxs-lookup"><span data-stu-id="f4b1c-151">PATCH /groups/{id}</span></span>
- <span data-ttu-id="f4b1c-152">Get/Post-/deviceManagement/deviceConfigurations</span><span class="sxs-lookup"><span data-stu-id="f4b1c-152">GET/POST /deviceManagement/deviceConfigurations</span></span>
- <span data-ttu-id="f4b1c-153">Get/Post-/deviceAppManagement/mobileApps</span><span class="sxs-lookup"><span data-stu-id="f4b1c-153">GET/POST /deviceAppManagement/mobileApps</span></span>
- <span data-ttu-id="f4b1c-154">/DeviceManagement/detectedApps abrufen</span><span class="sxs-lookup"><span data-stu-id="f4b1c-154">GET /deviceManagement/detectedApps</span></span>
- <span data-ttu-id="f4b1c-155">/Devices abrufen</span><span class="sxs-lookup"><span data-stu-id="f4b1c-155">GET /devices</span></span>
- <span data-ttu-id="f4b1c-156">Post/users/{ID | userPrincipalName}/assignLicense</span><span class="sxs-lookup"><span data-stu-id="f4b1c-156">POST /users/{id | userPrincipalName}/assignLicense</span></span>
- <span data-ttu-id="f4b1c-157">/SubscribedSkus abrufen</span><span class="sxs-lookup"><span data-stu-id="f4b1c-157">GET /subscribedSkus</span></span>

## <a name="accounts-used-by-microsoft-managed-desktop"></a><span data-ttu-id="f4b1c-158">Von Microsoft Managed Desktop verwendete Konten</span><span class="sxs-lookup"><span data-stu-id="f4b1c-158">Accounts used by Microsoft Managed Desktop</span></span>





| <span data-ttu-id="f4b1c-159">Konto</span><span class="sxs-lookup"><span data-stu-id="f4b1c-159">Account</span></span> | <span data-ttu-id="f4b1c-160">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4b1c-160">Description</span></span>  | <span data-ttu-id="f4b1c-161">Bedingter Zugriff</span><span class="sxs-lookup"><span data-stu-id="f4b1c-161">Conditional access</span></span>  | <span data-ttu-id="f4b1c-162">Mehrstufige Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="f4b1c-162">Multi-factor authentication</span></span>  | <span data-ttu-id="f4b1c-163">Gründe für die ordnungsgemäße</span><span class="sxs-lookup"><span data-stu-id="f4b1c-163">Why this is OK</span></span> |
|---------|---------|---------|---------|--------------|
| <span data-ttu-id="f4b1c-164">msadmin @ \* onmmicrosoft. com</span><span class="sxs-lookup"><span data-stu-id="f4b1c-164">msadmin@\*onmmicrosoft.com</span></span> | <span data-ttu-id="f4b1c-165">Das beschränkte Dienstkonto mit Administratorrechten, das als Microsoft InTune und Benutzer Administrator verwendet wird {What es this?}</span><span class="sxs-lookup"><span data-stu-id="f4b1c-165">Limited service account with administrator privileges, used as a Microsoft Intune and User administrator {what's this?}</span></span> <span data-ttu-id="f4b1c-166">So definieren und konfigurieren Sie den Mandanten für moderne Desktop Geräte von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f4b1c-166">to define and configure the tenant for Microsoft Modern Desktop devices.</span></span><span data-ttu-id="f4b1c-167">Verfügt nicht über interaktive Anmeldeberechtigungen; führt Vorgänge nur über den Dienst aus.</span><span class="sxs-lookup"><span data-stu-id="f4b1c-167">  Does not have interactive login permissions; performs operations only through the service.</span></span>  | <span data-ttu-id="f4b1c-168">Ausgeschlossen, da Sie nicht in Ihrem Netzwerk stammt</span><span class="sxs-lookup"><span data-stu-id="f4b1c-168">Excluded, because it doesn't originate in your network</span></span>        | <span data-ttu-id="f4b1c-169">Ausgeschlossen, da keine interaktive Anmeldung vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="f4b1c-169">Excluded because there is no interactive logon</span></span>        | <span data-ttu-id="f4b1c-170">Im Azure Key Vault gespeichertes Kennwort</span><span class="sxs-lookup"><span data-stu-id="f4b1c-170">Password stored in Azure Key Vault</span></span> |
| <span data-ttu-id="f4b1c-171">MSTest @ \* onmmicrosoft. com</span><span class="sxs-lookup"><span data-stu-id="f4b1c-171">mstest@\*onmmicrosoft.com</span></span>     |         |         |         |
| <span data-ttu-id="f4b1c-172">mssupport @ \* onmmicrosoft. com</span><span class="sxs-lookup"><span data-stu-id="f4b1c-172">mssupport@\*onmmicrosoft.com</span></span>     |         |         |         |
| <span data-ttu-id="f4b1c-173">msadminint @ \* onmmicrosoft. com</span><span class="sxs-lookup"><span data-stu-id="f4b1c-173">msadminint@\*onmmicrosoft.com</span></span>     |         |         |         |
