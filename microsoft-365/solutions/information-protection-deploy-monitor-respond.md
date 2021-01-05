---
title: Überwachen und reagieren auf Datenschutz Vorfälle in Ihrer Organisation
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 01/04/2021
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Verwenden Sie Überwachungs-und Warnungsrichtlinien sowie Anforderungen von Datensubjekten zur Überwachung und Reaktion auf personenbezogene Daten Vorfälle.
ms.openlocfilehash: 3ae0f2a6528f6188500c7cee7732c6447013eaa6
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749587"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a><span data-ttu-id="3a7a2-103">Überwachen und reagieren auf Datenschutz Vorfälle in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="3a7a2-103">Monitor and respond to data privacy incidents in your organization</span></span>

<span data-ttu-id="3a7a2-104">Microsoft 365-Funktionen stehen Ihnen zur Überwachung, Untersuchung und Reaktion auf Datenschutz Vorfälle in Ihrer Organisation zur Verfügung, wenn Sie verwandte Funktionen einbringen.</span><span class="sxs-lookup"><span data-stu-id="3a7a2-104">Microsoft 365 features are available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> <span data-ttu-id="3a7a2-105">Es kann auch wichtig sein, Prozesse, Verfahren und andere Dokumentationen für diese zu untersuchen, um die Einhaltung von Regulierungsstellen zu demonstrieren.</span><span class="sxs-lookup"><span data-stu-id="3a7a2-105">Having processes, procedures, and other documentation for each of these may also be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="3a7a2-106">Zu diesen zählen:</span><span class="sxs-lookup"><span data-stu-id="3a7a2-106">These include:</span></span> 

- <span data-ttu-id="3a7a2-107">Überwachungs-und Warnungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="3a7a2-107">Auditing and alert policies</span></span>
- <span data-ttu-id="3a7a2-108">Anforderungen von Datensubjekten (einschließlich Inhaltssuche und eDiscovery)</span><span class="sxs-lookup"><span data-stu-id="3a7a2-108">Data subject requests (including content search and eDiscovery)</span></span>
- <span data-ttu-id="3a7a2-109">Zusätzliche Ermittlungs Tools und Berichte</span><span class="sxs-lookup"><span data-stu-id="3a7a2-109">Additional investigative tools and reporting</span></span>

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a><span data-ttu-id="3a7a2-110">Datenschutzbestimmungen, die sich auf die Verwendung von Überwachungs-und Antwort Tools auswirken</span><span class="sxs-lookup"><span data-stu-id="3a7a2-110">Data privacy regulations impacting the use of monitoring and response tools</span></span>

<span data-ttu-id="3a7a2-111">Im folgenden finden Sie eine Beispielliste der Datenschutzbestimmungen, die sich möglicherweise auf die Steuerelemente für die Informationssteuerung beziehen:</span><span class="sxs-lookup"><span data-stu-id="3a7a2-111">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="3a7a2-112">LGPD-Artikel 46</span><span class="sxs-lookup"><span data-stu-id="3a7a2-112">LGPD Article 46</span></span>
- <span data-ttu-id="3a7a2-113">LGPD-Artikel 48</span><span class="sxs-lookup"><span data-stu-id="3a7a2-113">LGPD Article 48</span></span>
- <span data-ttu-id="3a7a2-114">Dsgvo-Artikel (5) (1) (f)</span><span class="sxs-lookup"><span data-stu-id="3a7a2-114">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="3a7a2-115">Dsgvo-Artikel (15) (1) (e)</span><span class="sxs-lookup"><span data-stu-id="3a7a2-115">GDPR Article (15)(1)(e)</span></span>
- <span data-ttu-id="3a7a2-116">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="3a7a2-116">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="3a7a2-117">164.308 (a) (1) (II) (D))</span><span class="sxs-lookup"><span data-stu-id="3a7a2-117">164.308(a)(1)(ii)(D))</span></span>
- <span data-ttu-id="3a7a2-118">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="3a7a2-118">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="3a7a2-119">164.308(a)(6)(ii)</span><span class="sxs-lookup"><span data-stu-id="3a7a2-119">164.308(a)(6)(ii)</span></span>
- <span data-ttu-id="3a7a2-120">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="3a7a2-120">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="3a7a2-121">164.312 (b))</span><span class="sxs-lookup"><span data-stu-id="3a7a2-121">164.312(b))</span></span>
- <span data-ttu-id="3a7a2-122">CCPA (1798.105 (c))</span><span class="sxs-lookup"><span data-stu-id="3a7a2-122">CCPA (1798.105(c))</span></span>

<span data-ttu-id="3a7a2-123">Weitere Informationen finden Sie unter [bewerten von Datenschutzrisiken und identifizieren vertraulicher Informationen](information-protection-deploy-assess.md).</span><span class="sxs-lookup"><span data-stu-id="3a7a2-123">For more information, see [Assess data privacy risks and identify sensitive information](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="3a7a2-124">In den Datenschutzbestimmungen wird generell folgendes zur Überwachung und Reaktion gefordert:</span><span class="sxs-lookup"><span data-stu-id="3a7a2-124">The data privacy regulations generally call for the following for monitoring and response:</span></span>

- <span data-ttu-id="3a7a2-125">Überwachung, Benachrichtigung und Berichterstellung für Aktivitäten im Zusammenhang mit der Speicherung, Freigabe und Verarbeitung personenbezogener Daten</span><span class="sxs-lookup"><span data-stu-id="3a7a2-125">Auditing, alerting, and reporting for activities related to the storage, sharing and processing of personal data</span></span>
- <span data-ttu-id="3a7a2-126">Die Möglichkeit, auf eine Datensubjekt Anforderung (DSR) zu reagieren und in einigen Fällen Ermittlungs-und andere administrative Maßnahmen durchzuführen, um diese Anforderungen einzuhalten.</span><span class="sxs-lookup"><span data-stu-id="3a7a2-126">The ability to respond to a data subject request (DSR) and in some cases, perform investigative and other administrative measures to comply with such requests.</span></span>

<span data-ttu-id="3a7a2-127">Ihre Organisation möchte möglicherweise auch Überwachungs-und Antwort Aktivitäten für andere Zwecke wie andere Compliance-Anforderungen oder aus geschäftlichen Gründen durchführen.</span><span class="sxs-lookup"><span data-stu-id="3a7a2-127">Your organization may also wish to perform monitoring and response activities for other purposes, such as other compliance needs or for business reasons.</span></span> <span data-ttu-id="3a7a2-128">Das Einrichten Ihres Überwachungs-und Reaktionsschemas für den Datenschutz sollte im Rahmen der allgemeinen Überwachung und der Reaktionsplanung, Implementierung und Verwaltung erfolgen.</span><span class="sxs-lookup"><span data-stu-id="3a7a2-128">Establishing your monitoring and response scheme for data privacy should be done as part of overall monitoring and response planning, implementation, and management.</span></span>

<span data-ttu-id="3a7a2-129">Um Ihnen den Einstieg in ein Überwachungs-und Reaktionsschema in Microsoft 365 für Datenschutzbestimmungen zu erleichtern, werden in diesem Artikel nützliche Funktionen in Microsoft 365 aufgelistet, um Fragen zu beantworten, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="3a7a2-129">To help you get started with a monitoring and response scheme in Microsoft 365 for data privacy regulations, this article lists useful capabilities in Microsoft 365 to answer questions such as:</span></span> 

- <span data-ttu-id="3a7a2-130">Welche Art von alltäglichen Überwachungs-, Ermittlungs-und Bericht Erstellungstechniken stehen für die verschiedenen Datentypen und Quellen zur Verfügung?</span><span class="sxs-lookup"><span data-stu-id="3a7a2-130">What sort of day-to-day monitoring, investigative and reporting techniques are available for the different data types and sources?</span></span>
- <span data-ttu-id="3a7a2-131">Welche Mechanismen erforderlich sind, um Anforderungen an die Datensubjekte (DSRs) und etwaige Korrekturmaßnahmen wie Anonymisierung, Korrektur und Löschung zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="3a7a2-131">What mechanisms will be needed to handle data subject requests (DSRs) and any remedial actions, such as anonymization, redaction, and deletion.</span></span>

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a><span data-ttu-id="3a7a2-132">Überwachungs-und Warnungsrichtlinien im Security and Compliance Center</span><span class="sxs-lookup"><span data-stu-id="3a7a2-132">Auditing and Alert Policies in the Security and Compliance Center</span></span>

<span data-ttu-id="3a7a2-133">Weitere Informationen finden Sie in den folgenden Artikeln zum Einrichten von Überwachung, erweiterter Überwachung und Warnungsrichtlinien:</span><span class="sxs-lookup"><span data-stu-id="3a7a2-133">See these articles for setting up auditing, advanced auditing, and alert policies:</span></span>

- [<span data-ttu-id="3a7a2-134">Vereinheitlichte Überwachung</span><span class="sxs-lookup"><span data-stu-id="3a7a2-134">Unified auditing</span></span>](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [<span data-ttu-id="3a7a2-135">Postfachüberwachung</span><span class="sxs-lookup"><span data-stu-id="3a7a2-135">Mailbox auditing</span></span>](../compliance/enable-mailbox-auditing.md)
- [<span data-ttu-id="3a7a2-136">Erweiterte Überwachung</span><span class="sxs-lookup"><span data-stu-id="3a7a2-136">Advanced audit</span></span>](../compliance/advanced-audit.md)
- [<span data-ttu-id="3a7a2-137">Warnungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="3a7a2-137">Alert policies</span></span>](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="3a7a2-138">Anforderungen von Datensubjekten für die dsgvo und CCPA</span><span class="sxs-lookup"><span data-stu-id="3a7a2-138">Data subject requests for the GDPR and CCPA</span></span>

<span data-ttu-id="3a7a2-139">Informationen zum Antworten auf einen DSR in Microsoft 365 finden Sie unter [Datensubjekt Anforderungen für die dsgvo und CCPA](../compliance/gdpr-dsr-office365.md) .</span><span class="sxs-lookup"><span data-stu-id="3a7a2-139">See [Data Subject Requests for the GDPR and CCPA](../compliance/gdpr-dsr-office365.md) for information on responding to a DSR in Microsoft 365.</span></span>

## <a name="manage-deleted-users-in-microsoft-stream"></a><span data-ttu-id="3a7a2-140">Verwalten von gelöschten Benutzern in Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="3a7a2-140">Manage deleted users in Microsoft Stream</span></span>

<span data-ttu-id="3a7a2-141">Wenn ein Benutzer für Microsoft Stream aus Azure Active Directory (Azure AD) gelöscht wird, wenn sein Name einem gebuchten Stream-Video vor diesem Zeitpunkt zugeordnet wurde, bleibt seine e-Mail-Adresse dem Video zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="3a7a2-141">For Microsoft Stream, when a user is deleted from Azure Active Directory (Azure AD), if their name was associated with a posted Stream video prior to that point, their email address remains associated with the video.</span></span> <span data-ttu-id="3a7a2-142">Entfernen Sie die Informationen unter [Verwalten gelöschter Benutzer aus Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) .</span><span class="sxs-lookup"><span data-stu-id="3a7a2-142">See [Manage deleted users from Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) to remove it.</span></span>

## <a name="insider-risk-management-as-an-investigative-tool"></a><span data-ttu-id="3a7a2-143">Insider Risikomanagement als Ermittlungs Tool</span><span class="sxs-lookup"><span data-stu-id="3a7a2-143">Insider risk management as an investigative tool</span></span>

<span data-ttu-id="3a7a2-144">Das [Insider Risikomanagement in Microsoft 365](../compliance/insider-risk-management.md) ist ein Feature des Microsoft Compliance Admin Center, mit dem Sie das interne Risikomini mieren können, indem Sie riskante Aktivitäten in Ihrer Organisation erkennen, untersuchen und Maßnahmen ergreifen können.</span><span class="sxs-lookup"><span data-stu-id="3a7a2-144">[Insider risk management in Microsoft 365](../compliance/insider-risk-management.md) is a feature of the Microsoft Compliance admin center to help you minimize internal risk by enabling you to detect, investigate, and take action on risky activities in your organization.</span></span>
