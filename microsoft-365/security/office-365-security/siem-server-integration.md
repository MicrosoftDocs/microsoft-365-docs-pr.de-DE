---
title: Integration von Siem-Servern in Microsoft 365-Dienste und-Anwendungen
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/15/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: Lesen Sie diesen Artikel, um einen Überblick über die Integration von Siem Server mit Microsoft 365 zu erhalten.
ms.openlocfilehash: bea6141022fef1275a7e291217f698f52613f170
ms.sourcegitcommit: d8d001c03c28c10bea005d1c9b5f4a8f393af706
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "38677508"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="f20c0-103">Integration von Siem-Servern in Microsoft 365-Dienste und-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="f20c0-103">SIEM server integration with Microsoft 365 services and applications</span></span>

## <a name="summary"></a><span data-ttu-id="f20c0-104">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="f20c0-104">Summary</span></span>

<span data-ttu-id="f20c0-105">Wenn Ihre Organisation einen Siem-Server (Security Information and Event Management) verwendet oder wenn Sie einen Siem-Server bald erhalten möchten, Fragen Sie sich möglicherweise, wie sich das in Microsoft 365 oder Office 365 integrieren lässt.</span><span class="sxs-lookup"><span data-stu-id="f20c0-105">If your organization is using a Security Information and Event Management (SIEM) server, or if you are planning to get a SIEM server soon, you might be wondering how that'll integrate with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="f20c0-106">Dieser Artikel enthält eine Liste der Ressourcen, die Sie zum Einrichten der Integration von Siem Server mit Ihren Microsoft 365-Diensten und-Anwendungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f20c0-106">This article provides a list of resources you can use to set up SIEM server integration with your Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="f20c0-107">Wenn Sie noch keinen Siem-Server haben und Ihre Optionen untersuchen, sollten Sie sich **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)** ansehen.</span><span class="sxs-lookup"><span data-stu-id="f20c0-107">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="f20c0-108">Benötige ich einen Siem-Server?</span><span class="sxs-lookup"><span data-stu-id="f20c0-108">Do I need a SIEM server?</span></span>

<span data-ttu-id="f20c0-109">Ob Sie einen Siem-Server benötigen, hängt von vielen Faktoren ab, beispielsweise von den Sicherheitsanforderungen Ihrer Organisation und dem Ort, an dem sich Ihre Daten befinden.</span><span class="sxs-lookup"><span data-stu-id="f20c0-109">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="f20c0-110">Microsoft 365 umfasst eine Vielzahl von Sicherheitsfeatures, die die Sicherheitsanforderungen vieler Organisationen erfüllen, ohne zusätzliche Server wie einen Siem-Server.</span><span class="sxs-lookup"><span data-stu-id="f20c0-110">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="f20c0-111">Einige Organisationen haben spezielle Umstände, die die Verwendung eines Siem-Servers erfordern.</span><span class="sxs-lookup"><span data-stu-id="f20c0-111">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="f20c0-112">Im Folgenden finden Sie einige Beispiele:</span><span class="sxs-lookup"><span data-stu-id="f20c0-112">Here are some examples:</span></span>

- <span data-ttu-id="f20c0-113">*Fabrikam* verfügt über einige Inhalte und Anwendungen vor Ort und einige in der Cloud (Sie verfügen über eine hybride Cloud-Bereitstellung).</span><span class="sxs-lookup"><span data-stu-id="f20c0-113">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="f20c0-114">Um Sicherheitsberichte über alle Inhalte und Anwendungen zu erhalten, hat Fabrikam einen Siem-Server implementiert.</span><span class="sxs-lookup"><span data-stu-id="f20c0-114">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span> 

- <span data-ttu-id="f20c0-115">*Contoso* ist eine Finanzdienstleistungsorganisation mit besonders strengen Sicherheitsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="f20c0-115">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="f20c0-116">Sie haben ihren Umgebungen einen Siem-Server hinzugefügt, um den zusätzlichen Sicherheitsschutz zu nutzen, den Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="f20c0-116">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="f20c0-117">Siem-Server Integration mit Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f20c0-117">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="f20c0-118">Ein Siem-Server kann Daten aus einer Vielzahl von Microsoft 365-Diensten und-Anwendungen empfangen.</span><span class="sxs-lookup"><span data-stu-id="f20c0-118">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="f20c0-119">In der folgenden Tabelle sind mehrere Microsoft 365-Dienste und-Anwendungen zusammen mit Siem Server-Eingaben und Ressourcen aufgeführt, um weitere Informationen zur Integration von Siem Server zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f20c0-119">The following table lists several Microsoft 365 services and applications along with SIEM server inputs, and resources to learn more about SIEM server integration.</span></span> 

| <span data-ttu-id="f20c0-120">Microsoft 365-Dienst oder-Anwendung</span><span class="sxs-lookup"><span data-stu-id="f20c0-120">Microsoft 365 Service or Application</span></span> | <span data-ttu-id="f20c0-121">Siem-Server Eingaben</span><span class="sxs-lookup"><span data-stu-id="f20c0-121">SIEM server inputs</span></span> | <span data-ttu-id="f20c0-122">Ressourcen mit mehr Informationen</span><span class="sxs-lookup"><span data-stu-id="f20c0-122">Resources to learn more</span></span> |
| --- | --- | --- |
| [<span data-ttu-id="f20c0-123">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f20c0-123">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)  | <span data-ttu-id="f20c0-124">Überwachungsprotokolle</span><span class="sxs-lookup"><span data-stu-id="f20c0-124">Audit logs</span></span> | [<span data-ttu-id="f20c0-125">Siem-Integration mit Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f20c0-125">SIEM integration with Office 365 Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md) |
| [<span data-ttu-id="f20c0-126">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f20c0-126">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/) | <span data-ttu-id="f20c0-127">In Azure gehosteter HTTPS-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f20c0-127">HTTPS endpoint hosted in Azure</span></span> <br/><span data-ttu-id="f20c0-128">REST-API</span><span class="sxs-lookup"><span data-stu-id="f20c0-128">REST API</span></span>| [<span data-ttu-id="f20c0-129">Abrufen von Benachrichtigungen an Ihre Siem-Tools</span><span class="sxs-lookup"><span data-stu-id="f20c0-129">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [<span data-ttu-id="f20c0-130">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f20c0-130">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | <span data-ttu-id="f20c0-131">Protokoll Integration</span><span class="sxs-lookup"><span data-stu-id="f20c0-131">Log integration</span></span> | [<span data-ttu-id="f20c0-132">Siem-Integration in Microsoft Cloud-App-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="f20c0-132">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem) |

> [!TIP]
> <span data-ttu-id="f20c0-133">Sehen Sie sich [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)an, der mit einer Reihe von Connectors für Microsoft-Lösungen ausgestattet ist, die sofort verfügbar sind und eine Echtzeitintegration bieten, einschließlich Microsoft Threat Protection-Lösungen und Microsoft 365-Quellen, einschließlich Office 365, Azure AD, Azure ATP und Microsoft Cloud-App-Sicherheit und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="f20c0-133">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview), which comes with a number of connectors for Microsoft solutions, available out of the box and providing real-time integration, including Microsoft Threat Protection solutions, and Microsoft 365 sources, including Office 365, Azure AD, Azure ATP, and Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="f20c0-134">Die Überwachungsprotokollierung muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="f20c0-134">Audit logging must be turned on</span></span>

<span data-ttu-id="f20c0-135">Stellen Sie sicher, dass die Überwachungsprotokollierung aktiviert ist, bevor Sie die Integration von Siem Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f20c0-135">Make sure audit logging is turned on before you configure SIEM server integration.</span></span> 

- <span data-ttu-id="f20c0-136">Für SharePoint Online, OneDrive für Unternehmen und Azure Active Directory [ist die Überwachungsprotokollierung im Security #a0 Compliance Center aktiviert](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span><span class="sxs-lookup"><span data-stu-id="f20c0-136">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span></span>

- <span data-ttu-id="f20c0-137">Für Exchange Online [ist die Überwachungsprotokollierung mit Windows PowerShell aktiviert](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span><span class="sxs-lookup"><span data-stu-id="f20c0-137">For Exchange Online, [audit logging is turned on with Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span></span>
 
## <a name="additional-resources"></a><span data-ttu-id="f20c0-138">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="f20c0-138">Additional resources</span></span>

[<span data-ttu-id="f20c0-139">Integrieren von Sicherheitslösungen im Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="f20c0-139">Integrate security solutions in Azure Security Center</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="f20c0-140">Integrieren von Sicherheits-API-Warnungen in Microsoft Graph in SIEM (Security Information &amp; Event Management)</span><span class="sxs-lookup"><span data-stu-id="f20c0-140">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)