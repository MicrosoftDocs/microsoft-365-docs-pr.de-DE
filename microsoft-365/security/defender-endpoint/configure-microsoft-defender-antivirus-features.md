---
title: Konfigurieren von Microsoft Defender Antivirus-Features
description: Sie können Microsoft Defender Antivirus Features mit Intune, Microsoft Endpoint Configuration Manager, Gruppenrichtlinien und PowerShell konfigurieren.
keywords: Microsoft Defender Antivirus, Antischadsoftware, Sicherheit, Defender, konfigurieren, Konfiguration, Konfigurations-Manager, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, Verwaltung mobiler Geräte, GP, Gruppenrichtlinie, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 6ef9a2c34a88d7c9f5506c681088db9dc84cb0cc
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789027"
---
# <a name="configure-microsoft-defender-antivirus-features"></a><span data-ttu-id="ff294-104">Konfigurieren von Microsoft Defender Antivirus-Features</span><span class="sxs-lookup"><span data-stu-id="ff294-104">Configure Microsoft Defender Antivirus features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ff294-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="ff294-105">**Applies to:**</span></span>

- [<span data-ttu-id="ff294-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="ff294-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="ff294-107">Sie können Microsoft Defender Antivirus mit einer Reihe von Tools konfigurieren, z. B.:</span><span class="sxs-lookup"><span data-stu-id="ff294-107">You can configure Microsoft Defender Antivirus with a number of tools, such as:</span></span>

- <span data-ttu-id="ff294-108">Microsoft Endpoint Manager (einschließlich Microsoft Intune und Microsoft Endpoint Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="ff294-108">Microsoft Endpoint Manager (which includes Microsoft Intune and Microsoft Endpoint Configuration Manager)</span></span>
- <span data-ttu-id="ff294-109">Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="ff294-109">Group Policy</span></span>
- <span data-ttu-id="ff294-110">PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ff294-110">PowerShell cmdlets</span></span>
- <span data-ttu-id="ff294-111">Windows-Verwaltungsinstrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="ff294-111">Windows Management Instrumentation (WMI)</span></span>

<span data-ttu-id="ff294-112">Die folgenden allgemeinen Kategorien von Features können konfiguriert werden:</span><span class="sxs-lookup"><span data-stu-id="ff294-112">The following broad categories of features can be configured:</span></span>

- <span data-ttu-id="ff294-113">Über die Cloud bereitgestellter Schutz.</span><span class="sxs-lookup"><span data-stu-id="ff294-113">Cloud-delivered protection.</span></span> <span data-ttu-id="ff294-114">Anzeigen [des über die Cloud bereitgestellten Schutzes und Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="ff294-114">See [Cloud-delivered protection and Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md)</span></span>
 
- <span data-ttu-id="ff294-115">Always-on-Echtzeitschutz, einschließlich Verhaltens-, Heuristik- und Machine Learning-basierter Schutz.</span><span class="sxs-lookup"><span data-stu-id="ff294-115">Always-on real-time protection, including behavioral, heuristic, and machine-learning-based protection.</span></span> <span data-ttu-id="ff294-116">Siehe [Konfigurieren von Verhaltens-, Heuristik- und Echtzeitschutz.](configure-protection-features-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="ff294-116">See [Configure behavioral, heuristic, and real-time protection](configure-protection-features-microsoft-defender-antivirus.md).</span></span>

- <span data-ttu-id="ff294-117">Wie Endbenutzer mit dem Client auf einzelnen Endpunkten interagieren.</span><span class="sxs-lookup"><span data-stu-id="ff294-117">How end users interact with the client on individual endpoints.</span></span> <span data-ttu-id="ff294-118">Informationen finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="ff294-118">See the following resources:</span></span>
   
   - [<span data-ttu-id="ff294-119">Benutzer am Anzeigen oder Interagieren mit der Microsoft Defender Antivirus Benutzeroberfläche hindern</span><span class="sxs-lookup"><span data-stu-id="ff294-119">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>](prevent-end-user-interaction-microsoft-defender-antivirus.md)

   - [<span data-ttu-id="ff294-120">Verhindern oder zulassen, dass Benutzer Microsoft Defender Antivirus Richtlinieneinstellungen lokal ändern</span><span class="sxs-lookup"><span data-stu-id="ff294-120">Prevent or allow users to locally modify Microsoft Defender Antivirus policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md) 

> [!TIP]
> <span data-ttu-id="ff294-121">Lesen Sie [die Referenzthemen für Verwaltungs- und Konfigurationstools.](configuration-management-reference-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="ff294-121">Review [Reference topics for management and configuration tools](configuration-management-reference-microsoft-defender-antivirus.md).</span></span>