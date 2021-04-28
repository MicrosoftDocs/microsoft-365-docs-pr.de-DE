---
title: Auflisten verfügbarer Geräte einer Korrekturaktivität
description: Gibt Informationen zu verfügbar gemachten Geräten für die angegebene Behebungsaufgabe zurück.
keywords: apis, remediation, remediation api, get, remediation tasks,
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
ms.openlocfilehash: 097d8d784ca7c02fce1fc0e9fc51bdc272951f4a
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061145"
---
# <a name="list-exposed-devices-of-one-remediation-activity"></a>Auflisten verfügbarer Geräte einer Korrekturaktivität

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-Beschreibung

Gibt Informationen zu verfügbar gemachten Geräten für die angegebene Behebungsaufgabe zurück.

[Erfahren Sie mehr über Korrekturaktivitäten](tvm-remediation.md).

## <a name="list-exposed-devices-associated-with-a-remediation-task-id"></a>Auflisten verfügbarer Geräte, die einer Problembehebungsaufgabe zugeordnet sind (id)

**URL:** GET: /api/remediationTasks/ \{ id \} /machineReferences

**Eigenschaftendetails**

Property (id) | Datentyp | Beschreibung | Beispiel
:---|:---|:---|:---
id | String | Geräte-ID | w2957837fwda8w9ae7f023dba081059dw8d94503
computerDnsName | String | Gerätename | PC-SRV2012R2Foo.UserNameVldNet.local
osPlatform | String | Gerätebetriebssystem | WindowsServer2012R2
rbacGroupName | String | Name der Gerätegruppe, der dieses Gerät zugeordnet ist | Server

## <a name="example"></a>Beispiel

**Anforderungsbeispiel**

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c/machinereferences
```

**Antwortbeispiel**

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

## <a name="see-also"></a>Siehe auch

- [Korrekturmethoden und -eigenschaften](get-remediation-methods-properties.md)

- [Get one remediation activity by Id](get-remediation-one-activity.md)

- [Auflisten aller Korrekturaktivitäten](get-remediation-all-activities.md)

- [Risikobasiertes Bedrohungsmanagement & Sicherheitsrisikoverwaltung](next-gen-threat-and-vuln-mgt.md)

- [Sicherheitsrisiken in Ihrer Organisation](tvm-weaknesses.md)
