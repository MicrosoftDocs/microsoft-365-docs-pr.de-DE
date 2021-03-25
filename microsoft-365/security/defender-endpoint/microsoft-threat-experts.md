---
title: Microsoft-Bedrohungsexperten
ms.reviewer: ''
description: Microsoft Threat Experts bietet Microsoft Defender for Endpoint eine zusätzliche Kompetenzebene.
keywords: Managed Threat Hunting Service, Managed Threat Hunting, Managed Detection and Response (MDR) Service, MTE, Microsoft Threat Experts, MTE-TAN, targeted attack notification, Targeted Attack Notification
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
ms.openlocfilehash: 466e67bb4649f8cf87e4152a07122d57c5071b79
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185575"
---
# <a name="microsoft-threat-experts"></a><span data-ttu-id="911da-104">Microsoft-Bedrohungsexperten</span><span class="sxs-lookup"><span data-stu-id="911da-104">Microsoft Threat Experts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="911da-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="911da-105">**Applies to:**</span></span>
- [<span data-ttu-id="911da-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="911da-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="911da-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="911da-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="911da-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="911da-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="911da-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="911da-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="911da-110">Microsoft Threat Experts ist ein verwalteter Bedrohungssuchedienst, der Ihren Security Operation Centers (SOCs) Überwachung und Analyse auf Expertenebene bietet, um sicherzustellen, dass kritische Bedrohungen in Ihren einzigartigen Umgebungen nicht übersehen werden.</span><span class="sxs-lookup"><span data-stu-id="911da-110">Microsoft Threat Experts is a managed threat hunting service that provides your Security Operation Centers (SOCs) with expert level monitoring and analysis to help them ensure that critical threats in your unique environments don’t get missed.</span></span>
  
<span data-ttu-id="911da-111">Dieser dienst für die Suche nach verwalteten Bedrohungen bietet expertengesteuerte Einblicke und Daten über diese beiden Funktionen: gezielte Angriffsbenachrichtigung und Zugriff auf Experten bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="911da-111">This managed threat hunting service provides expert-driven insights and data through these two capabilities: targeted attack notification and access to experts on demand.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="911da-112">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="911da-112">Before you begin</span></span> 
> [!NOTE]
> <span data-ttu-id="911da-113">Besprechen Sie die Berechtigungsanforderungen mit Ihrem Microsoft Technical Service-Anbieter und Ihrem Kontoteam, bevor Sie sich auf den dienst für die Suche nach verwalteten Bedrohungen bewerben.</span><span class="sxs-lookup"><span data-stu-id="911da-113">Discuss the eligibility requirements with your Microsoft Technical Service provider and account team before you apply to the managed threat hunting service.</span></span>

<span data-ttu-id="911da-114">Wenn Sie Microsoft Defender for Endpoint-Kunde sind, müssen Sie microsoft **Threat Experts – Targeted Attack Notifications** beantragen, um spezielle Einblicke und Analysen zu erhalten, die ihnen helfen, die wichtigsten Bedrohungen in Ihrer Umgebung zu identifizieren, damit Sie schnell darauf reagieren können.</span><span class="sxs-lookup"><span data-stu-id="911da-114">If you're a Microsoft Defender for Endpoint customer, you need to apply for **Microsoft Threat Experts - Targeted Attack Notifications** to get special insights and analysis that help identify the most critical threats in your environment so you can respond to them quickly</span></span>

<span data-ttu-id="911da-115">Um sich bei Microsoft Threat Experts – Vorteile für gezielte Angriffsbenachrichtigungen zu registrieren, wechseln Sie zu **Einstellungen** Allgemeine erweiterte Features  >    >    >  **Microsoft Threat Experts – Targeted Attack Notifications,** um zu gelten.</span><span class="sxs-lookup"><span data-stu-id="911da-115">To enroll to Microsoft Threat Experts - Targeted Attack Notifications benefits, go to **Settings** > **General** > **Advanced features** > **Microsoft Threat Experts - Targeted Attack Notifications** to apply.</span></span> <span data-ttu-id="911da-116">Sobald sie akzeptiert wurden, erhalten Sie die Vorteile von Benachrichtigungen über gezielte Angriffe.</span><span class="sxs-lookup"><span data-stu-id="911da-116">Once accepted, you will get the benefits of Targeted Attack Notifications.</span></span>

<span data-ttu-id="911da-117">Wenden Sie sich an Ihr Kontoteam oder Ihren Microsoft-Vertreter, um **Microsoft Threat Experts – Experts on Demand** zu abonnieren, um sich mit unseren Bedrohungsexperten zu relevanten Erkennungen und Gegnern in Ihrer Organisation zu beraten.</span><span class="sxs-lookup"><span data-stu-id="911da-117">Contact your account team or Microsoft representative to subscribe to **Microsoft Threat Experts - Experts on Demand** to consult with our threat experts on relevant detections and adversaries that your organization is facing.</span></span>

<span data-ttu-id="911da-118">Weitere [Informationen finden Sie unter Configure Microsoft Threat Experts capabilities.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#before-you-begin)</span><span class="sxs-lookup"><span data-stu-id="911da-118">See [Configure Microsoft Threat Experts capabilities](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#before-you-begin) for details.</span></span> 

## <a name="microsoft-threat-experts---targeted-attack-notification"></a><span data-ttu-id="911da-119">Microsoft Threat Experts – Benachrichtigung über gezielte Angriffe</span><span class="sxs-lookup"><span data-stu-id="911da-119">Microsoft Threat Experts - Targeted attack notification</span></span> 
<span data-ttu-id="911da-120">Microsoft Threat Experts – Die Benachrichtigung über gezielte Angriffe bietet proaktive Suche nach den wichtigsten Bedrohungen für Ihr Netzwerk, z. B. Angriffe von menschlichen Angreifern, Hands-on-Keyboard-Angriffen oder erweiterten Angriffen wie Cyberspionage.</span><span class="sxs-lookup"><span data-stu-id="911da-120">Microsoft Threat Experts - Targeted attack notification provides proactive hunting for the most important threats to your network, including human adversary intrusions, hands-on-keyboard attacks, or advanced attacks like cyber-espionage.</span></span> <span data-ttu-id="911da-121">Diese Benachrichtigungen werden als neue Warnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="911da-121">These notifications shows up as a new alert.</span></span> <span data-ttu-id="911da-122">Der verwaltete Suchesdienst umfasst:</span><span class="sxs-lookup"><span data-stu-id="911da-122">The managed hunting service includes:</span></span>  
- <span data-ttu-id="911da-123">Überwachung und Analyse von Bedrohungen, Reduzierung der Verweilzeit und des Risikos für das Unternehmen</span><span class="sxs-lookup"><span data-stu-id="911da-123">Threat monitoring and analysis, reducing dwell time and risk to the business</span></span> 
- <span data-ttu-id="911da-124">Von Jägern geschulte künstliche Intelligenz zum Ermitteln und Priorisieren bekannter und unbekannter Angriffe</span><span class="sxs-lookup"><span data-stu-id="911da-124">Hunter-trained artificial intelligence to discover and prioritize both known and unknown attacks</span></span>  
- <span data-ttu-id="911da-125">Identifizieren der wichtigsten Risiken, die so beitragen, dass SOCs Zeit und Energie maximieren</span><span class="sxs-lookup"><span data-stu-id="911da-125">Identifying the most important risks, helping SOCs maximize time and energy</span></span> 
- <span data-ttu-id="911da-126">Umfang der Kompromisse und so viel Kontext, wie schnell zugestellt werden kann, um eine schnelle SOC-Antwort zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="911da-126">Scope of compromise and as much context as can be quickly delivered to enable fast SOC response.</span></span> 
 
## <a name="microsoft-threat-experts---experts-on-demand"></a><span data-ttu-id="911da-127">Microsoft Threat Experts – Experten bei Bedarf</span><span class="sxs-lookup"><span data-stu-id="911da-127">Microsoft Threat Experts - Experts on Demand</span></span>
<span data-ttu-id="911da-128">Kunden können unsere Sicherheitsexperten direkt im Microsoft Defender Security Center für eine zeitnahe und genaue Antwort kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="911da-128">Customers can engage our security experts directly from within Microsoft Defender Security Center for timely and accurate response.</span></span> <span data-ttu-id="911da-129">Experten bieten Einblicke, die erforderlich sind, um die komplexen Bedrohungen, die Ihre Organisation betreffen, besser zu verstehen, von Warnungsanfragen, potenziell gefährdeten Geräten, der Hauptursache einer verdächtigen Netzwerkverbindung bis zu zusätzlicher Bedrohungsintelligenz im Zusammenhang mit laufenden erweiterten Kampagnen für dauerhafte Bedrohungen.</span><span class="sxs-lookup"><span data-stu-id="911da-129">Experts provide insights needed to better understand the complex threats affecting your organization, from alert inquiries, potentially compromised devices, root cause of a suspicious network connection, to additional threat intelligence regarding ongoing advanced persistent threat campaigns.</span></span> <span data-ttu-id="911da-130">Mit dieser Funktion können Sie:</span><span class="sxs-lookup"><span data-stu-id="911da-130">With this capability, you can:</span></span>
- <span data-ttu-id="911da-131">Weitere Erläuterungen zu Warnungen, einschließlich der Ursache oder des Umfangs des Vorfalls, erhalten</span><span class="sxs-lookup"><span data-stu-id="911da-131">Get additional clarification on alerts including root cause or scope of the incident</span></span> 
- <span data-ttu-id="911da-132">Verschaffen Sie sich Klarheit über das Verhalten verdächtiger Geräte und die nächsten Schritte, wenn sie mit einem erweiterten Angreifer konfrontiert werden</span><span class="sxs-lookup"><span data-stu-id="911da-132">Gain clarity into suspicious device behavior and next steps if faced with an advanced attacker</span></span>  
- <span data-ttu-id="911da-133">Bestimmen des Risikos und des Schutzes von Bedrohungsakteuren, Kampagnen oder neuen Angreifertechniken</span><span class="sxs-lookup"><span data-stu-id="911da-133">Determine risk and protection regarding threat actors, campaigns, or emerging attacker techniques</span></span> 

<span data-ttu-id="911da-134">Die Option, **einen Bedrohungsexperten** zu konsultieren, steht an mehreren Stellen im Portal zur Verfügung, sodass Sie im Rahmen Ihrer Untersuchung mit Experten interagieren können:</span><span class="sxs-lookup"><span data-stu-id="911da-134">The option to **Consult a threat expert** is available in several places in the portal so you can engage with experts in the context of your investigation:</span></span>

- <span data-ttu-id="911da-135"><i>**Hilfe- und Supportmenü**</i></span><span class="sxs-lookup"><span data-stu-id="911da-135"><i>**Help and support menu**</i></span></span><BR>
<span data-ttu-id="911da-136">![Screenshot der MTE-EOD-Menüoption](images/mte-eod-menu.png)</span><span class="sxs-lookup"><span data-stu-id="911da-136">![Screenshot of MTE-EOD menu option](images/mte-eod-menu.png)</span></span>

- <span data-ttu-id="911da-137"><i>**Menü "Geräteseitenaktionen"**</i></span><span class="sxs-lookup"><span data-stu-id="911da-137"><i>**Device page actions menu**</i></span></span><BR>
<span data-ttu-id="911da-138">![Screenshot der MTE-EOD-Aktionsmenüoption für Geräteseiten](images/mte-eod-machines.png)</span><span class="sxs-lookup"><span data-stu-id="911da-138">![Screenshot of MTE-EOD device page action menu option](images/mte-eod-machines.png)</span></span>

- <span data-ttu-id="911da-139"><i>**Menü Benachrichtigungen für Seitenaktionen**</i></span><span class="sxs-lookup"><span data-stu-id="911da-139"><i>**Alerts page actions menu**</i></span></span><BR>
<span data-ttu-id="911da-140">![Screenshot der Menüoption MTE-EOD-Warnungsseite](images/mte-eod-alerts.png)</span><span class="sxs-lookup"><span data-stu-id="911da-140">![Screenshot of MTE-EOD alert page action menu option](images/mte-eod-alerts.png)</span></span>

- <span data-ttu-id="911da-141"><i>**Menü "Dateiseitenaktionen"**</i></span><span class="sxs-lookup"><span data-stu-id="911da-141"><i>**File page actions menu**</i></span></span><BR>
<span data-ttu-id="911da-142">![Screenshot der MTE-EOD-Dateiseiten-Aktionsmenüoption](images/mte-eod-file.png)</span><span class="sxs-lookup"><span data-stu-id="911da-142">![Screenshot of MTE-EOD file page action menu option](images/mte-eod-file.png)</span></span>

> [!NOTE]
> <span data-ttu-id="911da-143">Wenn Sie den Status Ihrer Experts on Demand-Fälle über Microsoft Services Hub nachverfolgen möchten, erreichen Sie Ihren Technical Account Manager.</span><span class="sxs-lookup"><span data-stu-id="911da-143">If you would like to track the status of your Experts on Demand cases through Microsoft Services Hub, reach out to your Technical Account Manager.</span></span> 

<span data-ttu-id="911da-144">Sehen Sie sich dieses Video an, um einen schnellen Überblick über den Microsoft Services Hub zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="911da-144">Watch this video for a quick overview of the Microsoft Services Hub.</span></span>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f] 

   
## <a name="related-topic"></a><span data-ttu-id="911da-145">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="911da-145">Related topic</span></span>
- [<span data-ttu-id="911da-146">Konfigurieren von Microsoft Threat Experts-Funktionen</span><span class="sxs-lookup"><span data-stu-id="911da-146">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md)
