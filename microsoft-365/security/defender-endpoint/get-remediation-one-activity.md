---
title: Erhalten einer Korrekturaktivität nach ID
description: Gibt Informationen für die angegebene Korrekturaktivität zurück.
keywords: apis, remediation, remediation api, get, remediation tasks, remediation by ID,
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
ms.technology: mde
ms.openlocfilehash: e0f68e8a28b302f0ae1ca06a2f892fea38a219b2
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244443"
---
# <a name="get-one-remediation-activity-by-id"></a><span data-ttu-id="a894f-104">Erhalten einer Korrekturaktivität nach ID</span><span class="sxs-lookup"><span data-stu-id="a894f-104">Get one remediation activity by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a894f-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a894f-105">**Applies to:**</span></span>

- [<span data-ttu-id="a894f-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="a894f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a894f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a894f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a894f-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="a894f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a894f-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="a894f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="a894f-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a894f-110">API description</span></span>

<span data-ttu-id="a894f-111">Gibt Informationen für die angegebene Korrekturaktivität zurück.</span><span class="sxs-lookup"><span data-stu-id="a894f-111">Returns information for the specified remediation activity.</span></span> <span data-ttu-id="a894f-112">Stellt die gleichen Spalten wie Alle Korrekturaktivitäten "get all [remediation"](get-remediation-all-activities.md)dar, gibt jedoch nur Ergebnisse für die angegebene _Korrekturaktivität zurück._</span><span class="sxs-lookup"><span data-stu-id="a894f-112">Presents the same columns as [Get all remediation activity](get-remediation-all-activities.md)", but returns results _only for the one specified remediation activity_.</span></span>

<span data-ttu-id="a894f-113">[Erfahren Sie mehr über Korrekturaktivitäten](tvm-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="a894f-113">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-a-specified-remediation-activity-for-id"></a><span data-ttu-id="a894f-114">Auflisten einer angegebenen Korrekturaktivität für (id)</span><span class="sxs-lookup"><span data-stu-id="a894f-114">List a specified remediation activity for (id)</span></span>

<span data-ttu-id="a894f-115">**URL:** GET: /api/remediationTasks/ \{ id\}</span><span class="sxs-lookup"><span data-stu-id="a894f-115">**URL:** GET: /api/remediationTasks/\{id\}</span></span>

## <a name="permissions"></a><span data-ttu-id="a894f-116">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="a894f-116">Permissions</span></span>

<span data-ttu-id="a894f-117">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a894f-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a894f-118">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Use Microsoft Defender for Endpoint APIs for Details.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a894f-118">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="a894f-119">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="a894f-119">Permission type</span></span> | <span data-ttu-id="a894f-120">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="a894f-120">Permission</span></span> | <span data-ttu-id="a894f-121">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="a894f-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a894f-122">Anwendung</span><span class="sxs-lookup"><span data-stu-id="a894f-122">Application</span></span> | <span data-ttu-id="a894f-123">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="a894f-123">RemediationTask.Read.All</span></span> | <span data-ttu-id="a894f-124">\'Informationen zu Sicherheitslücken in Bedrohungs- und Sicherheitsrisikoverwaltung lesen\'</span><span class="sxs-lookup"><span data-stu-id="a894f-124">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="a894f-125">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="a894f-125">Delegated (work or school account)</span></span> | <span data-ttu-id="a894f-126">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="a894f-126">RemediationTask.Read.Read</span></span> | <span data-ttu-id="a894f-127">\'Informationen zu Sicherheitslücken in Bedrohungs- und Sicherheitsrisikoverwaltung lesen\'</span><span class="sxs-lookup"><span data-stu-id="a894f-127">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="a894f-128">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a894f-128">Properties</span></span>

<span data-ttu-id="a894f-129">Property (id)</span><span class="sxs-lookup"><span data-stu-id="a894f-129">Property (id)</span></span> | <span data-ttu-id="a894f-130">Datentyp</span><span class="sxs-lookup"><span data-stu-id="a894f-130">Data type</span></span> | <span data-ttu-id="a894f-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a894f-131">Description</span></span> | <span data-ttu-id="a894f-132">Beispiel für einen zurückgegebenen Wert</span><span class="sxs-lookup"><span data-stu-id="a894f-132">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="a894f-133">category</span><span class="sxs-lookup"><span data-stu-id="a894f-133">category</span></span> | <span data-ttu-id="a894f-134">String</span><span class="sxs-lookup"><span data-stu-id="a894f-134">String</span></span> | <span data-ttu-id="a894f-135">Kategorie der Korrekturaktivität (Software-/Sicherheitskonfiguration)</span><span class="sxs-lookup"><span data-stu-id="a894f-135">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="a894f-136">Software</span><span class="sxs-lookup"><span data-stu-id="a894f-136">Software</span></span>
<span data-ttu-id="a894f-137">completerEmail</span><span class="sxs-lookup"><span data-stu-id="a894f-137">completerEmail</span></span> | <span data-ttu-id="a894f-138">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a894f-138">String</span></span> | <span data-ttu-id="a894f-139">Wenn die Korrekturaktivität manuell von einer Person abgeschlossen wurde, enthält diese Spalte ihre E-Mails.</span><span class="sxs-lookup"><span data-stu-id="a894f-139">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="a894f-140">null</span><span class="sxs-lookup"><span data-stu-id="a894f-140">null</span></span>
<span data-ttu-id="a894f-141">completerId</span><span class="sxs-lookup"><span data-stu-id="a894f-141">completerId</span></span> | <span data-ttu-id="a894f-142">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a894f-142">String</span></span> | <span data-ttu-id="a894f-143">Wenn die Korrekturaktivität manuell von einer Person abgeschlossen wurde, enthält diese Spalte ihre Objekt-ID.</span><span class="sxs-lookup"><span data-stu-id="a894f-143">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="a894f-144">null</span><span class="sxs-lookup"><span data-stu-id="a894f-144">null</span></span>
<span data-ttu-id="a894f-145">completionMethod</span><span class="sxs-lookup"><span data-stu-id="a894f-145">completionMethod</span></span> | <span data-ttu-id="a894f-146">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a894f-146">String</span></span> | <span data-ttu-id="a894f-147">Eine Korrekturaktivität kann "automatisch" (wenn alle Geräte gepatcht sind) oder "manuell" von einer Person abgeschlossen werden, die "als abgeschlossen markieren" auswählt.</span><span class="sxs-lookup"><span data-stu-id="a894f-147">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="a894f-148">Automatisch</span><span class="sxs-lookup"><span data-stu-id="a894f-148">Automatic</span></span>
<span data-ttu-id="a894f-149">createdOn</span><span class="sxs-lookup"><span data-stu-id="a894f-149">createdOn</span></span> | <span data-ttu-id="a894f-150">DateTime</span><span class="sxs-lookup"><span data-stu-id="a894f-150">DateTime</span></span> | <span data-ttu-id="a894f-151">Zeitpunkt, zu dem diese Korrekturaktivität erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="a894f-151">Time this remediation activity was created</span></span> | <span data-ttu-id="a894f-152">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="a894f-152">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="a894f-153">description</span><span class="sxs-lookup"><span data-stu-id="a894f-153">description</span></span> | <span data-ttu-id="a894f-154">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a894f-154">String</span></span> | <span data-ttu-id="a894f-155">Beschreibung dieser Korrekturaktivität</span><span class="sxs-lookup"><span data-stu-id="a894f-155">Description of this remediation activity</span></span> | <span data-ttu-id="a894f-156">Aktualisieren Sie Microsoft Silverlight auf eine spätere Version, um bekannte Sicherheitsrisiken für Ihre Geräte zu mindern.</span><span class="sxs-lookup"><span data-stu-id="a894f-156">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="a894f-157">dueOn</span><span class="sxs-lookup"><span data-stu-id="a894f-157">dueOn</span></span> | <span data-ttu-id="a894f-158">DateTime</span><span class="sxs-lookup"><span data-stu-id="a894f-158">DateTime</span></span> | <span data-ttu-id="a894f-159">Fälligkeitsdatum, das der Ersteller für diese Korrekturaktivität festgelegt hat</span><span class="sxs-lookup"><span data-stu-id="a894f-159">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="a894f-160">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="a894f-160">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="a894f-161">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="a894f-161">fixedDevices</span></span> |  | <span data-ttu-id="a894f-162">Die Anzahl der geräte, die behoben wurden</span><span class="sxs-lookup"><span data-stu-id="a894f-162">The number of devices that have been fixed</span></span> | <span data-ttu-id="a894f-163">2</span><span class="sxs-lookup"><span data-stu-id="a894f-163">2</span></span>
<span data-ttu-id="a894f-164">id</span><span class="sxs-lookup"><span data-stu-id="a894f-164">id</span></span> | <span data-ttu-id="a894f-165">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a894f-165">String</span></span> | <span data-ttu-id="a894f-166">ID dieser Korrekturaktivität</span><span class="sxs-lookup"><span data-stu-id="a894f-166">ID of this remediation activity</span></span> | <span data-ttu-id="a894f-167">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="a894f-167">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="a894f-168">nameId</span><span class="sxs-lookup"><span data-stu-id="a894f-168">nameId</span></span> | <span data-ttu-id="a894f-169">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a894f-169">String</span></span> | <span data-ttu-id="a894f-170">Verwandter Produktname</span><span class="sxs-lookup"><span data-stu-id="a894f-170">Related product name</span></span> | <span data-ttu-id="a894f-171">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="a894f-171">Microsoft Silverlight</span></span>
<span data-ttu-id="a894f-172">priority</span><span class="sxs-lookup"><span data-stu-id="a894f-172">priority</span></span> | <span data-ttu-id="a894f-173">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a894f-173">String</span></span> | <span data-ttu-id="a894f-174">Priorität, die der Ersteller für diese Korrekturaktivität festgelegt hat (High\Medium\Low)</span><span class="sxs-lookup"><span data-stu-id="a894f-174">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="a894f-175">Hoch</span><span class="sxs-lookup"><span data-stu-id="a894f-175">High</span></span>
<span data-ttu-id="a894f-176">productId</span><span class="sxs-lookup"><span data-stu-id="a894f-176">productId</span></span> | <span data-ttu-id="a894f-177">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a894f-177">String</span></span> | <span data-ttu-id="a894f-178">Verwandte Produkt-ID</span><span class="sxs-lookup"><span data-stu-id="a894f-178">Related product ID</span></span> | <span data-ttu-id="a894f-179">microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="a894f-179">microsoft-_-silverlight</span></span>
<span data-ttu-id="a894f-180">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="a894f-180">productivityImpactRemediationType</span></span> | <span data-ttu-id="a894f-181">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a894f-181">String</span></span> | <span data-ttu-id="a894f-182">Einige Konfigurationsänderungen konnten nur für Geräte ohne Benutzerwirkung angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="a894f-182">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="a894f-183">Dieser Wert gibt die Auswahl zwischen "allen verfügbar gemachten Geräten" oder "nur Geräten ohne Benutzerwirkung" an.</span><span class="sxs-lookup"><span data-stu-id="a894f-183">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="a894f-184">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="a894f-184">AllExposedAssets</span></span>
<span data-ttu-id="a894f-185">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="a894f-185">rbacGroupNames</span></span> | <span data-ttu-id="a894f-186">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a894f-186">String</span></span> | <span data-ttu-id="a894f-187">Verwandte Gerätegruppennamen</span><span class="sxs-lookup"><span data-stu-id="a894f-187">Related device group names</span></span> | <span data-ttu-id="a894f-188">[ "Windows Server", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="a894f-188">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="a894f-189">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="a894f-189">recommendedProgram</span></span> | <span data-ttu-id="a894f-190">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a894f-190">String</span></span> | <span data-ttu-id="a894f-191">Empfohlenes Programm zum Upgrade auf</span><span class="sxs-lookup"><span data-stu-id="a894f-191">Recommended program to upgrade to</span></span> | <span data-ttu-id="a894f-192">null</span><span class="sxs-lookup"><span data-stu-id="a894f-192">null</span></span>
<span data-ttu-id="a894f-193">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="a894f-193">recommendedVendor</span></span> | <span data-ttu-id="a894f-194">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a894f-194">String</span></span> | <span data-ttu-id="a894f-195">Empfohlener Anbieter zum Upgrade auf</span><span class="sxs-lookup"><span data-stu-id="a894f-195">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="a894f-196">null</span><span class="sxs-lookup"><span data-stu-id="a894f-196">null</span></span>
<span data-ttu-id="a894f-197">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="a894f-197">recommendedVersion</span></span> | <span data-ttu-id="a894f-198">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a894f-198">String</span></span> | <span data-ttu-id="a894f-199">Empfohlene Version zum Aktualisieren/Aktualisieren auf</span><span class="sxs-lookup"><span data-stu-id="a894f-199">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="a894f-200">null</span><span class="sxs-lookup"><span data-stu-id="a894f-200">null</span></span>
<span data-ttu-id="a894f-201">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="a894f-201">relatedComponent</span></span> | <span data-ttu-id="a894f-202">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a894f-202">String</span></span> | <span data-ttu-id="a894f-203">Verwandte Komponente dieser Korrekturaktivität (ähnlich der zugehörigen Komponente für eine Sicherheitsempfehlung)</span><span class="sxs-lookup"><span data-stu-id="a894f-203">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="a894f-204">Microsoft Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="a894f-204">Microsoft Microsoft Silverlight</span></span>
<span data-ttu-id="a894f-205">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="a894f-205">requesterEmail</span></span> | <span data-ttu-id="a894f-206">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a894f-206">String</span></span> | <span data-ttu-id="a894f-207">E-Mail-Adresse des Erstellers</span><span class="sxs-lookup"><span data-stu-id="a894f-207">Creator email address</span></span> | <span data-ttu-id="a894f-208">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a894f-208">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="a894f-209">requesterId</span><span class="sxs-lookup"><span data-stu-id="a894f-209">requesterId</span></span> | <span data-ttu-id="a894f-210">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a894f-210">String</span></span> | <span data-ttu-id="a894f-211">Creator-Objekt-ID</span><span class="sxs-lookup"><span data-stu-id="a894f-211">Creator object id</span></span> | <span data-ttu-id="a894f-212">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="a894f-212">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="a894f-213">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="a894f-213">requesterNotes</span></span> | <span data-ttu-id="a894f-214">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a894f-214">String</span></span> | <span data-ttu-id="a894f-215">Die Notizen (Freitext), die der Ersteller für diese Korrekturaktivität hinzugefügt hat</span><span class="sxs-lookup"><span data-stu-id="a894f-215">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="a894f-216">null</span><span class="sxs-lookup"><span data-stu-id="a894f-216">null</span></span>
<span data-ttu-id="a894f-217">scid</span><span class="sxs-lookup"><span data-stu-id="a894f-217">scid</span></span> | <span data-ttu-id="a894f-218">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a894f-218">String</span></span> | <span data-ttu-id="a894f-219">SCID der zugehörigen Sicherheitsempfehlung</span><span class="sxs-lookup"><span data-stu-id="a894f-219">SCID of the related security recommendation</span></span> | <span data-ttu-id="a894f-220">null</span><span class="sxs-lookup"><span data-stu-id="a894f-220">null</span></span>
<span data-ttu-id="a894f-221">status</span><span class="sxs-lookup"><span data-stu-id="a894f-221">status</span></span> | <span data-ttu-id="a894f-222">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a894f-222">String</span></span> | <span data-ttu-id="a894f-223">Status der Korrekturaktivität (Aktiv/Abgeschlossen)</span><span class="sxs-lookup"><span data-stu-id="a894f-223">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="a894f-224">Aktiv</span><span class="sxs-lookup"><span data-stu-id="a894f-224">Active</span></span>
<span data-ttu-id="a894f-225">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="a894f-225">statusLastModifiedOn</span></span> | <span data-ttu-id="a894f-226">DateTime</span><span class="sxs-lookup"><span data-stu-id="a894f-226">DateTime</span></span> | <span data-ttu-id="a894f-227">Datum, an dem das Statusfeld aktualisiert wurde</span><span class="sxs-lookup"><span data-stu-id="a894f-227">Date when the status field was updated</span></span> | <span data-ttu-id="a894f-228">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="a894f-228">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="a894f-229">targetDevices</span><span class="sxs-lookup"><span data-stu-id="a894f-229">targetDevices</span></span> | <span data-ttu-id="a894f-230">Long</span><span class="sxs-lookup"><span data-stu-id="a894f-230">Long</span></span> | <span data-ttu-id="a894f-231">Anzahl der verfügbar gemachten Geräte, auf die diese Behebung anwendbar ist</span><span class="sxs-lookup"><span data-stu-id="a894f-231">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="a894f-232">43</span><span class="sxs-lookup"><span data-stu-id="a894f-232">43</span></span>
<span data-ttu-id="a894f-233">title</span><span class="sxs-lookup"><span data-stu-id="a894f-233">title</span></span> | <span data-ttu-id="a894f-234">String</span><span class="sxs-lookup"><span data-stu-id="a894f-234">String</span></span> | <span data-ttu-id="a894f-235">Titel dieser Korrekturaktivität</span><span class="sxs-lookup"><span data-stu-id="a894f-235">Title of this remediation activity</span></span> | <span data-ttu-id="a894f-236">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="a894f-236">Microsoft Silverlight</span></span>
<span data-ttu-id="a894f-237">type</span><span class="sxs-lookup"><span data-stu-id="a894f-237">type</span></span> | <span data-ttu-id="a894f-238">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a894f-238">String</span></span> | <span data-ttu-id="a894f-239">Behebungstyp</span><span class="sxs-lookup"><span data-stu-id="a894f-239">Remediation type</span></span> | <span data-ttu-id="a894f-240">Aktualisieren</span><span class="sxs-lookup"><span data-stu-id="a894f-240">Update</span></span>
<span data-ttu-id="a894f-241">vendorId</span><span class="sxs-lookup"><span data-stu-id="a894f-241">vendorId</span></span> | <span data-ttu-id="a894f-242">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a894f-242">String</span></span> | <span data-ttu-id="a894f-243">Verwandter Herstellername</span><span class="sxs-lookup"><span data-stu-id="a894f-243">Related vendor name</span></span> | <span data-ttu-id="a894f-244">Microsoft</span><span class="sxs-lookup"><span data-stu-id="a894f-244">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="a894f-245">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a894f-245">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="a894f-246">Anforderungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="a894f-246">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

### <a name="response-example"></a><span data-ttu-id="a894f-247">Anforderungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="a894f-247">Response example</span></span>

```json
{ 
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks/$entity", 
    "id": "03942ef5-aecb-4c6e-b555-d6a97013844c", 
    "title": "Update Microsoft Silverlight", 
    "createdOn": "2021-02-10T13:20:36.4718166Z", 
    "requesterId": "65548a1d-efo0-4a7a-8d19-1b967b5c36f4", 
    "requesterEmail": "user1@contoso.com", 
    "status": "Active", 
    "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z", 
    "description": "Update Silverlight to a later version to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ", 
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
```

## <a name="see-also"></a><span data-ttu-id="a894f-248">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a894f-248">See also</span></span>

- [<span data-ttu-id="a894f-249">Korrekturmethoden und -eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a894f-249">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="a894f-250">Auflisten aller Korrekturaktivitäten</span><span class="sxs-lookup"><span data-stu-id="a894f-250">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="a894f-251">Auflisten verfügbarer Geräte einer Korrekturaktivität</span><span class="sxs-lookup"><span data-stu-id="a894f-251">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="a894f-252">Risikobasierte Bedrohungsrisiken & Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="a894f-252">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="a894f-253">Sicherheitsrisiken in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="a894f-253">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
