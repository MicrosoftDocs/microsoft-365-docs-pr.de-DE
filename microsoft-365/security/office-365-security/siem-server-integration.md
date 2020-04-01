---
title: " Integration von Security Information and Event Management (SIEM) Server in Microsoft 365-Dienste und-Anwendungen"
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: Erhalten Sie einen Überblick über die Integration von Security Information and Event Management (SIEM) Server mit Ihren Microsoft 365 Cloud-Diensten und-Anwendungen.
ms.openlocfilehash: a4ef144d02ebf0481481861c3dfa60a43b4f3ace
ms.sourcegitcommit: a7b2cd892cb65a61ee246268e1af2f8b9e526f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2020
ms.locfileid: "43081220"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="d75c0-103">Integration von Security Information and Event Management (SIEM) Server in Microsoft 365-Dienste und-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="d75c0-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

## <a name="summary"></a><span data-ttu-id="d75c0-104">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="d75c0-104">Summary</span></span>

<span data-ttu-id="d75c0-105">Verwendet oder plant Ihre Organisation einen Siem-Server (Security Information and Event Management)?</span><span class="sxs-lookup"><span data-stu-id="d75c0-105">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="d75c0-106">Möglicherweise Fragen Sie sich, wie es in Microsoft 365 oder Office 365 integriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="d75c0-106">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="d75c0-107">Dieser Artikel enthält eine Liste der Ressourcen, die Sie zur Integration Ihres Siem-Servers in Microsoft 365-Dienste und-Anwendungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="d75c0-107">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="d75c0-108">Wenn Sie noch keinen Siem-Server haben und Ihre Optionen untersuchen, sollten Sie sich **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)** ansehen.</span><span class="sxs-lookup"><span data-stu-id="d75c0-108">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="d75c0-109">Benötige ich einen Siem-Server?</span><span class="sxs-lookup"><span data-stu-id="d75c0-109">Do I need a SIEM server?</span></span>

<span data-ttu-id="d75c0-110">Ob Sie einen Siem-Server benötigen, hängt von vielen Faktoren ab, beispielsweise von den Sicherheitsanforderungen Ihrer Organisation und dem Ort, an dem sich Ihre Daten befinden.</span><span class="sxs-lookup"><span data-stu-id="d75c0-110">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="d75c0-111">Microsoft 365 umfasst eine Vielzahl von Sicherheitsfeatures, die die Sicherheitsanforderungen vieler Organisationen erfüllen, ohne zusätzliche Server wie einen Siem-Server.</span><span class="sxs-lookup"><span data-stu-id="d75c0-111">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="d75c0-112">Einige Organisationen haben spezielle Umstände, die die Verwendung eines Siem-Servers erfordern.</span><span class="sxs-lookup"><span data-stu-id="d75c0-112">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="d75c0-113">Im Folgenden finden Sie einige Beispiele:</span><span class="sxs-lookup"><span data-stu-id="d75c0-113">Here are some examples:</span></span>

- <span data-ttu-id="d75c0-114">*Fabrikam* verfügt über einige Inhalte und Anwendungen vor Ort und einige in der Cloud (Sie verfügen über eine hybride Cloud-Bereitstellung).</span><span class="sxs-lookup"><span data-stu-id="d75c0-114">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="d75c0-115">Um Sicherheitsberichte über alle Inhalte und Anwendungen zu erhalten, hat Fabrikam einen Siem-Server implementiert.</span><span class="sxs-lookup"><span data-stu-id="d75c0-115">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="d75c0-116">*Contoso* ist eine Finanzdienstleistungsorganisation mit besonders strengen Sicherheitsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="d75c0-116">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="d75c0-117">Sie haben ihren Umgebungen einen Siem-Server hinzugefügt, um den zusätzlichen Sicherheitsschutz zu nutzen, den Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="d75c0-117">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="d75c0-118">Siem-Server Integration mit Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d75c0-118">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="d75c0-119">Ein Siem-Server kann Daten aus einer Vielzahl von Microsoft 365-Diensten und-Anwendungen empfangen.</span><span class="sxs-lookup"><span data-stu-id="d75c0-119">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="d75c0-120">In der folgenden Tabelle sind mehrere Microsoft 365-Dienste und-Anwendungen zusammen mit Siem Server-Eingaben und Ressourcen aufgeführt, um weitere Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d75c0-120">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

||||
|---|---|---|
|<span data-ttu-id="d75c0-121">**Microsoft 365-Dienst oder-Anwendung**</span><span class="sxs-lookup"><span data-stu-id="d75c0-121">**Microsoft 365 Service or Application**</span></span>|<span data-ttu-id="d75c0-122">**Siem-Server-Eingänge/-Methoden**</span><span class="sxs-lookup"><span data-stu-id="d75c0-122">**SIEM server inputs/methods**</span></span>|<span data-ttu-id="d75c0-123">**Ressourcen mit mehr Informationen**</span><span class="sxs-lookup"><span data-stu-id="d75c0-123">**Resources to learn more**</span></span>|
|[<span data-ttu-id="d75c0-124">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d75c0-124">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)|<span data-ttu-id="d75c0-125">Überwachungsprotokolle</span><span class="sxs-lookup"><span data-stu-id="d75c0-125">Audit logs</span></span>|[<span data-ttu-id="d75c0-126">Siem-Integration mit Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d75c0-126">SIEM integration with Office 365 Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="d75c0-127">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d75c0-127">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)|<span data-ttu-id="d75c0-128">In Azure gehosteter HTTPS-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="d75c0-128">HTTPS endpoint hosted in Azure</span></span> <br/><span data-ttu-id="d75c0-129">REST-API</span><span class="sxs-lookup"><span data-stu-id="d75c0-129">REST API</span></span>|[<span data-ttu-id="d75c0-130">Abrufen von Benachrichtigungen an Ihre Siem-Tools</span><span class="sxs-lookup"><span data-stu-id="d75c0-130">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[<span data-ttu-id="d75c0-131">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d75c0-131">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="d75c0-132">Protokoll Integration</span><span class="sxs-lookup"><span data-stu-id="d75c0-132">Log integration</span></span>|[<span data-ttu-id="d75c0-133">Siem-Integration in Microsoft Cloud-App-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d75c0-133">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="d75c0-134">Schauen Sie sich [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)an.</span><span class="sxs-lookup"><span data-stu-id="d75c0-134">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span></span> <span data-ttu-id="d75c0-135">Azure Sentinel verfügt über Connectors für Microsoft-Lösungen.</span><span class="sxs-lookup"><span data-stu-id="d75c0-135">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="d75c0-136">Diese Konnektoren sind "Out-of-the-Box" verfügbar und bieten eine Echtzeitintegration.</span><span class="sxs-lookup"><span data-stu-id="d75c0-136">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="d75c0-137">Sie können Azure Sentinel mit Ihren Microsoft Threat Protection-Lösungen und Microsoft 365-Diensten verwenden, darunter Office 365, Azure AD, Azure ATP, Microsoft Cloud App Security und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="d75c0-137">You can use Azure Sentinel with your Microsoft Threat Protection solutions and Microsoft 365 services, including Office 365, Azure AD, Azure ATP, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="d75c0-138">Die Überwachungsprotokollierung muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="d75c0-138">Audit logging must be turned on</span></span>

<span data-ttu-id="d75c0-139">Stellen Sie sicher, dass die Überwachungsprotokollierung aktiviert ist, bevor Sie die Integration von Siem Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d75c0-139">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="d75c0-140">Für SharePoint Online, OneDrive für Unternehmen und Azure Active Directory [ist die Überwachungsprotokollierung im Security & Compliance Center aktiviert](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="d75c0-140">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="d75c0-141">Informationen zu Exchange Online finden Sie unter [Verwalten der postfachüberwachung](../../compliance/enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="d75c0-141">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="d75c0-142">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="d75c0-142">More resources</span></span>

[<span data-ttu-id="d75c0-143">Integrieren von Sicherheitslösungen im Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="d75c0-143">Integrate security solutions in Azure Security Center</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="d75c0-144">Integrieren von Sicherheits-API-Warnungen in Microsoft Graph in SIEM (Security Information &amp; Event Management)</span><span class="sxs-lookup"><span data-stu-id="d75c0-144">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)
