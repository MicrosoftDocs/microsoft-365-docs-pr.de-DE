---
title: Unterstützte Microsoft Defender for Endpoint-APIs
ms.reviewer: ''
description: Erfahren Sie mehr über die spezifischen unterstützten Microsoft Defender for Endpoint-Entitäten, an die Sie API-Aufrufe erstellen können.
keywords: apis, supported apis, actor, alerts, device, user, domain, ip, file, advanced queries, advanced hunting
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
ms.openlocfilehash: 77491620f7efa88f8ab249c2b76cd2532ba679dd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198322"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a>Unterstützte Microsoft Defender for Endpoint-APIs

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

## <a name="endpoint-uri-and-versioning"></a>Endpunkt-URI und Versionsing

### <a name="endpoint-uri"></a>Endpunkt-URI:            

> Der Dienstbasis-URI ist: https://api.securitycenter.microsoft.com
> 
> Die abfragenbasierten OData haben das Präfix "/api". Um z. B. Warnungen zu erhalten, können Sie eine GET-Anforderung an https://api.securitycenter.microsoft.com/api/alerts

### <a name="versioning"></a>Versionierung:

> Die API unterstützt die Versionsierung.
> 
> Die aktuelle Version ist **V1.0**.
> 
> Verwenden Sie dieses Format, um eine bestimmte Version zu verwenden: `https://api.securitycenter.microsoft.com/api/{Version}` . Beispiel: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`
> 
> Wenn Sie keine Version (z. B. ) angeben, erhalten Sie https://api.securitycenter.microsoft.com/api/alerts die neueste Version.


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Erfahren Sie mehr über die einzelnen unterstützten Entitäten, an die Sie API-Aufrufe ausführen können, sowie Details wie HTTP-Anforderungswerte, Anforderungsheader und erwartete Antworten.

## <a name="in-this-section"></a>Inhalt dieses Abschnitts

Thema | Beschreibung
:---|:---
Erweiterte Suche | Führen Sie Abfragen aus der API aus.
Warnungen | Führen Sie API-Aufrufe aus, z. B. Warnungen abrufen, Warnung erstellen, Warnung aktualisieren und vieles mehr.
Domänen | Führen Sie API-Aufrufe aus, z. B. domänenbezogene Geräte, Domänenstatistiken und vieles mehr.
Dateien | Führen Sie API-Aufrufe aus, z. B. Dateiinformationen abrufen, dateibezogene Warnungen, dateibezogene Geräte und Dateistatistiken.
IPs | Führen Sie API-Aufrufe aus, z. B. IP-bezogene Warnungen abrufen und IP-Statistiken abrufen.
Maschinen | Führen Sie API-Aufrufe aus, z. B. Geräte abrufen, Geräte nach ID abrufen, Informationen zu angemeldeten Benutzern, Bearbeiten von Tags und mehr.
Computeraktionen | Führen Sie API-Aufrufe wie Isolation, Virenschutzscan ausführen und vieles mehr aus.
Indikatoren | Führen Sie API-Aufrufe aus, z. B. Indikator erstellen, Indikatoren abrufen und Indikatoren löschen.
Benutzer | Führen Sie API-Aufrufe aus, z. B. benutzerbezogene Warnungen und benutzerbezogene Geräte.
Bewertung | Führen Sie API-Aufrufe aus, z. B. das Abrufen der Belichtungsergebnis oder das Abrufen der gerätesicheren Bewertung.
Software | Führen Sie API-Aufrufe wie z. B. das Auflisten von Sicherheitsrisiken nach Software aus.
Sicherheitsrisiko | Führen Sie API-Aufrufe wie z. B. Listengeräte nach Sicherheitsrisiko aus.
Empfehlung | Führen Sie API-Aufrufe wie Empfehlung nach ID abrufen aus.

## <a name="see-also"></a>Siehe auch
- [Microsoft Defender für Endpunkt-APIs](apis-intro.md)
