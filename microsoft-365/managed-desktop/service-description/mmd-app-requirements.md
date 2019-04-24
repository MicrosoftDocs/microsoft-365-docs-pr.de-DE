---
title: Microsoft Managed Desktop-App-Anforderungen
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/08/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: de6cc7d77e023a9d41961e5fbcce060f1bb659ae
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278335"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="43235-103">Microsoft Managed Desktop-App-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="43235-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="43235-104">Branchenanwendungen, die Sie auf Microsoft Managed Desktop-Geräten bereitstellen möchten, müssen die Anforderungen in diesem Thema erfüllen.</span><span class="sxs-lookup"><span data-stu-id="43235-104">Line-of-business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span> 

## <a name="application-condition"></a><span data-ttu-id="43235-105">Anwendungs Bedingung</span><span class="sxs-lookup"><span data-stu-id="43235-105">Application condition</span></span>

<span data-ttu-id="43235-106">Es ist wichtig, dass sich Anwendungen nicht negativ auf die Microsoft Managed Desktop-Umgebung auswirken.</span><span class="sxs-lookup"><span data-stu-id="43235-106">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment.</span></span> <span data-ttu-id="43235-107">Es folgen die Anforderungen, die eine Anwendung erfüllen muss, damit Microsoft Sie bereitstellen kann.</span><span class="sxs-lookup"><span data-stu-id="43235-107">The following are the requirements that an application must meet in order for Microsoft to deploy it.</span></span> <span data-ttu-id="43235-108">Für eine bestimmte Anwendung oder einen Treiber kann Microsoft auf die hier aufgeführten Anforderungen verzichten.</span><span class="sxs-lookup"><span data-stu-id="43235-108">For any given application or driver, Microsoft may waive any requirement provided herein.</span></span> <span data-ttu-id="43235-109">Microsoft kann beschließen, alle Anwendungen oder Treiber zu entfernen, die sich negativ auf die Leistung und Zuverlässigkeit von Microsoft Managed Desktop-Geräten auswirken.</span><span class="sxs-lookup"><span data-stu-id="43235-109">Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="deployable-using-microsoft-technologies"></a><span data-ttu-id="43235-110">Bereitstellen mithilfe von Microsoft-Technologien</span><span class="sxs-lookup"><span data-stu-id="43235-110">Deployable using Microsoft technologies</span></span>

<span data-ttu-id="43235-111">Microsoft Managed Desktop verwendet InTune, Microsoft Store und Microsoft Store for Business, um Anwendungen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="43235-111">Microsoft Managed Desktop uses Intune,  Microsoft Store, and  Microsoft Store for Business to deploy applications.</span></span> <span data-ttu-id="43235-112">Daher müssen Anwendungen so verpackt werden, dass Sie von der jeweils aktuellen Version dieser Dienste bereitgestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="43235-112">Consequently, applications must be packaged in a manner able to be deployed by the then-current version of those services.</span></span>

## <a name="prohibited-app-classes"></a><span data-ttu-id="43235-113">Verbotene App-Klassen</span><span class="sxs-lookup"><span data-stu-id="43235-113">Prohibited app classes</span></span>

<span data-ttu-id="43235-114">Bestimmte Anwendungstypen sind auf verwalteten Desktop Geräten von Microsoft nicht zulässig:</span><span class="sxs-lookup"><span data-stu-id="43235-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="43235-115">Antiviren-, Sicherheits-oder Überwachungssoftware von Drittanbietern</span><span class="sxs-lookup"><span data-stu-id="43235-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="43235-116">Drittanbieter-Webbrowser</span><span class="sxs-lookup"><span data-stu-id="43235-116">3rd party web browsers</span></span>
- <span data-ttu-id="43235-117">Versionen von Microsoft Office vor Office 365 pro Plus</span><span class="sxs-lookup"><span data-stu-id="43235-117">Versions of Microsoft Office prior to Office 365 Pro Plus</span></span>
- <span data-ttu-id="43235-118">Anwendungen, die andere Drittanbietersoftware installieren oder bündeln</span><span class="sxs-lookup"><span data-stu-id="43235-118">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="43235-119">Eingeschränktes App-Verhalten</span><span class="sxs-lookup"><span data-stu-id="43235-119">Restricted app behaviors</span></span>

<span data-ttu-id="43235-120">Bestimmte Anwendungsverhaltens weisen können eine Beeinträchtigung der Benutzerfreundlichkeit oder ein Sicherheitsrisiko für verwaltete Desktop Geräte von Microsoft darstellen.</span><span class="sxs-lookup"><span data-stu-id="43235-120">Certain application behaviors can either be detrimental to user experience or present a security risk to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="43235-121">Anwendungen dürfen nicht die folgenden Verhaltensweisen oder Merkmale aufweisen:</span><span class="sxs-lookup"><span data-stu-id="43235-121">Applications shall not exhibit the following behaviors or characteristics:</span></span> 

<span data-ttu-id="43235-122">Benutzererfahrung:</span><span class="sxs-lookup"><span data-stu-id="43235-122">User Experience:</span></span>
- <span data-ttu-id="43235-123">Installieren von Hintergrunddiensten oder Laichen von lang andauernden Hintergrundprozessen</span><span class="sxs-lookup"><span data-stu-id="43235-123">Install background services or spawn long-running background processes</span></span>
- <span data-ttu-id="43235-124">Hinzufügen des Windows-Start Pfads</span><span class="sxs-lookup"><span data-stu-id="43235-124">Add itself to the Windows startup path</span></span>

<span data-ttu-id="43235-125">Sicherheit:</span><span class="sxs-lookup"><span data-stu-id="43235-125">Security:</span></span>
- <span data-ttu-id="43235-126">Aufrufen von nicht dokumentierten Windows-oder Office-APIs oder Abhängigkeiten von internen Windows-oder Office-Datenstrukturen</span><span class="sxs-lookup"><span data-stu-id="43235-126">Call undocumented Windows or Office APIs or take dependencies on internal Windows or Office data structures</span></span>
- <span data-ttu-id="43235-127">Fungieren als APP-Speicher oder haben integrierten Erweiterungs-Manager</span><span class="sxs-lookup"><span data-stu-id="43235-127">Act as an app store or have built-in extension manager</span></span>
- <span data-ttu-id="43235-128">Erhöhen der Berechtigungen des Endbenutzers</span><span class="sxs-lookup"><span data-stu-id="43235-128">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="43235-129">Bekannte Sicherheitsrisiken</span><span class="sxs-lookup"><span data-stu-id="43235-129">Have known security vulnerabilities</span></span>
- <span data-ttu-id="43235-130">Signiert mit einem Zertifikat, das nicht für ein vertrauenswürdiges Stammverzeichnis verwendet wird</span><span class="sxs-lookup"><span data-stu-id="43235-130">Signed using a certificate which doesn’t roll up to a trusted root</span></span>
- <span data-ttu-id="43235-131">VerSchlüsseln oder Einschränken des Zugriffs auf Endbenutzerdaten</span><span class="sxs-lookup"><span data-stu-id="43235-131">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="43235-132">Ändern des Betriebssystemcodes zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="43235-132">Modify operating system code at run time</span></span>

## <a name="driver-deployment"></a><span data-ttu-id="43235-133">Treiberbereitstellung</span><span class="sxs-lookup"><span data-stu-id="43235-133">Driver deployment</span></span>

<span data-ttu-id="43235-134">Wenn ein Treiber in Windows Update nicht verfügbar ist oder von Windows Hardware Quality Lab (WHQL) separat signiert wurde, muss Microsoft einen Treiber genehmigen, bevor Microsoft den Treiber für Microsoft Managed Desktop Devices bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="43235-134">Unless a driver is available in Windows Update or is separately signed by Windows Hardware Quality Lab (WHQL), Microsoft must approve a driver before Microsoft will deploy the driver to Microsoft Managed Desktop devices.</span></span>
