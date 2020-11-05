---
title: Häufig gestellte Fragen beim Aktivieren von Microsoft 365 Defender
description: Hier finden Sie Antworten auf die am häufigsten gestellten Fragen zu Lizenzierung, Berechtigungen, anfänglichen Einstellungen und anderen Produkten und Diensten im Zusammenhang mit der Aktivierung von Microsoft 365 Defender.
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
ms.openlocfilehash: 3dae9f208f5bb08d694322eb9f7cff35986930da
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920490"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="6e806-104">Häufig gestellte Fragen beim Aktivieren von Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6e806-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6e806-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="6e806-105">**Applies to:**</span></span>
- <span data-ttu-id="6e806-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6e806-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6e806-107">Hier finden Sie Antworten auf die am häufigsten gestellten Fragen zum Aktivieren von [Microsoft 365 Defender](microsoft-threat-protection.md), einschließlich der erforderlichen Lizenzen und Berechtigungen, der Bereitstellung von Supportdiensten und der anfänglichen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="6e806-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-threat-protection.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="6e806-108">Anweisungen zum Aktivieren des Diensts finden [Sie unter Aktivieren von Microsoft 365 Defender](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="6e806-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="6e806-109">Ich habe keine Microsoft 365 E5-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="6e806-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="6e806-110">Kann ich weiterhin Microsoft 365 Defender verwenden?</span><span class="sxs-lookup"><span data-stu-id="6e806-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="6e806-111">Kunden mit den folgenden nicht-E5-Lizenzen können Microsoft 365 Defender verwenden:</span><span class="sxs-lookup"><span data-stu-id="6e806-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="6e806-112">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6e806-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="6e806-113">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="6e806-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="6e806-114">Microsoft Cloud App-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="6e806-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="6e806-115">Verteidiger für Office 365 (Plan 2)</span><span class="sxs-lookup"><span data-stu-id="6e806-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="6e806-116">Eine vollständige Liste unterstützter Lizenzen [finden Sie in den Lizenzierungsanforderungen](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="6e806-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="6e806-117">Muss ich etwas installieren oder bereitstellen, um mit Microsoft 365 Defender zu beginnen?</span><span class="sxs-lookup"><span data-stu-id="6e806-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="6e806-118">Nein, Microsoft 365 Defender konsolidiert Daten von Microsoft 365-Sicherheitsdiensten, die Sie bereits bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="6e806-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="6e806-119">Sobald Sie die Funktion aktiviert haben, werden Vorfall-, Automatisierungs-und Jagd Erfahrungen im Rahmen der bereitgestellten Produkte ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6e806-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="6e806-120">Wenn keines dieser Produkte ordnungsgemäß bereitgestellt wird, zeigt Microsoft 365 Defender keine Daten an und kann keine Aktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="6e806-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="6e806-121">Zur Optimierung Ihrer Microsoft 365 Defender-Erlebnisse wird empfohlen, *alle* unterstützten [Microsoft 365-Sicherheitsprodukte und-Dienste](deploy-supported-services.md)bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="6e806-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="6e806-122">Wo verarbeitet und speichert Microsoft 365 Defender meine Daten?</span><span class="sxs-lookup"><span data-stu-id="6e806-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="6e806-123">Microsoft 365 Defender wählt automatisch einen optimalen Standort für das Rechenzentrum aus, in dem konsolidierte Daten verarbeitet und gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="6e806-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="6e806-124">Wenn Sie über Microsoft Defender für Endpoint verfügen, wird derselbe Speicherort ausgewählt, der von Defender für Endpoint verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6e806-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="6e806-125">Microsoft Defender für Endpoint stellt in den Datencentern der Europäischen Union (EU) automatisch Rückstellungen bereit, wenn Sie über Azure Defender aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="6e806-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="6e806-126">Microsoft 365 Defender wird automatisch im gleichen EU-Rechenzentrum für Kunden bereitgestellt, die Microsoft Defender für Endpoint auf diese Weise bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="6e806-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="6e806-127">Der Speicherort des Rechenzentrums wird vor und nach der Einrichtung des Diensts auf der Seite Einstellungen für Microsoft 365 Defender ( **Settings > Microsoft 365 Defender** ) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6e806-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender ( **Settings > Microsoft 365 Defender** ).</span></span> <span data-ttu-id="6e806-128">Wenn Sie lieber einen anderen rechenzentrumsstandort verwenden möchten, wählen Sie **need help?** im Microsoft 365 Security Center aus, um den Microsoft-Support zu kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="6e806-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="6e806-129">Wo kann ich auf Microsoft 365 Defender zugreifen?</span><span class="sxs-lookup"><span data-stu-id="6e806-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="6e806-130">Microsoft 365 Defender steht im Microsoft 365 Security Center zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="6e806-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="6e806-131">Um zum Sicherheitscenter zu wechseln, navigieren Sie zur URL [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="6e806-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="6e806-132">Welche Berechtigungen benötige ich für den Zugriff auf Microsoft 365 Defender im Microsoft 365 Security Center?</span><span class="sxs-lookup"><span data-stu-id="6e806-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="6e806-133">Konten, denen die folgenden Azure Active Directory (AD)-Rollen zugewiesen sind, können auf Microsoft 365 Defender-Funktionen und-Daten zugreifen:</span><span class="sxs-lookup"><span data-stu-id="6e806-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="6e806-134">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="6e806-134">Global administrator</span></span>
- <span data-ttu-id="6e806-135">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="6e806-135">Security administrator</span></span>
- <span data-ttu-id="6e806-136">Sicherheitsoperator</span><span class="sxs-lookup"><span data-stu-id="6e806-136">Security Operator</span></span>
- <span data-ttu-id="6e806-137">Globaler Leser</span><span class="sxs-lookup"><span data-stu-id="6e806-137">Global Reader</span></span>
- <span data-ttu-id="6e806-138">Sicherheitsleseberechtigter</span><span class="sxs-lookup"><span data-stu-id="6e806-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="6e806-139">Rollenbasierte Zugriffssteuerungseinstellungen in Microsoft Defender für Endpoint beeinflussen den Zugriff auf Daten.</span><span class="sxs-lookup"><span data-stu-id="6e806-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="6e806-140">Weitere Informationen finden Sie unter [Managing Access to Microsoft 365 Defender](mtp-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="6e806-140">For more information, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="6e806-141">In welcher Zeitzone wird Microsoft 365 Defender standardmäßig verwendet?</span><span class="sxs-lookup"><span data-stu-id="6e806-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="6e806-142">Standardmäßig zeigt Microsoft 365 Defender Zeit Informationen in der UTC-Zeitzone an.</span><span class="sxs-lookup"><span data-stu-id="6e806-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="6e806-143">Sie können diese Einstellung so ändern, dass Sie Ihre lokale Zeitzone verwendet.</span><span class="sxs-lookup"><span data-stu-id="6e806-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="6e806-144">Informationen zum Festlegen der Zeitzone</span><span class="sxs-lookup"><span data-stu-id="6e806-144">Learn about setting the time zone</span></span>](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="6e806-145">Wie kann ich neue Features von Microsoft 365 Defender und Benutzeroberflächen Updates erfahren?</span><span class="sxs-lookup"><span data-stu-id="6e806-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="6e806-146">Microsoft stellt regelmäßig Informationen über die verschiedenen Kanäle bereit, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="6e806-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="6e806-147">Das [Nachrichtencenter](../../admin/manage/message-center.md) im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="6e806-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="6e806-148">Blogposts in der [Microsoft 365 Security & Compliance Tech-Community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="6e806-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="6e806-149">Holen Sie sich die neuesten öffentlich verfügbaren Benutzeroberflächen, indem Sie die [Vorschaufunktionen](preview.md)aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6e806-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="6e806-150">Ist Microsoft 365 Defender für US Government Community Cloud (gcc) oder gcc High verfügbar?</span><span class="sxs-lookup"><span data-stu-id="6e806-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="6e806-151">Zurzeit ist Microsoft Threat Protection dafür nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6e806-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6e806-152">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="6e806-152">Related topics</span></span>

- [<span data-ttu-id="6e806-153">Microsoft 365 Defender (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="6e806-153">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- <span data-ttu-id="6e806-154">[Aktivieren Sie Microsoft 365 Defender](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="6e806-154">[Turn on Microsoft 365 Defender](mtp-enable.md).</span></span>
- [<span data-ttu-id="6e806-155">Lizenzierungsanforderungen und andere Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6e806-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="6e806-156">Bereitstellen unterstützter Dienste</span><span class="sxs-lookup"><span data-stu-id="6e806-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="6e806-157">Vorschaufeatures aktivieren</span><span class="sxs-lookup"><span data-stu-id="6e806-157">Turn on preview features</span></span>](preview.md)
