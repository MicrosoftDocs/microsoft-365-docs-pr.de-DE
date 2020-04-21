---
title: Office 365, betrieben von 21Vianet
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: mnirkhe
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- MET150
- GEU150
- GEA150
description: Erfahren Sie mehr über Azure Information Protection für Office 365 betrieben von 21Vianet und wie diese für Kunden in China konfiguriert werden.
monikerRange: o365-21vianet
ms.openlocfilehash: 3d24b450cc9ba9a6427732d408e35af1394b4a34
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627654"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="485a9-103">Parität zwischen Azure Information Protection für Office 365 betrieben von 21Vianet und kommerziellen angeboten</span><span class="sxs-lookup"><span data-stu-id="485a9-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="485a9-104">Unser Ziel ist es, Kunden in China alle kommerziellen Features und Funktionen mit unserem Azure Information Protection für Office 365 zu liefern, die von 21Vianet angeboten betrieben werden, es gibt jedoch einige fehlende Funktionen, die wir hervorheben möchten.</span><span class="sxs-lookup"><span data-stu-id="485a9-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection for Office 365 operated by 21Vianet offer, there is some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="485a9-105">Hierbei handelt es sich um die vorhandenen Lücken zwischen Azure Information Protection für Office 365, die von 21Vianet betrieben werden, und unseren kommerziellen Angeboten ab Juli 2019:</span><span class="sxs-lookup"><span data-stu-id="485a9-105">These are the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of July 2019:</span></span>

- <span data-ttu-id="485a9-106">Die Verwaltung von Informationsrechten (Information Rights Management, IRM) wird nur für Microsoft 365-Apps für Unternehmen (Build 11731,10000 oder höher) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="485a9-106">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="485a9-107">Office 2010, Office 2013 und andere Office 2016 Versionen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="485a9-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="485a9-108">Die Migration von Active Directory Rights Management Services (AD RMS) zu Azure Information Protection ist derzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="485a9-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="485a9-109">Die Freigabe geschützter e-Mails an Benutzer in der kommerziellen Cloud wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="485a9-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="485a9-110">Die Freigabe von Dokumenten und e-Mail-Anlagen für Benutzer in der kommerziellen Cloud ist derzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="485a9-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="485a9-111">Dazu gehören Office 365, die von 21Vianet-Benutzern in der kommerziellen Cloud betrieben werden, nicht Office 365, die von 21Vianet-Benutzern in der kommerziellen Cloud betrieben werden, und Benutzer mit einer RMS for Individuals-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="485a9-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="485a9-112">IRM mit SharePoint (IRM-geschützte Websites und Bibliotheken) ist derzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="485a9-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="485a9-113">Der Rights Management-Connector ist derzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="485a9-113">The Rights Management Connector is currently not available.</span></span>
  
- <span data-ttu-id="485a9-114">Die Erweiterung für mobile Geräte für AD RMS ist derzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="485a9-114">The Mobile Device Extension for AD RMS is currently not available.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="485a9-115">Konfigurieren von Azure Information Protection für Kunden in China</span><span class="sxs-lookup"><span data-stu-id="485a9-115">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="485a9-116">Aktivieren der Rechteverwaltung für den Mandanten</span><span class="sxs-lookup"><span data-stu-id="485a9-116">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="485a9-117">Damit die Verschlüsselung ordnungsgemäß funktioniert, muss der RMS-Dienst für den Mandanten aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="485a9-117">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="485a9-118">Überprüfen, ob der RMS aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="485a9-118">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="485a9-119">Starten Sie PowerShell als Administrator.</span><span class="sxs-lookup"><span data-stu-id="485a9-119">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="485a9-120">Wenn das AIPService-Modul nicht installiert ist, `Install-Module AipService`führen Sie aus.</span><span class="sxs-lookup"><span data-stu-id="485a9-120">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="485a9-121">Importieren Sie das Modul `Import-Module AipService`mithilfe von.</span><span class="sxs-lookup"><span data-stu-id="485a9-121">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="485a9-122">Stellen Sie eine Verbindung mit `Connect-AipService -environmentname azurechinacloud`dem Dienst mithilfe von her.</span><span class="sxs-lookup"><span data-stu-id="485a9-122">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="485a9-123">Führen `(Get-AipServiceConfiguration).FunctionalState` Sie aus, und überprüfen `Enabled`Sie, ob der Status lautet.</span><span class="sxs-lookup"><span data-stu-id="485a9-123">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="485a9-124">Wenn der Funktionszustand lautet `Disabled`, führen `Enable-AipService`Sie aus.</span><span class="sxs-lookup"><span data-stu-id="485a9-124">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="485a9-125">DNS-Konfiguration für die Verschlüsselung (Windows)</span><span class="sxs-lookup"><span data-stu-id="485a9-125">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="485a9-126">Damit die Verschlüsselung ordnungsgemäß funktioniert, müssen Office-Clientanwendungen eine Verbindung mit der China-Instanz des Diensts und dem Bootstrap von dort herstellen.</span><span class="sxs-lookup"><span data-stu-id="485a9-126">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="485a9-127">Um Clientanwendungen an die richtige Dienstinstanz umzuleiten, muss der mandantenadministrator einen DNS-SRV-Eintrag mit Informationen zur Azure RMS-URL konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="485a9-127">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="485a9-128">Ohne den DNS-SRV-Eintrag versucht die Clientanwendung standardmäßig eine Verbindung mit der öffentlichen Cloud-Instanz herzustellen, und es tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="485a9-128">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="485a9-129">Darüber hinaus wird davon ausgegangen, dass sich Benutzer mit einem Benutzernamen anmelden, der auf der Mandantendomäne basiert `joe@contoso.cn`(beispielsweise) und `onmschina` nicht dem Benutzernamen ( `joe@contoso.onmschina.cn`beispielsweise).</span><span class="sxs-lookup"><span data-stu-id="485a9-129">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="485a9-130">Der Domänenname aus dem Benutzernamen wird für die DNS-Umleitung zur korrekten Dienstinstanz verwendet.</span><span class="sxs-lookup"><span data-stu-id="485a9-130">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="485a9-131">Abrufen der RMS-ID:</span><span class="sxs-lookup"><span data-stu-id="485a9-131">Get the RMS ID:</span></span>
  1. <span data-ttu-id="485a9-132">Starten Sie PowerShell als Administrator.</span><span class="sxs-lookup"><span data-stu-id="485a9-132">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="485a9-133">Wenn das AIPService-Modul nicht installiert ist, `Install-Module AipService`führen Sie aus.</span><span class="sxs-lookup"><span data-stu-id="485a9-133">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="485a9-134">Stellen Sie eine Verbindung mit `Connect-AipService -environmentname azurechinacloud`dem Dienst mithilfe von her.</span><span class="sxs-lookup"><span data-stu-id="485a9-134">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="485a9-135">Ausführen `(Get-AipServiceConfiguration).RightsManagementServiceId` , um die RMS-ID abzurufen.</span><span class="sxs-lookup"><span data-stu-id="485a9-135">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="485a9-136">Melden Sie sich bei Ihrem DNS-Anbieter an, navigieren Sie zu den DNS-Einstellungen für die Domäne, und fügen Sie dann einen neuen SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="485a9-136">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="485a9-137">Dienst = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="485a9-137">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="485a9-138">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="485a9-138">Protocol = `_http`</span></span>
  - <span data-ttu-id="485a9-139">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="485a9-139">Name = `_tcp`</span></span>
  - <span data-ttu-id="485a9-140">Target = `[GUID].rms.aadrm.cn` (wobei GUID die RMS-ID ist)</span><span class="sxs-lookup"><span data-stu-id="485a9-140">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="485a9-141">Priorität, Gewichtung, Sekunden, TTL = Standardwerte</span><span class="sxs-lookup"><span data-stu-id="485a9-141">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="485a9-142">Ordnen Sie die benutzerdefinierte Domäne dem Mandanten im [Azure-Portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)zu.</span><span class="sxs-lookup"><span data-stu-id="485a9-142">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="485a9-143">Dadurch wird ein Eintrag in DNS hinzugefügt, der nach dem Hinzufügen des Werts zu den DNS-Einstellungen einige Minuten in Anspruch nehmen kann, um überprüft zu werden.</span><span class="sxs-lookup"><span data-stu-id="485a9-143">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="485a9-144">Melden Sie sich beim Microsoft 365 Admin Center mit den entsprechenden globalen Administratoranmeldeinformationen an, und fügen Sie die Domäne `contoso.cn`(zum Beispiel) für die Benutzererstellung hinzu.</span><span class="sxs-lookup"><span data-stu-id="485a9-144">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="485a9-145">Im Verifizierungsprozess sind möglicherweise zusätzliche DNS-Änderungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="485a9-145">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="485a9-146">Sobald die Überprüfung erfolgt ist, können Benutzer erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="485a9-146">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="485a9-147">DNS-Konfiguration für die Verschlüsselung (Mac, Ios, Android)</span><span class="sxs-lookup"><span data-stu-id="485a9-147">DNS configuration for encryption (Mac, iOS, Android)</span></span>

- <span data-ttu-id="485a9-148">Melden Sie sich bei Ihrem DNS-Anbieter an, navigieren Sie zu den DNS-Einstellungen für die Domäne, und fügen Sie dann einen neuen SRV-Eintrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="485a9-148">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="485a9-149">Dienst = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="485a9-149">Service = `_rmsdisco`</span></span>
  - <span data-ttu-id="485a9-150">Protocol = `_http`</span><span class="sxs-lookup"><span data-stu-id="485a9-150">Protocol = `_http`</span></span>
  - <span data-ttu-id="485a9-151">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="485a9-151">Name = `_tcp`</span></span>
  - <span data-ttu-id="485a9-152">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="485a9-152">Target = `api.aadrm.cn`</span></span>
  - <span data-ttu-id="485a9-153">Port = `80`</span><span class="sxs-lookup"><span data-stu-id="485a9-153">Port = `80`</span></span>
  - <span data-ttu-id="485a9-154">Priorität, Gewichtung, Sekunden, TTL = Standardwerte</span><span class="sxs-lookup"><span data-stu-id="485a9-154">Priority, Weight, Seconds, TTL = default values</span></span>
