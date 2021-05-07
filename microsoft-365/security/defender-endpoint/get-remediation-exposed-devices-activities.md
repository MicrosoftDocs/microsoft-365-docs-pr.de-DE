---
title: Auflisten verfügbarer Geräte einer Korrekturaktivität
description: Gibt Informationen zu verfügbar gemachten Geräten für die angegebene Behebungsaufgabe zurück.
keywords: apis, remediation, remediation api, get, remediation tasks, remediation exposed devices
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
ms.openlocfilehash: 92b5a93e86a20f36469d2b5cb606a8ddc2e97077
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241712"
---
# <a name="list-exposed-devices-of-one-remediation-activity"></a><span data-ttu-id="6a4be-104">Auflisten verfügbarer Geräte einer Korrekturaktivität</span><span class="sxs-lookup"><span data-stu-id="6a4be-104">List exposed devices of one remediation activity</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6a4be-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="6a4be-105">**Applies to:**</span></span>

- [<span data-ttu-id="6a4be-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6a4be-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6a4be-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6a4be-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6a4be-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="6a4be-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6a4be-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="6a4be-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="6a4be-110">API-Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6a4be-110">API Description</span></span>

<span data-ttu-id="6a4be-111">Gibt Informationen zu verfügbar gemachten Geräten für die angegebene Behebungsaufgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="6a4be-111">Returns information about exposed devices for the specified remediation task.</span></span>

<span data-ttu-id="6a4be-112">[Erfahren Sie mehr über Korrekturaktivitäten](tvm-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="6a4be-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-exposed-devices-associated-with-a-remediation-task-id"></a><span data-ttu-id="6a4be-113">Auflisten verfügbarer Geräte, die einer Problembehebungsaufgabe zugeordnet sind (id)</span><span class="sxs-lookup"><span data-stu-id="6a4be-113">List exposed devices associated with a remediation task (id)</span></span>

<span data-ttu-id="6a4be-114">**URL:** GET: /api/remediationTasks/ \{ id \} /machineReferences</span><span class="sxs-lookup"><span data-stu-id="6a4be-114">**URL:** GET: /api/remediationTasks/\{id\}/machineReferences</span></span>

## <a name="permissions"></a><span data-ttu-id="6a4be-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="6a4be-115">Permissions</span></span>

<span data-ttu-id="6a4be-116">Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6a4be-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6a4be-117">Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Use Microsoft Defender for Endpoint APIs for Details.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="6a4be-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="6a4be-118">Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="6a4be-118">Permission type</span></span> | <span data-ttu-id="6a4be-119">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="6a4be-119">Permission</span></span> | <span data-ttu-id="6a4be-120">Anzeigename der Berechtigung</span><span class="sxs-lookup"><span data-stu-id="6a4be-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="6a4be-121">Anwendung</span><span class="sxs-lookup"><span data-stu-id="6a4be-121">Application</span></span> | <span data-ttu-id="6a4be-122">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="6a4be-122">RemediationTask.Read.All</span></span> | <span data-ttu-id="6a4be-123">\'Informationen zu Sicherheitslücken in Bedrohungs- und Sicherheitsrisikoverwaltung lesen\'</span><span class="sxs-lookup"><span data-stu-id="6a4be-123">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="6a4be-124">Delegiert (Geschäfts-, Schul- oder Unikonto)</span><span class="sxs-lookup"><span data-stu-id="6a4be-124">Delegated (work or school account)</span></span> | <span data-ttu-id="6a4be-125">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="6a4be-125">RemediationTask.Read.Read</span></span> | <span data-ttu-id="6a4be-126">\'Informationen zu Sicherheitslücken in Bedrohungs- und Sicherheitsrisikoverwaltung lesen\'</span><span class="sxs-lookup"><span data-stu-id="6a4be-126">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties-details"></a><span data-ttu-id="6a4be-127">Eigenschaftendetails</span><span class="sxs-lookup"><span data-stu-id="6a4be-127">Properties details</span></span>

<span data-ttu-id="6a4be-128">Property (id)</span><span class="sxs-lookup"><span data-stu-id="6a4be-128">Property (id)</span></span> | <span data-ttu-id="6a4be-129">Datentyp</span><span class="sxs-lookup"><span data-stu-id="6a4be-129">Data type</span></span> | <span data-ttu-id="6a4be-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6a4be-130">Description</span></span> | <span data-ttu-id="6a4be-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6a4be-131">Example</span></span>
:---|:---|:---|:---
<span data-ttu-id="6a4be-132">id</span><span class="sxs-lookup"><span data-stu-id="6a4be-132">id</span></span> | <span data-ttu-id="6a4be-133">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6a4be-133">String</span></span> | <span data-ttu-id="6a4be-134">Geräte-ID</span><span class="sxs-lookup"><span data-stu-id="6a4be-134">Device ID</span></span> | <span data-ttu-id="6a4be-135">w2957837fwda8w9ae7f023dba081059dw8d94503</span><span class="sxs-lookup"><span data-stu-id="6a4be-135">w2957837fwda8w9ae7f023dba081059dw8d94503</span></span>
<span data-ttu-id="6a4be-136">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="6a4be-136">computerDnsName</span></span> | <span data-ttu-id="6a4be-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6a4be-137">String</span></span> | <span data-ttu-id="6a4be-138">Gerätename</span><span class="sxs-lookup"><span data-stu-id="6a4be-138">Device name</span></span> | <span data-ttu-id="6a4be-139">PC-SRV2012R2Foo.UserNameVldNet.local</span><span class="sxs-lookup"><span data-stu-id="6a4be-139">PC-SRV2012R2Foo.UserNameVldNet.local</span></span>
<span data-ttu-id="6a4be-140">osPlatform</span><span class="sxs-lookup"><span data-stu-id="6a4be-140">osPlatform</span></span> | <span data-ttu-id="6a4be-141">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6a4be-141">String</span></span> | <span data-ttu-id="6a4be-142">Gerätebetriebssystem</span><span class="sxs-lookup"><span data-stu-id="6a4be-142">Device operating system</span></span> | <span data-ttu-id="6a4be-143">WindowsServer2012R2</span><span class="sxs-lookup"><span data-stu-id="6a4be-143">WindowsServer2012R2</span></span>
<span data-ttu-id="6a4be-144">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="6a4be-144">rbacGroupName</span></span> | <span data-ttu-id="6a4be-145">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6a4be-145">String</span></span> | <span data-ttu-id="6a4be-146">Name der Gerätegruppe, der dieses Gerät zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="6a4be-146">Name of the device group this device is associated with</span></span> | <span data-ttu-id="6a4be-147">Server</span><span class="sxs-lookup"><span data-stu-id="6a4be-147">Servers</span></span>

## <a name="example"></a><span data-ttu-id="6a4be-148">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6a4be-148">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="6a4be-149">Anforderungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="6a4be-149">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c/machinereferences
```

### <a name="response-example"></a><span data-ttu-id="6a4be-150">Anforderungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="6a4be-150">Response example</span></span>

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "3cb5df6bb3640a2d37ad09fcd357b182d684fafc",
            "computerDnsName": "ComputerPII_2ea21b2d97c9df23c143ad9e3e454cb674232529.DomainPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3d9b1ca53e8f077199c7dcbfc9dbfa78f9bf1918",
            "computerDnsName": "ComputerPII_001d606fc149567c192747f48fae304b43c0ddba.DomainxPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3db8b27e6172951d7ea2e2d75945abec56feaf82",
            "computerDnsName": "ComputerPII_ce60cfbjj4b82a091deb5eae560332bba99a9bd7.DomainPII_0bc1aee0fa396d175e514bd61a9e7a5b2b07ee8e.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3bad326dcda5b53fab47408cd4a7080f3f3cc8ab",
            "computerDnsName": "ComputerPII_b6b35960dd6539d1d1cef5ada02e235e7b357408.DomainPII_21eed80b089e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",
            
        }
]
}
```

## <a name="see-also"></a><span data-ttu-id="6a4be-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a4be-151">See also</span></span>

- [<span data-ttu-id="6a4be-152">Korrekturmethoden und -eigenschaften</span><span class="sxs-lookup"><span data-stu-id="6a4be-152">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="6a4be-153">Erhalten einer Korrekturaktivität nach ID</span><span class="sxs-lookup"><span data-stu-id="6a4be-153">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="6a4be-154">Auflisten aller Korrekturaktivitäten</span><span class="sxs-lookup"><span data-stu-id="6a4be-154">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="6a4be-155">Risikobasierte Bedrohungsrisiken & Sicherheitsrisikomanagement</span><span class="sxs-lookup"><span data-stu-id="6a4be-155">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="6a4be-156">Sicherheitsrisiken in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="6a4be-156">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
