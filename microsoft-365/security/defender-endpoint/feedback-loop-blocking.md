---
title: Feedback-Loop-Blockierung
description: Das Blockieren von Feedbackschleifen, auch als schneller Schutz bezeichnet, ist Teil der Funktionen zum Blockieren und Eindämmen von Verhaltensweisen in Microsoft Defender für Endpunkt.
keywords: Verhaltensblockierung, schneller Schutz, Feedbackblockierung, Microsoft Defender für Endpunkt
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection: ''
ms.technology: mde
ms.openlocfilehash: 7319ff5a89a20529eed7d36aa0d0b1522013abd4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842458"
---
# <a name="feedback-loop-blocking"></a><span data-ttu-id="4e80c-104">Feedback-Loop-Blockierung</span><span class="sxs-lookup"><span data-stu-id="4e80c-104">Feedback-loop blocking</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4e80c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="4e80c-105">**Applies to:**</span></span>
- [<span data-ttu-id="4e80c-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="4e80c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

## <a name="overview"></a><span data-ttu-id="4e80c-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="4e80c-107">Overview</span></span>

<span data-ttu-id="4e80c-108">Das Blockieren von Feedbackschleifen, auch als schneller Schutz bezeichnet, ist eine Komponente der Funktionen zum [Blockieren und Eindämmen](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) von Verhaltensweisen in [Microsoft Defender für Endpunkt.](/windows/security/threat-protection/)</span><span class="sxs-lookup"><span data-stu-id="4e80c-108">Feedback-loop blocking, also referred to as rapid protection, is a component of [behavioral blocking and containment capabilities](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) in [Microsoft Defender for Endpoint](/windows/security/threat-protection/).</span></span> <span data-ttu-id="4e80c-109">Dank der Blockierung der Feedbackschleife sind Geräte in Ihrer Organisation besser vor Angriffen geschützt.</span><span class="sxs-lookup"><span data-stu-id="4e80c-109">With feedback-loop blocking, devices across your organization are better protected from attacks.</span></span> 

## <a name="how-feedback-loop-blocking-works"></a><span data-ttu-id="4e80c-110">Funktionsweise der Blockierung von Feedbackschleifen</span><span class="sxs-lookup"><span data-stu-id="4e80c-110">How feedback-loop blocking works</span></span>

<span data-ttu-id="4e80c-111">Wenn ein verdächtiges Verhalten oder eine Datei erkannt wird, z. B. durch [Microsoft Defender Antivirus,](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)werden Informationen zu diesem Artefakt an mehrere Klassifizierer gesendet.</span><span class="sxs-lookup"><span data-stu-id="4e80c-111">When a suspicious behavior or file is detected, such as by [Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10), information about that artifact is sent to multiple classifiers.</span></span> <span data-ttu-id="4e80c-112">Das Modul für schnelle Schutzschleifen prüft und korreliert die Informationen mit anderen Signalen, um zu einer Entscheidung zu gelangen, ob eine Datei blockiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4e80c-112">The rapid protection loop engine inspects and correlates the information with other signals to arrive at a decision as to whether to block a file.</span></span> <span data-ttu-id="4e80c-113">Das Überprüfen und Klassifizieren von Artefakten erfolgt schnell.</span><span class="sxs-lookup"><span data-stu-id="4e80c-113">Checking and classifying artifacts happens quickly.</span></span> <span data-ttu-id="4e80c-114">Dies führt zu einer schnellen Blockierung bestätigter Schadsoftware und treibt den Schutz im gesamten Ökosystem voran.</span><span class="sxs-lookup"><span data-stu-id="4e80c-114">It results in rapid blocking of confirmed malware, and drives protection across the entire ecosystem.</span></span> 

<span data-ttu-id="4e80c-115">Bei schnellem Schutz kann ein Angriff auf einem Gerät, auf anderen Geräten in der Organisation und auf Geräten in anderen Organisationen beendet werden, da ein Angriff versucht, seine Reichweite zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="4e80c-115">With rapid protection in place, an attack can be stopped on a device, other devices in the organization, and devices in other organizations, as an attack attempts to broaden its foothold.</span></span>


## <a name="configuring-feedback-loop-blocking"></a><span data-ttu-id="4e80c-116">Konfigurieren der Blockierung von Feedbackschleifen</span><span class="sxs-lookup"><span data-stu-id="4e80c-116">Configuring feedback-loop blocking</span></span>

<span data-ttu-id="4e80c-117">Wenn Ihre Organisation Defender für Endpunkt verwendet, ist das Blockieren von Feedbackschleifen standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4e80c-117">If your organization is using Defender for Endpoint, feedback-loop blocking is enabled by default.</span></span> <span data-ttu-id="4e80c-118">Der schnelle Schutz erfolgt jedoch durch eine Kombination aus Defender für Endpunkt-Funktionen, Machine Learning-Schutzfeatures und Signalfreigabe über Microsoft-Sicherheitsdienste hinweg.</span><span class="sxs-lookup"><span data-stu-id="4e80c-118">However, rapid protection occurs through a combination of Defender for Endpoint capabilities, machine learning protection features, and signal-sharing across Microsoft security services.</span></span> <span data-ttu-id="4e80c-119">Stellen Sie sicher, dass die folgenden Features und Funktionen von Defender für Endpunkt aktiviert und konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="4e80c-119">Make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="4e80c-120">Microsoft Defender für Endpunkt-Basispläne</span><span class="sxs-lookup"><span data-stu-id="4e80c-120">Microsoft Defender for Endpoint baselines</span></span>](/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [<span data-ttu-id="4e80c-121">Geräte, die in Microsoft Defender für Endpunkt integriert sind</span><span class="sxs-lookup"><span data-stu-id="4e80c-121">Devices onboarded to Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/onboard-configure)

- [<span data-ttu-id="4e80c-122">EDR im Blockmodus</span><span class="sxs-lookup"><span data-stu-id="4e80c-122">EDR in block mode</span></span>](/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- <span data-ttu-id="4e80c-123">[Verringerung der Angriffsfläche](/microsoft-365/security/defender-endpoint/attack-surface-reduction):</span><span class="sxs-lookup"><span data-stu-id="4e80c-123">[Attack surface reduction](/microsoft-365/security/defender-endpoint/attack-surface-reduction)</span></span>

- <span data-ttu-id="4e80c-124">[Schutz](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) der nächsten Generation (Antivirus)</span><span class="sxs-lookup"><span data-stu-id="4e80c-124">[Next-generation protection](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span></span>

## <a name="related-articles"></a><span data-ttu-id="4e80c-125">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="4e80c-125">Related articles</span></span>

- [<span data-ttu-id="4e80c-126">Verhaltensbasiertes Blockieren und Eindämmen</span><span class="sxs-lookup"><span data-stu-id="4e80c-126">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)

- [<span data-ttu-id="4e80c-127">(Blog) Blockieren und Eindämmen von Verhaltensweisen: Umwandeln von Optik in Schutz</span><span class="sxs-lookup"><span data-stu-id="4e80c-127">(Blog) Behavioral blocking and containment: Transforming optics into protection</span></span>](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [<span data-ttu-id="4e80c-128">Hilfreiche Microsoft Defender für Endpunkt-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="4e80c-128">Helpful Microsoft Defender for Endpoint resources</span></span>](/microsoft-365/security/defender-endpoint/helpful-resources)
