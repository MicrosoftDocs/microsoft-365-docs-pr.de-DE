---
title: Parität zwischen Azure Information Protection für Office 365, betrieben von 21Vianet und kommerziellen Angeboten
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
ms.reviewer: arthurj
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEU150
- GEA150
description: Erfahren Sie mehr über Azure Information Protection (AIP) für Office 365, betrieben von 21Vianet, und wie Sie es für Kunden in China konfigurieren.
monikerRange: o365-21vianet
ms.openlocfilehash: 50269749b5f4e544263f790ec9c7e4474af57219
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840301"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="ac0bd-103">Parität zwischen Azure Information Protection für Office 365, betrieben von 21Vianet und kommerziellen Angeboten</span><span class="sxs-lookup"><span data-stu-id="ac0bd-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="ac0bd-104">Während unser Ziel ist, alle kommerziellen Features und Funktionen für Kunden in China mit unserem Azure Information Protection (AIP) für Office 365, betrieben von 21Vianet, bereitzustellen, gibt es einige fehlende Funktionen, die wir hervorheben möchten.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection (AIP) for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="ac0bd-105">Die folgende Liste enthält die bestehenden Lücken zwischen Azure Information Protection für Office 365, betrieben von 21Vianet und unseren kommerziellen Angeboten ab Januar 2021:</span><span class="sxs-lookup"><span data-stu-id="ac0bd-105">The following list includes the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="ac0bd-106">Verwaltung von Informationsrechten (Information Rights Management, IRM) wird nur für Microsoft 365 Apps for Enterprise (Build 11731.10000 oder höher) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-106">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="ac0bd-107">Office 2010, Office 2013 und andere Office 2016-Versionen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="ac0bd-108">Die Migration Active Directory-Rechteverwaltungsdienste (AD RMS) zu Azure Information Protection ist derzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="ac0bd-109">Die Freigabe geschützter E-Mails an Benutzer in der kommerziellen Cloud wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="ac0bd-110">Die Freigabe von Dokumenten und E-Mail-Anlagen für Benutzer in der kommerziellen Cloud ist derzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="ac0bd-111">Dies umfasst Office 365, betrieben von 21Vianet-Benutzern in der kommerziellen Cloud, Nicht-Office 365-Benutzer, die von 21Vianet-Benutzern in der kommerziellen Cloud betrieben werden, und Benutzer mit einer RMS für Einzelpersonen-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="ac0bd-112">IRM mit SharePoint (IRM-geschützte Websites und Bibliotheken) ist derzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="ac0bd-113">Die Erweiterung für mobile Geräte für AD RMS ist derzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-113">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="ac0bd-114">Der [mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) wird von Azure China 21Vianet nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-114">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="ac0bd-115">Konfigurieren von Azure Information Protection für Kunden in China</span><span class="sxs-lookup"><span data-stu-id="ac0bd-115">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="ac0bd-116">Aktivieren der Rechteverwaltung für den Mandanten</span><span class="sxs-lookup"><span data-stu-id="ac0bd-116">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="ac0bd-117">Damit die Verschlüsselung ordnungsgemäß funktioniert, muss der RMS für den Mandanten aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-117">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="ac0bd-118">Überprüfen Sie, ob rmS aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="ac0bd-118">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="ac0bd-119">Starten Sie PowerShell als Administrator.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-119">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="ac0bd-120">Wenn das Modul AIPService nicht installiert ist, führen Sie `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="ac0bd-120">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="ac0bd-121">Importieren Sie das Modul mithilfe `Import-Module AipService` von .</span><span class="sxs-lookup"><span data-stu-id="ac0bd-121">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="ac0bd-122">Stellen Sie eine Verbindung mit dem Dienst mithilfe von `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="ac0bd-122">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="ac0bd-123">Führen Sie `(Get-AipServiceConfiguration).FunctionalState` die Ausführung aus, und überprüfen Sie, ob der Status `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="ac0bd-123">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="ac0bd-124">Wenn der Funktionsstatus "ist" `Disabled` ist, führen Sie `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="ac0bd-124">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="ac0bd-125">DNS-Konfiguration für Verschlüsselung (Windows)</span><span class="sxs-lookup"><span data-stu-id="ac0bd-125">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="ac0bd-126">Damit die Verschlüsselung ordnungsgemäß funktioniert, müssen die Office-Clientanwendungen eine Verbindung mit der Chinesischen Instanz des Diensts herstellen und von dort bootstrapen.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-126">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="ac0bd-127">Um Clientanwendungen an die richtige Dienstinstanz umzuleiten, muss der Mandantenadministrator einen DNS-SRV-Eintrag mit Informationen zur Azure RMS-URL konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-127">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="ac0bd-128">Ohne den DNS-SRV-Eintrag versucht die Clientanwendung standardmäßig, eine Verbindung mit der öffentlichen Cloudinstanz herzustellen, und es wird ein Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-128">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="ac0bd-129">Außerdem wird davon ausgegangen, dass sich Benutzer mit einem Benutzernamen anmelden, der auf der domäne des Mandanten basiert (z. B. ) und nicht mit dem Benutzernamen (z. B. `joe@contoso.cn` `onmschina` `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="ac0bd-129">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="ac0bd-130">Der Domänenname aus dem Benutzernamen wird für die DNS-Umleitung an die richtige Dienstinstanz verwendet.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-130">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="ac0bd-131">Holen Sie sich die RMS-ID:</span><span class="sxs-lookup"><span data-stu-id="ac0bd-131">Get the RMS ID:</span></span>
  1. <span data-ttu-id="ac0bd-132">Starten Sie PowerShell als Administrator.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-132">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="ac0bd-133">Wenn das Modul AIPService nicht installiert ist, führen Sie `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="ac0bd-133">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="ac0bd-134">Stellen Sie eine Verbindung mit dem Dienst mithilfe von `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="ac0bd-134">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="ac0bd-135">Führen Sie `(Get-AipServiceConfiguration).RightsManagementServiceId` diese Aus, um die RMS-ID zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-135">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="ac0bd-136">Melden Sie sich bei Ihrem DNS-Anbieter an, navigieren Sie zu den DNS-Einstellungen für die Domäne, und fügen Sie dann einen neuen SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-136">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="ac0bd-137">Dienst = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="ac0bd-137">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="ac0bd-138">Protokoll = `_http`</span><span class="sxs-lookup"><span data-stu-id="ac0bd-138">Protocol = `_http`</span></span>
  - <span data-ttu-id="ac0bd-139">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="ac0bd-139">Name = `_tcp`</span></span>
  - <span data-ttu-id="ac0bd-140">Target = `[GUID].rms.aadrm.cn` (wobei GUID die RMS-ID ist)</span><span class="sxs-lookup"><span data-stu-id="ac0bd-140">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="ac0bd-141">Priorität, Gewichtung, Sekunden, TTL = Standardwerte</span><span class="sxs-lookup"><span data-stu-id="ac0bd-141">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="ac0bd-142">Ordnen Sie die benutzerdefinierte Domäne dem Mandanten im [Azure-Portal zu.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)</span><span class="sxs-lookup"><span data-stu-id="ac0bd-142">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="ac0bd-143">Dadurch wird ein Eintrag in DNS hinzugefügt, der einige Minuten dauern kann, um überprüft zu werden, nachdem Sie den Wert zu den DNS-Einstellungen hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-143">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="ac0bd-144">Melden Sie sich beim Microsoft 365 Admin Center mit den entsprechenden globalen Administratoranmeldeinformationen an, und fügen Sie die Domäne (z. B. ) für die `contoso.cn` Benutzererstellung hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-144">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="ac0bd-145">Im Überprüfungsprozess sind möglicherweise zusätzliche DNS-Änderungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-145">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="ac0bd-146">Sobald die Überprüfung erfolgt ist, können Benutzer erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-146">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="ac0bd-147">DNS-Konfiguration für Verschlüsselung (Mac, iOS, Android)</span><span class="sxs-lookup"><span data-stu-id="ac0bd-147">DNS configuration for encryption (Mac, iOS, Android)</span></span>

<span data-ttu-id="ac0bd-148">Melden Sie sich bei Ihrem DNS-Anbieter an, navigieren Sie zu den DNS-Einstellungen für die Domäne, und fügen Sie dann einen neuen SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-148">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="ac0bd-149">Dienst = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="ac0bd-149">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="ac0bd-150">Protokoll = `_http`</span><span class="sxs-lookup"><span data-stu-id="ac0bd-150">Protocol = `_http`</span></span>
- <span data-ttu-id="ac0bd-151">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="ac0bd-151">Name = `_tcp`</span></span>
- <span data-ttu-id="ac0bd-152">Ziel = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="ac0bd-152">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="ac0bd-153">Port = `80`</span><span class="sxs-lookup"><span data-stu-id="ac0bd-153">Port = `80`</span></span>
- <span data-ttu-id="ac0bd-154">Priorität, Gewichtung, Sekunden, TTL = Standardwerte</span><span class="sxs-lookup"><span data-stu-id="ac0bd-154">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="aip-client-configuration"></a><span data-ttu-id="ac0bd-155">Konfiguration des AIP-Clients</span><span class="sxs-lookup"><span data-stu-id="ac0bd-155">AIP client configuration</span></span>

<span data-ttu-id="ac0bd-156">Der einheitliche AIP-Client kann aus dem [Microsoft Download Center heruntergeladen werden.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="ac0bd-156">The unified AIP client can be downloaded from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="ac0bd-157">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="ac0bd-157">For more information, see:</span></span>

- [<span data-ttu-id="ac0bd-158">Dokumentation zu Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="ac0bd-158">Azure Information Protection documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="ac0bd-159">AIP-Versionsverlauf und Supportrichtlinie</span><span class="sxs-lookup"><span data-stu-id="ac0bd-159">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="ac0bd-160">AIP-Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="ac0bd-160">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="ac0bd-161">AIP-Schnellstart: Bereitstellen des AIP-Clients</span><span class="sxs-lookup"><span data-stu-id="ac0bd-161">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="ac0bd-162">Leitfaden für den AIP-Administrator</span><span class="sxs-lookup"><span data-stu-id="ac0bd-162">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="ac0bd-163">Benutzerhandbuch für AIP</span><span class="sxs-lookup"><span data-stu-id="ac0bd-163">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="ac0bd-164">Informationen zu Microsoft 365-Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="ac0bd-164">Learn about Microsoft 365 sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels)

### <a name="aip-apps-configuration-unified-labeling-client-only"></a><span data-ttu-id="ac0bd-165">Konfiguration von AIP-Apps (nur Client mit einheitlichen Bezeichnungen)</span><span class="sxs-lookup"><span data-stu-id="ac0bd-165">AIP apps configuration (unified labeling client only)</span></span>

<span data-ttu-id="ac0bd-166">Für die Einheitliche Bezeichnungslösung benötigen die AIP-Apps unter Windows den folgenden Registrierungsschlüssel, um sie auf die richtige, unabhängigen Cloud für Azure China zu verweisen:</span><span class="sxs-lookup"><span data-stu-id="ac0bd-166">For the unified labeling solution, AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="ac0bd-167">Registrierungsknoten = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="ac0bd-167">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="ac0bd-168">Name = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="ac0bd-168">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="ac0bd-169">Wert = `6` (Standard = 0)</span><span class="sxs-lookup"><span data-stu-id="ac0bd-169">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="ac0bd-170">Typ = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="ac0bd-170">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac0bd-171">Stellen Sie sicher, dass Sie den Registrierungsschlüssel nach einer Deinstallation nicht löschen.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-171">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="ac0bd-172">Wenn der Schlüssel leer, falsch oder nicht vorhanden ist, verhält sich die Funktionalität wie der Standardwert (Standardwert = 0 für die kommerzielle Cloud).</span><span class="sxs-lookup"><span data-stu-id="ac0bd-172">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="ac0bd-173">Wenn der Schlüssel leer oder falsch ist, wird dem Protokoll auch ein Druckfehler hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-173">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="manage-azure-information-protection-content-scan-jobs"></a><span data-ttu-id="ac0bd-174">Verwalten von Azure Information Protection-Inhaltsscanaufträgen</span><span class="sxs-lookup"><span data-stu-id="ac0bd-174">Manage Azure Information Protection content scan jobs</span></span>

<span data-ttu-id="ac0bd-175">Um Ihre Azure Information Protection-Inhaltsscanaufträge mit einem Azure China -Scannerserver zu verwalten, verwenden Sie die folgenden Cmdlets anstelle des Azure-Portals:</span><span class="sxs-lookup"><span data-stu-id="ac0bd-175">To manage your Azure Information Protection content scan jobs with an Azure China scanner server, use the following cmdlets instead of the Azure portal:</span></span><br><br>

| <span data-ttu-id="ac0bd-176">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="ac0bd-176">Cmdlet</span></span> | <span data-ttu-id="ac0bd-177">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac0bd-177">Description</span></span> |
|--|--|
| [<span data-ttu-id="ac0bd-178">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="ac0bd-178">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="ac0bd-179">Fügt Ihrem Inhaltsscanauftrag ein neues Repository hinzu.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-179">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="ac0bd-180">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="ac0bd-180">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="ac0bd-181">Ruft Details zu Ihrem Inhaltsscanauftrag ab.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-181">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="ac0bd-182">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="ac0bd-182">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="ac0bd-183">Ruft Details zu Repositorys ab, die für ihren Inhaltsscanauftrag definiert sind.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-183">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="ac0bd-184">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="ac0bd-184">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="ac0bd-185">Löscht den Auftrag zum Überprüfen von Inhalten.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-185">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="ac0bd-186">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="ac0bd-186">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="ac0bd-187">Entfernt ein Repository aus dem Auftrag zum Überprüfen von Inhalten.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-187">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="ac0bd-188">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="ac0bd-188">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="ac0bd-189">Definiert Einstellungen für ihren Inhaltsscanauftrag.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-189">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="ac0bd-190">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="ac0bd-190">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="ac0bd-191">Definiert Einstellungen für ein vorhandenes Repository in Ihrem Inhaltsscanauftrag.</span><span class="sxs-lookup"><span data-stu-id="ac0bd-191">Defines settings for an existing repository in your content scan job.</span></span> |

<span data-ttu-id="ac0bd-192">Weitere Informationen finden Sie unter [Verwalten Ihrer Aufträge zum Überprüfen von Inhalten nur mithilfe von PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)</span><span class="sxs-lookup"><span data-stu-id="ac0bd-192">For more information, see [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>