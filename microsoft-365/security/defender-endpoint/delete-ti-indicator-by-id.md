---
title: Indikator-API löschen.
description: Erfahren Sie, wie Sie die Indikator-API zum Löschen einer Indikatorentität nach ID in Microsoft Defender für Endpunkt verwenden.
keywords: APIs, öffentliche API, unterstützte APIs, löschen, TI-Indikator, Entität, ID
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
ms.openlocfilehash: eaef6b25e2db72149a1a1128899d8a79a38a4c60
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771021"
---
# <a name="delete-indicator-api"></a>Indikator-API löschen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)  

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-Beschreibung
Löscht eine [](ti-indicator.md) Indikatorentität nach ID.


## <a name="limitations"></a>Begrenzungen
1. Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.


## <a name="permissions"></a>Berechtigungen
Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter ["Erste Schritte".](apis-intro.md)

Berechtigungstyp |   Berechtigung  |   Anzeigename der Berechtigung
:---|:---|:---
Anwendung |   Ti.ReadWrite |  "TI-Indikatoren lesen und schreiben"
Anwendung |   Ti.ReadWrite.All |  "Indikatoren lesen und schreiben"


## <a name="http-request"></a>HTTP-Anforderung
```
Delete https://api.securitycenter.microsoft.com/api/indicators/{id}
```

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="request-headers"></a>Anforderungsheader

Name | Typ | Beschreibung
:---|:---|:---
Authorization | String | Bearer {token}. **Erforderlich**.


## <a name="request-body"></a>Anforderungstext
Empty

## <a name="response"></a>Antwort
Wenn Indikator vorhanden und erfolgreich gelöscht – 204 OK ohne Inhalt.
Wenn indikator mit der angegebenen ID nicht gefunden wurde - 404 Nicht gefunden.

## <a name="example"></a>Beispiel

**Anforderung**

Nachfolgend sehen Sie ein Beispiel der Anforderung.

```http
DELETE https://api.securitycenter.microsoft.com/api/indicators/995
```
