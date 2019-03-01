---
title: Bereitstellungsstrategien für die Foundation-Infrastruktur von Microsoft 365 Enterprise
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 01/23/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Erfahren Sie mehr darüber, wie Sie die Phasen der Foundation-Infrastruktur für Microsoft 365 Enterprise bereitstellen können.
ms.openlocfilehash: fb4cf301f1e450cd5db9b392c0ca2d8e3767242a
ms.sourcegitcommit: e749e2db2a15bb52b1a2857dbccdf55c31cff3d7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "30340115"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure-deployment-strategies"></a><span data-ttu-id="c4d01-103">Bereitstellungsstrategien für die Foundation-Infrastruktur von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c4d01-103">Microsoft 365 Enterprise foundation infrastructure deployment strategies</span></span>

<span data-ttu-id="c4d01-p101">Es gibt viele Möglichkeiten, die Phasen der [Foundation-Infrastruktur](deploy-foundation-infrastructure.md) von Microsoft 365 Enterprise zu nutzen und ihre Funktionen, Software und Dienste für Ihre Benutzer bereitzustellen. Um mit dem Projektmanagement dieses Vorhabens zu beginnen, das je nach Größe Ihres Unternehmens und der vorhandenen Infrastruktur groß und komplex sein kann, sollten Sie die folgenden Bereitstellungsstrategien in Betracht ziehen:</span><span class="sxs-lookup"><span data-stu-id="c4d01-p101">There are many ways you can deploy the phases of the [foundation infrastructure](deploy-foundation-infrastructure.md) of Microsoft 365 Enterprise and roll out its capabilities, software, and services to your users. To get you started on the project management of this undertaking, which can be large and complex depending on the size of your organization and its existing infrastructure, consider the following deployment strategies:</span></span>

- <span data-ttu-id="c4d01-106">Serielle Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="c4d01-106">Serial deployment</span></span>
- <span data-ttu-id="c4d01-107">Parallele Bereitstellung mit nicht überlappendem Benutzerrollout</span><span class="sxs-lookup"><span data-stu-id="c4d01-107">Parallel deployment with non-overlapping user rollout</span></span>
- <span data-ttu-id="c4d01-108">Parallele Bereitstellung mit überlappendem Benutzerrollout</span><span class="sxs-lookup"><span data-stu-id="c4d01-108">Parallel deployment with overlapping user rollout</span></span>
- <span data-ttu-id="c4d01-109">Vorabinfrastruktur und Rollout der End-to-End-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c4d01-109">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

<span data-ttu-id="c4d01-110">Nutzen Sie diese Strategien für Ideen, wie Sie das Gesamtprojekt verwalten und die Geschäftsvorteile von Microsoft 365 Enterprise schneller nutzen können.</span><span class="sxs-lookup"><span data-stu-id="c4d01-110">Use these strategies for ideas on how to manage the overall project and more quickly realize the business benefits of Microsoft 365 Enterprise.</span></span>

>[!Note]
><span data-ttu-id="c4d01-p102">Dieser Artikel enthält Annahmen und Vereinfachungen für eine einheitliche Beschreibung der Bereitstellungsstrategien. Diese Bereitstellungsstrategien sind verallgemeinert und sollen weder einen bestimmten Zeitrahmen implizieren, noch sollen sie für alle Organisationen und Situationen gelten.</span><span class="sxs-lookup"><span data-stu-id="c4d01-p102">This article contains assumptions and simplifications for a consistent way to describe the deployment strategies. These deployment strategies are generalized and are not meant to imply any specific timeframes, nor are they meant to apply to all organizations and situations.</span></span>
>

## <a name="elements-of-it-project-management-for-typical-enterprise-organizations"></a><span data-ttu-id="c4d01-113">Elemente des IT-Projektmanagements für typische Unternehmensorganisationen</span><span class="sxs-lookup"><span data-stu-id="c4d01-113">Elements of IT project management for typical enterprise organizations</span></span>

<span data-ttu-id="c4d01-p103">Die IT-Infrastruktur umfasst sowohl Back-End-Dienste als auch die Einführung neuer oder verbesserter Funktionen oder installierter Software für Endbenutzer. IT-Abteilungen setzen in der Regel Elemente einer IT-Infrastruktur methodisch ein. Ein Ansatz für die erfolgreiche Bereitstellung eines Elements der IT-Infrastruktur berücksichtigt die folgenden Aspekte:</span><span class="sxs-lookup"><span data-stu-id="c4d01-p103">IT infrastructure includes both backend services and the rollout of new or improved capabilities or installed software to end users. IT departments typically deploy elements of an IT infrastructure in a methodical way. One approach to the successful deployment of an element of IT infrastructure consists of:</span></span>

- <span data-ttu-id="c4d01-117">Eine Pilotbereitstellung</span><span class="sxs-lookup"><span data-stu-id="c4d01-117">A pilot rollout</span></span> 

  <span data-ttu-id="c4d01-118">Dazu gehören die anfängliche Infrastrukturkonfiguration und das Rollout für eine Pilotgruppe von Benutzern, das Testen und spätere Änderungen der Infrastrukturkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="c4d01-118">This includes initial infrastructure configuration and rollout to a pilot set of users, testing, and subsequent modifications to the infrastructure configuration.</span></span>

- <span data-ttu-id="c4d01-119">Eine Benutzerbereitstellung</span><span class="sxs-lookup"><span data-stu-id="c4d01-119">A user rollout</span></span>

  <span data-ttu-id="c4d01-120">Dazu gehört auch das Rollout für den Rest Ihres Unternehmens basierend auf Regionen, Abteilungen, Gruppen oder anderen Arten der systematischen Verteilung von Konfiguration oder Software.</span><span class="sxs-lookup"><span data-stu-id="c4d01-120">This includes the rollout to the rest of your organization based on regions, departments, groups, or other types of systematic propagation of configuration or software.</span></span>

<span data-ttu-id="c4d01-121">Die Benutzergruppe im Pilotrollout ist nicht identisch mit derjenigen im Benutzerrollout.</span><span class="sxs-lookup"><span data-stu-id="c4d01-121">The set of users in the pilot rollout are not the same as those in the user rollout.</span></span>

<span data-ttu-id="c4d01-122">Dieser Artikel verwendet die folgenden Grafikelemente, um diese Definitionen darzustellen:</span><span class="sxs-lookup"><span data-stu-id="c4d01-122">This article uses the following graphics to depict these definitions:</span></span> 

![](./media/deployment-strategies-microsoft-365-enterprise/definitions.png) 

<span data-ttu-id="c4d01-123">Die Schattierung für die Benutzerrolloutgrafik zeigt den Prozentanteil in Ihrem Unternehmen von 0 % bis 100 % mit einem strukturierten oder methodischen Ansatz wie Gruppen, Abteilungen oder Regionen.</span><span class="sxs-lookup"><span data-stu-id="c4d01-123">The shading for the user rollout graphic indicates the percentage across your organization from 0% to 100% using a structured or methodical approach such as groups, departments, or regions.</span></span>

## <a name="deployment-strategies"></a><span data-ttu-id="c4d01-124">Bereitstellungsstrategien</span><span class="sxs-lookup"><span data-stu-id="c4d01-124">Deployment strategies</span></span>

<span data-ttu-id="c4d01-125">Ziehen Sie die folgenden Bereitstellungsstrategien in Betracht:</span><span class="sxs-lookup"><span data-stu-id="c4d01-125">Consider the following deployment strategies:</span></span>

- <span data-ttu-id="c4d01-126">Serielle Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="c4d01-126">Serial deployment</span></span>
- <span data-ttu-id="c4d01-127">Parallele Bereitstellung mit nicht überlappendem Benutzerrollout</span><span class="sxs-lookup"><span data-stu-id="c4d01-127">Parallel deployment with non-overlapping user rollout</span></span>
- <span data-ttu-id="c4d01-128">Parallele Bereitstellung mit überlappendem Benutzerrollout</span><span class="sxs-lookup"><span data-stu-id="c4d01-128">Parallel deployment with overlapping user rollout</span></span>
- <span data-ttu-id="c4d01-129">Vorabinfrastruktur und Rollout der End-to-End-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c4d01-129">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

### <a name="serial-deployment"></a><span data-ttu-id="c4d01-130">Serielle Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="c4d01-130">Serial deployment</span></span>

<span data-ttu-id="c4d01-p104">Bei einer seriellen Bereitstellung führen Sie eine Phase vollständig aus, sodass die Phase einen 100%igen Abschluss der Bereitstellung für alle Ihre Benutzer erreicht, bevor Sie zur nächsten Phase übergehen. Im Folgenden finden Sie einige der Gründe, warum Sie diese Art der Bereitstellung wählen sollten:</span><span class="sxs-lookup"><span data-stu-id="c4d01-p104">With a serial deployment, you completely roll out a phase, allowing the phase to reach 100% completion of deployment to all of your users, before moving on to the next one. Here are some of the reasons why you might deploy this way:</span></span>

- <span data-ttu-id="c4d01-133">Risikominderung</span><span class="sxs-lookup"><span data-stu-id="c4d01-133">Risk mitigation</span></span>
- <span data-ttu-id="c4d01-134">Ressourceneinschränkungen</span><span class="sxs-lookup"><span data-stu-id="c4d01-134">Resourcing constraints</span></span>
- <span data-ttu-id="c4d01-135">Finanzierungszyklen der IT-Abteilung</span><span class="sxs-lookup"><span data-stu-id="c4d01-135">IT department funding cycles</span></span>
- <span data-ttu-id="c4d01-136">IT-Technologieabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="c4d01-136">IT technology dependencies</span></span>
- <span data-ttu-id="c4d01-137">Geschäftsänderungsverwaltung und Endbenutzerresistenz</span><span class="sxs-lookup"><span data-stu-id="c4d01-137">Business change management and end-user resistance</span></span>

<span data-ttu-id="c4d01-138">Dieses Gantt-Diagramm zeigt eine vereinfachte serielle Bereitstellung der Phasen 2 bis 6 der Foundation-Infrastruktur für Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c4d01-138">This Gantt chart shows a simplified serial deployment of phases 2-6 of the foundation infrastructure for Microsoft 365 Enterprise.</span></span>

![](./media/deployment-strategies-microsoft-365-enterprise/serial.png) 
 
<span data-ttu-id="c4d01-139">Um die Erläuterung und das Beispiel zu vereinfachen, wird davon ausgegangen, dass jede Phase und jedes Einsatzsegment innerhalb jeder Phase die gleiche Zeit in Anspruch nimmt.</span><span class="sxs-lookup"><span data-stu-id="c4d01-139">To simplify the discussion and example, each phase and deployment segment within each phase are assumed to take the same amount of time.</span></span>

>[!Note]
><span data-ttu-id="c4d01-p105">Phase 1: Die Vernetzung der Microsoft 365 Enterprise Foundation-Infrastruktur ist eine reine Phase der IT-Abteilung. Benutzer profitieren von den Vorteilen einer optimierten Konnektivität mit den Cloudressourcen von Microsoft, werden aber nicht dazu gezwungen.</span><span class="sxs-lookup"><span data-stu-id="c4d01-p105">Phase 1: Networking of the Microsoft 365 Enterprise Foundation Infrastructure is an IT department-only phase. Users reap the benefits of optimized connectivity to Microsoft’s cloud resources but are not imposed upon to achieve it.</span></span>
>

<span data-ttu-id="c4d01-142">Vereinfachtes Beispiel für eine Pilotprojekt-Benutzererfahrung:</span><span class="sxs-lookup"><span data-stu-id="c4d01-142">Simplified example pilot user experience:</span></span>

- <span data-ttu-id="c4d01-p106">Im Dezember muss ich mein Smartphone für MFA verwenden. (Identität)</span><span class="sxs-lookup"><span data-stu-id="c4d01-p106">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="c4d01-p107">Im März wird Windows 10 Enterprise auf meinem Windows 8.1-Desktopcomputer installiert. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="c4d01-p107">In March, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="c4d01-p108">Im Juni wird Office 365 ProPlus installiert und ersetzt Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="c4d01-p108">In June, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="c4d01-p109">Im September erhalte ich Geräteregistrierung und App, und bedingte Zugriffsrichtlinien werden angewendet. (Verwaltung mobiler Geräte)</span><span class="sxs-lookup"><span data-stu-id="c4d01-p109">In September, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="c4d01-p110">Im Dezember wird der Azure Information Protection-Client installiert, und ich erhalte Schulung, wie Bezeichnungen auf Dokumente angewendet werden. (Information Protection)</span><span class="sxs-lookup"><span data-stu-id="c4d01-p110">In December, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="c4d01-153">Das Ergebnis ist eine Kadenz von 90 Tagen zwischen den aufeinanderfolgenden Pilotrollouts.</span><span class="sxs-lookup"><span data-stu-id="c4d01-153">The result is a 90-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="c4d01-154">Vereinfachtes Beispiel für eine Endbenutzererfahrung:</span><span class="sxs-lookup"><span data-stu-id="c4d01-154">Simplified example end-user experience:</span></span>

- <span data-ttu-id="c4d01-p111">Im Januar muss ich mein Smartphone für MFA verwenden. (Identität)</span><span class="sxs-lookup"><span data-stu-id="c4d01-p111">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="c4d01-p112">Im April wird Windows 10 Enterprise auf meinem Windows 8.1-Desktopcomputer installiert. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="c4d01-p112">In April, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="c4d01-p113">Im Juli wird Office 365 ProPlus installiert und ersetzt Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="c4d01-p113">In July, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="c4d01-p114">Im Oktober erhalte ich Geräteregistrierung und App, und bedingte Zugriffsrichtlinien werden angewendet. (Verwaltung mobiler Geräte)</span><span class="sxs-lookup"><span data-stu-id="c4d01-p114">In October, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="c4d01-p115">Im Januar des Folgejahres wird der Azure Information Protection-Client installiert, und ich erhalte Schulung, wie Bezeichnungen auf Dokumente angewendet werden. (Information Protection)</span><span class="sxs-lookup"><span data-stu-id="c4d01-p115">In January of the following year, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="c4d01-165">Das Ergebnis ist eine Kadenz von 90 Tagen zwischen den aufeinanderfolgenden Benutzerrollouts.</span><span class="sxs-lookup"><span data-stu-id="c4d01-165">The result is a 90-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="c4d01-166">Der Nachteil dieser Bereitstellungsstrategie besteht darin, dass es lange dauern kann, bis die Microsoft 365 Enterprise Foundation-Infrastruktur vollständig bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c4d01-166">The disadvantage to this deployment strategy is that it can take a long time to fully deploy the Microsoft 365 Enterprise foundation infrastructure.</span></span>

### <a name="parallel-deployment-with-non-overlapping-user-rollout-parallel-1"></a><span data-ttu-id="c4d01-167">Parallele Bereitstellung mit nicht überlappendem Benutzerrollout (Parallel 1)</span><span class="sxs-lookup"><span data-stu-id="c4d01-167">Parallel deployment with non-overlapping user rollout (Parallel 1)</span></span>

<span data-ttu-id="c4d01-p116">Für diese Bereitstellungsstrategie starten Sie das Pilotrollout der nächsten Phase im letzten Teil des Benutzerrollouts der aktuellen Phase. Hier findet die Bereitstellung der Phasen 2 bis 6 statt, wenn das Pilotrollout stattfindet, während das Benutzerrollout der vorherigen Phase abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="c4d01-p116">For this deployment strategy, you start the pilot rollout of the next phase during the last part of the user rollout of the current phase. Here is the deployment of phases 2-6 when the pilot rollout occurs as the user rollout of the previous phase is wrapping up.</span></span>

<span data-ttu-id="c4d01-170">Dies ist ein vereinfachter Vergleich zwischen parallelen und seriellen Bereitstellungsstrategien.</span><span class="sxs-lookup"><span data-stu-id="c4d01-170">Here is a simplified comparison between parallel and serial deployment strategies.</span></span>

![](./media/deployment-strategies-microsoft-365-enterprise/parallel1.png) 
 
<span data-ttu-id="c4d01-p117">Das Endergebnis ist, dass das Benutzerrollout für die aktuelle Phase in Ihrem Unternehmen abgeschlossen ist, bevor die nächste Phase beginnt. Benutzer, die sich nicht in Pilotrollouts befinden, befassen sich nicht gleichzeitig mit den Rollouts mehrerer Phasen, aber Pilotrollouts werden parallel zu Benutzerrollouts durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="c4d01-p117">The end result is that user rollout for the current phase completes across your organization before the next one starts. Users that are not in pilot rollouts are not dealing with the rollouts of multiple phases at the same time, but pilot rollouts are done in parallel with user rollouts.</span></span>

<span data-ttu-id="c4d01-173">Vereinfachtes Beispiel für eine Pilotprojekt-Benutzererfahrung:</span><span class="sxs-lookup"><span data-stu-id="c4d01-173">Simplified example pilot user experience:</span></span> 

- <span data-ttu-id="c4d01-p118">Im Dezember muss ich mein Smartphone für MFA verwenden. (Identität)</span><span class="sxs-lookup"><span data-stu-id="c4d01-p118">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="c4d01-p119">Im Februar wird Windows 10 Enterprise auf meinem Windows 8.1-Desktopcomputer installiert. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="c4d01-p119">In February, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="c4d01-p120">Im April wird Office 365 ProPlus installiert und ersetzt Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="c4d01-p120">In April, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="c4d01-p121">Im Juni erhalte ich Geräteregistrierung und App, und bedingte Zugriffsrichtlinien werden angewendet. (Verwaltung mobiler Geräte)</span><span class="sxs-lookup"><span data-stu-id="c4d01-p121">In June, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="c4d01-p122">Im August wird der Azure Information Protection-Client installiert, und ich erhalte Schulung, wie Bezeichnungen auf Dokumente angewendet werden. (Information Protection)</span><span class="sxs-lookup"><span data-stu-id="c4d01-p122">In August, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="c4d01-184">Das Ergebnis ist eine Kadenz von 60 Tagen zwischen den aufeinanderfolgenden Pilotrollouts.</span><span class="sxs-lookup"><span data-stu-id="c4d01-184">The result is a 60-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="c4d01-185">Vereinfachtes Beispiel für eine Endbenutzererfahrung:</span><span class="sxs-lookup"><span data-stu-id="c4d01-185">Simplified example end-user experience:</span></span>

- <span data-ttu-id="c4d01-p123">Im Januar muss ich mein Smartphone für MFA verwenden. (Identität)</span><span class="sxs-lookup"><span data-stu-id="c4d01-p123">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="c4d01-p124">Im März wird Windows 10 Enterprise auf meinem Windows 8.1-Desktopcomputer installiert. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="c4d01-p124">In March, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="c4d01-p125">Im Mai wird Office 365 ProPlus installiert und ersetzt Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="c4d01-p125">In May, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="c4d01-p126">Im Juli erhalte ich Geräteregistrierung und App, und bedingte Zugriffsrichtlinien werden angewendet. (Verwaltung mobiler Geräte)</span><span class="sxs-lookup"><span data-stu-id="c4d01-p126">In July, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="c4d01-p127">Im September wird der Azure Information Protection-Client installiert, und ich erhalte Schulung, wie Bezeichnungen auf Dokumente angewendet werden. (Information Protection)</span><span class="sxs-lookup"><span data-stu-id="c4d01-p127">In September, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="c4d01-196">Das Ergebnis ist eine Kadenz von 60 Tagen zwischen den aufeinanderfolgenden Benutzerrollouts.</span><span class="sxs-lookup"><span data-stu-id="c4d01-196">The result is a 60-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="c4d01-197">Der Vorteil dieser Bereitstellungsstrategie besteht darin, dass die vollständige Bereitstellung der Microsoft 365 Enterprise Foundation-Infrastruktur in kürzerer Zeit erfolgen kann, ohne dass Ihre IT-Abteilung und Benutzer mehrere Rollouts gleichzeitig durchführen müssen.</span><span class="sxs-lookup"><span data-stu-id="c4d01-197">The advantage to this deployment strategy is that it can take less time to fully deploy the Microsoft 365 Enterprise foundation infrastructure, without having your IT department and users deal with multiple rollouts the same time.</span></span>

### <a name="parallel-deployment-with-overlapping-user-rollout-parallel-2"></a><span data-ttu-id="c4d01-198">Parallele Bereitstellung mit überlappendem Benutzerrollout (Parallel 2)</span><span class="sxs-lookup"><span data-stu-id="c4d01-198">Parallel deployment with overlapping user rollout (Parallel 2)</span></span>

<span data-ttu-id="c4d01-199">Für diese Bereitstellungsstrategie beginnen Sie:</span><span class="sxs-lookup"><span data-stu-id="c4d01-199">For this deployment strategy, you start the:</span></span>

- <span data-ttu-id="c4d01-200">Das Pilotrollout der nächsten Phase während des letzten Teils des Benutzerrollouts der aktuellen Phase.</span><span class="sxs-lookup"><span data-stu-id="c4d01-200">Pilot rollout of the next phase during the last part of the user rollout of the current phase.</span></span>
- <span data-ttu-id="c4d01-p128">Das Benutzerrollout der nächsten Phase während des Benutzerrollouts der aktuellen Phase so, dass kein Benutzer gleichzeitig mit den Rollouts mehrerer Phasen beschäftigt ist. Dies setzt voraus, dass Sie jede Phase der Foundation-Infrastruktur auf die gleiche Weise (über Regionen, Abteilungen usw.) umsetzen.</span><span class="sxs-lookup"><span data-stu-id="c4d01-p128">User rollout of the next phase during the user rollout of the current phase in such a way that no user is dealing with the rollouts of multiple phases at the same time. This assumes that you are rolling out each phase of the foundation infrastructure in the same way, via regions, departments, or other.</span></span>

<span data-ttu-id="c4d01-203">Dies ist ein vereinfachter Vergleich zwischen den verschiedenen Bereitstellungsstrategien.</span><span class="sxs-lookup"><span data-stu-id="c4d01-203">Here is a simplified comparison between the different deployment strategies.</span></span>

![](./media/deployment-strategies-microsoft-365-enterprise/parallel2.png) 

<span data-ttu-id="c4d01-204">Für das Endergebnis gilt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c4d01-204">The end result is that:</span></span>

- <span data-ttu-id="c4d01-205">Pilotrollouts gehen ohne Unterbrechung von einer Phase in die nächste über.</span><span class="sxs-lookup"><span data-stu-id="c4d01-205">Pilot rollouts go from one phase to the next without a pause.</span></span>
- <span data-ttu-id="c4d01-206">Das Benutzerrollout für eine Phase beginnt vor Abschluss des Benutzerrollouts der vorherigen Phase, aber kein einzelner Benutzer führt mehr als eine Phase gleichzeitig aus.</span><span class="sxs-lookup"><span data-stu-id="c4d01-206">The user rollout for a phase begins before the completion of the user rollout of the previous phase, but no individual user is rolling out more than one phase at a time.</span></span>

<span data-ttu-id="c4d01-207">Vereinfachtes Beispiel für eine Pilotprojekt-Benutzererfahrung:</span><span class="sxs-lookup"><span data-stu-id="c4d01-207">Simplified example pilot user experience:</span></span> 

- <span data-ttu-id="c4d01-p129">Im Dezember muss ich mein Smartphone für MFA verwenden. (Identität)</span><span class="sxs-lookup"><span data-stu-id="c4d01-p129">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="c4d01-p130">Im Januar wird Windows 10 Enterprise auf meinem Windows 8.1-Desktopcomputer installiert. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="c4d01-p130">In January, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="c4d01-p131">Im Februar wird Office 365 ProPlus installiert und ersetzt Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="c4d01-p131">In February, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="c4d01-p132">Im März erhalte ich Geräteregistrierung und App, und bedingte Zugriffsrichtlinien werden angewendet. (Verwaltung mobiler Geräte)</span><span class="sxs-lookup"><span data-stu-id="c4d01-p132">In March, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="c4d01-p133">Im April wird der Azure Information Protection-Client installiert, und ich erhalte Schulung, wie Bezeichnungen auf Dokumente angewendet werden. (Information Protection)</span><span class="sxs-lookup"><span data-stu-id="c4d01-p133">In April, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="c4d01-218">Das Ergebnis ist eine Kadenz von 30 Tagen zwischen den aufeinanderfolgenden Pilotrollouts.</span><span class="sxs-lookup"><span data-stu-id="c4d01-218">The result is a 30-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="c4d01-219">Vereinfachtes Beispiel für eine Endbenutzererfahrung:</span><span class="sxs-lookup"><span data-stu-id="c4d01-219">Simplified example end-user experience:</span></span>

- <span data-ttu-id="c4d01-p134">Im Januar muss ich mein Smartphone für MFA verwenden. (Identität)</span><span class="sxs-lookup"><span data-stu-id="c4d01-p134">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="c4d01-p135">Im Februar wird Windows 10 Enterprise auf meinem Windows 8.1-Desktopcomputer installiert. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="c4d01-p135">In February, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="c4d01-p136">Im März wird Office 365 ProPlus installiert und ersetzt Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="c4d01-p136">In March, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="c4d01-p137">Im April erhalte ich Geräteregistrierung und App, und bedingte Zugriffsrichtlinien werden angewendet. (Verwaltung mobiler Geräte)</span><span class="sxs-lookup"><span data-stu-id="c4d01-p137">In April, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="c4d01-p138">Im Mai wird der Azure Information Protection-Client installiert, und ich erhalte Schulung, wie Bezeichnungen auf Dokumente angewendet werden. (Information Protection)</span><span class="sxs-lookup"><span data-stu-id="c4d01-p138">In May, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="c4d01-230">Das Ergebnis ist eine Kadenz von 30 Tagen zwischen den aufeinanderfolgenden Benutzerrollouts.</span><span class="sxs-lookup"><span data-stu-id="c4d01-230">The result is a 30-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="c4d01-p139">Der Vorteil dieser Bereitstellungsstrategie besteht darin, dass die vollständige Bereitstellung der Microsoft 365 Enterprise Foundation-Infrastruktur noch schneller erfolgen kann, ohne dass einzelne Benutzer gleichzeitig mehrere Rollouts durchführen müssen. Die Benutzer erhalten jedoch keine Pause zwischen den aufeinanderfolgenden Phasen.</span><span class="sxs-lookup"><span data-stu-id="c4d01-p139">The advantage to this deployment strategy is that it can take even less time to fully deploy the Microsoft 365 Enterprise foundation infrastructure, still without having individual users deal with multiple rollouts the same time. However, users don’t get a break between successive phases.</span></span>

### <a name="up-front-infrastructure-and-rollout-of-end-to-end-configuration"></a><span data-ttu-id="c4d01-233">Vorabinfrastruktur und Rollout der End-to-End-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c4d01-233">Up-front infrastructure and rollout of end-to-end configuration</span></span>

<span data-ttu-id="c4d01-234">Für kleinere Unternehmen mit der Möglichkeit, die Phasen 2 bis 6 in einem einzigen Bereitstellungssegment zu komprimieren, sieht die sich ergebende Bereitstellung folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="c4d01-234">For smaller organizations with the ability to compress phases 2-6 into a single deployment segment, the resulting deployment looks like this:</span></span>
 
![](./media/deployment-strategies-microsoft-365-enterprise/up-front.png) 

<span data-ttu-id="c4d01-p140">Die IT-Abteilung konfiguriert die Infrastruktur für die Phasen 2 bis 6 und stellt sie dann für die Pilotbenutzer bereit, um die End-to-End-Funktionalität zu überprüfen. Beispielsweise erhalten Pilotbenutzer alle diese Funktionen gleichzeitig:</span><span class="sxs-lookup"><span data-stu-id="c4d01-p140">The IT department configures the infrastructure for phases 2-6, then rolls out to the pilot users to check for the end-to-end functionality. For example, pilot users get all of this functionality at the same time:</span></span>

- <span data-ttu-id="c4d01-237">MFA und andere Identitätsfeatures (Identität)</span><span class="sxs-lookup"><span data-stu-id="c4d01-237">MFA and other identity features (Identity)</span></span>
- <span data-ttu-id="c4d01-238">Windows 10 Enterprise auf Windows-Geräten (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="c4d01-238">Windows 10 Enterprise on Windows devices (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="c4d01-239">Office 365 ProPlus für die Office-Suite (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="c4d01-239">Office 365 ProPlus for the Office suite (Office 365 ProPlus)</span></span>
- <span data-ttu-id="c4d01-240">App und bedingte Zugriffsrichtlinien (Verwaltung mobiler Geräte)</span><span class="sxs-lookup"><span data-stu-id="c4d01-240">App and conditional access policies (Mobile device management)</span></span>
- <span data-ttu-id="c4d01-241">Installation des Azure Information Protection-Clients und Schulung, wie Bezeichnungen auf Dokumente angewendet werden (Information Protection)</span><span class="sxs-lookup"><span data-stu-id="c4d01-241">Azure Information Protection client installed and training on how to apply labels to documents (Information protection)</span></span>

<span data-ttu-id="c4d01-242">Nach Abschluss des Pilotrollouts beginnt das Benutzerrollout, bei dem jeder Benutzer alle Funktionen gleichzeitig erhält.</span><span class="sxs-lookup"><span data-stu-id="c4d01-242">Once the pilot rollout is concluded, the user rollout begins in which each user gets all the functionality the same time.</span></span>

## <a name="next-step"></a><span data-ttu-id="c4d01-243">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="c4d01-243">Next step</span></span>

<span data-ttu-id="c4d01-244">Starten der Bereitstellung von Microsoft 365 Enterprise mit der [Foundation-Infrastruktur](deploy-foundation-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="c4d01-244">Start your deployment of Microsoft 365 Enterprise with the [foundation infrastructure](deploy-foundation-infrastructure.md).</span></span>
