---
title: Konfigurieren von Microsoft Defender Antivirus-Features
description: Sie können Microsoft Defender Antivirus Features mit Intune, Microsoft Endpoint Configuration Manager, Gruppenrichtlinien und PowerShell konfigurieren.
keywords: Microsoft Defender Antivirus, Antischadsoftware, Sicherheit, Defender, konfigurieren, Konfiguration, Config Manager, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, Verwaltung mobiler Geräte, GP, Gruppenrichtlinie, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 7fa5959ede9f0c71c75cefafc0fcb0d4376a1a4f
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925395"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="00bff-104">Konfigurieren von Microsoft Defender Antivirus-Features</span><span class="sxs-lookup"><span data-stu-id="00bff-104">Configure Microsoft Defender Antivirus features</span></span>


<span data-ttu-id="00bff-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="00bff-105">**Applies to:**</span></span>

- [<span data-ttu-id="00bff-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="00bff-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="00bff-107">Sie können Microsoft Defender Antivirus mit einer Reihe von Tools konfigurieren, z. B.:</span><span class="sxs-lookup"><span data-stu-id="00bff-107">You can configure Microsoft Defender Antivirus with a number of tools, such as:</span></span>

- <span data-ttu-id="00bff-108">Microsoft Endpoint Manager (einschließlich Microsoft Intune und Microsoft Endpoint Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="00bff-108">Microsoft Endpoint Manager (which includes Microsoft Intune and Microsoft Endpoint Configuration Manager)</span></span>
- <span data-ttu-id="00bff-109">Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="00bff-109">Group Policy</span></span>
- <span data-ttu-id="00bff-110">PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="00bff-110">PowerShell cmdlets</span></span>
- <span data-ttu-id="00bff-111">Windows-Verwaltungsinstrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="00bff-111">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="00bff-112">Die folgenden allgemeinen Kategorien von Features können konfiguriert werden:</span><span class="sxs-lookup"><span data-stu-id="00bff-112">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="00bff-113">Über die Cloud bereitgestellter Schutz.</span><span class="sxs-lookup"><span data-stu-id="00bff-113">Cloud-delivered protection.</span></span> <span data-ttu-id="00bff-114">Anzeigen [des über die Cloud bereitgestellten Schutzes und Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="00bff-114">See [Cloud-delivered protection and Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md)</span></span>
 
- <span data-ttu-id="00bff-115">Always-on-Echtzeitschutz, einschließlich Verhaltens-, Heuristik- und Machine Learning-basierter Schutz.</span><span class="sxs-lookup"><span data-stu-id="00bff-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection.</span></span> <span data-ttu-id="00bff-116">Siehe [Konfigurieren von Verhaltens-, Heuristik- und Echtzeitschutz.](configure-protection-features-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="00bff-116">See [Configure behavioral, heuristic, and real-time protection](configure-protection-features-microsoft-defender-antivirus.md).</span></span>

- <span data-ttu-id="00bff-117">Wie Endbenutzer mit dem Client auf einzelnen Endpunkten interagieren.</span><span class="sxs-lookup"><span data-stu-id="00bff-117">How end users interact with the client on individual endpoints.</span></span> <span data-ttu-id="00bff-118">Informationen finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="00bff-118">See the following resources:</span></span>
   
   - [<span data-ttu-id="00bff-119">Benutzer am Anzeigen oder Interagieren mit der Microsoft Defender Antivirus Benutzeroberfläche hindern</span><span class="sxs-lookup"><span data-stu-id="00bff-119">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>](prevent-end-user-interaction-microsoft-defender-antivirus.md)

   - [<span data-ttu-id="00bff-120">Verhindern oder zulassen, dass Benutzer Microsoft Defender Antivirus Richtlinieneinstellungen lokal ändern</span><span class="sxs-lookup"><span data-stu-id="00bff-120">Prevent or allow users to locally modify Microsoft Defender Antivirus policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md) 

> [!TIP]
> <span data-ttu-id="00bff-121">Lesen Sie [die Referenzthemen für Verwaltungs- und Konfigurationstools.](configuration-management-reference-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="00bff-121">Review [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md).</span></span>
