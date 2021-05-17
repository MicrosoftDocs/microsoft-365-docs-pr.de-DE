---
title: Häufig gestellte Fragen beim Aktivieren Microsoft 365 Defender
description: Erhalten Sie Antworten auf die am häufigsten gestellten Fragen zur Lizenzierung, berechtigungen, anfänglichen Einstellungen und anderen Produkten und Diensten im Zusammenhang mit der Aktivierung Microsoft 365 Defender
keywords: Häufig gestellte Fragen, HÄUFIG gestellte Fragen, GCC, erste Schritte, Aktivieren von Microsoft 365 Defender, Microsoft 365 Defender, M365, Sicherheit, Datenspeicherort, erforderlichen Berechtigungen, Lizenzberechtigung, Einstellungsseite
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 55c1a3807fe8e28ca12f4f638c1ab2ca717523ed
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933433"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="6ced9-104">Häufig gestellte Fragen beim Aktivieren Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6ced9-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6ced9-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="6ced9-105">**Applies to:**</span></span>
- <span data-ttu-id="6ced9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6ced9-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6ced9-107">Lesen Sie Antworten auf die am häufigsten gestellten Fragen zum Aktivieren von [Microsoft 365 Defender,](microsoft-365-defender.md)einschließlich erforderlicher Lizenzen und Berechtigungen, bereitstellen von Supportdiensten und anfänglichen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="6ced9-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-365-defender.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="6ced9-108">Anweisungen zum Aktivieren des Diensts finden Sie unter [Aktivieren Microsoft 365 Defender](m365d-enable.md).</span><span class="sxs-lookup"><span data-stu-id="6ced9-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="6ced9-109">Ich habe keine Microsoft 365 E5 Lizenz.</span><span class="sxs-lookup"><span data-stu-id="6ced9-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="6ced9-110">Kann ich defender weiterhin Microsoft 365 verwenden?</span><span class="sxs-lookup"><span data-stu-id="6ced9-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="6ced9-111">Kunden mit den folgenden Nicht-E5-Lizenzen können defender Microsoft 365 verwenden:</span><span class="sxs-lookup"><span data-stu-id="6ced9-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="6ced9-112">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6ced9-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="6ced9-113">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="6ced9-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="6ced9-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6ced9-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="6ced9-115">Microsoft Defender für Office 365 (Plan 2)</span><span class="sxs-lookup"><span data-stu-id="6ced9-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="6ced9-116">Eine vollständige Liste der unterstützten Lizenzen finden Sie [in den Lizenzierungsanforderungen](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="6ced9-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="6ced9-117">Muss ich etwas installieren oder bereitstellen, um mit der Verwendung von Microsoft 365 starten?</span><span class="sxs-lookup"><span data-stu-id="6ced9-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="6ced9-118">Nein, Microsoft 365 Defender daten aus Microsoft 365, die Sie bereits bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="6ced9-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="6ced9-119">Sobald Sie dies aktivieren, werden Die Erfahrungen mit Vorfällen, Automatisierung und Suche im Rahmen der bereitgestellten Produkte verwendet.</span><span class="sxs-lookup"><span data-stu-id="6ced9-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="6ced9-120">Wenn keines dieser Produkte ordnungsgemäß bereitgestellt wird, zeigt Microsoft 365 Defender keine Daten an und kann keine Aktionen ergreifen.</span><span class="sxs-lookup"><span data-stu-id="6ced9-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="6ced9-121">Zur Optimierung ihrer Microsoft 365 von Defender empfehlen  wir die Bereitstellung aller [unterstützten](deploy-supported-services.md)Microsoft 365 und Dienste .</span><span class="sxs-lookup"><span data-stu-id="6ced9-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="6ced9-122">Wo werden Microsoft 365 Von Defender verarbeiten und meine Daten gespeichert?</span><span class="sxs-lookup"><span data-stu-id="6ced9-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="6ced9-123">Microsoft 365 Defender wählt automatisch einen optimalen Speicherort für das Rechenzentrum aus, in dem konsolidierte Daten verarbeitet und gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="6ced9-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="6ced9-124">Wenn Sie über Microsoft Defender for Endpoint verfügen, wird derselbe Speicherort ausgewählt, der von Defender for Endpoint verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6ced9-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="6ced9-125">Microsoft Defender for Endpoint stellt automatisch In Rechenzentren in der Europäischen Union (EU) bereit, wenn sie über Azure Defender aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="6ced9-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="6ced9-126">Microsoft 365 Defender stellt automatisch im gleichen EU-Rechenzentrum Kunden zur Verfügung, die Microsoft Defender for Endpoint auf diese Weise bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="6ced9-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="6ced9-127">Der Speicherort des Rechenzentrums wird vor und nach der Bereitstellung des Diensts auf der Einstellungsseite für Microsoft 365 Defender ( Einstellungen > Microsoft 365 Defender )**angezeigt.**</span><span class="sxs-lookup"><span data-stu-id="6ced9-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender (**Settings > Microsoft 365 Defender**).</span></span> <span data-ttu-id="6ced9-128">Wenn Sie lieber einen anderen Rechenzentrumsspeicherort verwenden möchten, wählen Sie Hilfe **benötigen?** im Microsoft 365 Security Center aus, um den Microsoft-Support zu kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="6ced9-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="6ced9-129">Wo kann ich auf Microsoft 365 zugreifen?</span><span class="sxs-lookup"><span data-stu-id="6ced9-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="6ced9-130">Microsoft 365 Defender ist in Microsoft 365 Security Center verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6ced9-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="6ced9-131">Um zum Sicherheitscenter zu wechseln, navigieren Sie zur URL [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="6ced9-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="6ced9-132">Welche Berechtigungen benötigt ich für den Zugriff auf Microsoft 365 Defender in Microsoft 365 Security Center?</span><span class="sxs-lookup"><span data-stu-id="6ced9-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="6ced9-133">Konten, denen die folgenden Azure Active Directory (AD)-Rollen zugewiesen sind, können auf Microsoft 365 Funktionen und Daten von Defender zugreifen:</span><span class="sxs-lookup"><span data-stu-id="6ced9-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="6ced9-134">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="6ced9-134">Global administrator</span></span>
- <span data-ttu-id="6ced9-135">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="6ced9-135">Security administrator</span></span>
- <span data-ttu-id="6ced9-136">Sicherheitsoperator</span><span class="sxs-lookup"><span data-stu-id="6ced9-136">Security Operator</span></span>
- <span data-ttu-id="6ced9-137">Globaler Leser</span><span class="sxs-lookup"><span data-stu-id="6ced9-137">Global Reader</span></span>
- <span data-ttu-id="6ced9-138">Sicherheitsleseberechtigter</span><span class="sxs-lookup"><span data-stu-id="6ced9-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="6ced9-139">Rollenbasierte Zugriffssteuerungseinstellungen in Microsoft Defender for Endpoint beeinflussen den Zugriff auf Daten.</span><span class="sxs-lookup"><span data-stu-id="6ced9-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="6ced9-140">Weitere Informationen finden Sie unter [Verwalten des Zugriffs auf Microsoft 365 Defender](m365d-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="6ced9-140">For more information, read about [managing access to Microsoft 365 Defender](m365d-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="6ced9-141">In welcher Zeitzone Microsoft 365 Defender standardmäßig?</span><span class="sxs-lookup"><span data-stu-id="6ced9-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="6ced9-142">Standardmäßig zeigt Microsoft 365 Defender Zeitinformationen in der UTC-Zeitzone an.</span><span class="sxs-lookup"><span data-stu-id="6ced9-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="6ced9-143">Sie können diese Einstellung so ändern, dass Ihre lokale Zeitzone verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6ced9-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="6ced9-144">Informationen zum Festlegen der Zeitzone</span><span class="sxs-lookup"><span data-stu-id="6ced9-144">Learn about setting the time zone</span></span>](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="6ced9-145">Wie erfahre ich mehr über neue Microsoft 365 und Benutzeroberflächenupdates für Defender?</span><span class="sxs-lookup"><span data-stu-id="6ced9-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="6ced9-146">Microsoft stellt regelmäßig Informationen über die verschiedenen Kanäle zur Verfügung, darunter:</span><span class="sxs-lookup"><span data-stu-id="6ced9-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="6ced9-147">Das [Nachrichtencenter](../../admin/manage/message-center.md) im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="6ced9-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="6ced9-148">Blogposts in der [Microsoft 365 Security & Compliance Tech Community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="6ced9-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="6ced9-149">Erhalten Sie die neuesten öffentlich verfügbaren Erfahrungen, indem Sie [Vorschaufeatures aktivieren.](preview.md)</span><span class="sxs-lookup"><span data-stu-id="6ced9-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="6ced9-150">Ist Microsoft 365 Defender für GOVERNMENT COMMUNITY CLOUD (GCC) oder GCC Verfügbar?</span><span class="sxs-lookup"><span data-stu-id="6ced9-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="6ced9-151">Zurzeit ist Microsoft Threat Protection dafür nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6ced9-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6ced9-152">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="6ced9-152">Related topics</span></span>

- [<span data-ttu-id="6ced9-153">Microsoft 365 Übersicht über Defender</span><span class="sxs-lookup"><span data-stu-id="6ced9-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- <span data-ttu-id="6ced9-154">[Aktivieren sie Microsoft 365 Defender](m365d-enable.md).</span><span class="sxs-lookup"><span data-stu-id="6ced9-154">[Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>
- [<span data-ttu-id="6ced9-155">Lizenzierungsanforderungen und andere Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6ced9-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="6ced9-156">Bereitstellen unterstützter Dienste</span><span class="sxs-lookup"><span data-stu-id="6ced9-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="6ced9-157">Vorschaufeatures aktivieren</span><span class="sxs-lookup"><span data-stu-id="6ced9-157">Turn on preview features</span></span>](preview.md)
