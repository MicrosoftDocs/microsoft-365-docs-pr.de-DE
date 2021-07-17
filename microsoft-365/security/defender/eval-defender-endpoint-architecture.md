---
title: Überprüfen der Architekturanforderungen und Schlüsselkonzepte von Microsoft Defender für Endpunkt
description: Das technische Diagramm für Microsoft Defender für Endpunkt in Microsoft 365 Defender hilft Ihnen, die Identität in Microsoft 365 zu verstehen, bevor Sie Ihre Testumgebung oder Pilotumgebung erstellen.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 4df1ac2ca5fdfaa88ec2d08c85112f52da26b873
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458130"
---
# <a name="review-microsoft-defender-for-endpoint-architecture-requirements-and-key-concepts"></a><span data-ttu-id="a6059-103">Überprüfen der Architekturanforderungen und Schlüsselkonzepte von Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="a6059-103">Review Microsoft Defender for Endpoint architecture requirements and key concepts</span></span>

<span data-ttu-id="a6059-104">**Gilt für:** Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a6059-104">**Applies to:** Microsoft 365 Defender</span></span>

<span data-ttu-id="a6059-105">Dieser Artikel führt Sie beim Einrichten der Evaluierung für die Microsoft Defender für Endpunkt-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="a6059-105">This article will guide you in the process of setting up the evaluation for Microsoft Defender for Endpoint environment.</span></span>

<span data-ttu-id="a6059-106">Weitere Informationen zu diesem Prozess finden Sie im [Übersichtsartikel.](eval-defender-endpoint-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a6059-106">For more information about this process, see the [overview article](eval-defender-endpoint-overview.md).</span></span>

<span data-ttu-id="a6059-107">Bevor Sie Microsoft Defender für Endpunkt aktivieren, stellen Sie sicher, dass Sie die Architektur verstehen und die Anforderungen erfüllen können.</span><span class="sxs-lookup"><span data-stu-id="a6059-107">Before enabling Microsoft Defender for Endpoint, be sure you understand the architecture and can meet the requirements.</span></span>

## <a name="understand-the-architecture"></a><span data-ttu-id="a6059-108">Grundlegendes zur Architektur</span><span class="sxs-lookup"><span data-stu-id="a6059-108">Understand the architecture</span></span>

<span data-ttu-id="a6059-109">Das folgende Diagramm veranschaulicht die Architektur und Integration von Microsoft Defender für Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="a6059-109">The following diagram illustrates Microsoft Defender for Endpoint architecture and integrations.</span></span> 

![Schritte zum Hinzufügen von Microsoft Defender für Office zur Defender-Evaluierungsumgebung](../../media/defender/m365-defender-endpoint-architecture.png)

<span data-ttu-id="a6059-111">In der folgenden Tabelle wird die Abbildung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a6059-111">The following table describes the illustration.</span></span>

<span data-ttu-id="a6059-112">Call-out</span><span class="sxs-lookup"><span data-stu-id="a6059-112">Call-out</span></span> | <span data-ttu-id="a6059-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a6059-113">Description</span></span>
:---|:---|
<span data-ttu-id="a6059-114">1</span><span class="sxs-lookup"><span data-stu-id="a6059-114">1</span></span> | <span data-ttu-id="a6059-115">Geräte werden über eines der unterstützten Verwaltungstools an boarded.</span><span class="sxs-lookup"><span data-stu-id="a6059-115">Devices are on-boarded through one of the supported management tools.</span></span> 
<span data-ttu-id="a6059-116">2</span><span class="sxs-lookup"><span data-stu-id="a6059-116">2</span></span> | <span data-ttu-id="a6059-117">On-boarded devices provide and respond to Microsoft Defender for Endpoint signal data.</span><span class="sxs-lookup"><span data-stu-id="a6059-117">On-boarded devices provide and respond to Microsoft Defender for Endpoint signal data.</span></span>
<span data-ttu-id="a6059-118">3</span><span class="sxs-lookup"><span data-stu-id="a6059-118">3</span></span> | <span data-ttu-id="a6059-119">Verwaltete Geräte sind in Azure Active Directory eingebunden und/oder registriert.</span><span class="sxs-lookup"><span data-stu-id="a6059-119">Managed devices are joined and/or enrolled in Azure Active Directory.</span></span>
<span data-ttu-id="a6059-120">4 </span><span class="sxs-lookup"><span data-stu-id="a6059-120">4</span></span> | <span data-ttu-id="a6059-121">In die Domäne eingebundene Windows 10 Geräte werden mit Azure Active Directory mithilfe von Azure Active Directory Verbinden synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="a6059-121">Domain-joined Windows 10 devices are synchronized to Azure Active Directory using Azure Active Directory Connect.</span></span>
<span data-ttu-id="a6059-122">5 </span><span class="sxs-lookup"><span data-stu-id="a6059-122">5</span></span> | <span data-ttu-id="a6059-123">Warnungen, Untersuchungen und Antworten von Microsoft Defender für Endpunkt werden in Microsoft 365 Defender verwaltet.</span><span class="sxs-lookup"><span data-stu-id="a6059-123">Microsoft Defender for Endpoint alerts, investigations, and responses are managed in Microsoft 365 Defender.</span></span>

## <a name="understand-key-concepts"></a><span data-ttu-id="a6059-124">Grundlegendes zu den wichtigsten Konzepten</span><span class="sxs-lookup"><span data-stu-id="a6059-124">Understand key concepts</span></span>

<span data-ttu-id="a6059-125">In der folgenden Tabelle sind die wichtigsten Konzepte aufgeführt, die beim Auswerten, Konfigurieren und Bereitstellen von Microsoft Defender für Endpunkt zu verstehen sind:</span><span class="sxs-lookup"><span data-stu-id="a6059-125">The following table identified key concepts that are important to understand when evaluating, configuring, and deploying Microsoft Defender for Endpoint:</span></span> 

<span data-ttu-id="a6059-126">Konzept</span><span class="sxs-lookup"><span data-stu-id="a6059-126">Concept</span></span> | <span data-ttu-id="a6059-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a6059-127">Description</span></span> | <span data-ttu-id="a6059-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a6059-128">More information</span></span>
:---|:---|:---|
<span data-ttu-id="a6059-129">Verwaltungsportal</span><span class="sxs-lookup"><span data-stu-id="a6059-129">Administration Portal</span></span> | <span data-ttu-id="a6059-130">Microsoft 365 Defender Portal zur Überwachung und Unterstützung bei der Reaktion auf Warnungen über potenzielle fortgeschrittene dauerhafte Bedrohungsaktivitäten oder Datenschutzverletzungen.</span><span class="sxs-lookup"><span data-stu-id="a6059-130">Microsoft 365 Defender portal to monitor and assist in responding to alerts of potential advanced persistent threat activity or data breaches.</span></span> | [<span data-ttu-id="a6059-131">Übersicht über das Microsoft Defender für Endpunkt-Portal</span><span class="sxs-lookup"><span data-stu-id="a6059-131">Microsoft Defender for Endpoint portal overview</span></span>](/defender-endpoint/portal-overview)
<span data-ttu-id="a6059-132">Attack Surface Reduction</span><span class="sxs-lookup"><span data-stu-id="a6059-132">Attack Surface Reduction</span></span> | <span data-ttu-id="a6059-133">Reduzieren Sie Ihre Angriffsflächen, indem Sie die Stellen minimieren, an denen Ihre Organisation anfällig für Cyberbedrohungen und Angriffe ist.</span><span class="sxs-lookup"><span data-stu-id="a6059-133">Help reduce your attack surfaces by minimizing the places where your organization is vulnerable to cyberthreats and attacks.</span></span> | [<span data-ttu-id="a6059-134">Übersicht der Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="a6059-134">Overview of attack surface reduction</span></span>](/defender-endpoint/overview-attack-surface-reduction)
<span data-ttu-id="a6059-135">Endpunkterkennung und -antwort</span><span class="sxs-lookup"><span data-stu-id="a6059-135">Endpoint Detection and Response</span></span> | <span data-ttu-id="a6059-136">Endpunkterkennungs- und -reaktionsfunktionen bieten erweiterte Angriffserkennungen, die nahezu in Echtzeit und umsetzbar sind.</span><span class="sxs-lookup"><span data-stu-id="a6059-136">Endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> | [<span data-ttu-id="a6059-137">Übersicht über EDR Funktionen</span><span class="sxs-lookup"><span data-stu-id="a6059-137">Overview of endpoint detection and response capabilities</span></span>](/defender-endpoint/overview-endpoint-detection-response)
<span data-ttu-id="a6059-138">Blockieren und Eindämmen von Verhaltensweisen</span><span class="sxs-lookup"><span data-stu-id="a6059-138">Behavioral Blocking and Containment</span></span> | <span data-ttu-id="a6059-139">Funktionen zum Blockieren und Eindämmen von Verhaltensweisen können dazu beitragen, Bedrohungen basierend auf ihren Verhaltensweisen und Prozessstrukturen zu erkennen und zu stoppen, selbst wenn die Bedrohung mit der Ausführung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="a6059-139">Behavioral blocking and containment capabilities can help identify and stop threats, based on their behaviors and process trees even when the threat has started execution.</span></span> | [<span data-ttu-id="a6059-140">Verhaltensbasiertes Blockieren und Eindämmen</span><span class="sxs-lookup"><span data-stu-id="a6059-140">Behavioral blocking and containment</span></span>](/defender-endpoint/behavioral-blocking-containment)
<span data-ttu-id="a6059-141">Automatisierte Untersuchung und Reaktion</span><span class="sxs-lookup"><span data-stu-id="a6059-141">Automated Investigation and Response</span></span> | <span data-ttu-id="a6059-142">Die automatisierte Untersuchung verwendet verschiedene Überprüfungsalgorithmen basierend auf Prozessen, die von Sicherheitsanalysten verwendet werden und darauf ausgelegt sind, Warnungen zu untersuchen und sofortige Maßnahmen zur Behebung von Verstößen zu ergreifen.</span><span class="sxs-lookup"><span data-stu-id="a6059-142">Automated investigation uses various inspection algorithms based on processes that are used by security analysts and designed to examine alerts and take immediate action to resolve breaches.</span></span> | [<span data-ttu-id="a6059-143">Verwenden automatisierter Untersuchungen zum Untersuchen und Beheben von Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="a6059-143">Use automated investigations to investigate and remediate threats</span></span>](/defender-endpoint/automated-investigations)
<span data-ttu-id="a6059-144">Erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="a6059-144">Advanced Hunting</span></span> | <span data-ttu-id="a6059-145">Die erweiterte Suche ist ein abfragebasiertes Tool zur Bedrohungssuche, mit dem Sie rohe Daten von bis zu 30 Tagen untersuchen können, damit Sie Ereignisse in Ihrem Netzwerk proaktiv untersuchen können, um Bedrohungsindikatoren und Entitäten zu finden.</span><span class="sxs-lookup"><span data-stu-id="a6059-145">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data so that you can proactively inspect events in your network to locate threat indicators and entities.</span></span> | [<span data-ttu-id="a6059-146">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="a6059-146">Overview of advanced hunting</span></span>](/defender-endpoint/advanced-hunting-overview)
<span data-ttu-id="a6059-147">Bedrohungsanalyse</span><span class="sxs-lookup"><span data-stu-id="a6059-147">Threat Analytics</span></span> | <span data-ttu-id="a6059-148">Bei der Bedrohungsanalyse handelt es sich um eine Reihe von Berichten von erfahrenen Microsoft-Sicherheitsexperten, die die relevantesten Bedrohungen abdecken.</span><span class="sxs-lookup"><span data-stu-id="a6059-148">Threat analytics is a set of reports from expert Microsoft security researchers covering the most relevant threats.</span></span> | [<span data-ttu-id="a6059-149">Nachverfolgen und Reagieren auf neue Bedrohungen mit Bedrohungsanalysen</span><span class="sxs-lookup"><span data-stu-id="a6059-149">Track and respond to emerging threats</span></span>](/defender-endpoint/threat-analytics)


<span data-ttu-id="a6059-150">Ausführlichere Informationen zu den in Microsoft Defender für Endpunkt enthaltenen Funktionen finden Sie unter [Was ist Microsoft Defender für Endpunkt.](/defender-endpoint/microsoft-defender-endpoint)</span><span class="sxs-lookup"><span data-stu-id="a6059-150">For more detailed information about the capabilities included with Microsoft Defender for Endpoint, see [What is Microsoft Defender for Endpoint](/defender-endpoint/microsoft-defender-endpoint).</span></span>

## <a name="siem-integration"></a><span data-ttu-id="a6059-151">SIEM-Integration</span><span class="sxs-lookup"><span data-stu-id="a6059-151">SIEM integration</span></span>

<span data-ttu-id="a6059-152">Sie können Microsoft Defender für Endpunkt in Azure Sentinel integrieren, um Sicherheitsereignisse in Ihrer Organisation umfassender zu analysieren und Playbooks für eine effektive und sofortige Reaktion zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a6059-152">You can integrate Microsoft Defender for Endpoint with Azure Sentinel to more comprehensively analyze security events across your organization and build playbooks for effective and immediate response.</span></span> 

<span data-ttu-id="a6059-153">Microsoft Defender für Endpunkt kann auch in andere SIEM-Lösungen (Security Information and Event Management) integriert werden.</span><span class="sxs-lookup"><span data-stu-id="a6059-153">Microsoft Defender for Endpoint can also be integrated into other Security Information and Event Management (SIEM) solutions.</span></span> <span data-ttu-id="a6059-154">Weitere Informationen finden Sie unter [Aktivieren der SIEM-Integration in Microsoft Defender für Endpunkt.](/defender-endpoint/enable-siem-integration)</span><span class="sxs-lookup"><span data-stu-id="a6059-154">For more information, see [Enable SIEM integration in Microsoft Defender for Endpoint](/defender-endpoint/enable-siem-integration).</span></span>


## <a name="next-steps"></a><span data-ttu-id="a6059-155">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a6059-155">Next steps</span></span>
[<span data-ttu-id="a6059-156">Aktivieren der Auswertung</span><span class="sxs-lookup"><span data-stu-id="a6059-156">Enable the evaluation</span></span>](eval-defender-endpoint-enable-eval.md)

<span data-ttu-id="a6059-157">Kehren Sie zur Übersicht für ["Auswerten von Microsoft Defender für Endpunkt"](eval-defender-endpoint-overview.md) zurück.</span><span class="sxs-lookup"><span data-stu-id="a6059-157">Return to the overview for [Evaluate Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)</span></span>

<span data-ttu-id="a6059-158">Kehren Sie zur Übersicht für [Evaluierungs- und Pilot-Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a6059-158">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>