---
title: Zusammenfassung der Projektergebnisse des Pilotprojekts Microsoft 365 Defender
description: Schließen Sie Ihr Pilotprojekt "Microsoft 365 Defender" ab, indem Sie die Scorecard fertig stellen, die Ergebnisse des Berichts analysieren und entscheiden, wie Sie fortfahren möchten.
keywords: Microsoft Threat Protection Pilot, entscheiden, was als nächstes zu tun, nachdem Pilotprojekt Microsoft Threat Protection, was zu tun ist, nach der Bewertung von Microsoft Threat Protection in der Produktion, der Übergang von Microsoft Threat Protection Pilot zur Bereitstellung, Cyber-Sicherheit, Advanced persistent Threat, Enterprise-Sicherheit, Geräte, Gerät, Identität, Benutzer, Daten, Anwendungen, Vorfälle, automatisierte Untersuchung
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 3fe5bfdec566b0988d9f565595624fc8dd597788
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130943"
---
# <a name="closing-and-summarizing-your-microsoft-365-defender-pilot"></a><span data-ttu-id="63470-104">Schließen und zusammenfassen Ihres Microsoft 365 Defender-Pilotprojekts</span><span class="sxs-lookup"><span data-stu-id="63470-104">Closing and summarizing your Microsoft 365 Defender pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="63470-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="63470-105">**Applies to:**</span></span>
- <span data-ttu-id="63470-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="63470-106">Microsoft 365 Defender</span></span>



|<span data-ttu-id="63470-107">[![Planung](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span><span class="sxs-lookup"><span data-stu-id="63470-107">[![Planning](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span></span><br/>[<span data-ttu-id="63470-108">Planung</span><span class="sxs-lookup"><span data-stu-id="63470-108">Planning</span></span>](mtp-pilot-plan.md) |<span data-ttu-id="63470-109">[![Vorbereiten](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="63470-109">[![Prepare](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="63470-110">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="63470-110">Preparation</span></span>](prepare-mtpeval.md) | <span data-ttu-id="63470-111">[![Angriff simulieren](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span><span class="sxs-lookup"><span data-stu-id="63470-111">[![Simulate attack](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span></span><br/>[<span data-ttu-id="63470-112">Angriff simulieren</span><span class="sxs-lookup"><span data-stu-id="63470-112">Simulate attack</span></span>](mtp-pilot-simulate.md) | ![Schließen und zusammenfassen](../../media/phase-diagrams/4-summary.png)<br/><span data-ttu-id="63470-114">Schließen und zusammenfassen</span><span class="sxs-lookup"><span data-stu-id="63470-114">Close and summarize</span></span>|
|--|--|--|--|
|| | |<span data-ttu-id="63470-115">*Sie sind hier!*</span><span class="sxs-lookup"><span data-stu-id="63470-115">*You are here!*</span></span>|


<span data-ttu-id="63470-116">Sie befinden sich derzeit in der Abschluss-und Zusammenfassungs Phase.</span><span class="sxs-lookup"><span data-stu-id="63470-116">You're currently in the closing and summarizing phase.</span></span>

<span data-ttu-id="63470-117">Sie haben soeben eine Advanced Memory-only-Angriffssimulation ausgeführt, die Code Remote auf einem Domänencontroller ausführt.</span><span class="sxs-lookup"><span data-stu-id="63470-117">You’ve just ran an advanced memory-only attack simulation that executed code remotely on a domain controller.</span></span> <span data-ttu-id="63470-118">Sie haben gesehen, wie Microsoft Defender für Endpoint und Microsoft Defender for Identity Warnungen für heimliche böswillige Aktivitäten erkennen und erstellen.</span><span class="sxs-lookup"><span data-stu-id="63470-118">You’ve seen how Microsoft Defender for Endpoint and Microsoft Defender for Identity detect and create alerts on stealthy malicious activity.</span></span> <span data-ttu-id="63470-119">Sie haben auch gesehen, wie Benachrichtigungen aus unterschiedlichen Quellen zusammen mit anderen Kontextinformationen in einem einzelnen Vorfall im Microsoft 365 Security Center-Portal zugestellt werden.</span><span class="sxs-lookup"><span data-stu-id="63470-119">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="63470-120">Durch diese Integration können SOC-Analysten untersuchen und erforderliche Maßnahmen ergreifen.</span><span class="sxs-lookup"><span data-stu-id="63470-120">Experiencing such integration enables SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="63470-121">Sie haben auch eine erweiterte Jagd Abfrage erstellt, mit der eingehende e-Mails identifiziert werden, bei denen der Benutzer die Anlage geöffnet oder gespeichert und die Erkennung basierend auf dieser Abfrage erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="63470-121">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="63470-122">Sie haben das Ende des Prozesses erreicht, nachdem alle Tests abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="63470-122">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="63470-123">Die endgültige Ausgabe sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="63470-123">The final output should be:</span></span>

- <span data-ttu-id="63470-124">Eine abgeschlossene Scorecard</span><span class="sxs-lookup"><span data-stu-id="63470-124">A completed scorecard</span></span>
- <span data-ttu-id="63470-125">Ausführlicher Bericht über die Ergebnisse des Pilotprojekts</span><span class="sxs-lookup"><span data-stu-id="63470-125">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="63470-126">Eine Entscheidung im Hinblick auf die Weiterentwicklung</span><span class="sxs-lookup"><span data-stu-id="63470-126">A decision on how to move forward</span></span>

<span data-ttu-id="63470-127">Zeigen Sie die Berichte aus der endgültigen Ausgabe den internen Beteiligten (die Sie während der [Vorbereitungs](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) Phase identifiziert haben) und Microsoft Contacts an.</span><span class="sxs-lookup"><span data-stu-id="63470-127">Present the reports from your final output to internal stakeholders (which you’ve identified during the [preparation](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) phase) and Microsoft contacts.</span></span> <span data-ttu-id="63470-128">Durch diesen Aufwand wird sichergestellt, dass Feedback zum Verbessern von Produkten und Dokumentation verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="63470-128">Such an effort ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="63470-129">Wir hoffen, dass Ihnen diese Simulation gefallen hat.</span><span class="sxs-lookup"><span data-stu-id="63470-129">We hope you enjoyed this simulation.</span></span> <span data-ttu-id="63470-130">Beginnen Sie mit der Implementierung, was Sie in Ihrer Organisation auf breiter Ebene gelernt haben, um die integrierte Sicherheitslösung optimal zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="63470-130">Start implementing what you've learned on a larger scale in your organization to get the most out of the integrated security solution.</span></span>

## <a name="next-step"></a><span data-ttu-id="63470-131">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="63470-131">Next step</span></span>
<span data-ttu-id="63470-132">Erfahren Sie mehr über die Microsoft 365 Defender-Säulen durch die folgenden interaktiven Leitfäden:</span><span class="sxs-lookup"><span data-stu-id="63470-132">Learn more about the Microsoft 365 Defender pillars through the following interactive guides:</span></span>
- [<span data-ttu-id="63470-133">Schützen Ihrer Organisation mit Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="63470-133">Safeguard your organization with Microsoft Defender for Office 365</span></span>](https://aka.ms/O365ATP-Interactive-Guide)
- [<span data-ttu-id="63470-134">Erkennen verdächtiger Aktivitäten und möglicher Angriffe mit Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="63470-134">Detect suspicious activities and potential attacks with Microsoft Defender for Identity</span></span>](https://aka.ms/AATP-Interactive-Guide)
- [<span data-ttu-id="63470-135">Erkennen von Bedrohungen und Verwalten von Warnungen mit Microsoft Cloud-App-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="63470-135">Detect threats and manage alerts with Microsoft Cloud App Security</span></span>](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [<span data-ttu-id="63470-136">Untersuchen und Beheben von Bedrohungen mit Microsoft Defender für Endpoint</span><span class="sxs-lookup"><span data-stu-id="63470-136">Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
