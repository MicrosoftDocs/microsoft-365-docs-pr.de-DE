---
title: Microsoft verwalteter Desktop-app-Anforderungen
description: ''
keywords: Dokumentation Microsoft verwalteter Desktop, Microsoft-365-Dienst
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/08/2019
ms.openlocfilehash: 6b6c6f6a2e719496578ac1d15c9b94a92a2ab492
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26867543"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="d1d8f-103">Microsoft verwalteter Desktop-app-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d1d8f-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="d1d8f-104">Line-of-Business Applications, die Sie an Microsoft verwalteter Desktop Geräte bereitstellen möchten, müssen die Anforderungen in diesem Thema erfüllen.</span><span class="sxs-lookup"><span data-stu-id="d1d8f-104">Line-of-business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span> 

## <a name="application-condition"></a><span data-ttu-id="d1d8f-105">Anwendung Bedingung</span><span class="sxs-lookup"><span data-stu-id="d1d8f-105">Application condition</span></span>

<span data-ttu-id="d1d8f-p101">Es ist wichtig, dass Anwendungen sich negativ auf die Umgebung Microsoft verwalteten Desktops keine Auswirkung auf die. Im folgenden werden die Anforderungen, dass eine Anwendung, damit Microsoft erfüllen muss bereitzustellen. Für jede Anwendung oder Treiber kann Microsoft jede Anforderung dargelegten verzichten. Microsoft kann beschließen, entfernen Sie alle Anwendung oder Treiber, die sich negativ auf Leistung und Zuverlässigkeit von Microsoft verwalteten Desktops Geräte auswirkt.</span><span class="sxs-lookup"><span data-stu-id="d1d8f-p101">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment. The following are the requirements that an application must meet in order for Microsoft to deploy it. For any given application or driver, Microsoft may waive any requirement provided herein. Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="deployable-using-microsoft-technologies"></a><span data-ttu-id="d1d8f-110">Bereitstellung von Microsoft-Technologien</span><span class="sxs-lookup"><span data-stu-id="d1d8f-110">Deployable using Microsoft technologies</span></span>

<span data-ttu-id="d1d8f-p102">Microsoft verwalteter Desktop verwendet Intune, Microsoft Store und Microsoft Store for Business Applications bereitstellen. Aus diesem Grund müssen Applications auf eine Weise, die von der aktuellen Version dieser Dienste bereitgestellt werden können verpackt werden.</span><span class="sxs-lookup"><span data-stu-id="d1d8f-p102">Microsoft Managed Desktop uses Intune,  Microsoft Store, and  Microsoft Store for Business to deploy applications. Consequently, applications must be packaged in a manner able to be deployed by the then-current version of those services.</span></span>

## <a name="prohibited-app-classes"></a><span data-ttu-id="d1d8f-113">Verbotene app-Klassen</span><span class="sxs-lookup"><span data-stu-id="d1d8f-113">Prohibited app classes</span></span>

<span data-ttu-id="d1d8f-114">Bestimmte Anwendungstypen dürfen nicht auf verwaltete Microsoft-Desktop-Geräten:</span><span class="sxs-lookup"><span data-stu-id="d1d8f-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="d1d8f-115">3. Partei Antivirus, Sicherheit oder Audit-software</span><span class="sxs-lookup"><span data-stu-id="d1d8f-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="d1d8f-116">3. Partei Webbrowser</span><span class="sxs-lookup"><span data-stu-id="d1d8f-116">3rd party web browsers</span></span>
- <span data-ttu-id="d1d8f-117">Versionen von Microsoft Office, bevor Sie Office 365 Pro Plus</span><span class="sxs-lookup"><span data-stu-id="d1d8f-117">Versions of Microsoft Office prior to Office 365 Pro Plus</span></span>
- <span data-ttu-id="d1d8f-118">Anwendungen, die installieren oder andere 3. Software von Drittanbietern Verpacken</span><span class="sxs-lookup"><span data-stu-id="d1d8f-118">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="d1d8f-119">Eingeschränkte app Verhaltensweisen</span><span class="sxs-lookup"><span data-stu-id="d1d8f-119">Restricted app behaviors</span></span>

<span data-ttu-id="d1d8f-p103">Bestimmte Anwendung Verhaltensweisen werden so stark beeinträchtigt bei Benutzeroberfläche oder an Microsoft verwalteter Desktop Geräte ein Sicherheitsrisiko darstellen können. Applikationen darf nicht die folgenden Verhaltensweisen oder Merkmale aufweisen:</span><span class="sxs-lookup"><span data-stu-id="d1d8f-p103">Certain application behaviors can either be detrimental to user experience or present a security risk to Microsoft Managed Desktop devices. Applications shall not exhibit the following behaviors or characteristics:</span></span> 

<span data-ttu-id="d1d8f-122">Benutzeroberfläche:</span><span class="sxs-lookup"><span data-stu-id="d1d8f-122">User Experience:</span></span>
- <span data-ttu-id="d1d8f-123">Installieren Sie Hintergrunddienste oder erzeugen langer Hintergrundprozesse</span><span class="sxs-lookup"><span data-stu-id="d1d8f-123">Install background services or spawn long-running background processes</span></span>
- <span data-ttu-id="d1d8f-124">Hinzufügen von selbst zu den Windows-Startpfad</span><span class="sxs-lookup"><span data-stu-id="d1d8f-124">Add itself to the Windows startup path</span></span>

<span data-ttu-id="d1d8f-125">Sicherheit:</span><span class="sxs-lookup"><span data-stu-id="d1d8f-125">Security:</span></span>
- <span data-ttu-id="d1d8f-126">Rufen Sie nicht dokumentierte Windows- oder Office-APIs oder internen Datenstrukturen Windows- oder Office übernehmen Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="d1d8f-126">Call undocumented Windows or Office APIs or take dependencies on internal Windows or Office data structures</span></span>
- <span data-ttu-id="d1d8f-127">Fungieren Sie als app-Store oder über die integrierte Erweiterungsmanager</span><span class="sxs-lookup"><span data-stu-id="d1d8f-127">Act as an app store or have built-in extension manager</span></span>
- <span data-ttu-id="d1d8f-128">Der Endbenutzer Berechtigungen ausweiten</span><span class="sxs-lookup"><span data-stu-id="d1d8f-128">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="d1d8f-129">Sicherheitsrisiken haben bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="d1d8f-129">Have known security vulnerabilities</span></span>
- <span data-ttu-id="d1d8f-130">Mit einem Zertifikat die vertrauenswürdige Stammzertifizierungsstelle Rollup nicht signiert</span><span class="sxs-lookup"><span data-stu-id="d1d8f-130">Signed using a certificate which doesn’t roll up to a trusted root</span></span>
- <span data-ttu-id="d1d8f-131">Verschlüsseln oder Einschränken des Zugriffs auf Endbenutzerdaten</span><span class="sxs-lookup"><span data-stu-id="d1d8f-131">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="d1d8f-132">Ändern der Betriebssystem-Code zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="d1d8f-132">Modify operating system code at run time</span></span>

## <a name="driver-deployment"></a><span data-ttu-id="d1d8f-133">Treiber-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="d1d8f-133">Driver deployment</span></span>

<span data-ttu-id="d1d8f-134">Es sei denn, ein Treiber in Windows Update verfügbar ist oder von Windows Hardware Quality Lab (WHQL) getrennt signiert ist, muss Microsoft einen Treiber genehmigen, bevor Microsoft des Treibers an Microsoft verwalteter Desktop-Geräte Deployment.</span><span class="sxs-lookup"><span data-stu-id="d1d8f-134">Unless a driver is available in Windows Update or is separately signed by Windows Hardware Quality Lab (WHQL), Microsoft must approve a driver before Microsoft will deploy the driver to Microsoft Managed Desktop devices.</span></span>
