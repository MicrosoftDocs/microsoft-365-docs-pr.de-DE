---
title: Optimieren der Bereitstellung und Erkennung von ASR-Regeln
description: Optimieren Sie Ihre Regeln zur Reduzierung der Angriffsfläche (Attack Surface Reduction, ASR), um typische Schadsoftware-Exploits zu identifizieren und zu verhindern.
keywords: Onboard, Intune-Verwaltung, Microsoft Defender for Endpoint, Microsoft Defender, Windows Defender, Attack Surface Reduction, ASR, Security Baseline
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 91295135c833c6b403078bdfd517c7b84ec7d630
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932847"
---
# <a name="optimize-asr-rule-deployment-and-detections"></a><span data-ttu-id="2c754-104">Optimieren der Bereitstellung und Erkennung von ASR-Regeln</span><span class="sxs-lookup"><span data-stu-id="2c754-104">Optimize ASR rule deployment and detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2c754-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2c754-105">**Applies to:**</span></span>
- [<span data-ttu-id="2c754-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="2c754-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2c754-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2c754-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2c754-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="2c754-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="2c754-109">[Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink).</span><span class="sxs-lookup"><span data-stu-id="2c754-109">[Sign up for a free trial](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink).</span></span>

<span data-ttu-id="2c754-110">[Regeln zur Reduzierung der Angriffsfläche (Attack Surface Reduction, ASR)](./attack-surface-reduction.md) identifizieren und verhindern typische Schadsoftware-Exploits.</span><span class="sxs-lookup"><span data-stu-id="2c754-110">[Attack surface reduction (ASR) rules](./attack-surface-reduction.md) identify and prevent typical malware exploits.</span></span> <span data-ttu-id="2c754-111">Sie steuern, wann und wie potenziell schädlicher Code ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="2c754-111">They control when and how potentially malicious code can run.</span></span> <span data-ttu-id="2c754-112">Sie können beispielsweise verhindern, dass JavaScript oder VBScript eine heruntergeladene ausführbare Datei startet, Win32-API-Aufrufe von Office-Makros blockieren und Prozesse blockieren, die von USB-Laufwerken ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2c754-112">For example, they can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, and block processes that run from USB drives.</span></span>

<span data-ttu-id="2c754-113">![Angriffsoberflächenverwaltungskarte](images/secconmgmt_asr_card.png)</span><span class="sxs-lookup"><span data-stu-id="2c754-113">![Attack surface management card](images/secconmgmt_asr_card.png)</span></span><br>
<span data-ttu-id="2c754-114">*Angriffsoberflächenverwaltungskarte*</span><span class="sxs-lookup"><span data-stu-id="2c754-114">*Attack surface management card*</span></span>

<span data-ttu-id="2c754-115">Die *Angriffsoberflächenverwaltungskarte* ist ein Einstiegspunkt für Tools im Microsoft 365 Security Center, die Sie verwenden können, um:</span><span class="sxs-lookup"><span data-stu-id="2c754-115">The *Attack surface management card* is an entry point to tools in Microsoft 365 security center that you can use to:</span></span>

* <span data-ttu-id="2c754-116">Erfahren Sie, wie ASR-Regeln derzeit in Ihrer Organisation bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2c754-116">Understand how ASR rules are currently deployed in your organization.</span></span>
* <span data-ttu-id="2c754-117">Überprüfen Sie ASR-Erkennungen, und identifizieren Sie mögliche falsche Erkennungen.</span><span class="sxs-lookup"><span data-stu-id="2c754-117">Review ASR detections and identify possible incorrect detections.</span></span>
* <span data-ttu-id="2c754-118">Analysieren Sie die Auswirkungen von Ausschlüssen, und generieren Sie die Liste der auszuschließenden Dateipfade.</span><span class="sxs-lookup"><span data-stu-id="2c754-118">Analyze the impact of exclusions and generate the list of file paths to exclude.</span></span>

<span data-ttu-id="2c754-119">Wählen **Sie Go to attack surface management** Monitoring & reports > Attack surface reduction rules > Add  >  **exclusions** aus.</span><span class="sxs-lookup"><span data-stu-id="2c754-119">Select **Go to attack surface management** > **Monitoring & reports > Attack surface reduction rules > Add exclusions**.</span></span> <span data-ttu-id="2c754-120">Von dort aus können Sie zu anderen Abschnitten des Microsoft 365 Security Centers navigieren.</span><span class="sxs-lookup"><span data-stu-id="2c754-120">From there, you can navigate to other sections of Microsoft 365 security center.</span></span>

<span data-ttu-id="2c754-121">![Registerkarte "Ausschlüsse hinzufügen" auf der Seite Attack surface reduction rules in Microsoft 365 Security Center](images/secconmgmt_asr_m365exlusions.png)</span><span class="sxs-lookup"><span data-stu-id="2c754-121">![Add exclusions tab in the Attack surface reduction rules page in Microsoft 365 security center](images/secconmgmt_asr_m365exlusions.png)</span></span><br>
<span data-ttu-id="2c754-122">Die ***Registerkarte Ausschlüsse hinzufügen** auf der Seite Attack surface reduction rules in Microsoft 365 Security Center*</span><span class="sxs-lookup"><span data-stu-id="2c754-122">The ***Add exclusions** tab in the Attack surface reduction rules page in Microsoft 365 security center*</span></span>

> [!NOTE]
> <span data-ttu-id="2c754-123">Für den Zugriff auf Microsoft 365 Security Center benötigen Sie eine Microsoft 365 E3- oder E5-Lizenz und ein Konto mit bestimmten Rollen in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2c754-123">To access Microsoft 365 security center, you need a Microsoft 365 E3 or E5 license and an account that has certain roles on Azure Active Directory.</span></span> <span data-ttu-id="2c754-124">[Lesen Sie mehr über erforderliche Lizenzen und Berechtigungen](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span><span class="sxs-lookup"><span data-stu-id="2c754-124">[Read about required licenses and permissions](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span></span>

<span data-ttu-id="2c754-125">Weitere Informationen zur Bereitstellung von ASR-Regeln in Microsoft 365 Security Center finden Sie unter Überwachen und Verwalten der Bereitstellung und Erkennung von [ASR-Regeln.](https://docs.microsoft.com/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections)</span><span class="sxs-lookup"><span data-stu-id="2c754-125">For more information about ASR rule deployment in Microsoft 365 security center, see [Monitor and manage ASR rule deployment and detections](https://docs.microsoft.com/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections).</span></span>

<span data-ttu-id="2c754-126">**Verwandte Themen**</span><span class="sxs-lookup"><span data-stu-id="2c754-126">**Related topics**</span></span>

* [<span data-ttu-id="2c754-127">Sicherstellen, dass Ihre Geräte ordnungsgemäß konfiguriert sind</span><span class="sxs-lookup"><span data-stu-id="2c754-127">Ensure your devices are configured properly</span></span>](configure-machines.md)
* [<span data-ttu-id="2c754-128">Get devices onboarded to Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2c754-128">Get devices onboarded to Microsoft Defender for Endpoint</span></span>](configure-machines-onboarding.md)
* [<span data-ttu-id="2c754-129">Überwachen der Einhaltung der Microsoft Defender for Endpoint-Sicherheitsgrundlinie</span><span class="sxs-lookup"><span data-stu-id="2c754-129">Monitor compliance to the Microsoft Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md)
