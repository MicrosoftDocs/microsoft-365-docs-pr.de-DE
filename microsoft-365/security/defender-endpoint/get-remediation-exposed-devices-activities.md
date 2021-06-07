---
title: Auflisten verfügbarer Geräte einer Korrekturaktivität
description: Gibt Informationen zu verfügbar gemachten Geräten für die angegebene Korrekturaufgabe zurück.
keywords: APIs, Wartung, Korrektur-API, abrufen, Wartungsaufgaben, bereitgestellte Geräte zur Problembehebung
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
ms.openlocfilehash: 9b10659f76e5b05bea11f5c6c55ca7c2a34a2db5
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772161"
---
# <a name="list-exposed-devices-of-one-remediation-activity"></a>Auflisten verfügbarer Geräte einer Korrekturaktivität

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-Beschreibung

Gibt Informationen zu verfügbar gemachten Geräten für die angegebene Korrekturaufgabe zurück.

[Erfahren Sie mehr über Korrekturaktivitäten.](tvm-remediation.md)

## <a name="list-exposed-devices-associated-with-a-remediation-task-id"></a>Auflisten verfügbarer Geräte, die einer Korrekturaufgabe zugeordnet sind (ID)

**URL:** GET: /api/remediationTasks/id \{ \} /machineReferences

## <a name="permissions"></a>Berechtigungen

Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs.](apis-intro.md)

Berechtigungstyp | Berechtigung | Anzeigename der Berechtigung
:---|:---|:---
Anwendung | RemediationTask.Read.All | \'Lesen von Sicherheitsrisiko- und Sicherheitsrisikoverwaltungsinformationen\'
Delegiert (Geschäfts-, Schul- oder Unikonto) | RemediationTask.Read.Read | \'Lesen von Sicherheitsrisiko- und Sicherheitsrisikoverwaltungsinformationen\'

## <a name="properties-details"></a>Eigenschaftendetails

Eigenschaft (ID) | Datentyp | Beschreibung | Beispiel
:---|:---|:---|:---
id | String | Geräte-ID | w2957837fwda8w9ae7f023dba081059dw8d94503
computerDnsName | String | Gerätename | PC-SRV2012R2Foo.UserNameVldNet.local
osPlatform | String | Betriebssystem des Geräts | WindowsServer2012R2
rbacGroupName | String | Name der Gerätegruppe, der dieses Gerät zugeordnet ist | Server

## <a name="example"></a>Beispiel

### <a name="request-example"></a>Anforderungsbeispiel

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c/machinereferences
```

### <a name="response-example"></a>Anforderungsbeispiel

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

- [Erhalten einer Korrekturaktivität nach ID](get-remediation-one-activity.md)

- [Auflisten aller Korrekturaktivitäten](get-remediation-all-activities.md)

- [Risikobasierte Bedrohungs-& Sicherheitsrisikomanagement](next-gen-threat-and-vuln-mgt.md)

- [Sicherheitsrisiken in Ihrer Organisation](tvm-weaknesses.md)
