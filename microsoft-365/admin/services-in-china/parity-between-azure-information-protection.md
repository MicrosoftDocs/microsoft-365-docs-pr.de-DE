---
title: Parität zwischen Azure Information Protection für Office 365 betrieben von 21Vianet und kommerziellen angeboten
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
description: Erfahren Sie mehr über Azure Information Protection für Office 365 betrieben von 21Vianet und wie diese für Kunden in China konfiguriert werden.
monikerRange: o365-21vianet
ms.openlocfilehash: ad3420483701c83ffef65994996047de56a7085c
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644663"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="fdf0b-103">Parität zwischen Azure Information Protection für Office 365 betrieben von 21Vianet und kommerziellen angeboten</span><span class="sxs-lookup"><span data-stu-id="fdf0b-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="fdf0b-104">Unser Ziel ist es, Kunden in China alle kommerziellen Features und Funktionen mit unserem Azure Information Protection für Office 365 zu liefern, die von 21Vianet angeboten betrieben werden, es gibt jedoch einige fehlende Funktionen, die wir hervorheben möchten.</span><span class="sxs-lookup"><span data-stu-id="fdf0b-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection for Office 365 operated by 21Vianet offer, there is some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="fdf0b-105">Die folgende Liste enthält die vorhandenen Lücken zwischen Azure Information Protection für Office 365 betrieben von 21Vianet und unseren kommerziellen Angeboten ab Juli 2019:</span><span class="sxs-lookup"><span data-stu-id="fdf0b-105">The following list includes the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of July 2019:</span></span>

- <span data-ttu-id="fdf0b-106">Die Verwaltung von Informationsrechten (Information Rights Management, IRM) wird nur für Microsoft 365-Apps für Unternehmen (Build 11731,10000 oder höher) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fdf0b-106">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="fdf0b-107">Office 2010, Office 2013 und andere Office 2016 Versionen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fdf0b-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="fdf0b-108">Die Migration von Active Directory Rights Management Services (AD RMS) zu Azure Information Protection ist derzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fdf0b-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="fdf0b-109">Die Freigabe geschützter e-Mails an Benutzer in der kommerziellen Cloud wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fdf0b-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="fdf0b-110">Die Freigabe von Dokumenten und e-Mail-Anlagen für Benutzer in der kommerziellen Cloud ist derzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fdf0b-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="fdf0b-111">Dazu gehören Office 365, die von 21Vianet-Benutzern in der kommerziellen Cloud betrieben werden, nicht Office 365, die von 21Vianet-Benutzern in der kommerziellen Cloud betrieben werden, und Benutzer mit einer RMS for Individuals-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="fdf0b-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="fdf0b-112">IRM mit SharePoint (IRM-geschützte Websites und Bibliotheken) ist derzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fdf0b-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="fdf0b-113">Der Rights Management-Connector ist derzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fdf0b-113">The Rights Management Connector is currently not available.</span></span>
  
- <span data-ttu-id="fdf0b-114">Die Erweiterung für mobile Geräte für AD RMS ist derzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fdf0b-114">The Mobile Device Extension for AD RMS is currently not available.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="fdf0b-115">Konfigurieren von Azure Information Protection für Kunden in China</span><span class="sxs-lookup"><span data-stu-id="fdf0b-115">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="fdf0b-116">Aktivieren der Rechteverwaltung für den Mandanten</span><span class="sxs-lookup"><span data-stu-id="fdf0b-116">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="fdf0b-117">Damit die Verschlüsselung ordnungsgemäß funktioniert, muss der RMS-Dienst für den Mandanten aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="fdf0b-117">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="fdf0b-118">Überprüfen, ob der RMS aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="fdf0b-118">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="fdf0b-119">Starten Sie PowerShell als Administrator.</span><span class="sxs-lookup"><span data-stu-id="fdf0b-119">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="fdf0b-120">Wenn das AIPService-Modul nicht installiert ist, führen Sie aus `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="fdf0b-120">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="fdf0b-121">Importieren Sie das Modul mithilfe von `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="fdf0b-121">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="fdf0b-122">Stellen Sie eine Verbindung mit dem Dienst mithilfe von her `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="fdf0b-122">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="fdf0b-123">Führen `(Get-AipServiceConfiguration).FunctionalState` Sie aus, und überprüfen Sie, ob der Status lautet `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="fdf0b-123">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="fdf0b-124">Wenn der Funktionszustand lautet `Disabled` , führen Sie aus `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="fdf0b-124">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="fdf0b-125">DNS-Konfiguration für die Verschlüsselung (Windows)</span><span class="sxs-lookup"><span data-stu-id="fdf0b-125">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="fdf0b-126">Damit die Verschlüsselung ordnungsgemäß funktioniert, müssen Office-Clientanwendungen eine Verbindung mit der China-Instanz des Diensts und dem Bootstrap von dort herstellen.</span><span class="sxs-lookup"><span data-stu-id="fdf0b-126">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="fdf0b-127">Um Clientanwendungen an die richtige Dienstinstanz umzuleiten, muss der mandantenadministrator einen DNS-SRV-Eintrag mit Informationen zur Azure RMS-URL konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="fdf0b-127">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="fdf0b-128">Ohne den DNS-SRV-Eintrag versucht die Clientanwendung standardmäßig eine Verbindung mit der öffentlichen Cloud-Instanz herzustellen, und es tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="fdf0b-128">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="fdf0b-129">Darüber hinaus wird davon ausgegangen, dass sich Benutzer mit einem Benutzernamen anmelden, der auf der Mandantendomäne basiert (beispielsweise `joe@contoso.cn` ) und nicht dem `onmschina` Benutzernamen (beispielsweise `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="fdf0b-129">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="fdf0b-130">Der Domänenname aus dem Benutzernamen wird für die DNS-Umleitung zur korrekten Dienstinstanz verwendet.</span><span class="sxs-lookup"><span data-stu-id="fdf0b-130">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="fdf0b-131">Abrufen der RMS-ID:</span><span class="sxs-lookup"><span data-stu-id="fdf0b-131">Get the RMS ID:</span></span>
  1. <span data-ttu-id="fdf0b-132">Starten Sie PowerShell als Administrator.</span><span class="sxs-lookup"><span data-stu-id="fdf0b-132">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="fdf0b-133">Wenn das AIPService-Modul nicht installiert ist, führen Sie aus `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="fdf0b-133">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="fdf0b-134">Stellen Sie eine Verbindung mit dem Dienst mithilfe von her `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="fdf0b-134">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="fdf0b-135">Ausführen `(Get-AipServiceConfiguration).RightsManagementServiceId` , um die RMS-ID abzurufen.</span><span class="sxs-lookup"><span data-stu-id="fdf0b-135">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="fdf0b-136">Melden Sie sich bei Ihrem DNS-Anbieter an, navigieren Sie zu den DNS-Einstellungen für die Domäne, und fügen Sie dann einen neuen SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="fdf0b-136">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="fdf0b-137">Dienst = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="fdf0b-137">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="fdf0b-138">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="fdf0b-138">Protocol = `_http`</span></span>
  - <span data-ttu-id="fdf0b-139">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="fdf0b-139">Name = `_tcp`</span></span>
  - <span data-ttu-id="fdf0b-140">Target = `[GUID].rms.aadrm.cn` (wobei GUID die RMS-ID ist)</span><span class="sxs-lookup"><span data-stu-id="fdf0b-140">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="fdf0b-141">Priorität, Gewichtung, Sekunden, TTL = Standardwerte</span><span class="sxs-lookup"><span data-stu-id="fdf0b-141">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="fdf0b-142">Ordnen Sie die benutzerdefinierte Domäne dem Mandanten im [Azure-Portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)zu.</span><span class="sxs-lookup"><span data-stu-id="fdf0b-142">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="fdf0b-143">Dadurch wird ein Eintrag in DNS hinzugefügt, der nach dem Hinzufügen des Werts zu den DNS-Einstellungen einige Minuten in Anspruch nehmen kann, um überprüft zu werden.</span><span class="sxs-lookup"><span data-stu-id="fdf0b-143">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="fdf0b-144">Melden Sie sich beim Microsoft 365 Admin Center mit den entsprechenden globalen Administratoranmeldeinformationen an, und fügen Sie die Domäne (zum Beispiel `contoso.cn` ) für die Benutzererstellung hinzu.</span><span class="sxs-lookup"><span data-stu-id="fdf0b-144">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="fdf0b-145">Im Verifizierungsprozess sind möglicherweise zusätzliche DNS-Änderungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fdf0b-145">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="fdf0b-146">Sobald die Überprüfung erfolgt ist, können Benutzer erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="fdf0b-146">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="fdf0b-147">DNS-Konfiguration für die Verschlüsselung (Mac, Ios, Android)</span><span class="sxs-lookup"><span data-stu-id="fdf0b-147">DNS configuration for encryption (Mac, iOS, Android)</span></span>

- <span data-ttu-id="fdf0b-148">Melden Sie sich bei Ihrem DNS-Anbieter an, navigieren Sie zu den DNS-Einstellungen für die Domäne, und fügen Sie dann einen neuen SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="fdf0b-148">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="fdf0b-149">Dienst = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="fdf0b-149">Service = `_rmsdisco`</span></span>
  - <span data-ttu-id="fdf0b-150">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="fdf0b-150">Protocol = `_http`</span></span>
  - <span data-ttu-id="fdf0b-151">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="fdf0b-151">Name = `_tcp`</span></span>
  - <span data-ttu-id="fdf0b-152">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="fdf0b-152">Target = `api.aadrm.cn`</span></span>
  - <span data-ttu-id="fdf0b-153">Port = `80`</span><span class="sxs-lookup"><span data-stu-id="fdf0b-153">Port = `80`</span></span>
  - <span data-ttu-id="fdf0b-154">Priorität, Gewichtung, Sekunden, TTL = Standardwerte</span><span class="sxs-lookup"><span data-stu-id="fdf0b-154">Priority, Weight, Seconds, TTL = default values</span></span>
