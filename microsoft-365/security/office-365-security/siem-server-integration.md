---
title: Siem-Server Integration mit Microsoft 365
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 06/17/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: 'Zusammenfassung: Lesen Sie diesen Artikel, um einen Überblick über die Integration von Siem Server mit Microsoft 365 zu erhalten.'
ms.openlocfilehash: 97f1c1d1f1862d140e014b4460ac9f40cb1934bb
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082644"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="9792a-103">Integration von Siem-Servern in Microsoft 365-Dienste und-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="9792a-103">SIEM server integration with Microsoft 365 services and applications</span></span>

## <a name="overview"></a><span data-ttu-id="9792a-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="9792a-104">Overview</span></span>

<span data-ttu-id="9792a-105">Wenn Ihre Organisation einen Siem-Server (Security Information and Event Management) verwendet oder wenn Sie einen Siem-Server bald erhalten möchten, Fragen Sie sich möglicherweise, wie sich das in Ihren Microsoft 365, einschließlich Office 365 E5, integrieren lässt.</span><span class="sxs-lookup"><span data-stu-id="9792a-105">If your organization is using a Security Information and Event Management (SIEM) server, or if you are planning to get a SIEM server soon, you might be wondering how that'll integrate with your Microsoft 365, including Office 365 E5.</span></span> <span data-ttu-id="9792a-106">Ob Sie einen Siem-Server benötigen, hängt von vielen Faktoren ab, beispielsweise von den Sicherheitsanforderungen Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="9792a-106">Whether you need a SIEM server depends on many factors, such as your organization's security requirements.</span></span> <span data-ttu-id="9792a-107">Microsoft 365 bietet eine Vielzahl von Sicherheitsfeatures; Wenn Ihre Organisation jedoch Inhalte und Anwendungen lokal und in der Cloud hat (wie bei einer hybriden Cloud-Bereitstellung), können Sie einen Siem-Server für zusätzlichen Schutz verwenden.</span><span class="sxs-lookup"><span data-stu-id="9792a-107">Microsoft 365 offers a variety of security features; however, if your organization has content and applications on premises and in the cloud (as in the case of a hybrid cloud deployment), you might consider adding a SIEM server for extra protection.</span></span> <span data-ttu-id="9792a-108">Wenn Ihre Organisation besonders strenge Sicherheitsanforderungen erfüllt, müssen Sie möglicherweise einen Siem-Server zu Ihrer Umgebung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9792a-108">Or, if your organization has particularly stringent security requirements you must meet, you might consider adding a SIEM server to your environment.</span></span>

## <a name="siem-server-integration-microsoft-365"></a><span data-ttu-id="9792a-109">Siem-Server Integration Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9792a-109">SIEM server integration Microsoft 365</span></span>

<span data-ttu-id="9792a-110">Ein Siem-Server kann Daten aus einer Vielzahl von Microsoft 365-Diensten und-Anwendungen empfangen.</span><span class="sxs-lookup"><span data-stu-id="9792a-110">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="9792a-111">In der folgenden Tabelle sind mehrere Microsoft 365-Dienste und-Anwendungen zusammen mit Siem Server-Eingaben aufgeführt, und weitere Informationen zur Integration von Siem Server finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="9792a-111">The following table lists several Microsoft 365 services and applications along with SIEM server inputs and where to go to learn more about SIEM server integration.</span></span> 

| <span data-ttu-id="9792a-112">Microsoft 365-Dienst oder-Anwendung</span><span class="sxs-lookup"><span data-stu-id="9792a-112">Microsoft 365 Service or Application</span></span> | <span data-ttu-id="9792a-113">Siem-Server Eingaben</span><span class="sxs-lookup"><span data-stu-id="9792a-113">SIEM server inputs</span></span> | <span data-ttu-id="9792a-114">Ressourcen für weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9792a-114">Resources to learn more</span></span> |
| --- | --- | --- |
| [<span data-ttu-id="9792a-115">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="9792a-115">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md) <br/><span data-ttu-id="9792a-116">oder</span><span class="sxs-lookup"><span data-stu-id="9792a-116">or</span></span><br/>[<span data-ttu-id="9792a-117">Informationen zu Bedrohungen in Office 365</span><span class="sxs-lookup"><span data-stu-id="9792a-117">Office 365 Threat Intelligence</span></span>](office-365-ti.md) | <span data-ttu-id="9792a-118">Überwachungsprotokolle</span><span class="sxs-lookup"><span data-stu-id="9792a-118">Audit logs</span></span> | [<span data-ttu-id="9792a-119">Siem-Integration mit Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="9792a-119">SIEM integration with Office 365 Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md) |
| [<span data-ttu-id="9792a-120">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="9792a-120">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | <span data-ttu-id="9792a-121">Protokoll Integration</span><span class="sxs-lookup"><span data-stu-id="9792a-121">Log integration</span></span> | [<span data-ttu-id="9792a-122">Siem-Integration in Microsoft Cloud-App-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="9792a-122">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem) |
| [<span data-ttu-id="9792a-123">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="9792a-123">Microsoft Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/) | <span data-ttu-id="9792a-124">Protokoll Integration</span><span class="sxs-lookup"><span data-stu-id="9792a-124">Log integration</span></span> | [<span data-ttu-id="9792a-125">Abrufen von Benachrichtigungen an Ihre Siem-Tools</span><span class="sxs-lookup"><span data-stu-id="9792a-125">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| <span data-ttu-id="9792a-126">[Azure-Sicherheits Center](https://docs.microsoft.com/azure/security-center/security-center-intro) (Bedrohungsschutz und Bedrohungserkennung)</span><span class="sxs-lookup"><span data-stu-id="9792a-126">[Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-intro) (Threat Protection and Threat Detection)</span></span> | <span data-ttu-id="9792a-127">Warnungen</span><span class="sxs-lookup"><span data-stu-id="9792a-127">Alerts</span></span> | [<span data-ttu-id="9792a-128">Azure Security Data Export to Siem-Pipeline Configuration – Vorschau</span><span class="sxs-lookup"><span data-stu-id="9792a-128">Azure Security data export to SIEM - Pipeline Configuration - Preview</span></span>](https://docs.microsoft.com/azure/security-center/security-center-export-data-to-siem) |
|[<span data-ttu-id="9792a-129">Azure Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="9792a-129">Azure Advanced Threat Analytics</span></span>](https://docs.microsoft.com/azure/security/azure-threat-detection) | <span data-ttu-id="9792a-130">Azure-Monitor</span><span class="sxs-lookup"><span data-stu-id="9792a-130">Azure Monitor</span></span> | [<span data-ttu-id="9792a-131">Blog Verwenden von Azure Monitor zur Integration in Siem-Tools</span><span class="sxs-lookup"><span data-stu-id="9792a-131">(Blog) Use Azure Monitor to integrate with SIEM tools</span></span>](https://azure.microsoft.com/blog/use-azure-monitor-to-integrate-with-siem-tools) |
|[<span data-ttu-id="9792a-132">Azure Active Directory Identity Protection</span><span class="sxs-lookup"><span data-stu-id="9792a-132">Azure Active Directory Identity Protection</span></span>](https://docs.microsoft.com/azure/active-directory/identity-protection/overview) |<span data-ttu-id="9792a-133">Protokoll Integration</span><span class="sxs-lookup"><span data-stu-id="9792a-133">Log integration</span></span> |[<span data-ttu-id="9792a-134">Integrieren von Sicherheits-API-Warnungen in Microsoft Graph in SIEM (Security Information &amp; Event Management)</span><span class="sxs-lookup"><span data-stu-id="9792a-134">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-siemintegration) |


## <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="9792a-135">Die Überwachungsprotokollierung muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="9792a-135">Audit logging must be turned on</span></span>

<span data-ttu-id="9792a-136">Stellen Sie sicher, dass die Überwachungsprotokollierung aktiviert ist, bevor Sie die Integration von Siem Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9792a-136">Make sure audit logging is turned on before you configure SIEM server integration.</span></span> 

- <span data-ttu-id="9792a-137">Für SharePoint Online, OneDrive für Unternehmen und Azure Active Directory [ist die Überwachungsprotokollierung im Security #a0 Compliance Center aktiviert](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span><span class="sxs-lookup"><span data-stu-id="9792a-137">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span></span>

- <span data-ttu-id="9792a-138">Für Exchange Online [ist die Überwachungsprotokollierung mit Windows PowerShell aktiviert](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span><span class="sxs-lookup"><span data-stu-id="9792a-138">For Exchange Online, [audit logging is turned on with Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span></span>
 
## <a name="see-also"></a><span data-ttu-id="9792a-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9792a-139">See Also</span></span>

[<span data-ttu-id="9792a-140">Cloudakzeptanz und Hybridlösungen</span><span class="sxs-lookup"><span data-stu-id="9792a-140">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[<span data-ttu-id="9792a-141">Testumgebungsanleitungen (TLGs) zur Cloudakzeptanz</span><span class="sxs-lookup"><span data-stu-id="9792a-141">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)


