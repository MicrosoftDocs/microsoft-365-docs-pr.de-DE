---
title: Häufig gestellte Fragen beim Aktivieren von Microsoft Threat Protection
description: Hier finden Sie Antworten auf die am häufigsten gestellten Fragen zu Lizenzierung, Berechtigungen, anfänglichen Einstellungen und anderen Produkten und Diensten im Zusammenhang mit der Aktivierung von Microsoft Threat Protection.
keywords: häufig gestellte Fragen, FAQ, gcc, erste Schritte, Aktivieren von MTP, Microsoft Threat Protection, M365, Sicherheit, Datenspeicherort, erforderliche Berechtigungen, Lizenz Berechtigung, Seite "Einstellungen"
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 6b0d8d9be0cc84e61a3228f79fc14f1bfc9f8a83
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198839"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-threat-protection"></a><span data-ttu-id="2a32e-104">Häufig gestellte Fragen beim Aktivieren von Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2a32e-104">Frequently asked questions when turning on Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2a32e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2a32e-105">**Applies to:**</span></span>
- <span data-ttu-id="2a32e-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2a32e-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="2a32e-107">Hier finden Sie Antworten auf die am häufigsten gestellten Fragen zum Aktivieren von [Microsoft Threat Protection](microsoft-threat-protection.md), einschließlich der erforderlichen Lizenzen und Berechtigungen, der Bereitstellung von Supportdiensten und der anfänglichen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="2a32e-107">Read responses to the most commonly asked questions about turning on [Microsoft Threat Protection](microsoft-threat-protection.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="2a32e-108">Anweisungen zum Aktivieren des Diensts finden [Sie unter Aktivieren von Microsoft Threat Protection](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="2a32e-108">For instructions on how to turn on the service, [read Turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-threat-protection"></a><span data-ttu-id="2a32e-109">Ich habe keine Microsoft 365 E5-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="2a32e-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="2a32e-110">Kann ich weiterhin Microsoft Threat Protection verwenden?</span><span class="sxs-lookup"><span data-stu-id="2a32e-110">Can I still use Microsoft Threat Protection?</span></span>

<span data-ttu-id="2a32e-111">Kunden mit den folgenden nicht-E5-Lizenzen können Microsoft Threat Protection verwenden:</span><span class="sxs-lookup"><span data-stu-id="2a32e-111">Customers with the following non-E5 licenses can use Microsoft Threat Protection:</span></span>

- <span data-ttu-id="2a32e-112">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2a32e-112">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="2a32e-113">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2a32e-113">Azure Advanced Threat Protection</span></span>
- <span data-ttu-id="2a32e-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2a32e-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="2a32e-115">Office 365 Advanced Threat Protection (Plan 2)</span><span class="sxs-lookup"><span data-stu-id="2a32e-115">Office 365 Advanced Threat Protection (Plan 2)</span></span>
 
<span data-ttu-id="2a32e-116">Eine vollständige Liste unterstützter Lizenzen [finden Sie in den Lizenzierungsanforderungen](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="2a32e-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-threat-protection"></a><span data-ttu-id="2a32e-117">Muss ich etwas installieren oder bereitstellen, um mit Microsoft Threat Protection zu beginnen?</span><span class="sxs-lookup"><span data-stu-id="2a32e-117">Do I need to install or deploy anything to start using Microsoft Threat Protection?</span></span>

<span data-ttu-id="2a32e-118">Nein, Microsoft Threat Protection konsolidiert Daten aus Microsoft 365-Sicherheitsdiensten, die Sie bereits bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="2a32e-118">No, Microsoft Threat Protection consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="2a32e-119">Sobald Sie die Funktion aktiviert haben, werden Vorfall-, Automatisierungs-und Jagd Erfahrungen im Rahmen der bereitgestellten Produkte ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2a32e-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="2a32e-120">Wenn keines dieser Produkte ordnungsgemäß bereitgestellt wird, zeigt Microsoft Threat Protection keine Daten an und kann keine Aktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="2a32e-120">If none of these products are properly deployed, Microsoft Threat Protection will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="2a32e-121">Zur Optimierung Ihrer Microsoft Threat Protection-Erlebnisse wird empfohlen, *alle* unterstützten [Microsoft 365-Sicherheitsprodukte und-Dienste](deploy-supported-services.md)bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="2a32e-121">To optimize your Microsoft Threat Protection experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-threat-protection-process-and-store-my-data"></a><span data-ttu-id="2a32e-122">Wo verarbeitet und speichert Microsoft Threat Protection meine Daten?</span><span class="sxs-lookup"><span data-stu-id="2a32e-122">Where does Microsoft Threat Protection process and store my data?</span></span>
<span data-ttu-id="2a32e-123">Microsoft Threat Protection wählt automatisch einen optimalen Standort für das Rechenzentrum aus, in dem konsolidierte Daten verarbeitet und gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="2a32e-123">Microsoft Threat Protection automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="2a32e-124">Wenn Sie Microsoft Defender ATP haben, wird derselbe Speicherort ausgewählt, der von Microsoft Defender ATP verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2a32e-124">If you have Microsoft Defender ATP, it selects the same location used by Microsoft Defender ATP.</span></span>

>[!NOTE]
><span data-ttu-id="2a32e-125">Microsoft Defender ATP stellt in den Rechenzentren der Europäischen Union (EU) automatisch Rückstellungen bereit, wenn Sie über das Azure Security Center aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="2a32e-125">Microsoft Defender ATP automatically provisions in European Union (EU) data centers when turned on through Azure Security Center.</span></span> <span data-ttu-id="2a32e-126">Microsoft Threat Protection wird automatisch im gleichen EU-Rechenzentrum für Kunden bereitgestellt, die Microsoft Defender ATP auf diese Weise bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="2a32e-126">Microsoft Threat Protection will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender ATP in this manner.</span></span> 

<span data-ttu-id="2a32e-127">Der Speicherort des Rechenzentrums wird vor und nach der Einrichtung des Diensts auf der Seite Einstellungen für Microsoft Threat Protection (**Einstellungen > Microsoft Threat Protection**) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2a32e-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft Threat Protection (**Settings > Microsoft Threat Protection**).</span></span> <span data-ttu-id="2a32e-128">Wenn Sie lieber einen anderen rechenzentrumsstandort verwenden möchten, wählen Sie **need help?** im Microsoft 365 Security Center aus, um den Microsoft-Support zu kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="2a32e-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-threat-protection"></a><span data-ttu-id="2a32e-129">Wo kann ich auf Microsoft Threat Protection zugreifen?</span><span class="sxs-lookup"><span data-stu-id="2a32e-129">Where can I access Microsoft Threat Protection?</span></span>

<span data-ttu-id="2a32e-130">Microsoft Threat Protection steht im Microsoft 365 Security Center zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="2a32e-130">Microsoft Threat Protection is available in Microsoft 365 security center.</span></span> <span data-ttu-id="2a32e-131">Um zum Sicherheitscenter zu wechseln, navigieren Sie zur URL [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="2a32e-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-threat-protection-in-microsoft-365-security-center"></a><span data-ttu-id="2a32e-132">Welche Berechtigungen benötige ich für den Zugriff auf Microsoft Threat Protection im Microsoft 365 Security Center?</span><span class="sxs-lookup"><span data-stu-id="2a32e-132">What permissions do I need to access Microsoft Threat Protection in Microsoft 365 security center?</span></span>

<span data-ttu-id="2a32e-133">Konten, denen die folgenden Azure Active Directory (AD)-Rollen zugewiesen sind, können auf Microsoft Threat Protection-Funktionen und -Daten zugreifen:</span><span class="sxs-lookup"><span data-stu-id="2a32e-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft Threat Protection functionality and data:</span></span>

- <span data-ttu-id="2a32e-134">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="2a32e-134">Global administrator</span></span>
- <span data-ttu-id="2a32e-135">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="2a32e-135">Security administrator</span></span>
- <span data-ttu-id="2a32e-136">Sicherheitsoperator</span><span class="sxs-lookup"><span data-stu-id="2a32e-136">Security Operator</span></span>
- <span data-ttu-id="2a32e-137">Globaler Leser</span><span class="sxs-lookup"><span data-stu-id="2a32e-137">Global Reader</span></span>
- <span data-ttu-id="2a32e-138">Sicherheitsleseberechtigter</span><span class="sxs-lookup"><span data-stu-id="2a32e-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="2a32e-139">Rollenbasierte Zugriffssteuerungseinstellungen in Microsoft Defender ATP beeinflussen den Zugriff auf Daten.</span><span class="sxs-lookup"><span data-stu-id="2a32e-139">Role-based access control settings in Microsoft Defender ATP influence access to data.</span></span> <span data-ttu-id="2a32e-140">Weitere Informationen finden Sie unter [Verwalten des Zugriffs auf Microsoft Threat Protection](mtp-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="2a32e-140">For more information, read about [managing access to Microsoft Threat Protection](mtp-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-threat-protection-default-to"></a><span data-ttu-id="2a32e-141">In welcher Zeitzone wird Microsoft Threat Protection standardmäßig verwendet?</span><span class="sxs-lookup"><span data-stu-id="2a32e-141">What time zone does Microsoft Threat Protection default to?</span></span>
<span data-ttu-id="2a32e-142">Standardmäßig zeigt Microsoft Threat Protection Zeit Informationen in der UTC-Zeitzone an.</span><span class="sxs-lookup"><span data-stu-id="2a32e-142">By default, Microsoft Threat Protection displays time information in the UTC time zone.</span></span> <span data-ttu-id="2a32e-143">Sie können diese Einstellung so ändern, dass Sie Ihre lokale Zeitzone verwendet.</span><span class="sxs-lookup"><span data-stu-id="2a32e-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="2a32e-144">Informationen zum Festlegen der Zeitzone</span><span class="sxs-lookup"><span data-stu-id="2a32e-144">Learn about setting the time zone</span></span>](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-threat-protection-feature-and-ui-updates"></a><span data-ttu-id="2a32e-145">Wie kann ich neue Features für Microsoft Threat Protection und Benutzeroberflächen Updates erfahren?</span><span class="sxs-lookup"><span data-stu-id="2a32e-145">How can I learn about new Microsoft Threat Protection feature and UI updates?</span></span>

<span data-ttu-id="2a32e-146">Microsoft stellt regelmäßig Informationen über die verschiedenen Kanäle bereit, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="2a32e-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="2a32e-147">Das [Nachrichtencenter](../../admin/manage/message-center.md) im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="2a32e-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="2a32e-148">Blogposts in der [Microsoft 365 Security & Compliance Tech-Community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="2a32e-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="2a32e-149">Holen Sie sich die neuesten öffentlich verfügbaren Benutzeroberflächen, indem Sie die [Vorschaufunktionen](preview.md)aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2a32e-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="2a32e-150">Ist Microsoft Threat Protection für US Government Community Cloud (GCC) oder GCC High verfügbar?</span><span class="sxs-lookup"><span data-stu-id="2a32e-150">Is Microsoft Threat Protection available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="2a32e-151">Zurzeit ist Microsoft Threat Protection dafür nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2a32e-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2a32e-152">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="2a32e-152">Related topics</span></span>

- [<span data-ttu-id="2a32e-153">Übersicht über Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2a32e-153">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- <span data-ttu-id="2a32e-154">[Aktivieren Sie Microsoft Threat Protection](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="2a32e-154">[Turn on Microsoft Threat Protection](mtp-enable.md).</span></span>
- [<span data-ttu-id="2a32e-155">Lizenzierungsanforderungen und andere Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="2a32e-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="2a32e-156">Bereitstellen unterstützter Dienste</span><span class="sxs-lookup"><span data-stu-id="2a32e-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="2a32e-157">Vorschaufunktionen aktivieren</span><span class="sxs-lookup"><span data-stu-id="2a32e-157">Turn on preview features</span></span>](preview.md)
