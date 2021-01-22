---
title: App-Überwachung & Berichterstellung - Security Center
description: Erfahren Sie, wie Sie mehr Einblicke in die Verwendung von Cloud-Apps in Ihrer Organisation erhalten. Umfasst verschiedene Arten von Apps, ihr Risikoniveau und Warnungen.
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, Sicherheitscenter, überwachen, Bericht, Apps
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: ed5fcfc16c08272a6a1d55af210ab48528538048
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930522"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="4cd23-105">Überwachung und Berichterstellung von Apps im Microsoft 365 Security Center</span><span class="sxs-lookup"><span data-stu-id="4cd23-105">App monitoring and reporting in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4cd23-106">Diese Berichte bieten mehr Einblick in die Verwendung von Cloud-Apps in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="4cd23-106">These reports provide more insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="4cd23-107">Umfasst verschiedene Arten von Apps, deren Risikostufe und Warnungen.</span><span class="sxs-lookup"><span data-stu-id="4cd23-107">Includes different kinds of apps, their level of risk, and alerts.</span></span>

## <a name="monitor-email-accounts-at-risk"></a><span data-ttu-id="4cd23-108">Überwachung von gefährdeten E-Mail-Konten</span><span class="sxs-lookup"><span data-stu-id="4cd23-108">Monitor email accounts at risk</span></span>

<span data-ttu-id="4cd23-109">**Beim E-Mail-Schutz** sind E-Mail-Konten gefährdet.</span><span class="sxs-lookup"><span data-stu-id="4cd23-109">**Email protection** shows email accounts at risk.</span></span> <span data-ttu-id="4cd23-110">Sie können ein Konto auswählen, um es im Microsoft Defender Security Center weiter zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="4cd23-110">You can select an account to investigate further in Microsoft Defender Security Center.</span></span>

![E-Mail-Schutzkarte](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a><span data-ttu-id="4cd23-112">Überwachen der von Benutzern erteilten App-Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="4cd23-112">Monitor app permissions granted by users</span></span>

<span data-ttu-id="4cd23-113">**Cloud App Security – OAuth-Apps** listen von Cloud App Security ermittelte Apps auf, die von Benutzern Berechtigungen erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="4cd23-113">**Cloud App Security - OAuth apps** lists apps discovered by Cloud App Security that have been granted permissions by users.</span></span> <span data-ttu-id="4cd23-114">Der Risikokatalog von Cloud App Security umfasst über 16.000 Apps, die mit über 70 Risikofaktoren bewertet werden.</span><span class="sxs-lookup"><span data-stu-id="4cd23-114">Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 70 risk factors.</span></span>

<span data-ttu-id="4cd23-115">Die Risikofaktoren beginnen mit allgemeinen Informationen, z. B. dem App-Herausgeber.</span><span class="sxs-lookup"><span data-stu-id="4cd23-115">The risk factors start from general information, such as the app publisher.</span></span> <span data-ttu-id="4cd23-116">Sie wechselt dann zu Sicherheitsmaßnahmen und -kontrollen, z. B. ob die App die Verschlüsselung im Ruhedienst unterstützt oder ein Überwachungsprotokoll der Benutzeraktivität enthält.</span><span class="sxs-lookup"><span data-stu-id="4cd23-116">It then moves to security measures and controls, such as whether the app supports encryption at rest or provides an audit log of user activity.</span></span>

![Cloud App Security OAuth-Apps-Karte](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a><span data-ttu-id="4cd23-118">Überwachen von Cloud-App-Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="4cd23-118">Monitor cloud app user accounts</span></span>

<span data-ttu-id="4cd23-119">**Cloud-App-Konten für Rezensionen** listen Konten auf, die möglicherweise Aufmerksamkeit erfordern.</span><span class="sxs-lookup"><span data-stu-id="4cd23-119">**Cloud app accounts for review** lists accounts that may require attention.</span></span>

![Cloud -App-Konten für Überprüfungskarte](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a><span data-ttu-id="4cd23-121">Verstehen, welche Cloud-Apps verwendet werden</span><span class="sxs-lookup"><span data-stu-id="4cd23-121">Understand which cloud apps are used</span></span>

<span data-ttu-id="4cd23-122">**Ermittelte Cloud-Apps (Kategorien)** zeigen, welche Arten von Apps in Ihrer Organisation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4cd23-122">**Discovered cloud apps (categories)** show what kinds of apps are being used in your organization.</span></span> <span data-ttu-id="4cd23-123">Es ist mit dem Cloud -Discovery-Dashboard in Cloud App Security verknüpft.</span><span class="sxs-lookup"><span data-stu-id="4cd23-123">It links to the Cloud Discovery dashboard in Cloud App Security.</span></span> <span data-ttu-id="4cd23-124">Weitere Informationen finden Sie unter [Schnellstart: Arbeiten mit ermittelten Apps.](https://docs.microsoft.com/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="4cd23-124">For more information, see [Quickstart: Work with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>  

![Karte "Kategorien für ermittelte Cloud-Apps"](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a><span data-ttu-id="4cd23-126">Überwachen, wo Benutzer auf Cloud-Apps zugreifen</span><span class="sxs-lookup"><span data-stu-id="4cd23-126">Monitor where users access cloud apps</span></span>

<span data-ttu-id="4cd23-127">**Cloud-App-Aktivitätsstandorte** zeigen an, wo Benutzer auf Cloud-Apps zugreifen.</span><span class="sxs-lookup"><span data-stu-id="4cd23-127">**Cloud app activity locations** show where users are accessing cloud apps.</span></span>

![Cloud App Activity Locations Card](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a><span data-ttu-id="4cd23-129">Überwachen der Integrität für Infrastrukturarbeitslasten</span><span class="sxs-lookup"><span data-stu-id="4cd23-129">Monitor health for infrastructure workloads</span></span>

<span data-ttu-id="4cd23-130">**Der Infrastrukturstatus** zeigt Integritätsstatuswarnungen für Infrastrukturarbeitsauslastungen in Azure Defender an.</span><span class="sxs-lookup"><span data-stu-id="4cd23-130">**Infrastructure health** shows health status alerts for infrastructure workloads in Azure Defender.</span></span>

<span data-ttu-id="4cd23-131">Azure Defender bietet eine einheitliche Sicherheitsverwaltung und Defender für Office 365 für lokale und Cloud-Workloads.</span><span class="sxs-lookup"><span data-stu-id="4cd23-131">Azure Defender provides unified security management and Defender for Office 365 across on-premises and cloud workloads.</span></span> <span data-ttu-id="4cd23-132">Sie können Sicherheitsdaten aus verschiedenen Quellen, einschließlich Firewalls und anderen Partnerlösungen, sammeln, durchsuchen und analysieren.</span><span class="sxs-lookup"><span data-stu-id="4cd23-132">You can collect, search, and analyze security data from different sources, including firewalls and other partner solutions.</span></span>

<span data-ttu-id="4cd23-133">Weitere Informationen finden Sie in der [Azure Defender-Dokumentation.](https://docs.microsoft.com/azure/security-center/)</span><span class="sxs-lookup"><span data-stu-id="4cd23-133">For more information, see [Azure Defender Documentation](https://docs.microsoft.com/azure/security-center/).</span></span>

![Infrastrukturintekarte](../../media/infrastructure-health.png)
