---
title: Unterstütze Microsoft Defender für Endpoint-APIs
ms.reviewer: ''
description: Erfahren Sie mehr über die spezifischen unterstützten Microsoft Defender für Endpunkt-Entitäten, an die Sie API-Aufrufe erstellen können.
keywords: APIs, unterstützte APIs, Actor, Warnungen, Gerät, Benutzer, Domäne, IP, Datei, erweiterte Abfragen, erweiterte Suche
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
ms.openlocfilehash: 63e38d5c9cfe50d1fa4cda1f7ae9c7df55a45083
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788835"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a>Unterstütze Microsoft Defender für Endpoint-APIs

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a>Endpunkt-URI und Versionsverwaltung

### <a name="endpoint-uri"></a>Endpunkt-URI

> Der Dienstbasis-URI lautet: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)
>
> Die abfragebasierten OData-Daten haben das Präfix "/api". Um beispielsweise Benachrichtigungen zu erhalten, können Sie eine GET-Anforderung an [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)

### <a name="versioning"></a>Versionsverwaltung

> Die API unterstützt die Versionsverwaltung.
>
> Die aktuelle Version ist **V1.0.**
>
> Verwenden Sie das folgende Format, um eine bestimmte Version zu verwenden: `https://api.securitycenter.microsoft.com/api/{Version}` . Beispiel: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`
>
> Wenn Sie keine Version (z. B. ) angeben, `https://api.securitycenter.microsoft.com/api/alerts` erhalten Sie die neueste Version.

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Erfahren Sie mehr über die einzelnen unterstützten Entitäten, an die Sie API-Aufrufe ausführen können, sowie Details wie HTTP-Anforderungswerte, Anforderungsheader und erwartete Antworten.

## <a name="in-this-section"></a>Inhalt dieses Abschnitts

Thema | Beschreibung
:---|:---
[Erweiterte Suche](run-advanced-query-api.md) | Führen Sie Abfragen aus der API aus.
[Warnungsmethoden und Eigenschaften](alerts.md) | Führen Sie API-Aufrufe aus, z. \- B. Warnungen abrufen, Warnung erstellen, Warnung aktualisieren und vieles mehr.
[Exportieren von Bewertungsmethoden und Eigenschaften pro Gerät](get-assessment-methods-properties.md) | Führen Sie API-Aufrufe aus, z. B. die Bewertung der sicheren Konfiguration exportieren, die Bewertung des \- Softwarebestands exportieren und die Bewertung von Software-Sicherheitsrisiken exportieren.
[Automatisierte Untersuchungsmethoden und -eigenschaften](investigation.md) | Führen Sie API-Aufrufe aus, \- z. B. abrufen einer Sammlung von Untersuchungen.
[Domänenbezogene Benachrichtigungen erhalten](get-domain-related-alerts.md) | Führen Sie API-Aufrufe aus, z. \- B. abrufen von domänenbezogenen Geräten, Domänenstatistiken und mehr.
[Dateimethoden und -eigenschaften](files.md) | Führen Sie API-Aufrufe aus, z. B. das Abrufen von \- Dateiinformationen, dateibezogenen Warnungen, dateibezogenen Geräten und Dateistatistiken.
[Methoden und Eigenschaften von Indikatoren](ti-indicator.md) | Führen Sie API-Aufrufe aus, z. \- B. "Indikatoren abrufen", "Indikator erstellen" und "Indikatoren löschen".
[IP-bezogene Benachrichtigungen erhalten](get-ip-related-alerts.md) | Führen Sie API-Aufrufe aus, z. \- B. ip-bezogene Warnungen abrufen und IP-Statistiken abrufen.
[Computermethoden und Eigenschaften](machine.md) | Führen Sie API-Aufrufe aus, z. B. \- Abrufen von Geräten, Abrufen von Geräten nach ID, Informationen zu angemeldeten Benutzern, Bearbeiten von Tags und mehr.
[Computer-Aktionsmethoden und Eigenschaften](machineaction.md) | Führen Sie API-Aufrufe wie \- Isolation, Virenscan und vieles mehr aus.
[Methoden und Eigenschaften für Empfehlung](recommendation.md) | Führen Sie API-Aufrufe aus, z. \- B. "Empfehlung nach ID abrufen".
[Methoden und Eigenschaften der Korrekturaktivität](get-remediation-methods-properties.md) | Führen Sie API-Aufrufe aus, z. \- B. alle Wartungsaufgaben abrufen, die Problembehebungsaufgabe für offen gelegte Geräte abrufen und eine Korrekturaufgabe nach ID abrufen.
[Bewertungsmethoden und -eigenschaften](score.md) | Führen Sie API-Aufrufe aus, z. \- B. das Abrufen der Belichtungsbewertung oder die Geräte-Sicherheitsbewertung.
[Softwaremethoden und -eigenschaften](software.md) | Führen Sie API-Aufrufe wie \- z. B. Sicherheitsrisiken nach Software auf.
[Benutzermethoden](user.md) | Führen Sie API-Aufrufe aus, z. \- B. das Abrufen von benutzerbezogenen Warnungen und benutzerbezogenen Geräten.
[Methoden und Eigenschaften für Sicherheitsrisiko](vulnerability.md) | Führen Sie API-Aufrufe, z. \- B. Geräte nach Sicherheitsrisiko auflisten, aus.

## <a name="see-also"></a>Siehe auch

- [Microsoft Defender für Endpunkt-APIs](apis-intro.md)

- [Versionshinweise zur Microsoft Defender für Endpunkt-API](api-release-notes.md)
