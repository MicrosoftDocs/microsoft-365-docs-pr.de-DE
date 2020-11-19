---
title: Überwachen und Anzeigen von Berichten – Security Center
description: Beschreibt, wie das Microsoft 365 Security Center einen Überblick über den Schutz und den Sicherheitsstatus bietet.
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, Sicherheitscenter, Überwachung, Bericht, Status
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: d52c401c4b2e995e5ec18895c158f77ce0fce746
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356883"
---
# <a name="monitor-and-view-reports-in-the-microsoft-365-security-center"></a><span data-ttu-id="7b560-104">Überwachen und Anzeigen von Berichten im Microsoft 365 Security Center</span><span class="sxs-lookup"><span data-stu-id="7b560-104">Monitor and view reports in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> <span data-ttu-id="7b560-105">Möchten Sie Microsoft 365 Defender erfahren?</span><span class="sxs-lookup"><span data-stu-id="7b560-105">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="7b560-106">Sie können [es in einer Laborumgebung auswerten](https://aka.ms/mtp-trial-lab) oder [ihr Pilotprojekt in der Produktion ausführen](https://aka.ms/m365d-pilotplaybook).</span><span class="sxs-lookup"><span data-stu-id="7b560-106">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="7b560-107">Das Microsoft 365 Security Center bietet eine Zusammenfassung der Schutz-und Sicherheitsstatus in Ihrer Microsoft 365-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="7b560-107">The Microsoft 365 security center provides a summary of protection and security statuses across your Microsoft 365 environment.</span></span>

<span data-ttu-id="7b560-108">Das Sicherheitscenter umfasst einen **Bericht** Abschnitt mit einer Vielzahl von Karten, die eine Reihe von Bereichen abdecken.</span><span class="sxs-lookup"><span data-stu-id="7b560-108">The security center includes a **Reports** section which features a host of cards covering a variety of areas.</span></span> <span data-ttu-id="7b560-109">Sicherheitsanalysten und Administratoren können die Karten im Rahmen ihrer täglichen Vorgänge nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="7b560-109">Security analysts and administrators can track the cards as part of their day-to-day operations.</span></span> <span data-ttu-id="7b560-110">Bei Drilldowns bieten Karten detaillierte Berichte und in einigen Fällen Verwaltungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="7b560-110">On drill-down, cards provide detailed reports and, in some cases, management options.</span></span>

## <a name="customize-views"></a><span data-ttu-id="7b560-111">Anpassen von Ansichten</span><span class="sxs-lookup"><span data-stu-id="7b560-111">Customize views</span></span>

<span data-ttu-id="7b560-112">Karten werden standardmäßig in folgende Kategorien unterteilt:</span><span class="sxs-lookup"><span data-stu-id="7b560-112">By default, cards are grouped into these categories:</span></span>
  
* <span data-ttu-id="7b560-113">[Identitäten](monitor-and-report-identities.md) – Benutzerkonten und Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="7b560-113">[Identities](monitor-and-report-identities.md) - user accounts and credentials</span></span>
* <span data-ttu-id="7b560-114">[Daten](monitor-data.md) – e-Mail-und Dokumentinhalte</span><span class="sxs-lookup"><span data-stu-id="7b560-114">[Data](monitor-data.md) - email and document contents</span></span>
* <span data-ttu-id="7b560-115">[Geräte](monitor-devices.md) – Computer, Mobiltelefone und andere Geräte</span><span class="sxs-lookup"><span data-stu-id="7b560-115">[Devices](monitor-devices.md) - computers, mobile phones, and other devices</span></span>
* <span data-ttu-id="7b560-116">[Apps](monitor-apps.md) -Programme und angefügte Onlinedienste</span><span class="sxs-lookup"><span data-stu-id="7b560-116">[Apps](monitor-apps.md) - programs and attached online services</span></span>

<span data-ttu-id="7b560-117">Wechseln Sie zu **Gruppieren nach Thema**, um die Karten neu anzuordnen und in die folgenden Themen zu gruppieren:</span><span class="sxs-lookup"><span data-stu-id="7b560-117">Switch to **Group by topic**, to rearrange the cards and group them into the following topics:</span></span>

* <span data-ttu-id="7b560-118">**Risiko** Karten, die Entitäten wie Konten und Geräte hervorheben, die möglicherweise gefährdet sind.</span><span class="sxs-lookup"><span data-stu-id="7b560-118">**Risk** - cards that highlight entities, such as accounts and devices, that might be at risk.</span></span> <span data-ttu-id="7b560-119">Diese Karten heben auch mögliche Risikoquellen hervor, beispielsweise neue Bedrohungs Kampagnen und privilegierte Cloud-apps.</span><span class="sxs-lookup"><span data-stu-id="7b560-119">These cards also highlight possible sources of risk, such as new threat campaigns and privileged cloud apps</span></span>  
* <span data-ttu-id="7b560-120">**Erkennungs Trends** -Karten, die neue Bedrohungserkennungen, Anomalien und Richtlinienverletzungen hervorheben</span><span class="sxs-lookup"><span data-stu-id="7b560-120">**Detection trends** - cards that highlight new threat detections, anomalies, and policy violations</span></span>
* <span data-ttu-id="7b560-121">**Konfigurations-und Integritäts** Karten, die die Konfiguration und Bereitstellung von Sicherheitskontrollen abdecken, einschließlich Geräte-Onboarding-Status für Verwaltungsdienste</span><span class="sxs-lookup"><span data-stu-id="7b560-121">**Configuration and health** - cards that cover the configuration and deployment of security controls, including device onboarding states to management services</span></span>
* <span data-ttu-id="7b560-122">**Other** -alle anderen Karten, die nicht unter andere Themen kategorisiert sind</span><span class="sxs-lookup"><span data-stu-id="7b560-122">**Other** - all other cards not categorized under other topics</span></span>
