---
title: Auflisten aller Korrekturaktivitäten
description: Gibt Informationen zu allen Korrekturaktivitäten zurück.
keywords: APIs, Wartung, Korrektur-API, abrufen, Wartungsaufgaben, alle Korrekturmaßnahmen,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 60f80e78a5f5c7da44a218c30f4b0173d4ecc829
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845132"
---
# <a name="list-all-remediation-activities"></a><span data-ttu-id="1b6ba-104">Auflisten aller Korrekturaktivitäten</span><span class="sxs-lookup"><span data-stu-id="1b6ba-104">List all remediation activities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1b6ba-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="1b6ba-105">**Applies to:**</span></span>

- [<span data-ttu-id="1b6ba-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="1b6ba-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1b6ba-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1b6ba-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1b6ba-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="1b6ba-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1b6ba-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="1b6ba-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="1b6ba-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1b6ba-110">API description</span></span>

<span data-ttu-id="1b6ba-111">Gibt Informationen zu allen Korrekturaktivitäten zurück.</span><span class="sxs-lookup"><span data-stu-id="1b6ba-111">Returns information about all remediation activities.</span></span>

<span data-ttu-id="1b6ba-112">[Erfahren Sie mehr über Korrekturaktivitäten.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="1b6ba-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

<span data-ttu-id="1b6ba-113">**URL:** GET: /api/remediationTasks</span><span class="sxs-lookup"><span data-stu-id="1b6ba-113">**URL:** GET: /api/remediationTasks</span></span>

## <a name="permissions"></a><span data-ttu-id="1b6ba-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1b6ba-114">Permissions</span></span>

<span data-ttu-id="1b6ba-115">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="1b6ba-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1b6ba-116">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="1b6ba-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="1b6ba-117">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="1b6ba-117">Permission type</span></span> | <span data-ttu-id="1b6ba-118">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="1b6ba-118">Permission</span></span> | <span data-ttu-id="1b6ba-119">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="1b6ba-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1b6ba-120">Anwendung</span><span class="sxs-lookup"><span data-stu-id="1b6ba-120">Application</span></span> | <span data-ttu-id="1b6ba-121">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="1b6ba-121">RemediationTask.Read.All</span></span> | <span data-ttu-id="1b6ba-122">\'Lesen von Sicherheitsrisiko- und Sicherheitsrisikoverwaltungsinformationen\'</span><span class="sxs-lookup"><span data-stu-id="1b6ba-122">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="1b6ba-123">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="1b6ba-123">Delegated (work or school account)</span></span> | <span data-ttu-id="1b6ba-124">RemediationTask.Read</span><span class="sxs-lookup"><span data-stu-id="1b6ba-124">RemediationTask.Read</span></span> | <span data-ttu-id="1b6ba-125">\'Lesen von Sicherheitsrisiko- und Sicherheitsrisikoverwaltungsinformationen\'</span><span class="sxs-lookup"><span data-stu-id="1b6ba-125">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="1b6ba-126">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1b6ba-126">Properties</span></span>

<span data-ttu-id="1b6ba-127">Eigenschaft (ID)</span><span class="sxs-lookup"><span data-stu-id="1b6ba-127">Property (id)</span></span> | <span data-ttu-id="1b6ba-128">Datentyp</span><span class="sxs-lookup"><span data-stu-id="1b6ba-128">Data type</span></span> | <span data-ttu-id="1b6ba-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1b6ba-129">Description</span></span> | <span data-ttu-id="1b6ba-130">Beispiel für einen zurückgegebenen Wert</span><span class="sxs-lookup"><span data-stu-id="1b6ba-130">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="1b6ba-131">category</span><span class="sxs-lookup"><span data-stu-id="1b6ba-131">category</span></span> | <span data-ttu-id="1b6ba-132">String</span><span class="sxs-lookup"><span data-stu-id="1b6ba-132">String</span></span> | <span data-ttu-id="1b6ba-133">Kategorie der Korrekturaktivität (Software/Sicherheitskonfiguration)</span><span class="sxs-lookup"><span data-stu-id="1b6ba-133">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="1b6ba-134">Software</span><span class="sxs-lookup"><span data-stu-id="1b6ba-134">Software</span></span>
<span data-ttu-id="1b6ba-135">completerEmail</span><span class="sxs-lookup"><span data-stu-id="1b6ba-135">completerEmail</span></span> | <span data-ttu-id="1b6ba-136">String</span><span class="sxs-lookup"><span data-stu-id="1b6ba-136">String</span></span> | <span data-ttu-id="1b6ba-137">Wenn die Korrekturaktivität manuell von einer Person abgeschlossen wurde, enthält diese Spalte ihre E-Mail</span><span class="sxs-lookup"><span data-stu-id="1b6ba-137">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="1b6ba-138">null</span><span class="sxs-lookup"><span data-stu-id="1b6ba-138">null</span></span>
<span data-ttu-id="1b6ba-139">completerId</span><span class="sxs-lookup"><span data-stu-id="1b6ba-139">completerId</span></span> | <span data-ttu-id="1b6ba-140">String</span><span class="sxs-lookup"><span data-stu-id="1b6ba-140">String</span></span> | <span data-ttu-id="1b6ba-141">Wenn die Korrekturaktivität manuell von einer Person abgeschlossen wurde, enthält diese Spalte ihre Objekt-ID.</span><span class="sxs-lookup"><span data-stu-id="1b6ba-141">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="1b6ba-142">null</span><span class="sxs-lookup"><span data-stu-id="1b6ba-142">null</span></span>
<span data-ttu-id="1b6ba-143">completionMethod</span><span class="sxs-lookup"><span data-stu-id="1b6ba-143">completionMethod</span></span> | <span data-ttu-id="1b6ba-144">String</span><span class="sxs-lookup"><span data-stu-id="1b6ba-144">String</span></span> | <span data-ttu-id="1b6ba-145">Eine Korrekturaktivität kann "automatisch" (wenn alle Geräte gepatcht sind) oder "manuell" von einer Person abgeschlossen abgeschlossen werden, die "Als abgeschlossen markieren" auswählt.</span><span class="sxs-lookup"><span data-stu-id="1b6ba-145">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="1b6ba-146">Automatisch</span><span class="sxs-lookup"><span data-stu-id="1b6ba-146">Automatic</span></span>
<span data-ttu-id="1b6ba-147">createdOn</span><span class="sxs-lookup"><span data-stu-id="1b6ba-147">createdOn</span></span> | <span data-ttu-id="1b6ba-148">DateTime</span><span class="sxs-lookup"><span data-stu-id="1b6ba-148">DateTime</span></span> | <span data-ttu-id="1b6ba-149">Zeitpunkt, zu dem diese Korrekturaktivität erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="1b6ba-149">Time this remediation activity was created</span></span> | <span data-ttu-id="1b6ba-150">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="1b6ba-150">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="1b6ba-151">description</span><span class="sxs-lookup"><span data-stu-id="1b6ba-151">description</span></span> | <span data-ttu-id="1b6ba-152">String</span><span class="sxs-lookup"><span data-stu-id="1b6ba-152">String</span></span> | <span data-ttu-id="1b6ba-153">Beschreibung dieser Korrekturaktivität</span><span class="sxs-lookup"><span data-stu-id="1b6ba-153">Description of this remediation activity</span></span> | <span data-ttu-id="1b6ba-154">Aktualisieren Sie Microsoft Silverlight auf eine höhere Version, um bekannte Sicherheitsrisiken zu beheben, die sich auf Ihre Geräte auswirken.</span><span class="sxs-lookup"><span data-stu-id="1b6ba-154">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="1b6ba-155">dueOn</span><span class="sxs-lookup"><span data-stu-id="1b6ba-155">dueOn</span></span> | <span data-ttu-id="1b6ba-156">DateTime</span><span class="sxs-lookup"><span data-stu-id="1b6ba-156">DateTime</span></span> | <span data-ttu-id="1b6ba-157">Fälligkeitsdatum, das der Ersteller für diese Korrekturaktivität festgelegt hat</span><span class="sxs-lookup"><span data-stu-id="1b6ba-157">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="1b6ba-158">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="1b6ba-158">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="1b6ba-159">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="1b6ba-159">fixedDevices</span></span> | <span data-ttu-id="1b6ba-160">.</span><span class="sxs-lookup"><span data-stu-id="1b6ba-160">.</span></span> | <span data-ttu-id="1b6ba-161">Die Anzahl der Geräte, die behoben wurden</span><span class="sxs-lookup"><span data-stu-id="1b6ba-161">The number of devices that have been fixed</span></span> | <span data-ttu-id="1b6ba-162">2</span><span class="sxs-lookup"><span data-stu-id="1b6ba-162">2</span></span>
<span data-ttu-id="1b6ba-163">id</span><span class="sxs-lookup"><span data-stu-id="1b6ba-163">id</span></span> | <span data-ttu-id="1b6ba-164">String</span><span class="sxs-lookup"><span data-stu-id="1b6ba-164">String</span></span> | <span data-ttu-id="1b6ba-165">ID dieser Korrekturaktivität</span><span class="sxs-lookup"><span data-stu-id="1b6ba-165">ID of this remediation activity</span></span> | <span data-ttu-id="1b6ba-166">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="1b6ba-166">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="1b6ba-167">nameId</span><span class="sxs-lookup"><span data-stu-id="1b6ba-167">nameId</span></span> | <span data-ttu-id="1b6ba-168">String</span><span class="sxs-lookup"><span data-stu-id="1b6ba-168">String</span></span> | <span data-ttu-id="1b6ba-169">Verwandter Produktname</span><span class="sxs-lookup"><span data-stu-id="1b6ba-169">Related product name</span></span> | <span data-ttu-id="1b6ba-170">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="1b6ba-170">Microsoft Silverlight</span></span>
<span data-ttu-id="1b6ba-171">priority</span><span class="sxs-lookup"><span data-stu-id="1b6ba-171">priority</span></span> | <span data-ttu-id="1b6ba-172">String</span><span class="sxs-lookup"><span data-stu-id="1b6ba-172">String</span></span> | <span data-ttu-id="1b6ba-173">Priorität des Erstellers für diese Korrekturaktivität (Hoch\Mittel\Niedrig)</span><span class="sxs-lookup"><span data-stu-id="1b6ba-173">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="1b6ba-174">Hoch</span><span class="sxs-lookup"><span data-stu-id="1b6ba-174">High</span></span>
<span data-ttu-id="1b6ba-175">Productid</span><span class="sxs-lookup"><span data-stu-id="1b6ba-175">productId</span></span> | <span data-ttu-id="1b6ba-176">String</span><span class="sxs-lookup"><span data-stu-id="1b6ba-176">String</span></span> | <span data-ttu-id="1b6ba-177">Verwandte Produkt-ID</span><span class="sxs-lookup"><span data-stu-id="1b6ba-177">Related product ID</span></span> | <span data-ttu-id="1b6ba-178">microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="1b6ba-178">microsoft-_-silverlight</span></span>
<span data-ttu-id="1b6ba-179">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="1b6ba-179">productivityImpactRemediationType</span></span> | <span data-ttu-id="1b6ba-180">String</span><span class="sxs-lookup"><span data-stu-id="1b6ba-180">String</span></span> | <span data-ttu-id="1b6ba-181">Einige Konfigurationsänderungen können nur für Geräte ohne Auswirkungen auf den Benutzer angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="1b6ba-181">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="1b6ba-182">Dieser Wert gibt die Auswahl zwischen "alle verfügbar gemachten Geräte" oder "nur Geräte ohne Auswirkungen auf den Benutzer" an.</span><span class="sxs-lookup"><span data-stu-id="1b6ba-182">This value indicates the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="1b6ba-183">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="1b6ba-183">AllExposedAssets</span></span>
<span data-ttu-id="1b6ba-184">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="1b6ba-184">rbacGroupNames</span></span> | <span data-ttu-id="1b6ba-185">String</span><span class="sxs-lookup"><span data-stu-id="1b6ba-185">String</span></span> | <span data-ttu-id="1b6ba-186">Verwandte Gerätegruppennamen</span><span class="sxs-lookup"><span data-stu-id="1b6ba-186">Related device group names</span></span> | <span data-ttu-id="1b6ba-187">[ "Windows Server", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="1b6ba-187">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="1b6ba-188">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="1b6ba-188">recommendedProgram</span></span> | <span data-ttu-id="1b6ba-189">String</span><span class="sxs-lookup"><span data-stu-id="1b6ba-189">String</span></span> | <span data-ttu-id="1b6ba-190">Empfohlenes Programm für ein Upgrade auf</span><span class="sxs-lookup"><span data-stu-id="1b6ba-190">Recommended program to upgrade to</span></span> | <span data-ttu-id="1b6ba-191">null</span><span class="sxs-lookup"><span data-stu-id="1b6ba-191">null</span></span>
<span data-ttu-id="1b6ba-192">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="1b6ba-192">recommendedVendor</span></span> | <span data-ttu-id="1b6ba-193">String</span><span class="sxs-lookup"><span data-stu-id="1b6ba-193">String</span></span> | <span data-ttu-id="1b6ba-194">Empfohlener Anbieter für ein Upgrade auf</span><span class="sxs-lookup"><span data-stu-id="1b6ba-194">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="1b6ba-195">null</span><span class="sxs-lookup"><span data-stu-id="1b6ba-195">null</span></span>
<span data-ttu-id="1b6ba-196">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="1b6ba-196">recommendedVersion</span></span> | <span data-ttu-id="1b6ba-197">String</span><span class="sxs-lookup"><span data-stu-id="1b6ba-197">String</span></span> | <span data-ttu-id="1b6ba-198">Empfohlene Version, auf die aktualisiert/aktualisiert werden soll</span><span class="sxs-lookup"><span data-stu-id="1b6ba-198">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="1b6ba-199">null</span><span class="sxs-lookup"><span data-stu-id="1b6ba-199">null</span></span>
<span data-ttu-id="1b6ba-200">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="1b6ba-200">relatedComponent</span></span> | <span data-ttu-id="1b6ba-201">String</span><span class="sxs-lookup"><span data-stu-id="1b6ba-201">String</span></span> | <span data-ttu-id="1b6ba-202">Verwandte Komponente dieser Korrekturaktivität (ähnlich der zugehörigen Komponente für eine Sicherheitsempfehlung)</span><span class="sxs-lookup"><span data-stu-id="1b6ba-202">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="1b6ba-203">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="1b6ba-203">Microsoft Silverlight</span></span>
<span data-ttu-id="1b6ba-204">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="1b6ba-204">requesterEmail</span></span> | <span data-ttu-id="1b6ba-205">String</span><span class="sxs-lookup"><span data-stu-id="1b6ba-205">String</span></span> | <span data-ttu-id="1b6ba-206">Creator-E-Mail-Adresse</span><span class="sxs-lookup"><span data-stu-id="1b6ba-206">Creator email address</span></span> | <span data-ttu-id="1b6ba-207">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1b6ba-207">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="1b6ba-208">requesterId</span><span class="sxs-lookup"><span data-stu-id="1b6ba-208">requesterId</span></span> | <span data-ttu-id="1b6ba-209">String</span><span class="sxs-lookup"><span data-stu-id="1b6ba-209">String</span></span> | <span data-ttu-id="1b6ba-210">Creator-Objekt-ID</span><span class="sxs-lookup"><span data-stu-id="1b6ba-210">Creator object id</span></span> | <span data-ttu-id="1b6ba-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="1b6ba-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="1b6ba-212">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="1b6ba-212">requesterNotes</span></span> | <span data-ttu-id="1b6ba-213">String</span><span class="sxs-lookup"><span data-stu-id="1b6ba-213">String</span></span> | <span data-ttu-id="1b6ba-214">Die Notizen (Freitext), die der Ersteller für diese Korrekturaktivität hinzugefügt hat</span><span class="sxs-lookup"><span data-stu-id="1b6ba-214">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="1b6ba-215">null</span><span class="sxs-lookup"><span data-stu-id="1b6ba-215">null</span></span>
<span data-ttu-id="1b6ba-216">Scid</span><span class="sxs-lookup"><span data-stu-id="1b6ba-216">scid</span></span> | <span data-ttu-id="1b6ba-217">String</span><span class="sxs-lookup"><span data-stu-id="1b6ba-217">String</span></span> | <span data-ttu-id="1b6ba-218">SCID der zugehörigen Sicherheitsempfehlung</span><span class="sxs-lookup"><span data-stu-id="1b6ba-218">SCID of the related security recommendation</span></span> | <span data-ttu-id="1b6ba-219">null</span><span class="sxs-lookup"><span data-stu-id="1b6ba-219">null</span></span>
<span data-ttu-id="1b6ba-220">status</span><span class="sxs-lookup"><span data-stu-id="1b6ba-220">status</span></span> | <span data-ttu-id="1b6ba-221">String</span><span class="sxs-lookup"><span data-stu-id="1b6ba-221">String</span></span> | <span data-ttu-id="1b6ba-222">Wartungsaktivitätsstatus (aktiv/abgeschlossen)</span><span class="sxs-lookup"><span data-stu-id="1b6ba-222">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="1b6ba-223">Aktiv</span><span class="sxs-lookup"><span data-stu-id="1b6ba-223">Active</span></span>
<span data-ttu-id="1b6ba-224">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="1b6ba-224">statusLastModifiedOn</span></span> | <span data-ttu-id="1b6ba-225">DateTime</span><span class="sxs-lookup"><span data-stu-id="1b6ba-225">DateTime</span></span> | <span data-ttu-id="1b6ba-226">Datum, an dem das Statusfeld aktualisiert wurde</span><span class="sxs-lookup"><span data-stu-id="1b6ba-226">Date when the status field was updated</span></span> | <span data-ttu-id="1b6ba-227">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="1b6ba-227">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="1b6ba-228">targetDevices</span><span class="sxs-lookup"><span data-stu-id="1b6ba-228">targetDevices</span></span> | <span data-ttu-id="1b6ba-229">Long</span><span class="sxs-lookup"><span data-stu-id="1b6ba-229">Long</span></span> | <span data-ttu-id="1b6ba-230">Anzahl der verfügbar gemachten Geräte, für die diese Korrektur gilt</span><span class="sxs-lookup"><span data-stu-id="1b6ba-230">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="1b6ba-231">43</span><span class="sxs-lookup"><span data-stu-id="1b6ba-231">43</span></span>
<span data-ttu-id="1b6ba-232">title</span><span class="sxs-lookup"><span data-stu-id="1b6ba-232">title</span></span> | <span data-ttu-id="1b6ba-233">String</span><span class="sxs-lookup"><span data-stu-id="1b6ba-233">String</span></span> | <span data-ttu-id="1b6ba-234">Titel dieser Korrekturaktivität</span><span class="sxs-lookup"><span data-stu-id="1b6ba-234">Title of this remediation activity</span></span> | <span data-ttu-id="1b6ba-235">Aktualisieren von Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="1b6ba-235">Update Microsoft Silverlight</span></span>
<span data-ttu-id="1b6ba-236">type</span><span class="sxs-lookup"><span data-stu-id="1b6ba-236">type</span></span> | <span data-ttu-id="1b6ba-237">String</span><span class="sxs-lookup"><span data-stu-id="1b6ba-237">String</span></span> | <span data-ttu-id="1b6ba-238">Korrekturtyp</span><span class="sxs-lookup"><span data-stu-id="1b6ba-238">Remediation type</span></span> | <span data-ttu-id="1b6ba-239">Update</span><span class="sxs-lookup"><span data-stu-id="1b6ba-239">Update</span></span>
<span data-ttu-id="1b6ba-240">Vendorid</span><span class="sxs-lookup"><span data-stu-id="1b6ba-240">vendorId</span></span> | <span data-ttu-id="1b6ba-241">String</span><span class="sxs-lookup"><span data-stu-id="1b6ba-241">String</span></span> | <span data-ttu-id="1b6ba-242">Name des zugehörigen Anbieters</span><span class="sxs-lookup"><span data-stu-id="1b6ba-242">Related vendor name</span></span> | <span data-ttu-id="1b6ba-243">Microsoft</span><span class="sxs-lookup"><span data-stu-id="1b6ba-243">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="1b6ba-244">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1b6ba-244">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="1b6ba-245">Anforderungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="1b6ba-245">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

### <a name="response-example"></a><span data-ttu-id="1b6ba-246">Anforderungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="1b6ba-246">Response example</span></span>

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks",
    "value": [
        {
            "id": "03942ef5-aewb-4w6e-b555-d6a97013844w",
            "title": "Update Microsoft Silverlight",
            "createdOn": "2021-02-10T13:20:36.4718166Z",
            "requesterId": "65548a1d-ef00-4a7a-8d19-1b967b5c36f4",
            "requesterEmail": "user1@contoso.com",
            "status": "Active",
            "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z",
            "description": "Update Silverlight to a later version  to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ",
            "relatedComponent": "Microsoft Silverlight",
            "targetDevices": 18511,
            "rbacGroupNames": [
                "UnassignedGroup",
                "hhh"
            ],
            "fixedDevices": 2866,
            "requesterNotes": "test",
            "dueOn": "2021-02-11T00:00:00Z",
            "category": "Software",
            "productivityImpactRemediationType": null,
            "priority": "Medium",
            "completionMethod": null,
            "completerId": null,
            "completerEmail": null,
            "scid": null,
            "type": "Update",
            "productId": "microsoft-_-silverlight",
            "vendorId": "microsoft",
            "nameId": "silverlight",
            "recommendedVersion": null,
            "recommendedVendor": null,
            "recommendedProgram": null
        }
    ]
}
```

## <a name="see-also"></a><span data-ttu-id="1b6ba-247">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b6ba-247">See also</span></span>

- [<span data-ttu-id="1b6ba-248">Korrekturmethoden und -eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1b6ba-248">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="1b6ba-249">Erhalten einer Korrekturaktivität nach ID</span><span class="sxs-lookup"><span data-stu-id="1b6ba-249">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="1b6ba-250">Auflisten verfügbarer Geräte einer Korrekturaktivität</span><span class="sxs-lookup"><span data-stu-id="1b6ba-250">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="1b6ba-251">Risikobasierte bedrohungsbasierte & Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="1b6ba-251">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="1b6ba-252">Sicherheitsrisiken in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="1b6ba-252">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
