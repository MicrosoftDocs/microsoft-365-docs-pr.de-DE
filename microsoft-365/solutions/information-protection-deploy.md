---
title: Bereitstellen des Informationsschutzes für Datenschutzbestimmungen mit Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: Konfigurieren Sie die Sicherheits-und Dienstinfrastruktur, um Ihre Informationen zu schützen und Datenschutzbestimmungen einzuhalten.
ms.openlocfilehash: 35ccfb21accd969c2a2cbdddde9a4ec1c7eeed64
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695108"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a><span data-ttu-id="409c2-103">Bereitstellen des Informationsschutzes für Datenschutzbestimmungen mit Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="409c2-103">Deploy information protection for data privacy regulations with Microsoft 365</span></span>

<span data-ttu-id="409c2-104">Diese Lösung enthält Anleitungen für die Planung und den Schutz personenbezogener Daten, die in Microsoft 365-Diensten gespeichert sind und möglicherweise Datenschutzbestimmungen unterliegen, beispielsweise die allgemeine Datenschutzverordnung (dsgvo) der Europäischen Union.</span><span class="sxs-lookup"><span data-stu-id="409c2-104">This solution provides guidance on how to plan for and protect personal data that is stored in Microsoft 365 services and potentially subject to data privacy regulations such as the European Union's General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="409c2-105">Diese Lösung konzentriert sich auf die anwendbaren Features von Microsoft Information Protection und Compliance, die Microsoft-Konformitätsbewertung und die Bewertungstools, die Ihnen dabei helfen, Ihre Daten zu kennen.</span><span class="sxs-lookup"><span data-stu-id="409c2-105">This solution focuses on applicable Microsoft information protection and compliance features, Microsoft Compliance Score, and assessment tools to help you know your data.</span></span> 
 
<span data-ttu-id="409c2-106">Weitere Informationen finden Sie auch im Hinblick auf die Verwendung von Microsoft-Identitäts-, Geräte-und Bedrohungsschutz-Steuerelementen für Ihre Datenschutzanforderungen sowie Daten Ermittlungs-und-Antwort Tools.</span><span class="sxs-lookup"><span data-stu-id="409c2-106">Additional information is also provided on the use of Microsoft identity, device, and threat protection controls for your data privacy needs, as well as data incident discovery and response tools.</span></span> 

## <a name="organization-of-this-guidance-material"></a><span data-ttu-id="409c2-107">Organisation dieses Anleitungs Materials</span><span class="sxs-lookup"><span data-stu-id="409c2-107">Organization of this guidance material</span></span>

<span data-ttu-id="409c2-108">Damit Sie sich mit den Microsoft 365-Tools vertraut machen können, die zum identifizieren, verwalten, Steuern und Überwachen von personenbezogenen Daten unter einer oder mehreren datenschutzbezogenen Bestimmungen verfügbar sind, sind diese Anleitungen in Abschnitten gegliedert.</span><span class="sxs-lookup"><span data-stu-id="409c2-108">To help you understand the Microsoft 365 tools available to identify, manage, control, and monitor personal data subject to one or more privacy-related regulations, this guidance is organized into sections.</span></span>
 
![Bereitstellen des Informationsschutzes für Datenschutzbestimmungen](../media/information-protection-deploy/information-protection-deploy-grid.png)

<span data-ttu-id="409c2-110">Jeder dieser Abschnitte entspricht einem separaten Artikel in dieser Lösung.</span><span class="sxs-lookup"><span data-stu-id="409c2-110">Each of these sections correspond to a separate article in this solution.</span></span>

>[!Note]
><span data-ttu-id="409c2-111">Wenn Sie bereits mit ihren Datenschutzverpflichtungen vertraut sind und gegen einen vorhandenen Plan ausgeführt werden, können Sie sich auf die Anleitungen zum verhindern, schützen, beibehalten und untersuchen konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="409c2-111">If you are already familiar with your data privacy obligations and are executing against an existing plan, you may want to focus on the Prevent, Protect, Retain, and Investigate guidance.</span></span>

>[!Important]
><span data-ttu-id="409c2-112">Wenn Sie diese Anleitung befolgen, müssen Sie nicht unbedingt mit den Datenschutzbestimmungen konform sein, insbesondere im Hinblick auf die Anzahl der erforderlichen Schritte, die außerhalb des Kontexts der Features liegen.</span><span class="sxs-lookup"><span data-stu-id="409c2-112">Following this guidance will not necessarily make you compliant with any data privacy regulation, especially considering the number of steps required that are outside the context of the features.</span></span> <span data-ttu-id="409c2-113">Sie sind dafür verantwortlich, dass Sie Ihre Einhaltung sicherstellen und ihre Rechts-und Compliance-Teams konsultieren oder sich von Drittanbietern beraten lassen, die sich auf die Einhaltung von Richtlinien spezialisieren.</span><span class="sxs-lookup"><span data-stu-id="409c2-113">You are responsible for ensuring your compliance and to consult your legal and compliance teams or to seek guidance and advice from third parties that specialize in compliance.</span></span>
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a><span data-ttu-id="409c2-114">Plan: Bewerten der Datenschutzrisiken und identifizieren vertraulicher Elemente</span><span class="sxs-lookup"><span data-stu-id="409c2-114">Plan: Assess data privacy risks and identify sensitive items</span></span> 

<span data-ttu-id="409c2-115">Die Bewertung der Datenschutzbestimmungen und der Risiken, denen Ihre Organisation unterliegt, ist ein wichtiger erster Schritt, bevor Sie mit der Implementierung von Verbesserungen beginnen, einschließlich der durch die Konfiguration von Microsoft 365 erreichbaren.</span><span class="sxs-lookup"><span data-stu-id="409c2-115">Assessing data privacy regulations and risks that your organization is subject to is a key first step to take before starting to implement improvements, including those achievable through Microsoft 365 configuration.</span></span> <span data-ttu-id="409c2-116">Dies kann eine allgemeine Eignungsbewertung oder die Identifizierung bestimmter vertraulicher Informationstypen sein, die den von Ihrer Organisation einzuhaltenden behördlichen Kontrollen unterliegen, sowie deren Auftreten in Ihrer Microsoft 365-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="409c2-116">This may include an overall readiness assessment or identification of particular sensitive information types that are subject to regulatory controls your organization needs to comply with, as well as the occurrence of them in your Microsoft 365 environment.</span></span>

<span data-ttu-id="409c2-117">Weitere Informationen finden Sie unter [bewerten von Datenschutzrisiken und identifizieren vertraulicher Elemente](information-protection-deploy-assess.md).</span><span class="sxs-lookup"><span data-stu-id="409c2-117">For more information, see [Assess data privacy risks and identify sensitive items](information-protection-deploy-assess.md).</span></span>

## <a name="track-use-compliance-score-and-compliance-manager"></a><span data-ttu-id="409c2-118">Track: Use Compliance Score and Compliance Manager</span><span class="sxs-lookup"><span data-stu-id="409c2-118">Track: Use Compliance Score and Compliance Manager</span></span> 

<span data-ttu-id="409c2-119">Compliance-Score und Compliance-Manager bieten eine integrierte Reihe von Tools, die im Microsoft 365 Compliance Admin Center und in Services Trust Portal zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="409c2-119">Compliance Score and Compliance Manager provide an integrated set of tools available in the Microsoft 365 Compliance admin center and Services Trust Portal.</span></span> <span data-ttu-id="409c2-120">Gemeinsam bieten Ihnen diese Tools eine integrierte Möglichkeit zum Nachverfolgen und Verwalten von Verbesserungs Aktionen insgesamt sowie in Bezug auf mehrere Datenschutzbestimmungen, denen Sie unterliegen.</span><span class="sxs-lookup"><span data-stu-id="409c2-120">Together, these tools provide you with a built-in ability to track and manage improvement actions overall as well as those related to multiple data privacy regulations to which you are subjected.</span></span>

<span data-ttu-id="409c2-121">Mit den Tools können Sie auch integrierte Bewertungs Vorlagen verwenden, die für jede Verordnung spezifisch sind, wobei Sie Aktionselemente für jede ausgewählte Bewertungs Vorlage nachverfolgen sowie bestimmte regulatorische Steuerelemente anzeigen und diese mit bestimmten Aktionen verknüpfen können.</span><span class="sxs-lookup"><span data-stu-id="409c2-121">The tools also allow you to leverage built in assessment templates specific to each regulation, where you can track action items for each assessment template selected, as well as view specific regulatory controls, and relate them to specific actions.</span></span>

<span data-ttu-id="409c2-122">Weitere Informationen finden Sie unter [use Compliance Score and Compliance Manager zur Verwaltung von Verbesserungs Aktionen](information-protection-deploy-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="409c2-122">For more information, see [Use Compliance Score and Compliance Manager to manage improvement actions](information-protection-deploy-compliance.md).</span></span>

## <a name="prevent-use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="409c2-123">Verhindern: Verwenden von Identitäts-, Geräte-und Bedrohungsschutz für die Datenschutzverordnung</span><span class="sxs-lookup"><span data-stu-id="409c2-123">Prevent: Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="409c2-124">Microsoft 365 bietet eine Reihe von Identitäts-, Geräte-und Bedrohungsschutz Funktionen, mit denen Sie die Einhaltung von Datenschutzbestimmungen in Einklang bringen können.</span><span class="sxs-lookup"><span data-stu-id="409c2-124">Microsoft 365 provides a number of identity, device, and threat protection capabilities that you can use to help comply with data privacy regulatory compliance.</span></span> 

<span data-ttu-id="409c2-125">Weitere Informationen finden Sie unter [Verwenden von Identität, Gerät und Bedrohungsschutz für die Datenschutzverordnung](information-protection-deploy-identity-device-threat.md).</span><span class="sxs-lookup"><span data-stu-id="409c2-125">For more information, see [Use identity, device, and threat protection for data privacy regulation](information-protection-deploy-identity-device-threat.md).</span></span>

<span data-ttu-id="409c2-126">In diesem Artikel wird kurz beschrieben, was die Datenschutzbestimmungen in diesen Bereichen allgemein betreffen, und enthält eine Liste der zugehörigen Microsoft 365-Lösungen mit Links zu weiteren Informationen, die Sie bei der Erfüllung von Implementierungsanforderungen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="409c2-126">This article briefly describes what the data privacy regulations generally call for in these areas and provides a listing of related Microsoft 365 solutions, with links to more information to help you address any implementation requirements.</span></span> 

## <a name="protect-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="409c2-127">Schützen von Informationen unterliegen der Datenschutzverordnung</span><span class="sxs-lookup"><span data-stu-id="409c2-127">Protect information subject to data privacy regulation</span></span>

<span data-ttu-id="409c2-128">Die Datenschutzbestimmungen diktieren eine Reihe von Steuerelementen für den Schutz personenbezogener Daten, die in Ihrer Umgebung eingesetzt werden können, einschließlich mehr als 40 Schutz von Informations Steuerelementen in den vier Datenschutzbestimmungen in unserem Beispielsatz von dsgvo, California Consumer Protection Act (CCPA), HIPAA-HITECH (United States Health Care Privacy Act) und dem Brazil Data Protection Act (LGPD).</span><span class="sxs-lookup"><span data-stu-id="409c2-128">Data privacy regulations dictate a number of personal information protection controls that can be employed in your environment, including more than forty Protect Information controls across just the four data privacy regulations in our sample set of GDPR, California Consumer Protection Act (CCPA), HIPAA-HITECH (United States health care privacy act), and the Brazil Data Protection Act (LGPD).</span></span>

<span data-ttu-id="409c2-129">Weitere Informationen finden Sie unter [Schützen von Informationen unterliegender Datenschutzbestimmungen in Ihrer Organisation](information-protection-deploy-protect-information.md).</span><span class="sxs-lookup"><span data-stu-id="409c2-129">For more information, see [Protect information subject to data privacy regulation in your organization](information-protection-deploy-protect-information.md).</span></span>

<span data-ttu-id="409c2-130">In diesem Artikel werden die wichtigsten steuerungsschemas erläutert, die für die Adressierung von Informationsschutz Anforderungen für den Datenschutz in Ihrer Organisation verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="409c2-130">This article lays out the main control schemes that can be used for addressing information protection needs for data privacy in your organization.</span></span>

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="409c2-131">Beibehalten: Informationen zur Datenschutzrichtlinie unterliegen Regeln</span><span class="sxs-lookup"><span data-stu-id="409c2-131">Retain: Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="409c2-132">Datenschutzbestimmungen rufen Sie die Steuerelemente für die Steuerung personenbezogener Informationen, die in Ihrer Umgebung eingesetzt werden können, einschließlich mehr als vierundzwanzig Steuerelemente in den vier Datenschutzbestimmungen in unserem Beispielsatz von dsgvo, CCPA, HIPAA-HITECH und LGPD auf.</span><span class="sxs-lookup"><span data-stu-id="409c2-132">Data privacy regulations call for personal information governance controls that can be employed in your environment, including more than twenty-four controls across the four data privacy regulations in our sample set of GDPR, CCPA, HIPAA-HITECH, and LGPD.</span></span>

<span data-ttu-id="409c2-133">Weitere Informationen finden Sie unter [Steuern von Informationen unterliegen der Datenschutzbestimmungen in Ihrer Organisation](information-protection-deploy-govern.md).</span><span class="sxs-lookup"><span data-stu-id="409c2-133">For more information, see [Govern information subject to data privacy regulation in your organization](information-protection-deploy-govern.md).</span></span>

<span data-ttu-id="409c2-134">Während die Datenschutzbestimmungen vage hinsichtlich der Informationssteuerung sein können &mdash; , wie zum Beispiel gezielte Aufbewahrung, Löschung und Archivierung, werden &mdash; in diesem Artikel die primären steuerungsschemas erläutert, die Sie für den Datenschutz in Ihrer Organisation mit den Anforderungen an die Informationssteuerung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="409c2-134">While the data privacy regulations can be vague regarding information governance&mdash;such as purposeful retention, deletion and archiving&mdash;this article lays out the primary control schemes that you can use address information governance needs for data privacy in your organization.</span></span>

## <a name="investigate-monitor-and-respond-subject-to-data-privacy-regulation"></a><span data-ttu-id="409c2-135">Untersuchen: überwachen und reagieren unterliegender Datenschutzverordnung</span><span class="sxs-lookup"><span data-stu-id="409c2-135">Investigate: Monitor and respond subject to data privacy regulation</span></span>

<span data-ttu-id="409c2-136">Es stehen Microsoft 365-Features zur Verfügung, die Sie bei der Überprüfung, Untersuchung und Reaktion auf Datenschutz Vorfälle in Ihrer Organisation unterstützen, wenn Sie verwandte Funktionen nutzen.</span><span class="sxs-lookup"><span data-stu-id="409c2-136">There are Microsoft 365 features available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> 

<span data-ttu-id="409c2-137">Es kann wichtig sein, Prozesse, Verfahren und andere Dokumentationen für diese zu untersuchen, um die Einhaltung von Regulierungsstellen zu demonstrieren.</span><span class="sxs-lookup"><span data-stu-id="409c2-137">Having processes, procedures, and other documentation for each of these can be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="409c2-138">Weitere Informationen finden Sie unter [überwachen und reagieren auf Datenschutz Vorfälle in Ihrer Organisation](information-protection-deploy-monitor-respond.md).</span><span class="sxs-lookup"><span data-stu-id="409c2-138">For more information, see [Monitor and respond to data privacy incidents in your organization](information-protection-deploy-monitor-respond.md).</span></span>
