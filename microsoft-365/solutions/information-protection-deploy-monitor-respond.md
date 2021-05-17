---
title: Überwachen und Reagieren auf Datenschutzvorfälle in Ihrer Organisation
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
description: Verwenden Sie Überwachungs- und Warnungsrichtlinien und Anfragen von personensubjektierten Personen, um Vorfälle mit personenbezogenen Daten zu überwachen und darauf zu reagieren.
ms.openlocfilehash: 4070cd772d243bcfba33bfb164fd05e1f0911b3b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928424"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a><span data-ttu-id="43d1d-103">Überwachen und Reagieren auf Datenschutzvorfälle in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="43d1d-103">Monitor and respond to data privacy incidents in your organization</span></span>

<span data-ttu-id="43d1d-104">Microsoft 365 stehen Ihnen bei der Überwachung, Untersuchung und Reaktion auf Datenschutzvorfälle in Ihrer Organisation bei der Operationalisierung verwandter Funktionen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="43d1d-104">Microsoft 365 features are available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> <span data-ttu-id="43d1d-105">Prozesse, Verfahren und andere Dokumentationen für jede dieser Verfahren können auch wichtig sein, um die Einhaltung von Vorschriften zu demonstrieren.</span><span class="sxs-lookup"><span data-stu-id="43d1d-105">Having processes, procedures, and other documentation for each of these may also be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="43d1d-106">Zu diesen zählen:</span><span class="sxs-lookup"><span data-stu-id="43d1d-106">These include:</span></span> 

- <span data-ttu-id="43d1d-107">Überwachungs- und Warnungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="43d1d-107">Auditing and alert policies</span></span>
- <span data-ttu-id="43d1d-108">Anfragen von Datensubjekten (einschließlich Inhaltssuche und eDiscovery)</span><span class="sxs-lookup"><span data-stu-id="43d1d-108">Data subject requests (including content search and eDiscovery)</span></span>
- <span data-ttu-id="43d1d-109">Zusätzliche Untersuchungstools und Berichte</span><span class="sxs-lookup"><span data-stu-id="43d1d-109">Additional investigative tools and reporting</span></span>

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a><span data-ttu-id="43d1d-110">Datenschutzbestimmungen, die sich auf die Verwendung von Überwachungs- und Reaktionstools auswirken</span><span class="sxs-lookup"><span data-stu-id="43d1d-110">Data privacy regulations impacting the use of monitoring and response tools</span></span>

<span data-ttu-id="43d1d-111">Im Folgenden finden Sie eine Beispielliste der Datenschutzbestimmungen, die sich auf Die Steuerung von Informationen beziehen können:</span><span class="sxs-lookup"><span data-stu-id="43d1d-111">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="43d1d-112">LGPD Artikel 46</span><span class="sxs-lookup"><span data-stu-id="43d1d-112">LGPD Article 46</span></span>
- <span data-ttu-id="43d1d-113">LGPD Artikel 48</span><span class="sxs-lookup"><span data-stu-id="43d1d-113">LGPD Article 48</span></span>
- <span data-ttu-id="43d1d-114">Artikel zur DSGVO (5)(1)(f)</span><span class="sxs-lookup"><span data-stu-id="43d1d-114">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="43d1d-115">Artikel zur DSGVO (15)(1)(e)</span><span class="sxs-lookup"><span data-stu-id="43d1d-115">GDPR Article (15)(1)(e)</span></span>
- <span data-ttu-id="43d1d-116">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="43d1d-116">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="43d1d-117">164.308(a)(1)(ii)(D))</span><span class="sxs-lookup"><span data-stu-id="43d1d-117">164.308(a)(1)(ii)(D))</span></span>
- <span data-ttu-id="43d1d-118">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="43d1d-118">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="43d1d-119">164.308(a)(6)(ii)</span><span class="sxs-lookup"><span data-stu-id="43d1d-119">164.308(a)(6)(ii)</span></span>
- <span data-ttu-id="43d1d-120">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="43d1d-120">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="43d1d-121">164.312(b))</span><span class="sxs-lookup"><span data-stu-id="43d1d-121">164.312(b))</span></span>
- <span data-ttu-id="43d1d-122">CCPA (1798.105(c))</span><span class="sxs-lookup"><span data-stu-id="43d1d-122">CCPA (1798.105(c))</span></span>

<span data-ttu-id="43d1d-123">Weitere Informationen finden Sie unter [Bewerten von Datenschutzrisiken und Identifizieren vertraulicher Informationen.](information-protection-deploy-assess.md)</span><span class="sxs-lookup"><span data-stu-id="43d1d-123">For more information, see [Assess data privacy risks and identify sensitive information](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="43d1d-124">Die Datenschutzbestimmungen fordern im Allgemeinen Folgendes zur Überwachung und Reaktion auf:</span><span class="sxs-lookup"><span data-stu-id="43d1d-124">The data privacy regulations generally call for the following for monitoring and response:</span></span>

- <span data-ttu-id="43d1d-125">Überwachung, Warnung und Berichterstellung für Aktivitäten im Zusammenhang mit der Speicherung, Freigabe und Verarbeitung personenbezogener Daten</span><span class="sxs-lookup"><span data-stu-id="43d1d-125">Auditing, alerting, and reporting for activities related to the storage, sharing and processing of personal data</span></span>
- <span data-ttu-id="43d1d-126">Die Möglichkeit, auf eine Anfrage einer Person zu antworten und in einigen Fällen Ermittlungen und andere administrative Maßnahmen zur Erfüllung dieser Anforderungen durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="43d1d-126">The ability to respond to a data subject request (DSR) and in some cases, perform investigative and other administrative measures to comply with such requests.</span></span>

<span data-ttu-id="43d1d-127">Ihre Organisation möchte möglicherweise auch Überwachungs- und Reaktionsaktivitäten für andere Zwecke durchführen, z. B. für andere Complianceanforderungen oder aus geschäftlichen Gründen.</span><span class="sxs-lookup"><span data-stu-id="43d1d-127">Your organization may also wish to perform monitoring and response activities for other purposes, such as other compliance needs or for business reasons.</span></span> <span data-ttu-id="43d1d-128">Die Einrichtung Ihres Überwachungs- und Reaktionsschemas für den Datenschutz sollte im Rahmen der allgemeinen Überwachungs- und Reaktionsplanung, -implementierung und -verwaltung durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="43d1d-128">Establishing your monitoring and response scheme for data privacy should be done as part of overall monitoring and response planning, implementation, and management.</span></span>

<span data-ttu-id="43d1d-129">Um Ihnen zu helfen, mit einem Überwachungs- und Reaktionsschema in Microsoft 365 datenschutzbestimmungen zu beginnen, werden in diesem Artikel nützliche Funktionen in Microsoft 365 aufgeführt, um Fragen zu beantworten, z. B.:</span><span class="sxs-lookup"><span data-stu-id="43d1d-129">To help you get started with a monitoring and response scheme in Microsoft 365 for data privacy regulations, this article lists useful capabilities in Microsoft 365 to answer questions such as:</span></span> 

- <span data-ttu-id="43d1d-130">Welche Art von Täglichen Überwachungs-, Untersuchungs- und Berichtstechniken stehen für die verschiedenen Datentypen und Quellen zur Verfügung?</span><span class="sxs-lookup"><span data-stu-id="43d1d-130">What sort of day-to-day monitoring, investigative and reporting techniques are available for the different data types and sources?</span></span>
- <span data-ttu-id="43d1d-131">Welche Mechanismen sind erforderlich, um Anträge von Datensubjekten (Data Subject Requests, DSRs) und Abhilfemaßnahmen wie Anonymisierung, Redaction und Löschung zu behandeln?</span><span class="sxs-lookup"><span data-stu-id="43d1d-131">What mechanisms will be needed to handle data subject requests (DSRs) and any remedial actions, such as anonymization, redaction, and deletion.</span></span>

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a><span data-ttu-id="43d1d-132">Überwachungs- und Warnungsrichtlinien im Security and Compliance Center</span><span class="sxs-lookup"><span data-stu-id="43d1d-132">Auditing and Alert Policies in the Security and Compliance Center</span></span>

<span data-ttu-id="43d1d-133">In diesen Artikeln finden Sie Informationen zum Einrichten von Überwachungs-, Erweiterten Überwachungs- und Warnungsrichtlinien:</span><span class="sxs-lookup"><span data-stu-id="43d1d-133">See these articles for setting up auditing, advanced auditing, and alert policies:</span></span>

- [<span data-ttu-id="43d1d-134">Vereinheitlichte Überwachung</span><span class="sxs-lookup"><span data-stu-id="43d1d-134">Unified auditing</span></span>](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [<span data-ttu-id="43d1d-135">Postfachüberwachung</span><span class="sxs-lookup"><span data-stu-id="43d1d-135">Mailbox auditing</span></span>](../compliance/enable-mailbox-auditing.md)
- [<span data-ttu-id="43d1d-136">Erweiterte Überwachung</span><span class="sxs-lookup"><span data-stu-id="43d1d-136">Advanced audit</span></span>](../compliance/advanced-audit.md)
- [<span data-ttu-id="43d1d-137">Warnungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="43d1d-137">Alert policies</span></span>](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="43d1d-138">Anträge von Datensubjekten für die DSGVO und das CCPA</span><span class="sxs-lookup"><span data-stu-id="43d1d-138">Data subject requests for the GDPR and CCPA</span></span>

<span data-ttu-id="43d1d-139">Informationen zum Reagieren auf eine Antragserfordererlichkeit finden Sie unter Anträge von Datensubjekten für die DSGVO und das [CCPA](/compliance/regulatory/gdpr-dsr-Office365) in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="43d1d-139">See [Data Subject Requests for the GDPR and CCPA](/compliance/regulatory/gdpr-dsr-Office365) for information on responding to a DSR in Microsoft 365.</span></span>

## <a name="manage-deleted-users-in-microsoft-stream"></a><span data-ttu-id="43d1d-140">Verwalten gelöschter Benutzer in Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="43d1d-140">Manage deleted users in Microsoft Stream</span></span>

<span data-ttu-id="43d1d-141">Wenn ein Benutzer in Microsoft Stream aus Azure Active Directory (Azure AD) gelöscht wird, bleibt seine E-Mail-Adresse dem Video zugeordnet, wenn sein Name vor diesem Zeitpunkt einem bereitgestellten Stream-Video zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="43d1d-141">For Microsoft Stream, when a user is deleted from Azure Active Directory (Azure AD), if their name was associated with a posted Stream video prior to that point, their email address remains associated with the video.</span></span> <span data-ttu-id="43d1d-142">Weitere [Informationen finden Sie unter Verwalten gelöschter Benutzer aus Microsoft Stream.](/stream/managing-deleted-users)</span><span class="sxs-lookup"><span data-stu-id="43d1d-142">See [Manage deleted users from Microsoft Stream](/stream/managing-deleted-users) to remove it.</span></span>

## <a name="insider-risk-management-as-an-investigative-tool"></a><span data-ttu-id="43d1d-143">Insider-Risikomanagement als Untersuchungstool</span><span class="sxs-lookup"><span data-stu-id="43d1d-143">Insider risk management as an investigative tool</span></span>

<span data-ttu-id="43d1d-144">[Insider risk management in Microsoft 365](../compliance/insider-risk-management.md) ist ein Feature des Microsoft Compliance Admin Centers, mit dem Sie interne Risiken minimieren können, indem Sie riskante Aktivitäten in Ihrer Organisation erkennen, untersuchen und Maßnahmen ergreifen können.</span><span class="sxs-lookup"><span data-stu-id="43d1d-144">[Insider risk management in Microsoft 365](../compliance/insider-risk-management.md) is a feature of the Microsoft Compliance admin center to help you minimize internal risk by enabling you to detect, investigate, and take action on risky activities in your organization.</span></span>