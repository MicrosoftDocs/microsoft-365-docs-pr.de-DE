---
title: App Monitoring & Reporting – Security Center
description: Hier erfahren Sie, wie Sie in Ihrer Organisation einen besseren Einblick in die Cloud-App-Nutzung erhalten. Umfasst verschiedene Arten von apps, deren Risikograd und Warnungen.
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, Sicherheitscenter, Monitor, Bericht, Apps
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8787bf212db342c84f13f8522e8853310e00c0ce
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429407"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="7a114-105">App-Überwachung und Berichterstellung im Microsoft 365 Security Center</span><span class="sxs-lookup"><span data-stu-id="7a114-105">App monitoring and reporting in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7a114-106">Diese Berichte bieten einen besseren Einblick in die Verwendung von Cloud-apps in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="7a114-106">These reports provide more insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="7a114-107">Umfasst verschiedene Arten von apps, deren Risikograd und Warnungen.</span><span class="sxs-lookup"><span data-stu-id="7a114-107">Includes different kinds of apps, their level of risk, and alerts.</span></span>

## <a name="monitor-email-accounts-at-risk"></a><span data-ttu-id="7a114-108">Überwachung von gefährdeten E-Mail-Konten</span><span class="sxs-lookup"><span data-stu-id="7a114-108">Monitor email accounts at risk</span></span>

<span data-ttu-id="7a114-109">**E-Mail-Schutz** zeigt e-Mail-Konten gefährdet an.</span><span class="sxs-lookup"><span data-stu-id="7a114-109">**Email protection** shows email accounts at risk.</span></span> <span data-ttu-id="7a114-110">Sie können ein Konto auswählen, das im Microsoft Defender Security Center weiter untersucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="7a114-110">You can select an account to investigate further in Microsoft Defender Security Center.</span></span>

![E-Mail-Schutzkarte](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a><span data-ttu-id="7a114-112">Überwachen der von Benutzern erteilten App-Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="7a114-112">Monitor app permissions granted by users</span></span>

<span data-ttu-id="7a114-113">**Cloud-App-Sicherheit – OAuth-apps** listet apps auf, die von der Cloud-App-Sicherheit erkannt wurden, denen Benutzerberechtigungen erteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="7a114-113">**Cloud App Security - OAuth apps** lists apps discovered by Cloud App Security that have been granted permissions by users.</span></span> <span data-ttu-id="7a114-114">Der Risikokatalog von Cloud App Security umfasst über 16.000 apps, die mit über 70 Risikofaktoren bewertet werden.</span><span class="sxs-lookup"><span data-stu-id="7a114-114">Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 70 risk factors.</span></span>

<span data-ttu-id="7a114-115">Die Risikofaktoren beginnen mit allgemeinen Informationen, beispielsweise mit dem App-Herausgeber.</span><span class="sxs-lookup"><span data-stu-id="7a114-115">The risk factors start from general information, such as the app publisher.</span></span> <span data-ttu-id="7a114-116">Anschließend werden Sicherheitsmaßnahmen und-Steuerelemente verschoben, beispielsweise ob die APP die Verschlüsselung in Rest unterstützt oder ein Überwachungsprotokoll der Benutzeraktivität bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="7a114-116">It then moves to security measures and controls, such as whether the app supports encryption at rest or provides an audit log of user activity.</span></span>

![Cloud App Security OAuth apps Card](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a><span data-ttu-id="7a114-118">Überwachen von Cloud-App-Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="7a114-118">Monitor cloud app user accounts</span></span>

<span data-ttu-id="7a114-119">**Cloud-App-Konten für die Überprüfung** listet Konten auf, die möglicherweise Aufmerksamkeit erfordern.</span><span class="sxs-lookup"><span data-stu-id="7a114-119">**Cloud app accounts for review** lists accounts that may require attention.</span></span>

![Cloud-App-Konten für Überprüfungs Karte](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a><span data-ttu-id="7a114-121">Grundlegendes zu den verwendeten Cloud-apps</span><span class="sxs-lookup"><span data-stu-id="7a114-121">Understand which cloud apps are used</span></span>

<span data-ttu-id="7a114-122">**Erkannte Cloud-Apps (Kategorien)** zeigen an, welche Arten von apps in Ihrer Organisation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7a114-122">**Discovered cloud apps (categories)** show what kinds of apps are being used in your organization.</span></span> <span data-ttu-id="7a114-123">Sie enthält Links zum Cloud Discovery-Dashboard in der Cloud-App-Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="7a114-123">It links to the Cloud Discovery dashboard in Cloud App Security.</span></span> <span data-ttu-id="7a114-124">Weitere Informationen finden Sie unter [Quick Start: Arbeiten mit entdeckten apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span><span class="sxs-lookup"><span data-stu-id="7a114-124">For more information, see [Quickstart: Work with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>  

![Entdeckte Cloud Apps-Kategorien Karte](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a><span data-ttu-id="7a114-126">Überwachen der Benutzer auf Cloud-apps</span><span class="sxs-lookup"><span data-stu-id="7a114-126">Monitor where users access cloud apps</span></span>

<span data-ttu-id="7a114-127">**Cloud-App-Aktivitäts Speicherorte** zeigen an, wo Benutzer auf Cloud-apps zugreifen.</span><span class="sxs-lookup"><span data-stu-id="7a114-127">**Cloud app activity locations** show where users are accessing cloud apps.</span></span>

![Cloud-App-Aktivitäts Speicherkarte](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a><span data-ttu-id="7a114-129">Überwachen der Integrität von Infrastruktur Auslastungen</span><span class="sxs-lookup"><span data-stu-id="7a114-129">Monitor health for infrastructure workloads</span></span>

<span data-ttu-id="7a114-130">**Infrastruktur Integrität** zeigt Integritätsstatus Warnungen für Infrastruktur Arbeitslasten im Azure Security Center an.</span><span class="sxs-lookup"><span data-stu-id="7a114-130">**Infrastructure health** shows health status alerts for infrastructure workloads in Azure Security Center.</span></span>

<span data-ttu-id="7a114-131">Azure Security Center bietet einheitliches Sicherheitsmanagement und fortschrittlichen Schutz vor Bedrohungen in lokalen und Cloud-Arbeitsauslastungen.</span><span class="sxs-lookup"><span data-stu-id="7a114-131">Azure Security Center provides unified security management and advanced threat protection across on-premises and cloud workloads.</span></span> <span data-ttu-id="7a114-132">Sie können Sicherheitsdaten aus unterschiedlichen Quellen, einschließlich Firewalls und anderen Partnerlösungen, sammeln, durchsuchen und analysieren.</span><span class="sxs-lookup"><span data-stu-id="7a114-132">You can collect, search, and analyze security data from different sources, including firewalls and other partner solutions.</span></span>

<span data-ttu-id="7a114-133">Weitere Informationen finden Sie unter [Azure Security Center-Dokumentation](https://docs.microsoft.com/azure/security-center/).</span><span class="sxs-lookup"><span data-stu-id="7a114-133">For more information, see [Azure Security Center Documentation](https://docs.microsoft.com/azure/security-center/).</span></span>

![Infrastruktur-Integritäts Karte](../../media/infrastructure-health.png)
