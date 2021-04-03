---
title: Minimieren von Zero-Day-Sicherheitsrisiken – Bedrohungs- und Sicherheitsrisikoverwaltung
description: Erfahren Sie, wie Sie Zero-Day-Sicherheitsrisiken in Ihrer Umgebung durch das Bedrohungs- und Sicherheitsrisikomanagement finden und mindern können.
keywords: mdatp tvm zero day vulnerabilites, tvm, threat & vulnerability management, zero day, 0-day, mitigate 0 day vulnerabilites, vulnerable CVE
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
ms.openlocfilehash: 941e4989dcb91ff9240131f5980d0e1eced2b21d
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501223"
---
# <a name="mitigate-zero-day-vulnerabilities---threat-and-vulnerability-management"></a><span data-ttu-id="7dea4-104">Minimieren von Zero-Day-Sicherheitsrisiken – Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="7dea4-104">Mitigate zero-day vulnerabilities - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7dea4-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="7dea4-105">**Applies to:**</span></span>

- [<span data-ttu-id="7dea4-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="7dea4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="7dea4-107">Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="7dea4-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="7dea4-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7dea4-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="7dea4-109">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="7dea4-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7dea4-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="7dea4-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="7dea4-111">Eine Zero-Day-Sicherheitslücke ist eine öffentlich offengelegte Sicherheitslücke, für die keine offiziellen Patches oder Sicherheitsupdates veröffentlicht wurden.</span><span class="sxs-lookup"><span data-stu-id="7dea4-111">A zero-day vulnerability is a publicly disclosed vulnerability for which no official patches or security updates have been released.</span></span> <span data-ttu-id="7dea4-112">Zero-Day-Sicherheitsrisiken haben häufig einen hohen Schweregrad und werden aktiv ausgenutzt.</span><span class="sxs-lookup"><span data-stu-id="7dea4-112">Zero-day vulnerabilities often have high severity levels and are actively exploited.</span></span>

<span data-ttu-id="7dea4-113">Das Bedrohungs- und Sicherheitsrisikomanagement zeigt nur Zero-Day-Sicherheitsrisiken an, über die informationen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="7dea4-113">Threat and vulnerability management will only display zero-day vulnerabilities it has information about.</span></span>

## <a name="find-information-about-zero-day-vulnerabilities"></a><span data-ttu-id="7dea4-114">Informationen zu Zero-Day-Sicherheitsrisiken finden</span><span class="sxs-lookup"><span data-stu-id="7dea4-114">Find information about zero-day vulnerabilities</span></span>

<span data-ttu-id="7dea4-115">Sobald eine Zero-Day-Sicherheitslücke gefunden wurde, werden Informationen dazu über die folgenden Erfahrungen im Microsoft Defender Security Center vermittelt.</span><span class="sxs-lookup"><span data-stu-id="7dea4-115">Once a zero-day vulnerability has been found, information about it will be conveyed through the following experiences in the Microsoft Defender Security Center.</span></span>

### <a name="threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="7dea4-116">Dashboard zur Verwaltung von Bedrohungen und Sicherheitslücken</span><span class="sxs-lookup"><span data-stu-id="7dea4-116">Threat and vulnerability management dashboard</span></span>

<span data-ttu-id="7dea4-117">Suchen Sie auf der Karte "Top security recommendations" nach Empfehlungen mit einem Zero-Day-Tag.</span><span class="sxs-lookup"><span data-stu-id="7dea4-117">Look for recommendations with a zero-day tag in the “Top security recommendations” card.</span></span>

![Die besten Empfehlungen mit einem Zero-Day-Tag.](images/tvm-zero-day-top-security-recommendations.png)

<span data-ttu-id="7dea4-119">Suchen Sie auf der Karte "Besonders anfällige Software" nach Top-Software mit dem Tag "Zero-Day".</span><span class="sxs-lookup"><span data-stu-id="7dea4-119">Find top software with the zero-day tag in the "Top vulnerable software" card.</span></span>

![Besonders anfällige Software mit einem Zero-Day-Tag.](images/tvm-zero-day-top-software.png)

### <a name="weaknesses-page"></a><span data-ttu-id="7dea4-121">Seite "Schwächen"</span><span class="sxs-lookup"><span data-stu-id="7dea4-121">Weaknesses page</span></span>

<span data-ttu-id="7dea4-122">Suchen Sie nach der benannten Zero-Day-Sicherheitslücke zusammen mit einer Beschreibung und Details.</span><span class="sxs-lookup"><span data-stu-id="7dea4-122">Look for the named zero-day vulnerability along with a description and details.</span></span>

- <span data-ttu-id="7dea4-123">Wenn dieser Sicherheitsanfälligkeit eine CVE-ID zugewiesen ist, wird neben dem CVE-Namen die Zero-Day-Bezeichnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7dea4-123">If this vulnerability has a CVE-ID assigned, you’ll see the zero-day label next to the CVE name.</span></span>

- <span data-ttu-id="7dea4-124">Wenn dieser Sicherheitsanfälligkeit keine CVE-ID zugewiesen ist, finden Sie sie unter einem internen, temporären Namen, der wie "TVM-XXXX-XXXX" aussieht.</span><span class="sxs-lookup"><span data-stu-id="7dea4-124">If this vulnerability has no CVE-ID assigned, you'll find it under an internal, temporary name that looks like “TVM-XXXX-XXXX”.</span></span> <span data-ttu-id="7dea4-125">Der Name wird aktualisiert, sobald eine offizielle CVE-ID zugewiesen wurde, aber der vorherige interne Name ist weiterhin durchsuchbar und wird im Seitenbereich gefunden.</span><span class="sxs-lookup"><span data-stu-id="7dea4-125">The name will be updated once an official CVE-ID has been assigned, but the previous internal name will still be searchable and found in the side-panel.</span></span>

![Zero day example for CVE-2020-17087 in weaknesses page.](images/tvm-zero-day-weakness-name.png)

### <a name="software-inventory-page"></a><span data-ttu-id="7dea4-127">Seite "Softwareinventar"</span><span class="sxs-lookup"><span data-stu-id="7dea4-127">Software inventory page</span></span>

<span data-ttu-id="7dea4-128">Suchen Sie nach Software mit dem Zero-Day-Tag.</span><span class="sxs-lookup"><span data-stu-id="7dea4-128">Look for software with the zero-day tag.</span></span> <span data-ttu-id="7dea4-129">Filtern Sie nach dem Tag "Zero Day", um nur Software mit Zero-Day-Sicherheitsrisiken zu sehen.</span><span class="sxs-lookup"><span data-stu-id="7dea4-129">Filter by the "zero day" tag to only see software with zero-day vulnerabilities.</span></span>

![Zero day example of Windows Server 2016 in the software inventory page.](images/tvm-zero-day-software-inventory.png)

### <a name="software-page"></a><span data-ttu-id="7dea4-131">Softwareseite</span><span class="sxs-lookup"><span data-stu-id="7dea4-131">Software page</span></span>

<span data-ttu-id="7dea4-132">Suchen Sie nach einem Zero-Day-Tag für jede Software, die von der Zero-Day-Sicherheitslücke betroffen ist.</span><span class="sxs-lookup"><span data-stu-id="7dea4-132">Look for a zero-day tag for each software that has been affected by the zero–day vulnerability.</span></span>

![Zero day example for Windows Server 2016 software page.](images/tvm-zero-day-software-page.png)

### <a name="security-recommendations-page"></a><span data-ttu-id="7dea4-134">Seite mit Sicherheitsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="7dea4-134">Security recommendations page</span></span>

<span data-ttu-id="7dea4-135">Zeigen Sie klare Vorschläge zu Korrektur- und Abhilfemaßnahmen an, einschließlich Problemumgehungen, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="7dea4-135">View clear suggestions about remediation and mitigation options, including workarounds if they exist.</span></span> <span data-ttu-id="7dea4-136">Filtern Sie nach dem Tag "Zero Day", um nur Sicherheitsempfehlungen zur Behandlung von Zero-Day-Sicherheitsrisiken zu sehen.</span><span class="sxs-lookup"><span data-stu-id="7dea4-136">Filter by the "zero day" tag to only see security recommendations addressing zero-day vulnerabilities.</span></span>

<span data-ttu-id="7dea4-137">Wenn Software mit einer Zero-Day-Sicherheitslücke und zusätzlichen Sicherheitsrisiken zur Verfügung steht, erhalten Sie eine Empfehlung zu allen Sicherheitsrisiken.</span><span class="sxs-lookup"><span data-stu-id="7dea4-137">If there's software with a zero-day vulnerability and additional vulnerabilities to address, you'll get one recommendation about all vulnerabilities.</span></span>

![Zero day example of Windows Server 2016 in the security recommendations page.](images/tvm-zero-day-security-recommendation.png)

## <a name="addressing-zero-day-vulnerabilities"></a><span data-ttu-id="7dea4-139">Behebung von Zero-Day-Sicherheitsrisiken</span><span class="sxs-lookup"><span data-stu-id="7dea4-139">Addressing zero-day vulnerabilities</span></span>

<span data-ttu-id="7dea4-140">Wechseln Sie zur Seite Sicherheitsempfehlung, und wählen Sie eine Empfehlung mit einem Nulltag aus.</span><span class="sxs-lookup"><span data-stu-id="7dea4-140">Go to the security recommendation page and select a recommendation with a zero-day.</span></span> <span data-ttu-id="7dea4-141">Ein Flyout wird mit Informationen zu den Zero-Day- und anderen Sicherheitsrisiken für diese Software geöffnet.</span><span class="sxs-lookup"><span data-stu-id="7dea4-141">A flyout will open with information about the zero-day and other vulnerabilities for that software.</span></span>

<span data-ttu-id="7dea4-142">Es gibt einen Link zu Abhilfemaßnahmen und Problemumgehungen, wenn diese verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="7dea4-142">There will be a link to mitigation options and workarounds if they are available.</span></span> <span data-ttu-id="7dea4-143">Problemumgehungen können dazu beitragen, das Risiko dieser Zero-Day-Sicherheitslücke zu verringern, bis ein Patch oder Sicherheitsupdate bereitgestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="7dea4-143">Workarounds may help reduce the risk posed by this zero-day vulnerability until a patch or security update can be deployed.</span></span>

<span data-ttu-id="7dea4-144">Öffnen Sie Korrekturoptionen, und wählen Sie den Aufmerksamkeitstyp aus.</span><span class="sxs-lookup"><span data-stu-id="7dea4-144">Open remediation options and choose the attention type.</span></span> <span data-ttu-id="7dea4-145">Für die Zero-Day-Sicherheitsrisiken wird eine Option zur Behebung von "Aufmerksamkeit erforderlich" empfohlen, da ein Update noch nicht veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="7dea4-145">An "attention required" remediation option is recommended for the zero-day vulnerabilities, since an update hasn't been released yet.</span></span> <span data-ttu-id="7dea4-146">Sie können kein Fälligkeitsdatum auswählen, da keine bestimmte Aktion durchzuführen ist.</span><span class="sxs-lookup"><span data-stu-id="7dea4-146">You won't be able to select a due date, since there's no specific action to perform.</span></span> <span data-ttu-id="7dea4-147">Wenn ältere Sicherheitsrisiken für diese Software vorhanden sind, die Sie bereinigungen möchten, können Sie die Option "Aufmerksamkeit erforderlich" außer Kraft setzen und "aktualisieren" auswählen.</span><span class="sxs-lookup"><span data-stu-id="7dea4-147">If there are older vulnerabilities for this software you wish to remediation, you can override the "attention required" remediation option and choose “update.”</span></span>

![Flyoutbeispiel für zero day von Windows Server 2016 auf der Seite sicherheitsempfehlungen.](images/tvm-zero-day-recommendation-flyout400.png)

## <a name="track-zero-day-remediation-activities"></a><span data-ttu-id="7dea4-149">Nachverfolgen von Zero-Day-Korrekturaktivitäten</span><span class="sxs-lookup"><span data-stu-id="7dea4-149">Track zero-day remediation activities</span></span>

<span data-ttu-id="7dea4-150">Wechseln Sie zur Seite [](tvm-remediation.md) Zur Behebung von Bedrohungen und Sicherheitslücken, um das Problembehebungsaktivitätselement zu sehen.</span><span class="sxs-lookup"><span data-stu-id="7dea4-150">Go to the threat and vulnerability management [Remediation](tvm-remediation.md) page to view the remediation activity item.</span></span> <span data-ttu-id="7dea4-151">Wenn Sie die Option "Aufmerksamkeit erforderlich" ausgewählt haben, gibt es keine Statusanzeige, keinen Ticketstatus oder kein Fälligkeitsdatum, da es keine tatsächliche Aktion gibt, die wir überwachen können.</span><span class="sxs-lookup"><span data-stu-id="7dea4-151">If you chose the "attention required" remediation option, there will be no progress bar, ticket status, or due date since there's no actual action we can monitor.</span></span> <span data-ttu-id="7dea4-152">Sie können nach Behebungstyp filtern, z. B. "Softwareupdate" oder "Aufmerksamkeit erforderlich", um alle Aktivitätselemente in derselben Kategorie zu sehen.</span><span class="sxs-lookup"><span data-stu-id="7dea4-152">You can filter by remediation type, such as "software update" or "attention required," to see all activity items in the same category.</span></span>

## <a name="patching-zero-day-vulnerabilities"></a><span data-ttu-id="7dea4-153">Patchen von Zero-Day-Sicherheitsrisiken</span><span class="sxs-lookup"><span data-stu-id="7dea4-153">Patching zero-day vulnerabilities</span></span>

<span data-ttu-id="7dea4-154">Wenn ein Patch für den Nulltag freigegeben wird, wird die Empfehlung in "Update" und eine blaue Beschriftung daneben mit der Bezeichnung "Neues Sicherheitsupdate für null Tag" geändert.</span><span class="sxs-lookup"><span data-stu-id="7dea4-154">When a patch is released for the zero-day, the recommendation will be changed to “Update” and a blue label next to it that says “New security update for zero day.”</span></span> <span data-ttu-id="7dea4-155">Es wird nicht mehr als Zero-Day-Tag in Betracht ziehen, das Zero-Day-Tag wird von allen Seiten entfernt.</span><span class="sxs-lookup"><span data-stu-id="7dea4-155">It will no longer consider as a zero-day, the zero-day tag will be removed from all pages.</span></span>

![Empfehlung für "Aktualisieren von Microsoft Windows 10" mit neuer Patchbezeichnung.](images/tvm-zero-day-patch.jpg)

## <a name="related-articles"></a><span data-ttu-id="7dea4-157">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="7dea4-157">Related articles</span></span>

- [<span data-ttu-id="7dea4-158">Übersicht über die Verwaltung von Bedrohungen und Sicherheitslücken</span><span class="sxs-lookup"><span data-stu-id="7dea4-158">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="7dea4-159">Dashboard</span><span class="sxs-lookup"><span data-stu-id="7dea4-159">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="7dea4-160">Sicherheitsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="7dea4-160">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="7dea4-161">Softwarebestand</span><span class="sxs-lookup"><span data-stu-id="7dea4-161">Software inventory</span></span>](tvm-software-inventory.md)
- [<span data-ttu-id="7dea4-162">Sicherheitsrisiken in meiner Organisation</span><span class="sxs-lookup"><span data-stu-id="7dea4-162">Vulnerabilities in my organization</span></span>](tvm-weaknesses.md)
