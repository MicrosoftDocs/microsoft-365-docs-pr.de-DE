---
title: Funktionsweise von Vertraulichkeitsbezeichnungen in Office-Apps
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Mit Vertraulichkeitsbezeichnungen können Sie Ihre vertraulichen Inhalte klassifizieren und schützen, ohne dass die Produktivität Ihrer Mitarbeiter und deren Fähigkeit zur Zusammenarbeit behindert wird. Mithilfe von Vertraulichkeitsbezeichnungen können Sie Schutzeinstellungen wie Verschlüsselung oder Wasserzeichen für bezeichnete Inhalte erzwingen.
ms.openlocfilehash: f702423f0b1074b5619ef1c321cc5e9f1daef1d7
ms.sourcegitcommit: 15173ab87325b7d79bab683702b35d77a355cd6b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2019
ms.locfileid: "37417564"
---
# <a name="how-sensitivity-labels-work-in-office-apps"></a><span data-ttu-id="be4c7-104">Funktionsweise von Vertraulichkeitsbezeichnungen in Office-Apps</span><span class="sxs-lookup"><span data-stu-id="be4c7-104">How sensitivity labels work in Office apps</span></span>

## <a name="what-prerequisites-are-there-to-use-sensitivity-labels-in-office-applications"></a><span data-ttu-id="be4c7-105">Welche Voraussetzungen gelten für die Verwendung von Vertraulichkeitsbezeichnungen in Office-Anwendungen?</span><span class="sxs-lookup"><span data-stu-id="be4c7-105">What prerequisites are there to use sensitivity labels in Office applications?</span></span>

### <a name="common-requirements"></a><span data-ttu-id="be4c7-106">Allgemeine Anforderungen</span><span class="sxs-lookup"><span data-stu-id="be4c7-106">Common requirements</span></span> 

- <span data-ttu-id="be4c7-107">Einheitliche Vertraulichkeitsbezeichnungen müssen [im Security & Compliance Center konfiguriert und veröffentlicht werden](https://aka.ms/managemip).</span><span class="sxs-lookup"><span data-stu-id="be4c7-107">Unified sensitivity labels must be [configured and published in the Security and Compliance Center](https://aka.ms/managemip)</span></span>
- <span data-ttu-id="be4c7-108">Benutzer müssen bei Office mit Ihrem Geschäftskonto angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="be4c7-108">Users must be signed in to Office with their work account.</span></span>
- <span data-ttu-id="be4c7-109">Benutzer müssen über eine Lizenz für Office 365 E3 oder höher verfügen.</span><span class="sxs-lookup"><span data-stu-id="be4c7-109">Users must have an Office 365 E3 or above license assigned.</span></span>

### <a name="additional-requirements-for-office-for-windows"></a><span data-ttu-id="be4c7-110">Zusätzliche Anforderungen für Office für Windows</span><span class="sxs-lookup"><span data-stu-id="be4c7-110">Additional requirements for Office for Windows</span></span> 

- <span data-ttu-id="be4c7-111">Der Azure Information Protection-Client darf nicht in Office ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="be4c7-111">The Azure Information Protection client must not be running in Office.</span></span> <span data-ttu-id="be4c7-112">Siehe auch: [Können Vertraulichkeitsbezeichnungen neben dem Azure Information Protection-Client in Office für Windows ausgeführt werden?](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows)</span><span class="sxs-lookup"><span data-stu-id="be4c7-112">See also: [Can sensitivity labels run alongside the Azure Information Protection client in Office for Windows?](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows).</span></span>

### <a name="additional-requirements-for-outlook-on-all-platforms"></a><span data-ttu-id="be4c7-113">Zusätzliche Voraussetzungen für Outlook auf allen Plattformen</span><span class="sxs-lookup"><span data-stu-id="be4c7-113">Additional requirements for Outlook on all platforms</span></span> 

- <span data-ttu-id="be4c7-114">Wenn Sie in Ihrer Bezeichnungskonfiguration die Inhaltskennzeichnung aktivieren, müssen Sie Exchange Online verwenden, damit diese Inhaltskennzeichnung während der Übertragung eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="be4c7-114">In your label configuration, if you turn on content marking, you must be using Exchange Online for that content marking to be inserted in transit.</span></span>

## <a name="what-sensitivity-label-capabilities-are-supported-in-office-today"></a><span data-ttu-id="be4c7-115">Welche Funktionen im Zusammenhang mit Vertraulichkeitsbezeichnungen werden in Office heute unterstützt?</span><span class="sxs-lookup"><span data-stu-id="be4c7-115">What sensitivity label capabilities are supported in Office today?</span></span> 

<table border="1" cellspacing="0" cellpadding="0">
<th><span data-ttu-id="be4c7-116"><font size="-1">Funktion</span><span class="sxs-lookup"><span data-stu-id="be4c7-116"><font size="-1">Capability</span></span><th><span data-ttu-id="be4c7-117"><font size="-1">Windows</span><span class="sxs-lookup"><span data-stu-id="be4c7-117"><font size="-1">Windows</span></span><th><span data-ttu-id="be4c7-118"><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Web</span><span class="sxs-lookup"><span data-stu-id="be4c7-118"><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Web</span></span></tr>
<tr><td>

<td><span data-ttu-id="be4c7-119"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="be4c7-119"><font size="-1"> Word</span></span><br>
<span data-ttu-id="be4c7-120">Excel</span><span class="sxs-lookup"><span data-stu-id="be4c7-120">Excel</span></span><br>
<span data-ttu-id="be4c7-121">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="be4c7-121">PowerPoint</span></span><br>
<span data-ttu-id="be4c7-122">Outlook</span><span class="sxs-lookup"><span data-stu-id="be4c7-122">Outlook</span></span>


<td><span data-ttu-id="be4c7-123"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="be4c7-123"><font size="-1"> Word</span></span><br>
<span data-ttu-id="be4c7-124">Excel</span><span class="sxs-lookup"><span data-stu-id="be4c7-124">Excel</span></span><br>
<span data-ttu-id="be4c7-125">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="be4c7-125">PowerPoint</span></span><br>
<span data-ttu-id="be4c7-126">Outlook</span><span class="sxs-lookup"><span data-stu-id="be4c7-126">Outlook</span></span>

<td><span data-ttu-id="be4c7-127"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="be4c7-127"><font size="-1"> Word</span></span><br>
<span data-ttu-id="be4c7-128">Excel</span><span class="sxs-lookup"><span data-stu-id="be4c7-128">Excel</span></span><br>
<span data-ttu-id="be4c7-129">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="be4c7-129">PowerPoint</span></span>
<td><span data-ttu-id="be4c7-130"><font size="-1"> Outlook</span><span class="sxs-lookup"><span data-stu-id="be4c7-130"><font size="-1"> Outlook</span></span>

<td><span data-ttu-id="be4c7-131"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="be4c7-131"><font size="-1"> Word</span></span><br>
<span data-ttu-id="be4c7-132">Excel</span><span class="sxs-lookup"><span data-stu-id="be4c7-132">Excel</span></span><br>
<span data-ttu-id="be4c7-133">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="be4c7-133">PowerPoint</span></span>
<td><span data-ttu-id="be4c7-134"><font size="-1"> Outlook</span><span class="sxs-lookup"><span data-stu-id="be4c7-134"><font size="-1"> Outlook</span></span>

<td><span data-ttu-id="be4c7-135"><font size="-1"> Word</span><span class="sxs-lookup"><span data-stu-id="be4c7-135"><font size="-1"> Word</span></span><br>
<span data-ttu-id="be4c7-136">Excel</span><span class="sxs-lookup"><span data-stu-id="be4c7-136">Excel</span></span><br>
<span data-ttu-id="be4c7-137">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="be4c7-137">PowerPoint</span></span>
<td><span data-ttu-id="be4c7-138"><font size="-1"> Outlook </b>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-138"><font size="-1"> Outlook </b>
</span></span></tr>

<tr>
<td><span data-ttu-id="be4c7-139"><font size="-1">Manuelles Anwenden, Ändern oder Entfernen einer Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="be4c7-139"><font size="-1">Manually apply, change, or remove label</span></span><td><span data-ttu-id="be4c7-140"><font size="-1"><b>Ja</b></span><span class="sxs-lookup"><span data-stu-id="be4c7-140"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="be4c7-141"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="be4c7-141"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="be4c7-142"><font size="-1"><b>Ja</b></span><span class="sxs-lookup"><span data-stu-id="be4c7-142"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="be4c7-143"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="be4c7-143"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="be4c7-144"><font size="-1"><b>Ja</b></span><span class="sxs-lookup"><span data-stu-id="be4c7-144"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="be4c7-145"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-145"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="be4c7-146"><font size="-1">Bald verfügbar<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-146"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="be4c7-147"><font size="-1"><b>Ja</b></span><span class="sxs-lookup"><span data-stu-id="be4c7-147"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="be4c7-148"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-148"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="be4c7-149"><font size="-1">Bald verfügbar<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-149"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="be4c7-150"><font size="-1">Bald verfügbar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="be4c7-150"><font size="-1">Coming soon<sup>3</sup></span></span><td><span data-ttu-id="be4c7-151"><font size="-1">Bald verfügbar<sup>3</sup>


</span><span class="sxs-lookup"><span data-stu-id="be4c7-151"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr>
<td><span data-ttu-id="be4c7-152"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Standardbezeichnung anwenden</a>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-152"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Apply a default label</a>
</span></span><td><span data-ttu-id="be4c7-153"><font size="-1"><b>Ja</b></span><span class="sxs-lookup"><span data-stu-id="be4c7-153"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="be4c7-154"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="be4c7-154"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="be4c7-155"><font size="-1"><b>Ja</b></span><span class="sxs-lookup"><span data-stu-id="be4c7-155"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="be4c7-156"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="be4c7-156"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="be4c7-157"><font size="-1"><b>Ja</b></span><span class="sxs-lookup"><span data-stu-id="be4c7-157"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="be4c7-158"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-158"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="be4c7-159"><font size="-1">Bald verfügbar<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-159"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="be4c7-160"><font size="-1"><b>Ja</b></span><span class="sxs-lookup"><span data-stu-id="be4c7-160"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="be4c7-161"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-161"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="be4c7-162"><font size="-1">Bald verfügbar<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-162"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="be4c7-163"><font size="-1">Bald verfügbar<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-163"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="be4c7-164"><font size="-1">Bald verfügbar<sup>3</sup>


</span><span class="sxs-lookup"><span data-stu-id="be4c7-164"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="be4c7-165"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Begründung für das Ändern einer Bezeichnung anfordern</a><sup>1</sup>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-165"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Require a justification for changing a label</a><sup>1</sup>
</span></span><td><span data-ttu-id="be4c7-166"><font size="-1"><b>Ja</b></span><span class="sxs-lookup"><span data-stu-id="be4c7-166"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="be4c7-167"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="be4c7-167"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="be4c7-168"><font size="-1"><b>Ja</b></span><span class="sxs-lookup"><span data-stu-id="be4c7-168"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="be4c7-169"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="be4c7-169"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="be4c7-170"><font size="-1"><b>Ja</b></span><span class="sxs-lookup"><span data-stu-id="be4c7-170"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="be4c7-171"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-171"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="be4c7-172"><font size="-1">Bald verfügbar<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-172"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="be4c7-173"><font size="-1"><b>Ja</b></span><span class="sxs-lookup"><span data-stu-id="be4c7-173"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="be4c7-174"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-174"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="be4c7-175"><font size="-1">Bald verfügbar<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-175"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="be4c7-176"><font size="-1">Bald verfügbar<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-176"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="be4c7-177"><font size="-1">Bald verfügbar<sup>3</sup>


</span><span class="sxs-lookup"><span data-stu-id="be4c7-177"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="be4c7-178"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Hilfelinks zu einer benutzerdefinierten Hilfeseite bereitstellen</a>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-178"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Provide help link to a custom help page</a>
</span></span><td><span data-ttu-id="be4c7-179"><font size="-1"><b>Ja</b></span><span class="sxs-lookup"><span data-stu-id="be4c7-179"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="be4c7-180"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="be4c7-180"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="be4c7-181"><font size="-1"><b>Ja</b></span><span class="sxs-lookup"><span data-stu-id="be4c7-181"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="be4c7-182"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="be4c7-182"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="be4c7-183"><font size="-1"><b>Ja</b></span><span class="sxs-lookup"><span data-stu-id="be4c7-183"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="be4c7-184"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-184"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="be4c7-185"><font size="-1">Bald verfügbar<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-185"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="be4c7-186"><font size="-1"><b>Ja</b></span><span class="sxs-lookup"><span data-stu-id="be4c7-186"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="be4c7-187"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-187"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="be4c7-188"><font size="-1">Bald verfügbar<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-188"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="be4c7-189"><font size="-1">Bald verfügbar<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-189"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="be4c7-190"><font size="-1">Bald verfügbar<sup>3</sup>


</span><span class="sxs-lookup"><span data-stu-id="be4c7-190"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="be4c7-191"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">Inhalt markieren</a>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-191"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">Mark the content</a>
</span></span><td><span data-ttu-id="be4c7-192"><font size="-1"><b>Ja</b></span><span class="sxs-lookup"><span data-stu-id="be4c7-192"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="be4c7-193"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="be4c7-193"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="be4c7-194"><font size="-1"><b>Ja</b></span><span class="sxs-lookup"><span data-stu-id="be4c7-194"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="be4c7-195"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="be4c7-195"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="be4c7-196"><font size="-1"><b>Ja</b></span><span class="sxs-lookup"><span data-stu-id="be4c7-196"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="be4c7-197"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-197"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="be4c7-198"><font size="-1">Bald verfügbar<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-198"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="be4c7-199"><font size="-1"><b>Ja</b></span><span class="sxs-lookup"><span data-stu-id="be4c7-199"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="be4c7-200"><font size="-1">16.0.11231+</font
</span><span class="sxs-lookup"><span data-stu-id="be4c7-200"><font size="-1">16.0.11231+</font
</span></span>><td><span data-ttu-id="be4c7-201"><font size="-1">Bald verfügbar<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-201"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="be4c7-202"><font size="-1">Bald verfügbar<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-202"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="be4c7-203"><font size="-1">Bald verfügbar<sup>3</sup>


</span><span class="sxs-lookup"><span data-stu-id="be4c7-203"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="be4c7-204"><font size="-1">
  <a href="https://docs.microsoft.com/en-us/microsoft-365/compliance/encryption-sensitivity-labels#assign-permissions-now">Zuweisen vordefinierter Berechtigungen</a>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-204"><font size="-1">Assign pre-defined permissions</span></span><td><span data-ttu-id="be4c7-205"><font size="-1"><b>Ja</b></span><span class="sxs-lookup"><span data-stu-id="be4c7-205"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="be4c7-206"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="be4c7-206"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="be4c7-207"><font size="-1"><b>Ja</b></span><span class="sxs-lookup"><span data-stu-id="be4c7-207"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="be4c7-208"><font size="-1">16.21.0+</font>

</span><span class="sxs-lookup"><span data-stu-id="be4c7-208"><font size="-1">16.21.0+</font>

</span></span><td><span data-ttu-id="be4c7-209"><font size="-1"><b>Ja</b></span><span class="sxs-lookup"><span data-stu-id="be4c7-209"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="be4c7-210"><font size="-1">2.21+</font>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-210"><font size="-1">2.21+</font>
</span></span><td><span data-ttu-id="be4c7-211"><font size="-1">Bald verfügbar<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-211"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="be4c7-212"><font size="-1"><b>Ja</b></span><span class="sxs-lookup"><span data-stu-id="be4c7-212"><font size="-1"><b>Yes</b></span></span><br><span data-ttu-id="be4c7-213"><font size="-1">16.0.11231+</font>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-213"><font size="-1">16.0.11231+</font>
</span></span><td><span data-ttu-id="be4c7-214"><font size="-1">Bald verfügbar<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-214"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="be4c7-215"><font size="-1">Bald verfügbar<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-215"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="be4c7-216"><font size="-1">Bald verfügbar<sup>3</sup>


</span><span class="sxs-lookup"><span data-stu-id="be4c7-216"><font size="-1">Coming soon<sup>3</sup>

</span></span><tr><td><span data-ttu-id="be4c7-217"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions">Benutzern die Zuweisung von Berechtigungen überlassen</a>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-217"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions">Let users assign permissions</a>
</span></span><td><span data-ttu-id="be4c7-218"><font size="-1"><b>Ja</b><sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="be4c7-218"><font size="-1"><b>Yes</b><sup>2</sup></span></span><br><span data-ttu-id="be4c7-219"><font size="-1">1910+</font>

</span><span class="sxs-lookup"><span data-stu-id="be4c7-219"><font size="-1">1910+</font>

</span></span><td><span data-ttu-id="be4c7-220"><font size="-1"><b>Ja</b><sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="be4c7-220"><font size="-1"><b>Yes</b><sup>2</sup></span></span><br><span data-ttu-id="be4c7-221"><font size="-1">16.21.0+</font></span><span class="sxs-lookup"><span data-stu-id="be4c7-221"><font size="-1">16.21.0+</font></span></span>

<td><span data-ttu-id="be4c7-222"><font size="-1">Noch nicht festgelegt</span><span class="sxs-lookup"><span data-stu-id="be4c7-222"><font size="-1">TBD</span></span>
<td><span data-ttu-id="be4c7-223"><font size="-1">Bald verfügbar<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-223"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="be4c7-224"><font size="-1">Noch nicht festgelegt</span><span class="sxs-lookup"><span data-stu-id="be4c7-224"><font size="-1">TBD</span></span><td
><span data-ttu-id="be4c7-225"><font size="-1">Bald verfügbar<sup>3</sup>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-225"><font size="-1">Coming soon<sup>3</sup>
</span></span><td><span data-ttu-id="be4c7-226"><font size="-1">Noch nicht festgelegt</span><span class="sxs-lookup"><span data-stu-id="be4c7-226"><font size="-1">TBD</span></span>
<td><span data-ttu-id="be4c7-227"><font size="-1">Bald verfügbar<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="be4c7-227"><font size="-1">Coming soon<sup>3</sup></span></span>

<tr><td><span data-ttu-id="be4c7-228"><font size="-1">Daten der <a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">Bezeichnungsanalyse</a> an Administratoren senden</span><span class="sxs-lookup"><span data-stu-id="be4c7-228"><font size="-1">Send <a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">label analytics</a> data for administrators</span></span>
<td><span data-ttu-id="be4c7-229"><font size="-1">Noch nicht festgelegt</span><span class="sxs-lookup"><span data-stu-id="be4c7-229"><font size="-1">TBD</span></span>

<td><span data-ttu-id="be4c7-230"><font size="-1">Noch nicht festgelegt</span><span class="sxs-lookup"><span data-stu-id="be4c7-230"><font size="-1">TBD</span></span>

<td><span data-ttu-id="be4c7-231"><font size="-1">Noch nicht festgelegt</span><span class="sxs-lookup"><span data-stu-id="be4c7-231"><font size="-1">TBD</span></span>
<td><span data-ttu-id="be4c7-232"><font size="-1">Noch nicht festgelegt</span><span class="sxs-lookup"><span data-stu-id="be4c7-232"><font size="-1">TBD</span></span>
<td><span data-ttu-id="be4c7-233"><font size="-1">Noch nicht festgelegt</span><span class="sxs-lookup"><span data-stu-id="be4c7-233"><font size="-1">TBD</span></span>
<td><span data-ttu-id="be4c7-234"><font size="-1">Noch nicht festgelegt</span><span class="sxs-lookup"><span data-stu-id="be4c7-234"><font size="-1">TBD</span></span>
<td><span data-ttu-id="be4c7-235"><font size="-1">Noch nicht festgelegt</span><span class="sxs-lookup"><span data-stu-id="be4c7-235"><font size="-1">TBD</span></span>
<td><span data-ttu-id="be4c7-236"><font size="-1">Noch nicht festgelegt</span><span class="sxs-lookup"><span data-stu-id="be4c7-236"><font size="-1">TBD</span></span>

<tr><td><span data-ttu-id="be4c7-237"><font size="-1">
  <a href="https://docs.microsoft.com/en-us/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">Benutzer müssen eine Bezeichnung auf ihre E-Mails und Dokumente anwenden</a>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-237"><font size="-1">Require users to apply a label to their email and documents</span></span><td><span data-ttu-id="be4c7-238"><font size="-1">Noch nicht festgelegt</span><span class="sxs-lookup"><span data-stu-id="be4c7-238"><font size="-1">TBD</span></span>

<td><span data-ttu-id="be4c7-239"><font size="-1">Noch nicht festgelegt</span><span class="sxs-lookup"><span data-stu-id="be4c7-239"><font size="-1">TBD</span></span>

<td><span data-ttu-id="be4c7-240"><font size="-1">Noch nicht festgelegt</span><span class="sxs-lookup"><span data-stu-id="be4c7-240"><font size="-1">TBD</span></span>
<td><span data-ttu-id="be4c7-241"><font size="-1">Noch nicht festgelegt</span><span class="sxs-lookup"><span data-stu-id="be4c7-241"><font size="-1">TBD</span></span>
<td><span data-ttu-id="be4c7-242"><font size="-1">Noch nicht festgelegt</span><span class="sxs-lookup"><span data-stu-id="be4c7-242"><font size="-1">TBD</span></span>
<td><span data-ttu-id="be4c7-243"><font size="-1">Noch nicht festgelegt</span><span class="sxs-lookup"><span data-stu-id="be4c7-243"><font size="-1">TBD</span></span>
<td><span data-ttu-id="be4c7-244"><font size="-1">Noch nicht festgelegt</span><span class="sxs-lookup"><span data-stu-id="be4c7-244"><font size="-1">TBD</span></span>
<td><span data-ttu-id="be4c7-245"><font size="-1">Noch nicht festgelegt</span><span class="sxs-lookup"><span data-stu-id="be4c7-245"><font size="-1">TBD</span></span>

<tr><td><span data-ttu-id="be4c7-246"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically">Vertraulichkeitsbezeichnung automatisch auf Inhalte anwenden</a>
</span><span class="sxs-lookup"><span data-stu-id="be4c7-246"><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically">Apply a sensitivity label to content automatically</a>
</span></span><td><span data-ttu-id="be4c7-247"><font size="-1">Noch nicht festgelegt</span><span class="sxs-lookup"><span data-stu-id="be4c7-247"><font size="-1">TBD</span></span>

<td><span data-ttu-id="be4c7-248"><font size="-1">Noch nicht festgelegt</span><span class="sxs-lookup"><span data-stu-id="be4c7-248"><font size="-1">TBD</span></span>

<td><span data-ttu-id="be4c7-249"><font size="-1">Noch nicht festgelegt</span><span class="sxs-lookup"><span data-stu-id="be4c7-249"><font size="-1">TBD</span></span>
<td><span data-ttu-id="be4c7-250"><font size="-1">Noch nicht festgelegt</span><span class="sxs-lookup"><span data-stu-id="be4c7-250"><font size="-1">TBD</span></span>
<td><span data-ttu-id="be4c7-251"><font size="-1">Noch nicht festgelegt</span><span class="sxs-lookup"><span data-stu-id="be4c7-251"><font size="-1">TBD</span></span>
<td><span data-ttu-id="be4c7-252"><font size="-1">Noch nicht festgelegt</span><span class="sxs-lookup"><span data-stu-id="be4c7-252"><font size="-1">TBD</span></span>
<td><span data-ttu-id="be4c7-253"><font size="-1">Noch nicht festgelegt</span><span class="sxs-lookup"><span data-stu-id="be4c7-253"><font size="-1">TBD</span></span>
<td><span data-ttu-id="be4c7-254"><font size="-1">Noch nicht festgelegt</span><span class="sxs-lookup"><span data-stu-id="be4c7-254"><font size="-1">TBD</span></span>
</table>

<br><span data-ttu-id="be4c7-255"><sup>1</sup>Wenn konfiguriert, werden die Benutzer aufgefordert, Herabstufungen von Bezeichnungen zu begründen.</span><span class="sxs-lookup"><span data-stu-id="be4c7-255"><sup>1</sup>If configured, users are prompted to justify label downgrades.</span></span> <span data-ttu-id="be4c7-256">Allerdings werden die Begründungsdaten Administratoren noch nicht zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="be4c7-256">However, the justification data is not made available for administrators yet.</span></span> <span data-ttu-id="be4c7-257">Sie werden verfügbar, wenn die Funktion "Daten der Bezeichnungsanalyse an Administratoren senden" unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="be4c7-257">It will become available when the “send label analytics data for administrators” capability is supported.</span></span>
<br><span data-ttu-id="be4c7-258"><sup>2</sup>"Benutzern die Zuweisung von Berechtigungen überlassen" ist derzeit nur in Outlook für Windows und Mac verfügbar.</span><span class="sxs-lookup"><span data-stu-id="be4c7-258"><sup>2</sup>Let users assign permissions is currently only available in Outlook for Windows and Mac.</span></span> <span data-ttu-id="be4c7-259">Verfügbarkeit für Word, Excel und PowerPoint ist noch nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="be4c7-259">Availability for Word, Excel, and PowerPoint is TBD.</span></span>
<br><span data-ttu-id="be4c7-260"><sup>3</sup>Voraussichtlich Q4 des Kalenderjahrs 2019.</span><span class="sxs-lookup"><span data-stu-id="be4c7-260"><sup>3</sup>Expected Q4 of calendar year 2019.</span></span>

## <a name="when-do-content-marks-or-encryption-get-applied-after-content-is-given-a-sensitivity-label"></a><span data-ttu-id="be4c7-261">Wann werden Inhaltskennzeichen oder Verschlüsselung angewendet, nachdem der Inhalt eine Vertraulichkeitsbezeichnung erhalten hat?</span><span class="sxs-lookup"><span data-stu-id="be4c7-261">When do content marks or encryption get applied after content is given a sensitivity label?</span></span>

| <span data-ttu-id="be4c7-262">Anwendung</span><span class="sxs-lookup"><span data-stu-id="be4c7-262">Application</span></span> | <span data-ttu-id="be4c7-263">Inhaltskennzeichnung</span><span class="sxs-lookup"><span data-stu-id="be4c7-263">Content marking</span></span> | <span data-ttu-id="be4c7-264">Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="be4c7-264">Encryption</span></span>
| --- | --- | --- |
| <span data-ttu-id="be4c7-265">Word, Excel, PowerPoint auf allen Plattformen</span><span class="sxs-lookup"><span data-stu-id="be4c7-265">Word, Excel, PowerPoint on all platforms</span></span> | <span data-ttu-id="be4c7-266">Sofort</span><span class="sxs-lookup"><span data-stu-id="be4c7-266">Immediately</span></span> | <span data-ttu-id="be4c7-267">Sofort</span><span class="sxs-lookup"><span data-stu-id="be4c7-267">Immediately</span></span> |
| <span data-ttu-id="be4c7-268">Outlook für PC und Mac</span><span class="sxs-lookup"><span data-stu-id="be4c7-268">Outlook for PC and Mac</span></span> | <span data-ttu-id="be4c7-269">Nachdem E-Mails von Exchange Online gesendet werden</span><span class="sxs-lookup"><span data-stu-id="be4c7-269">After the email is sent by Exchange Online</span></span> | <span data-ttu-id="be4c7-270">Sofort</span><span class="sxs-lookup"><span data-stu-id="be4c7-270">Immediately</span></span> |
| <span data-ttu-id="be4c7-271">Outlook im Web, für iOS und Android</span><span class="sxs-lookup"><span data-stu-id="be4c7-271">Outlook on the web, iOS, and Android</span></span> | <span data-ttu-id="be4c7-272">Nachdem E-Mails von Exchange Online gesendet werden</span><span class="sxs-lookup"><span data-stu-id="be4c7-272">After the email is sent by Exchange Online</span></span> | <span data-ttu-id="be4c7-273">Nachdem E-Mails von Exchange Online gesendet werden</span><span class="sxs-lookup"><span data-stu-id="be4c7-273">After the email is sent by Exchange Online</span></span> |

## <a name="can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows"></a><span data-ttu-id="be4c7-274">Können Vertraulichkeitsbezeichnungen neben dem Azure Information Protection-Client in Office für Windows ausgeführt werden?</span><span class="sxs-lookup"><span data-stu-id="be4c7-274">Can sensitivity labels run alongside the Azure Information Protection client in Office for Windows?</span></span>

<span data-ttu-id="be4c7-275">Nein.</span><span class="sxs-lookup"><span data-stu-id="be4c7-275">No.</span></span> <span data-ttu-id="be4c7-276">Vertraulichkeitsbezeichnungen werden deaktiviert, wenn der Azure Information Protection-Client in Office für Windows geladen wird.</span><span class="sxs-lookup"><span data-stu-id="be4c7-276">Sensitivity labels are turned off if the Azure Information Protection client is loaded in Office for Windows.</span></span>

<span data-ttu-id="be4c7-277">Wenn Sie den Azure Information Protection-Client installiert haben, aber stattdessen Vertraulichkeitsbezeichnungen verwenden möchten, haben Sie folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="be4c7-277">If you have the Azure Information Protection client installed, but you want to use sensitivity labels instead, you can:</span></span>

1. <span data-ttu-id="be4c7-278">Konfigurieren Sie das Gruppenrichtlinieneinstellung  **Vertraulichkeitsfeature in Office verwenden, um Vertraulichkeitsbezeichnungen anzuwenden und anzuzeigen** das unter **Benutzerkonfiguration/Administrative Vorlagen/Microsoft Office 2016/Sicherheitseinstellungen** zu finden ist.</span><span class="sxs-lookup"><span data-stu-id="be4c7-278">Configure the **Use the Sensitivity feature in Office to apply and view sensitivity labels** Group Policy setting, which can be found under **User Configuration/Administrative Templates/Microsoft Office 2016/Security Settings**.</span></span>

  ><span data-ttu-id="be4c7-279">Hinweis: Diese Einstellung kann über herkömmliche Bereitstellungsmechanismen für Gruppenrichtlinien oder über den [Office-Cloudrichtliniendienst](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service) bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="be4c7-279">Note: this setting can be deployed via traditional group policy deployment mechanisms, or by the [Office cloud policy service](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service).</span></span> 
 
  <span data-ttu-id="be4c7-280">Alternativ können Sie auch den Azure Information Protection-Client deinstallieren oder  [deaktivieren](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d).</span><span class="sxs-lookup"><span data-stu-id="be4c7-280">Alternatively, you can uninstall or [disable](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) the Azure Information Protection client.</span></span> 

2. <span data-ttu-id="be4c7-281">Starten Sie alle Office-Anwendungen neu.</span><span class="sxs-lookup"><span data-stu-id="be4c7-281">Restart all Office applications.</span></span>

## <a name="will-sensitivity-labels-be-supported-in-non-subscription-versions-of-office-like-office-2016-or-office-2019"></a><span data-ttu-id="be4c7-282">Werden Vertraulichkeitsbezeichnungen in Nicht-Abonnementversionen von Office wie Office 2016 oder Office 2019 unterstützt?</span><span class="sxs-lookup"><span data-stu-id="be4c7-282">Will sensitivity labels be supported in non-subscription versions of Office like Office 2016 or Office 2019?</span></span>

<span data-ttu-id="be4c7-283">Nein.</span><span class="sxs-lookup"><span data-stu-id="be4c7-283">No.</span></span> <span data-ttu-id="be4c7-284">Vertraulichkeitsbezeichnungen werden nur im Office 365-Abonnement und nicht in Nicht-Abonnementversionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="be4c7-284">Sensitivity labels will only be supported in the Office 365 subscription and will not be supported in any non-subscription version.</span></span> <span data-ttu-id="be4c7-285">Allerdings kann der Azure Information Protection-Client mit einheitlichen Bezeichnungen in Nicht-Abonnementversionen von Office verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="be4c7-285">However, the Azure Information Protection unified labeling client may be used in non-subscription versions of Office.</span></span> 

## <a name="i-previously-deployed-protection-templates-before-setting-up-sensitivity-labels-where-did-they-go"></a><span data-ttu-id="be4c7-286">Ich habe vor dem Einrichten von Vertraulichkeitsbezeichnungen Schutzvorlagen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="be4c7-286">I previously deployed protection templates before setting up sensitivity labels.</span></span> <span data-ttu-id="be4c7-287">Wo sind diese nun?</span><span class="sxs-lookup"><span data-stu-id="be4c7-287">Where did they go?</span></span>

<span data-ttu-id="be4c7-288">Die von Administratoren definierten [Schutzvorlagen](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) werden in der Office-Benutzeroberfläche ausgeblendet, wenn Vertraulichkeitsbezeichnungen aktiviert sind, da sie bei Verwendung von Vertraulichkeitsbezeichnungen mit aktivierter Verschlüsselung überflüssig sind.</span><span class="sxs-lookup"><span data-stu-id="be4c7-288">Administrator-defined [protection templates](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) are hidden from the Office user experience when sensitivity labels are enabled because they are redundant with sensitivity labels that have encryption enabled.</span></span> 

## <a name="can-a-file-or-email-have-more-than-one-classification"></a><span data-ttu-id="be4c7-289">Kann eine Datei oder eine E-Mail-Nachricht mehr als eine Klassifizierung aufweisen?</span><span class="sxs-lookup"><span data-stu-id="be4c7-289">Can a file or email have more than one classification?</span></span>

<span data-ttu-id="be4c7-290">Nein.</span><span class="sxs-lookup"><span data-stu-id="be4c7-290">No.</span></span> <span data-ttu-id="be4c7-291">Benutzer können für jedes Dokument oder jede E-Mail jeweils nur eine Bezeichnung auswählen.</span><span class="sxs-lookup"><span data-stu-id="be4c7-291">Users can select just one label at a time for each document or email, which often results in just one classification.</span></span>

## <a name="when-an-email-is-labeled-do-any-attachments-automatically-get-the-same-labeling"></a><span data-ttu-id="be4c7-292">Wenn eine E-Mail mit einer Bezeichnung versehen ist, erhalten Anlagen automatisch dieselbe Bezeichnung?</span><span class="sxs-lookup"><span data-stu-id="be4c7-292">When an email is labeled, do any attachments automatically get the same labeling?</span></span>

<span data-ttu-id="be4c7-293">Nein.</span><span class="sxs-lookup"><span data-stu-id="be4c7-293">No.</span></span> <span data-ttu-id="be4c7-294">Wenn Sie eine Bezeichnung auf eine E-Mail-Nachricht mit Anlagen anwenden, erben diese Anlagen nicht dieselbe Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="be4c7-294">When you label an email message that has attachments, those attachments do not inherit the same label.</span></span> <span data-ttu-id="be4c7-295">Die Anlagen bleiben entweder ohne Bezeichnung oder behalten die möglicherweise separat angewendete Bezeichnung bei.</span><span class="sxs-lookup"><span data-stu-id="be4c7-295">The attachments remain either without a label or retain a separately applied label.</span></span> <span data-ttu-id="be4c7-296">Wenn die Bezeichnung für die E-Mail-Adresse aber Schutz anwendet, wird dieser Schutz für Office-Anlagen übernommen.</span><span class="sxs-lookup"><span data-stu-id="be4c7-296">However, if the label for the email applies protection, that protection is applied to Office attachments.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="be4c7-297">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="be4c7-297">Additional resources</span></span>

[<span data-ttu-id="be4c7-298">Häufig gestellte Fragen zur Klassifizierung und zu Bezeichnungen in Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="be4c7-298">Frequently asked questions about classification and labeling in Azure Information Protection</span></span>](https://docs.microsoft.com/azure/information-protection/faqs-infoprotect)<br>
[<span data-ttu-id="be4c7-299">Anwenden von Vertraulichkeitsbezeichnungen auf Ihre Dokumente und E-Mails in Office</span><span class="sxs-lookup"><span data-stu-id="be4c7-299">Apply sensitivity labels to your documents and email within Office</span></span>](https://support.office.com/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
