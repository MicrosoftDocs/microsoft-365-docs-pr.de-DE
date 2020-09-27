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
ms.openlocfilehash: bb06ed6919a396bef1e5d1f1cb04731fa11267ae
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235717"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies-preview"></a><span data-ttu-id="62c44-103">Verwenden von Vertraulichkeitsbezeichnungen als Bedingungen in DLP-Richtlinien (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="62c44-103">Use sensitivity labels as conditions in DLP policies (preview)</span></span>

<span data-ttu-id="62c44-104">Sie können [Vertraulichkeitsbezeichnungen](sensitivity-labels.md) als Bedingung in DLP-Richtlinien für folgende Speicherorte verwenden:</span><span class="sxs-lookup"><span data-stu-id="62c44-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="62c44-105">Exchange Online-E-Mails</span><span class="sxs-lookup"><span data-stu-id="62c44-105">Exchange Online email messages</span></span>
- <span data-ttu-id="62c44-106">Microsoft Office SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="62c44-106">SharePoint Online</span></span>
- <span data-ttu-id="62c44-107">OneDrive for Business-Websites</span><span class="sxs-lookup"><span data-stu-id="62c44-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="62c44-108">Windows 10-Geräte</span><span class="sxs-lookup"><span data-stu-id="62c44-108">Windows 10 devices</span></span>

<span data-ttu-id="62c44-109">Vertraulichkeitsbezeichnungen werden als Option in der Liste **Inhalt enthält** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="62c44-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

![Vertraulichkeitsbezeichnungen als Bedingung](../media/dlp-sensitivity-label-as-a-condition.png)

## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="62c44-111">Unterstützte Elemente, Szenarien und Richtlinientipps</span><span class="sxs-lookup"><span data-stu-id="62c44-111">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="62c44-112">Sie können Vertraulichkeitsbezeichnungen als Bedingungen für diese Elemente und in diesen Szenarien verwenden.</span><span class="sxs-lookup"><span data-stu-id="62c44-112">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="62c44-113">unterstützte Elemente</span><span class="sxs-lookup"><span data-stu-id="62c44-113">Supported items</span></span>

|<span data-ttu-id="62c44-114">Dienst</span><span class="sxs-lookup"><span data-stu-id="62c44-114">service</span></span>  |<span data-ttu-id="62c44-115">Elementtyp</span><span class="sxs-lookup"><span data-stu-id="62c44-115">item type</span></span>  |<span data-ttu-id="62c44-116">verfügbar für Richtlinientipps</span><span class="sxs-lookup"><span data-stu-id="62c44-116">available to policy tip</span></span>  |<span data-ttu-id="62c44-117">durchsetzbar</span><span class="sxs-lookup"><span data-stu-id="62c44-117">enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="62c44-118">Exchange</span><span class="sxs-lookup"><span data-stu-id="62c44-118">Exchange</span></span>    |<span data-ttu-id="62c44-119">E-Mail-Nachricht</span><span class="sxs-lookup"><span data-stu-id="62c44-119">email message</span></span>         |<span data-ttu-id="62c44-120">ja</span><span class="sxs-lookup"><span data-stu-id="62c44-120">yes</span></span>         |<span data-ttu-id="62c44-121">ja</span><span class="sxs-lookup"><span data-stu-id="62c44-121">yes</span></span>         |
|<span data-ttu-id="62c44-122">Exchange</span><span class="sxs-lookup"><span data-stu-id="62c44-122">Exchange</span></span>    |<span data-ttu-id="62c44-123">E-Mail-Anlage</span><span class="sxs-lookup"><span data-stu-id="62c44-123">email attachment</span></span>         |<span data-ttu-id="62c44-124">nein \*</span><span class="sxs-lookup"><span data-stu-id="62c44-124">no \*</span></span>         |<span data-ttu-id="62c44-125">nein \*</span><span class="sxs-lookup"><span data-stu-id="62c44-125">no \*</span></span>         |
|<span data-ttu-id="62c44-126">Microsoft Office SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="62c44-126">SharePoint Online</span></span>     |<span data-ttu-id="62c44-127">Elemente in Microsoft Office SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="62c44-127">items in SharePoint Online</span></span>         |<span data-ttu-id="62c44-128">ja</span><span class="sxs-lookup"><span data-stu-id="62c44-128">yes</span></span>         |<span data-ttu-id="62c44-129">ja</span><span class="sxs-lookup"><span data-stu-id="62c44-129">yes</span></span>         |
|<span data-ttu-id="62c44-130">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="62c44-130">OneDrive for Business</span></span>     |<span data-ttu-id="62c44-131">Elemente</span><span class="sxs-lookup"><span data-stu-id="62c44-131">items</span></span>         |<span data-ttu-id="62c44-132">ja</span><span class="sxs-lookup"><span data-stu-id="62c44-132">yes</span></span>         |<span data-ttu-id="62c44-133">ja</span><span class="sxs-lookup"><span data-stu-id="62c44-133">yes</span></span>         |
|<span data-ttu-id="62c44-134">Teams</span><span class="sxs-lookup"><span data-stu-id="62c44-134">Teams</span></span>     |<span data-ttu-id="62c44-135">Microsoft Teams- und Kanalnachrichten</span><span class="sxs-lookup"><span data-stu-id="62c44-135">Teams and channel messages</span></span>         |<span data-ttu-id="62c44-136">nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="62c44-136">not applicable</span></span>         |<span data-ttu-id="62c44-137">nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="62c44-137">not applicable</span></span>         |
|<span data-ttu-id="62c44-138">Teams</span><span class="sxs-lookup"><span data-stu-id="62c44-138">Teams</span></span>     |<span data-ttu-id="62c44-139">Anlagen</span><span class="sxs-lookup"><span data-stu-id="62c44-139">attachements</span></span>         |<span data-ttu-id="62c44-140">ja \*\*</span><span class="sxs-lookup"><span data-stu-id="62c44-140">yes \*\*</span></span>         |<span data-ttu-id="62c44-141">ja \*\*</span><span class="sxs-lookup"><span data-stu-id="62c44-141">yes \*\*</span></span>         |
|<span data-ttu-id="62c44-142">Windows 10-Geräte (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="62c44-142">Windows 10 devices (preview)</span></span>     |<span data-ttu-id="62c44-143">Elemente</span><span class="sxs-lookup"><span data-stu-id="62c44-143">items</span></span>         |<span data-ttu-id="62c44-144">ja</span><span class="sxs-lookup"><span data-stu-id="62c44-144">yes</span></span>         |<span data-ttu-id="62c44-145">ja</span><span class="sxs-lookup"><span data-stu-id="62c44-145">yes</span></span>         |
|<span data-ttu-id="62c44-146">MCAS (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="62c44-146">MCAS (preview)</span></span> |<span data-ttu-id="62c44-147">Elemente</span><span class="sxs-lookup"><span data-stu-id="62c44-147">items</span></span>         |<span data-ttu-id="62c44-148">ja</span><span class="sxs-lookup"><span data-stu-id="62c44-148">yes</span></span>         |<span data-ttu-id="62c44-149">ja</span><span class="sxs-lookup"><span data-stu-id="62c44-149">yes</span></span>         |

<span data-ttu-id="62c44-150">\* DLP-Erkennung von Vertraulichkeitsbezeichnungen in E-Mails wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="62c44-150">\* DLP detection of sensitivity labels on emails are supported.</span></span> <span data-ttu-id="62c44-151">DLP-Erkennung von Vertraulichkeitsbezeichnungen in E-Mails wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="62c44-151">DLP detection of sensitivity labeled email attachments are not.</span></span>

<span data-ttu-id="62c44-152">\*\* Anlagen, die in Teams über Einzelchat oder Kanäle gesendet werden, werden automatisch auf OneDrive for Business und Microsoft Office SharePoint Online hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="62c44-152">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to One drive for business and SharePoint.</span></span> <span data-ttu-id="62c44-153">Wenn also Microsoft Office SharePoint Online oder OneDrive for Business als Speicherorte in ihrer DLP-Richtlinie enthalten ist, werden beschriftete Anlagen, die in Teams gesendet wurden, automatisch in den Umfang dieser Bedingung einbezogen.</span><span class="sxs-lookup"><span data-stu-id="62c44-153">So if SharePoint Online or One Drive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="62c44-154">Teams muss in der DLP-Richtlinie nicht als Speicherort ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="62c44-154">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="62c44-155">Unterstützte Szenarien</span><span class="sxs-lookup"><span data-stu-id="62c44-155">Supported scenarios</span></span>

- <span data-ttu-id="62c44-156">Der DLP-Administrator kann eine Liste aller Vertraulichkeitsbezeichnugen im Mandanten anzeigen, wenn er eine oder mehrere Vertraulichkeitsbezeichnungen als Bedingung einschließt.</span><span class="sxs-lookup"><span data-stu-id="62c44-156">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>
- <span data-ttu-id="62c44-157">Die Verwendung von Vertraulichkeitsbezeichnungen als Bedingung wird in allen Workloads unterstützt, wie in der obigen Supportmatrix angegeben.</span><span class="sxs-lookup"><span data-stu-id="62c44-157">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above</span></span>
- <span data-ttu-id="62c44-158">DLP-Richtlinientipps werden weiterhin für Workloads (mit Ausnahme von Outlook Win32) angezeigt, die eine Vertraulichkeitsbezeichnung als Bedingung enthalten.</span><span class="sxs-lookup"><span data-stu-id="62c44-158">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>
- <span data-ttu-id="62c44-159">Vertraulichkeitsbezeichnungen werden auch als Bestandteil der Schadensbericht-E-Mail angezeigt, wenn eine DLP-Richtlinie mit einer Vertraulichkeitsbezeichnung als Bedingung übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="62c44-159">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>
- <span data-ttu-id="62c44-160">Details zur Vertraulichkeitsbezeichnung werden auch im Überwachungsprotokoll „DLP-Regelabgleich“ für eine Übereinstimmung mit einer DLP-Richtlinie angezeigt, die die Vertraulichkeitsbezeichnung als Bedingung enthält.</span><span class="sxs-lookup"><span data-stu-id="62c44-160">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="62c44-161">Support-Richtlinientipps</span><span class="sxs-lookup"><span data-stu-id="62c44-161">Support policy tips</span></span>


|<span data-ttu-id="62c44-162">Workload</span><span class="sxs-lookup"><span data-stu-id="62c44-162">workload</span></span>  |<span data-ttu-id="62c44-163">unterstützte/nicht unterstützte Richtlinientipps</span><span class="sxs-lookup"><span data-stu-id="62c44-163">policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="62c44-164">OWA</span><span class="sxs-lookup"><span data-stu-id="62c44-164">OWA</span></span> |    <span data-ttu-id="62c44-165">unterstützt</span><span class="sxs-lookup"><span data-stu-id="62c44-165">supported</span></span>     |
|<span data-ttu-id="62c44-166">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="62c44-166">Outlook Win 32</span></span>    |  <span data-ttu-id="62c44-167">nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="62c44-167">not supported</span></span>       |
|<span data-ttu-id="62c44-168">Microsoft Office SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="62c44-168">SharePoint</span></span>   |   <span data-ttu-id="62c44-169">unterstützt</span><span class="sxs-lookup"><span data-stu-id="62c44-169">supported</span></span>      |
|<span data-ttu-id="62c44-170">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="62c44-170">OneDrive for Business</span></span>    |    <span data-ttu-id="62c44-171">unterstützt</span><span class="sxs-lookup"><span data-stu-id="62c44-171">supported</span></span>     |
|<span data-ttu-id="62c44-172">Endpunktgeräte</span><span class="sxs-lookup"><span data-stu-id="62c44-172">endpoint devices</span></span>   |  <span data-ttu-id="62c44-173">nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="62c44-173">not supported</span></span>       |
