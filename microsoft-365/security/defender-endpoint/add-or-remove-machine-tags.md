---
title: Hinzufügen oder Entfernen der Computertag-API
description: Erfahren Sie, wie Sie die Api zum Hinzufügen oder Entfernen von Computertags verwenden, um ein Tag für einen Computer in Microsoft Defender für Endpunkt hinzuzufügen oder zu entfernen.
keywords: APIs, Graph-API, unterstützte APIs, Tags, Computertags
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
ms.openlocfilehash: 3818fc0050790b2c3b307f95ee0760c516cbf893
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769821"
---
# <a name="add-or-remove-machine-tags-api"></a>Hinzufügen oder Entfernen der Computertag-API

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-Beschreibung

Fügt einem bestimmten [Computer](machine.md)ein Tag hinzu oder entfernt es.

## <a name="limitations"></a>Begrenzungen

1. Sie können Beiträge auf Computern bereitstellen, die zuletzt gemäß Ihrem konfigurierten Aufbewahrungszeitraum angezeigt wurden.

2. Die Rateneinschränkungen für diese API liegen bei 100 Aufrufen pro Minute und 1500 Aufrufen pro Stunde.


## <a name="permissions"></a>Berechtigungen

Eine der folgenden Berechtigungen ist erforderlich, um diese API aufzurufen. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie unter [Verwenden von Defender für Endpunkt-APIs](apis-intro.md)

Berechtigungstyp |    Berechtigung    |    Anzeigename der Berechtigung
:---|:---|:---
Anwendung |    Machine.ReadWrite.All |    "Alle Computerinformationen lesen und schreiben"
Delegiert (Geschäfts-, Schul- oder Unikonto) | Machine.ReadWrite | "Lesen und Schreiben von Computerinformationen"

>[!Note]
> Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:
>
>- Der Benutzer muss mindestens über die folgende Rollenberechtigung verfügen: "Sicherheitseinstellung verwalten". Weitere Informationen (weitere Informationen finden Sie unter [Erstellen und Verwalten von Rollen)](user-roles.md)
>- Der Benutzer muss basierend auf den Computergruppeneinstellungen Zugriff auf den Computer haben (Weitere Informationen finden Sie unter [Erstellen und Verwalten von Computergruppen).](machine-groups.md)

## <a name="http-request"></a>HTTP-Anforderung

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/tags
```

## <a name="request-headers"></a>Anforderungsheader

Name | Typ | Beschreibung
:---|:---|:---
Authorization | String | Bearer {token}. **Erforderlich**.
Content-Type | Zeichenfolge | application/json. **Erforderlich**.

## <a name="request-body"></a>Anforderungstext

Geben Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern an:

Parameter |    Typ    | Beschreibung
:---|:---|:---
Wert |    String |    Der Tagname. **Erforderlich**.
Aktion    | Enum |    Hinzufügen oder Entfernen. Zulässige Werte sind: 'Add' oder 'Remove'. **Erforderlich**.


## <a name="response"></a>Antwort

Wenn die Methode erfolgreich ist, werden der Antwortcode "200 – Ok" und der aktualisierte Computer im Antworttext zurückgegeben.

## <a name="example"></a>Beispiel

**Anforderung**

Nachfolgend sehen Sie ein Beispiel für eine Anforderung, die ein Computertag hinzufügt.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/tags
```

```json
{
  "Value" : "test Tag 2",
  "Action": "Add"
}
```

- Um das Computertag zu entfernen, legen Sie die Aktion im Anforderungstext auf "Entfernen" anstelle von "Hinzufügen" fest.
