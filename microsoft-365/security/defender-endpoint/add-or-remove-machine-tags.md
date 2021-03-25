---
title: Hinzufügen oder Entfernen der Computertags-API
description: Erfahren Sie, wie Sie mithilfe der API computertags hinzufügen oder entfernen ein Tag für einen Computer in Microsoft Defender for Endpoint hinzufügen oder entfernen.
keywords: apis, graph api, supported apis, tags, machine tags
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
ms.openlocfilehash: 98dd513cc66683ff1b95f66d6d7b89916ce54bab
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199775"
---
# <a name="add-or-remove-machine-tags-api"></a>Hinzufügen oder Entfernen der Computertags-API

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API-Beschreibung

Fügt einem bestimmten Computer ein Tag hinzu oder [entfernt es.](machine.md)

## <a name="limitations"></a>Einschränkungen

1. Sie können auf Computern posten, die zuletzt gemäß Ihrem konfigurierten Aufbewahrungszeitraum gesehen wurden.

2. Die Tarifeinschränkungen für diese API sind 100 Anrufe pro Minute und 1500 Anrufe pro Stunde.


## <a name="permissions"></a>Berechtigungen

Zum Aufrufen dieser API ist eine der folgenden Berechtigungen erforderlich. Weitere Informationen, einschließlich der Auswahl von Berechtigungen, finden Sie [unter Use Defender for Endpoint APIs](apis-intro.md)

Berechtigungstyp |    Berechtigung    |    Anzeigename der Berechtigung
:---|:---|:---
Anwendung |    Machine.ReadWrite.All |    "Alle Computerinformationen lesen und schreiben"
Delegiert (Geschäfts-, Schul- oder Unikonto) | Machine.ReadWrite | "Computerinformationen lesen und schreiben"

>[!Note]
> Beim Abrufen eines Tokens mithilfe von Benutzeranmeldeinformationen:
>
>- Der Benutzer benötigt mindestens die folgende Rollenberechtigung: "Sicherheitseinstellung verwalten". Weitere Informationen finden Sie unter [Erstellen und Verwalten von](user-roles.md) Rollen.
>- Der Benutzer muss auf der Grundlage der Computergruppeneinstellungen auf den Computer zugreifen können (weitere Informationen finden Sie unter [Erstellen](machine-groups.md) und Verwalten von Computergruppen).

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

Stellen Sie im Anforderungstext ein JSON-Objekt mit den folgenden Parametern zur Verfügung:

Parameter |    Typ    | Beschreibung
:---|:---|:---
Wert |    String |    Der Tagname. **Erforderlich**.
Aktion    | Enum |    Hinzufügen oder Entfernen. Zulässige Werte sind: "Hinzufügen" oder "Entfernen". **Erforderlich**.


## <a name="response"></a>Antwort

Wenn die Methode erfolgreich ist, werden der Antwortcode 200 – Ok und der aktualisierte Computer im Antworttext zurückgegeben.

## <a name="example"></a>Beispiel

**Anforderung**

Im Folgenden finden Sie ein Beispiel für eine Anforderung, die ein Computertag hinzufügt.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/tags
```

```json
{
  "Value" : "test Tag 2",
  "Action": "Add"
}
```

- Wenn Sie das Computertag entfernen möchten, legen Sie die Aktion im Anforderungstext auf "Entfernen" statt auf "Hinzufügen" festgelegt.
