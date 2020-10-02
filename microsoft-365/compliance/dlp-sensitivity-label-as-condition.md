---
title: Verwenden von Vertraulichkeitsbezeichnungen als Bedingungen in DLP-Richtlinien (Vorschau)
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
ms.openlocfilehash: 561a6cbd7b8aeb9082862319c5cc6419fd79c896
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321110"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies-preview"></a><span data-ttu-id="52207-103">Verwenden von Vertraulichkeitsbezeichnungen als Bedingungen in DLP-Richtlinien (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="52207-103">Use sensitivity labels as conditions in DLP policies (preview)</span></span>

<span data-ttu-id="52207-104">Sie können [Vertraulichkeitsbezeichnungen](sensitivity-labels.md) als Bedingung in DLP-Richtlinien für folgende Speicherorte verwenden:</span><span class="sxs-lookup"><span data-stu-id="52207-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="52207-105">Exchange Online-E-Mails</span><span class="sxs-lookup"><span data-stu-id="52207-105">Exchange Online email messages</span></span>
- <span data-ttu-id="52207-106">Microsoft Office SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="52207-106">SharePoint Online</span></span>
- <span data-ttu-id="52207-107">OneDrive for Business-Websites</span><span class="sxs-lookup"><span data-stu-id="52207-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="52207-108">Windows 10-Geräte</span><span class="sxs-lookup"><span data-stu-id="52207-108">Windows 10 devices</span></span>

<span data-ttu-id="52207-109">Vertraulichkeitsbezeichnungen werden als Option in der Liste **Inhalt enthält** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="52207-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

![Vertraulichkeitsbezeichnungen als Bedingung](../media/dlp-sensitivity-label-as-a-condition.png)

## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="52207-111">Unterstützte Elemente, Szenarien und Richtlinientipps</span><span class="sxs-lookup"><span data-stu-id="52207-111">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="52207-112">Sie können Vertraulichkeitsbezeichnungen als Bedingungen für diese Elemente und in diesen Szenarien verwenden.</span><span class="sxs-lookup"><span data-stu-id="52207-112">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="52207-113">unterstützte Elemente</span><span class="sxs-lookup"><span data-stu-id="52207-113">Supported items</span></span>

|<span data-ttu-id="52207-114">Dienst</span><span class="sxs-lookup"><span data-stu-id="52207-114">service</span></span>  |<span data-ttu-id="52207-115">Elementtyp</span><span class="sxs-lookup"><span data-stu-id="52207-115">item type</span></span>  |<span data-ttu-id="52207-116">verfügbar für Richtlinientipps</span><span class="sxs-lookup"><span data-stu-id="52207-116">available to policy tip</span></span>  |<span data-ttu-id="52207-117">durchsetzbar</span><span class="sxs-lookup"><span data-stu-id="52207-117">enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="52207-118">Exchange</span><span class="sxs-lookup"><span data-stu-id="52207-118">Exchange</span></span>    |<span data-ttu-id="52207-119">E-Mail-Nachricht</span><span class="sxs-lookup"><span data-stu-id="52207-119">email message</span></span>         |<span data-ttu-id="52207-120">ja</span><span class="sxs-lookup"><span data-stu-id="52207-120">yes</span></span>         |<span data-ttu-id="52207-121">ja</span><span class="sxs-lookup"><span data-stu-id="52207-121">yes</span></span>         |
|<span data-ttu-id="52207-122">Exchange</span><span class="sxs-lookup"><span data-stu-id="52207-122">Exchange</span></span>    |<span data-ttu-id="52207-123">E-Mail-Anlage</span><span class="sxs-lookup"><span data-stu-id="52207-123">email attachment</span></span>         |<span data-ttu-id="52207-124">nein \*</span><span class="sxs-lookup"><span data-stu-id="52207-124">no \*</span></span>         |<span data-ttu-id="52207-125">nein \*</span><span class="sxs-lookup"><span data-stu-id="52207-125">no \*</span></span>         |
|<span data-ttu-id="52207-126">Microsoft Office SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="52207-126">SharePoint Online</span></span>     |<span data-ttu-id="52207-127">Elemente in Microsoft Office SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="52207-127">items in SharePoint Online</span></span>         |<span data-ttu-id="52207-128">ja</span><span class="sxs-lookup"><span data-stu-id="52207-128">yes</span></span>         |<span data-ttu-id="52207-129">ja</span><span class="sxs-lookup"><span data-stu-id="52207-129">yes</span></span>         |
|<span data-ttu-id="52207-130">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="52207-130">OneDrive for Business</span></span>     |<span data-ttu-id="52207-131">Elemente</span><span class="sxs-lookup"><span data-stu-id="52207-131">items</span></span>         |<span data-ttu-id="52207-132">ja</span><span class="sxs-lookup"><span data-stu-id="52207-132">yes</span></span>         |<span data-ttu-id="52207-133">ja</span><span class="sxs-lookup"><span data-stu-id="52207-133">yes</span></span>         |
|<span data-ttu-id="52207-134">Teams</span><span class="sxs-lookup"><span data-stu-id="52207-134">Teams</span></span>     |<span data-ttu-id="52207-135">Microsoft Teams- und Kanalnachrichten</span><span class="sxs-lookup"><span data-stu-id="52207-135">Teams and channel messages</span></span>         |<span data-ttu-id="52207-136">nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="52207-136">not applicable</span></span>         |<span data-ttu-id="52207-137">nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="52207-137">not applicable</span></span>         |
|<span data-ttu-id="52207-138">Teams</span><span class="sxs-lookup"><span data-stu-id="52207-138">Teams</span></span>     |<span data-ttu-id="52207-139">Anlagen</span><span class="sxs-lookup"><span data-stu-id="52207-139">attachments</span></span>         |<span data-ttu-id="52207-140">ja \*\*</span><span class="sxs-lookup"><span data-stu-id="52207-140">yes \*\*</span></span>         |<span data-ttu-id="52207-141">ja \*\*</span><span class="sxs-lookup"><span data-stu-id="52207-141">yes \*\*</span></span>         |
|<span data-ttu-id="52207-142">Windows 10-Geräte (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="52207-142">Windows 10 devices (preview)</span></span>     |<span data-ttu-id="52207-143">Elemente</span><span class="sxs-lookup"><span data-stu-id="52207-143">items</span></span>         |<span data-ttu-id="52207-144">ja</span><span class="sxs-lookup"><span data-stu-id="52207-144">yes</span></span>         |<span data-ttu-id="52207-145">ja</span><span class="sxs-lookup"><span data-stu-id="52207-145">yes</span></span>         |
|<span data-ttu-id="52207-146">MCAS (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="52207-146">MCAS (preview)</span></span> |<span data-ttu-id="52207-147">Elemente</span><span class="sxs-lookup"><span data-stu-id="52207-147">items</span></span>         |<span data-ttu-id="52207-148">ja</span><span class="sxs-lookup"><span data-stu-id="52207-148">yes</span></span>         |<span data-ttu-id="52207-149">ja</span><span class="sxs-lookup"><span data-stu-id="52207-149">yes</span></span>         |

<span data-ttu-id="52207-150">\* DLP-Erkennung von Vertraulichkeitsbezeichnungen in E-Mails wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="52207-150">\* DLP detection of sensitivity labels on emails are supported.</span></span> <span data-ttu-id="52207-151">DLP-Erkennung von Vertraulichkeitsbezeichnungen in E-Mails wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="52207-151">DLP detection of sensitivity labeled email attachments are not.</span></span>

<span data-ttu-id="52207-152">\*\* Anlagen, die in Teams über einen 1:1-Chat oder über Kanäle gesendet werden, werden automatisch auf OneDrive for Business und Microsoft Office SharePoint Online hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="52207-152">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to OneDrive for Business and SharePoint.</span></span> <span data-ttu-id="52207-153">Wenn also Microsoft Office SharePoint Online oder OneDrive for Business als Speicherorte in ihrer DLP-Richtlinie enthalten sind, werden bezeichnete Anlagen, die in Teams gesendet wurden, automatisch in den Umfang dieser Bedingung einbezogen.</span><span class="sxs-lookup"><span data-stu-id="52207-153">So if SharePoint Online or OneDrive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="52207-154">Teams muss in der DLP-Richtlinie nicht als Speicherort ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="52207-154">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="52207-155">Unterstützte Szenarien</span><span class="sxs-lookup"><span data-stu-id="52207-155">Supported scenarios</span></span>

- <span data-ttu-id="52207-156">Der DLP-Administrator kann eine Liste aller Vertraulichkeitsbezeichnugen im Mandanten anzeigen, wenn er eine oder mehrere Vertraulichkeitsbezeichnungen als Bedingung einschließt.</span><span class="sxs-lookup"><span data-stu-id="52207-156">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>
- <span data-ttu-id="52207-157">Die Verwendung von Vertraulichkeitsbezeichnungen als Bedingung wird in allen Workloads unterstützt, wie in der obigen Supportmatrix angegeben.</span><span class="sxs-lookup"><span data-stu-id="52207-157">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above</span></span>
- <span data-ttu-id="52207-158">DLP-Richtlinientipps werden weiterhin für Workloads (mit Ausnahme von Outlook Win32) angezeigt, die eine Vertraulichkeitsbezeichnung als Bedingung enthalten.</span><span class="sxs-lookup"><span data-stu-id="52207-158">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>
- <span data-ttu-id="52207-159">Vertraulichkeitsbezeichnungen werden auch als Bestandteil der Schadensbericht-E-Mail angezeigt, wenn eine DLP-Richtlinie mit einer Vertraulichkeitsbezeichnung als Bedingung übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="52207-159">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>
- <span data-ttu-id="52207-160">Details zur Vertraulichkeitsbezeichnung werden auch im Überwachungsprotokoll „DLP-Regelabgleich“ für eine Übereinstimmung mit einer DLP-Richtlinie angezeigt, die die Vertraulichkeitsbezeichnung als Bedingung enthält.</span><span class="sxs-lookup"><span data-stu-id="52207-160">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="52207-161">Support-Richtlinientipps</span><span class="sxs-lookup"><span data-stu-id="52207-161">Support policy tips</span></span>


|<span data-ttu-id="52207-162">Workload</span><span class="sxs-lookup"><span data-stu-id="52207-162">workload</span></span>  |<span data-ttu-id="52207-163">unterstützte/nicht unterstützte Richtlinientipps</span><span class="sxs-lookup"><span data-stu-id="52207-163">policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="52207-164">OWA</span><span class="sxs-lookup"><span data-stu-id="52207-164">OWA</span></span> |    <span data-ttu-id="52207-165">unterstützt</span><span class="sxs-lookup"><span data-stu-id="52207-165">supported</span></span>     |
|<span data-ttu-id="52207-166">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="52207-166">Outlook Win 32</span></span>    |  <span data-ttu-id="52207-167">nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="52207-167">not supported</span></span>       |
|<span data-ttu-id="52207-168">Microsoft Office SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="52207-168">SharePoint</span></span>   |   <span data-ttu-id="52207-169">unterstützt</span><span class="sxs-lookup"><span data-stu-id="52207-169">supported</span></span>      |
|<span data-ttu-id="52207-170">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="52207-170">OneDrive for Business</span></span>    |    <span data-ttu-id="52207-171">unterstützt</span><span class="sxs-lookup"><span data-stu-id="52207-171">supported</span></span>     |
|<span data-ttu-id="52207-172">Endpunktgeräte</span><span class="sxs-lookup"><span data-stu-id="52207-172">endpoint devices</span></span>   |  <span data-ttu-id="52207-173">nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="52207-173">not supported</span></span>       |
