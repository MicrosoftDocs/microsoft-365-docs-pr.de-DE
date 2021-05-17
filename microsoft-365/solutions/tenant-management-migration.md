---
title: 'Schritt 4: Migration für Ihre Microsoft 365 für Enterprise-Mandanten'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Migrieren Sie Windows Geräte, Office Client-Apps und Office Server für Microsoft 365 Mandanten.
ms.openlocfilehash: 336dee2e62c6d0917c437252ba1d741c304998fa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929144"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="95ba9-104">Schritt 4.</span><span class="sxs-lookup"><span data-stu-id="95ba9-104">Step 4.</span></span> <span data-ttu-id="95ba9-105">Migration für Ihre Microsoft 365 für Enterprise-Mandanten</span><span class="sxs-lookup"><span data-stu-id="95ba9-105">Migration for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="95ba9-106">Die meisten Unternehmensorganisationen verfügen über eine heterogene Umgebung, die mehrere Versionen von Betriebssystemen, Clientsoftware und Serversoftware umfasst.</span><span class="sxs-lookup"><span data-stu-id="95ba9-106">Most enterprise organizations have a heterogeneous environment that includes multiple releases of operating systems, client software, and server software.</span></span> <span data-ttu-id="95ba9-107">Microsoft 365 für Unternehmen umfasst die sichersten Versionen der wichtigsten Komponenten Ihrer IT-Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="95ba9-107">Microsoft 365 for enterprise includes the most secure versions of the key components of your IT infrastructure.</span></span> <span data-ttu-id="95ba9-108">Es enthält auch Produktivitätsfeatures, die für die Nutzung von Cloudtechnologien entwickelt wurden.</span><span class="sxs-lookup"><span data-stu-id="95ba9-108">It also includes productivity features that are designed to take advantage of cloud technologies.</span></span>

<span data-ttu-id="95ba9-109">Um den Geschäftswert der integrierten Microsoft 365 unternehmensintegrierten Produktsuite zu maximieren, beginnen Sie mit der Planung und Implementierung einer Strategie zum Migrieren dieser Versionen:</span><span class="sxs-lookup"><span data-stu-id="95ba9-109">To maximize the business value of the Microsoft 365 for enterprise integrated suite of products, begin planning and implementing a strategy to migrate these releases:</span></span>

| <span data-ttu-id="95ba9-110">Von</span><span class="sxs-lookup"><span data-stu-id="95ba9-110">From</span></span> | <span data-ttu-id="95ba9-111">An</span><span class="sxs-lookup"><span data-stu-id="95ba9-111">To</span></span> |
|:-------|:-----|
| <span data-ttu-id="95ba9-112">Windows 7 und Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="95ba9-112">Windows 7 and Windows 8.1</span></span> | <span data-ttu-id="95ba9-113">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="95ba9-113">Windows 10 Enterprise</span></span> |
| <span data-ttu-id="95ba9-114">Office Auf den Geräten Ihrer Mitarbeiter installierte Clientprodukte</span><span class="sxs-lookup"><span data-stu-id="95ba9-114">Office client products installed on your worker's devices</span></span> | <span data-ttu-id="95ba9-115">Microsoft 365 Apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="95ba9-115">Microsoft 365 Apps for enterprise</span></span> |
| <span data-ttu-id="95ba9-116">Office auf lokalen Servern installierte Serverprodukte</span><span class="sxs-lookup"><span data-stu-id="95ba9-116">Office server products installed on on-premises servers</span></span> | <span data-ttu-id="95ba9-117">Ihre entsprechenden cloudbasierten Dienste in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="95ba9-117">Their equivalent cloud-based services in Microsoft 365</span></span> |
|  |  |

## <a name="migrating-to-windows-10"></a><span data-ttu-id="95ba9-118">Migrieren zu Windows 10</span><span class="sxs-lookup"><span data-stu-id="95ba9-118">Migrating to Windows 10</span></span>

<span data-ttu-id="95ba9-119">Jede Microsoft 365 enterprise-Lizenz enthält eine Lizenz für Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="95ba9-119">Each Microsoft 365 for enterprise license includes a license for Windows 10 Enterprise.</span></span> <span data-ttu-id="95ba9-120">Um Ihre Geräte zu migrieren, auf Windows 7 oder Windows 8.1, können Sie ein in-Place-Upgrade durchführen.</span><span class="sxs-lookup"><span data-stu-id="95ba9-120">To migrate your devices that run Windows 7 or Windows 8.1, you can do an in-place upgrade.</span></span> <span data-ttu-id="95ba9-121">Der Support wurde für Windows 7 am *14. Januar 2020 beendet.*</span><span class="sxs-lookup"><span data-stu-id="95ba9-121">Support ended for Windows 7 on *January 14, 2020*.</span></span> 

<span data-ttu-id="95ba9-122">Weitere Methoden zum Installieren von Windows 10 Enterprise über ein in-place-Upgrade hinaus finden Sie [unter Windows 10 Bereitstellungsszenarien](/windows/deployment/windows-10-deployment-scenarios).</span><span class="sxs-lookup"><span data-stu-id="95ba9-122">For additional methods of installing Windows 10 Enterprise beyond an in-place upgrade, see [Windows 10 deployment scenarios](/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="95ba9-123">Sie können [die Bereitstellung von Windows 10 auch selbst planen](/windows/deployment/planning/).</span><span class="sxs-lookup"><span data-stu-id="95ba9-123">You can also [plan for Windows 10 deployment](/windows/deployment/planning/) on your own.</span></span>

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="95ba9-124">Migrieren zu Microsoft 365 Apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="95ba9-124">Migrating to Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="95ba9-125">Microsoft 365 enterprise enthält Microsoft 365 Apps for Enterprise, eine Version der Office-Clientprodukte (Word, PowerPoint, Excel und Outlook), die in der Microsoft Cloud installiert und aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="95ba9-125">Microsoft 365 for enterprise includes Microsoft 365 Apps for enterprise, a version of the Office client products (Word, PowerPoint, Excel, and Outlook) that is installed and updated from the Microsoft cloud.</span></span> <span data-ttu-id="95ba9-126">Weitere Informationen finden Sie unter [Informationen Microsoft 365 Apps for Enterprise](/deployoffice/about-microsoft-365-apps).</span><span class="sxs-lookup"><span data-stu-id="95ba9-126">For more information, see [About Microsoft 365 Apps for enterprise](/deployoffice/about-microsoft-365-apps).</span></span>

<span data-ttu-id="95ba9-127">Anstatt Ihre Computer für Office 2019 oder älteren Versionen auf dem neuesten Stand zu halten, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="95ba9-127">Rather than keeping your computers current for Office 2019 or older versions, take the following steps:</span></span>

1. <span data-ttu-id="95ba9-128">Hier können Sie eine Microsoft 365 für Ihre Benutzer erhalten und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="95ba9-128">Get and assign a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="95ba9-129">Deinstallieren Office 2013 oder Office 2016 auf ihren Computern.</span><span class="sxs-lookup"><span data-stu-id="95ba9-129">Uninstall Office 2013 or Office 2016 on their computers.</span></span>
3. <span data-ttu-id="95ba9-130">Installieren Microsoft 365 Apps for Enterprise, entweder einzeln oder während eines IT-Rollouts.</span><span class="sxs-lookup"><span data-stu-id="95ba9-130">Install Microsoft 365 Apps for enterprise, either individually or during an IT rollout.</span></span> <span data-ttu-id="95ba9-131">Weitere Informationen finden Sie unter [Bereitstellungshandbuch für Microsoft 365 Apps](/deployoffice/deployment-guide-microsoft-365-apps).</span><span class="sxs-lookup"><span data-stu-id="95ba9-131">For more information, see [Deployment guide for Microsoft 365 Apps](/deployoffice/deployment-guide-microsoft-365-apps).</span></span>

<span data-ttu-id="95ba9-132">Microsoft 365 Apps for Enterprise installiert sowohl Sicherheitsupdates als auch neue Featureupdates automatisch und kann cloudbasierte Dienste in Microsoft 365 sicherheit und Produktivität nutzen.</span><span class="sxs-lookup"><span data-stu-id="95ba9-132">Microsoft 365 Apps for enterprise installs both security updates and new feature updates automatically and can take advantage of cloud-based services in Microsoft 365 for enhanced security and productivity.</span></span>

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a><span data-ttu-id="95ba9-133">Migrieren von lokalen Servern und Daten zu Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="95ba9-133">Migrating on-premises servers and data to Microsoft 365</span></span>

<span data-ttu-id="95ba9-134">Microsoft 365 für Unternehmen umfasst cloudbasierte Versionen von Office-Serverdiensten, die einige der gleichen Tools wie lokale Versionen von Office-Serversoftware verwenden, z. B. Webbrowser und Outlook Client.</span><span class="sxs-lookup"><span data-stu-id="95ba9-134">Microsoft 365 for enterprise includes cloud-based versions of Office server services that use some of the same tools as on-premises versions of Office server software, such as web browsers and the Outlook client.</span></span> <span data-ttu-id="95ba9-135">Diese cloudbasierten Dienste werden aus Sicherheitsgründen und neuen Features automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="95ba9-135">These cloud-based services are automatically updated for security and new features.</span></span> <span data-ttu-id="95ba9-136">Nach der Migration kann Ihre IT-Abteilung die Zeit sparen, die zum Warten und Aktualisieren von lokalen Servern benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="95ba9-136">After migration, your IT department can save the time it takes to maintain and update on-premises servers.</span></span>

<span data-ttu-id="95ba9-137">Verwenden Sie die folgenden Ressourcen, um Informationen zum Migrieren von Benutzern und Daten für bestimmte Microsoft 365 zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="95ba9-137">Use the following resources for information about migrating users and data for specific Microsoft 365 workloads:</span></span>

- [<span data-ttu-id="95ba9-138">Verschieben von Postfächern von lokalen Exchange Server in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="95ba9-138">Move mailboxes from on-premises Exchange Server to Exchange Online</span></span>](/exchange/hybrid-deployment/move-mailboxes)
- [<span data-ttu-id="95ba9-139">Migrieren SharePoint Daten von SharePoint Server zu SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="95ba9-139">Migrate SharePoint data from SharePoint Server to SharePoint Online</span></span>](/sharepointmigration/migrate-to-sharepoint-online)
- [<span data-ttu-id="95ba9-140">Migrieren Skype for Business Online zu Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="95ba9-140">Migrate Skype for Business Online to Microsoft Teams</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a><span data-ttu-id="95ba9-141">Umstellung Ihrer gesamten Organisation</span><span class="sxs-lookup"><span data-stu-id="95ba9-141">Transition your entire organization</span></span>

<span data-ttu-id="95ba9-142">Laden Sie dieses Übergangsposter herunter, um ein besseres Bild davon zu erhalten, wie Sie Ihre gesamte Organisation zu den Produkten und Diensten in Microsoft 365 Enterprise verschieben:</span><span class="sxs-lookup"><span data-stu-id="95ba9-142">To get a better picture of how to move your entire organization to the products and services in Microsoft 365 for enterprise, download this transition poster:</span></span>

<span data-ttu-id="95ba9-143">[![Abbildung des Posters "Transition to Microsoft 365".](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span><span class="sxs-lookup"><span data-stu-id="95ba9-143">[![Image showing the Transition to Microsoft 365 poster.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span></span>

<span data-ttu-id="95ba9-144">Dieses zweiseitige Poster bietet eine schnelle Methode, um Ihre vorhandene Infrastruktur aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="95ba9-144">This two-page poster is a quick way to inventory your existing infrastructure.</span></span> <span data-ttu-id="95ba9-145">Verwenden Sie sie, um Anleitungen für den Wechsel zu einem Produkt oder dienst in Microsoft 365 Unternehmen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="95ba9-145">Use it to get guidance for moving to a product or service in Microsoft 365 for enterprise.</span></span> <span data-ttu-id="95ba9-146">Es zeigt Windows und Office Produkte sowie andere Infrastruktur- und Sicherheitselemente wie Geräteverwaltung, Identitäts- und Bedrohungsschutz sowie Informationsschutz und Compliance.</span><span class="sxs-lookup"><span data-stu-id="95ba9-146">It shows Windows and Office products and other infrastructure and security elements such as device management, identity and threat protection, and information protection and compliance.</span></span>

## <a name="results-of-step-4"></a><span data-ttu-id="95ba9-147">Ergebnisse von Schritt 4</span><span class="sxs-lookup"><span data-stu-id="95ba9-147">Results of Step 4</span></span>

<span data-ttu-id="95ba9-148">Für die Migration für Microsoft 365 Mandanten haben Sie ermittelt:</span><span class="sxs-lookup"><span data-stu-id="95ba9-148">For migration for your Microsoft 365 tenant, you have determined:</span></span>

- <span data-ttu-id="95ba9-149">Welche Geräte ausgeführt Windows 7 oder Windows 8.1 und der Plan, sie auf Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="95ba9-149">Which devices are running Windows 7 or Windows 8.1 and the plan to update them to Windows 10 Enterprise.</span></span>
- <span data-ttu-id="95ba9-150">Auf welchen Geräten werden die Office Client-Apps ausgeführt, und der Plan, sie auf Microsoft 365 für Unternehmen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="95ba9-150">Which devices are running the Office client apps and the plan to update them to Microsoft 365 apps for enterprise.</span></span>
- <span data-ttu-id="95ba9-151">Welche lokalen Office Serverdienste zu ihren Microsoft 365 migriert werden sollten, sowie der Plan, sie und ihre Daten zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="95ba9-151">Which on-premises Office server services should be migrated to their Microsoft 365 equivalent and the plan to migrate them and their data.</span></span>

<span data-ttu-id="95ba9-152">Im Folgenden finden Sie ein Beispiel für einen Mandanten mit einer abgeschlossenen Migration von lokalen Servern.</span><span class="sxs-lookup"><span data-stu-id="95ba9-152">Here is an example of a tenant with a completed migration of on-premises servers.</span></span>

![Beispiel für einen Mandanten mit einer abgeschlossenen Migration von lokalen Servern](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

<span data-ttu-id="95ba9-154">In dieser Abbildung verfügt die Organisation über:</span><span class="sxs-lookup"><span data-stu-id="95ba9-154">In this illustration, the organization has:</span></span>

- <span data-ttu-id="95ba9-155">Die lokalen Postfächer wurden Exchange Server zu Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="95ba9-155">Migrated its on-premises Exchange Server mailboxes to Exchange Online.</span></span>
- <span data-ttu-id="95ba9-156">Die lokalen Serverwebsites und -SharePoint wurden zu SharePoint in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="95ba9-156">Migrated its on-premises SharePoint Server sites and data to SharePoint in Microsoft 365.</span></span>

## <a name="ongoing-maintenance-for-migration"></a><span data-ttu-id="95ba9-157">Fortlaufende Wartung der Migration</span><span class="sxs-lookup"><span data-stu-id="95ba9-157">Ongoing maintenance for migration</span></span>

<span data-ttu-id="95ba9-158">Auf fortlaufender Basis müssen Sie möglicherweise:</span><span class="sxs-lookup"><span data-stu-id="95ba9-158">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="95ba9-159">Je nachdem, wie Exchange Postfachmigration ist, rollen Sie den Übergang zu Exchange Online ihrer Organisation fort.</span><span class="sxs-lookup"><span data-stu-id="95ba9-159">Depending on the state of your Exchange mailbox migration, continue rolling the transition to Exchange Online out to your organization.</span></span>
- <span data-ttu-id="95ba9-160">Je nach Status der lokalen Migration SharePoint Sie den Übergang zu SharePoint in Microsoft 365 Ihrer Organisation fort.</span><span class="sxs-lookup"><span data-stu-id="95ba9-160">Depending on the state of your on-premises SharePoint site migration, continue rolling the transition to SharePoint in Microsoft 365 out to your organization.</span></span>

## <a name="next-step"></a><span data-ttu-id="95ba9-161">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="95ba9-161">Next step</span></span>

<span data-ttu-id="95ba9-162">[![Schritt 5. Bereitstellen der Geräte- und App-Verwaltung](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span><span class="sxs-lookup"><span data-stu-id="95ba9-162">[![Step 5. Deploy device and app management](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span></span>

<span data-ttu-id="95ba9-163">Fahren Sie mit [der Geräte- und App-Verwaltung fort,](tenant-management-device-management.md) um die Geräte- und App-Verwaltung zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="95ba9-163">Continue with [device and app management](tenant-management-device-management.md) to deploy device and app management.</span></span>