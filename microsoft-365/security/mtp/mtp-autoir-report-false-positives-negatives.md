---
title: Vorgehensweise Melden von falsch positiven oder falschen negativen Daten in Air in Microsoft Threat Protection
description: Wurde in Microsoft Threat Protection etwas übersehen oder fälschlicherweise von Air erkannt? Hier erfahren Sie, wie Sie falsch positive Ergebnisse oder falsch negative Informationen zur Analyse an Microsoft übermitteln.
keywords: automatisiert, Untersuchung, Warnung, Auslöser, Aktion, Korrektur, falsch positiv, falsch negativ
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: d9175e78326832a2be874359babae5ae9c689420
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600082"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="e2521-105">Vorgehensweise Melden von falsch positiven/negativen Ergebnissen in automatisierten Ermittlungs-und Antwortfunktionen</span><span class="sxs-lookup"><span data-stu-id="e2521-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="e2521-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e2521-106">**Applies to:**</span></span>
- <span data-ttu-id="e2521-107">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e2521-107">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="e2521-108">Haben [automatisierte Ermittlungs-und Antwortfunktionen](mtp-autoir.md) im Microsoft Threat Protection-Vorgang fehl am oder falsch erkannt?</span><span class="sxs-lookup"><span data-stu-id="e2521-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft Threat Protection miss or wrongly detect something?</span></span> <span data-ttu-id="e2521-109">Sie können diesen Bericht an Microsoft melden oder Ihre Benachrichtigungen anpassen (falls erforderlich).</span><span class="sxs-lookup"><span data-stu-id="e2521-109">You can report it to Microsoft or adjust your alerts (if needed).</span></span> <span data-ttu-id="e2521-110">Verwenden Sie die folgende Tabelle als Leitfaden:</span><span class="sxs-lookup"><span data-stu-id="e2521-110">Use the following table as a guide:</span></span> 


|<span data-ttu-id="e2521-111">Element</span><span class="sxs-lookup"><span data-stu-id="e2521-111">Item</span></span>  |<span data-ttu-id="e2521-112">Erkannt von</span><span class="sxs-lookup"><span data-stu-id="e2521-112">Detected by</span></span>  |<span data-ttu-id="e2521-113">Vorgehensweise melden</span><span class="sxs-lookup"><span data-stu-id="e2521-113">How to report it</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="e2521-114">E-Mail</span><span class="sxs-lookup"><span data-stu-id="e2521-114">Email message</span></span> <br/><span data-ttu-id="e2521-115">E-Mail-Anlage</span><span class="sxs-lookup"><span data-stu-id="e2521-115">Email attachment</span></span> <br/><span data-ttu-id="e2521-116">URL in einer e-Mail-Nachricht oder Office-Datei</span><span class="sxs-lookup"><span data-stu-id="e2521-116">URL in an email message or Office file</span></span>      |[<span data-ttu-id="e2521-117">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e2521-117">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="e2521-118">Übermitteln von verdächtigen Spam, Phishing, URLs und Dateien an Microsoft für Office 365-Scans</span><span class="sxs-lookup"><span data-stu-id="e2521-118">Submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="e2521-119">Datei oder App auf einem Gerät</span><span class="sxs-lookup"><span data-stu-id="e2521-119">File or app on a device</span></span>    |[<span data-ttu-id="e2521-120">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e2521-120">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="e2521-121">Übermitteln einer Datei an Microsoft zur Analyse von Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="e2521-121">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |
|<span data-ttu-id="e2521-122">Warnung durch legitime Verwendung ausgelöst</span><span class="sxs-lookup"><span data-stu-id="e2521-122">Alert triggered by legitimate use</span></span> <br/><span data-ttu-id="e2521-123">Falsche Warnung</span><span class="sxs-lookup"><span data-stu-id="e2521-123">Inaccurate alert</span></span>    |[<span data-ttu-id="e2521-124">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e2521-124">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="e2521-125">oder</span><span class="sxs-lookup"><span data-stu-id="e2521-125">or</span></span> <br/>[<span data-ttu-id="e2521-126">Erkennung erweiterter Azure-Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="e2521-126">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="e2521-127">Verwalten von Benachrichtigungen im Cloud-App-Sicherheitsportal</span><span class="sxs-lookup"><span data-stu-id="e2521-127">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |


## <a name="next-steps"></a><span data-ttu-id="e2521-128">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="e2521-128">Next steps</span></span>

- [<span data-ttu-id="e2521-129">Genehmigen oder Ablehnen von Aktionen im Zusammenhang mit der automatischen Untersuchung und Reaktion</span><span class="sxs-lookup"><span data-stu-id="e2521-129">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)
- [<span data-ttu-id="e2521-130">Erfahren Sie mehr über das Info-Center</span><span class="sxs-lookup"><span data-stu-id="e2521-130">Learn more about the Action center</span></span>](mtp-action-center.md)
- [<span data-ttu-id="e2521-131">Proaktive Suche nach Bedrohungen mit der erweiterten Suche in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e2521-131">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>](advanced-hunting-overview.md)
