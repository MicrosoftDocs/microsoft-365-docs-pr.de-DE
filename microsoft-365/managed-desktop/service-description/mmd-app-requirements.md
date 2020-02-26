---
title: Microsoft Managed Desktop-App-Anforderungen
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1ca08e84bf27a64ba7515b6f4c0307c94621601c
ms.sourcegitcommit: 6d672eb8287526a9db90df5fa85bc4984a7047d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2020
ms.locfileid: "42280103"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="45282-103">Microsoft Managed Desktop-App-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="45282-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="45282-104">Um die Leistung, Zuverlässigkeit und Servicefähigkeit von Microsoft Managed Desktop-Geräten zu gewährleisten, dürfen die Branchen-apps eines Kunden keine ernsthaften Auswirkungen auf die Endbenutzererfahrung haben oder die Sicherheitseinstellung ändern.</span><span class="sxs-lookup"><span data-stu-id="45282-104">In order to guarantee the performance, reliability, and serviceability of Microsoft Managed Desktop devices a customer’s line of business apps must not seriously impact end user experience or modify the security stance.</span></span> <span data-ttu-id="45282-105">Daher müssen Branchenanwendungen, die Sie auf Microsoft Managed Desktop-Geräten bereitstellen möchten, die Anforderungen in diesem Thema erfüllen.</span><span class="sxs-lookup"><span data-stu-id="45282-105">Consequently, line of business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span>

## <a name="application-condition"></a><span data-ttu-id="45282-106">Anwendungs Bedingung</span><span class="sxs-lookup"><span data-stu-id="45282-106">Application condition</span></span>

<span data-ttu-id="45282-107">Es ist wichtig, dass sich Anwendungen nicht nachteilig auf die von Microsoft verwaltete Desktop Umgebung auswirken.</span><span class="sxs-lookup"><span data-stu-id="45282-107">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment.</span></span> <span data-ttu-id="45282-108">Im folgenden sind die Anforderungen aufgeführt, die eine Anwendung erfüllen muss, damit eine Anwendung bereitgestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="45282-108">The following are the requirements that an application must meet for an application to be deployed.</span></span> <span data-ttu-id="45282-109">Für jede Anwendung oder jeden Treiber verzichtet Microsoft möglicherweise auf die hierin entgegenstehenden Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="45282-109">For any given application or driver, Microsoft may waive any requirement provided herein.</span></span> <span data-ttu-id="45282-110">Microsoft kann beschließen, jede Anwendung oder jeden Treiber zu entfernen, die sich negativ auf die Leistung und Zuverlässigkeit von von Microsoft verwalteten Desktop Geräten auswirkt.</span><span class="sxs-lookup"><span data-stu-id="45282-110">Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="centrally-managed-apps"></a><span data-ttu-id="45282-111">Zentral verwaltete apps</span><span class="sxs-lookup"><span data-stu-id="45282-111">Centrally managed apps</span></span>

<span data-ttu-id="45282-112">Alle auf Microsoft Managed Devices installierten Anwendungen und Treiber müssen über Microsoft InTune, den Microsoft Store oder den Microsoft Store for Business bereitgestellt werden. Wenn verfügbar, werden Treiber auch über den Windows Update-Dienst bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="45282-112">All applications and drivers installed on Microsoft Managed Devices must be deployed through Microsoft Intune, the Microsoft Store, or the Microsoft Store for Business; if available, drivers will also be deployed through the Windows Update service.</span></span> 

## <a name="prohibited-app-classes"></a><span data-ttu-id="45282-113">Verbotene App-Klassen</span><span class="sxs-lookup"><span data-stu-id="45282-113">Prohibited app classes</span></span>

<span data-ttu-id="45282-114">Bestimmte Anwendungstypen sind auf Microsoft Managed Desktop-Geräten nicht zulässig:</span><span class="sxs-lookup"><span data-stu-id="45282-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="45282-115">Virenschutz-, Sicherheits-oder Überwachungssoftware von Drittanbietern</span><span class="sxs-lookup"><span data-stu-id="45282-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="45282-116">Versionen von Microsoft Office vor Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="45282-116">Versions of Microsoft Office prior to Office 365 ProPlus</span></span>
- <span data-ttu-id="45282-117">Anwendungen, die andere Drittanbietersoftware installieren oder bündeln</span><span class="sxs-lookup"><span data-stu-id="45282-117">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="45282-118">Eingeschränktes App-Verhalten</span><span class="sxs-lookup"><span data-stu-id="45282-118">Restricted app behaviors</span></span>

<span data-ttu-id="45282-119">Bestimmte App-Verhaltensweisen können sich negativ auf die Benutzerfreundlichkeit auswirken oder ein Sicherheitsrisiko für von Microsoft verwaltete Desktop Geräte darstellen.</span><span class="sxs-lookup"><span data-stu-id="45282-119">Certain app behaviors can negatively impact the user experience or may present a security risk to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="45282-120">Apps mit den folgenden Verhaltensweisen dürfen nicht in der Microsoft Managed Desktop-Umgebung ohne einen bestimmten von Microsoft ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="45282-120">Apps with the following behaviors are not permitted to run in the Microsoft Managed Desktop environment without a specific  from Microsoft.</span></span>

<span data-ttu-id="45282-121">Benutzererfahrung:</span><span class="sxs-lookup"><span data-stu-id="45282-121">User Experience:</span></span>
- <span data-ttu-id="45282-122">Installieren von Hintergrunddiensten</span><span class="sxs-lookup"><span data-stu-id="45282-122">Install background services</span></span>
- <span data-ttu-id="45282-123">Selbst zum Start Pfad von Windows hinzufügen</span><span class="sxs-lookup"><span data-stu-id="45282-123">Add itself to the Windows startup path</span></span>
- <span data-ttu-id="45282-124">Von Treibern abhängige Anwendungen</span><span class="sxs-lookup"><span data-stu-id="45282-124">Applications dependent on drivers</span></span>
- <span data-ttu-id="45282-125">Drittanbieter-Webbrowser</span><span class="sxs-lookup"><span data-stu-id="45282-125">3rd party web browsers</span></span>

<span data-ttu-id="45282-126">Sicherheit:</span><span class="sxs-lookup"><span data-stu-id="45282-126">Security:</span></span>
- <span data-ttu-id="45282-127">Erhöhen der Benutzerberechtigungen</span><span class="sxs-lookup"><span data-stu-id="45282-127">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="45282-128">Fungieren als App Store oder verfügen über einen integrierten Erweiterungs-Manager</span><span class="sxs-lookup"><span data-stu-id="45282-128">Act as an app store or have a built-in extension manager</span></span>
- <span data-ttu-id="45282-129">Bekannte Sicherheitsrisiken</span><span class="sxs-lookup"><span data-stu-id="45282-129">Have known security vulnerabilities</span></span>
- <span data-ttu-id="45282-130">Verschlüsseln oder Einschränken des Zugriffs auf Endbenutzerdaten</span><span class="sxs-lookup"><span data-stu-id="45282-130">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="45282-131">Ist nicht signiert oder wird mit einem Zertifikat signiert, das nicht auf einen vertrauenswürdigen Stamm aufrollen kann.</span><span class="sxs-lookup"><span data-stu-id="45282-131">Is unsigned or is signed using a certificate which doesn’t roll up to a trusted root</span></span>


## <a name="driver-deployment"></a><span data-ttu-id="45282-132">Treiberbereitstellung</span><span class="sxs-lookup"><span data-stu-id="45282-132">Driver deployment</span></span>

<span data-ttu-id="45282-133">Microsoft Managed Desktop unterstützt nur Gerätetreiber, die über Windows Update oder einen installierten Posteingang mit dem von Microsoft verwalteten Gerät zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="45282-133">Microsoft Managed Desktop only supports device drivers that are available through Windows Update or installed inbox with the Microsoft Managed Device.</span></span> 

<span data-ttu-id="45282-134">Wenn für eine Anwendung eine bestimmte Treiber Ausführung erforderlich ist, wird Sie als eingeschränkte Anwendung betrachtet und erfordert eine Bereitstellung für Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="45282-134">If an application requires a specific driver(s) to run it is considered a Restricted Application and requires an  to be deployed to Microsoft Managed Desktop.</span></span> 

