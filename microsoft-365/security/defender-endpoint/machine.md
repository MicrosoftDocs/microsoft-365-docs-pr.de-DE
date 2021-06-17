---
title: Computerressourcentyp
description: Erfahren Sie mehr über die Methoden und Eigenschaften des Machine-Ressourcentyps in Microsoft Defender für Endpunkt.
keywords: APIs, unterstützte APIs, abrufen, Computer
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
ms.openlocfilehash: 5ca147c9e69168b2f15aa69bba8728567b782fa9
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984460"
---
# <a name="machine-resource-type"></a>Computerressourcentyp

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Methoden

Methode|Rückgabetyp |Beschreibung
:---|:---|:---
[Auflisten von Computern](get-machines.md) | [Computersammlung](machine.md) | Listet [](machine.md) den Satz von Computerentitäten in der Organisation auf.
[Computer abrufen](get-machine-by-id.md) | [Maschine](machine.md) | Rufen Sie einen [Computer](machine.md) anhand seiner Identität ab.
[Angemeldete Benutzer abrufen](get-machine-log-on-users.md) | [user](user.md)-Sammlung | Rufen Sie die Gruppe von [Benutzern](user.md) ab, die sich auf dem [Computer](machine.md)angemeldet haben.
[Abrufen verwandter Warnungen](get-machine-related-alerts.md) | [Warnung](alerts.md) Sammlung | Rufen Sie den Satz von Warnungsentitäten ab, die auf dem [Computer](machine.md)ausgelöst wurden. [](alerts.md)
[Erhalten von installierter Software](get-installed-software.md) | [Softwaresammlung](software.md) | Ruft eine Auflistung der installierten Software im Zusammenhang mit einer bestimmten Computer-ID ab.
[Erhalten von entdeckten Sicherheitsrisiken](get-discovered-vulnerabilities.md) | [Sammlung von Sicherheitsrisiken](vulnerability.md) | Ruft eine Sammlung von ermittelten Sicherheitsrisiken im Zusammenhang mit einer bestimmten Computer-ID ab.
[Erhalten von Sicherheitsempfehlungen](get-security-recommendations.md) | [Empfehlungssammlung](recommendation.md) | Ruft eine Sammlung von Sicherheitsempfehlungen im Zusammenhang mit einer bestimmten Computer-ID ab.
[Hinzufügen oder Entfernen von Computertags](add-or-remove-machine-tags.md) | [Maschine](machine.md) | Hinzufügen oder Entfernen eines Tags zu einem bestimmten Computer.
[Suchen von Computern nach IP](find-machines-by-ip.md) | [Computersammlung](machine.md) | Suchen sie Computer, die mit IP angezeigt werden.
[Suchen von Computern nach Tag](find-machines-by-tag.md) | [Computersammlung](machine.md) | Suchen von Computern nach [Tag](machine-tags.md).
[Fehlende KBs erhalten](get-missing-kbs-machine.md) | KB-Auflistung | Abrufen einer Liste der fehlenden KBs, die der Computer-ID zugeordnet sind
[Setzen des Gerätewerts](set-device-value.md)| [Computersammlung](machine.md) | Legen Sie den [Wert eines Geräts](tvm-assign-device-value.md)fest.
[Aktualisieren des Computers](update-machine-method.md) |[Computersammlung](machine.md) | Dient zum Abrufen des Updatestatus eines Computers.

## <a name="properties"></a>Eigenschaften

Eigenschaft |   Typ   |   Beschreibung
:---|:---|:---
id | Zeichenfolge | [Computeridentität.](machine.md)
computerDnsName | Zeichenfolge | [Computer](machine.md) vollqualifizierte Name.
firstSeen | DateTimeOffset | Das erste Datum und die erste Uhrzeit, an dem der [Computer](machine.md) von Microsoft Defender für Endpunkt beobachtet wurde.
lastSeen | DateTimeOffset |Uhrzeit und Datum des letzten empfangenen vollständigen Geräteberichts. Ein Gerät sendet in der Regel alle 24 Stunden einen vollständigen Bericht.
osPlatform | Zeichenfolge | Betriebssystemplattform.
osProcessor | Zeichenfolge | Betriebssystemprozessor. Verwenden Sie stattdessen die osArchitecture-Eigenschaft.
Version | String | Betriebssystemversion.
osBuild | Nullable long | Buildnummer des Betriebssystems.
lastIpAddress | Zeichenfolge | Last IP on local NIC on the [machine](machine.md).
lastExternalIpAddress | Zeichenfolge | Letzte IP, über die der [Computer](machine.md) auf das Internet zugegriffen hat.
healthStatus | Enum | [](machine.md) Computerintegritätsstatus. Mögliche Werte sind: "Active", "Inactive", "ImpairedCommunication", "NoSensorData", "NoSensorDataImpairedCommunication" und "Unknown". 
rbacGroupName | Zeichenfolge | Computergruppenname.
riskScore | Nullable Enum | Risikobewertung gemäß Bewertung durch Microsoft Defender für Endpunkt. Mögliche Werte sind: "None", "Informational", "Low", "Medium" und "High".
exposureScore | Nullable Enum | Von Microsoft Defender für Endpunkt ausgewertete [Belichtungsbewertung.](tvm-exposure-score.md) Mögliche Werte sind: 'None', 'Low', 'Medium' und 'High'.
aadDeviceId | Guid für nullfähige Darstellung | AAD-Geräte-ID (wenn [der Computer](machine.md) AAD beigetreten ist).
machineTags | String-Sammlung | Satz [](machine.md) von Computertags.
exposureLevel | Nullable Enum | Belichtungsstufe, die von Microsoft Defender für Endpunkt ausgewertet wird. Mögliche Werte sind: 'None', 'Low', 'Medium' und 'High'.
deviceValue | Nullable Enum | Der [Wert des Geräts.](tvm-assign-device-value.md) Mögliche Werte sind: 'Normal', 'Low' und 'High'.
Ipaddresses | IpAddress-Sammlung | Satz von ***IpAddress-Objekten.*** Siehe "Abrufen der [Computer-API".](get-machines.md)
osArchitecture | Zeichenfolge | Betriebssystemarchitektur. Mögliche Werte sind: "32-Bit", "64-Bit". Verwenden Sie diese Eigenschaft anstelle von osProcessor.


