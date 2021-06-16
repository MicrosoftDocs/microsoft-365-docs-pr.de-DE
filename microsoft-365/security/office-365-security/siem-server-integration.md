---
title: SIEM-Serverintegration mit Microsoft 365 Diensten und Anwendungen
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: Hier erhalten Sie eine Übersicht über die Integration von SIEM-Servern (Security Information and Event Management) in Ihre Microsoft 365 Clouddienste und -anwendungen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8b9c17ba2dcefa65b60a53ab8bff405de4850fc0
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929791"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="cfacc-103">Siem-Serverintegration (Security Information and Event Management) in Microsoft 365 Dienste und Anwendungen</span><span class="sxs-lookup"><span data-stu-id="cfacc-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

<span data-ttu-id="cfacc-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="cfacc-104">**Applies to**</span></span>
- [<span data-ttu-id="cfacc-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="cfacc-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="cfacc-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="cfacc-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="cfacc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cfacc-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a><span data-ttu-id="cfacc-108">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="cfacc-108">Summary</span></span>

<span data-ttu-id="cfacc-109">Verwendet Oder plant Ihre Organisation, einen SIEM-Server (Security Information and Event Management) zu erhalten?</span><span class="sxs-lookup"><span data-stu-id="cfacc-109">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="cfacc-110">Sie fragen sich vielleicht, wie sie in Microsoft 365 oder Office 365 integriert wird.</span><span class="sxs-lookup"><span data-stu-id="cfacc-110">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="cfacc-111">Dieser Artikel enthält eine Liste der Ressourcen, die Sie verwenden können, um Ihren SIEM-Server in Microsoft 365 Dienste und Anwendungen zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="cfacc-111">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="cfacc-112">Wenn Sie noch keinen SIEM-Server haben und Ihre Optionen erkunden, sollten Sie **[Microsoft Azure Sentinel](/azure/sentinel/overview)** in Betracht ziehen.</span><span class="sxs-lookup"><span data-stu-id="cfacc-112">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="cfacc-113">Benötisiere ich einen SIEM-Server?</span><span class="sxs-lookup"><span data-stu-id="cfacc-113">Do I need a SIEM server?</span></span>

<span data-ttu-id="cfacc-114">Ob Sie einen SIEM-Server benötigen, hängt von vielen Faktoren ab, z. B. den Sicherheitsanforderungen Ihrer Organisation und dem Speicherort Ihrer Daten.</span><span class="sxs-lookup"><span data-stu-id="cfacc-114">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="cfacc-115">Microsoft 365 umfasst eine Vielzahl von Sicherheitsfeatures, die die Sicherheitsanforderungen vieler Organisationen ohne zusätzliche Server erfüllen, z. B. einen SIEM-Server.</span><span class="sxs-lookup"><span data-stu-id="cfacc-115">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="cfacc-116">Einige Organisationen haben besondere Umstände, die die Verwendung eines SIEM-Servers erfordern.</span><span class="sxs-lookup"><span data-stu-id="cfacc-116">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="cfacc-117">Im Folgenden finden Sie einige Beispiele:</span><span class="sxs-lookup"><span data-stu-id="cfacc-117">Here are some examples:</span></span>

- <span data-ttu-id="cfacc-118">*Fabrikam* verfügt über lokale Inhalte und Anwendungen und einige in der Cloud (sie verfügen über eine Hybrid-Cloudbereitstellung).</span><span class="sxs-lookup"><span data-stu-id="cfacc-118">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="cfacc-119">Um Sicherheitsberichte über alle Inhalte und Anwendungen hinweg zu erhalten, hat Fabrikam einen SIEM-Server implementiert.</span><span class="sxs-lookup"><span data-stu-id="cfacc-119">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="cfacc-120">*Contoso* ist eine Finanzdienstleistungsorganisation mit besonders strengen Sicherheitsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="cfacc-120">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="cfacc-121">Sie haben ihrer Umgebung einen SIEM-Server hinzugefügt, um den zusätzlichen Sicherheitsschutz zu nutzen, den sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="cfacc-121">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="cfacc-122">SIEM-Serverintegration in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cfacc-122">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="cfacc-123">Ein SIEM-Server kann Daten aus einer Vielzahl von Microsoft 365 Diensten und Anwendungen empfangen.</span><span class="sxs-lookup"><span data-stu-id="cfacc-123">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="cfacc-124">In der folgenden Tabelle sind mehrere Microsoft 365 Dienste und Anwendungen sowie SIEM-Servereingaben und Ressourcen aufgeführt, um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="cfacc-124">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

****

|<span data-ttu-id="cfacc-125">Microsoft 365 Dienst oder Anwendung</span><span class="sxs-lookup"><span data-stu-id="cfacc-125">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="cfacc-126">SIEM-Servereingaben/-methoden</span><span class="sxs-lookup"><span data-stu-id="cfacc-126">SIEM server inputs/methods</span></span>|<span data-ttu-id="cfacc-127">Ressourcen mit mehr Informationen</span><span class="sxs-lookup"><span data-stu-id="cfacc-127">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="cfacc-128">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="cfacc-128">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)|<span data-ttu-id="cfacc-129">Überwachungsprotokolle</span><span class="sxs-lookup"><span data-stu-id="cfacc-129">Audit logs</span></span>|[<span data-ttu-id="cfacc-130">SIEM-Integration in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="cfacc-130">SIEM integration with Microsoft Defender for Office 365</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="cfacc-131">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="cfacc-131">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)|<span data-ttu-id="cfacc-132">IN Azure gehosteter HTTPS-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="cfacc-132">HTTPS endpoint hosted in Azure</span></span> <p> <span data-ttu-id="cfacc-133">REST-API</span><span class="sxs-lookup"><span data-stu-id="cfacc-133">REST API</span></span>|[<span data-ttu-id="cfacc-134">Abrufen von Warnungen an Ihre SIEM-Tools</span><span class="sxs-lookup"><span data-stu-id="cfacc-134">Pull alerts to your SIEM tools</span></span>](../defender-endpoint/configure-siem.md)|
|[<span data-ttu-id="cfacc-135">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="cfacc-135">Microsoft Cloud App Security</span></span>](/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="cfacc-136">Protokollintegration</span><span class="sxs-lookup"><span data-stu-id="cfacc-136">Log integration</span></span>|[<span data-ttu-id="cfacc-137">SIEM-Integration in Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="cfacc-137">SIEM integration with Microsoft Cloud App Security</span></span>](/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="cfacc-138">Werfen Sie einen Blick auf [Azure Sentinel.](/azure/sentinel/overview)</span><span class="sxs-lookup"><span data-stu-id="cfacc-138">Take a look at [Azure Sentinel](/azure/sentinel/overview).</span></span> <span data-ttu-id="cfacc-139">Azure Sentinel enthält Connectors für Microsoft-Lösungen.</span><span class="sxs-lookup"><span data-stu-id="cfacc-139">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="cfacc-140">Diese Connectors sind sofort verfügbar und ermöglichen die Integration in Echtzeit.</span><span class="sxs-lookup"><span data-stu-id="cfacc-140">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="cfacc-141">Sie können Azure Sentinel mit Ihren Microsoft 365 Defender-Lösungen und Microsoft 365-Diensten verwenden, einschließlich Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security und mehr.</span><span class="sxs-lookup"><span data-stu-id="cfacc-141">You can use Azure Sentinel with your Microsoft 365 Defender solutions and Microsoft 365 services, including Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="cfacc-142">Überwachungsprotokollierung muss aktiviert sein</span><span class="sxs-lookup"><span data-stu-id="cfacc-142">Audit logging must be turned on</span></span>

<span data-ttu-id="cfacc-143">Stellen Sie sicher, dass die Überwachungsprotokollierung aktiviert ist, bevor Sie die SIEM-Serverintegration konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="cfacc-143">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="cfacc-144">Bei SharePoint Online-, OneDrive for Business- und Azure Active Directory ist [die Überwachungsprotokollierung im Microsoft 365 Defender-Portal aktiviert.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="cfacc-144">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Microsoft 365 Defender portal](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="cfacc-145">Informationen Exchange Online finden Sie unter Verwalten der [Postfachüberwachung.](../../compliance/enable-mailbox-auditing.md)</span><span class="sxs-lookup"><span data-stu-id="cfacc-145">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="cfacc-146">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="cfacc-146">More resources</span></span>

[<span data-ttu-id="cfacc-147">Integrieren von Sicherheitslösungen in Azure Defender</span><span class="sxs-lookup"><span data-stu-id="cfacc-147">Integrate security solutions in Azure Defender</span></span>](/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="cfacc-148">Integrieren von Sicherheits-API-Warnungen in Microsoft Graph in SIEM (Security Information &amp; Event Management)</span><span class="sxs-lookup"><span data-stu-id="cfacc-148">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](/graph/security-integration)