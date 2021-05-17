---
title: Feedback-Loop-Blockierung
description: Das Blockieren von Feedbackschleifen, auch als schneller Schutz bezeichnet, ist Teil der Funktionen zum Blockieren und Eindähen von Verhaltensweisen in Microsoft Defender for Endpoint
keywords: Verhaltensblockierung, schneller Schutz, Feedbackblockierung, Microsoft Defender for Endpoint
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
ms.openlocfilehash: b1ec879a2f05a0354b1a49cf94fccacb4a382193
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068575"
---
# <a name="feedback-loop-blocking"></a><span data-ttu-id="69b2d-104">Feedback-Loop-Blockierung</span><span class="sxs-lookup"><span data-stu-id="69b2d-104">Feedback-loop blocking</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="69b2d-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="69b2d-105">**Applies to:**</span></span>
- [<span data-ttu-id="69b2d-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="69b2d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

## <a name="overview"></a><span data-ttu-id="69b2d-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="69b2d-107">Overview</span></span>

<span data-ttu-id="69b2d-108">Das Blockieren von Feedbackschleifen, auch als schneller Schutz bezeichnet, ist eine Komponente von Funktionen zum Blockieren und Eindähen von Verhaltensweisen [in](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) Microsoft Defender [for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/).</span><span class="sxs-lookup"><span data-stu-id="69b2d-108">Feedback-loop blocking, also referred to as rapid protection, is a component of [behavioral blocking and containment capabilities](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/).</span></span> <span data-ttu-id="69b2d-109">Durch das Blockieren von Feedbackschleifen sind Geräte in Ihrer Organisation besser vor Angriffen geschützt.</span><span class="sxs-lookup"><span data-stu-id="69b2d-109">With feedback-loop blocking, devices across your organization are better protected from attacks.</span></span> 

## <a name="how-feedback-loop-blocking-works"></a><span data-ttu-id="69b2d-110">Funktionsweise der Feedbackschleifensperrung</span><span class="sxs-lookup"><span data-stu-id="69b2d-110">How feedback-loop blocking works</span></span>

<span data-ttu-id="69b2d-111">Wenn ein verdächtiges Verhalten oder eine Datei erkannt wird, z. B. durch [Microsoft Defender Antivirus,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)werden Informationen zu diesem Artefakt an mehrere Klassifizierungen gesendet.</span><span class="sxs-lookup"><span data-stu-id="69b2d-111">When a suspicious behavior or file is detected, such as by [Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10), information about that artifact is sent to multiple classifiers.</span></span> <span data-ttu-id="69b2d-112">Das Schnellschutzschleifenmodul prüft und korreliert die Informationen mit anderen Signalen, um eine Entscheidung darüber zu treffen, ob eine Datei blockiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="69b2d-112">The rapid protection loop engine inspects and correlates the information with other signals to arrive at a decision as to whether to block a file.</span></span> <span data-ttu-id="69b2d-113">Das Überprüfen und Klassifizieren von Artefakten erfolgt schnell.</span><span class="sxs-lookup"><span data-stu-id="69b2d-113">Checking and classifying artifacts happens quickly.</span></span> <span data-ttu-id="69b2d-114">Es führt zu einer schnellen Blockierung bestätigter Schadsoftware und treibt den Schutz im gesamten Ökosystem voran.</span><span class="sxs-lookup"><span data-stu-id="69b2d-114">It results in rapid blocking of confirmed malware, and drives protection across the entire ecosystem.</span></span> 

<span data-ttu-id="69b2d-115">Mit schnellem Schutz kann ein Angriff auf einem Gerät, auf anderen Geräten in der Organisation und auf Geräten in anderen Organisationen beendet werden, während ein Angriff versucht, seine Fußstapfen zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="69b2d-115">With rapid protection in place, an attack can be stopped on a device, other devices in the organization, and devices in other organizations, as an attack attempts to broaden its foothold.</span></span>


## <a name="configuring-feedback-loop-blocking"></a><span data-ttu-id="69b2d-116">Konfigurieren des Blockierens von Feedbackschleifen</span><span class="sxs-lookup"><span data-stu-id="69b2d-116">Configuring feedback-loop blocking</span></span>

<span data-ttu-id="69b2d-117">Wenn Ihre Organisation Defender for Endpoint verwendet, ist das Blockieren von Feedbackschleifen standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="69b2d-117">If your organization is using Defender for Endpoint, feedback-loop blocking is enabled by default.</span></span> <span data-ttu-id="69b2d-118">Der schnelle Schutz erfolgt jedoch durch eine Kombination aus Defender for Endpoint-Funktionen, Funktionen zum Schutz von maschinellem Lernen und Signalfreigabe über Microsoft-Sicherheitsdienste hinweg.</span><span class="sxs-lookup"><span data-stu-id="69b2d-118">However, rapid protection occurs through a combination of Defender for Endpoint capabilities, machine learning protection features, and signal-sharing across Microsoft security services.</span></span> <span data-ttu-id="69b2d-119">Stellen Sie sicher, dass die folgenden Features und Funktionen von Defender for Endpoint aktiviert und konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="69b2d-119">Make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="69b2d-120">Microsoft Defender for Endpoint-Baselines</span><span class="sxs-lookup"><span data-stu-id="69b2d-120">Microsoft Defender for Endpoint baselines</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [<span data-ttu-id="69b2d-121">In Microsoft Defender for Endpoint integrierte Geräte</span><span class="sxs-lookup"><span data-stu-id="69b2d-121">Devices onboarded to Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-configure)

- [<span data-ttu-id="69b2d-122">EDR im Blockmodus</span><span class="sxs-lookup"><span data-stu-id="69b2d-122">EDR in block mode</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- <span data-ttu-id="69b2d-123">[Verringerung der Angriffsfläche](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction):</span><span class="sxs-lookup"><span data-stu-id="69b2d-123">[Attack surface reduction](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)</span></span>

- <span data-ttu-id="69b2d-124">[Schutz der nächsten Generation](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (Antivirus)</span><span class="sxs-lookup"><span data-stu-id="69b2d-124">[Next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span></span>

## <a name="related-articles"></a><span data-ttu-id="69b2d-125">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="69b2d-125">Related articles</span></span>

- [<span data-ttu-id="69b2d-126">Verhaltensbasiertes Blockieren und Eindämmen</span><span class="sxs-lookup"><span data-stu-id="69b2d-126">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)

- [<span data-ttu-id="69b2d-127">(Blog) Verhaltensblockierung und -eindämmung: Transformieren von Optik in Schutz</span><span class="sxs-lookup"><span data-stu-id="69b2d-127">(Blog) Behavioral blocking and containment: Transforming optics into protection</span></span>](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [<span data-ttu-id="69b2d-128">Hilfreiche Microsoft Defender for Endpoint-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="69b2d-128">Helpful Microsoft Defender for Endpoint resources</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/helpful-resources)
