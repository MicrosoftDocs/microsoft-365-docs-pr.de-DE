---
title: Bewerten von Microsoft Defender Antivirus
description: Unternehmen aller Größen können dieses Handbuch verwenden, um den von Microsoft Defender Antivirus in Windows 10 angebotenen Schutz auszuwerten und zu testen.
keywords: Microsoft Defender Antivirus, Cloudschutz, Cloud, Antischalware, Sicherheit, Defender, Evaluieren, Testen, Schutz, Vergleichen, Echtzeitschutz
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: de9c7e845188f47ab5b8e1f9d97871ea36340d19
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690712"
---
# <a name="evaluate-microsoft-defender-antivirus"></a><span data-ttu-id="368cd-104">Bewerten von Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="368cd-104">Evaluate Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="368cd-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="368cd-105">**Applies to:**</span></span>

- [<span data-ttu-id="368cd-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="368cd-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="368cd-107">Verwenden Sie dieses Handbuch, um zu bestimmen, wie gut Microsoft Defender Antivirus Sie vor Viren, Schadsoftware und potenziell unerwünschten Anwendungen schützt.</span><span class="sxs-lookup"><span data-stu-id="368cd-107">Use this guide to determine how well Microsoft Defender Antivirus protects you from viruses, malware, and potentially unwanted applications.</span></span>

>[!TIP]
><span data-ttu-id="368cd-108">Sie können auch die Microsoft Defender for Endpoint-Demowebsite unter [demo.wd.microsoft.com,](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) um zu bestätigen, dass die folgenden Features funktionieren und wie sie funktionieren:</span><span class="sxs-lookup"><span data-stu-id="368cd-108">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working and see how they work:</span></span>
>- <span data-ttu-id="368cd-109">In der Cloud zugestellter Schutz</span><span class="sxs-lookup"><span data-stu-id="368cd-109">Cloud-delivered protection</span></span>
>- <span data-ttu-id="368cd-110">Schnelles Lernen (einschließlich "Bei erster Sicht blockieren")</span><span class="sxs-lookup"><span data-stu-id="368cd-110">Fast learning (including Block at first sight)</span></span>
>- <span data-ttu-id="368cd-111">Potenziell unerwünschte Anwendungsblockierung</span><span class="sxs-lookup"><span data-stu-id="368cd-111">Potentially unwanted application blocking</span></span>

<span data-ttu-id="368cd-112">Es erläutert die wichtigen Schutzfunktionen der nächsten Generation von Microsoft Defender Antivirus, die sowohl für kleine als auch für große Unternehmen verfügbar sind, und wie sie die Erkennung und den Schutz von Schadsoftware im gesamten Netzwerk erhöhen.</span><span class="sxs-lookup"><span data-stu-id="368cd-112">It explains the important next-generation protection features of Microsoft Defender Antivirus available for both small and large enterprises, and how they increase malware detection and protection across your network.</span></span>

<span data-ttu-id="368cd-113">Sie können jede Einstellung unabhängig oder alle gleichzeitig konfigurieren und auswerten.</span><span class="sxs-lookup"><span data-stu-id="368cd-113">You can choose to configure and evaluate each setting independently, or all at once.</span></span> <span data-ttu-id="368cd-114">Wir haben ähnliche Einstellungen basierend auf typischen Auswertungsszenarien zusammengefasst und Anweisungen für die Verwendung von PowerShell zum Aktivieren der Einstellungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="368cd-114">We have grouped similar settings based upon typical evaluation scenarios, and include instructions for using PowerShell to enable the settings.</span></span>

<span data-ttu-id="368cd-115">Das Handbuch ist im PDF-Format für die Offlineanzeige verfügbar:</span><span class="sxs-lookup"><span data-stu-id="368cd-115">The guide is available in PDF format for offline viewing:</span></span>

- [<span data-ttu-id="368cd-116">Herunterladen des Handbuchs im PDF-Format</span><span class="sxs-lookup"><span data-stu-id="368cd-116">Download the guide in PDF format</span></span>](https://www.microsoft.com/download/details.aspx?id=54795)

<span data-ttu-id="368cd-117">Sie können auch eine PowerShell herunterladen, die alle in der Anleitung beschriebenen Einstellungen automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="368cd-117">You can also download a PowerShell that will enable all the settings described in the guide automatically.</span></span> <span data-ttu-id="368cd-118">Sie können das Skript zusammen mit dem obigen PDF-Download oder einzeln im PowerShell Gallery abrufen:</span><span class="sxs-lookup"><span data-stu-id="368cd-118">You can obtain the script alongside the PDF download above, or individually from PowerShell Gallery:</span></span>

- [<span data-ttu-id="368cd-119">Laden Sie das PowerShell-Skript herunter, um die Einstellungen automatisch zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="368cd-119">Download the PowerShell script to automatically configure the settings</span></span>](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> <span data-ttu-id="368cd-120">Das Handbuch ist derzeit für die Auswertung von Microsoft Defender Antivirus auf einem Computer vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="368cd-120">The guide is currently intended for single-machine evaluation of Microsoft Defender Antivirus.</span></span> <span data-ttu-id="368cd-121">Das Aktivieren aller Einstellungen in diesem Handbuch ist möglicherweise nicht für die bereitstellung in der realen Welt geeignet.</span><span class="sxs-lookup"><span data-stu-id="368cd-121">Enabling all of the settings in this guide may not be suitable for real-world deployment.</span></span>
>
> <span data-ttu-id="368cd-122">Die neuesten Empfehlungen für die bereitstellung und Überwachung von Microsoft Defender Antivirus in einem Netzwerk finden Sie unter [Deploy Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="368cd-122">For the latest recommendations for real-world deployment and monitoring of Microsoft Defender Antivirus across a network, see [Deploy Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="368cd-123">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="368cd-123">Related topics</span></span>

- [<span data-ttu-id="368cd-124">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="368cd-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="368cd-125">Bereitstellen von Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="368cd-125">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)