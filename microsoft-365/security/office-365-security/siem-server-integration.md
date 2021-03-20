---
title: SIEM-Serverintegration in Microsoft 365-Dienste und -Anwendungen
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
description: Verschaffen Sie sich einen Überblick über die Integration von SieM-Servern (Security Information and Event Management) in Ihre Microsoft 365-Clouddienste und -Anwendungen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 21aaad71f40a01a3bea2f9535d1c3256ae667bae
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916586"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="76088-103">Integration von Sicherheitsinformationen und Ereignisverwaltungsservern in Microsoft 365-Dienste und -Anwendungen</span><span class="sxs-lookup"><span data-stu-id="76088-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

<span data-ttu-id="76088-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="76088-104">**Applies to**</span></span>
- [<span data-ttu-id="76088-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="76088-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="76088-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="76088-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="76088-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="76088-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a><span data-ttu-id="76088-108">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="76088-108">Summary</span></span>

<span data-ttu-id="76088-109">Verwendet oder plant Ihre Organisation, einen Sicherheitsinformations- und Ereignisverwaltungsserver (Security Information and Event Management, SIEM) zu erhalten?</span><span class="sxs-lookup"><span data-stu-id="76088-109">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="76088-110">Sie fragen sich vielleicht, wie es in Microsoft 365 oder Office 365 integriert wird.</span><span class="sxs-lookup"><span data-stu-id="76088-110">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="76088-111">Dieser Artikel enthält eine Liste der Ressourcen, die Sie verwenden können, um Ihren SIEM-Server in Microsoft 365-Dienste und -Anwendungen zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="76088-111">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="76088-112">Wenn Sie noch keinen SIEM-Server haben und Ihre Optionen erkunden, ziehen Sie **[Microsoft Azure Sentinel in Betracht.](/azure/sentinel/overview)**</span><span class="sxs-lookup"><span data-stu-id="76088-112">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="76088-113">Benötigen Sie einen SIEM-Server?</span><span class="sxs-lookup"><span data-stu-id="76088-113">Do I need a SIEM server?</span></span>

<span data-ttu-id="76088-114">Ob Sie einen SIEM-Server benötigen, hängt von vielen Faktoren ab, z. B. den Sicherheitsanforderungen Ihrer Organisation und dem Ort, an dem Sich Ihre Daten befinden.</span><span class="sxs-lookup"><span data-stu-id="76088-114">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="76088-115">Microsoft 365 umfasst eine Vielzahl von Sicherheitsfeatures, die die Sicherheitsanforderungen vieler Organisationen ohne zusätzliche Server erfüllen, z. B. einen SIEM-Server.</span><span class="sxs-lookup"><span data-stu-id="76088-115">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="76088-116">Einige Organisationen haben spezielle Umstände, die die Verwendung eines SIEM-Servers erfordern.</span><span class="sxs-lookup"><span data-stu-id="76088-116">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="76088-117">Im Folgenden finden Sie einige Beispiele:</span><span class="sxs-lookup"><span data-stu-id="76088-117">Here are some examples:</span></span>

- <span data-ttu-id="76088-118">*Fabrikam* verfügt über einige Inhalte und Anwendungen lokal und einige in der Cloud (sie verfügen über eine Hybrid-Cloud-Bereitstellung).</span><span class="sxs-lookup"><span data-stu-id="76088-118">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="76088-119">Um Sicherheitsberichte für alle Inhalte und Anwendungen zu erhalten, hat Fabrikam einen SIEM-Server implementiert.</span><span class="sxs-lookup"><span data-stu-id="76088-119">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="76088-120">*Contoso* ist eine Finanzdienstleisterorganisation, die besonders strenge Sicherheitsanforderungen hat.</span><span class="sxs-lookup"><span data-stu-id="76088-120">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="76088-121">Sie haben ihrer Umgebung einen SIEM-Server hinzugefügt, um den zusätzlichen Sicherheitsschutz zu nutzen, den sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="76088-121">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="76088-122">SIEM-Serverintegration in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="76088-122">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="76088-123">Ein SIEM-Server kann Daten aus einer Vielzahl von Microsoft 365-Diensten und -Anwendungen empfangen.</span><span class="sxs-lookup"><span data-stu-id="76088-123">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="76088-124">In der folgenden Tabelle sind verschiedene Microsoft 365-Dienste und -Anwendungen sowie SIEM-Servereingaben und -ressourcen aufgeführt, um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="76088-124">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

****

|<span data-ttu-id="76088-125">Microsoft 365-Dienst oder -Anwendung</span><span class="sxs-lookup"><span data-stu-id="76088-125">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="76088-126">EINGABEN/Methoden des SIEM-Servers</span><span class="sxs-lookup"><span data-stu-id="76088-126">SIEM server inputs/methods</span></span>|<span data-ttu-id="76088-127">Ressourcen mit mehr Informationen</span><span class="sxs-lookup"><span data-stu-id="76088-127">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="76088-128">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="76088-128">Microsoft Defender for Office 365</span></span>](office-365-atp.md)|<span data-ttu-id="76088-129">Überwachungsprotokolle</span><span class="sxs-lookup"><span data-stu-id="76088-129">Audit logs</span></span>|[<span data-ttu-id="76088-130">SIEM-Integration in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="76088-130">SIEM integration with Microsoft Defender for Office 365</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="76088-131">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="76088-131">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)|<span data-ttu-id="76088-132">IN Azure gehosteter HTTPS-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="76088-132">HTTPS endpoint hosted in Azure</span></span> <p> <span data-ttu-id="76088-133">REST-API</span><span class="sxs-lookup"><span data-stu-id="76088-133">REST API</span></span>|[<span data-ttu-id="76088-134">Ziehen von Warnungen an Ihre SIEM-Tools</span><span class="sxs-lookup"><span data-stu-id="76088-134">Pull alerts to your SIEM tools</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[<span data-ttu-id="76088-135">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="76088-135">Microsoft Cloud App Security</span></span>](/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="76088-136">Protokollintegration</span><span class="sxs-lookup"><span data-stu-id="76088-136">Log integration</span></span>|[<span data-ttu-id="76088-137">SIEM-Integration in Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="76088-137">SIEM integration with Microsoft Cloud App Security</span></span>](/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="76088-138">Sehen Sie sich [Azure Sentinel an.](/azure/sentinel/overview)</span><span class="sxs-lookup"><span data-stu-id="76088-138">Take a look at [Azure Sentinel](/azure/sentinel/overview).</span></span> <span data-ttu-id="76088-139">Azure Sentinel bietet Connectors für Microsoft-Lösungen.</span><span class="sxs-lookup"><span data-stu-id="76088-139">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="76088-140">Diese Connectors sind "sofort verfügbar" und ermöglichen die Echtzeitintegration.</span><span class="sxs-lookup"><span data-stu-id="76088-140">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="76088-141">Sie können Azure Sentinel mit Ihren Microsoft 365 Defender-Lösungen und Microsoft 365-Diensten verwenden, einschließlich Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security und mehr.</span><span class="sxs-lookup"><span data-stu-id="76088-141">You can use Azure Sentinel with your Microsoft 365 Defender solutions and Microsoft 365 services, including Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="76088-142">Überwachungsprotokollierung muss aktiviert sein</span><span class="sxs-lookup"><span data-stu-id="76088-142">Audit logging must be turned on</span></span>

<span data-ttu-id="76088-143">Stellen Sie sicher, dass die Überwachungsprotokollierung aktiviert ist, bevor Sie die SIEM-Serverintegration konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="76088-143">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="76088-144">Für SharePoint Online, OneDrive for Business und Azure Active Directory ist die Überwachungsprotokollierung im [Security & Compliance Center aktiviert.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="76088-144">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="76088-145">Informationen zu Exchange Online finden Sie unter [Verwalten der Postfachüberwachung](../../compliance/enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="76088-145">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="76088-146">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="76088-146">More resources</span></span>

[<span data-ttu-id="76088-147">Integrieren von Sicherheitslösungen in Azure Defender</span><span class="sxs-lookup"><span data-stu-id="76088-147">Integrate security solutions in Azure Defender</span></span>](/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="76088-148">Integrieren von Sicherheits-API-Warnungen in Microsoft Graph in SIEM (Security Information &amp; Event Management)</span><span class="sxs-lookup"><span data-stu-id="76088-148">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](/graph/security-integration)