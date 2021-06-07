---
title: Methoden und Eigenschaften für Empfehlung
description: Ruft die wichtigsten Warnungen der letzten Zeit ab.
keywords: APIs, Graph-API, unterstützte APIs, abrufen, Warnungen, zuletzt verwendet
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: bd7aa2af2c7500bbe02108bb8aa5dee452ff2998
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771597"
---
# <a name="recommendation-resource-type"></a>Empfehlungsressourcentyp

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

> Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Methoden
Methode |Rückgabetyp |Beschreibung
:---|:---|:---
[Auflisten aller Empfehlungen](get-all-recommendations.md) | Empfehlungssammlung | Ruft eine Liste aller Sicherheitsempfehlungen ab, die sich auf die Organisation auswirken.
[Empfehlung nach ID erhalten](get-recommendation-by-id.md) | Empfehlung | Ruft eine Sicherheitsempfehlung anhand ihrer ID ab.
[Empfehlungssoftware abrufen](get-recommendation-software.md)| [Software](software.md) | Ruft eine Sicherheitsempfehlung im Zusammenhang mit einer bestimmten Software ab.
[Empfehlungsgeräte abrufen](get-recommendation-machines.md)|MachineRef-Sammlung | Ruft eine Liste der Geräte ab, die der Sicherheitsempfehlung zugeordnet sind
[Empfehlungs-Sicherheitsrisiken abrufen](get-recommendation-vulnerabilities.md) | [Sammlung von Sicherheitsrisiken](vulnerability.md) | Ruft eine Liste der Sicherheitsrisiken im Zusammenhang mit der Sicherheitsempfehlung ab.


## <a name="properties"></a>Eigenschaften
Eigenschaft |   Typ   |   Beschreibung
:---|:---|:---
id | String | Empfehlungs-ID
productName | String | Verwandter Softwarename  
recommendationName | String | Empfehlungsname
Schwächen | Long | Anzahl der entdeckten Sicherheitsrisiken
Anbieter | String | Name des zugehörigen Anbieters
recommendedVersion | String | Empfohlene Version
recommendationCategory | String | Empfehlungskategorie. Mögliche Werte sind: "Accounts", "Application", "Network", "OS", "SecurityStack
Unterkategorie | String | Empfehlungsunterkategorie
severityScore | Gleitkommawert mit doppelter Genauigkeit | Mögliche Auswirkungen der Konfiguration auf die Microsoft-Sicherheitsbewertung für Geräte (1-10)
publicExploit | Boolesch | Öffentlicher Exploit verfügbar 
activeAlert | Boolesch | Dieser Empfehlung ist eine aktive Warnung zugeordnet.
associatedThreats | String collection | Dieser Empfehlung ist der Bericht "Bedrohungsanalyse" zugeordnet.
remediationType | String | Korrekturtyp. Mögliche Werte sind: "ConfigurationChange","Update","Upgrade","Uninstall"
Status | Enum | Empfehlungsausnahmestatus. Mögliche Werte sind: "Active" und "Exception"
configScoreImpact | Gleitkommawert mit doppelter Genauigkeit | Auswirkungen der Microsoft-Sicherheitsbewertung für Geräte
exposureImpacte | Gleitkommawert mit doppelter Genauigkeit | Auswirkung der Belichtungsbewertung
totalMachineCount | Long | Anzahl der installierten Geräte
exposedMachinesCount | Long | Anzahl der installierten Geräte, die Sicherheitsrisiken ausgesetzt sind
nonProductivityImpactedAssets | Long | Anzahl der Geräte, die nicht betroffen sind  
relatedComponent | String |  Verwandte Softwarekomponente
