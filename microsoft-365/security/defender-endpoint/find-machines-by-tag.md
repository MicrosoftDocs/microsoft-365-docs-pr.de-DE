---
title: Suchen von Geräten nach Tag-API
description: Suchen aller Geräte, die ein bestimmtes Tag enthalten
keywords: APIs, unterstützte APIs, abrufen, Gerät, suchen, Gerät suchen, nach Tag, Tag
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 88ad63d8b7cc71f7d3f809c7cb0371fc41bb9f5d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771165"
---
# <a name="find-devices-by-tag-api"></a>Suchen von Geräten nach Tag-API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:** [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API-Beschreibung
Suchen von [Computern](machine.md) nach [Tag](machine-tags.md).
<br>```startswith``` abfrage wird unterstützt. 

## <a name="limitations"></a>Begrenzungen
1. Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.


## <a name="permissions"></a>Berechtigungen
Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Microsoft Defender für Endpunkt-APIs](apis-intro.md)

Berechtigungstyp |   Berechtigung  |   Anzeigename der Berechtigung
:---|:---|:---
Anwendung |   Machine.Read.All |  "Alle Computerprofile lesen"
Anwendung |   Machine.ReadWrite.All | "Alle Computerinformationen lesen und schreiben"
Delegiert (Geschäfts-, Schul- oder Unikonto) | Machine.Read | "Computerinformationen lesen"
Delegiert (Geschäfts-, Schul- oder Unikonto) | Machine.ReadWrite | "Lesen und Schreiben von Computerinformationen"

>[!Note]
> Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:
> - Die Antwort enthält nur Geräte, auf die der Benutzer basierend auf den Gerätegruppeneinstellungen Zugriff hat (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)
> - Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Daten anzeigen" (Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen")](user-roles.md)
> - Die Antwort enthält nur Geräte, auf die der Benutzer basierend auf den Gerätegruppeneinstellungen Zugriff hat (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen).](machine-groups.md)

## <a name="http-request"></a>HTTP-Anforderung
```
GET /api/machines/findbytag?tag={tag}&useStartsWithFilter={true/false}
```

## <a name="request-headers"></a>Anforderungsheader

Name | Typ | Beschreibung
:---|:---|:---
Authorization | String | Bearer {token}. **Erforderlich**.

## <a name="request-uri-parameters"></a>Anforderungs-URI-Parameter

Name | Typ | Beschreibung
:---|:---|:---
tag | String | Der Tagname. **Erforderlich**.
useStartsWithFilter | Boolesch | Wenn der Wert auf "true" festgelegt ist, wird die Suche nach allen Geräten mit Tagnamen gesucht, die mit dem angegebenen Tag in der Abfrage beginnen. Standardwert ist false. **Optional**.

## <a name="request-body"></a>Anforderungstext
Empty

## <a name="response"></a>Antwort
Wenn erfolgreich – 200 OK mit der Liste der Computer im Antworttext.

## <a name="example"></a>Beispiel

**Anforderung**

Nachfolgend sehen Sie ein Beispiel der Anforderung.

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbytag?tag=testTag&useStartsWithFilter=true
```