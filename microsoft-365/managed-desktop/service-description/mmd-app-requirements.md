---
title: Microsoft Managed Desktop-App-Anforderungen
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/08/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 07e4719d87cb11910a90665ce9beb95edf6641a4
ms.sourcegitcommit: e15cf5d0d8ff3dfdc457b469992d72ac802e6434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2019
ms.locfileid: "33467743"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="a6046-103">Microsoft Managed Desktop-App-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a6046-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="a6046-104">Um die Leistung, Zuverlässigkeit und Wartbarkeit von Microsoft Managed Desktop-Geräten zu gewährleisten, dürfen die Branchen-apps eines Kunden keine gravierenden Auswirkungen auf die Endbenutzererfahrung haben oder die Sicherheitseinstellung ändern.</span><span class="sxs-lookup"><span data-stu-id="a6046-104">In order to guarantee the performance, reliability, and serviceability of Microsoft Managed Desktop devices a customer’s line of business apps must not seriously impact end user experience or modify the security stance.</span></span> <span data-ttu-id="a6046-105">Daher müssen Branchenanwendungen, die Sie auf Microsoft Managed Desktop-Geräten bereitstellen möchten, die Anforderungen in diesem Thema erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a6046-105">Consequently, line of business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span>

## <a name="application-condition"></a><span data-ttu-id="a6046-106">Anwendungs Bedingung</span><span class="sxs-lookup"><span data-stu-id="a6046-106">Application condition</span></span>

<span data-ttu-id="a6046-107">Es ist wichtig, dass sich Anwendungen nicht negativ auf die Microsoft Managed Desktop-Umgebung auswirken.</span><span class="sxs-lookup"><span data-stu-id="a6046-107">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment.</span></span> <span data-ttu-id="a6046-108">Die folgenden Anforderungen müssen erfüllt sein, damit eine Anwendung bereitgestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="a6046-108">The following are the requirements that an application must meet for an application to be deployed.</span></span> <span data-ttu-id="a6046-109">Für eine bestimmte Anwendung oder einen Treiber kann Microsoft auf die hier aufgeführten Anforderungen verzichten.</span><span class="sxs-lookup"><span data-stu-id="a6046-109">For any given application or driver, Microsoft may waive any requirement provided herein.</span></span> <span data-ttu-id="a6046-110">Microsoft kann beschließen, alle Anwendungen oder Treiber zu entfernen, die sich negativ auf die Leistung und Zuverlässigkeit von Microsoft Managed Desktop-Geräten auswirken.</span><span class="sxs-lookup"><span data-stu-id="a6046-110">Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="centrally-managed-apps"></a><span data-ttu-id="a6046-111">Zentral verwaltete apps</span><span class="sxs-lookup"><span data-stu-id="a6046-111">Centrally managed apps</span></span>

<span data-ttu-id="a6046-112">Alle Anwendungen und Treiber, die auf verwalteten Microsoft-Geräten installiert sind, müssen über InTune, den Microsoft Store oder den Microsoft Store for Business bereitgestellt werden. Falls verfügbar, werden auch Treiber über den Windows Update-Dienst bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a6046-112">All applications and drivers installed on Microsoft Managed Devices must be deployed through Intune, the Microsoft Store, or the Microsoft Store for Business; if available, drivers will also be deployed through the Windows Update service.</span></span> 

## <a name="prohibited-app-classes"></a><span data-ttu-id="a6046-113">Verbotene App-Klassen</span><span class="sxs-lookup"><span data-stu-id="a6046-113">Prohibited app classes</span></span>

<span data-ttu-id="a6046-114">Bestimmte Anwendungstypen sind auf verwalteten Desktop Geräten von Microsoft nicht zulässig:</span><span class="sxs-lookup"><span data-stu-id="a6046-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="a6046-115">Antiviren-, Sicherheits-oder Überwachungssoftware von Drittanbietern</span><span class="sxs-lookup"><span data-stu-id="a6046-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="a6046-116">Versionen von Microsoft Office vor Office 365 pro Plus</span><span class="sxs-lookup"><span data-stu-id="a6046-116">Versions of Microsoft Office prior to Office 365 Pro Plus</span></span>
- <span data-ttu-id="a6046-117">Anwendungen, die andere Drittanbietersoftware installieren oder bündeln</span><span class="sxs-lookup"><span data-stu-id="a6046-117">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="a6046-118">Eingeschränktes App-Verhalten</span><span class="sxs-lookup"><span data-stu-id="a6046-118">Restricted app behaviors</span></span>

<span data-ttu-id="a6046-119">Bestimmte App-Verhaltensweisen können sich negativ auf die Benutzererfahrung auswirken oder können ein Sicherheitsrisiko für verwaltete Desktop Geräte von Microsoft darstellen.</span><span class="sxs-lookup"><span data-stu-id="a6046-119">Certain app behaviors can negatively impact the user experience or may present a security risk to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="a6046-120">Apps mit den folgenden Verhaltensweisen sind nicht zulässig, in der Microsoft Managed Desktop-Umgebung ohne eine bestimmte Ausnahme von Microsoft ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a6046-120">Apps with the following behaviors are not permitted to run in the Microsoft Managed Desktop environment without a specific exemption from Microsoft.</span></span>

<span data-ttu-id="a6046-121">Benutzererfahrung:</span><span class="sxs-lookup"><span data-stu-id="a6046-121">User Experience:</span></span>
- <span data-ttu-id="a6046-122">Installieren von Hintergrunddiensten</span><span class="sxs-lookup"><span data-stu-id="a6046-122">Install background services</span></span>
- <span data-ttu-id="a6046-123">Hinzufügen des Windows-Start Pfads</span><span class="sxs-lookup"><span data-stu-id="a6046-123">Add itself to the Windows startup path</span></span>
- <span data-ttu-id="a6046-124">Von Treibern abhängige Anwendungen</span><span class="sxs-lookup"><span data-stu-id="a6046-124">Applications dependent on drivers</span></span>
- <span data-ttu-id="a6046-125">Drittanbieter-Webbrowser</span><span class="sxs-lookup"><span data-stu-id="a6046-125">3rd party web browsers</span></span>

<span data-ttu-id="a6046-126">Sicherheit:</span><span class="sxs-lookup"><span data-stu-id="a6046-126">Security:</span></span>
- <span data-ttu-id="a6046-127">Erhöhen der Berechtigungen des Endbenutzers</span><span class="sxs-lookup"><span data-stu-id="a6046-127">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="a6046-128">Fungieren als APP-Speicher oder verfügen über einen integrierten Erweiterungs-Manager</span><span class="sxs-lookup"><span data-stu-id="a6046-128">Act as an app store or have a built-in extension manager</span></span>
- <span data-ttu-id="a6046-129">Bekannte Sicherheitsrisiken</span><span class="sxs-lookup"><span data-stu-id="a6046-129">Have known security vulnerabilities</span></span>
- <span data-ttu-id="a6046-130">VerSchlüsseln oder Einschränken des Zugriffs auf Endbenutzerdaten</span><span class="sxs-lookup"><span data-stu-id="a6046-130">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="a6046-131">Ist nicht signiert oder wird mit einem Zertifikat signiert, das nicht für ein vertrauenswürdiges Stammverzeichnis verwendet wird</span><span class="sxs-lookup"><span data-stu-id="a6046-131">Is unsigned or is signed using a certificate which doesn’t roll up to a trusted root</span></span>


## <a name="driver-deployment"></a><span data-ttu-id="a6046-132">Treiberbereitstellung</span><span class="sxs-lookup"><span data-stu-id="a6046-132">Driver deployment</span></span>

<span data-ttu-id="a6046-133">Microsoft Managed Desktop unterstützt nur Gerätetreiber, die über Windows Update oder den installierten Posteingang mit dem verwalteten Microsoft-Gerät zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="a6046-133">Microsoft Managed Desktop only supports device drivers that are available through Windows Update or installed inbox with the Microsoft Managed Device.</span></span> 

<span data-ttu-id="a6046-134">Wenn eine Anwendung einen bestimmten Treiber benötigt, um Sie auszuführen, wird Sie als eingeschränkte Anwendung angesehen, und es ist eine Ausnahmegenehmigung für Microsoft Managed Desktop erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a6046-134">If an application requires a specific driver(s) to run it is considered a Restricted Application and requires an exemption to be deployed to Microsoft Managed Desktop.</span></span> 

