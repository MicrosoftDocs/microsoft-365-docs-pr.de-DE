---
title: Erstellen einer Warnung aus der Ereignis-API
description: Erfahren Sie, wie Sie die Api zum Erstellen von Warnungen verwenden, um eine neue Warnung über das Ereignis in Microsoft Defender für Endpunkt zu erstellen.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Warnung, Informationen, ID
search.product: eADQiWindows 10XVcnh
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 8b05dde015bc96e1ccd3f80e25c416a371e03199
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772389"
---
# <a name="create-alert-api"></a><span data-ttu-id="2daca-104">Erstellen der Warnungs-API</span><span class="sxs-lookup"><span data-stu-id="2daca-104">Create alert API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2daca-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2daca-105">**Applies to:**</span></span>
- [<span data-ttu-id="2daca-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="2daca-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2daca-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2daca-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="2daca-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="2daca-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2daca-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="2daca-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="2daca-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2daca-110">API description</span></span>
<span data-ttu-id="2daca-111">Erstellt neue [Warnung](alerts.md) am Anfang des **Ereignisses.**</span><span class="sxs-lookup"><span data-stu-id="2daca-111">Creates new [Alert](alerts.md) on top of **Event**.</span></span>
<br><span data-ttu-id="2daca-112">**Das Microsoft Defender für Endpunkt-Ereignis** ist für die Erstellung von Warnungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2daca-112">**Microsoft Defender for Endpoint Event** is required for the alert creation.</span></span>
<br><span data-ttu-id="2daca-113">Sie müssen 3 Parameter aus dem Ereignis in der Anforderung angeben: **Ereigniszeit,** **Computer-ID** und **Berichts-ID.**</span><span class="sxs-lookup"><span data-stu-id="2daca-113">You will need to supply 3 parameters from the Event in the request: **Event Time**, **Machine ID** and **Report ID**.</span></span> <span data-ttu-id="2daca-114">Siehe Beispiel unten.</span><span class="sxs-lookup"><span data-stu-id="2daca-114">See example below.</span></span>
<br><span data-ttu-id="2daca-115">Sie können ein Ereignis in der API für die erweiterte Suche oder im Portal verwenden.</span><span class="sxs-lookup"><span data-stu-id="2daca-115">You can use an event found in Advanced Hunting API or Portal.</span></span>
<br><span data-ttu-id="2daca-116">Wenn auf demselben Gerät mit demselben Titel eine geöffnete Warnung vorhanden ist, wird die neu erstellte Warnung mit ihr zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="2daca-116">If there existing an open alert on the same Device with the same Title, the new created alert will be merged with it.</span></span>
<br><span data-ttu-id="2daca-117">Bei warnungen, die über die API erstellt wurden, wird automatisch eine automatische Untersuchung gestartet.</span><span class="sxs-lookup"><span data-stu-id="2daca-117">An automatic investigation starts automatically on alerts created via the API.</span></span>


## <a name="limitations"></a><span data-ttu-id="2daca-118">Begrenzungen</span><span class="sxs-lookup"><span data-stu-id="2daca-118">Limitations</span></span>
1. <span data-ttu-id="2daca-119">Die Rateneinschränkungen für diese API sind 15 Aufrufe pro Minute.</span><span class="sxs-lookup"><span data-stu-id="2daca-119">Rate limitations for this API are 15 calls per minute.</span></span>


## <a name="permissions"></a><span data-ttu-id="2daca-120">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="2daca-120">Permissions</span></span>

<span data-ttu-id="2daca-121">Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="2daca-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2daca-122">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="2daca-122">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="2daca-123">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="2daca-123">Permission type</span></span> |   <span data-ttu-id="2daca-124">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="2daca-124">Permission</span></span>  |   <span data-ttu-id="2daca-125">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="2daca-125">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2daca-126">Anwendung</span><span class="sxs-lookup"><span data-stu-id="2daca-126">Application</span></span> |   <span data-ttu-id="2daca-127">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="2daca-127">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="2daca-128">"Alle Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="2daca-128">'Read and write all alerts'</span></span>
<span data-ttu-id="2daca-129">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="2daca-129">Delegated (work or school account)</span></span> | <span data-ttu-id="2daca-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="2daca-130">Alert.ReadWrite</span></span> | <span data-ttu-id="2daca-131">"Warnungen lesen und schreiben"</span><span class="sxs-lookup"><span data-stu-id="2daca-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="2daca-132">Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:</span><span class="sxs-lookup"><span data-stu-id="2daca-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="2daca-133">Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Warnungsuntersuchung" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="2daca-133">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="2daca-134">Der Benutzer muss basierend auf den Gerätegruppeneinstellungen Zugriff auf das Gerät haben, das der Warnung zugeordnet ist (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="2daca-134">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="2daca-135">HTTP-Anforderung</span><span class="sxs-lookup"><span data-stu-id="2daca-135">HTTP request</span></span>

```
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

## <a name="request-headers"></a><span data-ttu-id="2daca-136">Anforderungsheader</span><span class="sxs-lookup"><span data-stu-id="2daca-136">Request headers</span></span>

<span data-ttu-id="2daca-137">Name</span><span class="sxs-lookup"><span data-stu-id="2daca-137">Name</span></span> | <span data-ttu-id="2daca-138">Typ</span><span class="sxs-lookup"><span data-stu-id="2daca-138">Type</span></span> | <span data-ttu-id="2daca-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2daca-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="2daca-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="2daca-140">Authorization</span></span> | <span data-ttu-id="2daca-141">String</span><span class="sxs-lookup"><span data-stu-id="2daca-141">String</span></span> | <span data-ttu-id="2daca-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="2daca-142">Bearer {token}.</span></span> <span data-ttu-id="2daca-143">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="2daca-143">**Required**.</span></span>
<span data-ttu-id="2daca-144">Content-Type</span><span class="sxs-lookup"><span data-stu-id="2daca-144">Content-Type</span></span> | <span data-ttu-id="2daca-145">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2daca-145">String</span></span> | <span data-ttu-id="2daca-146">application/json.</span><span class="sxs-lookup"><span data-stu-id="2daca-146">application/json.</span></span> <span data-ttu-id="2daca-147">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="2daca-147">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="2daca-148">Anforderungstext</span><span class="sxs-lookup"><span data-stu-id="2daca-148">Request body</span></span>

<span data-ttu-id="2daca-149">Geben Sie im Anforderungstext die folgenden Werte an (alle sind erforderlich):</span><span class="sxs-lookup"><span data-stu-id="2daca-149">In the request body, supply the following values (all are required):</span></span>

<span data-ttu-id="2daca-150">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="2daca-150">Property</span></span> | <span data-ttu-id="2daca-151">Typ</span><span class="sxs-lookup"><span data-stu-id="2daca-151">Type</span></span> | <span data-ttu-id="2daca-152">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2daca-152">Description</span></span>
:---|:---|:---
<span data-ttu-id="2daca-153">eventTime</span><span class="sxs-lookup"><span data-stu-id="2daca-153">eventTime</span></span> | <span data-ttu-id="2daca-154">DateTime(UTC)</span><span class="sxs-lookup"><span data-stu-id="2daca-154">DateTime(UTC)</span></span> | <span data-ttu-id="2daca-155">Der genaue Zeitpunkt des Ereignisses als Zeichenfolge, wie er von der erweiterten Suche abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="2daca-155">The precise time of the event as string, as obtained from advanced hunting.</span></span> <span data-ttu-id="2daca-156">z. B. ```2018-08-03T16:45:21.7115183Z``` **Erforderlich.**</span><span class="sxs-lookup"><span data-stu-id="2daca-156">e.g. ```2018-08-03T16:45:21.7115183Z``` **Required**.</span></span>
<span data-ttu-id="2daca-157">reportId</span><span class="sxs-lookup"><span data-stu-id="2daca-157">reportId</span></span> | <span data-ttu-id="2daca-158">String</span><span class="sxs-lookup"><span data-stu-id="2daca-158">String</span></span> | <span data-ttu-id="2daca-159">Die reportId des Ereignisses, wie sie von der erweiterten Suche abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="2daca-159">The reportId of the event, as obtained from advanced hunting.</span></span> <span data-ttu-id="2daca-160">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="2daca-160">**Required**.</span></span>
<span data-ttu-id="2daca-161">machineId</span><span class="sxs-lookup"><span data-stu-id="2daca-161">machineId</span></span> | <span data-ttu-id="2daca-162">String</span><span class="sxs-lookup"><span data-stu-id="2daca-162">String</span></span> | <span data-ttu-id="2daca-163">ID des Geräts, auf dem das Ereignis identifiziert wurde.</span><span class="sxs-lookup"><span data-stu-id="2daca-163">Id of the device on which the event was identified.</span></span> <span data-ttu-id="2daca-164">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="2daca-164">**Required**.</span></span>
<span data-ttu-id="2daca-165">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="2daca-165">severity</span></span> | <span data-ttu-id="2daca-166">String</span><span class="sxs-lookup"><span data-stu-id="2daca-166">String</span></span> | <span data-ttu-id="2daca-167">Der Schweregrad der Warnung.</span><span class="sxs-lookup"><span data-stu-id="2daca-167">Severity of the alert.</span></span> <span data-ttu-id="2daca-168">Die Eigenschaftswerte sind: 'Low', 'Medium' und 'High'.</span><span class="sxs-lookup"><span data-stu-id="2daca-168">The property values are: 'Low', 'Medium' and 'High'.</span></span> <span data-ttu-id="2daca-169">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="2daca-169">**Required**.</span></span>
<span data-ttu-id="2daca-170">title</span><span class="sxs-lookup"><span data-stu-id="2daca-170">title</span></span> | <span data-ttu-id="2daca-171">String</span><span class="sxs-lookup"><span data-stu-id="2daca-171">String</span></span> | <span data-ttu-id="2daca-172">Titel für die Warnung.</span><span class="sxs-lookup"><span data-stu-id="2daca-172">Title for the alert.</span></span> <span data-ttu-id="2daca-173">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="2daca-173">**Required**.</span></span>
<span data-ttu-id="2daca-174">description</span><span class="sxs-lookup"><span data-stu-id="2daca-174">description</span></span> | <span data-ttu-id="2daca-175">String</span><span class="sxs-lookup"><span data-stu-id="2daca-175">String</span></span> | <span data-ttu-id="2daca-176">Beschreibung der Warnung.</span><span class="sxs-lookup"><span data-stu-id="2daca-176">Description of the alert.</span></span> <span data-ttu-id="2daca-177">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="2daca-177">**Required**.</span></span>
<span data-ttu-id="2daca-178">recommendedAction</span><span class="sxs-lookup"><span data-stu-id="2daca-178">recommendedAction</span></span>| <span data-ttu-id="2daca-179">String</span><span class="sxs-lookup"><span data-stu-id="2daca-179">String</span></span> | <span data-ttu-id="2daca-180">Aktion, die vom Sicherheitsbeauftragten bei der Analyse der Warnung empfohlen wird.</span><span class="sxs-lookup"><span data-stu-id="2daca-180">Action that is recommended to be taken by security officer when analyzing the alert.</span></span> <span data-ttu-id="2daca-181">**Erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="2daca-181">**Required**.</span></span>
<span data-ttu-id="2daca-182">category</span><span class="sxs-lookup"><span data-stu-id="2daca-182">category</span></span>| <span data-ttu-id="2daca-183">String</span><span class="sxs-lookup"><span data-stu-id="2daca-183">String</span></span> | <span data-ttu-id="2daca-184">Die Kategorie der Warnung.</span><span class="sxs-lookup"><span data-stu-id="2daca-184">Category of the alert.</span></span> <span data-ttu-id="2daca-185">Die Eigenschaftswerte sind: "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistence", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required**.</span><span class="sxs-lookup"><span data-stu-id="2daca-185">The property values are: "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistence", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required**.</span></span>

## <a name="response"></a><span data-ttu-id="2daca-186">Antwort</span><span class="sxs-lookup"><span data-stu-id="2daca-186">Response</span></span>

<span data-ttu-id="2daca-187">Bei erfolgreicher Ausführung gibt die Methode 200 OK und ein neues [Warnungsobjekt](alerts.md) im Antworttext zurück.</span><span class="sxs-lookup"><span data-stu-id="2daca-187">If successful, this method returns 200 OK, and a new [alert](alerts.md) object in the response body.</span></span> <span data-ttu-id="2daca-188">Wenn das Ereignis mit den angegebenen Eigenschaften (_reportId_, _eventTime_ und _machineId_) nicht gefunden wurde – 404 Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="2daca-188">If event with the specified properties (_reportId_, _eventTime_ and _machineId_) was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="2daca-189">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2daca-189">Example</span></span>

<span data-ttu-id="2daca-190">**Anforderung**</span><span class="sxs-lookup"><span data-stu-id="2daca-190">**Request**</span></span>

<span data-ttu-id="2daca-191">Nachfolgend sehen Sie ein Beispiel der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="2daca-191">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

```json
{
    "machineId": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "severity": "Low",
    "title": "example",
    "description": "example alert",
    "recommendedAction": "nothing",
    "eventTime": "2018-08-03T16:45:21.7115183Z",
    "reportId": "20776",
    "category": "Exploit"
}
```
