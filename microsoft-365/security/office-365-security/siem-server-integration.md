---
title: SieM-Server-Integration in Microsoft 365-Dienste und -Anwendungen
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
description: Erhalten Sie eine Übersicht über die Integration von SieM-Servern (Security Information and Event Management) in Ihre Microsoft 365-Clouddienste und -Anwendungen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b4490d52cbd403bf4ce2cc3f3fb3c5a91c5646b9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290381"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="8e3fd-103">Integration von SieM-Servern (Security Information and Event Management) in Microsoft 365-Dienste und -Anwendungen</span><span class="sxs-lookup"><span data-stu-id="8e3fd-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

<span data-ttu-id="8e3fd-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="8e3fd-104">**Applies to**</span></span>
- [<span data-ttu-id="8e3fd-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8e3fd-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8e3fd-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="8e3fd-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="8e3fd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8e3fd-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a><span data-ttu-id="8e3fd-108">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="8e3fd-108">Summary</span></span>

<span data-ttu-id="8e3fd-109">Verwendet ihre Organisation einen SIEM-Server (Security Information and Event Management) oder plant sie dies?</span><span class="sxs-lookup"><span data-stu-id="8e3fd-109">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="8e3fd-110">Sie fragen sich vielleicht, wie es in Microsoft 365 oder Office 365 integriert wird.</span><span class="sxs-lookup"><span data-stu-id="8e3fd-110">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="8e3fd-111">Dieser Artikel enthält eine Liste der Ressourcen, die Sie verwenden können, um Ihren SIEM-Server in Microsoft 365-Dienste und -Anwendungen zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="8e3fd-111">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="8e3fd-112">Wenn Sie noch keinen SIEM-Server haben und Ihre Optionen erkunden, ziehen Sie **[Microsoft Azure Sentinel in Betracht.](https://docs.microsoft.com/azure/sentinel/overview)**</span><span class="sxs-lookup"><span data-stu-id="8e3fd-112">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="8e3fd-113">Benötigen Sie einen SIEM-Server?</span><span class="sxs-lookup"><span data-stu-id="8e3fd-113">Do I need a SIEM server?</span></span>

<span data-ttu-id="8e3fd-114">Ob Sie einen SIEM-Server benötigen, hängt von vielen Faktoren ab, z. B. den Sicherheitsanforderungen Ihrer Organisation und dem Ort, an dem sich Ihre Daten befinden.</span><span class="sxs-lookup"><span data-stu-id="8e3fd-114">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="8e3fd-115">Microsoft 365 umfasst eine Vielzahl von Sicherheitsfeatures, die die Sicherheitsanforderungen vieler Organisationen ohne zusätzliche Server erfüllen, z. B. einen SIEM-Server.</span><span class="sxs-lookup"><span data-stu-id="8e3fd-115">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="8e3fd-116">Einige Organisationen haben besondere Umstände, die die Verwendung eines SIEM-Servers erfordern.</span><span class="sxs-lookup"><span data-stu-id="8e3fd-116">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="8e3fd-117">Im Folgenden finden Sie einige Beispiele:</span><span class="sxs-lookup"><span data-stu-id="8e3fd-117">Here are some examples:</span></span>

- <span data-ttu-id="8e3fd-118">*Fabrikam* verfügt über lokale Inhalte und Anwendungen und einige in der Cloud (sie verfügen über eine Hybrid-Cloud-Bereitstellung).</span><span class="sxs-lookup"><span data-stu-id="8e3fd-118">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="8e3fd-119">Um Sicherheitsberichte für alle Inhalte und Anwendungen zu erhalten, hat Fabrikam einen SIEM-Server implementiert.</span><span class="sxs-lookup"><span data-stu-id="8e3fd-119">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="8e3fd-120">*Contoso* ist ein Finanzdienstleister, der besonders strenge Sicherheitsanforderungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="8e3fd-120">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="8e3fd-121">Sie haben ihrer Umgebung einen SIEM-Server hinzugefügt, um den zusätzlichen Sicherheitsschutz zu nutzen, den sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="8e3fd-121">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="8e3fd-122">SieM-Server-Integration in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8e3fd-122">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="8e3fd-123">Ein SIEM-Server kann Daten aus einer Vielzahl von Microsoft 365-Diensten und -Anwendungen empfangen.</span><span class="sxs-lookup"><span data-stu-id="8e3fd-123">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="8e3fd-124">In der folgenden Tabelle sind mehrere Microsoft 365-Dienste und -Anwendungen sowie die Eingaben und Ressourcen des SIEM-Servers aufgeführt, um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="8e3fd-124">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

****

|<span data-ttu-id="8e3fd-125">Microsoft 365-Dienst oder -Anwendung</span><span class="sxs-lookup"><span data-stu-id="8e3fd-125">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="8e3fd-126">Eingaben/Methoden des SIEM-Servers</span><span class="sxs-lookup"><span data-stu-id="8e3fd-126">SIEM server inputs/methods</span></span>|<span data-ttu-id="8e3fd-127">Ressourcen mit mehr Informationen</span><span class="sxs-lookup"><span data-stu-id="8e3fd-127">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="8e3fd-128">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="8e3fd-128">Microsoft Defender for Office 365</span></span>](office-365-atp.md)|<span data-ttu-id="8e3fd-129">Überwachungsprotokolle</span><span class="sxs-lookup"><span data-stu-id="8e3fd-129">Audit logs</span></span>|[<span data-ttu-id="8e3fd-130">SIEM-Integration in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="8e3fd-130">SIEM integration with Microsoft Defender for Office 365</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="8e3fd-131">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="8e3fd-131">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)|<span data-ttu-id="8e3fd-132">In Azure gehosteter HTTPS-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="8e3fd-132">HTTPS endpoint hosted in Azure</span></span> <p> <span data-ttu-id="8e3fd-133">REST-API</span><span class="sxs-lookup"><span data-stu-id="8e3fd-133">REST API</span></span>|[<span data-ttu-id="8e3fd-134">Ziehen von Warnungen an Ihre SIEM-Tools</span><span class="sxs-lookup"><span data-stu-id="8e3fd-134">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[<span data-ttu-id="8e3fd-135">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="8e3fd-135">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="8e3fd-136">Protokollintegration</span><span class="sxs-lookup"><span data-stu-id="8e3fd-136">Log integration</span></span>|[<span data-ttu-id="8e3fd-137">SIEM-Integration in Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="8e3fd-137">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="8e3fd-138">Sehen Sie sich [Azure Sentinel an.](https://docs.microsoft.com/azure/sentinel/overview)</span><span class="sxs-lookup"><span data-stu-id="8e3fd-138">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span></span> <span data-ttu-id="8e3fd-139">Azure Sentinel enthält Connectors für Microsoft-Lösungen.</span><span class="sxs-lookup"><span data-stu-id="8e3fd-139">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="8e3fd-140">Diese Connectors sind sofort verfügbar und ermöglichen die Integration in Echtzeit.</span><span class="sxs-lookup"><span data-stu-id="8e3fd-140">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="8e3fd-141">Sie können Azure Sentinel mit Ihren Microsoft 365 Defender-Lösungen und Microsoft 365-Diensten verwenden, einschließlich Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security und mehr.</span><span class="sxs-lookup"><span data-stu-id="8e3fd-141">You can use Azure Sentinel with your Microsoft 365 Defender solutions and Microsoft 365 services, including Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="8e3fd-142">Überwachungsprotokollierung muss aktiviert sein</span><span class="sxs-lookup"><span data-stu-id="8e3fd-142">Audit logging must be turned on</span></span>

<span data-ttu-id="8e3fd-143">Stellen Sie sicher, dass die Überwachungsprotokollierung aktiviert ist, bevor Sie die SieM-Serverintegration konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8e3fd-143">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="8e3fd-144">Für SharePoint Online, OneDrive for Business und Azure Active Directory ist die Überwachungsprotokollierung im [Security & Compliance Center aktiviert.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="8e3fd-144">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="8e3fd-145">Informationen zu Exchange Online finden Sie unter [Verwalten der Postfachüberwachung.](../../compliance/enable-mailbox-auditing.md)</span><span class="sxs-lookup"><span data-stu-id="8e3fd-145">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="8e3fd-146">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="8e3fd-146">More resources</span></span>

[<span data-ttu-id="8e3fd-147">Integrieren von Sicherheitslösungen in Azure Defender</span><span class="sxs-lookup"><span data-stu-id="8e3fd-147">Integrate security solutions in Azure Defender</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="8e3fd-148">Integrieren von Sicherheits-API-Warnungen in Microsoft Graph in SIEM (Security Information &amp; Event Management)</span><span class="sxs-lookup"><span data-stu-id="8e3fd-148">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)
