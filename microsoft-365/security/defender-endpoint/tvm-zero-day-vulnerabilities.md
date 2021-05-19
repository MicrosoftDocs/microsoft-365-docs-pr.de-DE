---
title: Minimieren von Zero-Day-Sicherheitsrisiken – Bedrohungs- und Sicherheitsrisikomanagement
description: Erfahren Sie, wie Sie Zero-Day-Sicherheitsrisiken in Ihrer Umgebung mithilfe von Bedrohungs- und Sicherheitsrisikomanagement.
keywords: Microsoft Defender for Endpoint tvm zero day vulnerabilities, tvm, threat & Sicherheitsrisikomanagement, zero day, 0-day, mitigate 0 day vulnerabilities, vulnerable CVE
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2c746a74899a34827e089f4c9c2f6ecc396bb69c
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538771"
---
# <a name="mitigate-zero-day-vulnerabilities---threat-and-vulnerability-management"></a><span data-ttu-id="12849-104">Minimieren von Zero-Day-Sicherheitsrisiken – Bedrohungs- und Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="12849-104">Mitigate zero-day vulnerabilities - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="12849-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="12849-105">**Applies to:**</span></span>

- [<span data-ttu-id="12849-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="12849-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="12849-107">Bedrohung und Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="12849-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="12849-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="12849-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="12849-109">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="12849-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="12849-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="12849-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="12849-111">Eine Zero-Day-Sicherheitslücke ist eine öffentlich offengelegte Sicherheitslücke, für die keine offiziellen Patches oder Sicherheitsupdates veröffentlicht wurden.</span><span class="sxs-lookup"><span data-stu-id="12849-111">A zero-day vulnerability is a publicly disclosed vulnerability for which no official patches or security updates have been released.</span></span> <span data-ttu-id="12849-112">Zero-Day-Sicherheitsrisiken haben häufig einen hohen Schweregrad und werden aktiv ausgenutzt.</span><span class="sxs-lookup"><span data-stu-id="12849-112">Zero-day vulnerabilities often have high severity levels and are actively exploited.</span></span>

<span data-ttu-id="12849-113">Bedrohungen und Sicherheitsrisikomanagement zeigen nur Zero-Day-Sicherheitsrisiken an, über die informationen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="12849-113">Threat and vulnerability management will only display zero-day vulnerabilities it has information about.</span></span>

## <a name="find-information-about-zero-day-vulnerabilities"></a><span data-ttu-id="12849-114">Informationen zu Zero-Day-Sicherheitsrisiken finden</span><span class="sxs-lookup"><span data-stu-id="12849-114">Find information about zero-day vulnerabilities</span></span>

<span data-ttu-id="12849-115">Sobald eine Zero-Day-Sicherheitslücke gefunden wurde, werden Informationen dazu über die folgenden Erfahrungen in der Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="12849-115">Once a zero-day vulnerability has been found, information about it will be conveyed through the following experiences in the Microsoft Defender Security Center.</span></span>

>[!NOTE]
> <span data-ttu-id="12849-116">Die 0-Tage-Funktion ist derzeit nicht für nicht Windows (Mac, Linux) verfügbar. Sie wird jedoch in Zukunft hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="12849-116">0-day capability is not currently available for non-Windows products (Mac, Linux); it will, however, be added in the future.</span></span>

### <a name="threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="12849-117">Bedrohung und Sicherheitsrisikomanagement Dashboard</span><span class="sxs-lookup"><span data-stu-id="12849-117">Threat and vulnerability management dashboard</span></span>

<span data-ttu-id="12849-118">Suchen Sie auf der Karte "Top security recommendations" nach Empfehlungen mit einem Zero-Day-Tag.</span><span class="sxs-lookup"><span data-stu-id="12849-118">Look for recommendations with a zero-day tag in the “Top security recommendations” card.</span></span>

![Die besten Empfehlungen mit einem Zero-Day-Tag.](images/tvm-zero-day-top-security-recommendations.png)

<span data-ttu-id="12849-120">Suchen Sie auf der Karte "Besonders anfällige Software" nach Top-Software mit dem Tag "Zero-Day".</span><span class="sxs-lookup"><span data-stu-id="12849-120">Find top software with the zero-day tag in the "Top vulnerable software" card.</span></span>

![Besonders anfällige Software mit einem Zero-Day-Tag.](images/tvm-zero-day-top-software.png)

### <a name="weaknesses-page"></a><span data-ttu-id="12849-122">Seite "Schwächen"</span><span class="sxs-lookup"><span data-stu-id="12849-122">Weaknesses page</span></span>

<span data-ttu-id="12849-123">Suchen Sie nach der benannten Zero-Day-Sicherheitslücke zusammen mit einer Beschreibung und Details.</span><span class="sxs-lookup"><span data-stu-id="12849-123">Look for the named zero-day vulnerability along with a description and details.</span></span>

- <span data-ttu-id="12849-124">Wenn dieser Sicherheitsanfälligkeit eine CVE-ID zugewiesen ist, wird neben dem CVE-Namen die Zero-Day-Bezeichnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="12849-124">If this vulnerability has a CVE-ID assigned, you’ll see the zero-day label next to the CVE name.</span></span>

- <span data-ttu-id="12849-125">Wenn dieser Sicherheitsanfälligkeit keine CVE-ID zugewiesen ist, finden Sie sie unter einem internen, temporären Namen, der wie "TVM-XXXX-XXXX" aussieht.</span><span class="sxs-lookup"><span data-stu-id="12849-125">If this vulnerability has no CVE-ID assigned, you'll find it under an internal, temporary name that looks like “TVM-XXXX-XXXX”.</span></span> <span data-ttu-id="12849-126">Der Name wird aktualisiert, sobald eine offizielle CVE-ID zugewiesen wurde, aber der vorherige interne Name ist weiterhin durchsuchbar und wird im Seitenbereich gefunden.</span><span class="sxs-lookup"><span data-stu-id="12849-126">The name will be updated once an official CVE-ID has been assigned, but the previous internal name will still be searchable and found in the side-panel.</span></span>

![Zero day example for CVE-2020-17087 in weaknesses page.](images/tvm-zero-day-weakness-name.png)

### <a name="software-inventory-page"></a><span data-ttu-id="12849-128">Seite "Softwareinventar"</span><span class="sxs-lookup"><span data-stu-id="12849-128">Software inventory page</span></span>

<span data-ttu-id="12849-129">Suchen Sie nach Software mit dem Zero-Day-Tag.</span><span class="sxs-lookup"><span data-stu-id="12849-129">Look for software with the zero-day tag.</span></span> <span data-ttu-id="12849-130">Filtern Sie nach dem Tag "Zero Day", um nur Software mit Zero-Day-Sicherheitsrisiken zu sehen.</span><span class="sxs-lookup"><span data-stu-id="12849-130">Filter by the "zero day" tag to only see software with zero-day vulnerabilities.</span></span>

![Zero day example of Windows Server 2016 in the software inventory page.](images/tvm-zero-day-software-inventory.png)

### <a name="software-page"></a><span data-ttu-id="12849-132">Softwareseite</span><span class="sxs-lookup"><span data-stu-id="12849-132">Software page</span></span>

<span data-ttu-id="12849-133">Suchen Sie nach einem Zero-Day-Tag für jede Software, die von der Zero-Day-Sicherheitslücke betroffen ist.</span><span class="sxs-lookup"><span data-stu-id="12849-133">Look for a zero-day tag for each software that has been affected by the zero–day vulnerability.</span></span>

![Zero day example for Windows Server 2016 software page.](images/tvm-zero-day-software-page.png)

### <a name="security-recommendations-page"></a><span data-ttu-id="12849-135">Seite mit Sicherheitsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="12849-135">Security recommendations page</span></span>

<span data-ttu-id="12849-136">Zeigen Sie klare Vorschläge zu Korrektur- und Abhilfemaßnahmen an, einschließlich Problemumgehungen, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="12849-136">View clear suggestions about remediation and mitigation options, including workarounds if they exist.</span></span> <span data-ttu-id="12849-137">Filtern Sie nach dem Tag "Zero Day", um nur Sicherheitsempfehlungen zur Behandlung von Zero-Day-Sicherheitsrisiken zu sehen.</span><span class="sxs-lookup"><span data-stu-id="12849-137">Filter by the "zero day" tag to only see security recommendations addressing zero-day vulnerabilities.</span></span>

<span data-ttu-id="12849-138">Wenn Software mit einer Zero-Day-Sicherheitslücke und zusätzlichen Sicherheitsrisiken zur Verfügung steht, erhalten Sie eine Empfehlung zu allen Sicherheitsrisiken.</span><span class="sxs-lookup"><span data-stu-id="12849-138">If there's software with a zero-day vulnerability and additional vulnerabilities to address, you'll get one recommendation about all vulnerabilities.</span></span>

![Zero day example of Windows Server 2016 in the security recommendations page.](images/tvm-zero-day-security-recommendation.png)

## <a name="addressing-zero-day-vulnerabilities"></a><span data-ttu-id="12849-140">Behebung von Zero-Day-Sicherheitsrisiken</span><span class="sxs-lookup"><span data-stu-id="12849-140">Addressing zero-day vulnerabilities</span></span>

<span data-ttu-id="12849-141">Wechseln Sie zur Seite Sicherheitsempfehlung, und wählen Sie eine Empfehlung mit einem Nulltag aus.</span><span class="sxs-lookup"><span data-stu-id="12849-141">Go to the security recommendation page and select a recommendation with a zero-day.</span></span> <span data-ttu-id="12849-142">Ein Flyout wird mit Informationen zu den Zero-Day- und anderen Sicherheitsrisiken für diese Software geöffnet.</span><span class="sxs-lookup"><span data-stu-id="12849-142">A flyout will open with information about the zero-day and other vulnerabilities for that software.</span></span>

<span data-ttu-id="12849-143">Es gibt einen Link zu Abhilfemaßnahmen und Problemumgehungen, wenn diese verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="12849-143">There will be a link to mitigation options and workarounds if they are available.</span></span> <span data-ttu-id="12849-144">Problemumgehungen können dazu beitragen, das Risiko dieser Zero-Day-Sicherheitslücke zu verringern, bis ein Patch oder Sicherheitsupdate bereitgestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="12849-144">Workarounds may help reduce the risk posed by this zero-day vulnerability until a patch or security update can be deployed.</span></span>

<span data-ttu-id="12849-145">Öffnen Sie Korrekturoptionen, und wählen Sie den Aufmerksamkeitstyp aus.</span><span class="sxs-lookup"><span data-stu-id="12849-145">Open remediation options and choose the attention type.</span></span> <span data-ttu-id="12849-146">Für die Zero-Day-Sicherheitsrisiken wird eine Option zur Behebung von "Aufmerksamkeit erforderlich" empfohlen, da ein Update noch nicht veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="12849-146">An "attention required" remediation option is recommended for the zero-day vulnerabilities, since an update hasn't been released yet.</span></span> <span data-ttu-id="12849-147">Sie können kein Fälligkeitsdatum auswählen, da keine bestimmte Aktion durchzuführen ist.</span><span class="sxs-lookup"><span data-stu-id="12849-147">You won't be able to select a due date, since there's no specific action to perform.</span></span> <span data-ttu-id="12849-148">Wenn ältere Sicherheitsrisiken für diese Software vorhanden sind, die Sie bereinigungen möchten, können Sie die Option "Aufmerksamkeit erforderlich" außer Kraft setzen und "aktualisieren" auswählen.</span><span class="sxs-lookup"><span data-stu-id="12849-148">If there are older vulnerabilities for this software you wish to remediation, you can override the "attention required" remediation option and choose “update.”</span></span>

![Flyoutbeispiel für zero day Windows Server 2016 auf der Seite sicherheitsempfehlungen.](images/tvm-zero-day-recommendation-flyout400.png)

## <a name="track-zero-day-remediation-activities"></a><span data-ttu-id="12849-150">Nachverfolgen von Zero-Day-Korrekturaktivitäten</span><span class="sxs-lookup"><span data-stu-id="12849-150">Track zero-day remediation activities</span></span>

<span data-ttu-id="12849-151">Wechseln Sie zur seite [Bedrohungs- und Sicherheitsrisikomanagement,](tvm-remediation.md) um das Problembehebungsaktivitätselement zu sehen.</span><span class="sxs-lookup"><span data-stu-id="12849-151">Go to the threat and vulnerability management [Remediation](tvm-remediation.md) page to view the remediation activity item.</span></span> <span data-ttu-id="12849-152">Wenn Sie die Option "Aufmerksamkeit erforderlich" ausgewählt haben, gibt es keine Statusanzeige, keinen Ticketstatus oder kein Fälligkeitsdatum, da es keine tatsächliche Aktion gibt, die wir überwachen können.</span><span class="sxs-lookup"><span data-stu-id="12849-152">If you chose the "attention required" remediation option, there will be no progress bar, ticket status, or due date since there's no actual action we can monitor.</span></span> <span data-ttu-id="12849-153">Sie können nach Behebungstyp filtern, z. B. "Softwareupdate" oder "Aufmerksamkeit erforderlich", um alle Aktivitätselemente in derselben Kategorie zu sehen.</span><span class="sxs-lookup"><span data-stu-id="12849-153">You can filter by remediation type, such as "software update" or "attention required," to see all activity items in the same category.</span></span>

## <a name="patching-zero-day-vulnerabilities"></a><span data-ttu-id="12849-154">Patchen von Zero-Day-Sicherheitsrisiken</span><span class="sxs-lookup"><span data-stu-id="12849-154">Patching zero-day vulnerabilities</span></span>

<span data-ttu-id="12849-155">Wenn ein Patch für den Nulltag freigegeben wird, wird die Empfehlung in "Update" und eine blaue Beschriftung daneben mit der Bezeichnung "Neues Sicherheitsupdate für null Tag" geändert.</span><span class="sxs-lookup"><span data-stu-id="12849-155">When a patch is released for the zero-day, the recommendation will be changed to “Update” and a blue label next to it that says “New security update for zero day.”</span></span> <span data-ttu-id="12849-156">Es wird nicht mehr als Zero-Day-Tag in Betracht ziehen, das Zero-Day-Tag wird von allen Seiten entfernt.</span><span class="sxs-lookup"><span data-stu-id="12849-156">It will no longer consider as a zero-day, the zero-day tag will be removed from all pages.</span></span>

![Empfehlung für "Update Microsoft Windows 10" mit neuer Patchbeschriftung.](images/tvm-zero-day-patch.jpg)

## <a name="related-articles"></a><span data-ttu-id="12849-158">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="12849-158">Related articles</span></span>

- [<span data-ttu-id="12849-159">Übersicht über Bedrohungen Sicherheitsrisikomanagement Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="12849-159">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="12849-160">Dashboard</span><span class="sxs-lookup"><span data-stu-id="12849-160">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="12849-161">Sicherheitsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="12849-161">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="12849-162">Softwarebestand</span><span class="sxs-lookup"><span data-stu-id="12849-162">Software inventory</span></span>](tvm-software-inventory.md)
- [<span data-ttu-id="12849-163">Sicherheitsrisiken in meiner Organisation</span><span class="sxs-lookup"><span data-stu-id="12849-163">Vulnerabilities in my organization</span></span>](tvm-weaknesses.md)
