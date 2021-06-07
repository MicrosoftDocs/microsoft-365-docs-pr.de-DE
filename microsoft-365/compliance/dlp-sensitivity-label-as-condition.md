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
ms.openlocfilehash: 94d5e9f53471f6113dcc755995a3f94e95a58e53
ms.sourcegitcommit: 50f484fc501d81506a714b127a56a6979888d849
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52779843"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies"></a><span data-ttu-id="69dd5-103">Verwenden von Vertraulichkeitsbezeichnungen als Bedingungen in DLP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="69dd5-103">Use sensitivity labels as conditions in DLP policies</span></span>

<span data-ttu-id="69dd5-104">Sie können [Vertraulichkeitsbezeichnungen](sensitivity-labels.md) als Bedingung in DLP-Richtlinien für folgende Speicherorte verwenden:</span><span class="sxs-lookup"><span data-stu-id="69dd5-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="69dd5-105">Exchange Online-E-Mails</span><span class="sxs-lookup"><span data-stu-id="69dd5-105">Exchange Online email messages</span></span>
- <span data-ttu-id="69dd5-106">Microsoft Office SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="69dd5-106">SharePoint Online</span></span>
- <span data-ttu-id="69dd5-107">OneDrive for Business-Websites</span><span class="sxs-lookup"><span data-stu-id="69dd5-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="69dd5-108">Windows 10-Geräte</span><span class="sxs-lookup"><span data-stu-id="69dd5-108">Windows 10 devices</span></span>

<span data-ttu-id="69dd5-109">Vertraulichkeitsbezeichnungen werden als Option in der Liste **Inhalt enthält** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="69dd5-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="69dd5-110">![Vertraulichkeitsbezeichnungen als Bedingung](../media/dlp-sensitivity-label-as-a-condition.png)</span><span class="sxs-lookup"><span data-stu-id="69dd5-110">![sensitivity label as a condition](../media/dlp-sensitivity-label-as-a-condition.png)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="69dd5-111">**Vertraulichkeitsbezeichnungen** als Bedingung werden nicht verfügbar sein, wenn Sie **Teams-Chat und Kanalnachrichten** als Ort für die Anwendung der DLP-Richtlinie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="69dd5-111">**Sensitivity Labels** as a condition will not be available if you have selected **Teams chat and channel messages** as a location to apply the DLP policy.</span></span>


## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="69dd5-112">Unterstützte Elemente, Szenarien und Richtlinientipps</span><span class="sxs-lookup"><span data-stu-id="69dd5-112">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="69dd5-113">Sie können Vertraulichkeitsbezeichnungen als Bedingungen für diese Elemente und in diesen Szenarien verwenden.</span><span class="sxs-lookup"><span data-stu-id="69dd5-113">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="69dd5-114">unterstützte Elemente</span><span class="sxs-lookup"><span data-stu-id="69dd5-114">Supported items</span></span>

|<span data-ttu-id="69dd5-115">Dienst</span><span class="sxs-lookup"><span data-stu-id="69dd5-115">Service</span></span>  |<span data-ttu-id="69dd5-116">Elementtyp</span><span class="sxs-lookup"><span data-stu-id="69dd5-116">Item type</span></span>  |<span data-ttu-id="69dd5-117">Verfügbar für Richtlinientipps</span><span class="sxs-lookup"><span data-stu-id="69dd5-117">Available to policy tip</span></span>  |<span data-ttu-id="69dd5-118">Durchsetzbar</span><span class="sxs-lookup"><span data-stu-id="69dd5-118">Enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="69dd5-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="69dd5-119">Exchange</span></span>    |<span data-ttu-id="69dd5-120">E-Mail-Nachricht</span><span class="sxs-lookup"><span data-stu-id="69dd5-120">email message</span></span>         |<span data-ttu-id="69dd5-121">ja</span><span class="sxs-lookup"><span data-stu-id="69dd5-121">yes</span></span>         |<span data-ttu-id="69dd5-122">ja</span><span class="sxs-lookup"><span data-stu-id="69dd5-122">yes</span></span>         |
|<span data-ttu-id="69dd5-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="69dd5-123">Exchange</span></span>    |<span data-ttu-id="69dd5-124">E-Mail-Anlage</span><span class="sxs-lookup"><span data-stu-id="69dd5-124">email attachment</span></span>         |<span data-ttu-id="69dd5-125">nein</span><span class="sxs-lookup"><span data-stu-id="69dd5-125">no</span></span>         |<span data-ttu-id="69dd5-126">ja \*</span><span class="sxs-lookup"><span data-stu-id="69dd5-126">yes \*</span></span>         |
|<span data-ttu-id="69dd5-127">Microsoft Office SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="69dd5-127">SharePoint Online</span></span>     |<span data-ttu-id="69dd5-128">Elemente in Microsoft Office SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="69dd5-128">items in SharePoint Online</span></span>         |<span data-ttu-id="69dd5-129">ja</span><span class="sxs-lookup"><span data-stu-id="69dd5-129">yes</span></span>         |<span data-ttu-id="69dd5-130">ja</span><span class="sxs-lookup"><span data-stu-id="69dd5-130">yes</span></span>         |
|<span data-ttu-id="69dd5-131">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="69dd5-131">OneDrive for Business</span></span>     |<span data-ttu-id="69dd5-132">Elemente</span><span class="sxs-lookup"><span data-stu-id="69dd5-132">items</span></span>         |<span data-ttu-id="69dd5-133">ja</span><span class="sxs-lookup"><span data-stu-id="69dd5-133">yes</span></span>         |<span data-ttu-id="69dd5-134">ja</span><span class="sxs-lookup"><span data-stu-id="69dd5-134">yes</span></span>         |
|<span data-ttu-id="69dd5-135">Teams</span><span class="sxs-lookup"><span data-stu-id="69dd5-135">Teams</span></span>     |<span data-ttu-id="69dd5-136">Microsoft Teams- und Kanalnachrichten</span><span class="sxs-lookup"><span data-stu-id="69dd5-136">Teams and channel messages</span></span>         |<span data-ttu-id="69dd5-137">nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="69dd5-137">not applicable</span></span>         |<span data-ttu-id="69dd5-138">nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="69dd5-138">not applicable</span></span>         |
|<span data-ttu-id="69dd5-139">Teams</span><span class="sxs-lookup"><span data-stu-id="69dd5-139">Teams</span></span>     |<span data-ttu-id="69dd5-140">Anlagen</span><span class="sxs-lookup"><span data-stu-id="69dd5-140">attachments</span></span>         |<span data-ttu-id="69dd5-141">ja \*\*</span><span class="sxs-lookup"><span data-stu-id="69dd5-141">yes \*\*</span></span>         |<span data-ttu-id="69dd5-142">ja \*\*</span><span class="sxs-lookup"><span data-stu-id="69dd5-142">yes \*\*</span></span>         |
|<span data-ttu-id="69dd5-143">Windows 10-Geräte</span><span class="sxs-lookup"><span data-stu-id="69dd5-143">Windows 10 devices</span></span>     |<span data-ttu-id="69dd5-144">Elemente</span><span class="sxs-lookup"><span data-stu-id="69dd5-144">items</span></span>         |<span data-ttu-id="69dd5-145">ja</span><span class="sxs-lookup"><span data-stu-id="69dd5-145">yes</span></span>         |<span data-ttu-id="69dd5-146">ja</span><span class="sxs-lookup"><span data-stu-id="69dd5-146">yes</span></span>         |
|<span data-ttu-id="69dd5-147">MCAS (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="69dd5-147">MCAS (preview)</span></span> |<span data-ttu-id="69dd5-148">Elemente</span><span class="sxs-lookup"><span data-stu-id="69dd5-148">items</span></span>         |<span data-ttu-id="69dd5-149">ja</span><span class="sxs-lookup"><span data-stu-id="69dd5-149">yes</span></span>         |<span data-ttu-id="69dd5-150">ja</span><span class="sxs-lookup"><span data-stu-id="69dd5-150">yes</span></span>         |

<span data-ttu-id="69dd5-151">\* DLP-Erkennung von E-Mail-Anlagen mit Vertraulichkeitsbezeichnungen wird nur für Office-Dateitypen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="69dd5-151">\* DLP detection of sensitivity labeled email attachments are supported for Office file types only.</span></span>

<span data-ttu-id="69dd5-152">\*\* Anlagen, die in Teams über einen 1:1-Chat oder über Kanäle gesendet werden, werden automatisch auf OneDrive for Business und Microsoft Office SharePoint Online hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="69dd5-152">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to OneDrive for Business and SharePoint.</span></span> <span data-ttu-id="69dd5-153">Wenn also Microsoft Office SharePoint Online oder OneDrive for Business als Speicherorte in ihrer DLP-Richtlinie enthalten sind, werden bezeichnete Anlagen, die in Teams gesendet wurden, automatisch in den Umfang dieser Bedingung einbezogen.</span><span class="sxs-lookup"><span data-stu-id="69dd5-153">So if SharePoint Online or OneDrive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="69dd5-154">Teams muss in der DLP-Richtlinie nicht als Speicherort ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="69dd5-154">Teams as a location does not need to be selected in the DLP policy.</span></span>

> [!NOTE]
> <span data-ttu-id="69dd5-155">Die DLP-Funktion zum Erkennen von Vertraulichkeitsbezeichnungen in SharePoint und OneDrive for Business ist eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="69dd5-155">DLP's ability to detect sensitivity labels in SharePoint and OneDrive for business is limited.</span></span> <span data-ttu-id="69dd5-156">Weitere Informationen finden Sie unter [Aktivieren von Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive](sensitivity-labels-sharepoint-onedrive-files.md#limitations).</span><span class="sxs-lookup"><span data-stu-id="69dd5-156">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md#limitations).</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="69dd5-157">Unterstützte Szenarien</span><span class="sxs-lookup"><span data-stu-id="69dd5-157">Supported scenarios</span></span>

- <span data-ttu-id="69dd5-158">Der DLP-Administrator kann eine Liste aller Vertraulichkeitsbezeichnugen im Mandanten anzeigen, wenn er eine oder mehrere Vertraulichkeitsbezeichnungen als Bedingung einschließt.</span><span class="sxs-lookup"><span data-stu-id="69dd5-158">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>

- <span data-ttu-id="69dd5-159">Die Verwendung von Vertraulichkeitsbezeichnungen als Bedingung wird in allen Workloads unterstützt, wie in der obigen Supportmatrix angegeben.</span><span class="sxs-lookup"><span data-stu-id="69dd5-159">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above.</span></span>

- <span data-ttu-id="69dd5-160">DLP-Richtlinientipps werden weiterhin für Workloads (mit Ausnahme von Outlook Win32) angezeigt, die eine Vertraulichkeitsbezeichnung als Bedingung enthalten.</span><span class="sxs-lookup"><span data-stu-id="69dd5-160">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>

- <span data-ttu-id="69dd5-161">Vertraulichkeitsbezeichnungen werden auch als Bestandteil der Schadensbericht-E-Mail angezeigt, wenn eine DLP-Richtlinie mit einer Vertraulichkeitsbezeichnung als Bedingung übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="69dd5-161">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>

- <span data-ttu-id="69dd5-162">Details zur Vertraulichkeitsbezeichnung werden auch im Überwachungsprotokoll „DLP-Regelabgleich“ für eine Übereinstimmung mit einer DLP-Richtlinie angezeigt, die die Vertraulichkeitsbezeichnung als Bedingung enthält.</span><span class="sxs-lookup"><span data-stu-id="69dd5-162">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="69dd5-163">Support-Richtlinientipps</span><span class="sxs-lookup"><span data-stu-id="69dd5-163">Support policy tips</span></span>


|<span data-ttu-id="69dd5-164">Workload</span><span class="sxs-lookup"><span data-stu-id="69dd5-164">Workload</span></span>  |<span data-ttu-id="69dd5-165">Richtlinientipps unterstützt / nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="69dd5-165">Policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="69dd5-166">OWA</span><span class="sxs-lookup"><span data-stu-id="69dd5-166">OWA</span></span> |    <span data-ttu-id="69dd5-167">unterstützt</span><span class="sxs-lookup"><span data-stu-id="69dd5-167">supported</span></span>     |
|<span data-ttu-id="69dd5-168">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="69dd5-168">Outlook Win 32</span></span>    |  <span data-ttu-id="69dd5-169">nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="69dd5-169">not supported</span></span>       |
|<span data-ttu-id="69dd5-170">Microsoft Office SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="69dd5-170">SharePoint</span></span>   |   <span data-ttu-id="69dd5-171">unterstützt</span><span class="sxs-lookup"><span data-stu-id="69dd5-171">supported</span></span>      |
|<span data-ttu-id="69dd5-172">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="69dd5-172">OneDrive for Business</span></span>    |    <span data-ttu-id="69dd5-173">unterstützt</span><span class="sxs-lookup"><span data-stu-id="69dd5-173">supported</span></span>     |
|<span data-ttu-id="69dd5-174">Endpunktgeräte</span><span class="sxs-lookup"><span data-stu-id="69dd5-174">endpoint devices</span></span>   |  <span data-ttu-id="69dd5-175">nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="69dd5-175">not supported</span></span>       |
