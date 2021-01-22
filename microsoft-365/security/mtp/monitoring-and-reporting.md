---
title: Überwachen und Anzeigen von Berichten – Security Center
description: Beschreibt, wie das Microsoft 365 Security Center auf einen Blick eine Übersicht über Schutz und Sicherheitsstatus bietet.
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, Security Center, überwachen, Bericht, Status
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 4667c39a8d416d7e186d41063d7057109758cd33
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930402"
---
# <a name="monitor-and-view-reports-in-the-microsoft-365-security-center"></a><span data-ttu-id="3b00a-104">Überwachen und Anzeigen von Berichten im Microsoft 365 Security Center</span><span class="sxs-lookup"><span data-stu-id="3b00a-104">Monitor and view reports in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> <span data-ttu-id="3b00a-105">Möchten Sie Microsoft 365 Defender erleben?</span><span class="sxs-lookup"><span data-stu-id="3b00a-105">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="3b00a-106">Sie können [es in einer Laborumgebung auswerten oder](https://aka.ms/mtp-trial-lab) ihr Pilotprojekt in der Produktion [ausführen.](https://aka.ms/m365d-pilotplaybook)</span><span class="sxs-lookup"><span data-stu-id="3b00a-106">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="3b00a-107">Das Microsoft 365 Security Center bietet eine Zusammenfassung der Schutz- und Sicherheitsstatus in Ihrer Microsoft 365-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="3b00a-107">The Microsoft 365 security center provides a summary of protection and security statuses across your Microsoft 365 environment.</span></span>

<span data-ttu-id="3b00a-108">Das Sicherheitscenter enthält einen Abschnitt **"Berichte",** in dem eine Vielzahl von Karten für eine Vielzahl von Bereichen enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="3b00a-108">The security center includes a **Reports** section which features a host of cards covering a variety of areas.</span></span> <span data-ttu-id="3b00a-109">Sicherheitsanalysten und Administratoren können die Karten im Rahmen ihres täglichen Betriebs nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="3b00a-109">Security analysts and administrators can track the cards as part of their day-to-day operations.</span></span> <span data-ttu-id="3b00a-110">Beim Drilldown stellen Karten detaillierte Berichte und in einigen Fällen Verwaltungsoptionen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="3b00a-110">On drill-down, cards provide detailed reports and, in some cases, management options.</span></span>

## <a name="customize-views"></a><span data-ttu-id="3b00a-111">Anpassen von Ansichten</span><span class="sxs-lookup"><span data-stu-id="3b00a-111">Customize views</span></span>

<span data-ttu-id="3b00a-112">Standardmäßig sind Karten in die folgenden Kategorien unterteilt:</span><span class="sxs-lookup"><span data-stu-id="3b00a-112">By default, cards are grouped into these categories:</span></span>
  
* <span data-ttu-id="3b00a-113">[Identitäten](monitor-and-report-identities.md) – Benutzerkonten und Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="3b00a-113">[Identities](monitor-and-report-identities.md) - user accounts and credentials</span></span>
* <span data-ttu-id="3b00a-114">[Daten](monitor-data.md) – E-Mail- und Dokumentinhalte</span><span class="sxs-lookup"><span data-stu-id="3b00a-114">[Data](monitor-data.md) - email and document contents</span></span>
* <span data-ttu-id="3b00a-115">[Geräte](monitor-devices.md) – Computer, Mobiltelefone und andere Geräte</span><span class="sxs-lookup"><span data-stu-id="3b00a-115">[Devices](monitor-devices.md) - computers, mobile phones, and other devices</span></span>
* <span data-ttu-id="3b00a-116">[Apps](monitor-apps.md) – Programme und angefügte Onlinedienste</span><span class="sxs-lookup"><span data-stu-id="3b00a-116">[Apps](monitor-apps.md) - programs and attached online services</span></span>

<span data-ttu-id="3b00a-117">Wechseln Sie **zu "Gruppieren nach Thema",** um die Karten neu anordnen und in den folgenden Themen gruppieren zu können:</span><span class="sxs-lookup"><span data-stu-id="3b00a-117">Switch to **Group by topic**, to rearrange the cards and group them into the following topics:</span></span>

* <span data-ttu-id="3b00a-118">**Risiko** – Karten, die Entitäten hervorheben, z. B. Konten und Geräte, die möglicherweise gefährdet sind.</span><span class="sxs-lookup"><span data-stu-id="3b00a-118">**Risk** - cards that highlight entities, such as accounts and devices, that might be at risk.</span></span> <span data-ttu-id="3b00a-119">Diese Karten heben auch mögliche Risikoquellen auf, z. B. neue Bedrohungskampagnen und privilegierte Cloud-Apps.</span><span class="sxs-lookup"><span data-stu-id="3b00a-119">These cards also highlight possible sources of risk, such as new threat campaigns and privileged cloud apps</span></span>  
* <span data-ttu-id="3b00a-120">**Erkennungstrends** – Karten, die neue Bedrohungserkennungen, Anomalien und Richtlinienverletzungen hervorheben</span><span class="sxs-lookup"><span data-stu-id="3b00a-120">**Detection trends** - cards that highlight new threat detections, anomalies, and policy violations</span></span>
* <span data-ttu-id="3b00a-121">**Konfiguration und Integrität** – Karten, die die Konfiguration und Bereitstellung von Sicherheitskontrollen abdecken, einschließlich des Geräte-Onboarding-Zustands für Verwaltungsdienste</span><span class="sxs-lookup"><span data-stu-id="3b00a-121">**Configuration and health** - cards that cover the configuration and deployment of security controls, including device onboarding states to management services</span></span>
* <span data-ttu-id="3b00a-122">**Sonstige** – alle anderen Karten, die nicht unter anderen Themen kategorisiert sind</span><span class="sxs-lookup"><span data-stu-id="3b00a-122">**Other** - all other cards not categorized under other topics</span></span>
