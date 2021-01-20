---
title: 'Schritt 4: Migration für Ihre Microsoft 365 Enterprise-Mandanten'
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
ms.custom:
- Ent_Solutions
description: Migrieren Sie Ihre Windows-Geräte, Office-Client-Apps und Office-Server für Ihre Microsoft 365-Mandanten.
ms.openlocfilehash: 3230f7e1087b573691f04b9335a15b4ad6d20b65
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908628"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="e2118-104">Schritt 4.</span><span class="sxs-lookup"><span data-stu-id="e2118-104">Step 4.</span></span> <span data-ttu-id="e2118-105">Migration für Ihre Microsoft 365 Enterprise-Mandanten</span><span class="sxs-lookup"><span data-stu-id="e2118-105">Migration for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="e2118-106">Die meisten Unternehmensorganisationen verfügen über eine heterogene Umgebung, die mehrere Versionen von Betriebssystemen, Clientsoftware und Serversoftware umfasst.</span><span class="sxs-lookup"><span data-stu-id="e2118-106">Most enterprise organizations have a heterogeneous environment that includes multiple releases of operating systems, client software, and server software.</span></span> <span data-ttu-id="e2118-107">Microsoft 365 Enterprise umfasst die sichersten Versionen der wichtigsten Komponenten Ihrer IT-Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="e2118-107">Microsoft 365 for enterprise includes the most secure versions of the key components of your IT infrastructure.</span></span> <span data-ttu-id="e2118-108">Es enthält auch Produktivitätsfeatures, die darauf ausgelegt sind, die Vorteile von Cloudtechnologien zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="e2118-108">It also includes productivity features that are designed to take advantage of cloud technologies.</span></span>

<span data-ttu-id="e2118-109">Um den Geschäftswert der integrierten Produktsuite von Microsoft 365 Enterprise zu maximieren, beginnen Sie mit der Planung und Implementierung einer Strategie zum Migrieren dieser Versionen:</span><span class="sxs-lookup"><span data-stu-id="e2118-109">To maximize the business value of the Microsoft 365 for enterprise integrated suite of products, begin planning and implementing a strategy to migrate these releases:</span></span>

| <span data-ttu-id="e2118-110">Von</span><span class="sxs-lookup"><span data-stu-id="e2118-110">From</span></span> | <span data-ttu-id="e2118-111">An</span><span class="sxs-lookup"><span data-stu-id="e2118-111">To</span></span> |
|:-------|:-----|
| <span data-ttu-id="e2118-112">Windows 7 und Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="e2118-112">Windows 7 and Windows 8.1</span></span> | <span data-ttu-id="e2118-113">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e2118-113">Windows 10 Enterprise</span></span> |
| <span data-ttu-id="e2118-114">Auf den Geräten Ihrer Mitarbeiter installierte Office-Clientprodukte</span><span class="sxs-lookup"><span data-stu-id="e2118-114">Office client products installed on your worker's devices</span></span> | <span data-ttu-id="e2118-115">Microsoft 365 Apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="e2118-115">Microsoft 365 Apps for enterprise</span></span> |
| <span data-ttu-id="e2118-116">Auf lokalen Servern installierte Office-Serverprodukte</span><span class="sxs-lookup"><span data-stu-id="e2118-116">Office server products installed on on-premises servers</span></span> | <span data-ttu-id="e2118-117">Die entsprechenden cloudbasierten Dienste in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e2118-117">Their equivalent cloud-based services in Microsoft 365</span></span> |
|  |  |

## <a name="migrating-to-windows-10"></a><span data-ttu-id="e2118-118">Migrieren zu Windows 10</span><span class="sxs-lookup"><span data-stu-id="e2118-118">Migrating to Windows 10</span></span>

<span data-ttu-id="e2118-119">Jede Microsoft 365 Enterprise-Lizenz enthält eine Lizenz für Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e2118-119">Each Microsoft 365 for enterprise license includes a license for Windows 10 Enterprise.</span></span> <span data-ttu-id="e2118-120">Um Ihre Geräte mit Windows 7 oder Windows 8.1 zu migrieren, können Sie ein in-Place-Upgrade durchführen.</span><span class="sxs-lookup"><span data-stu-id="e2118-120">To migrate your devices that run Windows 7 or Windows 8.1, you can do an in-place upgrade.</span></span> <span data-ttu-id="e2118-121">Der Support für Windows 7 wurde am *14. Januar 2020 eingestellt.*</span><span class="sxs-lookup"><span data-stu-id="e2118-121">Support ended for Windows 7 on *January 14, 2020*.</span></span> 

<span data-ttu-id="e2118-122">Weitere Methoden zum Installieren von Windows 10 Enterprise über ein in-Place-Upgrade hinaus finden Sie unter [Windows 10-Bereitstellungsszenarien.](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)</span><span class="sxs-lookup"><span data-stu-id="e2118-122">For additional methods of installing Windows 10 Enterprise beyond an in-place upgrade, see [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="e2118-123">Sie können [die Bereitstellung von Windows 10 auch selbst planen](https://aka.ms/planforwin10deployment).</span><span class="sxs-lookup"><span data-stu-id="e2118-123">You can also [plan for Windows 10 deployment](https://aka.ms/planforwin10deployment) on your own.</span></span>

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="e2118-124">Migrieren zu Microsoft 365 Apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="e2118-124">Migrating to Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="e2118-125">Microsoft 365 Enterprise umfasst Microsoft 365 Apps for Enterprise, eine Version der Office-Clientprodukte (Word, PowerPoint, Excel und Outlook), die aus der Microsoft Cloud installiert und aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="e2118-125">Microsoft 365 for enterprise includes Microsoft 365 Apps for enterprise, a version of the Office client products (Word, PowerPoint, Excel, and Outlook) that is installed and updated from the Microsoft cloud.</span></span> <span data-ttu-id="e2118-126">Weitere Informationen finden Sie unter [Microsoft 365 Apps for Enterprise](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps).</span><span class="sxs-lookup"><span data-stu-id="e2118-126">For more information, see [About Microsoft 365 Apps for enterprise](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps).</span></span>

<span data-ttu-id="e2118-127">Anstatt Ihre Computer für Office 2019 oder ältere Versionen auf dem neuesten Stand zu halten, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="e2118-127">Rather than keeping your computers current for Office 2019 or older versions, take the following steps:</span></span>

1. <span data-ttu-id="e2118-128">Sie können eine Microsoft 365-Lizenz für Ihre Benutzer erwerben und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e2118-128">Get and assign a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="e2118-129">Deinstallieren Sie Office 2013 oder Office 2016 auf ihren Computern.</span><span class="sxs-lookup"><span data-stu-id="e2118-129">Uninstall Office 2013 or Office 2016 on their computers.</span></span>
3. <span data-ttu-id="e2118-130">Installieren Sie Microsoft 365 Apps for Enterprise entweder einzeln oder während eines IT-Rollouts.</span><span class="sxs-lookup"><span data-stu-id="e2118-130">Install Microsoft 365 Apps for enterprise, either individually or during an IT rollout.</span></span> <span data-ttu-id="e2118-131">Weitere Informationen finden Sie im [Bereitstellungshandbuch für Microsoft 365-Apps.](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)</span><span class="sxs-lookup"><span data-stu-id="e2118-131">For more information, see [Deployment guide for Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps).</span></span>

<span data-ttu-id="e2118-132">Microsoft 365 Apps for Enterprise installiert sowohl Sicherheitsupdates als auch neue Featureupdates automatisch und kann cloudbasierte Dienste in Microsoft 365 für erhöhte Sicherheit und Produktivität nutzen.</span><span class="sxs-lookup"><span data-stu-id="e2118-132">Microsoft 365 Apps for enterprise installs both security updates and new feature updates automatically and can take advantage of cloud-based services in Microsoft 365 for enhanced security and productivity.</span></span>

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a><span data-ttu-id="e2118-133">Migrieren von lokalen Servern und Daten zu Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e2118-133">Migrating on-premises servers and data to Microsoft 365</span></span>

<span data-ttu-id="e2118-134">Microsoft 365 Enterprise umfasst cloudbasierte Versionen von Office-Serverdiensten, die einige der gleichen Tools wie lokale Versionen von Office Server-Software, z. B. Webbrowser und den Outlook-Client, verwenden.</span><span class="sxs-lookup"><span data-stu-id="e2118-134">Microsoft 365 for enterprise includes cloud-based versions of Office server services that use some of the same tools as on-premises versions of Office server software, such as web browsers and the Outlook client.</span></span> <span data-ttu-id="e2118-135">Diese cloudbasierten Dienste werden automatisch für Sicherheit und neue Features aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="e2118-135">These cloud-based services are automatically updated for security and new features.</span></span> <span data-ttu-id="e2118-136">Nach der Migration kann Ihre IT-Abteilung die Zeit sparen, die für die Wartung und Aktualisierung von lokalen Servern benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="e2118-136">After migration, your IT department can save the time it takes to maintain and update on-premises servers.</span></span>

<span data-ttu-id="e2118-137">Verwenden Sie die folgenden Ressourcen für Informationen zum Migrieren von Benutzern und Daten für bestimmte Microsoft 365-Workloads:</span><span class="sxs-lookup"><span data-stu-id="e2118-137">Use the following resources for information about migrating users and data for specific Microsoft 365 workloads:</span></span>

- [<span data-ttu-id="e2118-138">Verschieben von Postfächern aus lokalen Exchange Server Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e2118-138">Move mailboxes from on-premises Exchange Server to Exchange Online</span></span>](https://docs.microsoft.com/exchange/hybrid-deployment/move-mailboxes)
- [<span data-ttu-id="e2118-139">Migrieren von SharePoint-Daten von SharePoint Server zu SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e2118-139">Migrate SharePoint data from SharePoint Server to SharePoint Online</span></span>](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)
- [<span data-ttu-id="e2118-140">Migrieren von Skype for Business Online zu Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e2118-140">Migrate Skype for Business Online to Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a><span data-ttu-id="e2118-141">Umstellung Ihrer gesamten Organisation</span><span class="sxs-lookup"><span data-stu-id="e2118-141">Transition your entire organization</span></span>

<span data-ttu-id="e2118-142">Laden Sie dieses Poster zur Umstellung herunter, um sich ein besseres Bild davon zu machen, wie Sie Ihre gesamte Organisation auf die Produkte und Dienste in Microsoft 365 Enterprise umziehen:</span><span class="sxs-lookup"><span data-stu-id="e2118-142">To get a better picture of how to move your entire organization to the products and services in Microsoft 365 for enterprise, download this transition poster:</span></span>

<span data-ttu-id="e2118-143">[![Abbildung des Posters "Übergang zu Microsoft 365".](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span><span class="sxs-lookup"><span data-stu-id="e2118-143">[![Image showing the Transition to Microsoft 365 poster.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span></span>

<span data-ttu-id="e2118-144">Dieses zweiseitige Poster bietet eine schnelle Methode, um Ihre vorhandene Infrastruktur aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="e2118-144">This two-page poster is a quick way to inventory your existing infrastructure.</span></span> <span data-ttu-id="e2118-145">Verwenden Sie diese, um Anleitungen für den Wechsel zu einem Produkt oder Dienst in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e2118-145">Use it to get guidance for moving to a product or service in Microsoft 365 for enterprise.</span></span> <span data-ttu-id="e2118-146">Es zeigt Windows- und Office-Produkte sowie andere Infrastruktur- und Sicherheitselemente wie Geräteverwaltung, Identitäts- und Bedrohungsschutz sowie Informationsschutz und Compliance.</span><span class="sxs-lookup"><span data-stu-id="e2118-146">It shows Windows and Office products and other infrastructure and security elements such as device management, identity and threat protection, and information protection and compliance.</span></span>

## <a name="results-of-step-4"></a><span data-ttu-id="e2118-147">Ergebnisse von Schritt 4</span><span class="sxs-lookup"><span data-stu-id="e2118-147">Results of Step 4</span></span>

<span data-ttu-id="e2118-148">Für die Migration für Ihren Microsoft 365-Mandanten haben Sie festgelegt:</span><span class="sxs-lookup"><span data-stu-id="e2118-148">For migration for your Microsoft 365 tenant, you have determined:</span></span>

- <span data-ttu-id="e2118-149">Auf welchen Geräten Windows 7 oder Windows 8.1 ausgeführt wird und welche Geräte auf Windows 10 Enterprise aktualisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e2118-149">Which devices are running Windows 7 or Windows 8.1 and the plan to update them to Windows 10 Enterprise.</span></span>
- <span data-ttu-id="e2118-150">Auf welchen Geräten die Office-Client-Apps ausgeführt werden, und welche Geräte auf Microsoft 365 Apps for Enterprise aktualisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e2118-150">Which devices are running the Office client apps and the plan to update them to Microsoft 365 apps for enterprise.</span></span>
- <span data-ttu-id="e2118-151">Welche lokalen Office -Serverdienste zu ihrem Microsoft 365-Äquivalent migriert werden sollen, sowie der Plan, diese und ihre Daten zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="e2118-151">Which on-premises Office server services should be migrated to their Microsoft 365 equivalent and the plan to migrate them and their data.</span></span>

<span data-ttu-id="e2118-152">Hier ist ein Beispiel für einen Mandanten mit einer abgeschlossenen Migration von lokalen Servern.</span><span class="sxs-lookup"><span data-stu-id="e2118-152">Here is an example of a tenant with a completed migration of on-premises servers.</span></span>

![Beispiel für einen Mandanten mit einer abgeschlossenen Migration von lokalen Servern](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

<span data-ttu-id="e2118-154">In dieser Abbildung verfügt die Organisation über:</span><span class="sxs-lookup"><span data-stu-id="e2118-154">In this illustration, the organization has:</span></span>

- <span data-ttu-id="e2118-155">Die lokalen Postfächer Exchange Server Exchange Online migriert.</span><span class="sxs-lookup"><span data-stu-id="e2118-155">Migrated its on-premises Exchange Server mailboxes to Exchange Online.</span></span>
- <span data-ttu-id="e2118-156">Die lokalen SharePoint Server-Websites und -Daten wurden zu SharePoint in Microsoft 365 migriert.</span><span class="sxs-lookup"><span data-stu-id="e2118-156">Migrated its on-premises SharePoint Server sites and data to SharePoint in Microsoft 365.</span></span>

## <a name="ongoing-maintenance-for-migration"></a><span data-ttu-id="e2118-157">Laufende Wartung für die Migration</span><span class="sxs-lookup"><span data-stu-id="e2118-157">Ongoing maintenance for migration</span></span>

<span data-ttu-id="e2118-158">Es kann sein, dass Sie regelmäßig:</span><span class="sxs-lookup"><span data-stu-id="e2118-158">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="e2118-159">Je nach Status der Migration Ihres Exchange-Postfachs setzen Sie den Übergang zu Exchange Online in Ihre Organisation fort.</span><span class="sxs-lookup"><span data-stu-id="e2118-159">Depending on the state of your Exchange mailbox migration, continue rolling the transition to Exchange Online out to your organization.</span></span>
- <span data-ttu-id="e2118-160">Je nach Status Der Migration Ihrer lokalen SharePoint-Website, setzen Sie den Übergang zu SharePoint in Microsoft 365 weiter auf Ihre Organisation um.</span><span class="sxs-lookup"><span data-stu-id="e2118-160">Depending on the state of your on-premises SharePoint site migration, continue rolling the transition to SharePoint in Microsoft 365 out to your organization.</span></span>

## <a name="next-step"></a><span data-ttu-id="e2118-161">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="e2118-161">Next step</span></span>

<span data-ttu-id="e2118-162">[![Schritt 5. Bereitstellen der Geräte- und App-Verwaltung](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span><span class="sxs-lookup"><span data-stu-id="e2118-162">[![Step 5. Deploy device and app management](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span></span>

<span data-ttu-id="e2118-163">Fahren Sie mit [der Geräte- und App-Verwaltung fort,](tenant-management-device-management.md) um geräte- und app-Verwaltung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e2118-163">Continue with [device and app management](tenant-management-device-management.md) to deploy device and app management.</span></span>
