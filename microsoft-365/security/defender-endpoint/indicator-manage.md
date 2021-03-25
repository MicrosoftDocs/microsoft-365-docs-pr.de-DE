---
title: Verwalten von Indikatoren
ms.reviewer: ''
description: 'Verwalten von Indikatoren für einen Dateihash, eine #A0, URLs oder Domänen, die die Erkennung, Verhinderung und den Ausschluss von Entitäten definieren.'
keywords: import, indicator, list, ioc, csv, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6edb4ddf764788a11ea3b6f1863dd95e694f1849
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067704"
---
# <a name="manage-indicators"></a><span data-ttu-id="e2f85-104">Verwalten von Indikatoren</span><span class="sxs-lookup"><span data-stu-id="e2f85-104">Manage indicators</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e2f85-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e2f85-105">**Applies to:**</span></span>
- [<span data-ttu-id="e2f85-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="e2f85-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="e2f85-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e2f85-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="e2f85-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="e2f85-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e2f85-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="e2f85-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


1. <span data-ttu-id="e2f85-110">Wählen Sie im Navigationsbereich **Einstellungsindikatoren**  >  **aus.**</span><span class="sxs-lookup"><span data-stu-id="e2f85-110">In the navigation pane, select **Settings** > **Indicators**.</span></span>

2. <span data-ttu-id="e2f85-111">Wählen Sie die Registerkarte des Entitätstyps aus, den Sie verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="e2f85-111">Select the tab of the entity type you'd like to manage.</span></span>  

3. <span data-ttu-id="e2f85-112">Aktualisieren Sie die Details des Indikators, und klicken Sie auf **Speichern** oder klicken Sie auf die Schaltfläche Löschen, wenn Sie die Entität aus der Liste entfernen möchten. </span><span class="sxs-lookup"><span data-stu-id="e2f85-112">Update the details of the indicator and click **Save** or click the **Delete** button if you'd like to remove the entity from the list.</span></span>

## <a name="import-a-list-of-iocs"></a><span data-ttu-id="e2f85-113">Importieren einer Liste von IoCs</span><span class="sxs-lookup"><span data-stu-id="e2f85-113">Import a list of IoCs</span></span>

<span data-ttu-id="e2f85-114">Sie können auch eine CSV-Datei hochladen, die die Attribute von Indikatoren, die zu ergreifende Aktion und andere Details definiert.</span><span class="sxs-lookup"><span data-stu-id="e2f85-114">You can also choose to upload a CSV file that defines the attributes of indicators, the action to be taken, and other details.</span></span>

<span data-ttu-id="e2f85-115">Laden Sie die Beispiel-CSV herunter, um die unterstützten Spaltenattribute zu kennen.</span><span class="sxs-lookup"><span data-stu-id="e2f85-115">Download the sample CSV to know the supported column attributes.</span></span>

1. <span data-ttu-id="e2f85-116">Wählen Sie im Navigationsbereich **Einstellungsindikatoren**  >  **aus.**</span><span class="sxs-lookup"><span data-stu-id="e2f85-116">In the navigation pane, select **Settings** > **Indicators**.</span></span>

2. <span data-ttu-id="e2f85-117">Wählen Sie die Registerkarte des Entitätstyps aus, für den Sie Indikatoren importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e2f85-117">Select the tab of the entity type you'd like to import indicators for.</span></span>

3. <span data-ttu-id="e2f85-118">Wählen **Sie Datei** importieren  >  **aus.**</span><span class="sxs-lookup"><span data-stu-id="e2f85-118">Select **Import** > **Choose file**.</span></span> 

4. <span data-ttu-id="e2f85-119">Wählen Sie **Importieren** aus.</span><span class="sxs-lookup"><span data-stu-id="e2f85-119">Select **Import**.</span></span> <span data-ttu-id="e2f85-120">Tun Sie dies für alle Dateien, die Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e2f85-120">Do this for all the files you'd like to import.</span></span> 

5. <span data-ttu-id="e2f85-121">Wählen Sie **Fertig** aus.</span><span class="sxs-lookup"><span data-stu-id="e2f85-121">Select **Done**.</span></span>

<span data-ttu-id="e2f85-122">In der folgenden Tabelle sind die unterstützten Parameter aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="e2f85-122">The following table shows the supported parameters.</span></span>

<span data-ttu-id="e2f85-123">Parameter</span><span class="sxs-lookup"><span data-stu-id="e2f85-123">Parameter</span></span> | <span data-ttu-id="e2f85-124">Typ</span><span class="sxs-lookup"><span data-stu-id="e2f85-124">Type</span></span>    |   <span data-ttu-id="e2f85-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e2f85-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="e2f85-126">indicatorType</span><span class="sxs-lookup"><span data-stu-id="e2f85-126">indicatorType</span></span> | <span data-ttu-id="e2f85-127">Enum</span><span class="sxs-lookup"><span data-stu-id="e2f85-127">Enum</span></span> | <span data-ttu-id="e2f85-128">Typ des Indikators.</span><span class="sxs-lookup"><span data-stu-id="e2f85-128">Type of the indicator.</span></span> <span data-ttu-id="e2f85-129">Mögliche Werte sind: "FileSha1", "FileSha256", "IpAddress", "DomainName" und "Url".</span><span class="sxs-lookup"><span data-stu-id="e2f85-129">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span> <span data-ttu-id="e2f85-130">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="e2f85-130">**Required**</span></span>
<span data-ttu-id="e2f85-131">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="e2f85-131">indicatorValue</span></span> | <span data-ttu-id="e2f85-132">String</span><span class="sxs-lookup"><span data-stu-id="e2f85-132">String</span></span> | <span data-ttu-id="e2f85-133">Identität der [Indicator-Entität.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="e2f85-133">Identity of the [Indicator](ti-indicator.md) entity.</span></span> <span data-ttu-id="e2f85-134">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="e2f85-134">**Required**</span></span>
<span data-ttu-id="e2f85-135">Aktion</span><span class="sxs-lookup"><span data-stu-id="e2f85-135">action</span></span> | <span data-ttu-id="e2f85-136">Enum</span><span class="sxs-lookup"><span data-stu-id="e2f85-136">Enum</span></span> | <span data-ttu-id="e2f85-137">Die Aktion, die ergriffen wird, wenn der Indikator in der Organisation ermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="e2f85-137">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="e2f85-138">Mögliche Werte sind: "Alert", "AlertAndBlock" und "Allowed".</span><span class="sxs-lookup"><span data-stu-id="e2f85-138">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span> <span data-ttu-id="e2f85-139">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="e2f85-139">**Required**</span></span>
<span data-ttu-id="e2f85-140">title</span><span class="sxs-lookup"><span data-stu-id="e2f85-140">title</span></span> | <span data-ttu-id="e2f85-141">String</span><span class="sxs-lookup"><span data-stu-id="e2f85-141">String</span></span> | <span data-ttu-id="e2f85-142">Titel der Warnung des Indikators.</span><span class="sxs-lookup"><span data-stu-id="e2f85-142">Indicator alert title.</span></span> <span data-ttu-id="e2f85-143">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="e2f85-143">**Required**</span></span>
<span data-ttu-id="e2f85-144">description</span><span class="sxs-lookup"><span data-stu-id="e2f85-144">description</span></span> | <span data-ttu-id="e2f85-145">String</span><span class="sxs-lookup"><span data-stu-id="e2f85-145">String</span></span> |  <span data-ttu-id="e2f85-146">Beschreibung des Indikators.</span><span class="sxs-lookup"><span data-stu-id="e2f85-146">Description of the indicator.</span></span> <span data-ttu-id="e2f85-147">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="e2f85-147">**Required**</span></span>
<span data-ttu-id="e2f85-148">expirationTime</span><span class="sxs-lookup"><span data-stu-id="e2f85-148">expirationTime</span></span> | <span data-ttu-id="e2f85-149">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="e2f85-149">DateTimeOffset</span></span> | <span data-ttu-id="e2f85-150">Die Ablaufzeit des Indikators im folgenden Format YYYY-MM-DDTHH:MM:SS.0Z.</span><span class="sxs-lookup"><span data-stu-id="e2f85-150">The expiration time of the indicator in the following format YYYY-MM-DDTHH:MM:SS.0Z.</span></span> <span data-ttu-id="e2f85-151">**Optional**</span><span class="sxs-lookup"><span data-stu-id="e2f85-151">**Optional**</span></span>
<span data-ttu-id="e2f85-152">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="e2f85-152">severity</span></span> | <span data-ttu-id="e2f85-153">Enum</span><span class="sxs-lookup"><span data-stu-id="e2f85-153">Enum</span></span> | <span data-ttu-id="e2f85-154">Der Schweregrad des Indikators.</span><span class="sxs-lookup"><span data-stu-id="e2f85-154">The severity of the indicator.</span></span> <span data-ttu-id="e2f85-155">Mögliche Werte sind: "Informational", "Low", "Medium" und "High".</span><span class="sxs-lookup"><span data-stu-id="e2f85-155">Possible values are: "Informational", "Low", "Medium" and "High".</span></span> <span data-ttu-id="e2f85-156">**Optional**</span><span class="sxs-lookup"><span data-stu-id="e2f85-156">**Optional**</span></span>
<span data-ttu-id="e2f85-157">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="e2f85-157">recommendedActions</span></span> | <span data-ttu-id="e2f85-158">String</span><span class="sxs-lookup"><span data-stu-id="e2f85-158">String</span></span> | <span data-ttu-id="e2f85-159">Empfohlene Aktionen zur Warnung des TI-Indikators.</span><span class="sxs-lookup"><span data-stu-id="e2f85-159">TI indicator alert recommended actions.</span></span> <span data-ttu-id="e2f85-160">**Optional**</span><span class="sxs-lookup"><span data-stu-id="e2f85-160">**Optional**</span></span>
<span data-ttu-id="e2f85-161">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="e2f85-161">rbacGroupNames</span></span> | <span data-ttu-id="e2f85-162">String</span><span class="sxs-lookup"><span data-stu-id="e2f85-162">String</span></span> | <span data-ttu-id="e2f85-163">Durch Kommas getrennte Liste der RBAC-Gruppennamen, auf die der Indikator angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e2f85-163">Comma-separated list of RBAC group names the indicator would be applied to.</span></span> <span data-ttu-id="e2f85-164">**Optional**</span><span class="sxs-lookup"><span data-stu-id="e2f85-164">**Optional**</span></span>
<span data-ttu-id="e2f85-165">category</span><span class="sxs-lookup"><span data-stu-id="e2f85-165">category</span></span> | <span data-ttu-id="e2f85-166">String</span><span class="sxs-lookup"><span data-stu-id="e2f85-166">String</span></span> | <span data-ttu-id="e2f85-167">Die Kategorie der Warnung.</span><span class="sxs-lookup"><span data-stu-id="e2f85-167">Category of the alert.</span></span> <span data-ttu-id="e2f85-168">Beispiele: Ausführung und Zugriff auf Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="e2f85-168">Examples include: Execution and credential access.</span></span> <span data-ttu-id="e2f85-169">**Optional**</span><span class="sxs-lookup"><span data-stu-id="e2f85-169">**Optional**</span></span>
<span data-ttu-id="e2f85-170">mitretechniques</span><span class="sxs-lookup"><span data-stu-id="e2f85-170">mitretechniques</span></span>| <span data-ttu-id="e2f85-171">String</span><span class="sxs-lookup"><span data-stu-id="e2f85-171">String</span></span> | <span data-ttu-id="e2f85-172">CODE/ID der MITRE-Techniken (durch Komma getrennt).</span><span class="sxs-lookup"><span data-stu-id="e2f85-172">MITRE techniques code/id (comma separated).</span></span> <span data-ttu-id="e2f85-173">Weitere Informationen finden Sie unter [Enterprise tactics](https://attack.mitre.org/tactics/enterprise/).</span><span class="sxs-lookup"><span data-stu-id="e2f85-173">For more information, see [Enterprise tactics](https://attack.mitre.org/tactics/enterprise/).</span></span> <span data-ttu-id="e2f85-174">**Optional** Es wird empfohlen, bei einer MITRE-Technik einen Wert in der Kategorie hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e2f85-174">**Optional** It is recommended to add a value in category when a MITRE technique.</span></span>

<span data-ttu-id="e2f85-175">Weitere Informationen finden Sie unter [Microsoft Defender for Endpoint alert categories are now aligned with MITRE ATT&CK!](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748).</span><span class="sxs-lookup"><span data-stu-id="e2f85-175">For more information, see [Microsoft Defender for Endpoint alert categories are now aligned with MITRE ATT&CK!](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748).</span></span>


## <a name="see-also"></a><span data-ttu-id="e2f85-176">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2f85-176">See also</span></span>
- [<span data-ttu-id="e2f85-177">Erstellen von Indikatoren</span><span class="sxs-lookup"><span data-stu-id="e2f85-177">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="e2f85-178">Erstellen von Indikatoren für Dateien</span><span class="sxs-lookup"><span data-stu-id="e2f85-178">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="e2f85-179">Erstellen von Indikatoren für IPs und URLs/Domänen</span><span class="sxs-lookup"><span data-stu-id="e2f85-179">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="e2f85-180">Erstellen von Indikatoren basierend auf Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="e2f85-180">Create indicators based on certificates</span></span>](indicator-certificates.md)
