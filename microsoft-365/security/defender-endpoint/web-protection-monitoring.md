---
title: Überwachen der Sicherheit des Browsens im Web in Microsoft Defender ATP
description: Verwenden von Webschutz in Microsoft Defender ATP zum Überwachen der Sicherheit des Webbrowsers
keywords: Webschutz, Schutz vor Webbedrohungen, Browsen im Web, Überwachung, Berichte, Karten, Domänenliste, Sicherheit, Phishing, Schadsoftware, Exploit, Websites, Netzwerkschutz, Edge, Internet Explorer, Chrome, Firefox, Webbrowser
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 629e18c7387f6063254f3482f93a5e17023c7316
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499946"
---
# <a name="monitor-web-browsing-security"></a><span data-ttu-id="a6210-104">Überwachen der Sicherheit des Browsens im Web</span><span class="sxs-lookup"><span data-stu-id="a6210-104">Monitor web browsing security</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a6210-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a6210-105">**Applies to:**</span></span>
- [<span data-ttu-id="a6210-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="a6210-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a6210-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a6210-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="a6210-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="a6210-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a6210-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="a6210-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="a6210-110">Mit Dem Webschutz können Sie die Sicherheit des Webbrowsens Ihrer Organisation mithilfe von Berichten unter **Berichte > Webschutz** im Microsoft Defender Security Center überwachen.</span><span class="sxs-lookup"><span data-stu-id="a6210-110">Web protection lets you monitor your organization’s web browsing security through reports under **Reports > Web protection** in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="a6210-111">Der Bericht enthält Karten, die Statistiken zur Erkennung von Webbedrohungen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a6210-111">The report contains cards that provide web threat detection statistics.</span></span>

- <span data-ttu-id="a6210-112">**Erkennungen** von Webbedrohungen im Laufe der Zeit – diese Trendkarte zeigt die Anzahl von Webbedrohungen an, die während des ausgewählten Zeitraums vom Typ erkannt wurden (Letzte 30 Tage, Letzte 3 Monate, letzte 6 Monate)</span><span class="sxs-lookup"><span data-stu-id="a6210-112">**Web threat protection detections over time** - this trending card displays the number of web threats detected by type during the selected time period (Last 30 days, Last 3 months, Last 6 months)</span></span>
 
    ![Abbildung der Karte mit Erkennungen von Webbedrohungen im Laufe der Zeit](images/wtp-blocks-over-time.png)

- <span data-ttu-id="a6210-114">**Zusammenfassung zum** Schutz von Webbedrohungen – diese Karte zeigt die gesamten Erkennungen von Webbedrohungen in den letzten 30 Tagen an und zeigt die Verteilung auf die verschiedenen Arten von Webbedrohungen an.</span><span class="sxs-lookup"><span data-stu-id="a6210-114">**Web threat protection summary** - this card displays the total web threat detections in the past 30 days, showing distribution across the different types of web threats.</span></span> <span data-ttu-id="a6210-115">Durch Auswählen eines Datenschnitts wird die Liste der Domänen geöffnet, die mit schädlichen oder unerwünschten Websites gefunden wurden.</span><span class="sxs-lookup"><span data-stu-id="a6210-115">Selecting a slice opens the list of the domains that were found with malicious or unwanted websites.</span></span>

    ![Abbildung der Karte mit der Zusammenfassung des Schutzes von Webbedrohungen](images/wtp-summary.png)

>[!Note]
><span data-ttu-id="a6210-117">Es kann bis zu 12 Stunden dauern, bis ein Block in den Karten oder in der Domänenliste angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a6210-117">It can take up to 12 hours before a block is reflected in the cards or the domain list.</span></span>

## <a name="types-of-web-threats"></a><span data-ttu-id="a6210-118">Arten von Webbedrohungen</span><span class="sxs-lookup"><span data-stu-id="a6210-118">Types of web threats</span></span>

<span data-ttu-id="a6210-119">Der Webschutz kategorisiert schädliche und unerwünschte Websites wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a6210-119">Web protection categorizes malicious and unwanted websites as:</span></span>

- <span data-ttu-id="a6210-120">**Phishing** – Websites mit gefälschten Webformularen und anderen Phishingmechanismen, die Benutzer dazu verleiten sollen, Anmeldeinformationen und andere vertrauliche Informationen zu verleiten</span><span class="sxs-lookup"><span data-stu-id="a6210-120">**Phishing** - websites that contain spoofed web forms and other phishing mechanisms designed to trick users into divulging credentials and other sensitive information</span></span>
- <span data-ttu-id="a6210-121">**Bösartig** – Websites, die Schadsoftware und Exploitcode hosten</span><span class="sxs-lookup"><span data-stu-id="a6210-121">**Malicious** - websites that host malware and exploit code</span></span>
- <span data-ttu-id="a6210-122">**Benutzerdefinierter** Indikator – Websites, deren URLs oder Domänen Sie Ihrer benutzerdefinierten Indikatorliste zum Blockieren [hinzugefügt](manage-indicators.md) haben</span><span class="sxs-lookup"><span data-stu-id="a6210-122">**Custom indicator** - websites whose URLs or domains you've added to your [custom indicator list](manage-indicators.md) for blocking</span></span>

## <a name="view-the-domain-list"></a><span data-ttu-id="a6210-123">Anzeigen der Domänenliste</span><span class="sxs-lookup"><span data-stu-id="a6210-123">View the domain list</span></span>

<span data-ttu-id="a6210-124">Wählen Sie auf der Sammelkarte web threat protection eine bestimmte Kategorie für **Webbedrohungen** aus, um die Seite **Domänen zu** öffnen.</span><span class="sxs-lookup"><span data-stu-id="a6210-124">Select a specific web threat category in the **Web threat protection summary** card to open the **Domains** page.</span></span> <span data-ttu-id="a6210-125">Auf dieser Seite wird die Liste der Domänen unter dieser Bedrohungskategorie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a6210-125">This page displays the list of the domains under that threat category.</span></span> <span data-ttu-id="a6210-126">Die Seite enthält die folgenden Informationen für jede Domäne:</span><span class="sxs-lookup"><span data-stu-id="a6210-126">The page provides the following information for each domain:</span></span>

- <span data-ttu-id="a6210-127">**Zugriffsanzahl** – Anzahl der Anforderungen für URLs in der Domäne</span><span class="sxs-lookup"><span data-stu-id="a6210-127">**Access count** - number of requests for URLs in the domain</span></span>
- <span data-ttu-id="a6210-128">**Blöcke** – Anzahl der blockierten Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a6210-128">**Blocks** - number of times requests were blocked</span></span>
- <span data-ttu-id="a6210-129">**Zugriffstrend** – Änderung der Anzahl der Zugriffsversuche</span><span class="sxs-lookup"><span data-stu-id="a6210-129">**Access trend** - change in number of access attempts</span></span>
- <span data-ttu-id="a6210-130">**Bedrohungskategorie** – Typ der Webbedrohung</span><span class="sxs-lookup"><span data-stu-id="a6210-130">**Threat category** - type of web threat</span></span>
- <span data-ttu-id="a6210-131">**Geräte** – Anzahl der Geräte mit Zugriffsversuchen</span><span class="sxs-lookup"><span data-stu-id="a6210-131">**Devices** - number of devices with access attempts</span></span>

<span data-ttu-id="a6210-132">Wählen Sie eine Domäne aus, um die Liste der Geräte, die versucht haben, auf URLs in dieser Domäne zu zugreifen, und die Liste der URLs anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a6210-132">Select a domain to view the list of devices that have attempted to access URLs in that domain and the list of URLs.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a6210-133">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a6210-133">Related topics</span></span>

- [<span data-ttu-id="a6210-134">Übersicht über Internetschutz</span><span class="sxs-lookup"><span data-stu-id="a6210-134">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="a6210-135">Internet-Inhaltsfilterung</span><span class="sxs-lookup"><span data-stu-id="a6210-135">Web content filtering</span></span>](web-content-filtering.md)
- [<span data-ttu-id="a6210-136">Internet-Bedrohungsschutz</span><span class="sxs-lookup"><span data-stu-id="a6210-136">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="a6210-137">Reagieren auf Internetbedrohungen</span><span class="sxs-lookup"><span data-stu-id="a6210-137">Respond to web threats</span></span>](web-protection-response.md)
