---
title: Zusammenfassung der Microsoft 365 Defender-Pilotprojektergebnisse
description: Schließen Sie Ihr Microsoft 365 -Defender-Pilotprojekt ab, indem Sie Ihre Scorecard abschließen, Die Ergebnisse Ihres Berichts analysieren und entscheiden, wie es weiter gehen soll.
keywords: Microsoft Threat Protection pilot, decide what to do next after pilot Microsoft Threat Protection project, what to do after evaluating Microsoft Threat Protection in production, transition from Microsoft Threat Protection pilot to deployment, cyber security, advanced persistent threat, enterprise security, devices, device, identity, users, data, applications, incidents, automated investigation and remediation, advanced hunting
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: c8608568301f11a20c940a5ff9f1c205ce6e48f1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930162"
---
# <a name="closing-and-summarizing-your-microsoft-365-defender-pilot"></a><span data-ttu-id="5173c-104">Schließen und Zusammenfassen Ihres Microsoft 365 Defender-Pilotprojekts</span><span class="sxs-lookup"><span data-stu-id="5173c-104">Closing and summarizing your Microsoft 365 Defender pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5173c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="5173c-105">**Applies to:**</span></span>
- <span data-ttu-id="5173c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5173c-106">Microsoft 365 Defender</span></span>



|<span data-ttu-id="5173c-107">[![Planung](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span><span class="sxs-lookup"><span data-stu-id="5173c-107">[![Planning](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span></span><br/>[<span data-ttu-id="5173c-108">Planung</span><span class="sxs-lookup"><span data-stu-id="5173c-108">Planning</span></span>](mtp-pilot-plan.md) |<span data-ttu-id="5173c-109">[![Vorbereiten](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="5173c-109">[![Prepare](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="5173c-110">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="5173c-110">Preparation</span></span>](prepare-mtpeval.md) | <span data-ttu-id="5173c-111">[![Angriff simulieren](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span><span class="sxs-lookup"><span data-stu-id="5173c-111">[![Simulate attack](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span></span><br/>[<span data-ttu-id="5173c-112">Angriff simulieren</span><span class="sxs-lookup"><span data-stu-id="5173c-112">Simulate attack</span></span>](mtp-pilot-simulate.md) | ![Schließen und zusammenfassen](../../media/phase-diagrams/4-summary.png)<br/><span data-ttu-id="5173c-114">Schließen und zusammenfassen</span><span class="sxs-lookup"><span data-stu-id="5173c-114">Close and summarize</span></span>|
|--|--|--|--|
|| | |<span data-ttu-id="5173c-115">*Sie sind hier!*</span><span class="sxs-lookup"><span data-stu-id="5173c-115">*You are here!*</span></span>|


<span data-ttu-id="5173c-116">Sie sind derzeit in der Abschluss- und Zusammenfassungsphase.</span><span class="sxs-lookup"><span data-stu-id="5173c-116">You're currently in the closing and summarizing phase.</span></span>

<span data-ttu-id="5173c-117">Sie haben gerade eine erweiterte Angriffssimulation nur im Arbeitsspeicher ausgeführt, die Code remote auf einem Domänencontroller ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="5173c-117">You’ve just ran an advanced memory-only attack simulation that executed code remotely on a domain controller.</span></span> <span data-ttu-id="5173c-118">Sie haben gesehen, wie Microsoft Defender for Endpoint und Microsoft Defender for Identity Warnungen zu stehlende böswilligen Aktivitäten erkennen und erstellen.</span><span class="sxs-lookup"><span data-stu-id="5173c-118">You’ve seen how Microsoft Defender for Endpoint and Microsoft Defender for Identity detect and create alerts on stealthy malicious activity.</span></span> <span data-ttu-id="5173c-119">Sie haben auch gesehen, wie Warnungen aus verschiedenen Quellen zusammen mit anderen kontextbezogenen Informationen zu einem einzelnen Vorfall im Microsoft 365 Security Center-Portal übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="5173c-119">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="5173c-120">Eine solche Integration ermöglicht es SOC-Analysten, die erforderlichen Maßnahmen zu untersuchen und zu ergreifen.</span><span class="sxs-lookup"><span data-stu-id="5173c-120">Experiencing such integration enables SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="5173c-121">Sie haben auch eine erweiterte Suchabfrage erstellt, die eingehende E-Mails identifiziert, in denen der Benutzer die Anlage geöffnet oder gespeichert und basierend auf dieser Abfrage eine Erkennung erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="5173c-121">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="5173c-122">Sie haben das Ende des Prozesses erreicht, nachdem alle Tests abgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="5173c-122">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="5173c-123">Die endgültige Ausgabe sollte wie dies sein:</span><span class="sxs-lookup"><span data-stu-id="5173c-123">The final output should be:</span></span>

- <span data-ttu-id="5173c-124">Eine abgeschlossene Scorecard</span><span class="sxs-lookup"><span data-stu-id="5173c-124">A completed scorecard</span></span>
- <span data-ttu-id="5173c-125">Detaillierter Bericht über die Ergebnisse des Pilotprojekts</span><span class="sxs-lookup"><span data-stu-id="5173c-125">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="5173c-126">Eine Entscheidung über den Fortschritt</span><span class="sxs-lookup"><span data-stu-id="5173c-126">A decision on how to move forward</span></span>

<span data-ttu-id="5173c-127">Stellen Sie die Berichte aus Ihrer endgültigen Ausgabe internen [](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) Beteiligten (die Sie während der Vorbereitungsphase identifiziert haben) und den Microsoft-Kontakten vor.</span><span class="sxs-lookup"><span data-stu-id="5173c-127">Present the reports from your final output to internal stakeholders (which you’ve identified during the [preparation](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) phase) and Microsoft contacts.</span></span> <span data-ttu-id="5173c-128">Durch diesen Aufwand wird sichergestellt, dass feedback zur Verbesserung von Produkten und Dokumentationen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="5173c-128">Such an effort ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="5173c-129">Wir hoffen, dass Ihnen diese Simulation spaßt.</span><span class="sxs-lookup"><span data-stu-id="5173c-129">We hope you enjoyed this simulation.</span></span> <span data-ttu-id="5173c-130">Beginnen Sie mit der Implementierung von Gelernten in größerem Umfang in Ihrer Organisation, um die integrierte Sicherheitslösung so gut wie nie zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="5173c-130">Start implementing what you've learned on a larger scale in your organization to get the most out of the integrated security solution.</span></span>

## <a name="next-step"></a><span data-ttu-id="5173c-131">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="5173c-131">Next step</span></span>
<span data-ttu-id="5173c-132">Weitere Informationen zu den Säulen von Microsoft 365 Defender finden Sie in den folgenden interaktiven Leitfäden:</span><span class="sxs-lookup"><span data-stu-id="5173c-132">Learn more about the Microsoft 365 Defender pillars through the following interactive guides:</span></span>
- [<span data-ttu-id="5173c-133">Schützen Ihrer Organisation mit Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="5173c-133">Safeguard your organization with Microsoft Defender for Office 365</span></span>](https://aka.ms/O365ATP-Interactive-Guide)
- [<span data-ttu-id="5173c-134">Erkennen Sie verdächtige Aktivitäten und potenzielle Angriffe mit Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="5173c-134">Detect suspicious activities and potential attacks with Microsoft Defender for Identity</span></span>](https://aka.ms/AATP-Interactive-Guide)
- [<span data-ttu-id="5173c-135">Erkennen von Bedrohungen und Verwalten von Warnungen mit Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5173c-135">Detect threats and manage alerts with Microsoft Cloud App Security</span></span>](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [<span data-ttu-id="5173c-136">Untersuchen und Behebung von Bedrohungen mit Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5173c-136">Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
