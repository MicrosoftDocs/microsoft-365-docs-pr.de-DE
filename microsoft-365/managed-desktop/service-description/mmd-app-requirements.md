---
title: Microsoft Managed Desktop-App-Anforderungen
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: ded8bcfd87a6b430dfc4be055a582b482872b104
ms.sourcegitcommit: 498340389e1c34f49f0b2da382c23c8d5334ae47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/12/2019
ms.locfileid: "34913016"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="89455-103">Microsoft Managed Desktop-App-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="89455-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="89455-104">Um die Leistung, Zuverlässigkeit und Servicefähigkeit von Microsoft Managed Desktop-Geräten zu gewährleisten, dürfen die Branchen-apps eines Kunden keine ernsthaften Auswirkungen auf die Endbenutzererfahrung haben oder die Sicherheitseinstellung ändern.</span><span class="sxs-lookup"><span data-stu-id="89455-104">In order to guarantee the performance, reliability, and serviceability of Microsoft Managed Desktop devices a customer’s line of business apps must not seriously impact end user experience or modify the security stance.</span></span> <span data-ttu-id="89455-105">Daher müssen Branchenanwendungen, die Sie auf Microsoft Managed Desktop-Geräten bereitstellen möchten, die Anforderungen in diesem Thema erfüllen.</span><span class="sxs-lookup"><span data-stu-id="89455-105">Consequently, line of business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span>

## <a name="application-condition"></a><span data-ttu-id="89455-106">Anwendungs Bedingung</span><span class="sxs-lookup"><span data-stu-id="89455-106">Application condition</span></span>

<span data-ttu-id="89455-107">Es ist wichtig, dass sich Anwendungen nicht nachteilig auf die von Microsoft verwaltete Desktop Umgebung auswirken.</span><span class="sxs-lookup"><span data-stu-id="89455-107">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment.</span></span> <span data-ttu-id="89455-108">Im folgenden sind die Anforderungen aufgeführt, die eine Anwendung erfüllen muss, damit eine Anwendung bereitgestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="89455-108">The following are the requirements that an application must meet for an application to be deployed.</span></span> <span data-ttu-id="89455-109">Für jede Anwendung oder jeden Treiber verzichtet Microsoft möglicherweise auf die hierin entgegenstehenden Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="89455-109">For any given application or driver, Microsoft may waive any requirement provided herein.</span></span> <span data-ttu-id="89455-110">Microsoft kann beschließen, jede Anwendung oder jeden Treiber zu entfernen, die sich negativ auf die Leistung und Zuverlässigkeit von von Microsoft verwalteten Desktop Geräten auswirkt.</span><span class="sxs-lookup"><span data-stu-id="89455-110">Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="centrally-managed-apps"></a><span data-ttu-id="89455-111">Zentral verwaltete apps</span><span class="sxs-lookup"><span data-stu-id="89455-111">Centrally managed apps</span></span>

<span data-ttu-id="89455-112">Alle auf Microsoft Managed Devices installierten Anwendungen und Treiber müssen über Microsoft InTune, den Microsoft Store oder den Microsoft Store for Business bereitgestellt werden. Wenn verfügbar, werden Treiber auch über den Windows Update-Dienst bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="89455-112">All applications and drivers installed on Microsoft Managed Devices must be deployed through Microsoft Intune, the Microsoft Store, or the Microsoft Store for Business; if available, drivers will also be deployed through the Windows Update service.</span></span> 

## <a name="prohibited-app-classes"></a><span data-ttu-id="89455-113">Verbotene App-Klassen</span><span class="sxs-lookup"><span data-stu-id="89455-113">Prohibited app classes</span></span>

<span data-ttu-id="89455-114">Bestimmte Anwendungstypen sind auf Microsoft Managed Desktop-Geräten nicht zulässig:</span><span class="sxs-lookup"><span data-stu-id="89455-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="89455-115">Virenschutz-, Sicherheits-oder Überwachungssoftware von Drittanbietern</span><span class="sxs-lookup"><span data-stu-id="89455-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="89455-116">Versionen von Microsoft Office vor Office 365 pro Plus</span><span class="sxs-lookup"><span data-stu-id="89455-116">Versions of Microsoft Office prior to Office 365 Pro Plus</span></span>
- <span data-ttu-id="89455-117">Anwendungen, die andere Drittanbietersoftware installieren oder bündeln</span><span class="sxs-lookup"><span data-stu-id="89455-117">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="89455-118">Eingeschränktes App-Verhalten</span><span class="sxs-lookup"><span data-stu-id="89455-118">Restricted app behaviors</span></span>

<span data-ttu-id="89455-119">Bestimmte App-Verhaltensweisen können sich negativ auf die Benutzerfreundlichkeit auswirken oder ein Sicherheitsrisiko für von Microsoft verwaltete Desktop Geräte darstellen.</span><span class="sxs-lookup"><span data-stu-id="89455-119">Certain app behaviors can negatively impact the user experience or may present a security risk to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="89455-120">Apps mit den folgenden Verhaltensweisen dürfen nicht ohne spezielle Ausnahme von Microsoft in der Microsoft Managed Desktop-Umgebung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="89455-120">Apps with the following behaviors are not permitted to run in the Microsoft Managed Desktop environment without a specific exemption from Microsoft.</span></span>

<span data-ttu-id="89455-121">Benutzererfahrung:</span><span class="sxs-lookup"><span data-stu-id="89455-121">User Experience:</span></span>
- <span data-ttu-id="89455-122">Installieren von Hintergrunddiensten</span><span class="sxs-lookup"><span data-stu-id="89455-122">Install background services</span></span>
- <span data-ttu-id="89455-123">Selbst zum Start Pfad von Windows hinzufügen</span><span class="sxs-lookup"><span data-stu-id="89455-123">Add itself to the Windows startup path</span></span>
- <span data-ttu-id="89455-124">Von Treibern abhängige Anwendungen</span><span class="sxs-lookup"><span data-stu-id="89455-124">Applications dependent on drivers</span></span>
- <span data-ttu-id="89455-125">Drittanbieter-Webbrowser</span><span class="sxs-lookup"><span data-stu-id="89455-125">3rd party web browsers</span></span>

<span data-ttu-id="89455-126">Sicherheit:</span><span class="sxs-lookup"><span data-stu-id="89455-126">Security:</span></span>
- <span data-ttu-id="89455-127">Erhöhen der Benutzerberechtigungen</span><span class="sxs-lookup"><span data-stu-id="89455-127">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="89455-128">Fungieren als App Store oder verfügen über einen integrierten Erweiterungs-Manager</span><span class="sxs-lookup"><span data-stu-id="89455-128">Act as an app store or have a built-in extension manager</span></span>
- <span data-ttu-id="89455-129">Bekannte Sicherheitsrisiken</span><span class="sxs-lookup"><span data-stu-id="89455-129">Have known security vulnerabilities</span></span>
- <span data-ttu-id="89455-130">Verschlüsseln oder Einschränken des Zugriffs auf Endbenutzerdaten</span><span class="sxs-lookup"><span data-stu-id="89455-130">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="89455-131">Ist nicht signiert oder wird mit einem Zertifikat signiert, das nicht auf einen vertrauenswürdigen Stamm aufrollen kann.</span><span class="sxs-lookup"><span data-stu-id="89455-131">Is unsigned or is signed using a certificate which doesn’t roll up to a trusted root</span></span>


## <a name="driver-deployment"></a><span data-ttu-id="89455-132">Treiberbereitstellung</span><span class="sxs-lookup"><span data-stu-id="89455-132">Driver deployment</span></span>

<span data-ttu-id="89455-133">Microsoft Managed Desktop unterstützt nur Gerätetreiber, die über Windows Update oder einen installierten Posteingang mit dem von Microsoft verwalteten Gerät zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="89455-133">Microsoft Managed Desktop only supports device drivers that are available through Windows Update or installed inbox with the Microsoft Managed Device.</span></span> 

<span data-ttu-id="89455-134">Wenn für eine Anwendung eine bestimmte Treiber Ausführung erforderlich ist, wird Sie als eingeschränkte Anwendung betrachtet und erfordert eine Ausnahme für die Bereitstellung auf dem Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="89455-134">If an application requires a specific driver(s) to run it is considered a Restricted Application and requires an exemption to be deployed to Microsoft Managed Desktop.</span></span> 

