---
title: Microsoft-Bedrohungsexperten
ms.reviewer: ''
description: Microsoft-Bedrohungsexperten bietet Microsoft Defender für Endpunkt eine zusätzliche Expertise.
keywords: Managed Threat Hunting Service, Managed Threat Hunting, Managed Detection and Response (MDR)-Dienst, MTE, Microsoft-Bedrohungsexperten, MTE-TAN, Benachrichtigung über gezielte Angriffe, Benachrichtigung über gezielte Angriffe
search.product: Windows 10
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ebde023db5196117a02a2372784a3110839c51fa
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843530"
---
# <a name="microsoft-threat-experts"></a><span data-ttu-id="4eb7c-104">Microsoft-Bedrohungsexperten</span><span class="sxs-lookup"><span data-stu-id="4eb7c-104">Microsoft Threat Experts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4eb7c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="4eb7c-105">**Applies to:**</span></span>
- [<span data-ttu-id="4eb7c-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="4eb7c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4eb7c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4eb7c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4eb7c-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="4eb7c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4eb7c-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="4eb7c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="4eb7c-110">Microsoft-Bedrohungsexperten ist ein verwalteter Dienst für die Bedrohungssuche, der Ihren Security Operation Centers (SOCs) Überwachung und Analyse auf Expertenebene bereitstellt, um sicherzustellen, dass kritische Bedrohungen in Ihren einzigartigen Umgebungen nicht übersehen werden.</span><span class="sxs-lookup"><span data-stu-id="4eb7c-110">Microsoft Threat Experts is a managed threat hunting service that provides your Security Operation Centers (SOCs) with expert level monitoring and analysis to help them ensure that critical threats in your unique environments don’t get missed.</span></span>
  
<span data-ttu-id="4eb7c-111">Dieser Dienst für die verwaltete Bedrohungssuche bietet expertengesteuerte Einblicke und Daten über diese beiden Funktionen: gezielte Angriffsbenachrichtigung und Zugriff auf Experten bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="4eb7c-111">This managed threat hunting service provides expert-driven insights and data through these two capabilities: targeted attack notification and access to experts on demand.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4eb7c-112">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="4eb7c-112">Before you begin</span></span> 
> [!NOTE]
> <span data-ttu-id="4eb7c-113">Besprechen Sie die Berechtigungsanforderungen mit Ihrem Microsoft Technical Service-Anbieter und Ihrem Kontoteam, bevor Sie sich auf den Verwalteten Dienst für die Bedrohungssuche anwenden.</span><span class="sxs-lookup"><span data-stu-id="4eb7c-113">Discuss the eligibility requirements with your Microsoft Technical Service provider and account team before you apply to the managed threat hunting service.</span></span>

<span data-ttu-id="4eb7c-114">Wenn Sie Ein Kunde von Microsoft Defender für Endpunkt sind, müssen Sie Microsoft-Bedrohungsexperten – **Benachrichtigungen** über gezielte Angriffe beantragen, um spezielle Einblicke und Analysen zu erhalten, die ihnen helfen, die kritischsten Bedrohungen in Ihrer Umgebung zu identifizieren, damit Sie schnell darauf reagieren können.</span><span class="sxs-lookup"><span data-stu-id="4eb7c-114">If you're a Microsoft Defender for Endpoint customer, you need to apply for **Microsoft Threat Experts - Targeted Attack Notifications** to get special insights and analysis that help identify the most critical threats in your environment so you can respond to them quickly</span></span>

<span data-ttu-id="4eb7c-115">Wenn Sie sich für Microsoft-Bedrohungsexperten – Vorteile von gezielten Angriffsbenachrichtigungen – registrieren möchten, wechseln Sie zu **Einstellungen**  >  **allgemeinen**  >  **erweiterten Features** Microsoft-Bedrohungsexperten –  >  **Zutreffende gezielte Angriffsbenachrichtigungen.**</span><span class="sxs-lookup"><span data-stu-id="4eb7c-115">To enroll to Microsoft Threat Experts - Targeted Attack Notifications benefits, go to **Settings** > **General** > **Advanced features** > **Microsoft Threat Experts - Targeted Attack Notifications** to apply.</span></span> <span data-ttu-id="4eb7c-116">Nach der Annahme erhalten Sie die Vorteile von Benachrichtigungen über gezielte Angriffe.</span><span class="sxs-lookup"><span data-stu-id="4eb7c-116">Once accepted, you will get the benefits of Targeted Attack Notifications.</span></span>

<span data-ttu-id="4eb7c-117">Wenden Sie sich an Ihr Kontoteam oder einen Microsoft-Mitarbeiter, um Microsoft-Bedrohungsexperten – **Experts on Demand** zu abonnieren, um sich mit unseren Bedrohungsexperten über relevante Erkennungen und Angreifer zu beraten, mit denen Ihre Organisation konfrontiert ist.</span><span class="sxs-lookup"><span data-stu-id="4eb7c-117">Contact your account team or Microsoft representative to subscribe to **Microsoft Threat Experts - Experts on Demand** to consult with our threat experts on relevant detections and adversaries that your organization is facing.</span></span>

<span data-ttu-id="4eb7c-118">Weitere Informationen finden Sie unter [Konfigurieren Microsoft-Bedrohungsexperten Funktionen.](/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#before-you-begin)</span><span class="sxs-lookup"><span data-stu-id="4eb7c-118">See [Configure Microsoft Threat Experts capabilities](/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#before-you-begin) for details.</span></span> 

## <a name="microsoft-threat-experts---targeted-attack-notification"></a><span data-ttu-id="4eb7c-119">Microsoft-Bedrohungsexperten – Benachrichtigung über gezielte Angriffe</span><span class="sxs-lookup"><span data-stu-id="4eb7c-119">Microsoft Threat Experts - Targeted attack notification</span></span> 
<span data-ttu-id="4eb7c-120">Microsoft-Bedrohungsexperten : Die Benachrichtigung über gezielte Angriffe ermöglicht die proaktive Suche nach den wichtigsten Bedrohungen für Ihr Netzwerk, einschließlich Angreiferangriffen, praktischen Tastaturangriffen oder fortgeschrittenen Angriffen wie Cyber-E-Mails.</span><span class="sxs-lookup"><span data-stu-id="4eb7c-120">Microsoft Threat Experts - Targeted attack notification provides proactive hunting for the most important threats to your network, including human adversary intrusions, hands-on-keyboard attacks, or advanced attacks like cyber-espionage.</span></span> <span data-ttu-id="4eb7c-121">Diese Benachrichtigungen werden als neue Warnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4eb7c-121">These notifications shows up as a new alert.</span></span> <span data-ttu-id="4eb7c-122">Der verwaltete Suchdienst umfasst:</span><span class="sxs-lookup"><span data-stu-id="4eb7c-122">The managed hunting service includes:</span></span>  
- <span data-ttu-id="4eb7c-123">Bedrohungsüberwachung und -analyse, Reduzierung der Verweilzeit und des Risikos für das Unternehmen</span><span class="sxs-lookup"><span data-stu-id="4eb7c-123">Threat monitoring and analysis, reducing dwell time and risk to the business</span></span> 
- <span data-ttu-id="4eb7c-124">Von Hunter trainierte künstliche Intelligenz, um bekannte und unbekannte Angriffe zu erkennen und zu priorisieren</span><span class="sxs-lookup"><span data-stu-id="4eb7c-124">Hunter-trained artificial intelligence to discover and prioritize both known and unknown attacks</span></span>  
- <span data-ttu-id="4eb7c-125">Identifizieren der wichtigsten Risiken, die SOCs dabei helfen, Zeit und Energie zu maximieren</span><span class="sxs-lookup"><span data-stu-id="4eb7c-125">Identifying the most important risks, helping SOCs maximize time and energy</span></span> 
- <span data-ttu-id="4eb7c-126">Umfang der Kompromittierung und so viel Kontext wie möglich schnell bereitgestellt werden können, um eine schnelle SOC-Antwort zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="4eb7c-126">Scope of compromise and as much context as can be quickly delivered to enable fast SOC response.</span></span> 
 
## <a name="microsoft-threat-experts---experts-on-demand"></a><span data-ttu-id="4eb7c-127">Microsoft-Bedrohungsexperten – Experten bei Bedarf</span><span class="sxs-lookup"><span data-stu-id="4eb7c-127">Microsoft Threat Experts - Experts on Demand</span></span>
<span data-ttu-id="4eb7c-128">Kunden können unsere Sicherheitsexperten direkt aus Microsoft Defender Security Center für eine zeitnahe und genaue Antwort einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="4eb7c-128">Customers can engage our security experts directly from within Microsoft Defender Security Center for timely and accurate response.</span></span> <span data-ttu-id="4eb7c-129">Experten bieten Einblicke, die erforderlich sind, um die komplexen Bedrohungen, die Sich auf Ihre Organisation auswirken, besser zu verstehen, von Warnungsanfragen, potenziell kompromittierten Geräten, der Ursache einer verdächtigen Netzwerkverbindung bis hin zu zusätzlichen Bedrohungsinformationen in Bezug auf laufende fortgeschrittene dauerhafte Bedrohungskampagnen.</span><span class="sxs-lookup"><span data-stu-id="4eb7c-129">Experts provide insights needed to better understand the complex threats affecting your organization, from alert inquiries, potentially compromised devices, root cause of a suspicious network connection, to additional threat intelligence regarding ongoing advanced persistent threat campaigns.</span></span> <span data-ttu-id="4eb7c-130">Mit dieser Funktion können Sie:</span><span class="sxs-lookup"><span data-stu-id="4eb7c-130">With this capability, you can:</span></span>
- <span data-ttu-id="4eb7c-131">Erhalten Sie zusätzliche Erläuterungen zu Warnungen, einschließlich der Ursache oder des Umfangs des Vorfalls</span><span class="sxs-lookup"><span data-stu-id="4eb7c-131">Get additional clarification on alerts including root cause or scope of the incident</span></span> 
- <span data-ttu-id="4eb7c-132">Verschaffen Sie sich Klarheit über verdächtiges Geräteverhalten und die nächsten Schritte, wenn Sie mit einem erweiterten Angreifer konfrontiert sind.</span><span class="sxs-lookup"><span data-stu-id="4eb7c-132">Gain clarity into suspicious device behavior and next steps if faced with an advanced attacker</span></span>  
- <span data-ttu-id="4eb7c-133">Ermitteln von Risiken und Schutz in Bezug auf Bedrohungsteilnehmer, Kampagnen oder neue Angreifertechniken</span><span class="sxs-lookup"><span data-stu-id="4eb7c-133">Determine risk and protection regarding threat actors, campaigns, or emerging attacker techniques</span></span> 

<span data-ttu-id="4eb7c-134">Die Möglichkeit, **einen Bedrohungsexperten** zu konsultieren, ist an mehreren Stellen im Portal verfügbar, sodass Sie sich im Rahmen Ihrer Untersuchung mit Experten in Verbindung setzen können:</span><span class="sxs-lookup"><span data-stu-id="4eb7c-134">The option to **Consult a threat expert** is available in several places in the portal so you can engage with experts in the context of your investigation:</span></span>

- <span data-ttu-id="4eb7c-135"><i>**Menü "Hilfe und Support"**</i></span><span class="sxs-lookup"><span data-stu-id="4eb7c-135"><i>**Help and support menu**</i></span></span><BR>
<span data-ttu-id="4eb7c-136">![Screenshot der MTE-EOD-Menüoption](images/mte-eod-menu.png)</span><span class="sxs-lookup"><span data-stu-id="4eb7c-136">![Screenshot of MTE-EOD menu option](images/mte-eod-menu.png)</span></span>

- <span data-ttu-id="4eb7c-137"><i>**Menü "Geräteseitenaktionen"**</i></span><span class="sxs-lookup"><span data-stu-id="4eb7c-137"><i>**Device page actions menu**</i></span></span><BR>
<span data-ttu-id="4eb7c-138">![Screenshot der Aktionsmenüoption "MTE-EOD-Geräteseite"](images/mte-eod-machines.png)</span><span class="sxs-lookup"><span data-stu-id="4eb7c-138">![Screenshot of MTE-EOD device page action menu option](images/mte-eod-machines.png)</span></span>

- <span data-ttu-id="4eb7c-139"><i>**Menü "Warnungsseitenaktionen"**</i></span><span class="sxs-lookup"><span data-stu-id="4eb7c-139"><i>**Alerts page actions menu**</i></span></span><BR>
<span data-ttu-id="4eb7c-140">![Screenshot der Aktionsmenüoption "MTE-EOD-Warnungsseite"](images/mte-eod-alerts.png)</span><span class="sxs-lookup"><span data-stu-id="4eb7c-140">![Screenshot of MTE-EOD alert page action menu option](images/mte-eod-alerts.png)</span></span>

- <span data-ttu-id="4eb7c-141"><i>**Menü "Dateiseitenaktionen"**</i></span><span class="sxs-lookup"><span data-stu-id="4eb7c-141"><i>**File page actions menu**</i></span></span><BR>
<span data-ttu-id="4eb7c-142">![Screenshot der Aktionsmenüoption "MTE-EOD-Dateiseite"](images/mte-eod-file.png)</span><span class="sxs-lookup"><span data-stu-id="4eb7c-142">![Screenshot of MTE-EOD file page action menu option](images/mte-eod-file.png)</span></span>

> [!NOTE]
> <span data-ttu-id="4eb7c-143">Wenn Sie den Status Ihrer Experts on Demand-Fälle über den Microsoft Services Hub nachverfolgen möchten, wenden Sie sich an Ihren Technical Account Manager.</span><span class="sxs-lookup"><span data-stu-id="4eb7c-143">If you would like to track the status of your Experts on Demand cases through Microsoft Services Hub, reach out to your Technical Account Manager.</span></span> 

<span data-ttu-id="4eb7c-144">Sehen Sie sich dieses Video an, um einen schnellen Überblick über den Microsoft Services Hub zu geben.</span><span class="sxs-lookup"><span data-stu-id="4eb7c-144">Watch this video for a quick overview of the Microsoft Services Hub.</span></span>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f] 

   
## <a name="related-topic"></a><span data-ttu-id="4eb7c-145">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="4eb7c-145">Related topic</span></span>
- [<span data-ttu-id="4eb7c-146">Konfigurieren Microsoft-Bedrohungsexperten Funktionen</span><span class="sxs-lookup"><span data-stu-id="4eb7c-146">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md)
