---
title: Microsoft Defender Antivirus beurteilen
description: Unternehmen aller Größen können diesen Leitfaden verwenden, um den von der Microsoft Defender Antivirus in Windows 10.
keywords: Microsoft Defender Antivirus, Cloudschutz, Cloud, Antischalware, Sicherheit, Defender, Evaluieren, Testen, Schutz, Vergleichen, Echtzeitschutz
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4f789ab80d48966d4cf922811d05d74882d728fe
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274736"
---
# <a name="evaluate-microsoft-defender-antivirus"></a><span data-ttu-id="6a151-104">Microsoft Defender Antivirus beurteilen</span><span class="sxs-lookup"><span data-stu-id="6a151-104">Evaluate Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6a151-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="6a151-105">**Applies to:**</span></span>

- [<span data-ttu-id="6a151-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6a151-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="6a151-107">Verwenden Sie dieses Handbuch, um zu bestimmen, Microsoft Defender Antivirus Schutz vor Viren, Schadsoftware und potenziell unerwünschten Anwendungen bietet.</span><span class="sxs-lookup"><span data-stu-id="6a151-107">Use this guide to determine how well Microsoft Defender Antivirus protects you from viruses, malware, and potentially unwanted applications.</span></span>

>[!TIP]
><span data-ttu-id="6a151-108">Sie können auch die Microsoft Defender for Endpoint-Demowebsite unter [demo.wd.microsoft.com,](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) um zu bestätigen, dass die folgenden Features funktionieren und wie sie funktionieren:</span><span class="sxs-lookup"><span data-stu-id="6a151-108">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working and see how they work:</span></span>
>- <span data-ttu-id="6a151-109">Aus der Cloud gelieferter Schutz</span><span class="sxs-lookup"><span data-stu-id="6a151-109">Cloud-delivered protection</span></span>
>- <span data-ttu-id="6a151-110">Schnelles Lernen (einschließlich "Bei erster Sicht blockieren")</span><span class="sxs-lookup"><span data-stu-id="6a151-110">Fast learning (including Block at first sight)</span></span>
>- <span data-ttu-id="6a151-111">Potenziell unerwünschte Anwendungsblockierung</span><span class="sxs-lookup"><span data-stu-id="6a151-111">Potentially unwanted application blocking</span></span>

<span data-ttu-id="6a151-112">Es wird erläutert, welche wichtigen Schutzfunktionen der nächsten Generation Microsoft Defender Antivirus kleinen und großen Unternehmen zur Verfügung stehen, und wie sie die Erkennung und den Schutz von Schadsoftware im gesamten Netzwerk erhöhen.</span><span class="sxs-lookup"><span data-stu-id="6a151-112">It explains the important next-generation protection features of Microsoft Defender Antivirus available for both small and large enterprises, and how they increase malware detection and protection across your network.</span></span>

<span data-ttu-id="6a151-113">Sie können jede Einstellung unabhängig oder alle gleichzeitig konfigurieren und auswerten.</span><span class="sxs-lookup"><span data-stu-id="6a151-113">You can choose to configure and evaluate each setting independently, or all at once.</span></span> <span data-ttu-id="6a151-114">Wir haben ähnliche Einstellungen basierend auf typischen Auswertungsszenarien zusammengefasst und Anweisungen für die Verwendung von PowerShell zum Aktivieren der Einstellungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="6a151-114">We have grouped similar settings based upon typical evaluation scenarios, and include instructions for using PowerShell to enable the settings.</span></span>

<span data-ttu-id="6a151-115">Das Handbuch ist im PDF-Format für die Offlineanzeige verfügbar:</span><span class="sxs-lookup"><span data-stu-id="6a151-115">The guide is available in PDF format for offline viewing:</span></span>

- [<span data-ttu-id="6a151-116">Herunterladen des Handbuchs im PDF-Format</span><span class="sxs-lookup"><span data-stu-id="6a151-116">Download the guide in PDF format</span></span>](https://www.microsoft.com/download/details.aspx?id=54795)

<span data-ttu-id="6a151-117">Sie können auch eine PowerShell herunterladen, die alle in der Anleitung beschriebenen Einstellungen automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6a151-117">You can also download a PowerShell that will enable all the settings described in the guide automatically.</span></span> <span data-ttu-id="6a151-118">Sie können das Skript zusammen mit dem obigen PDF-Download oder einzeln im PowerShell Gallery abrufen:</span><span class="sxs-lookup"><span data-stu-id="6a151-118">You can obtain the script alongside the PDF download above, or individually from PowerShell Gallery:</span></span>

- [<span data-ttu-id="6a151-119">Laden Sie das PowerShell-Skript herunter, um die Einstellungen automatisch zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6a151-119">Download the PowerShell script to automatically configure the settings</span></span>](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> <span data-ttu-id="6a151-120">Das Handbuch ist derzeit für die Auswertung von Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="6a151-120">The guide is currently intended for single-machine evaluation of Microsoft Defender Antivirus.</span></span> <span data-ttu-id="6a151-121">Das Aktivieren aller Einstellungen in diesem Handbuch ist möglicherweise nicht für die bereitstellung in der realen Welt geeignet.</span><span class="sxs-lookup"><span data-stu-id="6a151-121">Enabling all of the settings in this guide may not be suitable for real-world deployment.</span></span>
>
> <span data-ttu-id="6a151-122">Die neuesten Empfehlungen für die bereitstellung und Überwachung von Microsoft Defender Antivirus in einem Netzwerk finden Sie unter [Deploy Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="6a151-122">For the latest recommendations for real-world deployment and monitoring of Microsoft Defender Antivirus across a network, see [Deploy Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="6a151-123">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="6a151-123">Related topics</span></span>

- [<span data-ttu-id="6a151-124">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="6a151-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="6a151-125">Bereitstellen Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="6a151-125">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)