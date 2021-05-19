---
title: Azure Information Protection-Unterstützung für Office 365 betrieben von 21Vianet
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: Erfahren Sie mehr über Azure Information Protection (AIP) für Office 365 betrieben von 21Vianet und wie Sie es für Kunden in China konfigurieren.
monikerRange: o365-21vianet
ms.openlocfilehash: 8b85ae43df31bb1947b841d616cc83c3a0b614e4
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535842"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="ecd89-103">Azure Information Protection-Unterstützung für Office 365 betrieben von 21Vianet</span><span class="sxs-lookup"><span data-stu-id="ecd89-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="ecd89-104">Dieser Artikel behandelt die Unterschiede zwischen Azure Information Protection (AIP)-Unterstützung für Office 365 betrieben von 21Vianet und kommerziellen Angeboten sowie spezifische Anweisungen zum Konfigurieren von AIP für Kunden in China, einschließlich der Installation des lokalen AIP-Scanners und verwalten von Inhaltsscanaufträgen. &mdash;</span><span class="sxs-lookup"><span data-stu-id="ecd89-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="ecd89-105">Unterschiede zwischen AIP für Office 365 von 21Vianet und kommerziellen Angeboten</span><span class="sxs-lookup"><span data-stu-id="ecd89-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="ecd89-106">Unser Ziel ist es zwar, kunden in China alle kommerziellen Features und Funktionen mit unserem AIP für Office 365 betrieben von 21Vianet bereitzustellen, es fehlen jedoch einige Funktionen, die wir hervorheben möchten.</span><span class="sxs-lookup"><span data-stu-id="ecd89-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="ecd89-107">Die folgende Liste enthält die bestehenden Lücken zwischen AIP für Office 365 betrieben von 21Vianet und unseren kommerziellen Angeboten ab Januar 2021:</span><span class="sxs-lookup"><span data-stu-id="ecd89-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="ecd89-108">Verwaltung von Informationsrechten (Information Rights Management, IRM) wird nur für Microsoft 365 Apps for Enterprise (Build 11731.10000 oder höher) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ecd89-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="ecd89-109">Office 2010, Office 2013 und andere versionen Office 2016 werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ecd89-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="ecd89-110">Die Migration von Active Directory Rights Management Services (AD RMS) zu AIP ist derzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ecd89-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="ecd89-111">Die Freigabe geschützter E-Mails für Benutzer in der kommerziellen Cloud wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ecd89-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="ecd89-112">Die Freigabe von Dokumenten und E-Mail-Anlagen für Benutzer in der kommerziellen Cloud ist derzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ecd89-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="ecd89-113">Dazu gehören Office 365, die von 21Vianet-Benutzern in der kommerziellen Cloud betrieben werden, nicht von Office 365 betrieben von 21Vianet-Benutzern in der kommerziellen Cloud und Von Benutzern mit einer RMS for Individuals-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="ecd89-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="ecd89-114">IRM mit SharePoint (IRM-geschützte Websites und Bibliotheken) ist derzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ecd89-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="ecd89-115">Die Mobile Device Extension für AD RMS ist derzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ecd89-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="ecd89-116">Der [mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) wird von Azure China 21Vianet nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ecd89-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

- <span data-ttu-id="ecd89-117">Der AIP-Bereich des Azure-Portals ist für Kunden in China nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ecd89-117">The AIP area of the Azure portal is unavailable to customers in China.</span></span> <span data-ttu-id="ecd89-118">Verwenden [Sie PowerShell-Befehle,](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) anstatt Aktionen im Portal auszuführen, z. B. verwalten und ausführen Sie Ihre Inhaltsscanaufträge.</span><span class="sxs-lookup"><span data-stu-id="ecd89-118">Use [PowerShell commands](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) instead of performing actions in the portal, such as managing and running your content scan jobs.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="ecd89-119">Konfigurieren von AIP für Kunden in China</span><span class="sxs-lookup"><span data-stu-id="ecd89-119">Configure AIP for customers in China</span></span>

<span data-ttu-id="ecd89-120">So konfigurieren Sie AIP für Kunden in China:</span><span class="sxs-lookup"><span data-stu-id="ecd89-120">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="ecd89-121">[Aktivieren der Rechteverwaltung für den Mandanten](#step-1-enable-rights-management-for-the-tenant).</span><span class="sxs-lookup"><span data-stu-id="ecd89-121">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

1. <span data-ttu-id="ecd89-122">[Fügen Sie den Dienstprinzipal des Microsoft Information Protection Sync Service hinzu.](#step-2-add-the-microsoft-information-protection-sync-service-service-principal)</span><span class="sxs-lookup"><span data-stu-id="ecd89-122">[Add the Microsoft Information Protection Sync Service service principal](#step-2-add-the-microsoft-information-protection-sync-service-service-principal).</span></span>

1. <span data-ttu-id="ecd89-123">[Konfigurieren der DNS-Verschlüsselung](#step-3-configure-dns-encryption).</span><span class="sxs-lookup"><span data-stu-id="ecd89-123">[Configure DNS encryption](#step-3-configure-dns-encryption).</span></span>

1. <span data-ttu-id="ecd89-124">[Installieren und Konfigurieren des AIP Unified Labeling-Clients](#step-4-install-and-configure-the-aip-unified-labeling-client).</span><span class="sxs-lookup"><span data-stu-id="ecd89-124">[Install and configure the AIP unified labeling client](#step-4-install-and-configure-the-aip-unified-labeling-client).</span></span>

1. <span data-ttu-id="ecd89-125">[Konfigurieren von AIP-Apps auf Windows](#step-5-configure-aip-apps-on-windows).</span><span class="sxs-lookup"><span data-stu-id="ecd89-125">[Configure AIP apps on Windows](#step-5-configure-aip-apps-on-windows).</span></span>

1. <span data-ttu-id="ecd89-126">[Installieren Sie den lokalen AIP-Scanner, und verwalten Sie Inhaltsscanaufträge.](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)</span><span class="sxs-lookup"><span data-stu-id="ecd89-126">[Install the AIP on-premises scanner and manage content scan jobs](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="ecd89-127">Schritt 1: Aktivieren der Rechteverwaltung für den Mandanten</span><span class="sxs-lookup"><span data-stu-id="ecd89-127">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="ecd89-128">Damit die Verschlüsselung ordnungsgemäß funktioniert, muss RMS für den Mandanten aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="ecd89-128">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="ecd89-129">Überprüfen Sie, ob RMS aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="ecd89-129">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="ecd89-130">Starten Sie PowerShell als Administrator.</span><span class="sxs-lookup"><span data-stu-id="ecd89-130">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="ecd89-131">Wenn das AIPService-Modul nicht installiert ist, führen Sie `Install-Module AipService` aus.</span><span class="sxs-lookup"><span data-stu-id="ecd89-131">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="ecd89-132">Importieren Sie das Modul mithilfe `Import-Module AipService` von .</span><span class="sxs-lookup"><span data-stu-id="ecd89-132">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="ecd89-133">Verbinden dem Dienst mithilfe von `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="ecd89-133">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="ecd89-134">Führen `(Get-AipServiceConfiguration).FunctionalState` Sie aus, und überprüfen Sie, ob der Status `Enabled` ist.</span><span class="sxs-lookup"><span data-stu-id="ecd89-134">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="ecd89-135">Wenn der Funktionszustand `Disabled` ist, führen Sie `Enable-AipService` aus.</span><span class="sxs-lookup"><span data-stu-id="ecd89-135">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-add-the-microsoft-information-protection-sync-service-service-principal"></a><span data-ttu-id="ecd89-136">Schritt 2: Hinzufügen des Dienstprinzipal des Microsoft Information Protection-Synchronisierungsdiensts</span><span class="sxs-lookup"><span data-stu-id="ecd89-136">Step 2: Add the Microsoft Information Protection Sync Service service principal</span></span>

<span data-ttu-id="ecd89-137">Der **Microsoft Information Protection Sync Service-Dienstprinzipal** ist in Azure China-Mandanten standardmäßig nicht verfügbar und ist für Azure Information Protection erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ecd89-137">The **Microsoft Information Protection Sync Service** service principal is not available in Azure China tenants by default, and is required for Azure Information Protection.</span></span>

1. <span data-ttu-id="ecd89-138">Erstellen Sie diesen Dienstprinzipal manuell mit dem [Cmdlet New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) und der Anwendungs-ID für `870c4f2e-85b6-4d43-bdda-6ed9a579b725` den Microsoft Information Protection Sync Service.</span><span class="sxs-lookup"><span data-stu-id="ecd89-138">Create this service principal manually using the [New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) cmdlet and the `870c4f2e-85b6-4d43-bdda-6ed9a579b725` application ID for the Microsoft Information Protection Sync Service.</span></span> 

    ```powershell 
    New-AzADServicePrincipal -ApplicationId 870c4f2e-85b6-4d43-bdda-6ed9a579b725
    ```

1. <span data-ttu-id="ecd89-139">Fügen Sie nach dem Hinzufügen des Dienstprinzipal die relevanten Berechtigungen hinzu, die für den Dienst erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="ecd89-139">After adding the service principal, add the relevant permissions required to the service.</span></span>

### <a name="step-3-configure-dns-encryption"></a><span data-ttu-id="ecd89-140">Schritt 3: Konfigurieren der DNS-Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="ecd89-140">Step 3: Configure DNS encryption</span></span>

<span data-ttu-id="ecd89-141">Damit die Verschlüsselung ordnungsgemäß funktioniert, Office Clientanwendungen eine Verbindung mit der China-Instanz des Diensts herstellen und bootstrap von dort aus.</span><span class="sxs-lookup"><span data-stu-id="ecd89-141">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="ecd89-142">Um Clientanwendungen an die richtige Dienstinstanz umzuleiten, muss der Mandantenadministrator einen DNS-SRV-Eintrag mit Informationen zur Azure RMS-URL konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ecd89-142">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="ecd89-143">Ohne den DNS-SRV-Eintrag versucht die Clientanwendung standardmäßig, eine Verbindung mit der öffentlichen Cloudinstanz herzustellen, und es wird ein Fehler ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ecd89-143">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="ecd89-144">Außerdem wird davon ausgegangen, dass sich Benutzer mit einem Benutzernamen anmelden, der auf der Domäne im Besitz des Mandanten basiert (z. B. ), und nicht mit dem Benutzernamen (z. B. `joe@contoso.cn` `onmschina` `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="ecd89-144">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="ecd89-145">Der Domänenname aus dem Benutzernamen wird für die DNS-Umleitung an die richtige Dienstinstanz verwendet.</span><span class="sxs-lookup"><span data-stu-id="ecd89-145">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="ecd89-146">Konfigurieren der DNS-Verschlüsselung – Windows</span><span class="sxs-lookup"><span data-stu-id="ecd89-146">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="ecd89-147">Hier erhalten Sie die RMS-ID:</span><span class="sxs-lookup"><span data-stu-id="ecd89-147">Get the RMS ID:</span></span>

    1. <span data-ttu-id="ecd89-148">Starten Sie PowerShell als Administrator.</span><span class="sxs-lookup"><span data-stu-id="ecd89-148">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="ecd89-149">Wenn das AIPService-Modul nicht installiert ist, führen Sie `Install-Module AipService` aus.</span><span class="sxs-lookup"><span data-stu-id="ecd89-149">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="ecd89-150">Verbinden dem Dienst mithilfe von `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="ecd89-150">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="ecd89-151">Führen `(Get-AipServiceConfiguration).RightsManagementServiceId` Sie aus, um die RMS-ID zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ecd89-151">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="ecd89-152">Melden Sie sich bei Ihrem DNS-Anbieter an, navigieren Sie zu den DNS-Einstellungen für die Domäne, und fügen Sie dann einen neuen SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="ecd89-152">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="ecd89-153">Dienst = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="ecd89-153">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="ecd89-154">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="ecd89-154">Protocol = `_http`</span></span>
    - <span data-ttu-id="ecd89-155">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="ecd89-155">Name = `_tcp`</span></span>
    - <span data-ttu-id="ecd89-156">Target = `[GUID].rms.aadrm.cn` (wobei GUID die RMS-ID ist)</span><span class="sxs-lookup"><span data-stu-id="ecd89-156">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="ecd89-157">Priorität, Gewichtung, Sekunden, TTL = Standardwerte</span><span class="sxs-lookup"><span data-stu-id="ecd89-157">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="ecd89-158">Ordnen Sie die benutzerdefinierte Domäne dem Mandanten im [Azure-Portal zu.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)</span><span class="sxs-lookup"><span data-stu-id="ecd89-158">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="ecd89-159">Dadurch wird ein Eintrag in DNS hinzugefügt, der einige Minuten dauern kann, um überprüft zu werden, nachdem Sie den Wert zu den DNS-Einstellungen hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="ecd89-159">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="ecd89-160">Melden Sie sich beim Microsoft 365 Admin Center mit den entsprechenden globalen Administratoranmeldeinformationen an, und fügen Sie die Domäne (z. B. ) für die `contoso.cn` Benutzererstellung hinzu.</span><span class="sxs-lookup"><span data-stu-id="ecd89-160">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="ecd89-161">Bei der Überprüfung sind möglicherweise zusätzliche DNS-Änderungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ecd89-161">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="ecd89-162">Sobald die Überprüfung erfolgt ist, können Benutzer erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ecd89-162">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="ecd89-163">Konfigurieren der DNS-Verschlüsselung – Mac, iOS, Android</span><span class="sxs-lookup"><span data-stu-id="ecd89-163">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="ecd89-164">Melden Sie sich bei Ihrem DNS-Anbieter an, navigieren Sie zu den DNS-Einstellungen für die Domäne, und fügen Sie dann einen neuen SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="ecd89-164">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="ecd89-165">Dienst = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="ecd89-165">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="ecd89-166">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="ecd89-166">Protocol = `_http`</span></span>
- <span data-ttu-id="ecd89-167">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="ecd89-167">Name = `_tcp`</span></span>
- <span data-ttu-id="ecd89-168">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="ecd89-168">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="ecd89-169">Port = `80`</span><span class="sxs-lookup"><span data-stu-id="ecd89-169">Port = `80`</span></span>
- <span data-ttu-id="ecd89-170">Priorität, Gewichtung, Sekunden, TTL = Standardwerte</span><span class="sxs-lookup"><span data-stu-id="ecd89-170">Priority, Weight, Seconds, TTL = default values</span></span>


### <a name="step-4-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="ecd89-171">Schritt 4: Installieren und Konfigurieren des AIP Unified Labeling-Clients</span><span class="sxs-lookup"><span data-stu-id="ecd89-171">Step 4: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="ecd89-172">Laden Sie den AIP Unified Labeling-Client aus dem Microsoft Download Center herunter, und [installieren Sie den AIP-Client für einheitliche Bezeichnungen.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="ecd89-172">Download and install the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="ecd89-173">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="ecd89-173">For more information, see:</span></span>

- [<span data-ttu-id="ecd89-174">AIP-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="ecd89-174">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="ecd89-175">AIP-Versionsverlauf und Supportrichtlinie</span><span class="sxs-lookup"><span data-stu-id="ecd89-175">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="ecd89-176">AIP-Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="ecd89-176">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="ecd89-177">AIP-Schnellstart: Bereitstellen des AIP-Clients</span><span class="sxs-lookup"><span data-stu-id="ecd89-177">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="ecd89-178">AIP-Administratorhandbuch</span><span class="sxs-lookup"><span data-stu-id="ecd89-178">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="ecd89-179">AIP-Benutzerhandbuch</span><span class="sxs-lookup"><span data-stu-id="ecd89-179">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="ecd89-180">Informationen zu Microsoft 365 Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="ecd89-180">Learn about Microsoft 365 sensitivity labels</span></span>](../../compliance/sensitivity-labels.md)

### <a name="step-5-configure-aip-apps-on-windows"></a><span data-ttu-id="ecd89-181">Schritt 5: Konfigurieren von AIP-Apps auf Windows</span><span class="sxs-lookup"><span data-stu-id="ecd89-181">Step 5: Configure AIP apps on Windows</span></span>

<span data-ttu-id="ecd89-182">AIP-apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span><span class="sxs-lookup"><span data-stu-id="ecd89-182">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="ecd89-183">Registrierungsknoten = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="ecd89-183">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="ecd89-184">Name = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="ecd89-184">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="ecd89-185">Wert = `6` (Standard = 0)</span><span class="sxs-lookup"><span data-stu-id="ecd89-185">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="ecd89-186">Type = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="ecd89-186">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ecd89-187">Stellen Sie sicher, dass Sie den Registrierungsschlüssel nach einer Deinstallation nicht löschen.</span><span class="sxs-lookup"><span data-stu-id="ecd89-187">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="ecd89-188">Wenn der Schlüssel leer, falsch oder nicht vorhanden ist, verhält sich die Funktionalität als Standardwert (Standardwert = 0 für die kommerzielle Cloud).</span><span class="sxs-lookup"><span data-stu-id="ecd89-188">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="ecd89-189">Wenn der Schlüssel leer oder falsch ist, wird dem Protokoll auch ein Druckfehler hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ecd89-189">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="ecd89-190">Schritt 6: Installieren des lokalen AIP-Scanners und Verwalten von Inhaltsscanaufträgen</span><span class="sxs-lookup"><span data-stu-id="ecd89-190">Step 6: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="ecd89-191">Installieren Sie den lokalen AIP-Scanner, um Ihre Netzwerk- und Inhaltsfreigaben auf vertrauliche Daten zu überprüfen, und wenden Sie Klassifizierungs- und Schutzbezeichnungen an, wie in der Richtlinie Ihrer Organisation konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="ecd89-191">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

<span data-ttu-id="ecd89-192">Verwenden Sie beim Konfigurieren und Verwalten Ihrer Aufträge für Inhaltsscans das folgende Verfahren anstelle der [Azure-Portalschnittstelle,](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) die von den kommerziellen Angeboten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ecd89-192">When configuring and managing your content scan jobs, use the following procedure instead of the [Azure portal interface](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) that's used by the commercial offerings.</span></span>

<span data-ttu-id="ecd89-193">Weitere Informationen finden Sie unter [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) und Manage your content scan jobs using [PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span><span class="sxs-lookup"><span data-stu-id="ecd89-193">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>

<span data-ttu-id="ecd89-194">**So installieren und konfigurieren Sie den Scanner:**</span><span class="sxs-lookup"><span data-stu-id="ecd89-194">**To install and configure your scanner**:</span></span>

1. <span data-ttu-id="ecd89-195">Melden Sie sich beim Windows Servercomputer an, auf dem der Scanner ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ecd89-195">Sign in to the Windows Server computer that will run the scanner.</span></span> <span data-ttu-id="ecd89-196">Verwenden Sie ein Konto, das über lokale Administratorrechte verfügt und über Berechtigungen zum Schreiben in die SQL Server verfügt.</span><span class="sxs-lookup"><span data-stu-id="ecd89-196">Use an account that has local administrator rights and that has permissions to write to the SQL Server master database.</span></span>

1. <span data-ttu-id="ecd89-197">Beginnen Sie mit dem Schließen von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ecd89-197">Start with PowerShell closed.</span></span> <span data-ttu-id="ecd89-198">Wenn Sie den AIP-Client und -Scanner bereits installiert haben, stellen Sie sicher, dass der **AIPScanner-Dienst** beendet wird.</span><span class="sxs-lookup"><span data-stu-id="ecd89-198">If you've previously installed the AIP client and scanner, make sure that the **AIPScanner** service is stopped.</span></span>

1. <span data-ttu-id="ecd89-199">Öffnen Sie Windows PowerShell sitzung mit der **Option Als Administrator ausführen.**</span><span class="sxs-lookup"><span data-stu-id="ecd89-199">Open a Windows PowerShell session with the **Run as an administrator** option.</span></span>

1. <span data-ttu-id="ecd89-200">Führen Sie [das Cmdlet Install-AIPScanner](/powershell/module/azureinformationprotection/Install-AIPScanner) aus, und geben Sie Ihre SQL Server-Instanz an, in der eine Datenbank für den Azure Information Protection-Scanner erstellt werden soll, und einen aussagekräftigen Namen für Ihren Scannercluster.</span><span class="sxs-lookup"><span data-stu-id="ecd89-200">Run the [Install-AIPScanner](/powershell/module/azureinformationprotection/Install-AIPScanner) cmdlet, specifying your SQL Server instance on which to create a database for the Azure Information Protection scanner, and a meaningful name for your scanner cluster.</span></span>

    ```PowerShell
    Install-AIPScanner -SqlServerInstance <name> -Cluster <cluster name>
    ```

    > [!TIP]
    > <span data-ttu-id="ecd89-201">Sie können denselben Clusternamen im [Befehl Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) verwenden, um mehrere Scannerknoten demselben Cluster zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="ecd89-201">You can use the same cluster name in the [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) command to associate multiple scanner nodes to the same cluster.</span></span> <span data-ttu-id="ecd89-202">Wenn Sie denselben Cluster für mehrere Scannerknoten verwenden, können mehrere Scanner zusammenarbeiten, um Ihre Scans durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="ecd89-202">Using the same cluster for multiple scanner nodes enables multiple scanners to work together to perform your scans.</span></span>
    > 

1. <span data-ttu-id="ecd89-203">Stellen Sie sicher, dass der Dienst jetzt mithilfe von **Administrative Tools Services installiert**  >  **ist.**</span><span class="sxs-lookup"><span data-stu-id="ecd89-203">Verify that the service is now installed by using **Administrative Tools** > **Services**.</span></span>

    <span data-ttu-id="ecd89-204">Der installierte Dienst heißt **Azure Information Protection Scanner** und wird für die Ausführung mithilfe des von Ihnen erstellten Scannerdienstkontos konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="ecd89-204">The installed service is named **Azure Information Protection Scanner** and is configured to run by using the scanner service account that you created.</span></span>

1. <span data-ttu-id="ecd89-205">Erhalten Sie ein Azure-Token, das mit Ihrem Scanner verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ecd89-205">Get an Azure token to use with your scanner.</span></span> <span data-ttu-id="ecd89-206">Ein Azure AD-Token ermöglicht es dem Scanner, sich beim Azure Information Protection-Dienst zu authentifizieren, sodass der Scanner nicht interaktiv ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ecd89-206">An Azure AD token allows the scanner to authenticate to the Azure Information Protection service, enabling the scanner to run non-interactively.</span></span> 

    1. <span data-ttu-id="ecd89-207">Öffnen Sie das Azure-Portal, und erstellen Sie eine Azure AD-Anwendung, um ein Zugriffstoken für die Authentifizierung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ecd89-207">Open the Azure portal and create an Azure AD application to specify an access token for authentication.</span></span> <span data-ttu-id="ecd89-208">Weitere Informationen finden Sie unter [How to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).</span><span class="sxs-lookup"><span data-stu-id="ecd89-208">For more information, see [How to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).</span></span>
    
        > [!TIP]
        > <span data-ttu-id="ecd89-209">Beim Erstellen und Konfigurieren von Azure AD-Anwendungen für den Befehl  [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) zeigt der Bereich Api-Berechtigungen anfordern die **APIs** an, die meine Organisation verwendet, anstelle der **Registerkarte Microsoft-APIs.** Wählen Sie **die APIs aus,** die meine Organisation verwendet, um dann **Azure Rights Management Services auszuwählen.**</span><span class="sxs-lookup"><span data-stu-id="ecd89-209">When creating and configuring Azure AD applications for the [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) command, the **Request API permissions** pane shows the **APIs my organization uses** tab instead of the **Microsoft APIs** tab. Select the **APIs my organization uses** to then select **Azure Rights Management Services**.</span></span> 
        >

    1. <span data-ttu-id="ecd89-210">Melden Sie Windows Servercomputer an, und starten Sie  eine PowerShell-Sitzung, wenn Ihrem Scannerdienstkonto die lokale Anmeldung für die Installation erteilt wurde.</span><span class="sxs-lookup"><span data-stu-id="ecd89-210">From the Windows Server computer, if your scanner service account has been granted the **Log on locally** right for the installation, sign in with this account and start a PowerShell session.</span></span> 
    
        <span data-ttu-id="ecd89-211">Wenn Ihrem Scannerdienstkonto das  Lokale Anmelden für die Installation nicht erteilt werden kann, verwenden Sie den *Parameter OnBehalfOf* mit [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), wie unter How [to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ecd89-211">If your scanner service account cannot be granted the **Log on locally** right for the installation, use the *OnBehalfOf* parameter with [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), as described in [How to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).</span></span>

    1. <span data-ttu-id="ecd89-212">Führen [Sie Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication)aus, und geben Sie Werte an, die aus Ihrer Azure AD-Anwendung kopiert wurden:</span><span class="sxs-lookup"><span data-stu-id="ecd89-212">Run [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), specifying values copied from your Azure AD application:</span></span>

      ```PowerShell
      Set-AIPAuthentication -AppId <ID of the registered app> -AppSecret <client secret sting> -TenantId <your tenant ID> -DelegatedUser <Azure AD account>
      ```

      <span data-ttu-id="ecd89-213">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ecd89-213">For example:</span></span>

      ```PowerShell
      $pscreds = Get-Credential CONTOSO\scanner
      Set-AIPAuthentication -AppId "77c3c1c3-abf9-404e-8b2b-4652836c8c66" -AppSecret "OAkk+rnuYc/u+]ah2kNxVbtrDGbS47L4" -DelegatedUser scanner@contoso.com -TenantId "9c11c87a-ac8b-46a3-8d5c-f4d0b72ee29a" -OnBehalfOf $pscreds
      Acquired application access token on behalf of CONTOSO\scanner.
      ```

    <span data-ttu-id="ecd89-214">Der Scanner verfügt jetzt über ein Token zur Authentifizierung bei Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ecd89-214">The scanner now has a token to authenticate to Azure AD.</span></span> <span data-ttu-id="ecd89-215">Dieses Token ist je nach Konfiguration des geheimen **Web-App-/API-Clientgeheimnis** in Azure AD ein Jahr, zwei Jahre oder nie gültig.</span><span class="sxs-lookup"><span data-stu-id="ecd89-215">This token is valid for one year, two years, or never, according to your configuration of the **Web app /API** client secret in Azure AD.</span></span> <span data-ttu-id="ecd89-216">Wenn das Token abläuft, müssen Sie dieses Verfahren wiederholen.</span><span class="sxs-lookup"><span data-stu-id="ecd89-216">When the token expires, you must repeat this procedure.</span></span>

1. <span data-ttu-id="ecd89-217">Führen Sie [das Cmdlet Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) aus, um die Funktion des Scanners im Offlinemodus zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ecd89-217">Run the [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) cmdlet to set the scanner to function in offline mode.</span></span> <span data-ttu-id="ecd89-218">Ausführen:</span><span class="sxs-lookup"><span data-stu-id="ecd89-218">Run:</span></span>

    ```powershell
    Set-AIPScannerConfiguration -OnlineConfiguration Off
    ```

1. <span data-ttu-id="ecd89-219">Führen Sie [das Cmdlet Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) aus, um einen Standardauftrag zum Überprüfen von Inhalten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ecd89-219">Run the [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) cmdlet to create a default content scan job.</span></span>

    <span data-ttu-id="ecd89-220">Der einzige erforderliche Parameter im **Cmdlet Set-AIPScannerContentScanJob** ist **Enforce**.</span><span class="sxs-lookup"><span data-stu-id="ecd89-220">The only required parameter in the **Set-AIPScannerContentScanJob** cmdlet is **Enforce**.</span></span> <span data-ttu-id="ecd89-221">Möglicherweise möchten Sie jedoch zu diesem Zeitpunkt andere Einstellungen für Ihren Inhaltsscanauftrag definieren.</span><span class="sxs-lookup"><span data-stu-id="ecd89-221">However, you may want to define other settings for your content scan job at this time.</span></span> <span data-ttu-id="ecd89-222">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ecd89-222">For example:</span></span>

    ```powershell
    Set-AIPScannerContentScanJob -Schedule Manual -DiscoverInformationTypes PolicyOnly -Enforce Off -DefaultLabelType PolicyDefault -RelabelFiles Off -PreserveFileDetails On -IncludeFileTypes '' -ExcludeFileTypes '.msg,.tmp' -DefaultOwner <account running the scanner>
    ```

    <span data-ttu-id="ecd89-223">Die obige Syntax konfiguriert die folgenden Einstellungen, während Sie die Konfiguration fortsetzen:</span><span class="sxs-lookup"><span data-stu-id="ecd89-223">The syntax above configures the following settings while you continue the configuration:</span></span>

    - <span data-ttu-id="ecd89-224">Sorgt dafür, dass die Planung für die Ausführung des Scanners manuell *ausgeführt wird*</span><span class="sxs-lookup"><span data-stu-id="ecd89-224">Keeps the scanner run scheduling to *manual*</span></span>
    - <span data-ttu-id="ecd89-225">Legt die informationstypen fest, die basierend auf der Vertraulichkeitsbezeichnungsrichtlinie ermittelt werden sollen</span><span class="sxs-lookup"><span data-stu-id="ecd89-225">Sets the information types to be discovered based on the sensitivity labeling policy</span></span>
    - <span data-ttu-id="ecd89-226">*Erzwingt* keine Vertraulichkeitsbezeichnungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="ecd89-226">Does *not* enforce a sensitivity labeling policy</span></span>
    - <span data-ttu-id="ecd89-227">Automatisches Beschriften von Dateien basierend auf Inhalten mithilfe der Standardbezeichnung, die für die Vertraulichkeitsbezeichnungsrichtlinie definiert ist</span><span class="sxs-lookup"><span data-stu-id="ecd89-227">Automatically labels files based on content, using the default label defined for the sensitivity labeling policy</span></span>
    - <span data-ttu-id="ecd89-228">Lässt *keine* Umetikettierung von Dateien zu</span><span class="sxs-lookup"><span data-stu-id="ecd89-228">Does *not* allow for relabeling files</span></span>
    - <span data-ttu-id="ecd89-229">Behält Dateidetails während der Überprüfung und automatischen Bezeichnung bei, einschließlich datumsbeändet, zuletzt geändert *und* *durch Werte* geändert</span><span class="sxs-lookup"><span data-stu-id="ecd89-229">Preserves file details while scanning and auto-labeling, including *date modified*, *last modified*, and *modified by* values</span></span>
    - <span data-ttu-id="ecd89-230">Legt fest, dass der Scanner MSG- und TMP-Dateien beim Ausführen ausschließt</span><span class="sxs-lookup"><span data-stu-id="ecd89-230">Sets the scanner to exclude .msg and .tmp files when running</span></span>
    - <span data-ttu-id="ecd89-231">Legt den Standardbesitzer auf das Konto fest, das Sie beim Ausführen des Scanners verwenden möchten</span><span class="sxs-lookup"><span data-stu-id="ecd89-231">Sets the default owner to the account you want to use when running the scanner</span></span>

1. <span data-ttu-id="ecd89-232">Verwenden Sie [das Cmdlet Add-AIPScannerRepository,](/powershell/module/azureinformationprotection/add-aipscannerrepository) um die Repositorys zu definieren, die Sie in Ihrem Inhaltsscanauftrag überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="ecd89-232">Use the [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) cmdlet to define the repositories you want to scan in your content scan job.</span></span> <span data-ttu-id="ecd89-233">Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="ecd89-233">For example, run:</span></span>

    ```powershell
    Add-AIPScannerRepository -OverrideContentScanJob Off -Path 'c:\repoToScan'
    ```
    
    <span data-ttu-id="ecd89-234">Verwenden Sie eine der folgenden Syntaxen, abhängig vom Typ des Repositorys, das Sie hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="ecd89-234">Use one of the following syntaxes, depending on the type of repository you're adding:</span></span>

    - <span data-ttu-id="ecd89-235">Verwenden Sie für eine Netzwerkfreigabe `\\Server\Folder` .</span><span class="sxs-lookup"><span data-stu-id="ecd89-235">For a network share, use `\\Server\Folder`.</span></span>
    - <span data-ttu-id="ecd89-236">Verwenden Sie für SharePoint Bibliothek `http://sharepoint.contoso.com/Shared%20Documents/Folder` .</span><span class="sxs-lookup"><span data-stu-id="ecd89-236">For a SharePoint library, use `http://sharepoint.contoso.com/Shared%20Documents/Folder`.</span></span>
    - <span data-ttu-id="ecd89-237">Für einen lokalen Pfad: `C:\Folder`</span><span class="sxs-lookup"><span data-stu-id="ecd89-237">For a local path: `C:\Folder`</span></span>
    - <span data-ttu-id="ecd89-238">Für einen UNC-Pfad: `\\Server\Folder`</span><span class="sxs-lookup"><span data-stu-id="ecd89-238">For a UNC path: `\\Server\Folder`</span></span>

    > [!NOTE]
    > <span data-ttu-id="ecd89-239">Platzhalter werden nicht unterstützt, und WebDav-Speicherorte werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ecd89-239">Wildcards are not supported and WebDav locations are not supported.</span></span>
    >
    > <span data-ttu-id="ecd89-240">Verwenden Sie stattdessen das [Cmdlet Set-AIPScannerRepository,](/powershell/module/azureinformationprotection/set-aipscannerrepository) um das Repository später zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ecd89-240">To modify the repository later on, use the [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) cmdlet instead.</span></span> 


<span data-ttu-id="ecd89-241">Fahren Sie bei Bedarf mit den folgenden Schritten fort:</span><span class="sxs-lookup"><span data-stu-id="ecd89-241">Continue with the following steps as needed:</span></span>

- [<span data-ttu-id="ecd89-242">Ausführen eines Suchzyklus und Anzeigen von Berichten für den Scanner</span><span class="sxs-lookup"><span data-stu-id="ecd89-242">Run a discovery cycle and view reports for the scanner</span></span>](/azure/information-protection/deploy-aip-scanner-manage#run-a-discovery-cycle-and-view-reports-for-the-scanner)
- [<span data-ttu-id="ecd89-243">Verwenden von PowerShell zum Konfigurieren des Scanners für die Anwendung von Klassifizierung und Schutz</span><span class="sxs-lookup"><span data-stu-id="ecd89-243">Use PowerShell to configure the scanner to apply classification and protection</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-the-scanner-to-apply-classification-and-protection)
- [<span data-ttu-id="ecd89-244">Konfigurieren einer DLP-Richtlinie mit dem Scanner mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="ecd89-244">Use PowerShell to configure a DLP policy with the scanner</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-a-dlp-policy-with-the-scanner)

<span data-ttu-id="ecd89-245">In der folgenden Tabelle sind powerShell-Cmdlets aufgeführt, die für die Installation des Scanners und die Verwaltung Ihrer Inhaltsscanaufträge relevant sind:</span><span class="sxs-lookup"><span data-stu-id="ecd89-245">The following table lists PowerShell cmdlets that are relevant for installing the scanner and managing your content scan jobs:</span></span>

| <span data-ttu-id="ecd89-246">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="ecd89-246">Cmdlet</span></span> | <span data-ttu-id="ecd89-247">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ecd89-247">Description</span></span> |
|--|--|
| [<span data-ttu-id="ecd89-248">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="ecd89-248">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="ecd89-249">Fügt Ihrem Inhaltsscanauftrag ein neues Repository hinzu.</span><span class="sxs-lookup"><span data-stu-id="ecd89-249">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="ecd89-250">Get-AIPScannerConfiguration</span><span class="sxs-lookup"><span data-stu-id="ecd89-250">Get-AIPScannerConfiguration</span></span>](/powershell/module/azureinformationprotection/get-aipscannerconfiguration)|<span data-ttu-id="ecd89-251">Gibt Details zu Ihrem Cluster zurück.</span><span class="sxs-lookup"><span data-stu-id="ecd89-251">Returns details about your cluster.</span></span> |
| [<span data-ttu-id="ecd89-252">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="ecd89-252">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="ecd89-253">Ruft Details zu Ihrem Inhaltsscanauftrag ab.</span><span class="sxs-lookup"><span data-stu-id="ecd89-253">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="ecd89-254">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="ecd89-254">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="ecd89-255">Ruft Details zu Repositorys ab, die für Ihren Inhaltsscanauftrag definiert sind.</span><span class="sxs-lookup"><span data-stu-id="ecd89-255">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="ecd89-256">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="ecd89-256">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="ecd89-257">Löscht den Auftrag zum Überprüfen von Inhalten.</span><span class="sxs-lookup"><span data-stu-id="ecd89-257">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="ecd89-258">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="ecd89-258">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="ecd89-259">Entfernt ein Repository aus Ihrem Inhaltsscanauftrag.</span><span class="sxs-lookup"><span data-stu-id="ecd89-259">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="ecd89-260">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="ecd89-260">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="ecd89-261">Definiert Einstellungen für Ihren Inhaltsscanauftrag.</span><span class="sxs-lookup"><span data-stu-id="ecd89-261">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="ecd89-262">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="ecd89-262">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="ecd89-263">Definiert Einstellungen für ein vorhandenes Repository in Ihrem Inhaltsscanauftrag.</span><span class="sxs-lookup"><span data-stu-id="ecd89-263">Defines settings for an existing repository in your content scan job.</span></span> |
| | |

<span data-ttu-id="ecd89-264">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="ecd89-264">For more information, see:</span></span>

- [<span data-ttu-id="ecd89-265">Was ist der Einheitliche Bezeichnungsscanner für Azure Information Protection?</span><span class="sxs-lookup"><span data-stu-id="ecd89-265">What is the Azure Information Protection unified labeling scanner?</span></span>](/azure/information-protection/deploy-aip-scanner)
- [<span data-ttu-id="ecd89-266">Konfigurieren und Installieren des Azure Information Protection (AIP)-Scanners für einheitliche Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="ecd89-266">Configuring and installing the Azure Information Protection (AIP) unified labeling scanner</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=powershell-only)
- <span data-ttu-id="ecd89-267">[Verwalten Sie Ihre Inhaltsscanaufträge nur mit PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)</span><span class="sxs-lookup"><span data-stu-id="ecd89-267">[Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>
