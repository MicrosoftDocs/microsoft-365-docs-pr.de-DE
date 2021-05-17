---
title: Methoden und Eigenschaften für Empfehlung
description: Ruft die letzten Warnungen der obersten Version ab.
keywords: apis, graph api, supported apis, get, alerts, recent
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
ms.technology: mde
ms.openlocfilehash: 6ab4d4e1acab0e4b837195f64c369057d7ceb417
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198233"
---
# <a name="recommendation-resource-type"></a>Empfehlungsressourcentyp

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Methoden
Methode |Rückgabetyp |Beschreibung
:---|:---|:---
[Auflisten aller Empfehlungen](get-all-recommendations.md) | Empfehlungssammlung | Ruft eine Liste aller Sicherheitsempfehlungen ab, die die Organisation betreffen
[Empfehlung nach ID erhalten](get-recommendation-by-id.md) | Empfehlung | Ruft eine Sicherheitsempfehlung nach ihrer ID ab
[Herunterladen von Empfehlungssoftware](get-recommendation-software.md)| [Software](software.md) | Ruft eine Sicherheitsempfehlung im Zusammenhang mit einer bestimmten Software ab
[Geräte mit Empfehlungsempfehlungen](get-recommendation-machines.md)|MachineRef-Auflistung | Ruft eine Liste der Geräte ab, die der Sicherheitsempfehlung zugeordnet sind
[Sicherheitsrisiken für Empfehlungsempfehlungen erhalten](get-recommendation-vulnerabilities.md) | [Vulnerability-Auflistung](vulnerability.md) | Ruft eine Liste der Sicherheitsrisiken ab, die der Sicherheitsempfehlung zugeordnet sind


## <a name="properties"></a>Eigenschaften
Eigenschaft |   Typ   |   Beschreibung
:---|:---|:---
id | String | Empfehlungs-ID
productName | String | Verwandter Softwarename  
recommendationName | String | Empfehlungsname
Schwächen | Long | Anzahl der erkannten Sicherheitsrisiken
Anbieter | String | Verwandter Herstellername
recommendedVersion | String | Empfohlene Version
recommendationCategory | String | Empfehlungskategorie. Mögliche Werte sind: "Accounts", "Application", "Network", "OS", "SecurityStack
subCategory | String | Empfehlungsunterkategorie
severityScore | Gleitkommawert mit doppelter Genauigkeit | Potenzielle Auswirkungen der Konfiguration auf die Microsoft Secure Score for Devices (1-10) der Organisation
publicExploit | Boolescher Wert | Öffentlicher Exploit ist verfügbar 
activeAlert | Boolescher Wert | Dieser Empfehlung ist eine aktive Warnung zugeordnet.
associatedThreats | String collection | Dieser Empfehlung ist der Bericht zur Bedrohungsanalyse zugeordnet.
remediationType | String | Behebungstyp. Mögliche Werte sind: "ConfigurationChange","Update","Upgrade","Uninstall"
Status | Enum | Empfehlungsausnahmestatus. Mögliche Werte sind: "Aktiv" und "Ausnahme"
configScoreImpact | Gleitkommawert mit doppelter Genauigkeit | Auswirkungen von Microsoft Secure Score für Geräte
exposureImpacte | Gleitkommawert mit doppelter Genauigkeit | Auswirkung der Belichtungsergebnis
totalMachineCount | Long | Anzahl der installierten Geräte
exposedMachinesCount | Long | Anzahl der installierten Geräte, die Sicherheitsrisiken ausgesetzt sind
nonProductivityImpactedAssets | Long | Anzahl der geräte, die nicht betroffen sind  
relatedComponent | String |  Verwandte Softwarekomponente
