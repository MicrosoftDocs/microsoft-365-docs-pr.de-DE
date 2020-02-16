---
title: App-Überwachung und Berichterstellung im Microsoft 365 Security Center
description: Beschreibt, wie Sie mehr Einblicke in die Cloud-App-Verwendung in Ihrer Organisation erhalten können.
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
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: f7b3f2fcaac71eefa2579a0c3fd66666fe00f605
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42087674"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="ff954-104">App-Überwachung und Berichterstellung im Microsoft 365 Security Center</span><span class="sxs-lookup"><span data-stu-id="ff954-104">App monitoring and reporting in the Microsoft 365 security center</span></span>

<span data-ttu-id="ff954-105">Diese Berichte bieten einen besseren Einblick in die Verwendung von Cloud-apps in Ihrer Organisation, einschließlich der Arten von apps, des Risikos und der Warnungen.</span><span class="sxs-lookup"><span data-stu-id="ff954-105">These reports provide more insight into how cloud apps are being used in your organization, including what kinds of apps, their level of risk, and alerts.</span></span>

## <a name="monitor-email-accounts-at-risk"></a><span data-ttu-id="ff954-106">Überwachung von gefährdeten E-Mail-Konten</span><span class="sxs-lookup"><span data-stu-id="ff954-106">Monitor email accounts at risk</span></span>

<span data-ttu-id="ff954-107">**E-Mail-Schutz** zeigt e-Mail-Konten gefährdet an.</span><span class="sxs-lookup"><span data-stu-id="ff954-107">**Email protection** shows email accounts at risk.</span></span> <span data-ttu-id="ff954-108">Sie können auf ein Konto klicken, um es im Sicherheits Center von Microsoft Defender weiter zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="ff954-108">You can click an account to investigate further in Microsoft Defender Security Center.</span></span>

![E-Mail-Schutzkarte](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a><span data-ttu-id="ff954-110">Überwachen der von Benutzern erteilten App-Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ff954-110">Monitor app permissions granted by users</span></span>

<span data-ttu-id="ff954-111">**Cloud-App-Sicherheit – OAuth-apps** listet apps auf, die von der Cloud-App-Sicherheit erkannt wurden, denen Benutzerberechtigungen erteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="ff954-111">**Cloud App Security - OAuth apps** lists apps discovered by Cloud App Security that have been granted permissions by users.</span></span> <span data-ttu-id="ff954-112">Der Risikokatalog von Cloud App Security umfasst über 16.000 apps, die mit über 70 Risikofaktoren bewertet werden.</span><span class="sxs-lookup"><span data-stu-id="ff954-112">Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 70 risk factors.</span></span>

<span data-ttu-id="ff954-113">Die Risikofaktoren beginnen mit allgemeinen Informationen wie dem App-Herausgeber für Sicherheitsmaßnahmen und-Steuerelemente, beispielsweise, ob die APP die Verschlüsselung in Ruhe unterstützt oder ein Überwachungsprotokoll der Benutzeraktivität bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ff954-113">The risk factors start from general information, such as the app publisher, to security measures and controls, such as whether the app supports for encryption at rest or provides an audit log of user activity.</span></span>

![Cloud App Security OAuth apps Card](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a><span data-ttu-id="ff954-115">Überwachen von Cloud-App-Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="ff954-115">Monitor cloud app user accounts</span></span>

<span data-ttu-id="ff954-116">**Cloud-App-Konten für die Überprüfung** listet Konten auf, die möglicherweise Aufmerksamkeit erfordern.</span><span class="sxs-lookup"><span data-stu-id="ff954-116">**Cloud app accounts for review** lists accounts that may require attention.</span></span>

![Cloud-App-Konten für Überprüfungs Karte](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a><span data-ttu-id="ff954-118">Grundlegendes zu den verwendeten Cloud-apps</span><span class="sxs-lookup"><span data-stu-id="ff954-118">Understand which cloud apps are used</span></span>

<span data-ttu-id="ff954-119">**Erkannte Cloud-Apps (Kategorien)** zeigen, welche Arten von apps in Ihrer Organisation verwendet werden, und Links zum Cloud Discovery-Dashboard in der Cloud-App-Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="ff954-119">**Discovered cloud apps (categories)** show what kinds of apps are being used in your organization and links to the Cloud Discovery dashboard in Cloud App Security.</span></span> <span data-ttu-id="ff954-120">Weitere Informationen finden Sie unter [Quick Start: Arbeiten mit entdeckten apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span><span class="sxs-lookup"><span data-stu-id="ff954-120">For more information, see [Quickstart: Work with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>  

![Entdeckte Cloud Apps-Kategorien Karte](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a><span data-ttu-id="ff954-122">Überwachen der Benutzer auf Cloud-apps</span><span class="sxs-lookup"><span data-stu-id="ff954-122">Monitor where users access cloud apps</span></span>

<span data-ttu-id="ff954-123">**Cloud-App-Aktivitäts Speicherorte** zeigen an, wo Benutzer auf Cloud-apps zugreifen.</span><span class="sxs-lookup"><span data-stu-id="ff954-123">**Cloud app activity locations** show where users are accessing cloud apps.</span></span>

![Cloud-App-Aktivitäts Speicherkarte](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a><span data-ttu-id="ff954-125">Überwachen der Integrität von Infrastruktur Auslastungen</span><span class="sxs-lookup"><span data-stu-id="ff954-125">Monitor health for infrastructure workloads</span></span>

<span data-ttu-id="ff954-126">**Infrastruktur Integrität** zeigt Integritätsstatus Warnungen für Infrastruktur Arbeitslasten im Azure Security Center an.</span><span class="sxs-lookup"><span data-stu-id="ff954-126">**Infrastructure health** shows health status alerts for infrastructure workloads in Azure Security Center.</span></span>

<span data-ttu-id="ff954-127">Azure Security Center bietet einheitliches Sicherheitsmanagement und fortschrittlichen Schutz vor Bedrohungen in lokalen und Cloud-Arbeitsauslastungen.</span><span class="sxs-lookup"><span data-stu-id="ff954-127">Azure Security Center provides unified security management and advanced threat protection across on-premises and cloud workloads.</span></span> <span data-ttu-id="ff954-128">Sie können Sicherheitsdaten aus einer Vielzahl von Quellen erfassen, suchen und analysieren, darunter Firewalls und andere Partnerlösungen.</span><span class="sxs-lookup"><span data-stu-id="ff954-128">You can collect, search, and analyze security data from a variety of sources, including firewalls and other partner solutions.</span></span>

<span data-ttu-id="ff954-129">Weitere Informationen finden Sie unter [Azure Security Center-Dokumentation](https://docs.microsoft.com/azure/security-center/).</span><span class="sxs-lookup"><span data-stu-id="ff954-129">For more information, see [Azure Security Center Documentation](https://docs.microsoft.com/azure/security-center/).</span></span>

![Infrastruktur-Integritäts Karte](../../media/infrastructure-health.png)
