---
title: Unterstütze Microsoft Defender für Endpoint-APIs
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
ms.openlocfilehash: ab3d3aa9a13b71f65d3d4335646e32a7e4270242
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061049"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a>Unterstütze Microsoft Defender für Endpoint-APIs

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a>Endpunkt-URI und Versionsing

### <a name="endpoint-uri"></a>Endpunkt-URI

> Der Dienstbasis-URI ist: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)
>
> Die abfragenbasierten OData haben das Präfix "/api". Um z. B. Warnungen zu erhalten, können Sie eine GET-Anforderung an [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)

### <a name="versioning"></a>Versionsverwaltung

> Die API unterstützt die Versionsierung.
>
> Die aktuelle Version ist **V1.0**.
>
> Verwenden Sie dieses Format, um eine bestimmte Version zu verwenden: `https://api.securitycenter.microsoft.com/api/{Version}` . Beispiel: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`
>
> Wenn Sie keine Version (z. B. ) angeben, erhalten Sie `https://api.securitycenter.microsoft.com/api/alerts` die neueste Version.

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Erfahren Sie mehr über die einzelnen unterstützten Entitäten, an die Sie API-Aufrufe ausführen können, sowie Details wie HTTP-Anforderungswerte, Anforderungsheader und erwartete Antworten.

## <a name="in-this-section"></a>Inhalt dieses Abschnitts

Thema | Beschreibung
:---|:---
[Erweiterte Suche](run-advanced-query-api.md) | Führen Sie Abfragen aus der API aus.
[Warnungsmethoden und Eigenschaften](alerts.md) | Führen Sie API-Aufrufe \- aus, z. B. Warnungen abrufen, Warnung erstellen, Warnung aktualisieren und vieles mehr.
[Methoden und Eigenschaften der automatisierten Untersuchung](investigation.md) | Führen Sie API-Aufrufe aus, \- z. B. Abrufen der Untersuchung.
[Domänenbezogene Benachrichtigungen erhalten](get-domain-related-alerts.md) | Führen Sie API-Aufrufe aus, z. B. \- domänenbezogene Geräte, Domänenstatistiken und vieles mehr.
[Dateimethoden und -eigenschaften](files.md) | Führen Sie API-Aufrufe aus, z. \- B. Dateiinformationen abrufen, dateibezogene Warnungen, dateibezogene Geräte und Dateistatistiken.
[Methoden und Eigenschaften von Indikatoren](ti-indicator.md) | Führen Sie API-Aufrufe aus, z. \- B. Indikatoren abrufen, Indikator erstellen und Indikatoren löschen.
[IP-bezogene Benachrichtigungen erhalten](get-ip-related-alerts.md) | Führen Sie API-Aufrufe \- aus, z. B. IP-bezogene Warnungen abrufen und IP-Statistiken abrufen.
[Computermethoden und Eigenschaften](machine.md) | Führen Sie API-Aufrufe aus, z. B. Geräte abrufen, Geräte nach ID abrufen, Informationen zu angemeldeten \- Benutzern, Bearbeiten von Tags und mehr.
[Computer-Aktionsmethoden und Eigenschaften](machineaction.md) | Führen Sie API-Aufrufe \- wie Isolation, Virenschutzscan ausführen und vieles mehr aus.
[Methoden und Eigenschaften für Empfehlung](recommendation.md) | Führen Sie API-Aufrufe aus, \- z. B. Empfehlung nach ID abrufen.
[Methoden und Eigenschaften der Korrekturaktivität](get-remediation-methods-properties.md) | Führen Sie API-Aufrufe aus, z. B. alle Wartungsaufgaben abrufen, Aufgaben zur Behebung verfügbarer Geräte abrufen und eine Problembehebungsaufgabe \- nach ID abrufen.
[Bewertungsmethoden und -eigenschaften](score.md) | Führen Sie API-Aufrufe aus, z. B. das Abrufen \- der Belichtungsergebnis oder das Abrufen der gerätesicheren Bewertung.
[Softwaremethoden und -eigenschaften](software.md) | Führen Sie API-Aufrufe wie \- z. B. das Auflisten von Sicherheitsrisiken nach Software aus.
[Benutzermethoden](user.md) | Führen Sie API-Aufrufe aus, z. B. \- benutzerbezogene Warnungen und benutzerbezogene Geräte.
[Methoden und Eigenschaften für Sicherheitsrisiko](vulnerability.md) | Führen Sie API-Aufrufe wie \- z. B. Listengeräte nach Sicherheitsrisiko aus.

## <a name="see-also"></a>Siehe auch

- [Microsoft Defender für Endpunkt-APIs](apis-intro.md)

- [Versionshinweise zur Microsoft Defender for Endpoint-API](api-release-notes.md)
