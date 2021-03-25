---
title: Computerressourcentyp
description: Erfahren Sie mehr über die Methoden und Eigenschaften des Ressourcentyps Machine in Microsoft Defender for Endpoint.
keywords: apis, supported apis, get, machines
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
ms.technology: mde
ms.openlocfilehash: f96cfd56cb8d61bc62c34e2b1ee08d6313c6a8ad
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186641"
---
# <a name="machine-resource-type"></a>Computerressourcentyp

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Methoden

Methode|Rückgabetyp |Beschreibung
:---|:---|:---
[Auflisten von Computern](get-machines.md) | [Computersammlung](machine.md) | Listet den [Satz von Computerentitäten](machine.md) in der Organisation auf.
[Computer erhalten](get-machine-by-id.md) | [machine](machine.md) | Einen Computer [nach](machine.md) seiner Identität erhalten.
[Angemeldete Benutzer erhalten](get-machine-log-on-users.md) | [user](user.md)-Sammlung | Get the set of [User](user.md) that logged on the [machine](machine.md).
[Erhalten verwandter Warnungen](get-machine-related-alerts.md) | [Warnung](alerts.md) Sammlung | Get the set of [alert](alerts.md) entities that were raised on the [machine](machine.md).
[Installieren von Software](get-installed-software.md) | [Softwaresammlung](software.md) | Ruft eine Sammlung installierter Software im Zusammenhang mit einer bestimmten Computer-ID ab.
[Entdecken von Sicherheitsrisiken](get-discovered-vulnerabilities.md) | [Vulnerability-Auflistung](vulnerability.md) | Ruft eine Sammlung von entdeckten Sicherheitsrisiken im Zusammenhang mit einer bestimmten Computer-ID ab.
[Sicherheitsempfehlungen erhalten](get-security-recommendations.md) | [Empfehlungssammlung](recommendation.md) | Ruft eine Sammlung von Sicherheitsempfehlungen im Zusammenhang mit einer bestimmten Computer-ID ab.
[Hinzufügen oder Entfernen von Computertags](add-or-remove-machine-tags.md) | [machine](machine.md) | Hinzufügen oder Entfernen eines Tags zu einem bestimmten Computer.
[Suchen von Computern nach IP](find-machines-by-ip.md) | [Computersammlung](machine.md) | Suchen von Computern, die mit IP gesehen werden.
[Suchen von Computern nach Tag](find-machines-by-tag.md) | [Computersammlung](machine.md) | Suchen von Computern nach [Tag](machine-tags.md).
[Fehlende KBs erhalten](get-missing-kbs-machine.md) | KB-Auflistung | Erhalten einer Liste fehlender KBs, die der Computer-ID zugeordnet sind
[Festlegen des Gerätewerts](set-device-value.md)| [Computersammlung](machine.md) | Legen Sie [den Wert eines Geräts .](tvm-assign-device-value.md)

## <a name="properties"></a>Eigenschaften

Eigenschaft |   Typ   |   Beschreibung
:---|:---|:---
id | String | [Computeridentität.](machine.md)
computerDnsName | String | [vollqualifizierten](machine.md) Namen des Computers.
firstSeen | DateTimeOffset | Datum und Uhrzeit des ersten [Zeitpunkts, an dem der](machine.md) Computer von Microsoft Defender for Endpoint beobachtet wurde.
lastSeen | DateTimeOffset |Uhrzeit und Datum des letzten empfangenen vollständigen Geräteberichts. Ein Gerät sendet in der Regel alle 24 Stunden einen vollständigen Bericht.
osPlatform | String | Betriebssystemplattform.
osProcessor | String | Betriebssystemprozessor.
Version | String | Betriebssystemversion.
osBuild | Nullable long | Buildnummer des Betriebssystems.
lastIpAddress | String | Letzte IP auf der lokalen NIC auf dem [Computer](machine.md).
lastExternalIpAddress | String | Letzte IP, über die [der Computer](machine.md) auf das Internet zugegriffen hat.
healthStatus | Enum | [Zustand des](machine.md) Computers. Mögliche Werte sind: "Active", "Inactive", "ImpairedCommunication", "NoSensorData", "NoSensorDataImpairedCommunication" und "Unknown". 
rbacGroupName | String | Computergruppenname.
riskScore | Nullable Enum | Risikobewertung, wie von Microsoft Defender for Endpoint ausgewertet. Mögliche Werte sind: "None", "Informational", "Low", "Medium" und "High".
exposureScore | Nullable Enum | [Belichtungsergebnis,](tvm-exposure-score.md) wie von Microsoft Defender for Endpoint ausgewertet. Mögliche Werte sind: "None", "Low", "Medium" und "High".
aadDeviceId | Guid für nullierbare Darstellung | AAD-Geräte-ID (wenn [der Computer](machine.md) mit AAD verbunden ist).
machineTags | String-Sammlung | Satz von [Computertags.](machine.md)
exposureLevel | Nullable Enum | Die Belichtungsstufe wird von Microsoft Defender for Endpoint ausgewertet. Mögliche Werte sind: "None", "Low", "Medium" und "High".
deviceValue | Nullable Enum | Der [Wert des Geräts](tvm-assign-device-value.md). Mögliche Werte sind: "Normal", "Niedrig" und "Hoch".
ipAddresses | IpAddress-Auflistung | Satz von ***IpAddress-Objekten.*** Weitere [Informationen finden Sie unter Abrufen der Computer-API](get-machines.md).


