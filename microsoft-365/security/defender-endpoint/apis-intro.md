---
title: Zugreifen auf die Microsoft Defender für Endpoint-APIs
ms.reviewer: ''
description: Erfahren Sie, wie Sie APIs verwenden können, um Workflows zu automatisieren und Innovationen basierend auf Microsoft Defender for Endpoint-Funktionen zu entwickeln
keywords: apis, api, wdatp, open api, microsoft defender for endpoint api, microsoft defender atp, public api, supported apis, alerts, device, user, domain, ip, file, advanced hunting, query
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a91a401d5d57c7757bc043178c95dc42e7733b41
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571829"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a>Zugreifen auf die Microsoft Defender für Endpoint-APIs 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


**Gilt für:** 
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Melden Sie sich für eine kostenlose Testversion an.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



Defender for Endpoint macht einen Großteil seiner Daten und Aktionen über eine Reihe programmatischer APIs verfügbar. Mit diesen APIs können Sie Workflows automatisieren und auf der Grundlage von Defender for Endpoint-Funktionen innovativ sein. Der API-Zugriff erfordert eine OAuth2.0-Authentifizierung. Weitere Informationen finden Sie unter [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

In diesem Video erhalten Sie einen schnellen Überblick über die APIs von Defender für Endpoint. 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

Im Allgemeinen müssen Sie die folgenden Schritte ausführen, um die APIs zu verwenden:
- Erstellen einer [AAD-Anwendung](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)
- Abrufen eines Zugriffstokens mithilfe dieser Anwendung
- Verwenden des Tokens für den Zugriff auf Defender für Endpoint-API


Sie können auf Defender for Endpoint API mit **Anwendungskontext** oder **Benutzerkontext** zugreifen.

- **Anwendungskontext: (Empfohlen)** <br>
    Wird von Apps verwendet, die ohne einen angemeldeten Benutzer ausgeführt werden. z. B. Apps, die als Hintergrunddienste oder Daemons ausgeführt werden.

    Schritte, die für den Zugriff auf defender for Endpoint API mit Anwendungskontext ausgeführt werden müssen:

  1. Erstellen Sie eine AAD-Webanwendung.
  2. Weisen Sie der Anwendung die gewünschte Berechtigung zu, z. B. "Warnungen lesen", "Computer isolieren". 
  3. Erstellen Sie einen Schlüssel für diese Anwendung.
  4. Holen Sie Token mit der Anwendung mit seinem Schlüssel.
  5. Verwenden des Tokens für den Zugriff auf die Microsoft Defender for Endpoint-API

     Weitere Informationen finden Sie unter [Zugriff mit Anwendungskontext](exposed-apis-create-app-webapp.md)abrufen .


- **Benutzerkontext:** <br>
    Wird verwendet, um Aktionen in der API im Namen eines Benutzers auszuführen.

    Schritte für den Zugriff auf Defender for Endpoint API mit Anwendungskontext:

  1. Erstellen Sie AAD Native-Application.
  2. Weisen Sie der Anwendung die gewünschte Berechtigung zu, z. B. 'Warnungen lesen', 'Isolieren von Maschinen' usw. 
  3. Abrufen von Token mithilfe der Anwendung mit Benutzeranmeldeinformationen.
  4. Verwenden des Tokens für den Zugriff auf die Microsoft Defender for Endpoint-API

     Weitere Informationen finden Sie unter [Zugriff mit Benutzerkontext](exposed-apis-create-app-nativeapp.md)abrufen .


## <a name="related-topics"></a>Verwandte Themen
- [Microsoft Defender für Endpunkt-APIs](exposed-apis-list.md)
- [Zugriff auf Microsoft Defender für Endpoint mit Anwendungskontext](exposed-apis-create-app-webapp.md)
- [Zugriff auf Microsoft Defender für Endpoint mit Benutzerkontext](exposed-apis-create-app-nativeapp.md)
