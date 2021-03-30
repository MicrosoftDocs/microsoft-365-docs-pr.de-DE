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
ms.openlocfilehash: bddba69ecc8b7b80d2b2c7c48d820ec22d293362
ms.sourcegitcommit: b56a8ff9bb496bf2bc1991000afca3d251f45b72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51418032"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="10160-103">Azure Information Protection-Unterstützung für Office 365 betrieben von 21Vianet</span><span class="sxs-lookup"><span data-stu-id="10160-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="10160-104">In diesem Artikel werden die Unterschiede zwischen der Azure Information Protection (AIP)-Unterstützung für Office 365, betrieben von 21Vianet und kommerziellen Angeboten, sowie spezifische Anweisungen zum Konfigurieren von AIP für Kunden in China behandelt, einschließlich der Installation des lokalen AIP-Scanners und verwalten von Aufträgen zur &mdash; Inhaltsscan.</span><span class="sxs-lookup"><span data-stu-id="10160-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="10160-105">Unterschiede zwischen AIP für Office 365, betrieben von 21Vianet und kommerziellen Angeboten</span><span class="sxs-lookup"><span data-stu-id="10160-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="10160-106">Unser Ziel ist es zwar, kunden in China alle kommerziellen Features und Funktionen mit unserem AIP für Office 365, betrieben von 21Vianet, bereitzustellen, es fehlen jedoch einige Funktionen, die wir hervorheben möchten.</span><span class="sxs-lookup"><span data-stu-id="10160-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="10160-107">Die folgende Liste enthält die bestehenden Lücken zwischen AIP für Office 365, betrieben von 21Vianet und unseren kommerziellen Angeboten ab Januar 2021:</span><span class="sxs-lookup"><span data-stu-id="10160-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="10160-108">Verwaltung von Informationsrechten (Information Rights Management, IRM) wird nur für Microsoft 365 Apps for Enterprise (Build 11731.10000 oder höher) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="10160-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="10160-109">Office 2010, Office 2013 und andere Office 2016-Versionen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="10160-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="10160-110">Die Migration von Active Directory-Rechteverwaltungsdienste (AD RMS) zu AIP ist derzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="10160-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="10160-111">Die Freigabe geschützter E-Mails für Benutzer in der kommerziellen Cloud wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="10160-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="10160-112">Die Freigabe von Dokumenten und E-Mail-Anlagen für Benutzer in der kommerziellen Cloud ist derzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="10160-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="10160-113">Dazu gehören Office 365, betrieben von 21Vianet-Benutzern in der kommerziellen Cloud, nicht von Office 365 betrieben von 21Vianet-Benutzern in der kommerziellen Cloud und Benutzer mit einer RMS for Individuals-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="10160-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="10160-114">IRM mit SharePoint (IRM-geschützte Websites und Bibliotheken) ist derzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="10160-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="10160-115">Die Mobile Device Extension für AD RMS ist derzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="10160-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="10160-116">Der [mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) wird von Azure China 21Vianet nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="10160-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

- <span data-ttu-id="10160-117">Der AIP-Bereich des Azure-Portals ist für Kunden in China nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="10160-117">The AIP area of the Azure portal is unavailable to customers in China.</span></span> <span data-ttu-id="10160-118">Verwenden [Sie PowerShell-Befehle,](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) anstatt Aktionen im Portal auszuführen, z. B. das Installieren des lokalen Scanners und die Verwaltung Ihrer Inhaltsscanaufträge.</span><span class="sxs-lookup"><span data-stu-id="10160-118">Use [PowerShell commands](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) instead of performing actions in the portal, such as installing the on-premises scanner and managing your content scan jobs.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="10160-119">Konfigurieren von AIP für Kunden in China</span><span class="sxs-lookup"><span data-stu-id="10160-119">Configure AIP for customers in China</span></span>

<span data-ttu-id="10160-120">So konfigurieren Sie AIP für Kunden in China:</span><span class="sxs-lookup"><span data-stu-id="10160-120">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="10160-121">[Aktivieren der Rechteverwaltung für den Mandanten](#step-1-enable-rights-management-for-the-tenant).</span><span class="sxs-lookup"><span data-stu-id="10160-121">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

2. <span data-ttu-id="10160-122">[Konfigurieren der DNS-Verschlüsselung](#step-2-configure-dns-encryption).</span><span class="sxs-lookup"><span data-stu-id="10160-122">[Configure DNS encryption](#step-2-configure-dns-encryption).</span></span>

3. <span data-ttu-id="10160-123">[Installieren und Konfigurieren des AIP Unified Labeling-Clients](#step-3-install-and-configure-the-aip-unified-labeling-client).</span><span class="sxs-lookup"><span data-stu-id="10160-123">[Install and configure the AIP unified labeling client](#step-3-install-and-configure-the-aip-unified-labeling-client).</span></span>

4. <span data-ttu-id="10160-124">[Konfigurieren von AIP-Apps unter Windows](#step-4-configure-aip-apps-on-windows).</span><span class="sxs-lookup"><span data-stu-id="10160-124">[Configure AIP apps on Windows](#step-4-configure-aip-apps-on-windows).</span></span>

5. <span data-ttu-id="10160-125">[Installieren Sie den lokalen AIP-Scanner, und verwalten Sie Inhaltsscanaufträge.](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)</span><span class="sxs-lookup"><span data-stu-id="10160-125">[Install the AIP on-premises scanner and manage content scan jobs](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="10160-126">Schritt 1: Aktivieren der Rechteverwaltung für den Mandanten</span><span class="sxs-lookup"><span data-stu-id="10160-126">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="10160-127">Damit die Verschlüsselung ordnungsgemäß funktioniert, muss RMS für den Mandanten aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="10160-127">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="10160-128">Überprüfen Sie, ob RMS aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="10160-128">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="10160-129">Starten Sie PowerShell als Administrator.</span><span class="sxs-lookup"><span data-stu-id="10160-129">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="10160-130">Wenn das AIPService-Modul nicht installiert ist, führen Sie `Install-Module AipService` aus.</span><span class="sxs-lookup"><span data-stu-id="10160-130">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="10160-131">Importieren Sie das Modul mithilfe `Import-Module AipService` von .</span><span class="sxs-lookup"><span data-stu-id="10160-131">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="10160-132">Stellen Sie eine Verbindung mit dem Dienst mithilfe von `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="10160-132">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="10160-133">Führen `(Get-AipServiceConfiguration).FunctionalState` Sie aus, und überprüfen Sie, ob der Status `Enabled` ist.</span><span class="sxs-lookup"><span data-stu-id="10160-133">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="10160-134">Wenn der Funktionszustand `Disabled` ist, führen Sie `Enable-AipService` aus.</span><span class="sxs-lookup"><span data-stu-id="10160-134">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-configure-dns-encryption"></a><span data-ttu-id="10160-135">Schritt 2: Konfigurieren der DNS-Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="10160-135">Step 2: Configure DNS encryption</span></span>

<span data-ttu-id="10160-136">Damit die Verschlüsselung ordnungsgemäß funktioniert, müssen Office-Clientanwendungen eine Verbindung mit der China-Instanz des Diensts herstellen und bootstrap von dort aus erstellen.</span><span class="sxs-lookup"><span data-stu-id="10160-136">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="10160-137">Um Clientanwendungen an die richtige Dienstinstanz umzuleiten, muss der Mandantenadministrator einen DNS-SRV-Eintrag mit Informationen zur Azure RMS-URL konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="10160-137">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="10160-138">Ohne den DNS-SRV-Eintrag versucht die Clientanwendung standardmäßig, eine Verbindung mit der öffentlichen Cloudinstanz herzustellen, und es wird ein Fehler ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="10160-138">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="10160-139">Außerdem wird davon ausgegangen, dass sich Benutzer mit einem Benutzernamen anmelden, der auf der Domäne im Besitz des Mandanten basiert (z. B. ), und nicht mit dem Benutzernamen (z. B. `joe@contoso.cn` `onmschina` `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="10160-139">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="10160-140">Der Domänenname aus dem Benutzernamen wird für die DNS-Umleitung an die richtige Dienstinstanz verwendet.</span><span class="sxs-lookup"><span data-stu-id="10160-140">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="10160-141">Konfigurieren der DNS-Verschlüsselung – Windows</span><span class="sxs-lookup"><span data-stu-id="10160-141">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="10160-142">Hier erhalten Sie die RMS-ID:</span><span class="sxs-lookup"><span data-stu-id="10160-142">Get the RMS ID:</span></span>

    1. <span data-ttu-id="10160-143">Starten Sie PowerShell als Administrator.</span><span class="sxs-lookup"><span data-stu-id="10160-143">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="10160-144">Wenn das AIPService-Modul nicht installiert ist, führen Sie `Install-Module AipService` aus.</span><span class="sxs-lookup"><span data-stu-id="10160-144">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="10160-145">Stellen Sie eine Verbindung mit dem Dienst mithilfe von `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="10160-145">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="10160-146">Führen `(Get-AipServiceConfiguration).RightsManagementServiceId` Sie aus, um die RMS-ID zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="10160-146">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="10160-147">Melden Sie sich bei Ihrem DNS-Anbieter an, navigieren Sie zu den DNS-Einstellungen für die Domäne, und fügen Sie dann einen neuen SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="10160-147">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="10160-148">Dienst = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="10160-148">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="10160-149">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="10160-149">Protocol = `_http`</span></span>
    - <span data-ttu-id="10160-150">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="10160-150">Name = `_tcp`</span></span>
    - <span data-ttu-id="10160-151">Target = `[GUID].rms.aadrm.cn` (wobei GUID die RMS-ID ist)</span><span class="sxs-lookup"><span data-stu-id="10160-151">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="10160-152">Priorität, Gewichtung, Sekunden, TTL = Standardwerte</span><span class="sxs-lookup"><span data-stu-id="10160-152">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="10160-153">Ordnen Sie die benutzerdefinierte Domäne dem Mandanten im [Azure-Portal zu.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)</span><span class="sxs-lookup"><span data-stu-id="10160-153">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="10160-154">Dadurch wird ein Eintrag in DNS hinzugefügt, der einige Minuten dauern kann, um überprüft zu werden, nachdem Sie den Wert zu den DNS-Einstellungen hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="10160-154">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="10160-155">Melden Sie sich beim Microsoft 365 Admin Center mit den entsprechenden globalen Administratoranmeldeinformationen an, und fügen Sie die Domäne (z. B. ) zur `contoso.cn` Benutzererstellung hinzu.</span><span class="sxs-lookup"><span data-stu-id="10160-155">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="10160-156">Bei der Überprüfung sind möglicherweise zusätzliche DNS-Änderungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="10160-156">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="10160-157">Sobald die Überprüfung erfolgt ist, können Benutzer erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="10160-157">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="10160-158">Konfigurieren der DNS-Verschlüsselung – Mac, iOS, Android</span><span class="sxs-lookup"><span data-stu-id="10160-158">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="10160-159">Melden Sie sich bei Ihrem DNS-Anbieter an, navigieren Sie zu den DNS-Einstellungen für die Domäne, und fügen Sie dann einen neuen SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="10160-159">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="10160-160">Dienst = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="10160-160">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="10160-161">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="10160-161">Protocol = `_http`</span></span>
- <span data-ttu-id="10160-162">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="10160-162">Name = `_tcp`</span></span>
- <span data-ttu-id="10160-163">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="10160-163">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="10160-164">Port = `80`</span><span class="sxs-lookup"><span data-stu-id="10160-164">Port = `80`</span></span>
- <span data-ttu-id="10160-165">Priorität, Gewichtung, Sekunden, TTL = Standardwerte</span><span class="sxs-lookup"><span data-stu-id="10160-165">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="10160-166">Schritt 3: Installieren und Konfigurieren des AIP Unified Labeling-Clients</span><span class="sxs-lookup"><span data-stu-id="10160-166">Step 3: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="10160-167">Laden Sie den AIP Unified Labeling-Client aus dem [Microsoft Download Center herunter.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="10160-167">Download the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="10160-168">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="10160-168">For more information, see:</span></span>

- [<span data-ttu-id="10160-169">AIP-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="10160-169">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="10160-170">AIP-Versionsverlauf und Supportrichtlinie</span><span class="sxs-lookup"><span data-stu-id="10160-170">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="10160-171">AIP-Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="10160-171">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="10160-172">AIP-Schnellstart: Bereitstellen des AIP-Clients</span><span class="sxs-lookup"><span data-stu-id="10160-172">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="10160-173">AIP-Administratorhandbuch</span><span class="sxs-lookup"><span data-stu-id="10160-173">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="10160-174">AIP-Benutzerhandbuch</span><span class="sxs-lookup"><span data-stu-id="10160-174">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="10160-175">Informationen zu Microsoft 365-Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="10160-175">Learn about Microsoft 365 sensitivity labels</span></span>](../../compliance/sensitivity-labels.md)

### <a name="step-4-configure-aip-apps-on-windows"></a><span data-ttu-id="10160-176">Schritt 4: Konfigurieren von AIP-Apps unter Windows</span><span class="sxs-lookup"><span data-stu-id="10160-176">Step 4: Configure AIP apps on Windows</span></span>

<span data-ttu-id="10160-177">AIP-Apps unter Windows benötigen den folgenden Registrierungsschlüssel, um sie auf die richtige cloudbasierte Cloud für Azure China zu verweisen:</span><span class="sxs-lookup"><span data-stu-id="10160-177">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="10160-178">Registrierungsknoten = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="10160-178">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="10160-179">Name = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="10160-179">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="10160-180">Wert = `6` (Standard = 0)</span><span class="sxs-lookup"><span data-stu-id="10160-180">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="10160-181">Type = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="10160-181">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="10160-182">Stellen Sie sicher, dass Sie den Registrierungsschlüssel nach einer Deinstallation nicht löschen.</span><span class="sxs-lookup"><span data-stu-id="10160-182">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="10160-183">Wenn der Schlüssel leer, falsch oder nicht vorhanden ist, verhält sich die Funktionalität als Standardwert (Standardwert = 0 für die kommerzielle Cloud).</span><span class="sxs-lookup"><span data-stu-id="10160-183">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="10160-184">Wenn der Schlüssel leer oder falsch ist, wird dem Protokoll auch ein Druckfehler hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="10160-184">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="10160-185">Schritt 5: Installieren des lokalen AIP-Scanners und Verwalten von Inhaltsscanaufträgen</span><span class="sxs-lookup"><span data-stu-id="10160-185">Step 5: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="10160-186">Installieren Sie den lokalen AIP-Scanner, um Ihre Netzwerk- und Inhaltsfreigaben auf vertrauliche Daten zu überprüfen, und wenden Sie Klassifizierungs- und Schutzbezeichnungen an, wie in der Richtlinie Ihrer Organisation konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="10160-186">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

- <span data-ttu-id="10160-187">Beim Erstellen und Konfigurieren von Azure AD-Anwendungen für den Befehl  [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) zeigt der Bereich Api-Berechtigungen anfordern die **APIs** an, die meine Organisation verwendet, anstelle der **Registerkarte Microsoft-APIs.** Wählen Sie **die APIs aus,** die meine Organisation verwendet, um dann **Azure Rights Management Services auszuwählen.**</span><span class="sxs-lookup"><span data-stu-id="10160-187">When creating and configuring Azure AD applications for the [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) command, the **Request API permissions** pane shows the **APIs my organization uses** tab instead of the **Microsoft APIs** tab. Select the **APIs my organization uses** to then select **Azure Rights Management Services**.</span></span>

- <span data-ttu-id="10160-188">Verwenden Sie bei der Installation des Scanners und beim Verwalten Ihrer Inhaltsscanaufträge die folgenden Cmdlets anstelle der Azure-Portalschnittstelle, die von den kommerziellen Angeboten verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="10160-188">When installing the scanner and managing your content scan jobs, use the following cmdlets instead of the Azure portal interface that's used by the commercial offerings:</span></span><br><br>

    | <span data-ttu-id="10160-189">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="10160-189">Cmdlet</span></span> | <span data-ttu-id="10160-190">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="10160-190">Description</span></span> |
    |--|--|
    | [<span data-ttu-id="10160-191">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="10160-191">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="10160-192">Fügt Ihrem Inhaltsscanauftrag ein neues Repository hinzu.</span><span class="sxs-lookup"><span data-stu-id="10160-192">Adds a new repository to your content scan job.</span></span> |
    | [<span data-ttu-id="10160-193">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="10160-193">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="10160-194">Ruft Details zu Ihrem Inhaltsscanauftrag ab.</span><span class="sxs-lookup"><span data-stu-id="10160-194">Gets details about your content scan job.</span></span> |
    | [<span data-ttu-id="10160-195">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="10160-195">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="10160-196">Ruft Details zu Repositorys ab, die für Ihren Inhaltsscanauftrag definiert sind.</span><span class="sxs-lookup"><span data-stu-id="10160-196">Gets details about repositories defined for your content scan job.</span></span> |
    | [<span data-ttu-id="10160-197">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="10160-197">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="10160-198">Löscht den Auftrag zum Überprüfen von Inhalten.</span><span class="sxs-lookup"><span data-stu-id="10160-198">Deletes your content scan job.</span></span> |
    | [<span data-ttu-id="10160-199">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="10160-199">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="10160-200">Entfernt ein Repository aus Ihrem Inhaltsscanauftrag.</span><span class="sxs-lookup"><span data-stu-id="10160-200">Removes a repository from your content scan job.</span></span> |
    | [<span data-ttu-id="10160-201">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="10160-201">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="10160-202">Definiert Einstellungen für Ihren Inhaltsscanauftrag.</span><span class="sxs-lookup"><span data-stu-id="10160-202">Defines settings for your content scan job.</span></span> |
    | [<span data-ttu-id="10160-203">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="10160-203">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="10160-204">Definiert Einstellungen für ein vorhandenes Repository in Ihrem Inhaltsscanauftrag.</span><span class="sxs-lookup"><span data-stu-id="10160-204">Defines settings for an existing repository in your content scan job.</span></span> |
    | | |

> [!TIP]
> <span data-ttu-id="10160-205">Verwenden [Sie bei der Installation](/azure/information-protection/deploy-aip-scanner-configure-install#install-the-scanner)des Scanners denselben Clusternamen im Befehl [Install-AIPScanner,](/powershell/module/azureinformationprotection/install-aipscanner) um mehrere Scannerknoten demselben Cluster zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="10160-205">When [installing the scanner](/azure/information-protection/deploy-aip-scanner-configure-install#install-the-scanner), use the same cluster name in the [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) command to associate multiple scanner nodes to the same cluster.</span></span> <span data-ttu-id="10160-206">Wenn Sie denselben Cluster für mehrere Scannerknoten verwenden, können mehrere Scanner zusammenarbeiten, um Ihre Scans durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="10160-206">Using the same cluster for multiple scanner nodes enables multiple scanners to work together to perform your scans.</span></span>
> 
> <span data-ttu-id="10160-207">Verwenden Sie [das Cmdlet Get-AIPScannerConfiguration,](/powershell/module/azureinformationprotection/get-aipscannerconfiguration) um Details zu Ihrem Cluster zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="10160-207">Use the [Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/get-aipscannerconfiguration) cmdlet to return details about your cluster.</span></span>
> 
<span data-ttu-id="10160-208">Weitere Informationen finden Sie unter [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) und Manage your content scan jobs using [PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span><span class="sxs-lookup"><span data-stu-id="10160-208">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>