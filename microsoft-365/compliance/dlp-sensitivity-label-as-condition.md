---
title: Verwenden von Vertraulichkeitsbezeichnungen als Bedingungen in DLP-Richtlinien
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie mehr über die Dienste und Elementtypen, die Sie mit Vertraulichkeitsbezeichnungen als Bedingungen in DLP-Richtlinien verwenden können.
ms.openlocfilehash: 19bd80de225f703b5c280163e94826498fa097bd
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876294"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies"></a><span data-ttu-id="96d7c-103">Verwenden von Vertraulichkeitsbezeichnungen als Bedingungen in DLP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="96d7c-103">Use sensitivity labels as conditions in DLP policies</span></span>

<span data-ttu-id="96d7c-104">Sie können [Vertraulichkeitsbezeichnungen](sensitivity-labels.md) als Bedingung in DLP-Richtlinien für folgende Speicherorte verwenden:</span><span class="sxs-lookup"><span data-stu-id="96d7c-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="96d7c-105">Exchange Online-E-Mails</span><span class="sxs-lookup"><span data-stu-id="96d7c-105">Exchange Online email messages</span></span>
- <span data-ttu-id="96d7c-106">Microsoft Office SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="96d7c-106">SharePoint Online</span></span>
- <span data-ttu-id="96d7c-107">OneDrive for Business-Websites</span><span class="sxs-lookup"><span data-stu-id="96d7c-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="96d7c-108">Windows 10-Geräte</span><span class="sxs-lookup"><span data-stu-id="96d7c-108">Windows 10 devices</span></span>

<span data-ttu-id="96d7c-109">Vertraulichkeitsbezeichnungen werden als Option in der Liste **Inhalt enthält** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="96d7c-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="96d7c-110">![Vertraulichkeitsbezeichnungen als Bedingung](../media/dlp-sensitivity-label-as-a-condition.png)</span><span class="sxs-lookup"><span data-stu-id="96d7c-110">![sensitivity label as a condition](../media/dlp-sensitivity-label-as-a-condition.png)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96d7c-111">**Vertraulichkeitsbezeichnungen** als Bedingung werden nicht verfügbar sein, wenn Sie **Teams-Chat und Kanalnachrichten** als Ort für die Anwendung der DLP-Richtlinie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="96d7c-111">**Sensitivity Labels** as a condition will not be available if you have selected **Teams chat and channel messages** as a location to apply the DLP policy.</span></span>


## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="96d7c-112">Unterstützte Elemente, Szenarien und Richtlinientipps</span><span class="sxs-lookup"><span data-stu-id="96d7c-112">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="96d7c-113">Sie können Vertraulichkeitsbezeichnungen als Bedingungen für diese Elemente und in diesen Szenarien verwenden.</span><span class="sxs-lookup"><span data-stu-id="96d7c-113">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="96d7c-114">unterstützte Elemente</span><span class="sxs-lookup"><span data-stu-id="96d7c-114">Supported items</span></span>

|<span data-ttu-id="96d7c-115">Dienst</span><span class="sxs-lookup"><span data-stu-id="96d7c-115">Service</span></span>  |<span data-ttu-id="96d7c-116">Elementtyp</span><span class="sxs-lookup"><span data-stu-id="96d7c-116">Item type</span></span>  |<span data-ttu-id="96d7c-117">Verfügbar für Richtlinientipps</span><span class="sxs-lookup"><span data-stu-id="96d7c-117">Available to policy tip</span></span>  |<span data-ttu-id="96d7c-118">Durchsetzbar</span><span class="sxs-lookup"><span data-stu-id="96d7c-118">Enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="96d7c-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="96d7c-119">Exchange</span></span>    |<span data-ttu-id="96d7c-120">E-Mail-Nachricht</span><span class="sxs-lookup"><span data-stu-id="96d7c-120">email message</span></span>         |<span data-ttu-id="96d7c-121">ja</span><span class="sxs-lookup"><span data-stu-id="96d7c-121">yes</span></span>         |<span data-ttu-id="96d7c-122">ja</span><span class="sxs-lookup"><span data-stu-id="96d7c-122">yes</span></span>         |
|<span data-ttu-id="96d7c-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="96d7c-123">Exchange</span></span>    |<span data-ttu-id="96d7c-124">E-Mail-Anlage</span><span class="sxs-lookup"><span data-stu-id="96d7c-124">email attachment</span></span>         |<span data-ttu-id="96d7c-125">nein \*</span><span class="sxs-lookup"><span data-stu-id="96d7c-125">no \*</span></span>         |<span data-ttu-id="96d7c-126">ja \*</span><span class="sxs-lookup"><span data-stu-id="96d7c-126">yes \*</span></span>         |
|<span data-ttu-id="96d7c-127">Microsoft Office SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="96d7c-127">SharePoint Online</span></span>     |<span data-ttu-id="96d7c-128">Elemente in Microsoft Office SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="96d7c-128">items in SharePoint Online</span></span>         |<span data-ttu-id="96d7c-129">ja</span><span class="sxs-lookup"><span data-stu-id="96d7c-129">yes</span></span>         |<span data-ttu-id="96d7c-130">ja</span><span class="sxs-lookup"><span data-stu-id="96d7c-130">yes</span></span>         |
|<span data-ttu-id="96d7c-131">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="96d7c-131">OneDrive for Business</span></span>     |<span data-ttu-id="96d7c-132">Elemente</span><span class="sxs-lookup"><span data-stu-id="96d7c-132">items</span></span>         |<span data-ttu-id="96d7c-133">ja</span><span class="sxs-lookup"><span data-stu-id="96d7c-133">yes</span></span>         |<span data-ttu-id="96d7c-134">ja</span><span class="sxs-lookup"><span data-stu-id="96d7c-134">yes</span></span>         |
|<span data-ttu-id="96d7c-135">Teams</span><span class="sxs-lookup"><span data-stu-id="96d7c-135">Teams</span></span>     |<span data-ttu-id="96d7c-136">Microsoft Teams- und Kanalnachrichten</span><span class="sxs-lookup"><span data-stu-id="96d7c-136">Teams and channel messages</span></span>         |<span data-ttu-id="96d7c-137">nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="96d7c-137">not applicable</span></span>         |<span data-ttu-id="96d7c-138">nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="96d7c-138">not applicable</span></span>         |
|<span data-ttu-id="96d7c-139">Teams</span><span class="sxs-lookup"><span data-stu-id="96d7c-139">Teams</span></span>     |<span data-ttu-id="96d7c-140">Anlagen</span><span class="sxs-lookup"><span data-stu-id="96d7c-140">attachments</span></span>         |<span data-ttu-id="96d7c-141">ja \*\*</span><span class="sxs-lookup"><span data-stu-id="96d7c-141">yes \*\*</span></span>         |<span data-ttu-id="96d7c-142">ja \*\*</span><span class="sxs-lookup"><span data-stu-id="96d7c-142">yes \*\*</span></span>         |
|<span data-ttu-id="96d7c-143">Windows 10-Geräte</span><span class="sxs-lookup"><span data-stu-id="96d7c-143">Windows 10 devices</span></span>     |<span data-ttu-id="96d7c-144">Elemente</span><span class="sxs-lookup"><span data-stu-id="96d7c-144">items</span></span>         |<span data-ttu-id="96d7c-145">ja</span><span class="sxs-lookup"><span data-stu-id="96d7c-145">yes</span></span>         |<span data-ttu-id="96d7c-146">ja</span><span class="sxs-lookup"><span data-stu-id="96d7c-146">yes</span></span>         |
|<span data-ttu-id="96d7c-147">MCAS (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="96d7c-147">MCAS (preview)</span></span> |<span data-ttu-id="96d7c-148">Elemente</span><span class="sxs-lookup"><span data-stu-id="96d7c-148">items</span></span>         |<span data-ttu-id="96d7c-149">ja</span><span class="sxs-lookup"><span data-stu-id="96d7c-149">yes</span></span>         |<span data-ttu-id="96d7c-150">ja</span><span class="sxs-lookup"><span data-stu-id="96d7c-150">yes</span></span>         |

<span data-ttu-id="96d7c-151">\* Die DLP-Erkennung und das Erzwingen von Vertraulichkeitsbezeichnungen auf E-Mails und Anlagen während der Übertragung werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="96d7c-151">\* DLP detection and enforcement of sensitivity labels on emails and attachments are supported in-transit.</span></span> <span data-ttu-id="96d7c-152">DLP-Richtlinientipps für Vertraulichkeitsbezeichnungen in E-Mails werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="96d7c-152">DLP policy tips of sensitivity labeled email attachments are not.</span></span>

<span data-ttu-id="96d7c-153">\*\* Anlagen, die in Teams über einen 1:1-Chat oder über Kanäle gesendet werden, werden automatisch auf OneDrive for Business und Microsoft Office SharePoint Online hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="96d7c-153">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to OneDrive for Business and SharePoint.</span></span> <span data-ttu-id="96d7c-154">Wenn also Microsoft Office SharePoint Online oder OneDrive for Business als Speicherorte in ihrer DLP-Richtlinie enthalten sind, werden bezeichnete Anlagen, die in Teams gesendet wurden, automatisch in den Umfang dieser Bedingung einbezogen.</span><span class="sxs-lookup"><span data-stu-id="96d7c-154">So if SharePoint Online or OneDrive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="96d7c-155">Teams muss in der DLP-Richtlinie nicht als Speicherort ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="96d7c-155">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="96d7c-156">Unterstützte Szenarien</span><span class="sxs-lookup"><span data-stu-id="96d7c-156">Supported scenarios</span></span>

- <span data-ttu-id="96d7c-157">Der DLP-Administrator kann eine Liste aller Vertraulichkeitsbezeichnugen im Mandanten anzeigen, wenn er eine oder mehrere Vertraulichkeitsbezeichnungen als Bedingung einschließt.</span><span class="sxs-lookup"><span data-stu-id="96d7c-157">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>

- <span data-ttu-id="96d7c-158">Die Verwendung von Vertraulichkeitsbezeichnungen als Bedingung wird in allen Workloads unterstützt, wie in der obigen Supportmatrix angegeben.</span><span class="sxs-lookup"><span data-stu-id="96d7c-158">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above.</span></span>

- <span data-ttu-id="96d7c-159">DLP-Richtlinientipps werden weiterhin für Workloads (mit Ausnahme von Outlook Win32) angezeigt, die eine Vertraulichkeitsbezeichnung als Bedingung enthalten.</span><span class="sxs-lookup"><span data-stu-id="96d7c-159">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>

- <span data-ttu-id="96d7c-160">Vertraulichkeitsbezeichnungen werden auch als Bestandteil der Schadensbericht-E-Mail angezeigt, wenn eine DLP-Richtlinie mit einer Vertraulichkeitsbezeichnung als Bedingung übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="96d7c-160">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>

- <span data-ttu-id="96d7c-161">Details zur Vertraulichkeitsbezeichnung werden auch im Überwachungsprotokoll „DLP-Regelabgleich“ für eine Übereinstimmung mit einer DLP-Richtlinie angezeigt, die die Vertraulichkeitsbezeichnung als Bedingung enthält.</span><span class="sxs-lookup"><span data-stu-id="96d7c-161">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="96d7c-162">Support-Richtlinientipps</span><span class="sxs-lookup"><span data-stu-id="96d7c-162">Support policy tips</span></span>


|<span data-ttu-id="96d7c-163">Workload</span><span class="sxs-lookup"><span data-stu-id="96d7c-163">Workload</span></span>  |<span data-ttu-id="96d7c-164">Richtlinientipps unterstützt / nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="96d7c-164">Policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="96d7c-165">OWA</span><span class="sxs-lookup"><span data-stu-id="96d7c-165">OWA</span></span> |    <span data-ttu-id="96d7c-166">unterstützt</span><span class="sxs-lookup"><span data-stu-id="96d7c-166">supported</span></span>     |
|<span data-ttu-id="96d7c-167">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="96d7c-167">Outlook Win 32</span></span>    |  <span data-ttu-id="96d7c-168">nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="96d7c-168">not supported</span></span>       |
|<span data-ttu-id="96d7c-169">Microsoft Office SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="96d7c-169">SharePoint</span></span>   |   <span data-ttu-id="96d7c-170">unterstützt</span><span class="sxs-lookup"><span data-stu-id="96d7c-170">supported</span></span>      |
|<span data-ttu-id="96d7c-171">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="96d7c-171">OneDrive for Business</span></span>    |    <span data-ttu-id="96d7c-172">unterstützt</span><span class="sxs-lookup"><span data-stu-id="96d7c-172">supported</span></span>     |
|<span data-ttu-id="96d7c-173">Endpunktgeräte</span><span class="sxs-lookup"><span data-stu-id="96d7c-173">endpoint devices</span></span>   |  <span data-ttu-id="96d7c-174">nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="96d7c-174">not supported</span></span>       |
